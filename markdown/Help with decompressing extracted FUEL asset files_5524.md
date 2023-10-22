## Post #1
- Username: vetron
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 14, 2010 7:21 am
- Post datetime: 2010-12-10T18:13:00+00:00
- Post Title: Help with decompressing extracted FUEL asset files

Hi

I've been trying to decompress some files for the PC game FUEL that I'm working on a mod project for. They are originally in a .dpc  container,  which I've seen already extracted using the .bms script posted in this thread: [viewtopic.php?f=18&p=30960](http://forum.xentax.com/viewtopic.php?f=18&p=30960)

Some of the files I'm trying to work with (contained within these .dpc containers) appear to be compressed, the point of the files in question is text scripts that controls the placement of assets within a race that is called upon when the race of matching name is launched in the game. 

Would anyone here be able to help decompress this file or at least take a look at the files attached and point me in the right direction to identifying the compression used (I've been struggling with this one for a while). Any help would be appreciated   

In the attached file.zip:
USA1_CR5_251C2C68.DPC  (original container)
file1.bin  (the extracted file... this is particular file I'm having trouble with, as it appears to have some compression, although there are a handful of plain text strings towards the file beginning)
dpc.bms (original script taken from [viewtopic.php?f=18&p=30960](http://forum.xentax.com/viewtopic.php?f=18&p=30960))
[file.zip](https://xentaxbackup.github.io/file/3682_file.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-10T19:43:37+00:00
- Post Title: Help with decompressing extracted FUEL asset files

haven't checked the dpc script, but the bin format has data blocks.
they can be parsed like so, but i haven't looked into anything else yet

```

get FSIZE asize

for
  get SIZE long # + 28 to get real structure size

  get UN1 long  # size of header (inside data) ??
  get UN2 long  # size of uncompressed data
  get UN3 long  # compressed size, or 0 when data is uncompressed

  get HASH1 long # data type id ?? (see text example below)
  get HASH2 long
  get HASH3 long

  if HASH1 = 1391959958
    # UN1 is the size of the header, or sizeof(long) == 4

    get STRLEN long       # with text, its the length ?
    getdstring STR STRLEN

    print "Found string: %STR%"
  else
    math SKIP = SIZE
    math SKIP -= 4
    getdstring DATA SKIP

  endif

  savepos POS
  if POS == FSIZE
    print "EoF. Parsing success!"
    cleanexit
  endif
next

```
