## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-08-31T09:48:10+00:00
- Post Title: [request]bms script for dump irb from dat(resistance 2/3)

The files from Resistance 2/3 and ratchet and clank for ps3 are stored in dat files, these dat files are composed by multiple *.irb files with header identifier "IGHW".



can someone write a quickbms script for decompose the big *.dat file to all little *.irb files?

here a example:

[http://www.mediafire.com/download/rt6n5 ... /mobys.rar](http://www.mediafire.com/download/rt6n5wz3wuj1n6r/mobys.rar)

thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-01T08:29:55+00:00
- Post Title: [request]bms script for dump irb from dat(resistance 2/3)

though it's not too hard in qbms i prefer using "C".
[http://www.uploadmb.com/dw.php?id=1409559891](http://www.uploadmb.com/dw.php?id=1409559891)
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-09-02T04:02:52+00:00
- Post Title: [request]bms script for dump irb from dat(resistance 2/3)

thanks a lot shak-otay the application works great.

Can you explain me how to dump files with known header from a big file plase? ...(how works the logic based in your tool) I have some other files with same structure.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-02T08:00:37+00:00
- Post Title: [request]bms script for dump irb from dat(resistance 2/3)

> Reply from luxox18
>
> Can you explain me how to dump files with known header from a big file plase? ...(how works the logic based in your tool)There's two loops: the first one searches for the pattern "IGHW" (49474857)
and logs the found offsets into an address array. The second loop dumps the irb files starting at offset addr with a size of (addr[i+1] - addr)

This is the first loop as a qbms script findPattern.bms.
It searches for "GHW" to keep it simple and logs the offset addresses of the findings to patternOffs.bin.

```
# usage: quickbms findpattern.bms archive.dat

log MEMORY_FILE 0 0

set i long 0
set OFFSET long 0
set offs long 0
do
    findloc OFFSET string "\x47\x48\x57" 0 0
    if OFFSET != 0
        math i += 1
        math offs = OFFSET
        math offs -= 1
        Put offs Long MEMORY_FILE
        math OFFSET += 3
        goto OFFSET
    endif
while OFFSET != 0

if i != 0
    print "finds %i%"
    Get sizeF1 ASIZE MEMORY_FILE
    Log "patterOffs.bin" 0 sizeF1 MEMORY_FILE
else
    print "pattern not found!"
    cleanexit
endif

```

example of patternOffs.bin:

```

00000  00 00 00 00 80 B8 00 00  80 D8 0E 00 80 9E 12 00
00010  80 F1 13 00 80 58 28 00  00 9A 28 00 00 51 2F 00
```

found addresses: 0x0, 0xB880, 0xED880, 0x129E80 etc.
of IGHW (== addresses of "GHW" - 1)

> I have some other files with same structure.
Here's the complete dat2irb.bms - should not be too hard to adapt it for other patterns to be searched for:

```
# usage: quickbms dat2irb.bms archive.dat

# this script takes into account that the first pattern find in the .dat
# files is at offset 0x0, so it's searching for "GHW" instead of "IGHW"
# keep this in mind if you want to adapt the script for another pattern search

log MEMORY_FILE 0 0

set i long 0
set OFFSET long 0
set offs long 0
set size long 0
set start long 0
set endAddr long 0

do
    findloc OFFSET string "\x47\x48\x57" 0 0
    if OFFSET != 0
        math i += 1
        math offs = OFFSET
        math offs -= 1
        Put offs Long MEMORY_FILE
        math OFFSET += 3
        goto OFFSET
    endif
while OFFSET != 0

if i != 0
    print "finds %i%"
    #Get sizeF1 ASIZE MEMORY_FILE
    #Log "patternOffs.bin" 0 sizeF1 MEMORY_FILE
else
    print "pattern not found!"
    cleanexit
endif

goto 0 MEMORY_FILE
Get start Long MEMORY_FILE
do
    Get endAddr Long MEMORY_FILE
    math size = endAddr
    math size -= start
    #print "%i%: size: %size%"
    Math fname = i ;
    string fname += .irb ;
    log fname start size
    math start = endAddr
    math i -= 1
while i > 1
Get endAddr ASIZE 0 
math size = endAddr
math size -= start
Math fname = i ;
string fname += .irb ;
log fname start size
print "\nirb numbering is starting from top not from '1.irb'.\n Sry for that! :D"
```
## Post #5
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-09-04T03:38:38+00:00
- Post Title: [request]bms script for dump irb from dat(resistance 2/3)

thanks for all shakotay!
## Post #6
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-11T22:31:37+00:00
- Post Title: [request]bms script for dump irb from dat(resistance 2/3)

Any chance you can include file names?

The file name and path for each irb always starts after this bit of padding
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-18T22:16:14+00:00
- Post Title: [request]bms script for dump irb from dat(resistance 2/3)

> Reply from o0DemonBoy0o
>
> Any chance you can include file names?
The file name and path for each irb always starts after this bit of padding
here is a bms script to split the mobys.dat with file names  

```
goto 0x0
findloc OFFSET binary "\x49\x47\x48\x57"
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET binary "\x49\x47\x48\x57" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE - OFFSET
    math OFFSET + 52
    goto OFFSET
    endian big
    get nameOFF long
    math OFFSET - 52
    math nameOFF + OFFSET
    goto nameOFF
    get NAME string
    log NAME OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```
