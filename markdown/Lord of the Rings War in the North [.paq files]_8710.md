## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-07T13:56:02+00:00
- Post Title: Lord of the Rings: War in the North [.paq files]

I suspect one of the .paq files contains the texts of game, but sadly it can't be edited. Does anyone know how to unpack/repack/edit this archive?

Had to remove link, because of the new rules.
## Post #2
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-09T08:42:54+00:00
- Post Title: Lord of the Rings: War in the North [.paq files]

Any thoughts?
## Post #3
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-13T11:18:25+00:00
- Post Title: Lord of the Rings: War in the North [.paq files]

Anyone?
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-04-14T15:10:39+00:00
- Post Title: Lord of the Rings: War in the North [.paq files]

```
# QuickBMS script - created by The Bacter
# work-in-progress version!
IDString "pc\x00\x00"
get UNK_40000000 long
if UNK_40000000 != 0x40000000
  print "Error! Exiting. Current value: %UNK_40000000|h% Expected: 0x40000000"
  cleanexit
endif
get DATASIZE long
get UNK_00000004 long
if UNK_00000004 != 4
  print "Error! Exiting. Current value: %UNK_00000004|h% Expected: 0x4"
  cleanexit
endif
get DATASTART long
getdstring DUMMY 112
get NR_OF_FILES long
set TTSIZE long DATASTART
math TTSIZE -= 128
log MEMORY_FILE 128 TTSIZE
for i = 0 < NR_OF_FILES
  get FN_pos long
  get FN_len long
  get DIR_pos long
  get DIR_len long
  get DUMMY long
  get DUMMY long
  get File_REL_START long
  get File_Size long
  set THE_POS long DATASTART
  math THE_POS += File_REL_START
  goto  FN_pos MEMORY_FILE
  getdstring FN FN_len  MEMORY_FILE
  goto  DIR_pos MEMORY_FILE
  getdstring DIR DIR_len  MEMORY_FILE
  set FULLPATH string DIR
  string FULLPATH += "\"
  string FULLPATH += FN
  string FULLPATH += "."
  string FULLPATH += i
  log FULLPATH THE_POS File_Size
next i
```
## Post #5
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-14T18:30:18+00:00
- Post Title: Lord of the Rings: War in the North [.paq files]

Thank you, bacter!!!! These .paq files contain files with different number extensions. Can they be decoded or edited?
And one more question: can the paq files be repacked? The game doesn't read from external files.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-14T21:08:22+00:00
- Post Title: Lord of the Rings: War in the North [.paq files]

Read the new rules. Fast.
## Post #7
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-22T19:19:46+00:00
- Post Title: Lord of the Rings: War in the North [.paq files]

Bump.
