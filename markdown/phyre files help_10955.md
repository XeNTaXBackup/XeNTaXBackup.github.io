## Post #1
- Username: Bitonius
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 04, 2013 4:53 am
- Post datetime: 2013-11-12T05:48:37+00:00
- Post Title: phyre files help

I've been looking around quite some time now about this format but cant find anything really specific.
Can someone please point me into the right direction? like code sample or similar on how to read these files.
//dont mind if its something really general.
Thnks.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-12T08:46:17+00:00
- Post Title: phyre files help

did you read the results of this?
[search.php](http://forum.xentax.com/search.php)
(type in phyre)
## Post #3
- Username: Bitonius
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 04, 2013 4:53 am
- Post datetime: 2013-11-12T13:45:08+00:00
- Post Title: phyre files help

I did the [search](http://forum.xentax.com/search.php?keywords=phyre&terms=all&author=&sc=1&sf=all&sk=t&sd=d&sr=topics&st=0&ch=-1&t=0&submit=Search) but while i get some results its nothing specific,  am i doing something wrong?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-12T15:16:14+00:00
- Post Title: phyre files help

> Reply from Bitonius
>
> I did the search but while i get some results its nothing specific,  am i doing something wrong?Nope, just wanted to be sure you tried.  

You might upload a small phyre (model) sample if you have one.
Then I would have a look at it.

cheers
## Post #5
- Username: Bitonius
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 04, 2013 4:53 am
- Post datetime: 2013-11-12T20:28:16+00:00
- Post Title: phyre files help

I did [this](http://forum.xentax.com/viewtopic.php?f=10&t=10941) cuz 
> This game uses the common .phyre format.
Common... Anyway there it is will it do?
edit:Added some more sampl as each one just seems to be a single part.
[sampl.7z](https://xentaxbackup.github.io/file/6769_sampl.7z)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-13T06:11:00+00:00
- Post Title: phyre files help

You can get the pics using TextureFinder:
[](http://www.pic-upload.de/view-21318966/face_base_h.jpg.html)

The models, well:
edit: vertices to be read as big endian

without face indices applied it could be a head, or could not:
[](http://www.pic-upload.de/view-21319512/head_a.jpg.html)
With face indices applied there's some edgy ball, not a head.

Maybe a simpler sample - like a box or a book would help.
(Ok, see, new samples available.  )
## Post #7
- Username: Bitonius
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 04, 2013 4:53 am
- Post datetime: 2013-11-13T06:28:07+00:00
- Post Title: phyre files help

i dont know much about on how to read the files but on some i loeaded the part (chrmd_f_head_a_001_lod2.dae.GCM.pepd) were vertices are and just before the first verts are some lines 
```
00 00 00 0C 00 00 00 FE 00 00 00 01 00 00 00 00 00 00 0B E8 00 00 00 00 
00 00 00 0C 00 00 00 FE 00 00 00 01 00 00 00 00 00 00 0B E8 00 00 00 00
00 00 00 10 00 00 00 FE 00 00 00 01 00 00 00 00 00 00 0F E0 00 00 00 00
00 00 00 04 00 00 00 FE 00 00 00 01 00 00 00 00 00 00 03 F8 00 00 00 00
BD 84 07 3D 3F BC B7 92 BC C7 76 E4 BD 5D D5 06 3F C0 12 8E BD 97 8A 77 <-- vert start
BD 10 C3 45 3F B9 CA 27 BD 29 88 F6 BD 1F 34 3D 3F B5 3E 8A BC EF FD 29
BC C6 8F 85 3F B7 33 F0 BA 06 91 D2 BC CF 36 2C 3F B3 41 10 BB E7 97 8F
```

the first 00 00 00 0C maybe some kind of id? then next 00 00 00 FE seems to be the count idk the next 8 bytes but the next seems to be the total size of each line...
div total size by count gives how much bytes to read and it goes like first pure verts then normals etc. but idk im just guessing by looks.
Anyway ill check that TextureFinder and see how it goes
Thnks.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-13T07:10:39+00:00
- Post Title: phyre files help

ok, big endian, is a console game.
shape's looking more than a head now.
0x7fb3:
v  -0.064467 1.474352 -0.024349 
v  -0.054158 1.500566 -0.073995 
v  -0.035342 1.451482 -0.041390 
v  -0.038868 1.415971 -0.029296 
v  -0.024238 1.431273 -0.000513 
...

Where do you see normals? (vector length==1)
edit: are in a separate block:
vn  -0.639434 -0.611696 -0.465781 
vn  -0.630582 -0.468357 -0.618876 
vn  -0.775633 -0.418069 -0.472876 
vn  -0.984208 0.176174 0.017245 
...

The face indices aren't that nice here - some fiddeling around required again.
## Post #9
- Username: Bitonius
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 04, 2013 4:53 am
- Post datetime: 2013-11-13T15:11:12+00:00
- Post Title: phyre files help

I checked the file again and it seems the line [started](http://imageshack.com/a/img41/1917/e9nx.jpg) at 0x7EC3
the firt count being 230.
About the faces of this particular file, they are at 0x138AA but not all of them seem to be used for it... in this case they are 276,there are more faces after but seem to be used elsewere.
now if only could find tex coords... after normals there a bunch of data idk, d you know if any of them could be tex coords?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-13T16:56:38+00:00
- Post Title: phyre files help

after 230 vertices and 230 normals there are another 230 normals (bi?).

There's another data field from 0xB203 to D5BB. 
edit: that's the hair mesh:
here the H2O file for hex2obj:

```
VB0
0x0
0xB203 254
1200
```

Maybe to search for tex at 0xEC77. But I would guess it's from 0x14FCA.  But too many negative values here.
Who knows? (That's the annoying part always.)

This is what I got so far:
[](http://www.pic-upload.de/view-21323632/head_a_.jpg.html) [](http://www.pic-upload.de/view-21323905/Head_a_hair.jpg.html)
## Post #11
- Username: Bitonius
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 04, 2013 4:53 am
- Post datetime: 2013-11-17T06:19:17+00:00
- Post Title: phyre files help

I checked chroxx's [post](http://forum.xentax.com/viewtopic.php?f=10&t=10813), and this and that seem to be the same phyre format,hopefully he figured out how to extract from them.
I checked the file but i can make little sense of it...
For texture files, header seems to be always 0x58 bytes in length, followed by the datablock which's size is specified at header offset 0x8.
This datablock seems to have a header of like 6 or 7 DWORDs(unsure), right after is the first offset to read and then a variable length of data depending of what the offset gets, and that is basically it.
The block header has the size of the string table, and the offsets are relative to the start position of it(the offset always start at 0 hence why im unsure if the length of the header is 6 or 7).
Now here's the thing, i dont know what the other data might mean but plain reading the offsets and the string table i get(part of it)...

```
        unk1    : 0
        offset  : 0
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_size
        unk1    : 0
        offset  : 4
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_instanceListCount
        unk1    : 0
        offset  : 16
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_packedNamespaceSize
        unk1    : 0
        offset  : 8
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_arrayFixupSize
        unk1    : 0
        offset  : 20
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_arrayFixupCount
        unk1    : 0
        offset  : 24
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_pointerFixupSize
        unk1    : 0
        offset  : 28
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_pointerFixupCount
        unk1    : 0
        offset  : 32
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_pointerArrayFixupSize
        unk1    : 0
        offset  : 36
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_pointerArrayFixupCount
        unk1    : 0
        offset  : 40
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_pointersInArraysCount
        unk1    : 0
        offset  : 44
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_userFixupCount
        unk1    : 0
        offset  : 48
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_userFixupDataSize
        unk1    : 0
        offset  : 52
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_totalDataSize
        unk1    : 0
        offset  : 56
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_headerClassInstanceCount
        unk1    : 0
        offset  : 60
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_headerClassChildCount
        unk1    : 0
        offset  : 64
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_platformID
        unk1    : 0
        offset  : 12
        datasize: 4
        unk4    : 8
        unk5    : 0
Process m_physicsEngineID
        unk1    : 0
        offset  : 68
        datasize: 4
        unk4    : 8
        unk5    : 0
```

which makes perfect sence of what the file header is composed of, but then some other part...

```
        unk1    : 3
        offset  : 0
        datasize: 1
        unk4    : 16
        unk5    : 0
Process mipmap
        unk1    : 3
        offset  : 1
        datasize: 1
        unk4    : 16
        unk5    : 0
Process dimension
        unk1    : 3
        offset  : 2
        datasize: 1
        unk4    : 16
        unk5    : 0
Process cubemap
        unk1    : 3
        offset  : 3
        datasize: 1
        unk4    : 16
        unk5    : 0
Process remap
        unk1    : 0
        offset  : 4
        datasize: 4
        unk4    : 16
        unk5    : 0
Process width
        unk1    : 5
        offset  : 8
        datasize: 2
        unk4    : 16
        unk5    : 0
Process height
        unk1    : 5
        offset  : 10
        datasize: 2
        unk4    : 16
        unk5    : 0
Process depth
        unk1    : 5
        offset  : 12
        datasize: 2
        unk4    : 16
        unk5    : 0
```

As you can see the offset i relative, and thats why it hard(for me at least) to figure how to properly read the file.
Manually locating this position was rather easy as the file isnt that big(offset 0xEF5),'insolating' this part of the data:

Those offsets make sence now,and it's like that throught all the file,If only i could figure how to properly read these blocks.... any Ideas?
note: extracted from maid texture file.
## Post #12
- Username: dilydaly123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 25, 2017 5:52 am
- Post datetime: 2017-06-25T18:17:57+00:00
- Post Title: phyre files help

> Reply from shakotay2
>
> You can get the pics using TextureFinder:


)

I am trying to get the textures and audio files out of this game now (the ps3 version) and when I run texture finder, I think that my using win7 is causing me to miss options in the program.

[http://i.imgur.com/QECBkWR.png](http://i.imgur.com/QECBkWR.png)
