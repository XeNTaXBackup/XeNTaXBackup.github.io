## Post #1
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2016-01-17T21:38:11+00:00
- Post Title: Unpacking XBM files? (Witcher 2, 3)

I have a ton of .xbm textures, and I can't get them unpacked as .tga or .dds without QuickBMS and some scripts. 

According to these threads: 
[viewtopic.php?f=10&t=6634&start=30](http://forum.xentax.com/viewtopic.php?f=10&t=6634&start=30)
[viewtopic.php?f=10&t=6634&hilit=xbm](http://forum.xentax.com/viewtopic.php?f=10&t=6634&hilit=xbm)

> Reply from hhrhhr
>
> tools for xbm->tga and tga->xbm converting: witcher2_texture_converter.zip (thx chrrox for initial edition 

usage: put quickbms.exe with unpacked files.

xbm2dds.cmd path_to_xbm
it make backup of original .xbm and produce 2 files:
filename_DXT(1,5).bin - some binary info need for export
filename_DXT(1,5).tga - your texture

So, I'm looking for w2_xbm2dds.bms and w2_xbm2tga.bms, and the witcher2_texture_converter.zip -- none of which I can find any working links for.
## Post #2
- Username: srcs34k
- Rank: n00b
- Number of posts: 14
- Joined date: Wed May 23, 2012 11:45 pm
- Post datetime: 2018-04-17T04:12:19+00:00
- Post Title: Unpacking XBM files? (Witcher 2, 3)

taken from [http://www.playground.ru/files/dds_to_x ... ter-48741/](http://www.playground.ru/files/dds_to_xbm_converter-48741/)

Content of file

> cudart64_30_14.dll
>
> dds2xbm.cmd
>
> nvcompress.exe
>
> nvdecompress.exe
>
> nvtt.dll
>
> w2_dds2xbm.bms
>
> w2_dzip_unpack.bms
>
> w2_xbm2dds.bms
>
> xbm2dds.cmd
>
> xbm2dds_all.cmd
[witcher2_texture_converter.7z](https://xentaxbackup.github.io/file/14227_witcher2_texture_converter.7z)
