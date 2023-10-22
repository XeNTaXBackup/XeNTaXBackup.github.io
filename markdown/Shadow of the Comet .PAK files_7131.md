## Post #1
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2011-08-06T22:33:36+00:00
- Post Title: Shadow of the Comet .PAK files

Hi, 

I've been looking into .PAK files from 1993 adventure game Shadow of the Comet.  If I am not mistaken, these resource files are chunk-based, where each file entry size is 36 bytes, where bytes 11 and 12 are the file size, and the last 12 bytes are the filename.  The file entry size is followed by the file itself, then another file entry begins. 


However, I could not figure out where do the files themselves begin (there is a variable size header which I cannot decypher), nor what the bytes in each entry mean aside from the filesize and filename, and a few correspondences between file entries (like, the last 4 bytes before the filename are the same for every file entry).

Can anyone help me figuring this out? I'm trying to make a resource extractor for this game, with the intention of making a background viewer.


I've attached a few of these files, plus HEX Workshop bookmarks for two of them.
[floppy.rar](https://xentaxbackup.github.io/file/4586_floppy.rar)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-07T17:31:30+00:00
- Post Title: Shadow of the Comet .PAK files

quick name parser (no idea on the algo used)

```

for i = 0
  savepos POS
  get FILEPOS long
  if FILEPOS == 0
    break
  endif

  #putarray 0 i FILEPOS # could be useful to check
next i

goto POS

# there are i files here

for j = 0 < i

  get DUMMY long
  get ZSIZE long # packed size
  get SIZE long  # unpacked size ?
  get ISCMP short# compression flag?
  get NSTRUCT short

  get UNKNOWN short
  getdstring NAME 18 #

  savepos DATAPOS

  # log NAME DATAPOS ZSIZE
  # or
  # clog NAME DATAPOS ZSIZE SIZE (when you know the algo)

  math DATAPOS += ZSIZE
  goto DATAPOS

  print "%j%: %NAME% at %DATAPOS%"

next j

```
## Post #3
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2011-08-07T19:15:10+00:00
- Post Title: Shadow of the Comet .PAK files

So the files are compressed, then?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-07T19:45:30+00:00
- Post Title: Shadow of the Comet .PAK files

i think so, see the size field i marked
