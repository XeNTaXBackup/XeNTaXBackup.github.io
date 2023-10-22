## Post #1
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-12T15:38:14+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

Is it possible to convert binary files to ordinary texture files like .dds format? I found some graphic tools (texture finder, tiledGGD, etc.), but I couldn't find manuals...

attachments is sample.
[IMAG_4.zip](https://xentaxbackup.github.io/file/20107_IMAG_4.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-12T15:45:52+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

Irfanview, 
left side: File open, Open as RAW file - (on the right I used a DXT1 dds header).
.



IMAG_4.png (224.8 KiB) Viewed 148 times
## Post #3
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-13T12:17:27+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

umm...I tried few method too. But no matter how I look at it, it doesn’t seem to be texture:( So, I got another question. Is it possible to mesh contain texture? If possible, can I divide mesh and texture?
[MESH.zip](https://xentaxbackup.github.io/file/20112_MESH.zip)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-13T17:49:31+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

You cut off the bytes before 0x4A70.
.



TexFromUnslz.png (153.26 KiB) Viewed 124 times



(I remember having had similar pictures years ago - some shifting required, or other pixel format, don't remember. Too lazy to search.)
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-05-13T19:21:43+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

What game are these samples from? They seem to be from a Tri-Ace game, but I haven't seen them before.
## Post #6
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-13T23:58:52+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

> Reply from akderebur ↑Fri May 14, 2021 3:21 am at Fri May 14, 2021 3:21 am
>
> 
What game are these samples from? They seem to be from a Tri-Ace game, but I haven't seen them before.

Yes, You're right. This game is Danball Senki Chou Custom from Tri-Ace
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-05-14T08:31:11+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

I see. Then it is likely that the textures use one of 3DS formats. Maybe ETC1 or ETC1A4. There might also be swizzling.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-14T11:20:09+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

Thanks! Things become more clear now, but not finished:
.



PVRtool-unslz.png (36.85 KiB) Viewed 92 times


Gave the afore said TexFromUnslz  a header (brute force, only thing I know is size, 0x40, 0x40 and "PVR!", 50565221):

```
34000000 40000000 40000000 00000000058A000000000004200000000000FF0000FF0000FF000000000000FF 50565221 01000000
```
## Post #9
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-15T05:07:15+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

Right is texture from other game Danball senki baku boost, but mesh is same.
Left is mesh's uv map before attached before. 

link is Danball senki baku boost's mesh.
[https://www.mediafire.com/file/1gnyhy54 ... d.zip/file](https://www.mediafire.com/file/1gnyhy544ide6o3/lbx004_00_head.zip/file)

These are look so similar, is there some hint?
[UV.PNG](https://xentaxbackup.github.io/file/20133_UV.PNG)
## Post #10
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-16T06:25:02+00:00
- Post Title: Danball Senki Chou Custom - Unknown binary texture file

> Reply from forarkorder ↑Sat May 15, 2021 1:07 pm at Sat May 15, 2021 1:07 pm
>
> 
Right is texture from other game Danball senki baku boost, but mesh is same.
Left is mesh's uv map before attached before. 

link is Danball senki baku boost's mesh.
https://www.mediafire.com/file/1gnyhy54 ... d.zip/file

These are look so similar, is there some hint?

oops, that's not mesh's texture.



lbx004_10_head.png (13.43 KiB) Viewed 57 times


I think this texture is right.

[https://www.mediafire.com/file/1gnyhy54 ... d.zip/file](https://www.mediafire.com/file/1gnyhy544ide6o3/lbx004_00_head.zip/file)
