## Post #1
- Username: deant
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jul 15, 2013 6:11 pm
- Post datetime: 2013-08-25T15:54:49+00:00
- Post Title: Strange .STX graphics format.

Hello guys, 
this is my first post here.  I usualy ask for  help as a last resort, and i  seem to hited  a rock with this one. The format is used in the PS/XBoX versions of the game  Beatdown: Fists of fury. Here is a  link of some sample  files (around 1 mb) ->[http://www.mediafire.com/download/82gnr ... agq/TEX.7z](http://www.mediafire.com/download/82gnr6kpp65yagq/TEX.7z)
When i  open it  in  hex and compared it with BMP  and  JPG, there seem to  be some  similarities, but the files have  absolutely no header.  I`m not  a programmer and  i cannot  go much further. I  also  tryed a nice little  software -> Texture finder, both the new  and old version(with the templates). I  can find the textures  in it, but cannot get the colorspace. I think they are not compressed. 
Thanks in advance to whoever respond to this request.
I hope u all had a nice weekend.
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-09-01T23:42:48+00:00
- Post Title: Strange .STX graphics format.

Hi!
Use TextureFinder v1.3.2 with these settings:



RO_FACE.png (118.25 KiB) Viewed 79 times



This is the STX file format:

```
0x00: chunk identifier (0x18)
0x04: chunk size
0x08: chunk version?
  {
  0x0C: chunk identifier (0x01)
  0x10: chunk size (0x10)
  0x14: chunk version?
    0x18: width
    0x1C: height
    0x20: bpp
    0x24: ?
  }
  0x28: bitmap (width*height bytes)
  0x28+width*height: color palette (RGBA, 0x400 bytes)
}
```


For example BILL_02.STX:

```
18 00 00 00
1C 04 01 00
FF FF 03 18
  {
  01 00 00 00
  10 00 00 00
  FF FF 03 18
    00 02 00 00
    80 00 00 00
    08 00 00 00
    00 02 00 00
  }
  ... bitmap
  ... palette
}
```

Hope this helps 
Cheers!
## Post #3
- Username: deant
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jul 15, 2013 6:11 pm
- Post datetime: 2013-09-02T08:31:46+00:00
- Post Title: Strange .STX graphics format.

Awesome!!! Ty for the  respond. I learned alot with your format explaining!
