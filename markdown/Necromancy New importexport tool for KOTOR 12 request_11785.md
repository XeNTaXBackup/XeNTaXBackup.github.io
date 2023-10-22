## Post #1
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2014-08-14T04:47:40+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

Is there anyone interested in taking a crack at coding a new compiler/decompiler for the MDL format used by Knights of the Old Republic (KOTOR) 1 and 2? There is an existing Perl-based tool, MDLOps, that can decompile and recompile the format, but it has always been fairly broken/buggy and it is limited in what it can do. MDLs that are decompiled into an ASCII format by MDLOps can be loaded with NWMax, a GMax/3DS Max import/export script for Neverwinter Nights (KOTOR 1/2 uses the Odyssey engine, a console variant of NWN's Aurora). I figure there is no need to reinvent the wheel as far as an import/export script goes, although if someone is that keen then by all means go ahead.

I know the games are fairly ancient now, hence the title, but there is still a small active modding community. A new, fully functional model tool would be a fantastic boost and enable a lot of stuff that has not been possible in the past. I'm trying to get some new custom models into the game, but for a number of them I just can't get MDLOps to compile them properly. They either cause the game to freeze/crash, or end up with wild distortions/mesh displacement. Hence this request.

If anyone is interested, here is a partial breakdown of the binary MDL format by the original MDLOps author cchargin - [https://home.comcast.net/~cchargin/kotor/mdl_info.html](https://home.comcast.net/~cchargin/kotor/mdl_info.html)

The original MDLOps tool is available here - [https://home.comcast.net/~cchargin/koto ... s0-5-0.zip](https://home.comcast.net/~cchargin/kotor/mdlops0-5-0.zip)

An updated version by JDNoa is available here - [http://www.starwarsknights.com/mtools/mdlops06a1.zip](http://www.starwarsknights.com/mtools/mdlops06a1.zip)

NWMax is available here - [http://neverwintervault.org/project/nwn ... ol/nwmax-8](http://neverwintervault.org/project/nwn1/other/tool/nwmax-8)

Mods: I know the rules forbid posting of model samples, but is it ok to supply them via PM/email on request? Otherwise I guess I am limited to hex snippets?
## Post #2
- Username: JohnBarleycorn
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 30, 2015 12:42 am
- Post datetime: 2015-06-18T23:17:40+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

*I AM* definitely interested. Alas, like you, time ago i was trying to import some models in Kotor (1&2) but there was some issue with the importers/exporters. There is people who did get his models into kotor, becouse i've seen lot of mods around, but i can't find a valid tutorial and working tools by now. That's really too bad, since even if those games may be "ancients" but they still rock. After all, their "heir" should be SWTOR which is not even worth considering...
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-11-21T16:48:00+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

Hi
Here is a blend for import meshes with vertex weights and animation.
It is important don't convert skin to trimesh from kotor tool.
Some mesh data after using KotorTool is corrupted. Missing vertex weights, rotation keys are totally wrong.

It requires installed Blender249 and Python 266 (all 32 bits).
How use:
-doubleclick Blender249.blend or copy all files to folder where is blender.exe and doubleclick Blender249.blend
-in Blender Text Window press alt+p and select ascii mdl file for meshes. 

If this file has animation data => importer extract animations into new folder with name ..._animfiles

-if you want to get right position of head, import body=>SELECT ARMATURE IN BLENDER 3D VIEW=>import head=>press PLAY ANIMATION for short time
-for animation=>SELECT ARMATURE IN BLENDER 3D VIEW=>press alt+p to import *.anim file from folder with name ..._animfiles
Animation works for me only with p_hk47 and p_zaalbar from KOTOR and some others models. Not to all.

Thanks to lyutor1945 for help , models and idea to make this script.

Script is not perfect . Please report bugs.

Animation example:
[http://www.mediafire.com/download/c9pia ... hk47.blend](http://www.mediafire.com/download/c9pia88ziffxwca/p_hk47.blend)
[Blender249[KOTOR][PC][mdl][2015-11-21].zip](https://xentaxbackup.github.io/file/10047_Blender249[KOTOR][PC][mdl][2015-11-21].zip)
## Post #4
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-12-01T11:31:01+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

Awesome work on the blender script!
There is another game from Bioware that seems to be the same format as KOTOR, which is Jade Empire. MDLOps doesn't work with it, and your script doesn't import anything. Is there any way to import these models too? I really would like them. I uploaded a few samples. I hope you can check these out.
[JadeEmpireMDLMDX.rar](https://xentaxbackup.github.io/file/10091_JadeEmpireMDLMDX.rar)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-02T00:24:45+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

*.mdx: first submesh only - it's a little bit tedious to get the second one:



n_dawn.jpg (44.72 KiB) Viewed 408 times
## Post #6
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-12-02T13:58:42+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

Nice! I am able to use hex2obj so I may try that way, but if there is any way to get a blender importer with bones and weights I would love that more.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-03T00:23:47+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

> Reply from TRDaz
>
> but if there is any way to get a blender importer with bones and weights I would love that more.guess Mariusz will care for that sooner or later if the model format is not too different.
There's .mdl and .mdx files in both games? Would be nice to have their structures compared.

(I'll see whether I can get the skeleton from the n_dawn_.mdl file.)
## Post #8
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-12-03T21:26:34+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

Yes I do believe both games have .mdx and .mdl, and there is a tool to compile them both into a different .mdl. I can try and get a .mdl and .mdx file from either of the KOTOR games (I have those games too).

EDIT: Here are 2 sets of mdl and mdx files from KOTOR 2. 
[https://www.sendspace.com/file/ggl1p1](https://www.sendspace.com/file/ggl1p1)
## Post #9
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-12-13T18:28:11+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

Any help with a script for those? I did find this post about the model format of the mdl's in Jade Empire if it's of any help: [http://www.lucasforums.com/showpost.php ... stcount=51](http://www.lucasforums.com/showpost.php?p=2318655&postcount=51)
## Post #10
- Username: Naionel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 03, 2016 3:46 am
- Post datetime: 2016-01-02T19:49:23+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

Hi guys,

I have to ask you about MDLops - I've tried to contact almost every, single forum i could, but all links have been expired. Could someone of you give me that file? I need it in order to get the models from the game (as you obviously know). Thanks for help!
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-02T20:56:45+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

I would just say go to StarWarsKnights.com but the site is down and has not had a snapshot since November 6th, fortunately the archived links still work. Get it while its hot! 

[http://web.archive.org/web/201511062222 ... /tools.php](http://web.archive.org/web/20151106222221/http://www.starwarsknights.com/tools.php)
## Post #12
- Username: Naionel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 03, 2016 3:46 am
- Post datetime: 2016-01-02T23:42:19+00:00
- Post Title: Necromancy: New import/export tool for KOTOR 1/2 request

Wow! That's amazing, thanks!
