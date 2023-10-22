## Post #1
- Username: x111
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 08, 2011 7:11 am
- Post datetime: 2011-02-07T23:31:41+00:00
- Post Title: orange box ps3 *.grp

hello, in archive STREAMED_SOUNDS.GRP  (*.waw files) how unpacked, replace the files and pack back?
[http://www.megaupload.com/?d=BVG2DRMK](http://www.megaupload.com/?d=BVG2DRMK)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-02-08T00:55:27+00:00
- Post Title: orange box ps3 *.grp

The file you uploaded it's a compressed with zlib and contains 3 small wav (pcm 16 bits)
Maybe someone can make a bms or tool.
## Post #3
- Username: x111
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 08, 2011 7:11 am
- Post datetime: 2011-02-08T01:34:11+00:00
- Post Title: orange box ps3 *.grp

where to download script for quickbms?
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-02-08T15:37:39+00:00
- Post Title: orange box ps3 *.grp

> Reply from x111
>
> where to download script for quickbms?
No idea.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-21T23:13:41+00:00
- Post Title: orange box ps3 *.grp

```
idstring "FGP\0"
get DUMMY long
get FILES long
get DUMMY long
math BASE_OFF long FILES
math BASE_OFF *= 16
math BASE_OFF += 0x10
for i = 0 < FILES
    get NAME_CRC long
    get OFFSET long
    get SIZE long
    get ZSIZE long
    math OFFSET += BASE_OFF
    clog "" OFFSET ZSIZE SIZE
next i
```
## Post #6
- Username: AndyAwe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 14, 2014 3:07 am
- Post datetime: 2014-09-28T04:57:31+00:00
- Post Title: orange box ps3 *.grp

Hi, can somebody help me, the game loads the text from this file INIT.GRP => 000000e5.dll (analog _preload_section.pre from XBOX) , I may be wrong, but experiments have confirmed this, has anyone any ideas how to get to unpack/pack the file? 
[https://mega.co.nz/#!xYAzTBIb!pZeHr4XSB ... AqOsaWRQGA](https://mega.co.nz/#!xYAzTBIb!pZeHr4XSBxhTKy7_uRFNTRRj1rv2ggMYtAqOsaWRQGA)
## Post #7
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2016-06-12T14:10:49+00:00
- Post Title: orange box ps3 *.grp

how i repack *.GRP files pls ??
## Post #8
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2016-06-19T13:28:52+00:00
- Post Title: orange box ps3 *.grp

Packing *.grp 

quickbms -w -r [orange_box.bms] [name.grp] [folder]
