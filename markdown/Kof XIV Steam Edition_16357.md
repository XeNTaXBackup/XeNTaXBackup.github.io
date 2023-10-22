## Post #1
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2017-06-03T21:04:42+00:00
- Post Title: Kof XIV Steam Edition

Here's the quickbms to extract wad file, made by Aluigi:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "AGAR"
get DUMMY long  # 1
get DUMMY long  # 1
get DUMMY long  # 0
get SIZE long
savepos OFFSET

# TOC
set KEY binary "\xfa\x52\x38\x8c\x66\xd6\x55\xfa\x1a\xfc\x2b\x6f\x97\xd8\x41\x41\xa9\x90\xb4\x41\xd4\xd2\xca\xb7\xa3\x82\xaf\x6d\x8d\xf7\x83\x2f\x82\xaf\x27\xa6\x1e\xc5\x26\x29\x9c\x1c\x6e\x23\xf5\xe4\xa0\xbe\x13\x4f\x13\xe1\x71\xf6\xfe\x31"
math KEYSZ = 0x38

callfunction SET_ENCRYPTION 1
log MEMORY_FILE OFFSET SIZE 0 XSIZE

math BASE_OFF = OFFSET
math BASE_OFF + XSIZE
math BASE_OFF x 8

# weird directory structure
set KEY binary "\x45\xaa\xb7\x2a\x4f\xb3\x1d\xe1\x66\x39\x2f\x5b\xd8\x23\x1f\xa4\xa3\xda\x89\xe5\x5e\x28\x9e\x18\x2c\x68\x71\x39\xec\x8d\xd6\x1a\xcd\xd3\xf8\x3d\xe5\x59\xe5\xd5\x8d\x19\x58\x6a\x9c\x9a\xd3\x81\x3c\xdd\xab\x81\xd8\x46\xda\xb7"
math KEYSZ = 0x38

# lame work-around!!!
math SIZE * 4
math SIZE | 0x80000000
callfunction SET_ENCRYPTION 1
log MEMORY_FILE2 BASE_OFF SIZE
findloc TMP binary "\x00\x01" MEMORY_FILE2
math TMP + 2
math TMP x 8
math BASE_OFF + TMP
print "guessed base offset %BASE_OFF|X%"

# keys for the files
putarray 0 0  "\x98\x3b\xa6\xcc\xa7\x52\x32\xf9\x23\xbb\xe8\x7d\x39\x6c\xb7\x4e"
putarray 0 1  "\x13\xc7\xe8\x81\xd9\x8c\x75\x16\xf3\x2f\xbb\xf4\x21\x56\xb1\xa6"
putarray 0 2  "\x38\x50\x7b\x33\xee\xe5\xf0\x53\x4c\x5d\x2f\xc7\xf1\x65\xb8\x4a"
putarray 0 3  "\xc4\x55\x7f\x7c\xba\xb4\x42\x91\xee\x51\x2e\x37\xeb\x23\xaf\x54"
putarray 0 4  "\x23\xeb\x2d\xe6\xf7\x49\x92\x7c\x82\xfd\xec\x8e\xdc\x9f\x3e\xbc"
putarray 0 5  "\xcb\x49\xd8\x7c\xcc\x59\x7b\xca\x2d\xe2\x24\xb7\x19\x36\x37\x4d"
putarray 0 6  "\x2d\x3a\xfb\x28\x54\x21\x50\xb4\xa0\x77\xb8\xbb\xbf\xe8\xb1\x67"
putarray 0 7  "\xe3\x6f\xb2\xef\x65\x2b\xa2\x3a\x58\x2a\xba\x1f\xae\x68\xec\xbc"
putarray 0 8  "\xe7\x1e\x3d\xd6\xf5\xe2\x87\x9f\x68\xa1\x8b\xbb\xc7\xd4\xf2\x7d"
putarray 0 9  "\x3e\x3a\x10\xe4\xc1\x7b\xdf\x72\x39\x46\x40\x16\xfe\x94\x6b\xb5"
putarray 0 10 "\x20\x59\x25\xb9\xa6\x6b\x77\xc0\xbd\x4e\xe0\xbd\x1a\x25\x64\x3b"
putarray 0 11 "\x3f\xd0\x85\x35\x18\xd3\x8c\x59\x89\xc6\xd6\x61\x82\xb8\x5f\x75"
putarray 0 12 "\x25\x2b\xbc\xe5\x3a\xb3\x8b\x75\xb1\x2c\x7a\xdf\x98\xe6\x57\x8b"
putarray 0 13 "\x81\x6a\xcb\xb0\x8b\x17\x15\x10\x40\x53\x7b\x4a\x8a\xce\x77\x18"
putarray 0 14 "\x44\xc9\xcb\xd2\xb1\x76\xed\x2b\x18\xc6\x95\xc9\xd9\xda\x5a\xec"
putarray 0 15 "\x6b\x88\xa6\xd4\x16\x57\x3d\xd0\xb2\x4d\x1f\xf2\x48\x73\x17\x44"
math KEYSZ = 0x10

