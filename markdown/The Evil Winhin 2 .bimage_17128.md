## Post #1
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-10-13T02:02:31+00:00
- Post Title: The Evil Winhin 2 .bimage

The Evil Winhin 2 fonts files .bimage how to open


[https://drive.google.com/file/d/0B2lK7_ ... sp=sharing](https://drive.google.com/file/d/0B2lK7_PJMWOSb2pWcUZGWEFaQ0U/view?usp=sharing)
## Post #2
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2017-10-14T09:34:00+00:00
- Post Title: The Evil Winhin 2 .bimage

```
//--- 010 Editor v6.0.3 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------

LittleEndian();

local uint i;

uint64 id;
uint zero;
uint mainwidth;
uint mainheigth;
uint zero;
uint mipmaps;
uint par0;
uint par1;
uint par2;
ushort zero;

for(i=0;i<mipmaps;i++) {
struct mipmap {

uint mipmapnum;
uint zero;
uint width;
uint heigth;
uint mipmapsize;

ubyte data[mipmapsize];

} record;
}
```


Looks like all font textures uses DXT5 compression. Header is 62 bytes, rest is RAW data.

Usage:

-run the tempalte on BIMAGE file, you will need 010 HEX Editor.
-check width / height and create in GIMP or Photoshop DDS file with the same width / height and save it with DXT5 compression.
-open created DDS and copy first 128 bytes and copy it over 62 bytes in BIMAGE and save as DDS.

result:
## Post #3
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-10-16T20:39:42+00:00
- Post Title: The Evil Winhin 2 .bimage

> Reply from GRiNDERKILLER
>
> Code: Select all//--------------------------------------
//--- 010 Editor v6.0.3 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------

LittleEndian();

local uint i;

uint64 id;
uint zero;
uint mainwidth;
uint mainheigth;
uint zero;
uint mipmaps;
uint par0;
uint par1;
uint par2;
ushort zero;

for(i=0;i<mipmaps;i++) {
struct mipmap {

uint mipmapnum;
uint zero;
uint width;
uint heigth;
uint mipmapsize;

ubyte data[mipmapsize];

} record;
}

Looks like all font textures uses DXT5 compression. Header is 62 bytes, rest is RAW data.

Usage:

-run the tempalte on BIMAGE file, you will need 010 HEX Editor.
-check width / height and create in GIMP or Photoshop DDS file with the same width / height and save it with DXT5 compression.
-open created DDS and copy first 128 bytes and copy it over 62 bytes in BIMAGE and save as DDS.

result:

Thanks but how to repack
## Post #4
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2017-10-19T21:02:07+00:00
- Post Title: The Evil Winhin 2 .bimage

Same as step 3 but reversed.
Open edited DDS in HEX editor and replace first 128 bytes with 62 bytes from original BIMAGE. That's all. Easy right?...  
BTW do you have a repacker of PKR files? I mean real one where you can repack bigger files than original.
## Post #5
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-10-27T01:08:29+00:00
- Post Title: The Evil Winhin 2 .bimage

> Reply from GRiNDERKILLER
>
> Same as step 3 but reversed.
Open edited DDS in HEX editor and replace first 128 bytes with 62 bytes from original BIMAGE. That's all. Easy right?...  
BTW do you have a repacker of PKR files? I mean real one where you can repack bigger files than original.


PKR repack not work


[https://zenhax.com/viewtopic.php?f=9&t=5088](https://zenhax.com/viewtopic.php?f=9&t=5088)
