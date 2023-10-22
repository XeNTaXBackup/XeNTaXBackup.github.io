## Post #1
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-10-29T07:12:34+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

I want to see if there are any text/subtitle file/s in english there liek there was in the first Deponia game.
Can someone create two scripts in bms to extract Chaos On Deponia German and a script to merge back the file ?

Thanks.
## Post #2
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-10-29T07:21:33+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

There is a one big file 55mb wich is Data.vis 
vis is part of Visionaire program. This is the file i want to extract and see what files there are inside and then somehow to copy and make it in english.
## Post #3
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-10-29T07:34:25+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

I just uploaded the .Vis file data.vis to here: [http://www.mediafire.com/?c15q8hz9eyai7rm](http://www.mediafire.com/?c15q8hz9eyai7rm)
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-11-01T12:19:54+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

Here is the password for the Visionaire .bms script: dcff854efc3e840c
## Post #5
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-11-01T22:31:33+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

> Reply from bacter
>
> Here is the password for the Visionaire .bms script: dcff854efc3e840c

This is the script file i have for Deponia. How do i use this password/key in this script for Chaos On Deponia ?
I mean how do i add and where this password/key in this script ?

Can someone modify and show me how the script should be like with the new password/key(dcff854efc3e840c) ?

This is the script im using now wich need a modify:

```
# script for QuickBMS http://quickbms.aluigi.org

set KEY binary "76093af7c458e3c5"   # md5 hash of unicode "VSADV3PL"
putarray 8 0 KEY
set KEY binary "98d1a1f120d8ce55"   # md5 hash of unknown string
putarray 8 1 KEY
set KEY binary ""
putarray 8 2 KEY

getdstring SIGN 4
if SIGN == "VIS3"
    get FILES long  # max 0x1869f?
    if FILES u> 0x00ffffff # 0x1869f
        endian big
        reverselong FILES
    endif
    savepos BASE_OFF
    math TMP = FILES
    math TMP *= 16
    math TMP += 6

    # key scanner
    math i = 0
    do
        getarray KEY 8 i
        if KEY == ""
            print "unknown Visionaire key, contact me"
            cleanexit
        endif
        encryption xor KEY
        log MEMORY_FILE BASE_OFF 3
        encryption "" ""
        getdstring SIGN 3 MEMORY_FILE
        math i += 1
    while SIGN != "HDR"
    print "use key %KEY%"

    encryption xor KEY
    log MEMORY_FILE BASE_OFF TMP
    encryption "" ""
    math BASE_OFF += TMP

    math LAME_VIS   = 0 # Deponia
    math OLD_OFFSET = 0
    math OLD_ZSIZE  = 0

    getdstring SIGN 3 MEMORY_FILE
    for i = 0 < FILES
        encryption "" ""
        get OFFSET long MEMORY_FILE
        get ZSIZE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get TYPE long MEMORY_FILE
        if i == 1
            if TYPE > 0xffff
                math LAME_VIS = 1
            endif
        endif
        if LAME_VIS != 0
            callfunction LAME_VIS_FIX 1
        endif
        math OFFSET += BASE_OFF
        set NAME long i
        string NAME += "."
        string NAME += TYPE
        #if TYPE == 0
        #    string NAME += ".ogv"
        #elif TYPE == 3
        #    string NAME += ".xml"
        #elif TYPE == 8
        #    string NAME += ".png"
        #else
        #    string NAME += ".dat"
        #endif
        set NAME string ""
        if TYPE & 2
            encryption xor KEY
        endif
        if SIZE == ZSIZE
            log NAME OFFSET SIZE
        else
            clog NAME OFFSET ZSIZE SIZE
        endif
    next i
else
    # if you have only one big executable you must first dump
    # everything from the first occurrence of the bytes d1 b5 d1
    set PASSWD string "PASSWD"
    strlen TMP PASSWD
    for i = 0 < TMP
        getvarchr BYTE PASSWD i
        math BYTE += 0x2b
        math BYTE n= BYTE   # needed for Encryption
        putvarchr PASSWD i BYTE
    next i
    encryption rot PASSWD "" "" TMP
    get SIZE asize  # yeah, lame way but it's the only one here
    math SIZE /= 4  # because it's necessary a one-byte function
    log MEMORY_FILE 0 SIZE
    encryption "" ""
    idstring MEMORY_FILE "VIS"
    get FILES long MEMORY_FILE
    for EXTRACT = 0 < 2
        goto 7 MEMORY_FILE
        for i = 0 < FILES
            get NAMESZ byte MEMORY_FILE
            getdstring NAME NAMESZ MEMORY_FILE
            get OFFSET long MEMORY_FILE
            get SIZE long MEMORY_FILE
            if EXTRACT != 0
                math OFFSET += BASE_OFF
                log NAME OFFSET SIZE
            endif
        next i
        savepos BASE_OFF MEMORY_FILE
    next EXTRACT
endif

startfunction LAME_VIS_FIX
    if i <= 4
        math TYPE = 0
    elif i <= 8
        math OFFSET = OLD_OFFSET
        math OFFSET += OLD_ZSIZE
    else
        math ZSIZE &= 0x00ffffff
        math LAME_VIS = 0   # reset
    endif
    math OLD_OFFSET = OFFSET
    math OLD_ZSIZE  = ZSIZE
endfunction
```
## Post #6
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2012-11-01T23:28:34+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

> Reply from Chocolade1972
>
> bacter wrote:Here is the password for the Visionaire .bms script: dcff854efc3e840c
Code: Select all# Visionaire Player/Studio (script 0.2.1)
# script for QuickBMS http://quickbms.aluigi.org

set KEY binary "dcff854efc3e840c"   # md5 hash of unicode "VSADV3PL"
putarray 8 0 KEY
set KEY binary "dcff854efc3e840c"   # md5 hash of unknown string
putarray 8 1 KEY
set KEY binary ""
putarray 8 2 KEY

getdstring SIGN 4
if SIGN == "VIS3"
    get FILES long  # max 0x1869f?
    if FILES u> 0x00ffffff # 0x1869f
        endian big
        reverselong FILES
    endif
    savepos BASE_OFF
    math TMP = FILES
    math TMP *= 16
    math TMP += 6

    # key scanner
    math i = 0
    do
        getarray KEY 8 i
        if KEY == ""
            print "unknown Visionaire key, contact me"
            cleanexit
        endif
        encryption xor KEY
        log MEMORY_FILE BASE_OFF 3
        encryption "" ""
        getdstring SIGN 3 MEMORY_FILE
        math i += 1
    while SIGN != "HDR"
    print "use key %KEY%"

    encryption xor KEY
    log MEMORY_FILE BASE_OFF TMP
    encryption "" ""
    math BASE_OFF += TMP

    math LAME_VIS   = 0 # Deponia
    math OLD_OFFSET = 0
    math OLD_ZSIZE  = 0

    getdstring SIGN 3 MEMORY_FILE
    for i = 0 < FILES
        encryption "" ""
        get OFFSET long MEMORY_FILE
        get ZSIZE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get TYPE long MEMORY_FILE
        if i == 1
            if TYPE > 0xffff
                math LAME_VIS = 1
            endif
        endif
        if LAME_VIS != 0
            callfunction LAME_VIS_FIX 1
        endif
        math OFFSET += BASE_OFF
        set NAME long i
        string NAME += "."
        string NAME += TYPE
        #if TYPE == 0
        #    string NAME += ".ogv"
        #elif TYPE == 3
        #    string NAME += ".xml"
        #elif TYPE == 8
        #    string NAME += ".png"
        #else
        #    string NAME += ".dat"
        #endif
        set NAME string ""
        if TYPE & 2
            encryption xor KEY
        endif
        if SIZE == ZSIZE
            log NAME OFFSET SIZE
        else
            clog NAME OFFSET ZSIZE SIZE
        endif
    next i
else
    # if you have only one big executable you must first dump
    # everything from the first occurrence of the bytes d1 b5 d1
    set PASSWD string "PASSWD"
    strlen TMP PASSWD
    for i = 0 < TMP
        getvarchr BYTE PASSWD i
        math BYTE += 0x2b
        math BYTE n= BYTE   # needed for Encryption
        putvarchr PASSWD i BYTE
    next i
    encryption rot PASSWD "" "" TMP
    get SIZE asize  # yeah, lame way but it's the only one here
    math SIZE /= 4  # because it's necessary a one-byte function
    log MEMORY_FILE 0 SIZE
    encryption "" ""
    idstring MEMORY_FILE "VIS"
    get FILES long MEMORY_FILE
    for EXTRACT = 0 < 2
        goto 7 MEMORY_FILE
        for i = 0 < FILES
            get NAMESZ byte MEMORY_FILE
            getdstring NAME NAMESZ MEMORY_FILE
            get OFFSET long MEMORY_FILE
            get SIZE long MEMORY_FILE
            if EXTRACT != 0
                math OFFSET += BASE_OFF
                log NAME OFFSET SIZE
            endif
        next i
        savepos BASE_OFF MEMORY_FILE
    next EXTRACT
endif

startfunction LAME_VIS_FIX
    if i <= 4
        math TYPE = 0
    elif i <= 8
        math OFFSET = OLD_OFFSET
        math OFFSET += OLD_ZSIZE
    else
        math ZSIZE &= 0x00ffffff
        math LAME_VIS = 0   # reset
    endif
    math OLD_OFFSET = OFFSET
    math OLD_ZSIZE  = ZSIZE
endfunction
I guess you just have to replace the firts KEY values. I've done this, juste try now
## Post #7
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-11-02T00:05:17+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

Illian i tried its starting to work to extract then when its getting to file number 00000407.dat its throwing error:

The compressed zlib/deflate input is wrong or incomplete <-3>
There is an error with the decompression the returned output size is negative <-1>

ENTER to quit

I seleceted the data.vis of Chaos On Deponia and selected output directory it start to extract many .dat files only dat files then throed the error.

What can i do ? How to fix it please ?
## Post #8
- Username: Chocolade1972
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Apr 23, 2012 10:16 am
- Post datetime: 2012-11-02T00:28:58+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

I also noticed now that the files on the hard disk that have extracted untill the error i cant view them.
There many .ogg files and many .png files i tried to view the .png files and get error that it cant be opened on any program since its damaged or currpt some of the files 13-19kb.

So i wonder whats wrong with the script and how to fix it.
## Post #9
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-11-13T18:53:04+00:00
- Post Title: Can someone make a script bms for chaos on deponia german ?

> Reply from Chocolade1972
>
> I also noticed now that the files on the hard disk that have extracted untill the error i cant view them.
There many .ogg files and many .png files i tried to view the .png files and get error that it cant be opened on any program since its damaged or currpt some of the files 13-19kb.

So i wonder whats wrong with the script and how to fix it.
It's nothing wrong with the unpacking. About the bad PNG's, read that article [http://www.nullsecurity.org/article/a_n ... png_fixing](http://www.nullsecurity.org/article/a_new_beginning-png_fixing)