get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get SIZE long MEMORY_FILE
    get DUMMY long MEMORY_FILE  # 0xffffffff or zero
    get OFFSET longlong MEMORY_FILE
    math OFFSET + BASE_OFF

    # lame guessing, the algorithm to know the idx is probably very easy so I leave you the fun
    if SIZE & 0x80000000
    callfunction LAME_GUESS_IDX 1
    endif

    math KEY_IDX & 0xf
    getarray KEY 0 KEY_IDX
    string KEY x KEY

    callfunction SET_ENCRYPTION 1
    log NAME OFFSET SIZE 0 XSIZE
next i

startfunction SET_ENCRYPTION
    if SIZE & 0x80000000    # DUMMY is -1 else is zero
        math SIZE & 0x7fffffff
        math XSIZE = SIZE
        math XSIZE x 8
        encryption blowfish KEY "" 0 KEYSZ
    else
        math XSIZE = SIZE
        encryption "" ""
    endif
endfunction

startfunction LAME_GUESS_IDX
    for KEY_IDX = 0 < 16
        getarray KEY 0 KEY_IDX
        string KEY x KEY
        encryption blowfish KEY "" 0 KEYSZ
        log MEMORY_FILE3 OFFSET 8
        math OK = 0
        for x = 0 < 8
            get TMP byte MEMORY_FILE3
            if TMP >= 0 && TMP < 0x80
                math OK + 1
            endif
        next x
        if OK >= 8
            break
        endif
    next KEY_IDX
