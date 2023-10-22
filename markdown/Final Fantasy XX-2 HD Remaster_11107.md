## Post #1
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-01-03T19:34:52+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

This game came out not that long ago and seems to use the phyre format
using shakotay2's hex2obj i managed to get Yunas model



Screenshot (14).png (151.09 KiB) Viewed 2015 times



I was just wondering if anyone could help and make a noesis script for this format since there are a ton of models and manually putting in the offsets for each model is tedious.
## Post #2
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2014-01-06T11:55:39+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

Can you tell the relative coordinates (Meaning, what's the order of items) for these models, or the exact ones for that sample?
## Post #3
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2014-01-06T13:50:54+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

Interesting. I hope lot of people will be interested to help.
## Post #4
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-01-06T20:26:37+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

Just looked at the high poly model files (the picture i posted before was of low poly yuna) and turns out they used 2048x2048 textures.
gonna try and rip the high poly model soon to show.

Basically the phyre format works like this:
Header stuff?
Vertex data (ignore)
Bones?
face indices for each object
(obj1)
verticies
uv
normals?
????
(obj2) ...
## Post #5
- Username: locakert22
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Mar 28, 2011 9:47 pm
- Post datetime: 2014-01-25T17:22:05+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

SOORY

how to extract file [psarc]  ??? 

FFX-2_Data.psarc
FFX_Data.psarc


[ff.jpg](https://xentaxbackup.github.io/file/6954_ff.jpg)
## Post #6
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-01-25T18:38:11+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

> Reply from locakert22
>
> how to extract file [psarc]  ???
use this 

 PSARC.zip
(26.06 KiB) Downloaded 285 times

 or there is another psarc extractor you can find in net, basicly they all almost the same (some old extractor can't work with TLoU game actually only)
## Post #7
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-02-15T22:22:13+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

Is there really no interest in this game? >< The updates they did seem very nice and FFx and X-2 are some of the best games out there.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-16T00:59:10+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

It's not that there's no interest. It's just that it uses the new PHRYENGINE format, which is a total pain in the ass. We looked into it once and the format is documented in the latest PS3 SDK through code, but it would take somebody with A LOT of time on their hands to figure it out completely (how all the PHRYE objects are serialized). This is one of those ones where I say, "Just wait for (or keep bugging) Rich to do it" hehehe.
## Post #9
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-02-16T11:12:05+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

> Reply from howfie
>
> It's not that there's no interest. It's just that it uses the new PHRYENGINE format, which is a total pain in the ass. We looked into it once and the format is documented in the latest PS3 SDK through code, but it would take somebody with A LOT of time on their hands to figure it out completely (how all the PHRYE objects are serialized). This is one of those ones where I say, "Just wait for (or keep bugging) Rich to do it" hehehe.

oh damn >< i thought .pssg was the painful format, is phyre the new version for that?
Ah well maybe one day someone will get around to do it xD
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-16T11:39:54+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

yep, phrye is the successor to pssg and it is worse lol
## Post #11
- Username: Jecht
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 26, 2012 9:32 am
- Post datetime: 2014-03-26T06:09:19+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

Kay, I know its post like a month later, but I did just notice heheh.

Maybe this gonna sound pretty noob,but:

Could not be more easy just extract the textures?

Like for what I've saw with mikulover39's SS and the Tumblr spam of the HD; they use the same models, just with biggest-redo-texture...

Just my way of see it anyway...
## Post #12
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2014-04-14T03:11:49+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

Still no news about this?
I'm trying to get a viewable DDS file out of the DDS.Phyre files but I'm guessing this needs some sort of extractor.

I'd be also nice to have a plugin for Noesis to view DAE.Phyre files cuz it seems that not only models use this format, also Maps do.
## Post #13
- Username: Jecht
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 26, 2012 9:32 am
- Post datetime: 2014-04-17T04:00:07+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

> Reply from Haro
>
> Still no news about this?
I'm trying to get a viewable DDS file out of the DDS.Phyre files but I'm guessing this needs some sort of extractor.

I'd be also nice to have a plugin for Noesis to view DAE.Phyre files cuz it seems that not only models use this format, also Maps do.
Maybe because it has turn hard to extract it... Or they don't have time for try something to (Cannot blame them)

On my case I cannot help on nothing because my know on scrip-relative stuff its -100%. A part that I don't have the game too.

I'm a patient man, so I'd wait if someone manage to get out something. At least the texture, that its the only it interesting me. Because I always get some bug with the Alpha map of the old FFX models.

Oh yeah, a part of wish you luck to man.
## Post #14
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-04-18T21:55:59+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

> Reply from Haro
>
> Still no news about this?
I'm trying to get a viewable DDS file out of the DDS.Phyre files but I'm guessing this needs some sort of extractor.

I'd be also nice to have a plugin for Noesis to view DAE.Phyre files cuz it seems that not only models use this format, also Maps do.

Use Iceberg's texture finder 2.0 on the dds.phyre files, and for player characters set the width to 1024.

[](http://s85.photobucket.com/user/ultima_espio/media/Yuna_zpsfc0cd77a.png.html)
## Post #15
- Username: Jecht
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 26, 2012 9:32 am
- Post datetime: 2014-04-19T04:43:51+00:00
- Post Title: Final Fantasy X/X-2 HD Remaster

> Reply from ultimaespio
>
> 
Use Iceberg's texture finder 2.0 on the dds.phyre files, and for player characters set the width to 1024.

Huh. So... I was wrong. They've join the two texture pieces of the High Poly in one. I guess why anyway...
But that mean each model has they own UV different from the old game. Still, this help me for don't think its just an "Re-texture" maybe wasn't just that...

Still wondering if the texture of one character of that game has being Re-UVmapped... (what its pretty obvious who by the nick I use, even do... I don't think I can request it hehe. well gotta wait)
## Post #16
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2014-04-23T12:42:28+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Looks like they also changed the mesh

PCSX2: [http://img3.wikia.nocookie.net/__cb2013 ... arkand.jpg](http://img3.wikia.nocookie.net/__cb20130116124524/finalfantasy/images/archive/8/88/20131226173049%21Tidus_and_auron_in_zanarkand.jpg)
PS3: [http://img2.wikia.nocookie.net/__cb2013 ... arkand.jpg](http://img2.wikia.nocookie.net/__cb20131226173050/finalfantasy/images/8/88/Tidus_and_auron_in_zanarkand.jpg)
## Post #17
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2014-05-04T02:35:05+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Got my hands on the Phyre SDK.
It seems those .phyre files are exported blob files specified for the corresponding platform.
originally imported DAE files are XML, but they get compiled to a proprietary binary format.
In the SDK, there is no importer for this or whatsoever.
## Post #18
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-05-04T15:45:23+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

> Reply from Haro
>
> Looks like they also changed the mesh

PCSX2: http://img3.wikia.nocookie.net/__cb2013 ... arkand.jpg
PS3: http://img2.wikia.nocookie.net/__cb2013 ... arkand.jpg

I don't see any new geometry, some new textures yeah, especially the eyes look a lot better, but thats still texture work.
## Post #19
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-05-04T18:51:14+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

There's definitely model work done though, even if it's not that noticeable. The lower poly models now have separate fingers (that move as one), and the Higher quality ones have at least had their faces rebuilt.



[http://www.deviantart.com/art/Final-Fan ... -425540640](http://www.deviantart.com/art/Final-Fantasy-X-2-HD-Remaster-Yuna-WIP-425540640)
## Post #20
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2014-05-19T10:39:35+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

I haven't further analized the format, but are they like .bdae (binary collada) files?
## Post #21
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2014-09-01T07:39:36+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Still not news?
Because its really hard try to extract a model using hex

What its not so hard its extract texture of the games, I've test my self and many NPC, Fiends, Objects, Weapons they use the same texture size and UV Mapping. If that help in something
## Post #22
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2014-09-23T16:35:28+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Nope. 
I'm still using the models from the original games, there are plenty of tools to dump/convert them.
## Post #23
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2014-09-28T06:04:44+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

> Reply from Haro
>
> Looks like they also changed the mesh

PCSX2: http://img3.wikia.nocookie.net/__cb2013 ... arkand.jpg
PS3: http://img2.wikia.nocookie.net/__cb2013 ... arkand.jpg

WOW!

(Auron looks...older.   Tidus looks so different though.)

It looks like they took all the cutscene FMV high def character design quality and applied it to the entire game. I am intrigued, even though it will take some getting used to; FFX has been around for quite some time now; I was sort of used to the barbie doll fingerless-hands.   

I'm excited for more tools to come out for the remaster! Hopefully something Noesis-friendly.
## Post #24
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-10-03T18:39:00+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Hello

Here is Noesis script for geometry.
Bones and skinning not supported.
Copy script in noesis   "...\plugins\python"  folder.
[fmt_phyre.zip](https://xentaxbackup.github.io/file/7881_fmt_phyre.zip)
## Post #25
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-10-03T22:01:08+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Thanks, testing it out now 


Tidus' cutscene model has UV issues on his hair, C101.

For some reason there's a model of Shuyin in FFX, C307.
## Post #26
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-10-05T22:27:30+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Thank you so much for the plugin Szkaradek. It works pretty well on the X-2 models I looked at (most of Yuna, a few of Rikku/Paine and some returning characters from X). Are you planning to add skeleton support down the line?
## Post #27
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2014-10-05T23:14:04+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

> Reply from Szkaradek123
>
> Hello

Here is Noesis script for geometry.
Bones and skinning not supported.
Copy script in noesis   "...\plugins\python"  folder.

can't open with noesis some file 

here sample

[http://www.mediafire.com/download/gxnhtn2hym1atal](http://www.mediafire.com/download/gxnhtn2hym1atal)
## Post #28
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-10-06T08:23:17+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Hi

Sorry. I can't fix script for bones or another files.
It is difficult.

Here is a logfile "c001.dae.phyre.log" with unpacked data from "c001.dae.phyre" file. Maybe it help someone to reversing.
I get stuck at offset 1311516. 
It is a section with a lot of bytes ,which keep maybe info about how each sections are joint.

Sections:
at offset 26799 - list of sections [type, unk,info size, data size , unk, unk, unk, unk, unk ]
at offset 32139 - section type "30" - list of parent id for bones
at offset 33367 - section type "47" - list of materials. It keep info about indices count, indices offset, boneMapList item offset, boneMapList item count
at offset 35475 - section type "8" - list of vertex data (position,uv,skin,normals) [stride, item count, data offset, data size]
at offset 51131 - section type "29" - list of all used matrices. bone count for meshes keep section "139"
at offset 72891 - section type"140" - boneMapList for all meshes
at offset 119371 - section type "75" - list of bones. [bone hash, bone parent hash, bone matrix]. I can't  to build skeleton from this data.

Numbers for type of section are another for each "version" of file.


[http://www.mediafire.com/download/6zm7v ... tf/GCM.zip](http://www.mediafire.com/download/6zm7v2490rz8utf/GCM.zip)
## Post #29
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-10-06T21:05:49+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

I know why there's UV errors on Tidus C101, his hair is a separate texture in a separate phyre file. In the textures folder there's:

c101.dds.phyre - Main body texture
c101_01.dds.phyre - Hair texture

So it's just loading the one texture and not both.
## Post #30
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-06T21:39:48+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Does this work with ore imo files??
## Post #31
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2014-11-12T22:40:17+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

> Reply from Szkaradek123
>
> Hello

Here is Noesis script for geometry.
Bones and skinning not supported.
Copy script in noesis   "...\plugins\python"  folder.

ABSOLUTE THANK YOU!!!!
it works almost perfectly, but at least now its possible extract the models from the game without many problems! plus, its possible watch the DDS file it got too!

Irony of all:
If it get better, maybe it could end on extracting World models, as on the HD version, its possible get those models, because they're on DAE.Phyre too.

Still, gotta wait to!
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-17T22:00:55+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

> Reply from lumekano
>
> Szkaradek123 wrote:Hello

Here is Noesis script for geometry.
Bones and skinning not supported.
Copy script in noesis   "...\plugins\python"  folder.

can't open with noesis some filethose which can't be loaded by the script can be assembled manually.
But it's no fun. Also I didn't look for the uvs:



m132.jpg (122.2 KiB) Viewed 1714 times
## Post #33
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2015-01-09T03:14:38+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

I'm interesting in converting maps.
Do you think this is possible with the script too?
## Post #34
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2015-02-20T03:23:52+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

> Reply from Haro
>
> I'm interesting in converting maps.
Do you think this is possible with the script too?

Late respond, but well, I was out:

Its not possible extract maps with the plugging (If you're saying about the world maps) Yet, the plugin it does open almost all the dds.phyre file, which are the texture of the models and even maps.
We can only wait till they upgrade the plunging.
## Post #35
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2016-05-13T01:16:52+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

This thread's been dead for over a year.
Now that the PC version is out, maybe people are interested in working on a model converter again.
## Post #36
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2016-05-16T17:55:09+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Topher on Qhimm forums made an unpacker for Steam version (They use VBF files):
[http://forums.qhimm.com/index.php?topic ... #msg240957](http://forums.qhimm.com/index.php?topic=16943.msg240957#msg240957)
Might help for modding. They use the same file format and structure, therefore a script posted here should work on PC files too. I'm going to see right now.

Nope>
```
version: -1118371840
version not supported: -1118371840
```
## Post #37
- Username: twink333
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 08, 2016 1:42 pm
- Post datetime: 2016-12-08T06:04:36+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

> Reply from Haro
>
> Got my hands on the Phyre SDK.
It seems those .phyre files are exported blob files specified for the corresponding platform.
originally imported DAE files are XML, but they get compiled to a proprietary binary format.
In the SDK, there is no importer for this or whatsoever.
There are full source, and u actually can do a reverse tool from it.

About .phyre files

> The PhyreEngine™ runtime requires that all assets are in an optimized format for the target platform.  The PhyreEngine™ target format is a .phyre file – this is a binary serialized form of a PhyreEngine™ PCluster object, which is the internal mechanism the PhyreEngine™ game engine uses to cluster together related objects for loading and unloading. This format cannot be directly exported from typical DCC tools, but must be converted from an intermediate format. For typical 3D data, the supported format is COLLADA, and we provide exporters for Maya and MAX. Other COLLADA exporters (including those for other DCC packages) are available, but compatibility is not guaranteed. Other source formats are supported for different types of asset.

And there is some explanations about how this work: (not usefull for conversion .phyre, but still very interesting)[https://research.ncl.ac.uk/game/masters ... turing.pdf](https://research.ncl.ac.uk/game/mastersdegree/workshops/ps3introductiontogcm/GCM%20Texturing.pdf)

And here is what u looking for [http://www63.zippyshare.com/v/s2GRiMEu/file.html](http://www63.zippyshare.com/v/s2GRiMEu/file.html)
Maybe u should have a Cg Toolkit 3.0 February 2011 (Ididnt testet that yet)

For PC .phyre description is much simplier due the most procces already are part of yre graphic's driver.

So, phyre extension basicaly is a part of very complicated occlusion culling system.

For a DDS file u can actually cheat (Didnt tryed yet, but this Workflow should work). So dump a dds with a Untitled Project X from a memory, edit it, and then with that Asset tool, convert it in .phyre. This should work for a textures that didnt attached for a 3D models. Like backgrounds sprites etc

Some more: 
[http://www114.zippyshare.com/v/ixhAh6Rf/file.html](http://www114.zippyshare.com/v/ixhAh6Rf/file.html)
This is how engine read a dds.phyre format
## Post #38
- Username: dtester1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 13, 2016 1:16 pm
- Post datetime: 2017-01-30T04:23:49+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Not sure if there's still any interest in getting out the models for this game on PC, but I made a python script that can extract both the character meshes as objs as well as the DDS textures. I haven't managed to figure out the exact format of these phyre files, so instead the script searches for the faces, vertices, UV maps, and normals by looking for certain markers. While this isn't absolutely foolproof, it's now robust enough to process every character mesh in FFX/FFX-2 without complaining. I haven't looked at every single mesh or texture to verify it, but for every file I have checked, it works correctly (including all the main character low and high poly meshes). 

The main script itself is phyre.py. You'll need python 3 to run it (I ran it on 3.5). The basics to run it look like:

```
extractMesh(r'/path/to/file.dae.phyre', r'outputfile.obj')
extractDDS(r'/path/to/file.dds.phyre', r'outputfile.dds')

```


That's it. There are some additional keyword arguments you can supply, but they are debugging tools for the most part. The only one that might be of interest is includeNormals for extractMesh(). By default it doesn't export the normals since they're unnecessary, but if you want them just add includeNormals=True to extractMesh().

I've also included my two test wrapper scripts. test_extraction.py is just a simple wrapper for extracting a single model. grab_meshes.py will extract all the models in the chr folder for both games. It'll create about 2GB of data and create some log files from the output, and it takes a couple minutes to run. For both scripts, you'll need to change ffxBaseDir and ffx2BaseDir to your install location. They'll both dump everything into the current working directory. 

There are a number of files that it can't process, but these don't appear to have any actual mesh data in them anyway. For FFX the files are c051, k002, k004, k007, k014, k015, k017, k201, k212, k214, k302, k303, k403 and k999. For FFX-2 they're k015, k201, k303, k403, and k999. The script will also give a warning for a random NPC (n174 in FFX, n119 in FFX-2) about the UV maps being out of bounds, but it's for a single tri, and that's actually how it's defined in the .dae.phyre file. The script will still process the file with the warning.

Finally, some caveats. This script is almost certainly only gonna work on the PC port of FFX/FFX-2 HD Remaster. It will definitely fail for the PS3 files due to the difference in endianness, and I'd be shocked if it worked on the PS4 version. I made it specifically for character meshes, and I haven't tested it out on anything outside of chr/. Finally, this is good for extracting meshes only. You're still SOL if you want to modify the meshes for in-game use.
[ffx_mesh_extractor.zip](https://xentaxbackup.github.io/file/12343_ffx_mesh_extractor.zip)
## Post #39
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-30T08:02:32+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

dtester1, thanks for this! Great work
## Post #40
- Username: CasualCrash
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 05, 2017 6:20 pm
- Post datetime: 2017-02-05T10:26:30+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Hi all! We translated Final Fantasy X in word documents. Now we want to put the text into the game. Can someone help us? With this extractor is it possible?
## Post #41
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2017-02-09T20:47:45+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Thanks for the work but converting this into a static obj will make us lose bones and other stuff right?
isn't there a way to convert this into collada?
## Post #42
- Username: dtester1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 13, 2016 1:16 pm
- Post datetime: 2017-02-10T08:13:44+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

You could convert it back to COLLADA if you knew the complete file structure. I'm not aware of any tools that can do that though, or else I wouldn't have made my scripts! As for getting bones and other data, I'm not familiar with how they are stored so I wouldn't know what to look for. I really just made the scripts to avoid having to manually create obj files using hex2obj for everything. 

There is extra data associated with the vertices that would be easy to extract, but I don't know what it is. After the faces are defined, the rest of the file is a stream of the vertex data, ordered by each submesh. For each submesh with N vertices, the first 3*N floats are the vertex coordinates, the next 3*N floats are the normals, and the next 2*N floats are the UV coordinates. After that, there are x*N floats, but x isn't constant between files, or even always between submeshes within a file. I imagine at least some of this is vertex skinning data, but I don't know what else it may be. 

If someone with more knowledge of skeletons and vertex skinning would like to extend my scripts, they are of course welcome to.
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-07T08:12:58+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Tool successfully converted all 872 skeletal and 409 level files from FFX remaster. There were about 5 very small files containing only cameras, which i hope is not needed.

Proceeding to FFX2. [viewtopic.php?p=130412#p130412](http://forum.xentax.com/viewtopic.php?p=130412#p130412)
## Post #44
- Username: Aelthien
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 19, 2017 3:48 pm
- Post datetime: 2017-06-21T02:50:08+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Can someone please explain how to get any of this to work?
## Post #45
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2017-06-24T15:26:08+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Just drag and drop the files into the program
## Post #46
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2018-03-17T17:44:42+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

---------------------------
Noesis Python Error
---------------------------
Traceback (most recent call last):
  File "D:\modding\tools\noesis\plugins\python\test_extraction.py", line 4, in <module>
    importlib.reload(phyre)
AttributeError: 'module' object has no attribute 'reload'

---------------------------
OK   
---------------------------



What that mean?
Running the latest version of noesis.
## Post #47
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-17T20:08:28+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

dtester1's scripts are not for Noesis, they are standalone python scripts.   
[viewtopic.php?p=126978#p126978](http://forum.xentax.com/viewtopic.php?p=126978#p126978)

> Reply from dtester1
>
> The main script itself is phyre.py. You'll need python 3 to run it (I ran it on 3.5). The basics to run it look like:
Code: Select allfrom phyre import extractMesh, extractDDS
extractMesh(r'/path/to/file.dae.phyre', r'outputfile.obj')
extractDDS(r'/path/to/file.dds.phyre', r'outputfile.dds')
## Post #48
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2018-03-19T23:24:16+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

oh ok, I was drunk and didn't read the part about needing python 3.
## Post #49
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2018-06-19T03:19:59+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

How do I view model animations and textures? Just drop the plugin into noesis plugin folder, then drop the files?

> 
Detected file type: Phyre
version: -133496832
version not supported: -133496832

Why cant I view the file in noesis?
## Post #50
- Username: Ambrellich
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 29, 2011 7:33 pm
- Post datetime: 2021-05-17T20:53:37+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Hey guys!
Just in case you missed tool that allow to extract FFX / FFX-2 models with skeleton, I would like to repost it here.

Just drag and drop name.dae.phyre file into tool and you will get extracted model in Noesis friendly format.
Note: tool does not extract textures, so use another tool posted previously in this topic.

Stay safe! Cheers!
[ffx.7z](https://xentaxbackup.github.io/file/20151_ffx.7z)
## Post #51
- Username: Kevin3DA
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 24, 2021 1:31 am
- Post datetime: 2021-08-23T17:39:52+00:00
- Post Title: Re: Final Fantasy X/X-2 HD Remaster

Hello all I'm new here so I apologize if requests are not allowed here. 
I'm a VR enthusiast and like to see ripped game worlds in VR. 

Would anyone here be willing to share some FFX maps with me that they have compiled? 
I'd need the material data for textures and such if possible to be setup in Unity. 
I only have exp ripping from Vagrant Story but I really want to see some FFX maps in VRchat. 
I was considering making the animation of the Zanarkand Blitzball stadium startup sequence in VR.
