## Post #1
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-06-28T19:33:49+00:00
- Post Title: The Technomancer - from .spk to .fbx

hey there,

as a huge fan of cyberpunk/scifi themes, sets and models, i'd love to see if we can get the model
files out of this game. the content looks gorgeous and would be perfect for Fan-Art. 
if some skilled person wants to take a look at the (yet packed) .spk files,
that'd be nice.
here's a few sample files:

[http://www.mediafire.com/download/fr6l1u61ga2rb26](http://www.mediafire.com/download/fr6l1u61ga2rb26)

developed by "Spiders" (Mars: War Logs, Bound by Flame), published by "Focus Home Interactive".
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-06-29T15:09:55+00:00
- Post Title: The Technomancer - from .spk to .fbx

Hi
Files from [http://www.mediafire.com/download/fr6l1u61ga2rb26](http://www.mediafire.com/download/fr6l1u61ga2rb26) have not skinned models, i think, only some terrain and collision meshes. 
Please try [viewtopic.php?f=16&t=12473](http://forum.xentax.com/viewtopic.php?f=16&t=12473) on others *.pkg
All files can unpack with 7z and check for characters.
## Post #3
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-06-29T17:44:39+00:00
- Post Title: The Technomancer - from .spk to .fbx

it can indeed simply be unpacked with 7zip. now i feel stupid.   

okay, i tested "Blender249[PSSG][pssg][gz][pgz][2015-01-10]" on mesh files (.pgz).
no errors so far. even rigging works. the only thing that doesn't seem to work, is textures.
if you want to have a look, i would really appreciate it. 
included texture files, along with a few meshes. 
even few hair meshes/textures, for checking, if transparency works in the end.

[TTM_Extracted_Sample_Files.7z](http://www.file-upload.net/download-11724167/TTM_Extracted_Sample_Files.7z.html)
## Post #4
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-06-29T21:04:48+00:00
- Post Title: The Technomancer - from .spk to .fbx

Some of PGZ files are gzip packed, unpack it with 7-zip and then use Ryder PSSG editor to export textures.
Hope it helps 

EDiT: O.K I find out that not all textures are 32-bit RGBA. Some "most" of them are BC1, BC3, BC4, BC5 formats. This means DXT1, DXT5, ATI1, ATI2.
Ryder PSSG editor isn't capable to export them with correct DDS header, so you must edit DDS header manualy. But it's not a big deal. You must only add those compression headers starting at 84 bytes of DDS header. Just HEX job 

Samples of Dog.
Diffuse, Normal, AO
## Post #5
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-06-29T21:37:57+00:00
- Post Title: The Technomancer - from .spk to .fbx

thank you for the information.
but it's all chinese and gibberish to me. i'm just a modder/artist.
i have to rely on the charitableness of the people with the appropriate knowledge for such stuff.

Edit: good work at the textures. is there maybe another way to make the textures "readable", then using a hex-editor?
## Post #6
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-06-30T13:23:15+00:00
- Post Title: The Technomancer - from .spk to .fbx

Send me filelist of textures which you want to convert. Or just sub-folders.
Hey where you put the content of Blender249[PSSG][pssg][gz][pgz][2015-01-10] folder in Blender 2.49?

EDiT: I finally figured it out how the hell import things into the blender and how it works. Now I will see what i can do with texturing.
## Post #7
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-07-01T15:01:10+00:00
- Post Title: The Technomancer - from .spk to .fbx

> Reply from GRiNDERKILLER
>
> Send me filelist of textures which you want to convert. Or just sub-folders.

thank you for the offer but wouldn't it be better if we had an .exe + a .bat file for anyone, 
rather then transferring GB of data around?
not sure how much work it is to write a texture converter though, even if it has only one function.
## Post #8
- Username: mtakerkart
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 22, 2016 5:01 am
- Post datetime: 2016-07-21T21:07:23+00:00
- Post Title: The Technomancer - from .spk to .fbx

Hi all , if someone can share the characters and monsters rigged, it will be very cool. I can give donations for the work. Thanks a lot.
It could be fbx, blend,collada,maya,max....
## Post #9
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-07-24T13:24:40+00:00
- Post Title: The Technomancer - from .spk to .fbx

> Reply from mtakerkart
>
> Hi all , if someone can share the characters and monsters rigged, it will be very cool. I can give donations for the work. Thanks a lot.
It could be fbx, blend,collada,maya,max....

You know how to get the textures from the game?
## Post #10
- Username: mtakerkart
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 22, 2016 5:01 am
- Post datetime: 2016-07-24T13:49:15+00:00
- Post Title: The Technomancer - from .spk to .fbx

You know how to get the textures from the game?[/quote]

No. My request is for rigged mesh with textures but whatever the textures format...
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-24T14:17:35+00:00
- Post Title: The Technomancer - from .spk to .fbx

Mtakerkart, maybe I can help, do you have the game?
## Post #12
- Username: mtakerkart
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 22, 2016 5:01 am
- Post datetime: 2016-07-24T14:29:05+00:00
- Post Title: The Technomancer - from .spk to .fbx

@Zaramot

Not but I can send you donation if you want to buy it  Or is your help to show how get models from game ?
Let me know. Just to confirm it's clearly not for buisness task , I'm an Hobbyest making machinima with game characters for fun.
Thank for your help Zaramot
## Post #13
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2016-07-24T14:32:19+00:00
- Post Title: The Technomancer - from .spk to .fbx

> Reply from zaramot
>
> Mtakerkart, maybe I can help, do you have the game?
HI zaramot，My friend you can download this file, BT file
[The.Technomancer-CODEX.zip](https://xentaxbackup.github.io/file/11358_The.Technomancer-CODEX.zip)
## Post #14
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-12-11T12:45:38+00:00
- Post Title: The Technomancer - from .spk to .fbx

hey there again, i really hate to necro that thread but it'd still be great to have a texture converter for it.

the sample files are still uploaded. 
after reading and messing around with header files i'm afraid i still have no clue how to do it myself.   
long story short, if anyone would be so kind to either explain how to do it in easy steps or have a simple converting method at hand, i'd appreciate it.
## Post #15
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-12-11T20:33:19+00:00
- Post Title: The Technomancer - from .spk to .fbx

Noesis plugin for Technomancer's textures, have fun xD 
How to use : extract texture with 7zip, then rename it's extenton to .tex, for bacth file renaming use any tool for batch renaming (Extension Changer smt) or do it one by one
[fmt_Technomancer_TEX.7z](https://xentaxbackup.github.io/file/12022_fmt_Technomancer_TEX.7z)
## Post #16
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-12-11T22:02:47+00:00
- Post Title: Re: The Technomancer - from .spk to .fbx

could you please check your script for errors?
any file inside any texture folder won't load.

i extracted different pgz files from inside texture folders, ending up with files without extension. 
i then added .tex to the file but Noesis still can't read it. 
any idea why that happens? i mean you explained it pretty good - there's not much one can do wrong here. still, it doesn't work.   
tried Noesis v4177, v4205 and v4206.

and loading the .pgz file directly doesn't work either. since your script is called ".pgz" Loader.
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-12-11T22:12:16+00:00
- Post Title: Re: The Technomancer - from .spk to .fbx

Don't remember exactly, though you might use 7zip twice xD Otherwise, attach one texture here I really forgot the process lol but I already gave this plugin to some guys and they got textures pretty easy.
## Post #18
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-12-11T22:17:57+00:00
- Post Title: Re: The Technomancer - from .spk to .fbx

thank you!
extracting twice doesn't work. can't do more then once.
okay, uploaded a random folder with a texture folder inside. by the look of the mesh, it's a freaky alien. ^^

[https://mega.nz/#!QUZXgC4C!eZlD_if1XbUi ... 9oZNJuo50Y](https://mega.nz/#!QUZXgC4C!eZlD_if1XbUiNdxjFNKhyJHD8wpiH4dtM9oZNJuo50Y)

okay, i see. extract and renaming the extracted thing back to pgz does work.
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-12-11T22:26:04+00:00
- Post Title: Re: The Technomancer - from .spk to .fbx

Lol I'm so sorry, you should rename extantion to .pgz not .tex xD Sorry guys, I was making plugin for other game, it's using .tex and said wrong xD
## Post #20
- Username: Adngel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 12, 2017 4:56 pm
- Post datetime: 2018-07-11T17:58:54+00:00
- Post Title: Re: The Technomancer - from .spk to .fbx

Hi there.

Could anyone guide me how do open the models in 3ds max (or blender).

I managed to get the textures with Zaramot's script, but I don't know how to open the mesh. (I don't care if it's rigged or not, I´m looking for hair wigs). 

Previously in this topic, it looks like that manage to open the models in Blender, with, maybe any kind of script to open the [pgz] format. But I can't find that script, (maybe it was in the link of the previous post, but the topic was removed), I could find a PKG importer for blender, but it doesn't work with these .pgz

I can't open the pgz that I extracted with 7zip, I neither can open the "sha" files that TheMask85 shared here:

> Reply from TheMask85
>
> thank you!
extracting twice doesn't work. can't do more then once.
okay, uploaded a random folder with a texture folder inside. by the look of the mesh, it's a freaky alien. ^^

https://mega.nz/#!QUZXgC4C!eZlD_if1XbUi ... 9oZNJuo50Y

okay, i see. extract and renaming the extracted thing back to pgz does work.

Anyone remembers how to open those .pgz models? O_ò

The hairs files I'm trying to open are in: ...Steam\SteamApps\common\The Technomancer\packs\datapc_initial.spk\hair\hum\
## Post #21
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2018-07-15T07:53:07+00:00
- Post Title: Re: The Technomancer - from .spk to .fbx

Hi guys, where can I find Blender249[PSSG][pssg][gz][pgz][2015-01-10]?
