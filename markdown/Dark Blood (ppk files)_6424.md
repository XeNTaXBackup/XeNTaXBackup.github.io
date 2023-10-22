## Post #1
- Username: SuperSecret
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 14, 2011 2:03 pm
- Post datetime: 2011-04-14T06:40:47+00:00
- Post Title: Dark Blood (ppk files)

thought today i would take another crack at trying to learn quickbms by myself, but ended up getting stuck once more, the data in this file is fairly simple, but i couldn't find the filename lenght in the hex code, it is also written in unicode and listed 2 times, anyways here's what i got so far



RED: Header Size
BLUE: Number of Files
GREEN: Compressed Data
YELLOW: Not sure what these 2 are, there are 2 file paths and neither of them or counted together (or diveded by 2 (cuz of unicode)) counted towards any hex char listed, so i didn't see anywhere where the filename/path lenght was listed in hex

would really appreciate it if any1 could help out me with this bms script, would save me alot of time :}

...unable to attach file, get it here:
[http://ifile.it/0mlv2jg/Sound_9.rar](http://ifile.it/0mlv2jg/Sound_9.rar) (500kb)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-14T11:16:52+00:00
- Post Title: Dark Blood (ppk files)

the script for quickbms is the following:

```
goto 0x218
get HEAD_SIZE long
savepos BASE_OFF
math BASE_OFF += HEAD_SIZE
get FILES long
get DUMMY long
get DUMMY byte
get DUMMY short
get DUMMY long
for i = 0 < FILES
    callfunction GET_UGLYSTRING 1
    set NAME string TMPNAME
    callfunction GET_UGLYSTRING 1
    get CRC long
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get DUMMY byte
    if DUMMY != 1
        print "DUMMY != 1: contact me"
        cleanexit
    endif
    math OFFSET += BASE_OFF
    log NAME OFFSET SIZE
next i

startfunction GET_UGLYSTRING
    math NAMESZ = 0
    math j = 0
    do
        get T byte
        math TMP = T
        math TMP &= 0x7f
        math TMP2 = j
        math TMP2 *= 7
        math TMP <<= TMP2
        math NAMESZ += TMP
        math j += 1
    while T <= 0x7f
    getdstring TMPNAME NAMESZ
    set TMPNAME unicode TMPNAME
endfunction
```
I guess that there are also compressed files but the archive you provided didn't contain them so it could not extract some files well so I have added that "contact me" message so that you can upload the archives with that particular byte set and I will verify them immediately
## Post #3
- Username: SuperSecret
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 14, 2011 2:03 pm
- Post datetime: 2011-04-14T15:05:37+00:00
- Post Title: Dark Blood (ppk files)

no, none of the files are actually compressed, that is there are a few files that use compression, but they have their own header, either way, it's not a problem

anyways, thanks alot for the script, getting the file paths seems to be alot more complex than i anticipated hehe. tested the script on all the packed files and didn't get any errors, so working perfectly
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T03:28:41+00:00
- Post Title: Dark Blood (ppk files)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-16T11:31:20+00:00
- Post Title: Dark Blood (ppk files)

script updated to version 0.1.1 which supports the J files which are compressed.

in short this compression is not part of the archive format but its specific for these files so I have made an on-the-fly decompression.

note that I will upload the new script within some minutes so if you don't see "(script 0.1.1)" in it wait more.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T08:23:11+00:00
- Post Title: Dark Blood (ppk files)

Works great
