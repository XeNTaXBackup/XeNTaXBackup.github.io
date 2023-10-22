## Post #1
- Username: Nukem
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 28, 2006 9:00 pm
- Post datetime: 2008-04-23T02:00:29+00:00
- Post Title: Threesome Adventure Archive

The demo of the adventure game ["So Blonde"](http://www.soblonde.de) (~400MB) archives its data via three distinct files. There are two bigger sets and one really small set which you can find [here](http://www.megaupload.com/de/?d=E4MRI75O) and also in the [attachment](http://forum.xentax.com/download/file.php?id=1497) (didn't see that at first ).

The DIR file obviously contains just a directory of names:
There are 16 ints which contain the starting address of a cstring in the same file each (like "edge_ramp.png").
Like all cstrings they are zero-terminated. That's all.

The DAT file is the biggest of the three and obviously contains the data:
It immediately starts with an ASCII text file (containing 3D material or shader descriptions).
Additional files follow padded with zeros each. Some offsets:

0000h: cg shader / material description
1200h: "
1E00h: "
2C00h: PNG file
2800h: cg
3800h: PNG
4400h: ogg vorbis file
etc.

There are 16 distinct file names in the DIR and 16 file offsets in the DAT I could identify (3 ogg, 3 png, 4 cg, 1 anim, 4 material, 1 overlay).

Now for the brain, the TOC file. It is supposed to connect all files in a parsable way. Here's what I found out:
It starts with magic number "PACK". I couldn't make much sense of the following bytes.
Start from the end of the file:
Omit 4 bytes.
You now can read 12-bytes at once - 15 times (one for each file (*)).
The first two bytes contain the offset in the DAT file (for the last entry this is 00 1E --> 1E00h (some cg shader stuff (see above))).
There are two zero bytes following.
There are six bytes of random (**) stuff following.
There are two zero bytes again.

So now for my questions:
[A] Why can I find 15 entries of 12 bytes each only (see (*) above), while there are 16 files?!
The last one (beginning at the end) is supposed to contain the offset 0000h, but it is 1052h. The file immediately at the beginning of DAT is the one missing, and there is no file at offset 1052h (it's in the middle of some shader stuff).

 The filenames in DIR and the data itself in DAT are NOT in the same order.
So there is supposed to be some connection between the entry with the data offset in the TOC and the filename in the DIR - I couldn't find any. 

[C] I couldn't find out, how the length of each data entry in DAT is stored in TOC. 

That's what (**) above is about: Of course the 6 bytes are NOT random, but contain important information. I couldn't find that out.
Additionally, the stuff after the 'PACK' is a mystery to me.

Is the connection made via a hash?! Is the length stored as a multiple of 256 or 512 bytes (remember there is padding at the end in DAT)?!

Thanks for helping me out, anybody.

I was just poking around in those files for the fun of it in the last 2.5 hours, now it's 4 am and I am going to get some sleep...  
[DATA.zip](https://xentaxbackup.github.io/file/1497_DATA.zip)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-04-23T11:14:40+00:00
- Post Title: Threesome Adventure Archive

You are lucky because I had some time to waste today!

TOC is chunk based structure, and the format is: 

```
char[4]    ChunkID
dword      Version
dword      DataSize
dword      DataCount
dword      ??
dword      ??
<data>
}
```


so the first chunk is "PACK" with 3 empty subchunk-> "MKRT", "OFFT" and "DEPT"

The second chunk is "REST" :
DataSize:0xC0
DataCount:0x10(16)

and the actual data start at 0x78 12bytes each(3 dword??)

```
 dword     ??
 dword     ofsLen       //the real size is this value divided by 4
 dword     ofsStart
}
```


Also it match the .dir file

```
6400    4B14->12C5  empty5s.ogg
2800    0EFC->03BF  actor3d_shadows.cg
8E00    0168->005A  preloadedanims.anim
5400    3FF8->0FFE  empty2s.ogg
1200    2F90->0BE4  actor3d_celshading.cg
7C00    02F4->00BD  fade.png
7800    0654->0195  fade.material
2C00    2C50->0B14  cel_shading_ramp.png
9000    0E10->0384  shadows.material
3800    2C40->0B10  edge_ramp.png
7E00    1C24->0709  object.material
4400    3FF8->0FFE  empty1s.ogg
7A00    0754->1D5   fade.overlay
8600    1ACC->06B3  object_celshading.cg
1E00    21A8->086A  actor3d_celshading11.cg
0000    45C8->1172  actor3d.material
```
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-26T08:47:06+00:00
- Post Title: Threesome Adventure Archive

Looking good, fatduck  Now we need a program that can open the files
## Post #4
- Username: Nukem
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 28, 2006 9:00 pm
- Post datetime: 2008-04-26T19:26:27+00:00
- Post Title: Threesome Adventure Archive

Hi fatduck, thanks for your fast response, and sorry for replying that late. 

Immediately the day after, after I've read your post, I began coding some unarchiving utility for checking out, whether the big files unarchive as well.
Unfortunately, I got little time thereafter, so that's why I'm writing so late. 

If I got time tomorrow, I will continue.

So far, thanks for pointing that out. 
I also thought about chunks, because of the 3 distinct "four-letter-words", but couldn't find out how these could actually fit together...
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-26T21:34:26+00:00
- Post Title: Threesome Adventure Archive

> Reply from Nukem
>
> I began coding some unarchiving utility for checking out, whether the big files unarchive as well.

Please do share the tool you create if it works out
## Post #6
- Username: theorbtwo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 10, 2008 9:19 pm
- Post datetime: 2008-08-10T14:48:09+00:00
- Post Title: Threesome Adventure Archive

An extractor for this is up at [http://desert-island.me.uk:8000/~theorb ... blonde.zip](http://desert-island.me.uk:8000/~theorb/unpack-soblonde.zip).  Please try it out and let me know how it goes, and any suggestions you have for next time -- this is my first one of these to be publicly posted.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-08-11T07:02:20+00:00
- Post Title: Threesome Adventure Archive

Nice, now I gotta get me some Perl
## Post #8
- Username: deant
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jul 15, 2013 6:11 pm
- Post datetime: 2014-03-14T16:17:40+00:00
- Post Title: Threesome Adventure Archive

> Reply from theorbtwo
>
> An extractor for this is up at http://desert-island.me.uk:8000/~theorb ... blonde.zip.  Please try it out and let me know how it goes, and any suggestions you have for next time -- this is my first one of these to be publicly posted.

Any chanse this exrtactor to be re-uploaded?:)
## Post #9
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-03-14T17:41:45+00:00
- Post Title: Threesome Adventure Archive

> Reply from deant
>
> Any chanse this exrtactor to be re-uploaded?:)
There is it. Attached.
[unpack-soblonde.zip](https://xentaxbackup.github.io/file/7090_unpack-soblonde.zip)
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-03-14T17:47:38+00:00
- Post Title: Threesome Adventure Archive

That is a perl script, if you don't want to run perl. You may wanty to try this QuickBMS script


```
# by Fatduck     May2012
# http://aluigi.altervista.org/quickbms.htm

open FDDE DAT 0
open FDDE DIR 1
open FDDE TOC 2

set OFSNAMEIDX 0
do 
   getdstring CHUNK 4 2
   get CUNKVER long 2
   get CHUNKSIZE long 2
   get NUMRES long 2
   getdstring DMY 16 2
while CHUNK != "REST"

for i = 0 < NUMRES
   get UNKNOWN long 2
   get RESSIZE long 2
   get OFSRES long 2
   math RESSIZE /= 4

   goto OFSNAMEIDX 1
   get OFSRESNAME long 1
   savepos OFSNAMEIDX 1
   goto OFSRESNAME 1 
   get RESNAME string 1

   log RESNAME OFSRES RESSIZE
next i
```
## Post #11
- Username: deant
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jul 15, 2013 6:11 pm
- Post datetime: 2014-03-16T00:01:31+00:00
- Post Title: Threesome Adventure Archive

Thanks alot both of you!!!
