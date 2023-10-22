## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-22T20:22:22+00:00
- Post Title: Overwatch

There are several types of textures i can convert with normal DDS.

```
0x48090008
0x4D010002
0x4E010062
```


for each file

```
DWORD dwUnknown; //??
SHORT m_Width;
SHORT m_Height;
DWORD dwDataSize;
```


Data begin always at offset 128

But last type 0x5F090008 I can not understand. Seems compressed. Can someone look it?

[https://www.sendspace.com/file/yx9dgk](https://www.sendspace.com/file/yx9dgk)
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-12-08T20:48:21+00:00
- Post Title: Overwatch

Cool, must check this asap 

What do you use for the dds header?

DXT1, DXT5 ... or is it depending on the hex code ?
[EDIT] Ok I found something, I did manage to convert the known types to dds format, but how come your file ( in the download section above) has .tex extension, while mine is xxx ?



T.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-21T07:16:16+00:00
- Post Title: Overwatch

first byte is DXGI format.

0x5F = DXGI_FORMAT_BC6H_UF16

But you probably already figured that out long time ago.
