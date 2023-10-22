## Post #1
- Username: doppler
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 10, 2012 2:48 am
- Post datetime: 2021-03-12T19:22:42+00:00
- Post Title: EA (PS1)  .p3o .ptl

Hello,

We've been extracting files from the PS1 game WCW Mayhem, and have come across what we believe to be the mesh/skin/weight data, just wondering if anybody could highlight whether this is actually mesh data, and if it's possible in hex to show where the vert/faces begin.

P.S They are from an EA .BIG archive. 

Thanks.
[chair.rar](https://xentaxbackup.github.io/file/19709_chair.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-12T20:13:12+00:00
- Post Title: EA (PS1)  .p3o .ptl

ptl could be the texture file (some shifting required to get the chair  )
.



chair-ptl-p3o.png (151.55 KiB) Viewed 36 times



.p3o? Well, I have a deja vue having got some mesh from similar data ages ago but no time for fiddling again.
## Post #3
- Username: doppler
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 10, 2012 2:48 am
- Post datetime: 2021-03-12T21:01:53+00:00
- Post Title: EA (PS1)  .p3o .ptl

> Reply from shakotay2 ↑Sat Mar 13, 2021 4:13 am at Sat Mar 13, 2021 4:13 am
>
> 
ptl could be the texture file (some shifting required to get the chair  )
.
chair-ptl-p3o.png

.p3o? Well, I have a deja vue having got some mesh from similar data ages ago but no time for fiddling again.

Hi mate, appreciate the help. We solved the .ptl file. It's a Playstation Texture Library (PTL). It consists of a header with image sizes and offsets to the image (.tim) data.

```
struct PTL
{
      unsigned int fileCount;
      unsigned int crc;
      PTLEntry[fileCount];
};

struct PTLEntry
{
      string textureID;
      unsigned int textureWidth;
      unsigned int textureHeight;
      unsigned int textureOffset;
};


```


Still working on the mesh data  though.
## Post #4
- Username: doppler
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 10, 2012 2:48 am
- Post datetime: 2021-03-18T17:09:35+00:00
- Post Title: EA (PS1)  .p3o .ptl

Update to anyone who wants to help. Having a hard time finding tangible data for the mesh information. However, here are some of our findings from the header area of the p3o file.

```
2 Bytes: Unknown
2 Bytes: Unknown

2 Bytes: Vertex Count or Face Count (QUADS?)
4 Bytes: Offset or Header Length

4 Bytes: Offset to Faces?
4 Bytes: Offset to Faces?

4 Bytes: Offset to UVs?

2 Bytes: Offset to Textures start
2 Bytes: Offset to Textures start
2 Bytes: Offset to Textures start

2 Bytes: Textures count

2 Bytes: Vertex Count?
4 Bytes: Offset to ??
4 Bytes: Offset to Faces?

2 Bytes: Unknown count?
4 Bytes: Offset to ??

```