endfunction
```


samples:

[http://www.mediafire.com/file/oovrvi8has5d18b/Chara.rar](http://www.mediafire.com/file/oovrvi8has5d18b/Chara.rar)

Almost all textures can be exported with noesis except the png ones.
## Post #2
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2017-06-20T11:33:55+00:00
- Post Title: Kof XIV Steam Edition

seems they changed the crypt keys already
## Post #3
- Username: Brilleas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 22, 2014 8:50 pm
- Post datetime: 2017-06-27T02:16:52+00:00
- Post Title: Kof XIV Steam Edition

Have any script for model Hear?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-06-27T09:04:26+00:00
- Post Title: Kof XIV Steam Edition

A lot of the files do not decrpt correctly with the current script. I am going to re write the bms script to make the files extract correctly.
## Post #5
- Username: Brilleas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 22, 2014 8:50 pm
- Post datetime: 2017-06-28T09:55:46+00:00
- Post Title: Kof XIV Steam Edition

Thank you very much.chrrox.I'm waiting for it.
## Post #6
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2017-07-13T02:00:52+00:00
- Post Title: Kof XIV Steam Edition

> Reply from Thony
>
> bump

Jesischrist:

> A lot of the files do not decrpt correctly with the current script. I am going to re write the bms script to make the files extract correctly.

There won't be any model script until all the files can be decripted and extracted correctly.
## Post #7
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2017-07-13T13:17:27+00:00
- Post Title: Kof XIV Steam Edition

yes, actually we stay tuned for more info about the update to this script
## Post #8
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-07-27T23:30:04+00:00
- Post Title: Kof XIV Steam Edition

I have a question regarding the script.

For the "Guessing" part, it runs the blowfish algorithm 16 times on the PNG until it matches the header. But how does injecting work? I mean you have to encrypt now. You can't "guess" the encryption key, because each output of the 16 is considered working. Someone please correct me.




Anyways, I fixed the PNG decryption and here it goes:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "AGAR"
get DUMMY long  # 1
get DUMMY long  # 1
get DUMMY long  # 0
get SIZE long
savepos OFFSET

# TOC
set KEY binary "\xfa\x52\x38\x8c\x66\xd6\x55\xfa\x1a\xfc\x2b\x6f\x97\xd8\x41\x41\xa9\x90\xb4\x41\xd4\xd2\xca\xb7\xa3\x82\xaf\x6d\x8d\xf7\x83\x2f\x82\xaf\x27\xa6\x1e\xc5\x26\x29\x9c\x1c\x6e\x23\xf5\xe4\xa0\xbe\x13\x4f\x13\xe1\x71\xf6\xfe\x31"
math KEYSZ = 0x38

callfunction SET_ENCRYPTION 1
log MEMORY_FILE OFFSET SIZE 0 XSIZE

math BASE_OFF = OFFSET
math BASE_OFF + XSIZE
math BASE_OFF x 8

# weird directory structure
set KEY binary "\x45\xaa\xb7\x2a\x4f\xb3\x1d\xe1\x66\x39\x2f\x5b\xd8\x23\x1f\xa4\xa3\xda\x89\xe5\x5e\x28\x9e\x18\x2c\x68\x71\x39\xec\x8d\xd6\x1a\xcd\xd3\xf8\x3d\xe5\x59\xe5\xd5\x8d\x19\x58\x6a\x9c\x9a\xd3\x81\x3c\xdd\xab\x81\xd8\x46\xda\xb7"
math KEYSZ = 0x38

# lame work-around!!!
math SIZE * 4
math SIZE | 0x80000000
callfunction SET_ENCRYPTION 1
log MEMORY_FILE2 BASE_OFF SIZE
findloc TMP binary "\xef\x4a\xdb" MEMORY_FILE2
math BASE_OFF + TMP
print "guessed base offset %BASE_OFF|X%"

# keys for the files
putarray 0 0  "\x98\x3b\xa6\xcc\xa7\x52\x32\xf9\x23\xbb\xe8\x7d\x39\x6c\xb7\x4e"
putarray 0 1  "\x13\xc7\xe8\x81\xd9\x8c\x75\x16\xf3\x2f\xbb\xf4\x21\x56\xb1\xa6"
putarray 0 2  "\x38\x50\x7b\x33\xee\xe5\xf0\x53\x4c\x5d\x2f\xc7\xf1\x65\xb8\x4a"
putarray 0 3  "\xc4\x55\x7f\x7c\xba\xb4\x42\x91\xee\x51\x2e\x37\xeb\x23\xaf\x54"
putarray 0 4  "\x23\xeb\x2d\xe6\xf7\x49\x92\x7c\x82\xfd\xec\x8e\xdc\x9f\x3e\xbc"
putarray 0 5  "\xcb\x49\xd8\x7c\xcc\x59\x7b\xca\x2d\xe2\x24\xb7\x19\x36\x37\x4d"
putarray 0 6  "\x2d\x3a\xfb\x28\x54\x21\x50\xb4\xa0\x77\xb8\xbb\xbf\xe8\xb1\x67"
putarray 0 7  "\xe3\x6f\xb2\xef\x65\x2b\xa2\x3a\x58\x2a\xba\x1f\xae\x68\xec\xbc"
putarray 0 8  "\xe7\x1e\x3d\xd6\xf5\xe2\x87\x9f\x68\xa1\x8b\xbb\xc7\xd4\xf2\x7d"
putarray 0 9  "\x3e\x3a\x10\xe4\xc1\x7b\xdf\x72\x39\x46\x40\x16\xfe\x94\x6b\xb5"
putarray 0 10 "\x20\x59\x25\xb9\xa6\x6b\x77\xc0\xbd\x4e\xe0\xbd\x1a\x25\x64\x3b"
putarray 0 11 "\x3f\xd0\x85\x35\x18\xd3\x8c\x59\x89\xc6\xd6\x61\x82\xb8\x5f\x75"
putarray 0 12 "\x25\x2b\xbc\xe5\x3a\xb3\x8b\x75\xb1\x2c\x7a\xdf\x98\xe6\x57\x8b"
putarray 0 13 "\x81\x6a\xcb\xb0\x8b\x17\x15\x10\x40\x53\x7b\x4a\x8a\xce\x77\x18"
putarray 0 14 "\x44\xc9\xcb\xd2\xb1\x76\xed\x2b\x18\xc6\x95\xc9\xd9\xda\x5a\xec"
putarray 0 15 "\x6b\x88\xa6\xd4\x16\x57\x3d\xd0\xb2\x4d\x1f\xf2\x48\x73\x17\x44"
math KEYSZ = 0x10

get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get SIZE long MEMORY_FILE
    get DUMMY long MEMORY_FILE  # 0xffffffff or zero
    get OFFSET longlong MEMORY_FILE
    math OFFSET + BASE_OFF

    # lame guessing, the algorithm to know the idx is probably very easy so I leave you the fun
    if SIZE & 0x80000000
    callfunction LAME_GUESS_IDX 1
    endif

    math KEY_IDX & 0xf
    getarray KEY 0 KEY_IDX
    string KEY x KEY

    callfunction SET_ENCRYPTION 1
    log NAME OFFSET SIZE 0 XSIZE
next i

startfunction SET_ENCRYPTION
    if SIZE & 0x80000000    # DUMMY is -1 else is zero
        math SIZE & 0x7fffffff
        math XSIZE = SIZE
        math XSIZE x 8
        encryption blowfish KEY "" 0 KEYSZ
    else
        math XSIZE = SIZE
        encryption "" ""
    endif
endfunction

startfunction LAME_GUESS_IDX
    for KEY_IDX = 0 < 16
        getarray KEY 0 KEY_IDX
        string KEY x KEY
        encryption blowfish KEY "" 0 KEYSZ
        log MEMORY_FILE3 OFFSET 8
        math OK = 0
		#
		get TMP byte MEMORY_FILE3
		if TMP == 0x89
			math OK + 1
		endif
		get TMP byte MEMORY_FILE3
		if TMP == 0x50
			math OK + 1
		endif
		get TMP byte MEMORY_FILE3
		if TMP == 0x4E
			math OK + 1
		endif
		get TMP byte MEMORY_FILE3
		if TMP == 0x47
			math OK + 1
		endif
		get TMP byte MEMORY_FILE3
		if TMP == 0x0D
			math OK + 1
		endif
		get TMP byte MEMORY_FILE3
		if TMP == 0x0A
			math OK + 1
		endif
		get TMP byte MEMORY_FILE3
		if TMP == 0x1A
			math OK + 1
		endif
		get TMP byte MEMORY_FILE3
		if TMP == 0x0A
			math OK + 1
		endif
		#
        if OK >= 8
            break
        endif
    next KEY_IDX
endfunction
```


