## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-25T14:20:51+00:00
- Post Title: Nitro+ soft pak file

Hello.
I need help unpack the Nitro+ soft pak file.
The title of the game is 'Kishin Hishou Demonbane'.
Here are the sample cut file of the original cg.pak which is around 410mb .
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-25T16:04:16+00:00
- Post Title: Nitro+ soft pak file

EXPERIMENTAL script for quickbms, some names could be not correct and the content of some files could be decrypted even when not needed so report here any problem you will have:

```

get VER long
getdstring KISHINDB 0x100
get ZSIZE long
get DUMMY long
get DUMMY long
get TMP long
math ZSIZE += TMP
comtype unzip_dynamic
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE ZSIZE
math BASE_OFF = OFFSET
math BASE_OFF += ZSIZE
get FULL_SIZE asize MEMORY_FILE
for CURR = 0 < FULL_SIZE
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get DUMMY1 long MEMORY_FILE
    get DUMMY2 long MEMORY_FILE
    get DUMMY3 long MEMORY_FILE
    get DUMMY4 long MEMORY_FILE
    get DUMMY5 long MEMORY_FILE
    savepos CURR MEMORY_FILE
    math DUMMY1 ^= DUMMY5
    math DUMMY2 ^= DUMMY5
    math DUMMY3 ^= DUMMY5
    math DUMMY4 ^= DUMMY5
    math OFFSET = DUMMY1
    math SIZE   = DUMMY2
    math NEXT   = DUMMY3
    math TYPE   = DUMMY4
    string XORKEY = DUMMY5
    math OFFSET += BASE_OFF

    math T2 = 0
    for j = 0 < NAMESZ
        getvarchr T NAME j
        if T >= 0x80
            math T2 = 1
        endif
    next j
    if T2 != 0
        encryption xor XORKEY
    endif
    log NAME OFFSET SIZE
    encryption "" ""

    math CURR = NEXT
    goto CURR MEMORY_FILE
next
```
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-30T08:30:57+00:00
- Post Title: Nitro+ soft pak file

Thanks alugie
