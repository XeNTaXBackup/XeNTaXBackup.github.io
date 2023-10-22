## Post #1
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-13T06:08:52+00:00
- Post Title: MadWorld [Wii] .dat

I haven't found any Noesis scripts to open these files, Any help will be appreciated 
[http://www.mediafire.com/file/3mm0r5akf ... l.zip/file](http://www.mediafire.com/file/3mm0r5akfe42gxx/pl.zip/file)
## Post #2
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2020-08-13T08:29:06+00:00
- Post Title: MadWorld [Wii] .dat

It's a Platinum Games game, you should ask Kerilk to add support for it [https://github.com/Kerilk/noesis_bayonetta_pc](https://github.com/Kerilk/noesis_bayonetta_pc)
It already supports pretty much all their games (bayonetta, TW101, Metal Gear Rising, Astral Chain, Nier Automata, Vanquish etc)

The naming convention in your samples. seems to be he same as the other games.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-13T08:52:26+00:00
- Post Title: MadWorld [Wii] .dat

Using hex2obj (view link in my sig):
.



pl0010_1-dat.png (30.23 KiB) Viewed 456 times


(no time to care for face indices)
## Post #4
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-08-14T00:23:51+00:00
- Post Title: MadWorld [Wii] .dat

The animation format seems to be the same as Bayonetta WiiU. The model format I have never seen, and skeleton seem to be havok related. The texture container is also unknown. So this one would take me a lot of work, don't know when I'll have time to add it.
## Post #5
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-14T03:07:11+00:00
- Post Title: MadWorld [Wii] .dat

> Reply from Kerilk ↑Fri Aug 14, 2020 8:23 am at Fri Aug 14, 2020 8:23 am
>
> 
The animation format seems to be the same as Bayonetta WiiU. The model format I have never seen, and skeleton seem to be havok related. The texture container is also unknown. So this one would take me a lot of work, don't know when I'll have time to add it.

Thank you! I'll be looking forward to the future for support to this game, Take your time.
## Post #6
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-14T12:57:08+00:00
- Post Title: MadWorld [Wii] .dat

Great to see some work on that game, I'd love to have animations viewable. 
The UInt at 0x20 gives the "JK" section offset, which is the one who seems to contain model information. 
Here's what I have after a quick look (thanks to Shakotay for the vertex information) 
```
	vertexFlag = bs.readUByte() #pos as shorts if 0x12, float if 0x13
	bs.readUByte()
	vertexCount = bs.readUInt()
	vertexOffset = bs.readUInt()
	
	bs.readUInt() #???
	bs.readUInt() #???
	
	bs.readUInt() #???
	bs.readUInt() #???
	
	bs.readUInt() #???
	bs.readUInt() #???
	
	bs.readUInt() #???
	bs.readUInt() #???
	
	jointCount = bs.readUInt()
	jointParentingOffset = bs.readUInt() #joint indices seem to be after that section, fixed length ?
	bs.readUInt() #???
	jointPosOffset = bs.readUInt()
	
```


I'll work a bit more on it this evening. UV and normal coords are probably in those unknown sections but I didn't look into it yet, was looking for face indices. I have an idea about where they could be but I need to do some testing first.
[Capture.PNG](https://xentaxbackup.github.io/file/18603_Capture.PNG)
## Post #7
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-14T17:18:37+00:00
- Post Title: MadWorld [Wii] .dat

Had more time to work on this, got the faces and the submeshes. I tried to find some skinning info but didn't find anything promising. There are also some weird indices interleaved between the face indices, gave me some trouble to figure faces out.
I didn't look into normals and UVs but I assume they must be in one of the sections following the vertex positions, couldn't check myself.

Anyways I won't have more time to work on this, hopefully someone finishes the job (to use the plugin you need to rename the .dat extension to .datM to avoid conflict with the bayonetta plugin). Don't forget to enable face cull when previewing.


[fmt_datM.zip](https://xentaxbackup.github.io/file/18605_fmt_datM.zip)
## Post #8
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-15T21:11:54+00:00
- Post Title: MadWorld [Wii] .dat

Had some stuff cancelled today so had some time to work more on it after all. 
Skinning cracked : 


I'm confused about Normals and UVs though. I'm pretty sure to know where they are but for some reason they have a count inferior to the position count, so I can't feed the buffer or it'll complain about an out of bounds error. Did anyone see a similar thing in another format ? It's the first time I see something like this myself, not really sure if I should pad the buffer with zeros or something like that.
Anyways, all that info is in that updated script, the normals and uv parts are commented out to avoid crashing for now.

So yeah only UVs and Normals left. Hopefully Kerilk can get the anims now.


 fmt_datM.zip
(1.59 KiB) Downloaded 16 times
## Post #9
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-16T00:34:38+00:00
- Post Title: MadWorld [Wii] .dat

> Reply from Joschka ↑Sun Aug 16, 2020 5:11 am at Sun Aug 16, 2020 5:11 am
>
> 
Had some stuff cancelled today so had some time to work more on it after all. 
Skinning cracked : 


I'm confused about Normals and UVs though. I'm pretty sure to know where they are but for some reason they have a count inferior to the position count, so I can't feed the buffer or it'll complain about an out of bounds error. Did anyone see a similar thing in another format ? It's the first time I see something like this myself, not really sure if I should pad the buffer with zeros or something like that.
Anyways, all that info is in that updated script, the normals and uv parts are commented out to avoid crashing for now.

So yeah only UVs and Normals left. Hopefully Kerilk can get the anims now.

fmt_datM.zip

If you'd like I can supply more files.
## Post #10
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-08-16T02:01:46+00:00
- Post Title: MadWorld [Wii] .dat

Hello,

I had some time to work on the models today, and thanks to Joschka's work I have the model format mostly figured out:
[https://github.com/Kerilk/bayonetta_too ... d%20mdb.bt](https://github.com/Kerilk/bayonetta_tools/blob/master/binary_templates/MadWorld%20mdb.bt)
Normal and UVs are indexed, same as positions.

I am having trouble with figuring the texture format:
[https://github.com/Kerilk/bayonetta_too ... d%20tpl.bt](https://github.com/Kerilk/bayonetta_tools/blob/master/binary_templates/MadWorld%20tpl.bt)
I am not having a lot of luck with rawtex:



MadWorl.jpg (227.01 KiB) Viewed 307 times


This is the best I could get.
## Post #11
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-08-16T09:10:26+00:00
- Post Title: MadWorld [Wii] .dat

> Reply from Kerilk ↑Sun Aug 16, 2020 10:01 am at Sun Aug 16, 2020 10:01 am
>
> 
I am having trouble with figuring the texture format:
https://github.com/Kerilk/bayonetta_too ... d%20tpl.bt
I am not having a lot of luck with rawtex:
MadWorl.jpg
This is the best I could get.

I dunno if it'll be helpfull at all, apologize in case...
There're some general infos on the format here
[http://wiki.tockdom.com/wiki/TPL_(File_Format)](http://wiki.tockdom.com/wiki/TPL_%28File_Format%29)
With a list of programs that can open them~
## Post #12
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-16T10:41:30+00:00
- Post Title: MadWorld [Wii] .dat

Quick and dirty Noesis script to get pl0010 and pl0030 textures, doesn't work on pl0000 but that's probably because there's some wrong offset or something, didn't look much into it, just wanted to see if I could get some textures to work.
Big thanks to Zheneq's Noesis wii texture library [https://github.com/Zheneq/Noesis-Plugin ... ndo_tex.py](https://github.com/Zheneq/Noesis-Plugins/blob/master/lib_zq_nintendo_tex.py)

You need to download the above script and put it next to the attached one, change the .dat to .datMT and you should get the textures (you'll need to cycle blend for some of them).




 tex_madWorld.zip
(653 Bytes) Downloaded 17 times



It's just meant as a proof of concept since Kerilk will integrate it in the bayonetta plugin.

> Reply from Kerilk ↑Sun Aug 16, 2020 10:01 am at Sun Aug 16, 2020 10:01 am
>
> 
Normal and UVs are indexed, same as positions.

Nice catch on that one, I never saw that before, these interleaved indices make a lot more sense now.
## Post #13
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-08-16T13:59:52+00:00
- Post Title: MadWorld [Wii] .dat

I have all the information I need. I just need to write it in C++. Getting more samples (a lot) would also be useful just to identify all vertex formats.
## Post #14
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-16T20:23:17+00:00
- Post Title: MadWorld [Wii] .dat

> Reply from Kerilk ↑Sun Aug 16, 2020 9:59 pm at Sun Aug 16, 2020 9:59 pm
>
> 
I have all the information I need. I just need to write it in C++. Getting more samples (a lot) would also be useful just to identify all vertex formats.

Here you go: [http://www.mediafire.com/file/osgxh1fwo ... s.zip/file](http://www.mediafire.com/file/osgxh1fwo7nxo4g/MadWorld+Examples.zip/file) 
Keep up the good work!
## Post #15
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-08-21T00:47:48+00:00
- Post Title: MadWorld [Wii] .dat

Okay, I updated the templates if anyone is interested. I don't understand the format fully yet, it was much more complicated than it seemed at first, but I should be good to start adding support into noesis. This will take some time.
## Post #16
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-08-24T03:37:34+00:00
- Post Title: Re: MadWorld [Wii] .dat

I released a new version of the plugin with support for MadWorld, including animations. Please, tell me if I missed something.
[https://github.com/Kerilk/noesis_bayonetta_pc](https://github.com/Kerilk/noesis_bayonetta_pc)
## Post #17
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-24T04:05:29+00:00
- Post Title: Re: MadWorld [Wii] .dat

> Reply from Kerilk ↑Mon Aug 24, 2020 11:37 am at Mon Aug 24, 2020 11:37 am
>
> 
I released a new version of the plugin with support for MadWorld, including animations. Please, tell me if I missed something.
https://github.com/Kerilk/noesis_bayonetta_pc

Amazing work!
[Jackcayy.jpg](https://xentaxbackup.github.io/file/18645_Jackcayy.jpg)
## Post #18
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-24T06:38:18+00:00
- Post Title: Re: MadWorld [Wii] .dat

> Reply from Kerilk ↑Mon Aug 24, 2020 11:37 am at Mon Aug 24, 2020 11:37 am
>
> 
I released a new version of the plugin with support for MadWorld, including animations. Please, tell me if I missed something.
https://github.com/Kerilk/noesis_bayonetta_pc

Found mesh error most meshes are fine, Example files: [http://www.mediafire.com/file/s0lrtaafp ... s.zip/file](http://www.mediafire.com/file/s0lrtaafpuqexxe/cs.zip/file)
[deform.JPG](https://xentaxbackup.github.io/file/18646_deform.JPG)
## Post #19
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-08-24T23:56:17+00:00
- Post Title: Re: MadWorld [Wii] .dat

I published an updated version that should fix this issue and a texture decoding problem for CMPR(BC1) texture compression. The only real issue left is alpha blending, but I can't find a way to determine if a model/material uses alpha for transparency or for shininess. Toggling it inside Noesis is easy anyway ("No default blend" option in the material).
## Post #20
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-25T00:45:37+00:00
- Post Title: Re: MadWorld [Wii] .dat

> Reply from Kerilk ↑Tue Aug 25, 2020 7:56 am at Tue Aug 25, 2020 7:56 am
>
> 
I published an updated version that should fix this issue and a texture decoding problem for CMPR(BC1) texture compression. The only real issue left is alpha blending, but I can't find a way to determine if a model/material uses alpha for transparency or for shininess. Toggling it inside Noesis is easy anyway ("No default blend" option in the material).

For the files in Case0 - Case5 , CaseA - CaseF don't open and cannot be exported
## Post #21
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-08-25T00:50:19+00:00
- Post Title: Re: MadWorld [Wii] .dat

Those are level files, adding support for those will require additional work.
## Post #22
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-08-25T17:34:13+00:00
- Post Title: Re: MadWorld [Wii] .dat

I got more time than I expected yesterday evening so I added support for the levels. I also changed the default material behavior as the game favors transparency above other usage of the alpha channel. I disabled lighting for materials as the engine did not support dynamic lighting, from the screen shots I could see.
## Post #23
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-25T18:24:25+00:00
- Post Title: Re: MadWorld [Wii] .dat

> Reply from Kerilk ↑Wed Aug 26, 2020 1:34 am at Wed Aug 26, 2020 1:34 am
>
> 
I got more time than I expected yesterday evening so I added support for the levels. I also changed the default material behavior as the game favors transparency above other usage of the alpha channel. I disabled lighting for materials as the engine did not support dynamic lighting, from the screen shots I could see.

This is awesome, thank you so much. Can't wait to check these out.
