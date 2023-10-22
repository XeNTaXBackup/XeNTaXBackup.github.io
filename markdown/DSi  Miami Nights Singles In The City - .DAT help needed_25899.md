## Post #1
- Username: IX285
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 12, 2022 5:30 pm
- Post datetime: 2022-10-12T09:40:55+00:00
- Post Title: DSi // Miami Nights: Singles In The City - .DAT help needed

GAME NAME / REGION / CONSOLE
Miami Nights:Singles In The City
Released region-free as DSiWare

GAME DEVELOPERS / PUBLISHERS
Gameloft

FIRST 8 BYTES OF THE ATTACHED FILE ARCHIVE
[.dat] A9 D1 20 00 00 03 00 03 00 - ｩ ﾑ . . . .

QUICKBMS SCRIPT I TRIED TO OPEN FILE WITH (credits to aluigi)

```
open FDDE "off"
open FDDE "dat" 1

get OFF_SIZE asize
for i = 0
    savepos TMP
    if TMP == OFF_SIZE
        break
    endif

    get NAME string
    get OFFSET long
    if OFFSET & 0x80000000
        math OFFSET & 0x7fffffff
        math ZIP = 1
    else
        math ZIP = 0
    endif
    putarray 0 i NAME
    putarray 1 i OFFSET
    putarray 2 i ZIP
next i
    get OFFSET asize 1
    putarray 1 i OFFSET

math FILES = i
for i = 0 < FILES
    getarray NAME   0 i
    getarray OFFSET 1 i
    getarray ZIP    2 i
    math i + 1
    getarray SIZE   1 i
    math SIZE - OFFSET
    if ZIP == 0
        log NAME OFFSET SIZE 1
    else
        goto OFFSET 1
        get XSIZE long 1
        math OFFSET + 4
        math SIZE   - 4
        clog NAME OFFSET SIZE XSIZE 1
    endif
next
```

[00000000.zip](https://xentaxbackup.github.io/file/22896_00000000.zip)
