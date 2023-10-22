## Post #1
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-02-23T06:21:03+00:00
- Post Title: WRC 6 .PTX Texture Files

Hi everybody, I've tried convert to .dds the textures from this game, but the only i get from this file is a .Rif file, I opened in Hex and find the words Riff and DTX1.

Here's a sample:


 OPTICS_DIFF.rar
(186.64 KiB) Downloaded 59 times



Best Regards.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-26T01:34:47+00:00
- Post Title: WRC 6 .PTX Texture Files

your sample is lz4f compressed, here is bms script to decompress it.  

```

comtype lz4f
get ZSIZE asize
goto 0x11
get SIZE long
math SIZE + 8
get NAME basename
get EXT extension
string NAME + _decomp.
string NAME + EXT
clog NAME 0 ZSIZE SIZE
```


i need more than one sample to compare for a script to open decompressed texture.
## Post #3
- Username: JesterSnap
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 18, 2018 11:00 pm
- Post datetime: 2018-04-18T16:02:49+00:00
- Post Title: WRC 6 .PTX Texture Files

Will you take a look at some TT Isle of Man PTX files from the same devs?
[PILOT_BOOTS_01_IOR.rar](https://xentaxbackup.github.io/file/14232_PILOT_BOOTS_01_IOR.rar)
## Post #4
- Username: JesterSnap
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 18, 2018 11:00 pm
- Post datetime: 2018-04-18T16:06:00+00:00
- Post Title: WRC 6 .PTX Texture Files

Another:
[TT_START_END_DIFF.rar](https://xentaxbackup.github.io/file/14233_TT_START_END_DIFF.rar)
## Post #5
- Username: JesterSnap
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 18, 2018 11:00 pm
- Post datetime: 2018-04-18T16:08:08+00:00
- Post Title: WRC 6 .PTX Texture Files

Last one.
[PILOT_HELMET_01_IOR.rar](https://xentaxbackup.github.io/file/14234_PILOT_HELMET_01_IOR.rar)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-19T02:02:37+00:00
- Post Title: WRC 6 .PTX Texture Files

here is Noesis python script to open your ptx samples and the decompressed one from first post  
*script updated Feb 27, 2019*


 tex_WorldRallyChampionship6_ptx.zip
(952 Bytes) Downloaded 114 times


supports dxt1, dxt5, rgba and bc5s, top level mip only
## Post #7
- Username: JesterSnap
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 18, 2018 11:00 pm
- Post datetime: 2018-04-19T07:39:43+00:00
- Post Title: WRC 6 .PTX Texture Files

Thanks, it works on these smaller files but the script seems to have issues with the bigger sized textures. The bikes for example (around 21MB) show this error:



If you have time to take a look: [https://www.sendspace.com/file/grc3fb](https://www.sendspace.com/file/grc3fb)
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-19T22:59:14+00:00
- Post Title: WRC 6 .PTX Texture Files

okay previous script updated to support BC5S   
[viewtopic.php?p=139861#p139861](http://forum.xentax.com/viewtopic.php?p=139861#p139861)
## Post #9
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2019-02-27T06:38:00+00:00
- Post Title: WRC 6 .PTX Texture Files

> Reply from Acewell ↑Fri Apr 20, 2018 6:59 am at Fri Apr 20, 2018 6:59 am
>
> 
okay previous script updated to support BC5S   
viewtopic.php?p=139861#p139861I can't view or export my PTX samples using your plugin... I get this error:



 PTX.7z
Samples (215.74 KiB) Downloaded 22 times
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-27T09:56:19+00:00
- Post Title: WRC 6 .PTX Texture Files

okay script updated here to support your samples.   
[https://forum.xentax.com/posting.php?mo ... 5#pr139861](https://forum.xentax.com/posting.php?mode=reply&f=18&t=15915#pr139861)
