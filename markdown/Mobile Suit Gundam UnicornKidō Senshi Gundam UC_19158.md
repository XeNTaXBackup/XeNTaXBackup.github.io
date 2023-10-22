## Post #1
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2018-12-07T19:51:24+00:00
- Post Title: Mobile Suit Gundam Unicorn/Kidō Senshi Gundam UC

So formats are .hkx for models and .tpf for textures as well as .bnd for the container file, usual from software games formats
Would be appreciated if I could get assistance getting into these files (also original bones support would definitly be appreciated to)
supplied some samples here

[https://cdn.discordapp.com/attachments/ ... NICORN.zip](https://cdn.discordapp.com/attachments/475386426658258944/520413935397109769/UNICORN.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-08T05:21:02+00:00
- Post Title: Mobile Suit Gundam Unicorn/Kidō Senshi Gundam UC

from c00_000_00.bnd:



c00_000_00-bnd-cut.png (117.86 KiB) Viewed 163 times


(unsure about uvs)
## Post #3
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2018-12-08T18:46:37+00:00
- Post Title: Mobile Suit Gundam Unicorn/Kidō Senshi Gundam UC

oh heck didnt expect progress, nice
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-08T19:30:21+00:00
- Post Title: Mobile Suit Gundam Unicorn/Kidō Senshi Gundam UC

You'll need to invest more efforts to get more progress, for example use tools to extract files from the .bnd.

There's flver contained which I used hex2obj on but there might exist scripts, too.



c_00_000_00-flver_3A2B10.png (64.56 KiB) Viewed 147 times
## Post #5
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2018-12-09T17:33:16+00:00
- Post Title: Mobile Suit Gundam Unicorn/Kidō Senshi Gundam UC

oh yeah believe me i tried everything i could, thats why my last resort was to make a thread, i did use a BMS script to extract the .bnd though (used a .bat to change from .bdt to .bnd)

```
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate
endian big
set FOLDER string ""
math OFFSET = 0

get EXT extension
open FDDE "chrtpfbhd" 1 EXISTS
if EXISTS == 0
    open FDDE "bhd" 1 EXISTS
endif
if EXISTS == 0
    if EXT & "bnd"
        open FDDE EXT 1 EXISTS
    else
        open FDDE "bnd" 1 EXISTS
    endif
endif
if EXISTS != 0
    # endian little
    callfunction DUMP_BHF_BDF 1
    cleanexit
endif

open FDDE "bhd5"
open FDDE "bdt" 1

idstring "BHD5"
get ZERO long
get ONE long
endian guess ONE
get BHD5_SIZE long
get BHD5_FOLDERS long
get DUMMY long

savepos TMP
    get BHD5_FILES long
    get OFFSET long
math METHOD = 0
if OFFSET == 0
    math METHOD = 1
else
    goto TMP
endif

for FOLDER = 0 < BHD5_FOLDERS
    get BHD5_FILES long
    if METHOD == 0
        get OFFSET long
    else
        get ONE long
        get OFFSET longlong
    endif

    savepos TMP
    goto OFFSET
    for FILE = 0 < BHD5_FILES
        get NAME_CRC long
        get SIZE long
        get OFFSET longlong
        string NAME p= "%d/" FOLDER

        goto OFFSET 1
        getdstring SIGN 3 1
        if SIGN == "BHF"
            callfunction DUMP_BHF_BDF 1
        elif SIGN == "BDF"
            # do nothing because it's already handled and extracted by DUMP_BHF_BDF
        else
            log NAME OFFSET SIZE 1
        endif
    next FILE
    goto TMP
next FOLDER

# BHF and BDF
startfunction DUMP_BHF_BDF
    get EXT extension 1
    get MYASIZE asize
    goto OFFSET 1
    math IS_BND = 0
    if EXT & "bnd"  # bnd, texbnd and so on
        math IS_BND = 1
        idstring 1 "BND"
    else
        idstring 1 "BHF"
    endif
    get VER byte 1
    if VER <= '4'
        get DUMMY long 1
        get DUMMY long 1
    else    # '5'
        padding 0x10 1
    endif
    get FILES long 1
    endian guess FILES
    if VER <= '4'
        goto 0x40 1
        for i = 0 < FILES
            get FLAGS long 1
            get DUMMY long 1
            get SIZE longlong 1
            get XSIZE longlong 1
            get OFFSET longlong 1
            if IS_BND == 0
                get NAME_IDX long 1
            endif
            get NAME_OFF long 1
            putarray 0 i OFFSET
            putarray 1 i SIZE
            putarray 2 i XSIZE
            savepos TMP 1
            goto NAME_OFF 1
            get NAME string 1
            putarray 3 i NAME
            goto TMP 1
        next i
    else
        padding 0x10 1
        for i = 0 < FILES
            get FLAGS long 1
            get SIZE long 1
            get OFFSET long 1
            get NAME_IDX long 1
            get DUMMY long 1    # NAME_OFF
            get XSIZE long 1
            putarray 0 i OFFSET
            putarray 1 i SIZE
            putarray 2 i XSIZE
        next i
        for i = 0 < FILES
            get NAME string 1
            putarray 3 i NAME
        next i
    endif

    if EXT == "chrtpfbhd"
        open FDDE "chrtpfbdt" 1
    elif EXT == "bhd"
        open FDDE "bdt" 1
    endif

    math BASE_OFF = 0
    if EXT != "bhd"
    if IS_BND == 0
        padding 0x10 1
        savepos BASE_OFF 1
        idstring 1 "BDF"
    endif
    endif
    for i = 0 < FILES
        getarray OFFSET 0 i
        getarray SIZE   1 i
        getarray XSIZE  2 i
        getarray NAME   3 i
        if XSIZE != 0
            math TMP = OFFSET
            math TMP + SIZE
            if TMP u<= MYASIZE
                math OFFSET += BASE_OFF
                if FOLDER != ""
                    string NAME p= "%d/%s" FOLDER NAME
                endif
                if SIZE == XSIZE
                    log NAME OFFSET SIZE 1
                else
                    goto OFFSET 1
                    getdstring SIGN 4 1
                    if SIGN u== "DCX"
                        get CHUNK_SIZE long 1
                        get DUMMY long 1
                        get DUMMY long 1
                        get DUMMY long 1
                        get CHUNKS_BASE_OFF long 1
                        getdstring DUMMY 0x58 1
                        xmath CHUNKS "(CHUNKS_BASE_OFF - 0x50) / (8 + 4 + 4)"
                        math CHUNKS_BASE_OFF + 0x20
                    else
                        get CHUNKS_BASE_OFF long 1
                        get CHUNKS long 1
                        get CHUNK_SIZE long 1
                        math CHUNKS_BASE_OFF - 0x18
                    endif
                    math CHUNKS_BASE_OFF + OFFSET
                    log NAME 0 0 1  # in case of duplicates
                    append
                    for x = 0 < CHUNKS
                        get CHUNK_OFF longlong 1
                        get CHUNK_ZSIZE long 1
                        get CHUNK_ZIP long 1
                        math CHUNK_OFF + CHUNKS_BASE_OFF
                        if CHUNK_ZIP == 0
                            log NAME CHUNK_OFF CHUNK_ZSIZE 1
                        else
                            clog NAME CHUNK_OFF CHUNK_ZSIZE CHUNK_SIZE 1
                        endif
                    next x
                    append
                endif
            endif
        endif
    next i
endfunction

```
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-09T21:56:22+00:00
- Post Title: Mobile Suit Gundam Unicorn/Kidō Senshi Gundam UC

So you got a bunch of 35 files with different types then, right?
For example 6 .hkx files. But the skeleton.hkx doesn't contain the strings "hka" or "hkClass".

Even worse the c00_000_00.flver created by the bms script doesn't have a FLVER signature at file start which I got when extracting that uncompressed file manually from the .bnd.

(You can cut the flver very easily from your 4 MB c00_000_00.bnd using a hex editor:
start 0x2cc030 (FLVER) to 0x384250, size: 754208 bytes)

Possibly your .bnd doesn't match the bms script or there's an unwanted offset on extracting, whatever.
