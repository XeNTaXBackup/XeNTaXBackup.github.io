## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-05-31T22:26:39+00:00
- Post Title: AKIBAS TRIP Undead Undressed

volume.dat extractor

```
#by chrrox
#AKIBAS TRIP Undead Undressed
endian BIG
get MAGIC long
get FILES long
get FILES2 long
get BASE long
get UNK long
savepos TMP
for i = 0 < files
   goto TMP
   get HASH long #?
   get OFFSET long
   get SIZE long
   get COMTYPE long
   get NAMEOFF long
   get NSIZE long
   savepos TMP
   set ZSIZE NAMEOFF
   math ZSIZE -= OFFSET
   math OFFSET += BASE
   math NAMEOFF += BASE
   goto NAMEOFF
   getdstring NAME NSIZE
   if ZSIZE == SIZE
      log NAME OFFSET ZSIZE
   else
      clog NAME OFFSET ZSIZE SIZE
   endif
next i
```
## Post #2
- Username: dragons
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 24, 2011 5:21 pm
- Post datetime: 2015-06-03T13:13:59+00:00
- Post Title: AKIBAS TRIP Undead Undressed

thank you 

but , how can I use it ?
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-06-03T13:48:46+00:00
- Post Title: AKIBAS TRIP Undead Undressed

> Reply from dragons
>
> thank you 

but , how can I use it ?
It's a script for Quickbms!
