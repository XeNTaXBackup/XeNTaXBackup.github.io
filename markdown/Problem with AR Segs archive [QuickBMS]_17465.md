## Post #1
- Username: Coolsonickirby
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 28, 2017 10:45 pm
- Post datetime: 2017-12-28T14:49:41+00:00
- Post Title: Problem with AR Segs archive [QuickBMS]

When I try to uncompress Sonic Unleashed PS3 files, it dosen't work.I would deeply appreciate any help. Thanks.

Here's the error it gives me

> "offset filesize filename
>
> --------------------------------------
>
> 30000010 990969856 #ActD_Snow.ar/Stage.stg.xml
>
> 
>
> Error: [myfseek] the offset 0x30000010 in the file -1 can't be reached
>
> 
>
> Last script line before the error or that produced the error:
>
> 62 log FNAME OFFSET SIZE MEMORY_FILE"

and the script I used

```
#   Sonic Unleashed
#   Battle Fantasia
#   BlazBlue
#   Arcana Heart 3
#   Persona 4 Arena (Ultimax)
#   ...
# script for QuickBMS http://quickbms.aluigi.org

get BASE_NAME basename
string BASE_NAME += /
comtype deflate
endian big
getdstring SIGN 4
if SIGN == "segs"
    get DUMMY short
    get CHUNKS short
    get FULL_SIZE long
    get FULL_ZSIZE long
    putvarchr MEMORY_FILE 0 FULL_SIZE
    log MEMORY_FILE 0 0
    append
    for i = 0 < CHUNKS
        get ZSIZE short
        get SIZE short
        get OFFSET long
        math OFFSET -= 1
        if SIZE == 0
            math SIZE = 0x00010000
        endif
        clog MEMORY_FILE OFFSET ZSIZE SIZE
    next i
    append
else
    # pfd
    get SIZE asize
    log MEMORY_FILE 0 SIZE
endif

# the files are just compressed pfd files
# so we handle them here automatically (both!)

goto 0 MEMORY_FILE
get FULL_SIZE asize MEMORY_FILE
endian big
getdstring TYPE 4 MEMORY_FILE
if TYPE == ""   # pfd
    get DUMMY long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get FILES long MEMORY_FILE
    savepos BASE_OFF MEMORY_FILE
    for BASE_OFF = BASE_OFF < FULL_SIZE
        get HEADDATA_SIZE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get OFFSET long MEMORY_FILE
        get DUMMY long MEMORY_FILE
        get DUMMY long MEMORY_FILE
        get NAME string MEMORY_FILE
        math OFFSET += BASE_OFF
        set FNAME string BASE_NAME
        string FNAME += NAME
        log FNAME OFFSET SIZE MEMORY_FILE
        math BASE_OFF += HEADDATA_SIZE
        goto BASE_OFF MEMORY_FILE
    next
elif TYPE == "FPAC"
    endian little
    get BASE_OFF long MEMORY_FILE
    if BASE_OFF u>= FULL_SIZE
      endian big
      ReverseLong BASE_OFF
    endif
    get TOT_SIZE long MEMORY_FILE
    get FILES long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get NAMELEN long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    for i = 0 < FILES
        getdstring NAME NAMELEN MEMORY_FILE
   get FILEID long MEMORY_FILE
        get OFFSET long MEMORY_FILE
        get SIZE long MEMORY_FILE
        Padding 16 MEMORY_FILE 0
        math OFFSET += BASE_OFF
        set FNAME string BASE_NAME
        string FNAME += NAME
        log FNAME OFFSET SIZE MEMORY_FILE
    next i
else
    get NAME basename
    get EXT extension
    string NAME += "_unpacked."
    string NAME += EXT
    set FNAME string BASE_NAME
    string FNAME += NAME
    log FNAME 0 FULL_SIZE MEMORY_FILE
endif

print "\nyou can try to reuse this script with the output files (pac, pfd and so on)\nfor extracting the other files contained in them"
```
