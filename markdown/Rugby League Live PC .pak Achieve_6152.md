## Post #1
- Username: Wouldubeinta
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 27, 2010 4:58 am
- Post datetime: 2011-02-28T12:45:26+00:00
- Post Title: Rugby League Live PC .pak Achieve

Hi there, I was just wondering if someone could help me make a bms script to extract and repack this easy layout achieve.

Any help would be much appreciated.



This is my understanding of the pak.pak format starting at the begining of the file-


How many pak achieves?

00 00 00 03


Version Number?

00 00 00 01


How many files in the achieve (little endian)

00 00 03 38


String name length (Folder & Files name)

0F


String name (Folder & Files name)

sound/music.fsb


File start offset (little endian)

E0 A7 00 00 


Dummy (long)

00 00 00 00


File size (little endian)

E0 AD 2A 14
[pak lba table.zip](https://xentaxbackup.github.io/file/3997_pak lba table.zip)
## Post #2
- Username: Wouldubeinta
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 27, 2010 4:58 am
- Post datetime: 2011-03-01T03:01:45+00:00
- Post Title: Rugby League Live PC .pak Achieve

This is the bms script to extract the pak file for quickbms from Luigi Auriemma. Now all I need now is a script to repack the pak file.

###
open "." "pak.pak" 1
endian big
get DUMMY long 1
get DUMMY long 1
get FILES long 1
endian little
for i = 0 < FILES
   get NAMESZ byte 1
   if NAMESZ == 0
       cleanexit
   endif
   getdstring NAME NAMESZ 1
   get OFFSET long 1
   get OFFSET64 long 1
   get SIZE long 1
   if OFFSET64 != 0
       print "QuickBMS doesn't support 64bits (%NAME%)"
   else
       log NAME OFFSET SIZE
   endif
next i
###

This script is for the pak1.pak file -

###
open "." "pak1.pak" 1
endian big
get DUMMY long 1
get DUMMY long 1
endian little
get FILES long 1
for i = 0 < FILES
   get NAMESZ byte 1
   if NAMESZ == 0
       cleanexit
   endif
   getdstring NAME NAMESZ 1
   get OFFSET long 1
   get OFFSET64 long 1
   get SIZE long 1
   if OFFSET64 != 0
       print "QuickBMS doesn't support 64bits (%NAME%)"
   else
       log NAME OFFSET SIZE
   endif
next i
###
## Post #3
- Username: Wouldubeinta
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 27, 2010 4:58 am
- Post datetime: 2011-03-01T06:37:54+00:00
- Post Title: Rugby League Live PC .pak Achieve

My girl friend just donated 20 euros to [register@xentax.com](mailto:register@xentax.com) So maybe now I might get some help helpfully