This will work for extracting PNGs. I dunno about injection I don't have the game. Also this corrupts DDS/CSV and other formats, this is only for PNG.


Edit: Works for injecting.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-28T00:13:14+00:00
- Post Title: Kof XIV Steam Edition

you can just turn off the encryption flag to inject files.
## Post #10
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-07-28T00:31:16+00:00
- Post Title: Kof XIV Steam Edition

I understand, but how does it work? I mean the algorithm to encrypt is completely different than the decryption algorithm. It requires 2 different ones. So how does QuickBMS find the correct key on the way back?
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-28T00:41:52+00:00
- Post Title: Kof XIV Steam Edition

what the script does is check that the first 4 characters are alpha numeric characters only.
that is how the decryption works
that is why it fails on some file types and some other files because the decryption happens to have 4 alpha numeric characters in the first 4.
Without looking at the source I would assume quickbms is checking the file in question and re extracting it before the import then using the ke it found to re inject it.
## Post #12
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-07-28T01:14:06+00:00
- Post Title: Kof XIV Steam Edition

> Reply from chrrox
>
> what the script does is check that the first 4 characters are alpha numeric characters only.
that is how the decryption works
that is why it fails on some file types and some other files because the decryption happens to have 4 alpha numeric characters in the first 4.
Without looking at the source I would assume quickbms is checking the file in question and re extracting it before the import then using the key it found to re inject it.

