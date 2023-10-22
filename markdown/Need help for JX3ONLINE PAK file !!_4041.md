## Post #1
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2010-01-12T13:09:10+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

Hello everyone,
I need help for  JX3ONLINE .It is a cool and beautiful game.Who can help me take a look at the game's files.
Here some pictures:



33333_1.gif (184.33 KiB) Viewed 520 times


The game's website:[http://jx3.xoyo.com/](http://jx3.xoyo.com/)
This is a link to the client ：[http://jx3.client.cdn3.kingsoft.com/jx3_v1.4.0.1820.rar](http://jx3.client.cdn3.kingsoft.com/jx3_v1.4.0.1820.rar)
 Thanks。
## Post #2
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2010-01-12T13:12:00+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

mt11.gif (110.56 KiB) Viewed 511 times
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-12T13:20:06+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

just fyi, if you don't upload one of the archives nobody will ever take a look at it
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-12T14:16:00+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

> Reply from aluigi
>
> just fyi, if you don't upload one of the archives nobody will ever take a look at it

I agree. We don't want to be forced to install a game just to look at the files. I only do that when it is clear I really need to take a look at the executable while the game is running to find an algorithm of some kind.

Upload an example file somewhere.
## Post #5
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2010-01-13T10:58:15+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-13T14:14:50+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

job done, the following is the script for quickbms

```

comtype NRV2b
idstring PACK
get FILES long
get INFO_OFF long
get BASE_OFF long
goto INFO_OFF
for i = 0 < FILES
    get CRC long
    get OFFSET long
    get SIZE long
    get ZSIZE long

    set doit long 0
    if CRC == -360607879    # some files are invalid!
    #elif CRC == 12345678   # put their crc/name here
    else                    # for skipping them!
        set doit long 1
    endif

    if doit != 0
        if ZSIZE & 0x10000000
            math ZSIZE &= 0x0fffffff
            callfunction unpack_0x10000000
        elif ZSIZE & 0x20000000
            math ZSIZE &= 0x0fffffff
            clog CRC OFFSET ZSIZE SIZE
        elif ZSIZE & 0x40000000
            print "Error: type 0x40000000 not supported"
            cleanexit
        elif ZSIZE & 0x80000000
            print "Error: type 0x80000000 not supported"
            cleanexit
        else
            log CRC OFFSET SIZE
        endif
    endif
next i

startfunction unpack_0x10000000
    savepos TMP
    goto OFFSET
    get CHUNKS long
    get CHUNKS_OFFSET long
    math CHUNKS_OFFSET += OFFSET
    goto CHUNKS_OFFSET
    putvarchr MEMORY_FILE SIZE 0    # pre-allocate for speed
    log MEMORY_FILE 0 0             # reset
    append
    for x = 0 < CHUNKS
        get OFFSETX long
        get SIZEX long
        get ZSIZEX long
        math OFFSETX += OFFSET
        if ZSIZEX & 0x10000000
            print "Error: type2 0x10000000 not supported"
            cleanexit
        elif ZSIZEX & 0x20000000
            math ZSIZEX &= 0x0fffffff
            clog MEMORY_FILE OFFSETX ZSIZEX SIZEX
        elif ZSIZEX & 0x40000000
            print "Error: type2 0x40000000 not supported"
            cleanexit
        elif ZSIZEX & 0x80000000
            print "Error: type2 0x80000000 not supported"
            cleanexit
        else
            log MEMORY_FILE OFFSETX SIZEX
        endif
    next x
    append
    log CRC 0 SIZE MEMORY_FILE
    goto TMP
endfunction
```

note that ui.pak contains a file that is archive wrongly, I mean that the file table claims it's compressed but its decompression fails, so I have added its name/crc to the list of files to skip.
if you encounter errors during the extraction of the other archives it's enough that you add their name where is located the example of "#elif CRC == 12345678" or simply let me know their names and I will tell you what to add in the script
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-13T19:39:02+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

Also, read the rules on which upload services are allowed (RAPIDSHARE is not !)
## Post #8
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2010-01-14T04:01:11+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

I am sorry my English is not very good Mr.Mouse. I did not find a suitable space for uploading.
I will continue to upload if there is a suitable space. Thank you for reminding me.Mr.Mouse

to aluigi ：
thanks for you script.
I used your script, but the extract all files out of the same type. I do not know the real name of the file and format.
I think， The image format in data.pak file is the "DDS", the model format is "mesh", 
In "UI.pak" file ,the image format is"TGA".
There are other formats, such as". Ani" ". Bsp" ". Block" and so on. 
You can look at "dat.rar".
[data.rar - 1.00MB](http://www.zshare.net/download/71182786352c7bab/)
If you need, I will provide more resources.
Hope that these examples to give you the help.
Very very thank you.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-14T13:39:39+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

I forgot to say that the filenames are not stored in the archive, the only thing stored is the crc of the filenames so that's the only thing you can use as name
## Post #10
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2010-01-22T11:11:02+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

sorry, I did not complete it.
BMS script is very difficult to me . I think I have to spend some time to learn it.
Hope to see aluigi and more friends to help.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-22T20:15:38+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

I don't understand what's the problem now:
there are NO filenames stored in the archives.

if you have other problems with the extraction, be more specific
## Post #12
- Username: troll1981
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 10, 2014 2:28 am
- Post datetime: 2014-07-13T11:55:11+00:00
- Post Title: Need help for JX3ONLINE PAK file !!

error when unpacking with QuickBMS  on new Client (version 3.3.3)

can aluigi update the quickbms script ?

Thx
[jx3 quickbms error.png](https://xentaxbackup.github.io/file/7574_jx3 quickbms error.png)
