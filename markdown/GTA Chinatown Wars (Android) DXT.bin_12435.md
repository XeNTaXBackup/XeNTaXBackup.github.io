## Post #1
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-27T14:56:22+00:00
- Post Title: GTA Chinatown Wars (Android) DXT.bin

So this game has been out on iOS for quite a while, but just recently a massive update for the iOS version came out, as well as the game's debut on Android. So I decided to take a look at the files, and turns out there's a new DXT.bin file. It contains higher quality textures compressed with DXT.

The thing that bugs me about this format is why they've decided to pad out the individual offsets - they're separated by null bytes, with seemingly arbitrary lengths.

This script extracts the DXT-compressed textures and gives them proper DDS headers. The only problem is that the script can't always differentiate between DXT3 and DXT5, so the header has to be corrected manually. I may or may not fix this in the future.

```
# script for QuickBMS http://quickbms.aluigi.org

math FCOUNT = 0

for SEEK = 0 == 0
    get SEEK long
next

putArray 0 0 SEEK
math FCOUNT += 1

for CURRPOS = 0 < SEEK
    get OFFSET long

    if OFFSET > 0
        putArray 0 FCOUNT OFFSET
    math FCOUNT += 1
    endif

    savepos CURRPOS
next

get SIZE asize
putArray 0 FCOUNT SIZE

for i = 0 < FCOUNT
    xmath j "i + 1"
    getArray OFFSET 0 i
    getArray SIZE   0 j
    string NAME p= "%08X.dds" OFFSET

    math SIZE -= OFFSET

    log MEMORY_FILE2 OFFSET SIZE
    callfunction buildDDS

    get SIZE asize MEMORY_FILE
    log NAME 0 SIZE MEMORY_FILE
next i

startfunction BuildDDS
    get dwWidth  short MEMORY_FILE2
    get dwHeight short MEMORY_FILE2
    get dxtFlag1 byte  MEMORY_FILE2
    get dxtFlag2 byte  MEMORY_FILE2
    get dxtFlag3 byte  MEMORY_FILE2
    get dxtFlag4 byte  MEMORY_FILE2
    get unknown  long  MEMORY_FILE2 # looks like image size, but breaks some textures

    set dwMipMaps long 1

    if dxtFlag1 = 0xF0
        math dwFourCC = 0x31545844 # "DXT1"
        xmath dwPitch "dwWidth * dwHeight * 8 / 16"
    elif dxtFlag1 = 0xF3
        math dwFourCC = 0x33545844 # "DXT3"
        xmath dwPitch "dwWidth * dwHeight * 16 / 16"
    else
        print "Unknown flag %dxtFlag1%."
        cleanexit
    endif

    math dwFlags = 0x1007
    math dwCaps  = 0x1000

    math dwFlags += 0x80000
    math dwFlags2 = 0x04

    log MEMORY_FILE 0 128
    put 0x20534444 long MEMORY_FILE # "DDS "
    put 0x7C       long MEMORY_FILE
    put dwFlags   long MEMORY_FILE
    put dwHeight  long MEMORY_FILE
    put dwWidth   long MEMORY_FILE
    put dwPitch   long MEMORY_FILE
    put 0x00       long MEMORY_FILE
    put dwMipMaps long MEMORY_FILE

    goto 44 MEMORY_FILE SEEK_CUR

    put 0x20      long MEMORY_FILE
    put dwFlags2 long MEMORY_FILE
    put dwFourCC long MEMORY_FILE

    goto 20 MEMORY_FILE SEEK_CUR
    put dwCaps long MEMORY_FILE

    math SIZE -= 12

    append
    log MEMORY_FILE 12 SIZE MEMORY_FILE2
    append
endfunction
```
