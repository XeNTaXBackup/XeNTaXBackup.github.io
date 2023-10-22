## Post #1
- Username: Bonzomi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 10, 2012 9:36 pm
- Post datetime: 2012-09-09T02:19:53+00:00
- Post Title: [Request]Gensou Rondo model game files

Download links here:
[http://www.mediafire.com/?9734a92p4epu34c](http://www.mediafire.com/?9734a92p4epu34c)
[http://www.mediafire.com/?z3cc5acr9tqcq2a](http://www.mediafire.com/?z3cc5acr9tqcq2a)

The game is from CUBETYPE. [http://www.cubetype.com/](http://www.cubetype.com/)

The files are in .dat format, sorry but I have very, very limited knowledge of extracting models out of games, can someone help me with this?

[http://doujingravity.blogspot.com/2012/ ... rondo.html](http://doujingravity.blogspot.com/2012/08/genso-rondo.html)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-09T02:35:49+00:00
- Post Title: [Request]Gensou Rondo model game files

Oh, another cubetype game. I like their art.

This script should work.

The file is big endian, archive incremental xor'd starting with 0.
The dgo files are also incremental xor'd inside the archive (so like double encryption?), but the rest are not xor'd.

The textures are compressed or something. I haven't looked into it.
The dgo format is likely the same format as touhou koubutou (?), which I never actually figured out. Then again, I looked at it awhile ago so maybe it is not as difficult now.

```
# Author: Finale
# Script for QuickBMS

encryption "incremental xor" 0x00
get size ASIZE
log MEMORY_FILE 0 size

encryption "" 0x00
Endian big
idstring "AAFC" MEMORY_FILE
get unk long MEMORY_FILE
get unk long MEMORY_FILE
get unk long MEMORY_FILE
get FILES long MEMORY_FILE

for i = 0 < FILES
  get nameLen long MEMORY_FILE
  math nameLen *= 2
  getdstring UNAME nameLen MEMORY_FILE
  Set NAME UNICODE UNAME
  get unk long MEMORY_FILE
  get SIZE long MEMORY_FILE
  putarray 0 i NAME
  putarray 1 i SIZE
next i 

savepos OFFSET MEMORY_FILE
for i = 0 < FILES
  getarray NAME 0 i 
  getarray SIZE 1 i 
  
  string EXT = NAME
  string EXT |= "."
  
  # double encryption
  if EXT == "dgo" 
    encryption "incremental xor" 0x00
  endif
  log NAME OFFSET SIZE MEMORY_FILE
  
  encryption "" 0x00
  math OFFSET += SIZE
next i

```


I'll look at the dgo format tomorrow. Today, it is "koi to senkyo to chocolate" night.
[asd.jpg](https://xentaxbackup.github.io/file/5791_asd.jpg)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-09T18:17:47+00:00
- Post Title: [Request]Gensou Rondo model game files

Can't figure out the faces.
[utsuho.JPG](https://xentaxbackup.github.io/file/5795_utsuho.JPG)
## Post #4
- Username: Bonzomi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 10, 2012 9:36 pm
- Post datetime: 2012-09-10T10:38:31+00:00
- Post Title: [Request]Gensou Rondo model game files

A script? .... what to do with it? compile it? wait what how @_@
## Post #5
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-10T13:33:26+00:00
- Post Title: [Request]Gensou Rondo model game files

> # Gensou Rondo .dat unpacker
>
> # Author: Finale
>
> # Script for QuickBMS

> # Script for QuickBMS

It's a script for QuickBMS, a tool for decompiling/extract data from archived/compressed files.


Here some links:

[viewtopic.php?f=29&t=3525](http://forum.xentax.com/viewtopic.php?f=29&t=3525)
[viewtopic.php?f=29&t=6797](http://forum.xentax.com/viewtopic.php?f=29&t=6797)
