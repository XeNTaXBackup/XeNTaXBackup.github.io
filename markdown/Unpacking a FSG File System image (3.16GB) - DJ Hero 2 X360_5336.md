## Post #1
- Username: bowtie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 31, 2010 6:24 am
- Post datetime: 2010-11-01T18:36:58+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

So I need some help in extracting files from an FSG File System image. The image is from the DJ Hero 2 game for the XBOX 360 console. It is 3.16GB big and titled DISC0.IMG (well actually it was DISC0.IMG.PART1 & DISC0.IMG.PART2 which were joined using the "copy /b" command in Windows). This is not a file system image I created. This was one big file in the actual game disc.

[Here is the first 4MB of the file system image](http://www.mediafire.com/?77tfzxc674z736b)

Here are some things I discovered:
[*]The file system operates on a structure of chunks, 20000 hex (4KB). If a file is larger than that, it continues until the end of the file.
[*]Folders within the file system are prefixed with a D (capital d) and files are prefixed with a F (capital f). So if a folder is titled AudioTracks, the file system will show DAudioTracks. Or if a file is titled Settings.xml, it will show as FSettings.xml.

At offset 40000, there are 6 folders (DAUDIO, DArt, DFAR, DText, DTrackPacks) and 1 file (FAttributes_Global.xml). The file system continues with all 00 (hex) until offset 60000. At that offset, there are 6 folders (DCREDIT, DFEM, DGAME, DNET, DRES, DTRAC). Again all 00 (hex) until the next chunk at offset 80000. There are 7 TXT files listed in this chunk. And then all 00 (hex) until offset A0000. Here I see the first instance of a TXT file (English, which I believe is FRESE.txt listed in the offset 80000 chunk). And at offsets C0000 (French, FRESF.txt), E0000 (German, FRESG.txt), 100000 (Italian, FRESI.txt), are other TXT files.

If needed, I can post a bigger file. Just let me know how big and I'll upload it.

Thanks in advance. I appreciate any help you can offer.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-03T00:02:29+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

nothing significant, but there's a pointer or data size which is just outside the cut. is there anything at pos 5690563 (decimal) of interest - the end of the xml data for example?

edit:i think a larger chunk would be useful. 40 mb or so should be enough to see how other files are stored.

lazy wip-bms:

```
idstring "FSG-FILE-SYSTEM\x0"

get IMGPARTS long     # 2, IMG parts?
get SECTIONSIZE long  # size of data in this chunk (unaligned)
get UNKNOWN long
get LASTTABLE long    # pointer to table 3
get NEXTCHUNK long    # next chunk (multiple of 0x20000)
goto 0x2C
get NUMOFENTRIES long

goto 0x38

# table 1:

for i = 1 to NUMOFENTRIES

  get PTR1 long   # pointer far off (data pointer?)
  get WIDTH short # 256 or 512
  get PTR2 short  # pointer to table 2 structure

next i

# table 2:

for i = 1 to NUMOFENTRIES

  get UNKNOWN long
  get UNKNOWN long

next i

# table 3:

math T3 = SECTIONSIZE
math T3 -= LASTTABLE
math T3 /= 8

for i = 1 to T3

  ## really REALLY don't understand this..

  get NUMBER1 long
  get NUMBER2 long # NUMBER + 128 (0x80)

next i

goto NEXTCHUNK # 0x40000

callfunction GETNAMES


math NEXTCHUNK += 0x20000
goto NEXTCHUNK

callfunction GETNAMES




## next chunk has a 0x38 sized header
## first header was 0x3C, so that may be wrong

# strings exist here anyway, only from RES (assumation) not TRAC
# v.confusing




startfunction GETNAMES
  for
    get TYPE char
    get NAME string

    if TYPE = 'D'
      print "%NAME%"
    elif TYPE = 'F'
    else
       break
    endif

  next
endfunction

```
## Post #3
- Username: bowtie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 31, 2010 6:24 am
- Post datetime: 2010-11-03T02:52:34+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

Thanks for the help. [Here's a 50MB slice](http://www.mediafire.com/?pgro3megmja82tb) of the DISC0.IMG.

Also, I tried the quickbms script and it said...

```
------------------------------
- SCRIPT's MESSAGE:
  AUDIO

- SCRIPT's MESSAGE:
  Art

- SCRIPT's MESSAGE:
  FAR

- SCRIPT's MESSAGE:
  Text

- SCRIPT's MESSAGE:
  TrackPacks

- SCRIPT's MESSAGE:
  Xml

- SCRIPT's MESSAGE:
  CREDIT

- SCRIPT's MESSAGE:
  FEM

- SCRIPT's MESSAGE:
  GAME

- SCRIPT's MESSAGE:
  NET

- SCRIPT's MESSAGE:
  RES

- SCRIPT's MESSAGE:
  TRAC


- 0 files found in 0 seconds
Press RETURN to quit
```
## Post #4
- Username: bowtie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 31, 2010 6:24 am
- Post datetime: 2010-11-05T02:58:05+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

Bump.
## Post #5
- Username: bowtie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 31, 2010 6:24 am
- Post datetime: 2010-11-16T02:20:39+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

One last bump.

I've provided a 50MB slice of the image. The files contained in the image aren't encrypted or compressed, so where do I go from there?
## Post #6
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2011-04-14T05:05:42+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

I reaeeaally wanna get inside this game 

[I wrote a little Python script](http://aluigi.freeforums.org/post12429.html#p12429) that was supposed to solve this problem and it finds 108 files and when you look at them in fsbext you can see "nos71RiT" but when you type that in, it says the password is probably wrong. Any idea why?
## Post #7
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2011-04-14T15:21:11+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

Awesome. Solved it, at least for one track. Now if only we could automate this to just grab all the tracks.
```

REM The FSB file can be found inside DISC0.IMG.part0 within the DJ Hero 2 XBox 360 disc image at offset 41960000 hexidecimal. It ends just before a big block of zeroes. "00 00 00 00 00 00 00 00"

REM That FSB file can be opened with fsbext using password nos71RiT

REM fsbext will output a file called tmp338.tmp.xma

REM In tmp338.tmp.xma, the "d" in "data" occurs at offset 534. Adding 8h to that gives us 53c. Adding 800h to that gives us d3c. Adding 800h to that gives us 153c.

REM The result of running this batch file (assuming you have xma_text and towav) is perfect and totally skip-free!!

xma_test.exe tmp338.tmp.xma -o 53c -r track-1.bin
xma_test.exe tmp338.tmp.xma -o d3c -r track-2.bin
xma_test.exe tmp338.tmp.xma -o 153c -r track-3.bin

copy /b xma-header.bin+%track-1.bin track-1.xma
copy /b xma-header.bin+%track-2.bin track-2.xma
copy /b xma-header.bin+%track-3.bin track-3.xma

convall
rem convall just means @towav.exe *.*
```
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-17T17:09:21+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

I have done the job:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
idstring "FSG-FILE-SYSTEM\0"
get DUMMY long  # 00000002
get HEADER_SIZE long
get DUMMY long  # 0000653d
get DUMMY long  # 0000af58
get BASE_OFF long
get DUMMY long  # 00003e80
get DUMMY long  # 00000008
get FILES long
get DUMMY long  # 00000000
get DUMMY long  # 4c67d364
for i = 0 < FILES
    get DUMMY long
    get DUMMY byte
    get OFFSET threebyte
    savepos TMP
    goto OFFSET
    get OFFSET long
    get SIZE long
    get DUMMY long
    get DUMMY long
    math OFFSET *= 1024
    math OFFSET += BASE_OFF
    log "" OFFSET SIZE
    goto TMP
next i
```
I guess there are also the filenames somewhere in disc0.img (at the end?) but I'm sure this is enough
## Post #9
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-11-12T14:06:16+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

does anyone know how to open this game none of theses scripts will work for me
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-11-14T18:52:46+00:00
- Post Title: Unpacking a FSG File System image (3.16GB) - DJ Hero 2 X360

simple script to merge the disc0.img parts:

```
log FNAME 0 0
append
for i = 0
    string NAME p= "DISC0.IMG.part%d" i
    open FDSE NAME 0 EXISTS
    if EXISTS == 0
        break
    endif
    get SIZE asize
    log FNAME 0 SIZE
next i
append
```
