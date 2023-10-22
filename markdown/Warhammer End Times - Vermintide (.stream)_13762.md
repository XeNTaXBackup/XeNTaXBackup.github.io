## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2016-01-03T02:05:34+00:00
- Post Title: Warhammer: End Times - Vermintide (.stream)

Just a container with Wwise RIFF/RIFX audio data but probably has data information in the end of file.

WAVE scanner by AlphaTwentyThree extracts only part of them(over 1GB from 1.15GB).

Part of extracted audio is IMA or ADPCM, which ww2ogg 0.22 can't decode because they don't have ogg data by 0x42. WWiseTool by Xaser can decode them, they work in XMPlay as minimum, but some decodes incorrect probably and he don't work with ww2ogg decodable WEMs.

Need correct .stream extractor and Wwise IMA|ADPCM decoder. 

.stream samples(filecut'ed) - [http://www92.zippyshare.com/v/PRrQePQ9/file.html](http://www92.zippyshare.com/v/PRrQePQ9/file.html)

WEM samples - [http://www30.zippyshare.com/v/yuB1cK1M/file.html](http://www30.zippyshare.com/v/yuB1cK1M/file.html)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-03T08:44:26+00:00
- Post Title: Warhammer: End Times - Vermintide (.stream)

Use package unpacker (bitsquid_unp) to split the streams into individual wwise banks and files. The information on how to split them is inside of the corresponding packages. If the package files are very large (more than 700 or 800 MB) you need to use bitsquid_unp_hd instead.

[viewtopic.php?p=106336#p106336](http://forum.xentax.com/viewtopic.php?p=106336#p106336)

But I believe WAVE scanner does its job well. Of you only need audio, and not the other data contained in streams.

ADPCM decoder - [viewtopic.php?p=110795#p110795](http://forum.xentax.com/viewtopic.php?p=110795#p110795)

Also from your samples I see some files are WWISE PCM. If you change codec code (fffe) to 1, they will play.
