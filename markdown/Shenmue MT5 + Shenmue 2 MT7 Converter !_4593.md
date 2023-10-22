## Post #1
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2010-06-12T15:25:11+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

2019: Final Edit : Shenmue Mt5/Mt7 converter now Available
wudecon
[https://www.shenmuedojo.com/forum/index ... 1-sm2.885/](https://www.shenmuedojo.com/forum/index.php?threads/release-wudecon-file-model-converter-for-sm1-sm2.885/)

-----------------------------------------------------------------------------------------------------------

2018 Update: Shenmue 1+2 'HD' PC (Xbox + Playstation) is Finally on Steam

Frustratingly they still use the original MT5 and MT7 model data, so once again I am requesting help to get a complete converter.

SHENMUE 1 MT5 CONVERSION SOUCRES (For anyone with Model Extraction Knowlege)

Yazgoo's (only works with individual MT5s)
[https://github.com/yazgoo/mt5_extraction_tools](https://github.com/yazgoo/mt5_extraction_tools)

Hellwig's is the most accurate converter
[https://github.com/hellwig/shencon](https://github.com/hellwig/shencon)

There is a whole bunch of Shenmue 1 MT5 file format information here:
[http://abdessel.iiens.net/dreamcast/mt5/](http://abdessel.iiens.net/dreamcast/mt5/)

There is Information on Shenmue 2's MT7 with a working maxscript that only appears to work on a few objects but thats got to be a start.
[viewtopic.php?f=16&t=11482](http://forum.xentax.com/viewtopic.php?f=16&t=11482)
another topic here
[viewtopic.php?f=16&t=2784&hilit=Shenmue](http://forum.xentax.com/viewtopic.php?f=16&t=2784&hilit=Shenmue)
more info here
[http://www.shenmuedojo.net/forum/viewtopic.php?t=47035](http://www.shenmuedojo.net/forum/viewtopic.php?t=47035)

Finally NinjaRipper Will capture models but all objects are placed at 0,0,0 axis , Hellwig's extractor will place 'most' objects correctly (some are rotated and animated objects are missing or break conversion)

UPDATE:
Someones figured out a Unity Importer based on Heliwigs sources
[https://www.shenmuedojo.com/forum/index ... unity.499/](https://www.shenmuedojo.com/forum/index.php?threads/shenmunity-shenmue-in-unity.499/)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-13T08:39:27+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

I have moved this to the right forum.
## Post #3
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2011-01-28T00:09:31+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2011-08-16T14:30:27+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

Its been over a year since my first post and Im still hoping that someone on xentax has the knowlege (and interest) to finish this extractor
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-16T14:58:01+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

> This format should be cake compared to todays file types

lol, it's already pretty foreign to me compared to the formats I've been looking at.
## Post #6
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2011-08-16T17:58:23+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

> Reply from finale00
>
>  This format should be cake compared to todays file types

lol, it's already pretty foreign to me compared to the formats I've been looking at.

Well its a Dreamcast file type, but the MT5 converter partially works and the sources are available, so It should be cake in comparison to the fact that most of the information and accumulated file documentation is freely available.

Basically the converter only seems to correctly rip single mesh objects, it cant rip multi part objects like town areas and people so (to me) it seems the problem isnt the mesh data itself but the order its complied in
## Post #7
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2012-04-22T16:54:45+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

I'm sorry for doing this necroposting, but I am interested on modding some MT7 (Shenmue 2) model files, because of the code that's posted on this topic (Which doesn't work on Vista/7), plus the tiny details detailed on this other topic: [Linky](http://forum.xentax.com/viewtopic.php?f=16&t=2784&hilit=Shenmue)

I'll explain my reasons: Right now I'm in the middle of assisting with the translation of Shenmue 2 to Spanish, and I've translated the map textures with the ShenmueSubs tools (Which only allow changing textures), but the problem is that some of the complete store names are in English format, per example, Lee's Barber, and I need to swap the order, to, following the example, Barbería de Lee, because Barber is shared with more Barber shops.

For doing that I'd need to move the triangles that represent the names, and possibly the UVWs. If someone's interested, I can help with additional details.
## Post #8
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2012-08-27T21:36:26+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

Bumping again?
## Post #9
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2013-11-30T10:47:29+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

Bumping again. I'm still in need of editing some of the meshes and UVW coordinates for the models.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-30T12:26:58+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

> Reply from McCuñao
>
> I'm sorry for doing this necroposting, but I am interested on modding some MT7 (Shenmue 2) model files, because of the code that's posted on this topic (Which doesn't work on Vista/7), [...]I don't see any code here.
## Post #11
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2013-12-07T18:26:50+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

It got lost because of the mass removal of content. Is there a way to recover the links?

EDIT: Oh, here's what I could retrieve.
[http://abdessel.iiens.net/dreamcast/mt5/](http://abdessel.iiens.net/dreamcast/mt5/)
[https://github.com/yazgoo/mt5_extraction_tools](https://github.com/yazgoo/mt5_extraction_tools)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-07T20:15:36+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

Thank you, retriever of the lost code/links.  

MT5 is an interesting format:
[https://raw.github.com/yazgoo/mt5_extra ... ucture.png](https://raw.github.com/yazgoo/mt5_extraction_tools/master/doc/mt5_structure.png)

Old converter being 50% done but the side linking to the new code 
[http://abdessel.iiens.net/dreamcast/mt5/hg.php](http://abdessel.iiens.net/dreamcast/mt5/hg.php)
is unavailable atm so we don't know how far it's grown.

For MT7 I did not find a format description. It might be very different to MT5.

Imho there's little chance for your request - I didn't find valuable infos in the net.

Anyway you might upload a small MT7 model sample so that we could get a clue what we are talking about.
## Post #13
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2013-12-07T22:29:04+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

Guess I'll have to prep a pack and upload it elsewhere...

Just to clarify, there's two OR three formats. That'll be MT5 (Shenmue I), MT7 (Shenmue II Dreamcast) and MT7 (Shenmue II XBOX).

There's a chap who has made a tool that can extract and replace .PVR and .DDS textures from MT5 and MT7 models, so that could help locate some of the missing information.
[http://sourceforge.net/projects/shenmue ... %20Editor/](http://sourceforge.net/projects/shenmuesubs/files/Models%20Textures%20Editor/)
[http://sourceforge.net/p/shenmuesubs/co ... %20Editor/](http://sourceforge.net/p/shenmuesubs/code/HEAD/tree/Package/Models%20Textures%20Editor/)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-08T12:13:36+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

Thx for the samples. I just fetched some vertices from two of them:
[](http://www.pic-upload.de/view-21564989/BIKS503G.png.html)

There's a void mt5::parseFaces() function in the gitihub project but I didn't get a clue on getting the faces.

edit: there are face indices but even used as tri strips it doesn't look nice:
[](http://www.pic-upload.de/view-21565480/upps.png.html)
## Post #15
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2013-12-13T11:38:49+00:00
- Post Title: Shenmue MT5 + Shenmue 2 MT7 Converter !

> Reply from shakotay2
>
> Thx for the samples. I just fetched some vertices from two of them:


There's a void mt5::parseFaces() function in the gitihub project but I didn't get a clue on getting the faces.

edit: there are face indices but even used as tri strips it doesn't look nice:
Lookin' good.
## Post #16
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2013-12-23T17:13:00+00:00
- Post Title: Re: deleted

Bump. Any updates?

Merry christmas, by the way.
## Post #17
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2014-01-03T14:49:39+00:00
- Post Title: Re: deleted

Happy new year. Bump again.
## Post #18
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-01-21T09:27:52+00:00
- Post Title: Re: deleted

2 yearly bump
## Post #19
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2018-08-25T08:09:43+00:00
- Post Title: Re: deleted

Since Shenmue PC (2008) is now here ... and the games use the same Model Data . Buuuuuuummmmmmmp
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-25T11:38:56+00:00
- Post Title: Re: deleted

well, from my experience you can bump threads as much as you want: if there's no interest you need to do your own research and show the results

With this said I make a little update to my post as of Sun Dec 08, 2013 1:13 pm concerning the MT5 format.
Not really sure what I missed then. After compiling the project from here:
[https://github.com/yazgoo/mt5_extraction_tools](https://github.com/yazgoo/mt5_extraction_tools)

```
 Creation Date 	4 9 2009
 License 	BSD
```

I surprisingly got this:



BIKS503G.jpg (64.88 KiB) Viewed 170 times



(There's a mt7 (py) project contained in the above linked project but as you may know I'm not a fan of python.)
## Post #21
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2018-08-25T11:52:45+00:00
- Post Title: Re: deleted

> Reply from shakotay2
>
> well, from my experience you can bump threads as much as you want: if there's no interest you need to do your own research and show the results

With this said I make a little update to my post as of Sun Dec 08, 2013 1:13 pm concerning the MT5 format.
Not really sure what I missed then. After compiling the project from here:
https://github.com/yazgoo/mt5_extraction_tools

Yazgoo did some solid groundwork for MT5 extraction but Hellwig's is the most accurate converter
[https://github.com/hellwig/shencon](https://github.com/hellwig/shencon)
[http://www.shenmuedojo.net/forum/viewto ... 37&t=47275](http://www.shenmuedojo.net/forum/viewtopic.php?f=37&t=47275)

I only bump this time because of the Re-Release and its better for search results not to make duplicate threads on the same topic.
With the re-release I hope there will be new interest in creating a fully working extractor , and possibly model exporter/importer to take Shenmue Modding to another level.

There is also a discord server 
[https://www.shenmuedojo.com/forum/index ... erver.376/](https://www.shenmuedojo.com/forum/index.php?threads/shenmue-hd-reverse-engineering-discord-server.376/)
## Post #22
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2018-08-29T22:53:14+00:00
- Post Title: Re: deleted

Someones figured out a Unity Importer based on Heliwigs sources
[https://www.shenmuedojo.com/forum/index ... unity.499/](https://www.shenmuedojo.com/forum/index.php?threads/shenmunity-shenmue-in-unity.499/)
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-23T20:16:21+00:00
- Post Title: Re: deleted

Another mt5 to obj conversion using yazgoo's basic mt5 "disasembler" (it's not a "disassembler" of course , it's a converter imho)



map07-mt5.png (94.34 KiB) Viewed 122 times



(small problem with the compiled exe is the correct use of parameters imho)
It's something like
test_mt5.exe --no-strips %1 [path to output directory] %1.obj %1.mtl x
in a batch file mt5.bat to be called like so
mt5.bat MAP07.MT5 
for example 
(MAP07.MT5 should reside in the exe folder if you don't want to mess with paths)

(Didn't check Hellwig's converter so far, only see that there's a huge png.h contained in his project, so texture support might be improved? Also the mt5 parser code is 4 times bigger than yazgoo's.)
## Post #24
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2018-10-25T22:09:27+00:00
- Post Title: Re: deleted

Fishbiters Shenmunity, an Importer that imports MT5 files (which contain PVR images) and MAP files from PKS archives which are similar but have a texture in a different PKF archive

Based on Heliwigs sources, Shenmunity is the Most advanced Importer in existance, it also extracts characters correctly which neither Yazgoo or Heliwigs extractor could do 
[https://www.shenmuedojo.com/forum/index ... -unity.499](https://www.shenmuedojo.com/forum/index.php?threads/shenmunity-shenmue-in-unity.499)

My only real issue is that it doesnt convert directly to OBJ (or whatever 3D format), there are Unity FBX, OBJ exporters but the FBX one doesnt keep textures and the OBJ one is out of date and I cant get it to work (or the structure of the import needs altering in some way)

Yazgoo laid the groundwork but building on his work is only copying what Heliwig did

Fishbiters sources
[https://github.com/Fishbiter/Shenmunity](https://github.com/Fishbiter/Shenmunity)
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-26T13:40:53+00:00
- Post Title: Re: deleted

well, fishbiter's source, don't have the time to deal with it- looks complicated.  

But I compiled Hellwig's source, good result, Unpacker outputs a dae and png files.

Sadly my blender dae importer doesn't load the textures automatically so I'd need to apply them manually.
Done for one only:



map07-mt5-HW.png (48.62 KiB) Viewed 106 times



@ReeceMix: maybe you could upload a character-mt5 files which Hellwig's Unpacker can't extract?
## Post #26
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2018-10-26T14:59:08+00:00
- Post Title: Re: deleted

[https://www.youtube.com/watch?v=jKqREkb7T1U](https://www.youtube.com/watch?v=jKqREkb7T1U)
## Post #27
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2019-03-28T12:34:16+00:00
- Post Title: Re: deleted

Final Bump: Took 9 years but we got there eventually due to renewed interest and the release of Shenmue 1&2 PC

Many Thanks to ShenmueDojo, Yazoo, Heliwig & Lemon Haze and the many people Involved over the years who complied thier knowlege into the ShenmueDKSharp tools & researchers (personally I did nothing but ask)
## Post #28
- Username: pititos
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 04, 2022 5:52 pm
- Post datetime: 2023-08-27T10:36:06+00:00
- Post Title: Re: deleted

Wanted to extract a few models off of What's Shenmue and Shenmue I, went on and compiled hellwig's shencon with Codeblocks, then used the binary on the .MT5 files extracted with GDI Explorer. For some reason it refuses to convert them and spits out this error intead:

uncompressed file with size198572
successful read 198572 bytes from file D:\file.MT5
Texture Pointer:10210 Model Pointer:f310
node definition ofs=62224 has unknown bytes not equal to zero.

What''s the issue here? Do .MT5 files have to be extracted or decompressed in any certain way first? I know it should be working fine since shakotay2 got it right. Are there any other tools to extract the models with skeleton/body weighing? Anything from .fbx to .dae will do; I hate .obj files with a burning passion.
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-27T14:59:50+00:00
- Post Title: Re: deleted

As far as I remember I didn't check a character-mt5 file because no one provided one.
## Post #30
- Username: pititos
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 04, 2022 5:52 pm
- Post datetime: 2023-08-27T17:14:40+00:00
- Post Title: Re: deleted

> Reply from shakotay2 ↑Sun Aug 27, 2023 10:59 pm at Sun Aug 27, 2023 10:59 pm
>
> 
As far as I remember I didn't check a character-mt5 file because no one provided one.
Could you be able to check these files if I posted them here? These were ripped from the original Dreamcast discs. I've been fighting my entire afternoon here trying to compile ShenmueDK with MSYS2, so if you were able to extract them I would appreaciate it.
For a lack of a better disposable file sharing service here's this link: [https://files.catbox.moe/az6arh.7z](https://files.catbox.moe/az6arh.7z) otherwise I would have used Anonfiles if it still existed.
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-27T18:42:38+00:00
- Post Title: Re: Shenmue MT5 + Shenmue 2 MT7 Converter !

> Reply from pititos ↑Mon Aug 28, 2023 1:14 am at Mon Aug 28, 2023 1:14 am
>
> 
, so if you were able to extract them I would appreaciate it.Sadly not. Both MT5 files produce 2 zero bytes .db files both using the unpacker (Hellwig source) while a map-MT5 extracts flawless.

NZM_M.MT5: node definition (at 0xf310) has unknown bytes not equal to zero
YWT_M.MT5: node definition (at 0xb6e8) has unknown bytes not equal to zero

There's a Noesis plugin from Benjamin Collins, which can import them, a little bit bent, though:
.



NZM_M.png (56.25 KiB) Viewed 26 times
## Post #32
- Username: pititos
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 04, 2022 5:52 pm
- Post datetime: 2023-08-27T22:25:50+00:00
- Post Title: Re: Shenmue MT5 + Shenmue 2 MT7 Converter !

> Reply from shakotay2 ↑Mon Aug 28, 2023 2:42 am at Mon Aug 28, 2023 2:42 am
>
> 
Sadly not.

What a shame. It's a shame that are a few tools that can export the .MT5 files to .obj yet none that use the Shenmue libraries to export them to .dae or .fbx. I may have to sort material manually but at least with either a .dae or an .fbx file I would have got to keep the skeleton and body weights.
Here's a screenshot with an .obj showing I can indeed extract the models, but I'd rather have anything other than .obj.
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-28T01:11:33+00:00
- Post Title: Re: Shenmue MT5 + Shenmue 2 MT7 Converter !

> Reply from pititos ↑Mon Aug 28, 2023 6:25 am at Mon Aug 28, 2023 6:25 am
>
> What a shame. It's a shame that are a few tools that can export the .MT5 files to .obj yet none that use the Shenmue libraries to export them to .dae or .fbx.I have no idea why you're complaining. The situation was clear (if I had read this again):
.

> Reply from ReeceMix ↑Fri Oct 26, 2018 6:09 am at Fri Oct 26, 2018 6:09 am
>
> Based on Heliwigs sources, Shenmunity is the Most advanced Importer in existance, it also extracts characters correctly which neither Yazgoo or Heliwigs extractor could do
