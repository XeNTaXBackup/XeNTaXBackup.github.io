## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-07T23:46:06+00:00
- Post Title: compression signatures

Do you know any compression signatures that could be used to identify compressions ( just like 78 xx for zlib)?
I'd love to write a compression detector.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T21:49:24+00:00
- Post Title: compression signatures

zlib:
78 01 - No Compression/low 
78 9C - Default Compression 
78 DA - Best Compression
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T21:50:46+00:00
- Post Title: compression signatures

> Reply from john_doe
>
> All data from Outcast is compressed using the PKWare Data Compression Library. You can find decompression source code on the web. 
The first two bytes (0x00 0x06) are the PKDCL header. There are other variations, too, they should be in the decompression code. Could be useful for your detection tool.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-21T14:35:18+00:00
- Post Title: compression signatures

```
"zlib 1.2.3 - no compression -> Mark Adler",[0x78,0x01]
"zlib 1.2.3 - default compression -> Mark Adler",[0x78,0x9C]
"zlib 1.2.3 - best comprssion -> Mark Adler",[0x78,0xDA]
"JCALG 5.xx -> Jeremy Collake",[0x78,0x43,0x6D,0x70] // "xCmp"
"JCALG 5.xx Simple -> Jeremy Collake",[0x78,0x53,0x6D,0x70] // "xSmp"
"LZO 2.02 -> Markus F.X.J. Oberhumer",[0x89,0x4C,0x5A,0x4F]  // 0x89 + "LZO"
```


not sure if they are all correct.
