## Post #1
- Username: njb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 18, 2010 5:16 pm
- Post datetime: 2011-03-21T03:24:18+00:00
- Post Title: Moonbuggy 98 MOON.SZ

Hi all,
I've researched these MOON.SZ files from Moonbuggy 98, and I can successfully unpack and pack it using a pair of python scripts I wrote.
I do have one question, however.
The file structure is itself is very simple. For each file there is a 64 byte header, followed by zlib compressed data.

```

32 bit integer for the Compressed Length
32 bit integer for the Uncompressed Length
<8 unknown bytes all but one is 0x00, possibly a bitfield, and maybe space for more metadata in the future?>
48 byte null padded filename

<File data>

```

I was wondering if anyone had an idea what those unknown bytes might be.
The lowest bit in the first byte of the unknown area is always set, I figured it might have something to do with compression - clearing the bit and packing the data plain simply resulted in a crash, so that can't be it.
For completeness, does anybody have an idea what this bit might be used for?
You can grab the demo [here](http://download.chip.eu/en/Moonbuggy-98_31461.html).
And my copy of MOON.SZ [here](http://www.speedyshare.com/files/27519003/MOON.SZ).
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-21T07:12:50+00:00
- Post Title: Moonbuggy 98 MOON.SZ

script for quickbms:

```
for OFFSET = 0 < FULL_SIZE
    get ZSIZE long
    get SIZE long
    get ZIP long
    get DUMMY long
    getdstring NAME 0x30
    savepos OFFSET
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
    math OFFSET += ZSIZE
    goto OFFSET
next
```
