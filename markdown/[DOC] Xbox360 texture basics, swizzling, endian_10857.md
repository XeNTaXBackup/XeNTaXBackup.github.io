## Post #1
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-10T08:57:41+00:00
- Post Title: [DOC] Xbox360 texture basics, swizzling, endian

I have written a large article about Xbox360 graphics storage methodology:
[http://dageron.com/?page_id=5238&lang=en](http://dageron.com/?page_id=5238&lang=en)

It has all info about swizzling (tiling), endiannes and other related things (D3DBaseTexture specification also).
Everything this I used in my [GTA V Console Texture Editor](http://dageron.com/?page_id=4973&lang=en).
Necessary parts of source code are provided.

Hope that will be helpful for developers interested in Xbox360 graphics research.
Improvements are welcome   .
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-10-10T12:53:19+00:00
- Post Title: [DOC] Xbox360 texture basics, swizzling, endian

Hi Dageron
Nice article.
I have implemented Xbox360 Untiling and it works but only on base mipmap. Other mipmaps are kinda strange.
I think they're 256 byte aligned.
Do you have any info on untiling mipmaps? especially the mipTail that is the most strange.
Thanks
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-19T05:41:09+00:00
- Post Title: [DOC] Xbox360 texture basics, swizzling, endian

Nice Documentation +1
## Post #4
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-10-19T18:05:03+00:00
- Post Title: [DOC] Xbox360 texture basics, swizzling, endian

Really nice docs and website, bookmarked!

Could you please do some documentation/examples on image swizzling in normal textures (DXT5) for pc?
Usually the image looks fine but channels are inverted + something else, making them not suitable for 3d apps.

> Reply from MrAdults
>
> Just swap the red and alpha channels of the image, scale and bias into vector space (0-255 to -1.0-1.0), then determine blue's contribution by subtracting the length of r+g from 1. (since you know the end result is a unit vector) Sometimes games will also store r+g biased, such that when you set blue to 1.0 and normalize you will end up with the correct normal. (this is common because the normal is in tangent space which means it will always revolve around z and can easily be clamped)

I Know how to decode DXT5, but I'd like to know the process and theory behind why they do that to import-export textures for diifferent game engines.
## Post #5
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-21T16:20:37+00:00
- Post Title: [DOC] Xbox360 texture basics, swizzling, endian

Hadn't worked with normal textures yet.
But figured out everything with mipmaps  .

Here it is my code for mipmap alignment, if someone is interested in:

```
var
  i: integer;
  dwSize: DWORD;
  h, w: DWORD;
begin
 for i := 1 to dwMipMaps-1 do
 begin
    if  GetGPUTEXTUREFORMAT(dwTextureType)='GPUTEXTUREFORMAT_DXT1' then
    begin
      W:=dwWidth;
      H:=dwHeight;
      if (W mod 128 <> 0) then W := W + (128 - W mod 128);
      if (H mod 128 <> 0) then H := H + (128 - H mod 128);
      dwSize:=W*H div 2;
    end;
  if GetGPUTEXTUREFORMAT(dwTextureType)='GPUTEXTUREFORMAT_DXT2_3' then
    begin
      W:=dwWidth;
      H:=dwHeight;
      if (W mod 128 <> 0) then W := W + (128 - W mod 128);
      if (H mod 128 <> 0) then H := H + (128 - H mod 128);
      dwSize:=W*H;
    end;
  if GetGPUTEXTUREFORMAT(dwTextureType)='GPUTEXTUREFORMAT_DXT4_5' then
    begin
      W:=dwWidth;
      H:=dwHeight;
      if (W mod 128 <> 0) then W := W + (128 - W mod 128);
      if (H mod 128 <> 0) then H := H + (128 - H mod 128);
      dwSize:=W*H;
    end;
  if  GetGPUTEXTUREFORMAT(dwTextureType)='GPUTEXTUREFORMAT_8_8_8_8' then
    begin
      W:=dwWidth;
      H:=dwHeight;
      if (W mod 128 <> 0) then W := W + (128 - W mod 128);
      if (H mod 128 <> 0) then H := H + (128 - H mod 128);
      dwSize:=W*H*4;
    end;
  dwWidth:=dwWidth div 2;
  dwHeight:=dwHeight div 2;
  dwOffset:=dwOffset+dwSize;
 end;
 result:=dwOffset;
end;
```

Calculates offset of the mimpap level you need.
Next you should work with it in the same way, as with usual texture (don't forget that Width and Height had been changed).
## Post #6
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-06-24T21:22:05+00:00
- Post Title: [DOC] Xbox360 texture basics, swizzling, endian

> Reply from Dageron ↑Thu Oct 10, 2013 4:57 pm at Thu Oct 10, 2013 4:57 pm
>
> 
I have written a large article about Xbox360 graphics storage methodology:
http://dageron.com/?page_id=5238&lang=en

It has all info about swizzling (tiling), endiannes and other related things (D3DBaseTexture specification also).
Everything this I used in my GTA V Console Texture Editor.
Necessary parts of source code are provided.

Hope that will be helpful for developers interested in Xbox360 graphics research.
Improvements are welcome   .

This article has been lost on the internet. There are many snapshots from dageron.com on the wayback machine but not this article. Has anyone saved it?
## Post #7
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-07-09T23:54:16+00:00
- Post Title: [DOC] Xbox360 texture basics, swizzling, endian

yeah, if anyone got these docs, i would love to have em too.
