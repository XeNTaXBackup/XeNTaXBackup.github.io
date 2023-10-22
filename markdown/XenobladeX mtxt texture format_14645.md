## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2016-07-18T17:26:25+00:00
- Post Title: XenobladeX mtxt texture format

So recently i got my hands on XenobladeX (or Xenoblade Chronicles X if you want).
I almost figured out model format, but textures are not my cup of tea, they have different pixel formats and different extensions but in the core they are all same. I'm curious now about standard format used for models.

See? The color is here, but segments are placed randomly in raster.
This is supposed to be DXT1(BC1) format.
Right texture is dumped from CEMU.


Textures have MTXT header (I believe Castlevania used those too), the funny thing is, the header is backwards and at the end of file.

Thanks for any info. Samples below.
[dds+orgdds+mtxt.7z](https://xentaxbackup.github.io/file/11301_dds+orgdds+mtxt.7z)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2016-07-23T13:08:43+00:00
- Post Title: XenobladeX mtxt texture format

Im not sure, but can this be stored in Morton (aka Z) order?
ATM I don't know what texture format WiiU adopted, so it looks like blind shot.

EDIT: After some more research I found this little program called texconv2, it may be answer to my question, the file seem to be gtx format, now I just need to find header for gtx and it should work.
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2016-07-23T17:51:14+00:00
- Post Title: XenobladeX mtxt texture format

MTXT Header

```
header offset: EOF-122
names according to GTX Header Decription
struct MTXTHeader {
	uint swizzle;
	uint dimension;
	uint width;
	uint height;
	uint depth;
	uint nomips;
	uint type;
	uint size;
	uint aamode;
	uint tiling;
	uint unk;
	uint alignment;
	uint pitch;
}
```


Common formats: DXT1,DXT5,ATI2(normal maps)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-29T06:25:21+00:00
- Post Title: XenobladeX mtxt texture format

ok so if Xenoblade is a WiiU game then the texture is likely gx2 (or gtx?) format, your samples are probably gx2 image data with a custom header, or footer in this case. 
texconv2 can supposedly convert gtx to dds as posted here
[http://zenhax.com/viewtopic.php?t=534](http://zenhax.com/viewtopic.php?t=534)
there is a Noesis python script by Zaramot that calls texconv2 to convert gtx image data here
[viewtopic.php?p=103731#p103731](http://forum.xentax.com/viewtopic.php?p=103731#p103731)

looks like there is some pretty good python 3.4 source code here for unswizzling etc
[https://github.com/aboood40091/GTX-Extractor](https://github.com/aboood40091/GTX-Extractor)
someday i would like to be able to use this in a script to eliminate having to use any tool called by the script  

> Reply from PredatorCZ
>
> Code: Select allheader offset: EOF-122
you meant 112 instead of 122 right?
## Post #5
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-10-14T13:44:10+00:00
- Post Title: XenobladeX mtxt texture format

Thanks for post Ace, I have finished converter months ago, so its fine. 
Since Xenoblade 2 will use same engine I will test my tool and probably release it to public.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-05-14T06:20:24+00:00
- Post Title: XenobladeX mtxt texture format

i put together a Noesis python script for fun to open your mtxt sample  


 XenobladeChroniclesX_WiiU_mtxt.7z
(170.03 KiB) Downloaded 91 times


i used your findings along with info from previous links i posted.

to make this work
extract tex_XenobladeChroniclesX_WiiU_mtxt.py to Noesis\plugins\python folder
extract TexConv2.exe, TexConv2.bat, texUtils.dll and gfd.dll to Noesis\scenes folder
## Post #7
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2019-01-08T05:42:52+00:00
- Post Title: XenobladeX mtxt texture format

well done~~;
