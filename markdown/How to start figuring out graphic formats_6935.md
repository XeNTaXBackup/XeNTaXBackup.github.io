## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T02:11:02+00:00
- Post Title: How to start figuring out graphic formats

I've gotten some idea how to deal with 3D formats and can build on my knowledge by looking at more formats, but at the moment I have no idea where to begin with when it comes to graphic formats.

I tried looking at the specs for the BMP format but there's a lot of information and not sure what is important or not.

Any starting points?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-08T02:39:04+00:00
- Post Title: How to start figuring out graphic formats

[http://en.wikipedia.org/wiki/BMP_file_format](http://en.wikipedia.org/wiki/BMP_file_format)

Just look at existing projects that can load them that are open source.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-08T06:06:31+00:00
- Post Title: How to start figuring out graphic formats

I would also suggest just picking some bit of BMP documentation and use it to build a BMP file, by hand, in a hex editor - playing around in this way should let you learn quite a bit, pretty quickly.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T12:45:43+00:00
- Post Title: How to start figuring out graphic formats

lol there's a lot of information, both from reading the bmp and about DXTn.

Maybe someone can make a simple tutorial to build a bmp file so people have an idea of a working process rather than trying to figure it out from finished products or pure specs.
## Post #5
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-15T20:53:19+00:00
- Post Title: How to start figuring out graphic formats

I would suggest using DDS instead of BMP,
DDS has advantages if you want to start easy:

Fixed header length: 128 Bytes, no matter what, no chunks or unnecessary stuff (except some flags and optional stuff)
Support for many data formats (DXTn, RGB, RGBA, RGBA with 'special' bit masks,YUV , Luminance, Mipmaps...)
An easy to understand documentation (except they write 0x8000 instead of 0x (8000) at the flag parts ) is available:
[http://msdn.microsoft.com/en-us/library ... S.85).aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/bb943990%28v=VS.85%29.aspx)

For viewing said files I would suggest a fast image viewer like Irfan View.

Maybe this overview will help:

(The following class is written for BinData, a 'gem' for the Ruby scripting language)

```
class DDS_fileheader < BinData::Record 
  endian :little

  string :dwMagic, :read_length => 4 #'DDS '
  
  #DDS_Header start
  uint32 :hSize, :value => 124                                #Fixed Value
  array  :hFlags, :type => :boolean, :initial_length => 32
  uint32 :hHeight
  uint32 :hWidth
  uint32 :hPitchOrLinearSize
  uint32 :hDepth
  uint32 :hMipMapCount
  array  :hReserved1, :type => :uint32,:initial_length => 11
  
  #DDS_PIXELFORMAT start
  uint32 :pSize, :value => 32                                 #Fixed Value
  array  :pFlags, :type => :boolean, :initial_length => 32
  uint32 :pFourCC
  uint32 :pRGBBitCount
  uint32 :pRBitMask
  uint32 :pGBitMask
  uint32 :pBBitMask
  uint32 :pABitMask
  #DDS_PIXELFORMAT end
  
  array  :hCaps,  :type => :boolean, :initial_length => 32
  array  :hCaps2, :type => :boolean, :initial_length => 32
  array  :hCaps3, :type => :boolean, :initial_length => 32
  array  :hCaps4, :type => :boolean, :initial_length => 32
  uint32 :hReserved2
  #DDS_Header end
end
```


I didn't choose BMP for learning because it has too much optional stuff and looks like a deprecated (yet widely used) format
that is pretty useless to me, but if you want to make a (modding) tool more accessible it's a good idea to learn it too.

Alternatives if you have a mathematical background:
Look at the compression that PNG or JPEG provide

If you want I can write an easy description of each field that enables you to make a 8BPP RGBA (or RGB), no mipmap, image. (But not more )

Edit: @Dinoguy1000: It's not widespread in the consumer world, if you look at games it's a different story. (I get your point though)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-11-15T20:58:16+00:00
- Post Title: How to start figuring out graphic formats

You touched on the major disadvantage of learning from DDS compared with BMP: DDS doesn't have anywhere near as widespread support as BMP does (but then, if you're the type of person wanting to get a good, technical feel for what makes graphical file formats tick, you'd probably not have any problem with installing software to be able to view a particular format, and DDS certainly isn't as obscure as some potential choices for a "learning" format).
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-27T04:32:52+00:00
- Post Title: How to start figuring out graphic formats

Hmm, pretty much every piece of information in the format is fairly technical. I think the only things that are obvious is the width and height lol.

I would imagine anyone that doesn't have a clue about what an image is beyond being an array of pixels would be lost regardless of how much documentation is provided.

The wiki page for BMP is somewhat detailed I guess.
Then again the page assumes prior knowledge of most of the technical terms as well.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-29T00:10:41+00:00
- Post Title: How to start figuring out graphic formats

Bmp format is just

Bitmap file header
Bitmap info header
32-bit bgra palette if 8-bit or less
Image data

A lot of the info parameters can be set to zero. Also no vendor that I know of has ever supported the version 5 info header so that can be ignored. No vendor has supported png or jpg compression in bmp either so that can be ignored too.
