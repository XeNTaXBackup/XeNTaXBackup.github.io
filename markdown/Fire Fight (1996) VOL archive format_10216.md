## Post #1
- Username: alcexhim
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 05, 2013 9:37 pm
- Post datetime: 2013-03-11T11:59:44+00:00
- Post Title: Fire Fight (1996) VOL archive format

Hey guys,

I'm trying to understand the format of the VOL archive (at least, I think it's an archive...) used in the Windows game Fire Fight. It's a pretty old game (1996), and the company who created it no longer exists, so I don't see any issue with posting a single VOL file for the talented people at XeNTaX to look at.

It's important to note that there appears to be long sequences of plain text (though not always in English, I believe the developers were Polish or something) that are sprinkled with other non-readable values (usually one or two bytes in length)... LZSS perhaps?

It seems like it would be relatively easy to decompress, but the LZSS code I have isn't working for me. Any ideas? Your help would be greatly appreciated!
[params.7z](https://xentaxbackup.github.io/file/6260_params.7z)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-04-01T08:42:47+00:00
- Post Title: Fire Fight (1996) VOL archive format

as you note there are some compressed chunks

edit
found the demo online and finished the script

```
# Script for QuickBMS by WRS (xentax.com)
# Rev 2

comtype COMP_LZRW1

get FSIZE asize
math FSIZE -= 20

# 20-byte header at end of file

goto FSIZE
get UNCOMPRESSED_SIZE long
get DATA_TO_READ long
get FILE_COUNT long
get FILE_LIST_OFFSET long
get VERSION long

# Version check made by client v1.2

if VERSION == 0x42024202
  print "Volume is uncompressed (unknown method)"
  cleanexit
elif VERSION == 0x43024202
  # expected version
else
  print "Unsupported volume (%VERSION%)"
  cleanexit
endif

get FNAME basename
math CURPOS = 0

log MEMORY_FILE 0 0
append

for CHUNK = 1
  goto CURPOS
  get CHUNKSIZE short
  math CURPOS += 2
  clog MEMORY_FILE CURPOS CHUNKSIZE 0xfffff
  math CURPOS += CHUNKSIZE
  if CURPOS >= FSIZE
    break
  endif
next CHUNK

append

get NFSIZE asize MEMORY_FILE

# confirms header values:
#  UNCOMPRESSED_SIZE == NFSIZE
# debug
#log "rawdump" 0 NFSIZE MEMORY_FILE


## parse the filelist

goto FILE_LIST_OFFSET MEMORY_FILE

for f = 0 < FILE_COUNT

  getdstring FITYPE 260 MEMORY_FILE
  getdstring FINAME 292 MEMORY_FILE
  get FISIZE long MEMORY_FILE
  get UNKNOWN long MEMORY_FILE # 0
  get FIOFFSET long MEMORY_FILE
  get UNKNOWN long MEMORY_FILE # 95
  get UNKNOWN long MEMORY_FILE # 0

  print "Extracting type %FITYPE% :"
  log FINAME FIOFFSET FISIZE MEMORY_FILE
  
next f



```
## Post #3
- Username: alcexhim
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 05, 2013 9:37 pm
- Post datetime: 2013-04-14T00:23:02+00:00
- Post Title: Fire Fight (1996) VOL archive format

Hmmm... I knew there were bits that had been compressed, but I was having difficulty figuring out which compression method it was. According to your script, it's LZRW1... I started researching that, found out that it was invented around the early 1990s... with not many implementations, which is probably why I hadn't recognized it like DEFLATE or gzip.

Your BMS script works great! But one of the reasons I joined this forum (besides asking for help with this file format, which I've wanted to open up for years!) was to learn more about the art of reverse-engineering. So, if you don't mind me asking, how did you figure this one out? It would have never occurred to me to start looking for a "header" at the END of the file...

Also, I'd like to use your information to build an asset creation studio for this game (and probably others using the Chaos Works engine, though there is only one other game I know of by this studio and it's in Polish   )

If it's okay with you, how should I credit you for your hard work?

Thank you for the assistance, it is greatly appreciated!
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-04-15T16:26:38+00:00
- Post Title: Fire Fight (1996) VOL archive format

I credit aluigi for starting my interest here - he has created some amazing tools - but this forum is packed with little challenges if you want to get started

I will direct you to the Wiki: [http://wiki.xentax.com](http://wiki.xentax.com)
And the definitive guide to exploring game resources: [http://wiki.xentax.com/index.php?title=DGTEFF](http://wiki.xentax.com/index.php?title=DGTEFF)

So for the decompression routine

From a hex editor you could tell it was lzss-variant
I used a aluigi's comtype scanner script to figure out the compression [http://aluigi.altervista.org/quickbms/comtype_scan.htm](http://aluigi.altervista.org/quickbms/comtype_scan.htm)



Finding the header comes with experience

I try to describe all my variables when I document a format
This also typically helps understand where various sizes or offsets come from

Before I found the filelist I thought each chunk was a file until I found the file_size wasn't equal to the number of chunks. Once the data was decompressed you can figure out things like the size of each file list entry using simple math

```
UNCOMPRESSED_SIZE - FILE_LIST_OFFSET / FILE_COUNT
```


The string sizes are non-standard, so that's something I likely have wrong but its often enough just to extract

I downloaded the game afterwards and found the version check. Sadly the routine exits when it hits an uncompressed file though.

For your program, please just link to XeNTaX somewhere in your credits
