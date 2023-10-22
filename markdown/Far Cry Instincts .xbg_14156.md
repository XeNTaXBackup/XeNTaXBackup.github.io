## Post #1
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-03-28T19:27:31+00:00
- Post Title: Far Cry Instincts .xbg

Hello. I very want to open Far Cry Instincts models files.
It is *.XBG format, but another than in Dunia1\2 engines. I guess that its can be modified Crytek .CGF format.
I absolute novice in hexing, and how much I tried, i can't get correct meshes in Hex2Obj. 

Please look this files: [http://www.mediafire.com/download/8vz40 ... _Models.7z](http://www.mediafire.com/download/8vz405s6sjoge2v/FCI_Models.7z)
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-03-28T20:17:41+00:00
- Post Title: Far Cry Instincts .xbg

Yeah, looks like modified CryTek, though modified quite good. Format is pretty straightforward, I'm sure someone will make a tool for model import
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-28T22:11:14+00:00
- Post Title: Far Cry Instincts .xbg

> Reply from StreamThread
>
> , and how much I tried, i can't get correct meshes in Hex2Obj.yep, there is some hurdle:
Doesn't look like a hat, for sure. 
edit: well, was 8 bytes off



Rangerhat.jpg (156 KiB) Viewed 339 times


UVpos is 8.

> Reply from zaramot
>
> [...], I'm sure someone will make a tool for model importthere aren't too many "someones" atm  

And meanwhile many requesters seem to use 3D rippers (at least on PC).
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-03-29T14:00:40+00:00
- Post Title: Far Cry Instincts .xbg

[out]
## Post #5
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-03-29T14:22:27+00:00
- Post Title: Far Cry Instincts .xbg

Thanks a lot all for help!

> Reply from Wobble
>
> 
 I get repeated indices (0,0...), (14,14...) (41,41...)

Double parts of geometry  and  vertices it is can be something like collision data (optimization for console).  I just guess.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-29T14:28:28+00:00
- Post Title: Far Cry Instincts .xbg

> Reply from Wobble
>
>  I get repeated indices (0,0...), (14,14...) (41,41...)hex2obj uses this standard (?) algo (which excludes doubles) for creating face indices in (tri) Strip mode: [viewtopic.php?f=16&t=12804&p=116367#p116367](http://forum.xentax.com/viewtopic.php?f=16&t=12804&p=116367#p116367)
(see post as of Sat Feb 27, 2016 12:12 am)

Seems to work in 99.9% of the cases...
but I admit there might be formats where it does not.
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-03-29T23:05:06+00:00
- Post Title: Far Cry Instincts .xbg

[out]
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-30T11:09:04+00:00
- Post Title: Far Cry Instincts .xbg

> Reply from Wobble
>
> Where are vertex/trig/index counts, where is vertex format size?(well, I know harder mysteries.  )
boat01.xgb, offset 0x03A0: 32 01 18 00 8C 00
(FI count, FVFsize, vertex count of 2nd submesh)
For the fst one it's at 0x37C.

Uploaded samples are low poly:



boat01_xbg.JPG (15.42 KiB) Viewed 293 times
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-03-30T14:25:07+00:00
- Post Title: Far Cry Instincts .xbg

[out]
## Post #10
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-03-30T15:01:58+00:00
- Post Title: Far Cry Instincts .xbg

[out]
## Post #11
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-03-30T17:49:29+00:00
- Post Title: Far Cry Instincts .xbg

> Reply from shakotay2
>
> 

Uploaded samples are low poly:
boat01_xbg.JPG

It is original detalization in game. In Far Cry Instincts Predator some models are most highpoly. Characters, vehicles and weapons in particular. But nobody did a unpacker of Predator's DAT archives
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-30T18:30:13+00:00
- Post Title: Far Cry Instincts .xbg

uvs? Yeah, a mystery - for the fst submesh they're overlapping or whatever.
For the 2nd one UVpos=8 is okay:



boat01_2ndSM.jpg (154.89 KiB) Viewed 273 times
## Post #13
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-03-30T20:51:56+00:00
- Post Title: Far Cry Instincts .xbg

[out]
## Post #14
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-03-30T22:01:59+00:00
- Post Title: Far Cry Instincts .xbg

> Reply from Wobble
>
> 
Do you have textures for these models to test UVs?

"\Objects_xbox\Vehicles\JetSki\JetSki_Val_DF.xbt"
"\objects_xbox\vehicles\jetski\jetski_nt.xbt"

Looks like diffuse (DF) and normal texture (nt).

Im using Far Cry Evolution BMS script. After unpacking, all models, textures and other gamefiles are in garbage of *.dat files, and each of this files should be identified manually. 
Textures with DXT 3\DXT 5 compression. TextureFinder_v21 open it, but with some artefacts. 

This texture loos like Jetski:
[](http://radikal.ru/big/9c10dc34983f41bbbd03faa02c272638)

Unpacked level Training_00: [http://www.mediafire.com/download/hz3kd ... raining.7z](http://www.mediafire.com/download/hz3kd397y4lwxrc/00_Training.7z)
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-03-30T23:36:53+00:00
- Post Title: Far Cry Instincts .xbg

[out]
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-31T05:44:24+00:00
- Post Title: Re: Far Cry Instincts .xbg

collision mesh also contained:



boat_hull.jpg (74.75 KiB) Viewed 440 times
## Post #17
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-03-31T06:28:46+00:00
- Post Title: Re: Far Cry Instincts .xbg

> Reply from Wobble
>
> 

Ok, if you can't find it, nevermind.  That is a texture of a person's helmet, btw.

Just most part of textures in very small resolution. Besides checking UVW's of models, it dont need in principle. Because in PC Far Cry 1 game are used the same textures in original, biggest, resolutions, so the conclusion suggests itself
## Post #18
- Username: maharnavi
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Dec 10, 2014 10:46 pm
- Post datetime: 2016-03-31T06:34:33+00:00
- Post Title: Re: Far Cry Instincts .xbg

Hello could anyone please help me regarding infinite crisis.I have the latest version and i want to decompress some model and animation files from that game.the file extensions are .rp and .pck please can anyone help me regarding this matter
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-31T07:38:26+00:00
- Post Title: Re: Far Cry Instincts .xbg

> Reply from StreamThread
>
> After unpacking, all models, textures and other gamefiles are in garbage of *.dat files, and each of this files should be identified manually. 
Textures with DXT 3\DXT 5 compression. TextureFinder_v21 open it, but with some artefacts. 

Unpacked level Training_00: http://www.mediafire.com/download/hz3kd ... raining.7z
I made a Noesis plugin that will open your dat textures  


 tex_FarCryInstincts_xbt-dat.zip
(683 Bytes) Downloaded 63 times


it supports the dxt1 and dxt5 textures
i think less than half of those dat files are actually textures though
## Post #20
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-03-31T13:13:40+00:00
- Post Title: Re: Far Cry Instincts .xbg

> Reply from AceWell
>
> StreamThread wrote:
I made a Noesis plugin that will open your dat textures  
tex_FarCryInstincts_xbt-dat.zip
it supports the dxt1 and dxt5 textures
i think less than half of those dat files are actually textures though

Great!

Thanks a lot   

Among *.dat also can be: 
*.xba files (Xbox Animation), *.bin (Maybe some binary animations, or anim info. Also it is can be analogs of *.cal files - animations lists from FC1, but binaries), and other map info files.

Reliable filenames with extensions and all pathes can be found in *.NFO files of Paradise Lost - arcade port of Far Cry Instincts. 
Im already created [the topic](http://forum.xentax.com/viewtopic.php?f=10&t=14136) in archives research thread. If someone will modify [Far Cry Evolution BMS script](http://wiki.xentax.com/index.php?title=Far_Cry_Evolution_DAT) for using info from this files, it would make a unpack is very simple.
## Post #21
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-04-02T21:58:52+00:00
- Post Title: Re: Far Cry Instincts .xbg

[out]
## Post #22
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-04-03T18:01:36+00:00
- Post Title: Re: Far Cry Instincts .xbg

> Reply from Wobble
>
> There are several .dat files that are models.
I don't understand why these haven't been renamed to .xbg.

I might have missed some, thanks. 
And i not rename all extensions before when i upload this unpacked level. All files with names - it's models.

Btw, characters models don't have multiply mesh files or something, what can be looks like Morphing data? (Characters face expressions morphing)
## Post #23
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-04-04T15:24:23+00:00
- Post Title: Re: Far Cry Instincts .xbg

[out]
## Post #24
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-04-06T16:47:29+00:00
- Post Title: Re: Far Cry Instincts .xbg

> Reply from Wobble
>
> 
merc.JPG

I see you already writing a plugin\scripts\importer for some 3d viewer\editor program (Noesis?) 
Maybe you can share it, if it already can load static meshes?

In principle, for me while would be enough any importer/converter only meshes from xbg. H2O still quite difficult for me =(
In the first, i want to import environments and decorations models (buildings, props, etc.). Sry for my English :~
## Post #25
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-04-06T19:47:03+00:00
- Post Title: Re: Far Cry Instincts .xbg

[out]
## Post #26
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-04-08T00:48:56+00:00
- Post Title: Re: Far Cry Instincts .xbg

[out]
## Post #27
- Username: Deathdoor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 02, 2010 2:35 am
- Post datetime: 2016-05-11T16:38:51+00:00
- Post Title: Re: Far Cry Instincts .xbg

> Reply from Wobble
>
> Ok, here's a plugin for uu3d.
Sorry, but what is uu3d? Can you make plugin for 3Dmax or Maya. Even without bones. I can rig it myself.
And can it work with far cry 2/3/4 .xbg files? if need i can send some.
## Post #28
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-05-13T18:13:53+00:00
- Post Title: Re: Far Cry Instincts .xbg

> Reply from Deathdoor
>
> Wobble wrote:Ok, here's a plugin for uu3d.

And can it work with far cry 2/3/4 .xbg files? if need i can send some.

It is will not work with other Far Cry .xbg files. For Far Cry 3-4 exist other scripts. There is topic: [viewtopic.php?f=16&t=12339&hilit=xbg](http://forum.xentax.com/viewtopic.php?f=16&t=12339&hilit=xbg)
## Post #29
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-05-13T19:27:15+00:00
- Post Title: Re: Far Cry Instincts .xbg

[out]
## Post #30
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2016-06-17T08:05:01+00:00
- Post Title: Re: Far Cry Instincts .xbg

> Reply from AceWell
>
> 
I made a Noesis plugin that will open your dat textures  
The attachment tex_FarCryInstincts_xbt-dat.zip is no longer available
it supports the dxt1 and dxt5 textures
i think less than half of those dat files are actually textures though

Some XBT textures not opening.
[00_xbt.zip](https://xentaxbackup.github.io/file/11069_00_xbt.zip)
## Post #31
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-17T22:36:39+00:00
- Post Title: Re: Far Cry Instincts .xbg

i added support for your non working diffuse texture samples. the normal map texture samples look morton swizzled but i still could not get correct image scale so i just commented out that in the script and is there if you want to play around with it to get it working right. i have no clue what format the oceandist_00.xbt texture is. ususally if i cannot get anything to show up in TextureFinder there is not much else i can do.  


 tex_FarCryInstincts_xbt-dat.zip
(793 Bytes) Downloaded 52 times
## Post #32
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2016-08-24T22:52:13+00:00
- Post Title: Re: Far Cry Instincts .xbg

I'm writing maxscript for importing this XBG format and want recognize vertex normals.

e.g. for model with FVFSize = 16 for normals remains only 4 bytes (allocated with bold text):

```

vx short, vy short, vz short, null\delimetr short, tu short, tv short, [b]normals??[/b]
```


I gues what normals can stored in these 4 bytes (nx, ny, nz, nw), but I cant get correct value for dividing. Divide to 65535.0,  or divide to 255.0 * 2 - 1 do not give right result as can be seen into 3ds Max.
## Post #33
- Username: donatoqueen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 24, 2011 1:59 pm
- Post datetime: 2020-05-22T19:36:18+00:00
- Post Title: Re: Far Cry Instincts .xbg

Can you please let me know how I can retrieve the filenames and extensions from the files I export using quickbms? Currently they all appear as .ubi etc and just use what looks hexadecimal values for the filenames.
## Post #34
- Username: meanstoanend
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 18, 2023 1:29 am
- Post datetime: 2023-05-17T18:08:56+00:00
- Post Title: Re: Far Cry Instincts .xbg

I'm new to this, made an account just to ask, but can someone please help me... I downloaded Noesis but it won't let me open any Instincts files. I downloaded Instincts plugin from someone on this thread but I don't know how to add it to Noesis.
## Post #35
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2023-05-25T15:25:32+00:00
- Post Title: Re: Far Cry Instincts .xbg

Well i got some filenames with hashes inside game files + get some more but without hashed name. And i don't know how to rehash them.
It's crc32 but with polynomials most probably.

EDiT: O.K I got some more filenames from other versions and merged them together.
So here is BMS for Instincts, Evolution, Paradise Lost, Vengance

```
# Instincts,Evolution,Paradise Lost,Vengance #

Open FDDE FAT 0
Open FDDE DAT 1
get BaseFileName basename
idstring "DAT2"
get Files uint32

for i = 0 < Files
	get Offset uint32
	get Size uint32
	get CRC32Name uint32
	namecrc CRCName CRC32Name "fci_filenames.list" 32
	string Name p= "%s/%s" BaseFileName CRCName
	log Name Offset Size 1
next i
```


And here is BMS for Predator. It uses same fci_filenames.list.

```
Open FDDE FAT 0
Open FDDE DAT 1
get BaseFileName basename
idstring "DAT2"
get Files uint32
comtype lzma_dynamic

for i = 0 < Files
	get Offset uint32
	get ComSize uint32
	get Size uint32
	get CRC32Name uint32
	namecrc CRCName CRC32Name "fci_filenames.list" 32
	string Name p= "%s/%s" BaseFileName CRCName
	if ComSize != Size
		clog Name Offset ComSize Size 1
	else
		log Name Offset Size 1
	endif
next i
```

[fci_filenames.zip](https://xentaxbackup.github.io/file/23849_fci_filenames.zip)
