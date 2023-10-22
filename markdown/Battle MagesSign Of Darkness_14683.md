## Post #1
- Username: ermaccer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 25, 2016 4:14 am
- Post datetime: 2016-07-25T13:42:29+00:00
- Post Title: Battle Mages/Sign Of Darkness

Battle Mages uses 2 formats;

-GSM
-SAM

(Units also have an .mrk file, it's just a renamed .tga)

They seem to be same thing, except the latter is skinned.
The animations seems to be packed in SAM too.


[Sample (GSM/SAM)](http://www.mediafire.com/download/e2d4hwti257q89n/samples.zip)

I have made a tool to edit these:
[https://ermaccer.github.io/posts/miracle3d-designer/](https://ermaccer.github.io/posts/miracle3d-designer/)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-25T15:06:22+00:00
- Post Title: Battle Mages/Sign Of Darkness

humantent1.gsm  



humantent1_gsm.png (25.23 KiB) Viewed 61 times



0x20 - vertex block length (divide by vertex stride to get number of vertices)
0x24 - vertex block start address
0x30 - face indices length (divide by 2 to get number of faces)
0x34 - face indices start address

edit
and here is h2o file for first submesh of berzerker.sam

```
Vb1
32 24
0xAA8 106
020000
0x0 255
```
