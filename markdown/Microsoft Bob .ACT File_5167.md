## Post #1
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2010-10-10T23:46:59+00:00
- Post Title: Microsoft Bob .ACT File

I was looking at my software collection the other day when I found an old copy of Microsoft Bob.
I really wanted to rip the character sprites but unfortunately they were not any old image files, but instead I got a bunch of .ACT files.  

Does anyone know how to decompress these files?

Download: [https://docs.google.com/leaf?id=0B-Tp7j ... Njgx&hl=en](https://docs.google.com/leaf?id=0B-Tp7j4ENOEvYjA1ZGViNjAtNWMxZS00YzhkLWJlOWQtMThhNTNiOGM1Njgx&hl=en)

Edit: I was looking at Rover's .ACT file with TiledGGD and here is the result:
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-11T20:01:58+00:00
- Post Title: Microsoft Bob .ACT File

wrong section - these act files are not compressed.

but its not a graphical format either. its a container, with dialogue texts and their prompt phrases and WAV data. but its not a game container.. so maybe this is the right section   


looking at it from an archive pov, the RIFF data is packed together. each file is easy to slip, as the chunks have a chunk size.

but the graphics. on a brief look, the header isn't very informative;

```
  uint16 unknown -- 0
  uint16 unknown -- 1
  uint16 ActorNameLength
  uint32 EOH -- end of header pointer (skips actor name)
  uint32 FileSize
  char ActorName[ ActorNameLength ]

```


the dialogue strings need to be split, so their length must be defined somewhere. the prompt phrases too.
the characters are animated sprites, so i'm expecting a frame count and number of animations.

thats my quick scan for now.
## Post #3
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2010-10-11T22:32:40+00:00
- Post Title: Microsoft Bob .ACT File

So if .ACT files aren't image files, what about these .ANIs?  

Download: [https://docs.google.com/leaf?id=0B-Tp7j ... YTM3&hl=en](https://docs.google.com/leaf?id=0B-Tp7j4ENOEvOGFmNDMzMGUtYjRjMC00YTMwLWE3OWItM2IzN2FmZTEyYTM3&hl=en)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-12T13:47:19+00:00
- Post Title: Microsoft Bob .ACT File

no no, the act files DO contain the graphics - i was getting distracted.
my point was that the format is a container, so shouldn't be treated as a raw image file - like you tried to do with tiledggd.

i took at look at the later office assistant format - and found there is even an official tool ([http://www.microsoft.com/downloads/en/d ... c122ef8eb6](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=c21be0ec-1712-427d-a43d-94c122ef8eb6))

its helpful to consider what values might be stored. learning about the graphics this way can also hint towards things like the palette - 256 colors - and since it uses timed animation - there could be some gif-like data.

i also found a screenshot of rover in msbob and can begin to understand the strings table (there is no null-terminator, so the string size and position must be stored etc). also can explain the poor gramma
## Post #5
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2010-10-13T00:17:39+00:00
- Post Title: Microsoft Bob .ACT File

Here is a full hex dump of ROVER.ACT: [https://docs.google.com/leaf?id=0B-Tp7j ... NzU0&hl=en](https://docs.google.com/leaf?id=0B-Tp7j4ENOEvODYxMjdjN2MtMDM5Yi00MzcyLWI0ZGMtMThhZjM4Nzg4NzU0&hl=en)

Each line is like much this:

```
00000000 4C 50 01 00 00 00 01 00 06 00 18 00 00 00 2D 8F 06 00 52 6F 76 65 72 00 46 00 01 00 C9 00 01 00 LP............-...Rover.F.......
```


Towards the bottom of the file, you can see most of Rover's text strings.  

Compare:



Ripped strings:

Rover's Ramblings

Did you know that Hopper used to be the main prize at a fair? It's true. Then one day she fell off the truck and wandered in here!

Onward, Rover!
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-13T01:03:04+00:00
- Post Title: Microsoft Bob .ACT File

now you're distracting yourself from the graphics!

already written a script to dump the strings and audio files, just hadn't gotten anywhere with the sprites.

```

idstring "LP\x1\x0"
get NUM short # 0
get NUM short # 1
get NAMELEN short
get HEADSIZE long
get FILESIZE long
getdstring ACTORNAME NAMELEN # null terminated

print "Actor: %ACTORNAME%"

## MISC DATA

getdstring UNKNOWN 42

## POINTERS
# Note: Offsets relative to end of header

get NUM long
get PAUDIO long
get NUM long
get NUM long
get NUM long
get STRTABLE long # packed strings
get PSTRINGS long


## Dump strings
math PSTRINGS += HEADSIZE
math STRTABLE += HEADSIZE

goto PSTRINGS

get NUM long

math NUM *= 6
savepos POS
math POS += NUM
goto pOS

get SIZE asize

append
log MEMORY_FILE 0 0

for i = 1

  get SPTR long
  get SSIZE short

  math SPTR += STRTABLE

  log MEMORY_FILE SPTR SSIZE
  set MEMORY_FILE binary "\xd\xa"

  savepos POS
  if POS == SIZE
    break
  endif

next i

print "Found %i% phrases!\n\nDumping.."

append

get SIZE asize MEMORY_FILE
log "strings.txt" 0 SIZE MEMORY_FILE


```


now lets get back to the graphics
## Post #7
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2010-10-13T01:43:06+00:00
- Post Title: Microsoft Bob .ACT File

OK, I will try and keep with the graphics.  

Sorry to be off-topic, but ZSPEAKER.ACT and ZVISIBLE.ACT don't appear to have sounds, so your script may not work with them.
And looking through HOME.EXE with a hex editor shows a buch of strings. I'll rip them.  
Edit: Rippped 1 string,the string is: Bob Birthday. Perhaps Bob Birthday is a canned part of Bob?  

Getting back to the graphics, this .dll and this .mdb may provide some help. And some sounds + strings.  

Download .DLL: [https://docs.google.com/leaf?id=0B-Tp7j ... OTkz&hl=en](https://docs.google.com/leaf?id=0B-Tp7j4ENOEvZWZhZTYyYjEtYjg0Zi00MjBlLWIyYmQtMTUyY2U1YzRiOTkz&hl=en)
Download .MDB: [https://docs.google.com/leaf?id=0B-Tp7j ... ODYy&hl=en](https://docs.google.com/leaf?id=0B-Tp7j4ENOEvMGRkNjMwNTgtZjg3Mi00Yzk5LWE4YzEtNGI4MjZkYjVlODYy&hl=en)

BTW, I found 2 more .ACT files in BOB's data.

Download: [https://docs.google.com/leaf?id=0B-Tp7j ... NmE3&hl=en](https://docs.google.com/leaf?id=0B-Tp7j4ENOEvMmNmZTkwYzUtZjg2MS00ODYxLWEyOTMtNDY2ZTI2ZGNiNmE3&hl=en)
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-12T20:55:36+00:00
- Post Title: Microsoft Bob .ACT File

after your tipoff about using wmf files, i looked up the format spec and made a signature just to dump the sprites out.
unfortunately, wmf files using gdi object calls (early vector method) may produce some strange images (at least they did on my windows machine)

```
#    xentax.com
#    [BMS] Microsoft Bob *.ACT - Sprite Extractor


idstring "LP\x1\x0"
get NUM short # 0
get NUM short # 1
get NAMELEN short
get HEADSIZE long
get FILESIZE long
getdstring ACTORNAME NAMELEN # null terminated

math i = 1
string PREFIX = ACTORNAME

for

  # WMF format signature
  findloc NXT string "\x0\x9\x0\x0"

  if NXT = ""
    cleanexit
  endif

  math NXT -= 1
  goto NXT

  # META_HEADER (from MS-WMF.pdf)

  get TYPE short
  get HEADERSIZE short
  get VERSION short
  get SIZE long
  get OBJCOUNT short # technically the number of GDI calls
  get MAXRECORD long
  get RESERVED short
  
  # 0x12 (18) bytes

  math SIZE *= 2
  math SIZE += 4
  math SIZE += 18

  string FNAME = PREFIX
  string FNAME += i
  string FNAME += ".wmf" # or let qbms auto-detect

  log FNAME NXT SIZE

  math SIZE -= 18
  math NXT += SIZE
  goto NXT

  math i += 1

next

```


will look into writing up the act spec with strings, wavs and wmfs as there doesn't seem to be one for this early format.

wmf spec: [http://msdn.microsoft.com/en-us/library/cc215212.aspx](http://msdn.microsoft.com/en-us/library/cc215212.aspx)

i've attached one of the wmf files it extracted which i converted to png easily enough
[Rover1.PNG](https://xentaxbackup.github.io/file/3594_Rover1.PNG)
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-13T00:59:52+00:00
- Post Title: Microsoft Bob .ACT File

actually, i've misread the spec. the wmf files in the act format all have "placeable header records" preceding the header record, which was why i was getting the incorrect scale on some of the images...  

so that script works, but produces incorrect files. dont plan to fix it though - will finish writing the new script which handles all sections
## Post #10
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2010-11-14T04:43:27+00:00
- Post Title: Microsoft Bob .ACT File

Great work!  

I just noticed how identical MS BOB .ACT files are to Office 97 .ACT files.
And that both of those are the ancestors to Microsoft Agent .ACS files.
Maybe, after we're done with MS BOB, we could work on Office 97 and Microsoft Agent.
## Post #11
- Username: mugenmidget
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 03, 2016 2:27 am
- Post datetime: 2016-06-02T18:34:33+00:00
- Post Title: Microsoft Bob .ACT File

Apologies for the super necro bump  , but I'm trying to extract WMFs from "CLIPPIT.ACT" (Office 97) using your script and not having any luck:

```
- open script clippyrip.bms
- set output folder .

  offset   filesize   filename
--------------------------------------
  0000005e 33554452   Clippit1.wmf

- The following output file already exists:
  Clippit1.wmf
  Do you want to overwrite it?
    y = overwrite (you can use also the 'o' key)
    n = skip (default, just press RETURN)
    a = overwrite all the files without asking
    r = automatically rename the files with the same name
    s = skip all the existent files without asking

y

Error: incomplete input file 0: E:\utils\quickbms\CLIPPIT.ACT
       Can't read 580404 bytes from offset 0007252a.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   101%   476408     468266

Last script line before the error or that produced the error:
  49  log FNAME NXT SIZE

```


I changed the idstring portion to "idstring "LP\x2\x0"", BTW (it looked like it had a slightly different header).

It looks like it's reading too large of a file size.  Did you ever do another version of this script?  Or could you make it work with an Office97 ACT?  Sorry for the bother, just thought I'd try asking!
## Post #12
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-06-02T21:59:10+00:00
- Post Title: Microsoft Bob .ACT File

> Reply from mugenmidget
>
> Apologies for the super necro bump  , but I'm trying to extract WMFs from "CLIPPIT.ACT" (Office 97) using your script and not having any luck:

I changed the idstring portion to "idstring "LP\x2\x0"", BTW (it looked like it had a slightly different header).

It looks like it's reading too large of a file size.  Did you ever do another version of this script?  Or could you make it work with an Office97 ACT?  Sorry for the bother, just thought I'd try asking!

i'd be suspicious of changing the idstring- that normally indicates something has changed!

do you have a sample file? i think the SIZE calculation is wrong in the my script for your new version
## Post #13
- Username: mugenmidget
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 03, 2016 2:27 am
- Post datetime: 2016-06-02T22:08:16+00:00
- Post Title: Microsoft Bob .ACT File

Oh, yeah, here you go:

[https://mega.nz/#!jJ1FxLIb!mBvB3Lj2nlUD ... sCx2XbGmH4](https://mega.nz/#!jJ1FxLIb!mBvB3Lj2nlUDn0krtjYE0snj7VpdNruqQsCx2XbGmH4)

And you were right, changing the idstring basically made it seek later in the file (I think).  Instead I just truncated the file to the first WMF header, removed that ACT file header search (first part of your script), and was able to extract the WMFs!  Thanks for posting it!