This is exactly what I was thinking of, it is the only possible way, but is a program really THAT smart?! I mean this has to be manually thought of by a human.
## Post #13
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2017-08-16T14:03:37+00:00
- Post Title: Kof XIV Steam Edition

aluigi's script has been updated on bbs.3dmgame forums:

[http://bbs.3dmgame.com/thread-5628441-1-1.html](http://bbs.3dmgame.com/thread-5628441-1-1.html)
## Post #14
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2017-08-16T16:57:14+00:00
- Post Title: Kof XIV Steam Edition

> Reply from Thony
>
> aluigi's script has been updated on bbs.3dmgame forums:

http://bbs.3dmgame.com/thread-5628441-1-1.html
Login is required to see the thread, can you post the script here?
## Post #15
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2017-08-16T21:20:50+00:00
- Post Title: Kof XIV Steam Edition

The script was posted here:

[viewtopic.php?f=10&t=16853](http://forum.xentax.com/viewtopic.php?f=10&t=16853)

```
# script for QuickBMS http://quickbms.aluigi.org
# updated by 0 DAY-S[EGCG] 海叔

idstring "AGAR"
get DUMMY long  # 1
get DUMMY long  # 1
get DUMMY long  # 0
get SIZE long
savepos OFFSET

# TOC
set KEY binary "\xfa\x52\x38\x8c\x66\xd6\x55\xfa\x1a\xfc\x2b\x6f\x97\xd8\x41\x41\xa9\x90\xb4\x41\xd4\xd2\xca\xb7\xa3\x82\xaf\x6d\x8d\xf7\x83\x2f\x82\xaf\x27\xa6\x1e\xc5\x26\x29\x9c\x1c\x6e\x23\xf5\xe4\xa0\xbe\x13\x4f\x13\xe1\x71\xf6\xfe\x31"
math KEYSZ = 0x38

callfunction SET_ENCRYPTION 1
log MEMORY_FILE OFFSET SIZE 0 XSIZE

math BASE_OFF = OFFSET
math BASE_OFF + XSIZE
math BASE_OFF x 8

# weird directory structure
set KEY binary "\x45\xaa\xb7\x2a\x4f\xb3\x1d\xe1\x66\x39\x2f\x5b\xd8\x23\x1f\xa4\xa3\xda\x89\xe5\x5e\x28\x9e\x18\x2c\x68\x71\x39\xec\x8d\xd6\x1a\xcd\xd3\xf8\x3d\xe5\x59\xe5\xd5\x8d\x19\x58\x6a\x9c\x9a\xd3\x81\x3c\xdd\xab\x81\xd8\x46\xda\xb7"
math KEYSZ = 0x38

# lame work-around!!!
math SIZE * 4
math SIZE | 0x80000000
callfunction SET_ENCRYPTION 1
log MEMORY_FILE2 BASE_OFF SIZE
findloc TMP binary "\xef\x4a\xdb" MEMORY_FILE2
math BASE_OFF + TMP
print "guessed base offset %BASE_OFF|X%"

# keys for the files
putarray 0 0  "\x98\x3b\xa6\xcc\xa7\x52\x32\xf9\x23\xbb\xe8\x7d\x39\x6c\xb7\x4e"
putarray 0 1  "\x13\xc7\xe8\x81\xd9\x8c\x75\x16\xf3\x2f\xbb\xf4\x21\x56\xb1\xa6"
putarray 0 2  "\x38\x50\x7b\x33\xee\xe5\xf0\x53\x4c\x5d\x2f\xc7\xf1\x65\xb8\x4a"
putarray 0 3  "\xc4\x55\x7f\x7c\xba\xb4\x42\x91\xee\x51\x2e\x37\xeb\x23\xaf\x54"
putarray 0 4  "\x23\xeb\x2d\xe6\xf7\x49\x92\x7c\x82\xfd\xec\x8e\xdc\x9f\x3e\xbc"
putarray 0 5  "\xcb\x49\xd8\x7c\xcc\x59\x7b\xca\x2d\xe2\x24\xb7\x19\x36\x37\x4d"
putarray 0 6  "\x2d\x3a\xfb\x28\x54\x21\x50\xb4\xa0\x77\xb8\xbb\xbf\xe8\xb1\x67"
putarray 0 7  "\xe3\x6f\xb2\xef\x65\x2b\xa2\x3a\x58\x2a\xba\x1f\xae\x68\xec\xbc"
putarray 0 8  "\xe7\x1e\x3d\xd6\xf5\xe2\x87\x9f\x68\xa1\x8b\xbb\xc7\xd4\xf2\x7d"
putarray 0 9  "\x3e\x3a\x10\xe4\xc1\x7b\xdf\x72\x39\x46\x40\x16\xfe\x94\x6b\xb5"
putarray 0 10 "\x20\x59\x25\xb9\xa6\x6b\x77\xc0\xbd\x4e\xe0\xbd\x1a\x25\x64\x3b"
putarray 0 11 "\x3f\xd0\x85\x35\x18\xd3\x8c\x59\x89\xc6\xd6\x61\x82\xb8\x5f\x75"
putarray 0 12 "\x25\x2b\xbc\xe5\x3a\xb3\x8b\x75\xb1\x2c\x7a\xdf\x98\xe6\x57\x8b"
putarray 0 13 "\x81\x6a\xcb\xb0\x8b\x17\x15\x10\x40\x53\x7b\x4a\x8a\xce\x77\x18"
putarray 0 14 "\x44\xc9\xcb\xd2\xb1\x76\xed\x2b\x18\xc6\x95\xc9\xd9\xda\x5a\xec"
putarray 0 15 "\x6b\x88\xa6\xd4\x16\x57\x3d\xd0\xb2\x4d\x1f\xf2\x48\x73\x17\x44"
math KEYSZ = 0x10

get FILES long MEMORY_FILE
for i = 0 < FILES
   
    get NAMESZ long MEMORY_FILE
   savepos POS MEMORY_FILE
   get N4 long MEMORY_FILE
   goto POS MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get SIZE long MEMORY_FILE
    get DUMMY long MEMORY_FILE  # 0xffffffff or zero
    get OFFSET longlong MEMORY_FILE
    math OFFSET + BASE_OFF
   
    if SIZE & 0x80000000
      callfunction CALC_IDX 1
    endif

    math KEY_IDX & 0xf
    getarray KEY 0 KEY_IDX
    string KEY x KEY

    callfunction SET_ENCRYPTION 1
    log NAME OFFSET SIZE 0 XSIZE
next i

startfunction SET_ENCRYPTION
    if SIZE & 0x80000000    # DUMMY is -1 else is zero
        math SIZE & 0x7fffffff
        math XSIZE = SIZE
        math XSIZE x 8
        encryption blowfish KEY "" 0 KEYSZ
    else
        math XSIZE = SIZE
        encryption "" ""
    endif
endfunction

#calc the key_idx
startfunction CALC_IDX
    math RSIZE = SIZE
   math RSIZE & 0x7fffffff
   math N4 ^ RSIZE
   #print "%SIZE%"

   math TMP1 = N4
   math TMP2 = N4
   math TMP2 >> 24

   math TMP1 >> 8
   math TMP1 ^ N4
   math TMP1 >> 8
   math TMP1 ^ N4

   math TMP1 & 255

   math TMP3 = TMP1

   math TMP1 ^ TMP2
   math TMP3 ^ TMP2
   math TMP3 >> 4
   

   math TMP1 ^ TMP3

   math TMP1 & 15

   math KEY_IDX = TMP1
endfunction
```
## Post #16
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-06-30T21:36:29+00:00
- Post Title: Re: Kof XIV Steam Edition

So are this game's models actually able to be ripped at all? Been some time since the game's release and I've only seen a few models online here and there...
## Post #17
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2018-07-02T11:38:03+00:00
- Post Title: Re: Kof XIV Steam Edition

Search fucntion is your friend
[viewtopic.php?p=135705#p135705](http://forum.xentax.com/viewtopic.php?p=135705#p135705)
