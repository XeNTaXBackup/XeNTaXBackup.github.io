## Post #1
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2013-04-19T11:00:51+00:00
- Post Title: Nvidia "A New Dawn" tech demo .NPK

Last summer Nvidia released remake of the old Dawn demo - ["A New Dawn"](http://www.geforce.com/games-applications/pc-applications/a-new-dawn)
Resources in .NPK archives, so I wrote bms script to unpack them:

```
IDString "\xBE\xEF\xCA\xFE"
Get FILES long
For I = 0 < FILES
 Get FNAMELEN long
 GetDString FNAME FNAMELEN
 Get UNKNOWN longlong # UNIX/C date+time ?
 Get FOFFSET longlong # file offset
 Get FCSIZE longlong # file compressed size
 Get FUSIZE longlong # file uncompressed size
 FileXOR "\x62\x6F\x67\x6F\x6D\x6F\x6A\x6F" FOFFSET # "bogomojo"
 #Log FNAME FOFFSET FCSIZE
 CLog FNAME FOFFSET FCSIZE FUSIZE
 FileXOR ""
Next I

```

Unfortunately, I have an ATI video card and can't run the demo to tell if it runs with resources unpacked.

Models are still in NMB files (there are several topics on them on this forum), but format is different - all 3d data (verts, idx, normals, uv, etc) is divided to several files. These files are in models\geo_main.npk and there are also several NMB and NMA files in demo.npk, which, I believe, the main ones, that referred to the first.

My first experience in writing Noesis script (and second ever in reversing 3d model format )
It imports vertex coordinates, normals and indices, no textures or even uv coords yet.
If someone can make a complete importer that would be great 
[dawn_face2.png](https://xentaxbackup.github.io/file/6344_dawn_face2.png)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-05-04T01:56:12+00:00
- Post Title: Nvidia "A New Dawn" tech demo .NPK

> Reply from Axsis
>
> Last summer Nvidia released remake of the old Dawn demo - "A New Dawn"
Resources in .NPK archives, so I wrote bms script to unpack them:
Code: Select all# Nvidia NPK unpacking script v0.1 by Axsis
IDString "\xBE\xEF\xCA\xFE"
Get FILES long
For I = 0 < FILES
 Get FNAMELEN long
 GetDString FNAME FNAMELEN
 Get UNKNOWN longlong # UNIX/C date+time ?
 Get FOFFSET longlong # file offset
 Get FCSIZE longlong # file compressed size
 Get FUSIZE longlong # file uncompressed size
 FileXOR "\x62\x6F\x67\x6F\x6D\x6F\x6A\x6F" FOFFSET # "bogomojo"
 #Log FNAME FOFFSET FCSIZE
 CLog FNAME FOFFSET FCSIZE FUSIZE
 FileXOR ""
Next I

Unfortunately, I have an ATI video card and can't run the demo to tell if it runs with resources unpacked.

Models are still in NMB files (there are several topics on them on this forum), but format is different - all 3d data (verts, idx, normals, uv, etc) is divided to several files. These files are in models\geo_main.npk and there are also several NMB and NMA files in demo.npk, which, I believe, the main ones, that referred to the first.

My first experience in writing Noesis script (and second ever in reversing 3d model format )
It imports vertex coordinates, normals and indices, no textures or even uv coords yet.
If someone can make a complete importer that would be great

Nice work man
