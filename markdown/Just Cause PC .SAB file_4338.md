## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-15T23:25:10+00:00
- Post Title: Just Cause PC .SAB file

[http://www.filefront.com/16136341/Music%20info.rar](http://www.filefront.com/16136341/Music%20info.rar)

Okay, here are two files one is a header for a raw pcm 22050hz 16bit liittle endian .sab 633MB file with markers for split points, the other file .sob contains the names of the files, since raw pcm is impossible to split in hex is it possible to write like a bms script that splits the tracks?

thanks.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-16T09:14:05+00:00
- Post Title: Just Cause PC .SAB file

it should be ok but I'm not 100% sure, try it with the other sab/sob files too:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

open FDDE SAB 0
open FDDE SOB 1

get CTF2 long 1
get DUMMY long 1
get FILES long 1
get DUMMY long 1
for i = 0 < FILES
    getdstring DUMMY 0x48 1
next i
for i = 0 < FILES
    get NUM long 1
    get NAMESZ long 1
    getdstring NAME NAMESZ 1
    putarray 0 NUM NAME
next i

get CSW2 long
get DUMMY long
get FILES long
get DUMMY20 long
get DUMMYOFF long
get DUMMY23 long
savepos GO_BACK

for EXTRACT = 0 < 2
    goto GO_BACK
    for i = 0 <= FILES
        get FILE_HERE long
        get CHANNELS long
        get FREQUENCY long
        get SIZE long
        get DUMMY long
        get DUMMY long
        get OFFSET long
        if FILE_HERE != 0
            if EXTRACT != 0
                set BITS long 16
                getarray FILENAME 0 i
                set NAME string FOLDER
                string NAME += /
                string NAME += FILENAME
                math OFFSET += BASE_OFF
                callfunction raw2wav 1
            endif
        endif
    next i
    get FOLDERSZ long
    getdstring FOLDER FOLDERSZ
    padding 16
    savepos BASE_OFF
next EXTRACT

startfunction raw2wav
    set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"

    set RIFFSIZE long SIZE
    math RIFFSIZE += 36
    set BLOCKALIGN long BITS
    set AVGBYTES long FREQUENCY
    math BLOCKALIGN /= 8
    math BLOCKALIGN *= CHANNELS
    math AVGBYTES *= BLOCKALIGN

    putvarchr MEMORY_FILE 4 RIFFSIZE long
    putvarchr MEMORY_FILE 20 1 short          # wFormatTag: Microsoft PCM Format (0x0001)
    putvarchr MEMORY_FILE 22 CHANNELS short   # wChannels
    putvarchr MEMORY_FILE 24 FREQUENCY long   # dwSamplesPerSec
    putvarchr MEMORY_FILE 28 AVGBYTES long    # dwAvgBytesPerSec
    putvarchr MEMORY_FILE 32 BLOCKALIGN short # wBlockAlign
    putvarchr MEMORY_FILE 34 BITS short       # wBitsPerSample
    putvarchr MEMORY_FILE 40 SIZE long

    log MEMORY_FILE2 0 44 MEMORY_FILE
    append
    log MEMORY_FILE2 OFFSET SIZE
    append

    math SIZE += 44
    log NAME 0 SIZE MEMORY_FILE2
endfunction
```
this script is only for music.sab/sob, DO NOT USE with other files!
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-27T10:10:51+00:00
- Post Title: Just Cause PC .SAB file

The contents of this post was deleted because of possible forum rules violation.
