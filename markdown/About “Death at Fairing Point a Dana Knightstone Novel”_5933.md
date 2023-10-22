## Post #1
- Username: kaninchen
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 11, 2010 9:03 am
- Post datetime: 2011-01-27T16:39:17+00:00
- Post Title: About “Death at Fairing Point: a Dana Knightstone Novel”

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-01-29T07:40:04+00:00
- Post Title: About “Death at Fairing Point: a Dana Knightstone Novel”

Very nice game! I like it.
Here's my simple extractor for the .ARC file.
And here is the QuickBMS script:

```
#
# Death at Fairing Point: A Dana Knightstone Novel CE
# .ARC file extractor script for QuickBMS
#
# created by The Bacter
#
################################################################

comtype zlib

idstring "CRAS"
get Version long                       # (1)
get NrOfFiles long
get packedDirStartPos long             # points to the end of the file
get packedDirSize long
get unpackedDirSize long
get DataStartPos long                  # (0x24)
get DataSize long                      # (packedDirSize - 0x24)
get unknown long                       # (0x27A16205)


clog MEMORY_FILE packedDirStartPos packedDirSize unpackedDirSize
for i = 0 < NrOfFiles
  getdstring FileName 256 MEMORY_FILE
  get Start_Pos long MEMORY_FILE
  get Stored_Size long MEMORY_FILE
  get unk0 long MEMORY_FILE
  get Original_Size long MEMORY_FILE
  get Flag long MEMORY_FILE            # (1=zlib 2=stored)
  if Flag == 1
    clog FileName Start_Pos Stored_Size Original_Size
  elif Flag == 2
    log FileName Start_Pos Stored_Size
  else
    print "Error: Invalid Flag"
    cleanexit
  endif
next i

```
