## Post #1
- Username: analyzethis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 09, 2012 4:08 am
- Post datetime: 2012-08-11T09:53:14+00:00
- Post Title: How to open/edit/save this TGA file?

Tried Ulead Photoimpack, GIMP, Photoshop, PAINT.NET and non were able to open it. Only Irfanview can open it, but when saving the file size changes. Dont want that to happen. 

Can someone provide some insight?

File: [http://www62.zippyshare.com/v/25133105/file.html](http://www62.zippyshare.com/v/25133105/file.html)

Game is NineDragons Online.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-08-11T11:39:13+00:00
- Post Title: How to open/edit/save this TGA file?

It looks like a *.dds file with a *.tga extension. When the image is saved as DXT5 with no MIP maps in Photoshop the file size remains the same.
You can also open it in TextureFinder2.1 as DXT5; Width 256 and Shifted by 128.

DDS header reference

```
  DWORD           Size;
  DWORD           Flags;
  DWORD           Height;
  DWORD           Width;
  DWORD           PitchOrLinearSize;
  DWORD           Depth;
  DWORD           MipMapCount;
  DWORD           Reserved1[11];
  DWORD           pf_Size;
  DWORD           pf_Flags;
  DWORD           pf_FourCC;
  DWORD           pf_RGBBitCount;
  DWORD           pf_RBitMask;
  DWORD           pf_GBitMask;
  DWORD           pf_BBitMask;
  DWORD           pf_ABitMask;
  DWORD           Caps;
  DWORD           Caps2;
  DWORD           Caps3;
  DWORD           Caps4;
  DWORD           Reserved2;
```
## Post #3
- Username: analyzethis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 09, 2012 4:08 am
- Post datetime: 2012-08-11T14:14:23+00:00
- Post Title: How to open/edit/save this TGA file?

Aw man I feel stupid. I remember turning off the warning by Irfanview which asked me to rename the file extension.

Well thanks alot for the software, tried with Paint.NET and it can open/edit DDS files.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-18T03:47:03+00:00
- Post Title: How to open/edit/save this TGA file?

What, my paint.NET doesn't support DDS.
Did you grab a plugin?
