## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-07T20:24:59+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

Tools for mesh extraction (with skeletons, fully rigged) for Frostbite games. Also can fix faces. Currently supported:
- Battlefield 1
- Battlefield 3
- Battlefield 4
- Battlefield Hardline
- Medal of Honor Warfighter
- Star Wars Battlefront 1
- Star Wars Battlefront 2
- Need for Speed Payback


Tools for more games posted later here: [viewtopic.php?p=147355#p147355](https://forum.xentax.com/viewtopic.php?p=147355#p147355)

Detailed tutorials by Crofty for everything you need to use the tools https://sta.sh/04jxcv9d9o0





Battlefield 1

This version will only work with characters using 3pantskeleton.ebx, it must be in the same dir (for both tools)

Fb_BF1_mesh.exe - mesh extractor

Usage: Fb_BF1_mesh <mesh> <chunk>

Fb_BF1_faces.exe - face fixing tool

Usage: drop VisualUnlock file onto the tool

This will make a small .SMD file with skeleton pose, which will fix the head. Apply transformation to bake it.

To apply transformation:
Load the head mesh, delete its skeleton, then import small SMD (it will actually be new skeleton with 2 poses: initial pose and corrected pose), and connect it to the head.

If you prefer to do it manually, you can edit model SMD file as text file. Open head SMD, scroll down to the "triangles" line, and delete all lines before it (this is the skeleton). Then insert small SMD in the beginning of the file.

Star Wars Battlefront 1, 2 - same tools, same usage,
skeleton name for SWBF1: humanmale.ebx
skeleton name for SWBF2: walrus_humanmale.ebx


------------------------------------
VisualUnlock files allows to automatically find the needed face asset inside the bank.
Every mesh in ANY frostbite game must have this unlock file. Can be called different. Usually located near mesh.ebx file. Example:
\ebx\characters\sp\ep3_mudandblood\townsend_ingame\sp_townsend_head_ingame_vu.ebx
\ebx\characters\mp\faces\unlocks\mp_faces_ako.ebx

Note that for some characters, these VisualUnlock files may contain asset links not in head, but in teeth, hair or beard instead. There are also some weird cases, where head links to incorrect asset, and the correct one is in hair.

Also in the same dir must be .assetbank file (or files) where you think assets for this face can be.
These are usually biggest bank for the level, located in "res\animations\antanimations\"
You can place ALL banks there, tool will check them all. This can be slow, because banks are HUGE.
Some scripts incorrectly name .assetbank files as ".ANT", in this case you need to rename them.
[fb_models_faces.rar](https://xentaxbackup.github.io/file/13636_fb_models_faces.rar)
## Post #2
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2017-10-07T21:05:25+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

Anyone know of any dumper scripts that dump Battlefront 2s beta?
## Post #3
- Username: Crageo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 15, 2016 2:28 pm
- Post datetime: 2017-10-07T21:25:00+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

I get this error when I try to do Maul even though I've got all of the AssetBanks in the same directory.

"Asset not found in asset banks (2)"
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-07T21:28:42+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

UFBE 0.2.1



Changes:

- case-insensitive search
- cloth and other "special" meshes (which require no chunks) will now have a number in its name, allowing mesh tool to convert it
[UFBE_0_2_1.rar](https://xentaxbackup.github.io/file/13633_UFBE_0_2_1.rar)
## Post #5
- Username: Crageo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 15, 2016 2:28 pm
- Post datetime: 2017-10-07T21:33:09+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

Yeah never mind I fixed it. Thanks for making the tools btw, you are a true legend.
## Post #6
- Username: Crageo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 15, 2016 2:28 pm
- Post datetime: 2017-10-07T21:35:13+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

Also another quick question, I can't seem to convert any of the textures with the batch converter. Do you have any other suggestions that I could use?
## Post #7
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-08T00:57:37+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

Is there a way to tell which chunk files go with the meshes and textures? I have been told a plugin for unwrap3d does this but i don't really want to buy that when i dont even use it.

Thanks so much for this either way!
## Post #8
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2017-10-08T02:11:56+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from o0Crofty0o
>
> Is there a way to tell which chunk files go with the meshes and textures? I have been told a plugin for unwrap3d does this but i don't really want to buy that when i dont even use it.

Thanks so much for this either way!
Use the demo
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-08T09:47:34+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Crageo
>
> Also another quick question, I can't seem to convert any of the textures with the batch converter. Do you have any other suggestions that I could use?

I will probably update texture converter. Or create something new. But not now.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-08T09:50:00+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from o0Crofty0o
>
> Is there a way to tell which chunk files go with the meshes and textures? I have been told a plugin for unwrap3d does this but i don't really want to buy that when i dont even use it.

Thanks so much for this either way!
The mesh and texture chunk IDs are near the beginning of EBX file if you open it with hex editor. There may be some tools to display IDs (or move the files), but I'm not familiar with them.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-08T09:50:58+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

Here are Python scripts for dumping the beta. 32-bit Python 2.7.3 recommended.

I was only able to fix Nikto and other "face skin" head variants by manually editing (splitting) VUR files. I can't find separate VUR file for those, they are merged together in one.

Also there are problems with troopers weights. I have no reports if anyone needs that fixed.


[swbf2b.rar](https://xentaxbackup.github.io/file/13415_swbf2b.rar)
## Post #12
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2017-10-08T13:39:57+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1
>
> Here are Python scripts for dumping the beta. 32-bit Python 2.7.3 recommended.

I was only able to fix Nikto and other "face skin" head variants by manually editing (splitting) VUR files. I can't find separate VUR file for those, they are merged together in one.

Also there are problems with troopers weights. I have no reports if anyone needs that fixed.

Can someone explain how to work the python scripts for dumping?
## Post #13
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-08T23:35:04+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

Thanks, i got it to work properly! No crashes or bugs happening with the mesh and face tools at the moment.

> Reply from lyutor1945
>
> 

Can someone explain how to work the python scripts for dumping?
Here's a small tutorial on that. Hope that helps!
[https://sta.sh/01s1dd3fmnpj](https://sta.sh/01s1dd3fmnpj)
## Post #14
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2017-10-09T00:09:46+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1
>
> 
The mesh and texture chunk IDs are near the beginning of EBX file if you open it with hex editor. There may be some tools to display IDs (or move the files), but I'm not familiar with them.

Is this the same with BF3, BF4 and Hardline? I tried looking and am not getting any ID (or that I can understand).
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-09T21:03:19+00:00
- Post Title: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from artworkplay
>
> Is this the same with BF3, BF4 and Hardline? I tried looking and am not getting any ID (or that I can understand).
yes its the same
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-10T20:16:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Python script to convert audio
[swbf2_sounds.rar](https://xentaxbackup.github.io/file/13430_swbf2_sounds.rar)
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-11T19:55:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Face-fixing SMDs for all 32 faces from SWBF2. I didn't check them all, but must be correct.

One strange thing: I checked all of the face animation assets, and they ALL present in VURs, except one! And this one also was in alpha, but no model corresponds to it. Must be some face they didn't put in the game yet.



[swbf2_fixed_faces.rar](https://xentaxbackup.github.io/file/13429_swbf2_fixed_faces.rar)
## Post #18
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2017-10-11T22:49:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

what plugin would i use to port the models into say max or something
plus how do i get textures?
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-12T15:45:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Audio script in the post above updated. Now it must get all sounds, including 9 ones which used more than 128 chunks.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-12T19:20:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Texture Batch converter
[Batch_Itexture_Converter_SWBF2.rar](https://xentaxbackup.github.io/file/13431_Batch_Itexture_Converter_SWBF2.rar)
## Post #21
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-12T19:41:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> Texture Batch converter

bug: it saves duplicates when the 'remove trailing zeroes' is checked. and i'd like to have a choice to output to another folder. build a copy of the folder tree, rather then converting into the extract folder.
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-12T19:52:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from episoder
>
> daemon1 wrote:Texture Batch converter

bug: it saves duplicates when the 'remove trailing zeroes' is checked. and i'd like to have a choice to output to another folder. build a copy of the folder tree, rather then converting into the extract folder.

Its not my tool, I just corrected it to support SWBF. I'm not going to improve it
## Post #23
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-12T20:24:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

okay. thx anyway.
## Post #24
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2017-10-13T01:05:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

ok every thing worked out great but the final issue is how do i open the mesh files to 3ds max
## Post #25
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-13T02:40:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from savinpvtmike
>
> ok every thing worked out great but the final issue is how do i open the mesh files to 3ds max

use an smd importer. max got wallworm. blender has sourcetools.

yeh. just refering to your facepunch post. i can't answer there anymore. they got a dumb mod and a stupid cat. /blah
## Post #26
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2017-10-13T02:51:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from episoder
>
> savinpvtmike wrote:ok every thing worked out great but the final issue is how do i open the mesh files to 3ds max

use an smd importer. max got wallworm. blender has sourcetools.

yeh. just refering to your facepunch post. i can't answer there anymore. they got a dumb mod and a stupid cat. /blah
i usually cant get answers there these days for anything
plus you are talking about the mesh files right or the smd files to fix faces
cus im trying to port some vehicles and other things
these type of files


ik it used to have a mesh file and a chunks file but that dosnt work anymore
## Post #27
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-13T03:19:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

have you read the 1st post howto use the tools? you gotta search the walrus_humanmale file, need the meshset files and find the chunk files. then put them all in the folder with the mesh tool. then use command prompt or a batch file with the command.

Fb_BF1_mesh <mesh> <chunk>

where mesh and chunk obviously gotta be replaced with the proper meshset and chunk file names.

to find the chunks you may have to use a hexeditor and read in the meshset files. there's the sha1 or whatever hash name in it. then copy those to the tool folder. then execute the mesh tool. that should give a sorta working smd.

if you wanna avoid all of this you gotta ask rancor022 on facepunch to give you the frosty version that has working export. nobody is allowed to share it, but he does it. i won't. still all good.
## Post #28
- Username: JohnMadden
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 23, 2016 8:45 am
- Post datetime: 2017-10-13T04:53:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Did I do something wrong with the converter? Keep getting this at the end:

Traceback (most recent call last):
File "Q:\Games\Origin\STAR WARS Battlefront II Multiplayer Beta\fb3decoder.py", line 576, in <module>
main()
File "Q:\Games\Origin\STAR WARS Battlefront II Multiplayer Beta\fb3decoder.py", line 566, in main
dbx=Dbx(f,relPath)
File "Q:\Games\Origin\STAR WARS Battlefront II Multiplayer Beta\fb3decoder.py", line 343, in __init__
inst=self.readComplex(instanceRepeater.complexInde x,f,True)
File "Q:\Games\Origin\STAR WARS Battlefront II Multiplayer Beta\fb3decoder.py", line 369, in readComplex
cmplx.fields.append(self.readField(fieldIndex,f))
File "Q:\Games\Origin\STAR WARS Battlefront II Multiplayer Beta\fb3decoder.py", line 422, in readField
(typ,length)=numDict[fieldDesc.type]
KeyError: 16685
## Post #29
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2017-10-13T11:20:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

ok so if i would open the mesh set file in hex editor what is the general area where i can find the correct chunk file name
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-13T15:11:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from savinpvtmike
>
> ok so if i would open the mesh set file in hex editor what is the general area where i can find the correct chunk file name

I will make a new version soon, that will automatically get the right chunk from "chunks" folder
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-13T15:12:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from JohnMadden
>
> Did I do something wrong with the converter?

No thats script problem. You have to wait until i post new version or just remove that problematic file from the folder.
## Post #32
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-13T15:54:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from savinpvtmike
>
> ok so if i would open the mesh set file in hex editor what is the general area where i can find the correct chunk file name

offset 0x114



> Reply from daemon1
>
> I will make a new version soon, that will automatically get the right chunk from "chunks" folder

if you redo the tool, can you think about redoing the export? i mean fix it to be complete or just usable. you could export all the meshes with all the uvs as seperate smd files. as a suggestion. and fix those broken meshes that export with it. this.



the quick test i did. most if not all of the other larger files even just break blender when importing. i waited a bit for another try but it just dies from those files. i'm not sure why. everything uptodate. and some of the data is obviously wrong. i got no clue where it chokes.

it works flawless for the heads. they only have one uv pair, but everyhting else...
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-13T17:16:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from episoder
>
> it works flawless for the heads. they only have one uv pair, but everyhting else...

I never had issues reported before this post of yours. All meshes I exported worked good. Including bodies, weapons, etc. But I never tested statics.
## Post #34
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2017-10-13T18:13:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> savinpvtmike wrote:ok so if i would open the mesh set file in hex editor what is the general area where i can find the correct chunk file name

I will make a new version soon, that will automatically get the right chunk from "chunks" folder 
Just when I recently figured out how to get the chunks in BF3 LOL.
One question though... BF3 uses veniceantske01.ebx and not 3pantskeleton.ebx, tried it and I get a "SystemOverflowException at FB_faceposer.FB_faceposer.Main<String[] args>" is there a workaround to avoid this?
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-13T19:08:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from artworkplay
>
> is there a workaround to avoid this?

No, I need to make separate tools for BF3,4 and HL. Each game is unique.
## Post #36
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2017-10-14T13:15:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> 

No, I need to make separate tools for BF3,4 and HL. Each game is unique.

Need any files to help you with this? I got BF3 unpacked just taking up a ton of space on my hd for some time now, I can pass you any file you might need before I get rid of it.
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-14T14:06:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

no, i have some examples from BF3. But right now i'm working on evil within 2. After that i'll return here
## Post #38
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2017-10-15T14:53:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

any one here use face punch here is the v3 thread
[https://facepunch.com/showthread.php?t= ... st52781885](https://facepunch.com/showthread.php?t=1582186&p=52781885#post52781885)
## Post #39
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-16T14:53:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from savinpvtmike
>
> any one here use face punch here is the v3 thread
https://facepunch.com/showthread.php?t= ... st52781885

you or somebody do me a favor. write a message to Tachyon. there. 

> the model doesn't extract correct. some of the parts have broken uvs. calm your tits and take the swbf falcon. i know the unreal model is a lil more accurate in some sections, but i won't release it if it's not complete. until i found how to fux those meshes it's dunzo

(i know i could register with another temporary account, but... i'm sick and tired of this throwaway account crap. and it's obvious that it's me responding. insta kill. pointless. i dunno if unknowing kidiots are just snitching to this mod-bots or just sgt doom or he thinks he's supercool bagging me for that cat. both stupid reasons. you can't change stupid. never.)

have a nice day.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-21T16:48:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

First post updated. Lots of improvements in SWBF2 mesh tools!

IMPORTANT: tool usage changed
Now you only need 1 parameter: meshset name, or just drag the meshset onto the tool. Chunk will be found automatically:

Chunk auto search
The tool will try to find the chunk it needs:
- in the current folder
- in the "chunks" subfolder
- in the directory structure created by dumper script. So for example if you just drop some meshset from "bundles\res" onto the tool, it will find it.
- if it still can't find the chunk, you'll get a message with chunk ID needed

Fixed static meshes
Statics now can be exported. They will still have skeletons, ignore them

Physics bones
Special physics bones will be created and mesh will be weighted to them. Manual bones adjusting may be required for them to work.

XNALara ascii format export with multi-UVs
If you need it with proper rotated bones, import SMD skeleton and connect it to model.

Skeleton read from EXE dir, not current dir
So you can use the tool from any folder, no need to put it next to the meshset file

Skeleton name parameter
For custom skeletons you can run:
Fb_SWBF2_mesh <meshset> <skeleton>
If no skeleton parameter provided, it will expect the default walrus_humanmale.ebx

Cloth meshes
Cloth meshes usually have no chunks. They have data inside of meshset itself. Now they are supported. Important note: the original dumped long name is required to detect the raw data position in the file, so don't rename the file.
## Post #41
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-28T15:40:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Tools for:
- Battlefield 3
- Battlefield 4
- Battlefield Hardline (same tool as Battlefield 4)
- Medal of Honor Warfighter

With all the newest options (from previous post) and a new face-fixing style for old games:
Since in old games face-fixing assets have proper names, usage is very simple:
Just run the face tool in the folder where you have assetbanks and corresponding skeleton file.
It will find and extract all face-fixing SMDs.
[fb_mohwf_bf34hl.rar](https://xentaxbackup.github.io/file/13500_fb_mohwf_bf34hl.rar)
## Post #42
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2017-10-29T14:54:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hi daemon1, I'm trying the BF3 tool out, I have the chunk, mesh, ebx and skeleton in one directory and am able to get the smd for body and head meshes but can't seem to make the face exe work. When you say "assetbank" are you referring to the mesh .ebx file?
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-29T15:51:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from artworkplay
>
> Hi daemon1, I'm trying the BF3 tool out, I have the chunk, mesh, ebx and skeleton in one directory and am able to get the smd for body and head meshes but can't seem to make the face exe work. When you say "assetbank" are you referring to the mesh .ebx file?

No. I'm referring to ANT animations assetbanks, as stated in the first post here.
Example for BF3: animations\antanimations\b_faceposer_sp_campo.assetbank
But I already posted all SMDs for all heads. You don't have to run face exe.

Also, you don't have to have the chunk, mesh, ebx and skeleton in one directory anymore.
You don't need ebx at all and you never needed that.
Chunk auto-finder will find the chunk for you. As described above in previous posts.
## Post #44
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-07T18:52:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Is there a way to convert these new EBX files in to readable text like the other games?
The usual script that is around here in the forum does not work, needs updated to support the new games.
## Post #45
- Username: ClubOn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 05, 2016 1:26 am
- Post datetime: 2017-11-14T21:13:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

delete
## Post #46
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-14T23:07:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from ClubOn
>
> Just install my pre-order copy and try to modified the Deamon dump script for the beta
But it fail. If you have any suggestion...
Uninstall your Python software and make sure you do a clean install of it using Python 2.7.3 32-bit
Then check if you have the EXACT location where the game is located, just copy/paste from the window explorer page where the exe is.
double check for the cas.cat location, but from the looks of it you need to do a clean install for Python.

cheers
## Post #47
- Username: ClubOn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 05, 2016 1:26 am
- Post datetime: 2017-11-15T13:28:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> ClubOn wrote:Just install my pre-order copy and try to modified the Deamon dump script for the beta
But it fail. If you have any suggestion...
Uninstall your Python software and make sure you do a clean install of it using Python 2.7.3 32-bit
Then check if you have the EXACT location where the game is located, just copy/paste from the window explorer page where the exe is.
double check for the cas.cat location, but from the looks of it you need to do a clean install for Python.

cheers

Effectively with Python 32bit it launch but still doesnt extract... I've got the "Chunk file not found" all the time... I will wait Deamon release a new script cause I'm really not an expert in this
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-17T18:32:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I've just made a ZSTD wrapper for SWBF2 scrtipt to work with full game. As soon as someone who has the game (and not only few files like I do) will test it, it will be published here.

After that, everyone will be able to use my model/texture/facefixing tools as before.

To fix faces which were not in beta, I need their files.
## Post #49
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-17T20:01:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

If you don't have someone to test it already, i have the full game and could do it. Either way, can't wait for this!
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-17T20:23:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

ok this is the current state of testing

32-bit python 2.7.3  as usual
and you should change directories as usual

probably will dump most, if not all files
## Post #51
- Username: Crageo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 15, 2016 2:28 pm
- Post datetime: 2017-11-17T21:26:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I can't get anything working, i just get this 
"abilities.toc
Error executing fb_zstd.
C:\Program Files (x86)\Origin Games\STAR WARS Battlefront II\Data\Win32\installation\initialexperience\cas_02.cas 509851537 40 E:\swbf2full_dump/bundles/res/fx/cinematics/textures/flares/t_cin_flare2x4_02_d f881310af9f6953b 02000000886f08960000000000000000.AtlasTexture"

[https://gyazo.com/cfda25e2e9d5dce77db16f81502710a7](https://gyazo.com/cfda25e2e9d5dce77db16f81502710a7)
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-17T21:37:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

maybe its access rights. If not, check folder names.
## Post #53
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-17T21:47:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I get the same error, even with the new version. I turned anti virus and anything else that could prevent the exe from running off, and also set it to be run as admin. Folder names are these: [https://cdn.pbrd.co/images/GU7uYtA.png](https://cdn.pbrd.co/images/GU7uYtA.png)
Only added one cat directory for now but i doubt that's the problem.
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-17T21:55:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I dont think you can set it to run as admin when its called from python. Anyway i still think its about access rights. Thy putting a few files into your normal drive (not origin folder) and run it there.
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-17T22:15:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

also python sometimes messing up folder names with some special characters. Anyway, one user was able to run it already. So it must be just some naming/access problem. Usual for python scripts.
## Post #56
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-17T22:16:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Yeah really seemed to be about being in origin folder. Put it elsewhere and it works now. Thanks a lot!
## Post #57
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-11-17T23:44:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

yeh. a full dump? i'm not interested. frosty editor and mod should be upgraded to allow selective extraction and maybe mod it to make this a good game. you know it's flawed.

and... somebody shoot the moderators or garry himself on facepunch. this numb box is terrible.  i don't get why i'm blocked from the modelling forum behind a stupid 'we only do gmail accounts' (which i can't register with a new mobile crap). i'd still like responding to casual support question that i know the answers for, but... i can't.

it all sux. maybe i should just leave.
## Post #58
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-18T00:34:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> maybe its access rights. Try this version. If not, check folder names.
Tried first version on the updated full game script as you mentioned, for NFS Payback, but I had to delete the .exe and the .dll you made for the SWBF2 game (otherwise the .exe you made would crash instantly, since its made for SWBF obviously) and I used the LZ77.dll and also to enable it in the script, after more than 2h of extraction an error popped out but I could not save it to post it here as python crashed.

There is a newly patched update for the NFSP game and wanted to try the script but no real success any possibility to make a version compatible please?
What files you need so I can upload for testing?

btw the script that extracts but shows error mid way, looks like this with the following modified lines by me:

```
targetDirectory = r"E:\3D Assets Game Geometry\NFSP_dump"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
tocRoot  = r"patch\win32" #patched and xpack files FIRST
tocRoot = r"data\win32"   #unpatched vanilla files SECOND
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
catPath        = r"Data\Win32\configurations\streaminginstallpackage\cas.cat" 
updateCatPath  = r"Patch\Win32\configurations\streaminginstallpackage\cas.cat"

catPath2       = r"Data\Win32\configurations\superbundleinstallpackage\cas.cat"
updateCatPath2 = r"Patch\Win32\configurations\superbundleinstallpackage\cas.cat"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
LZ77 = cdll.LoadLibrary("LZ77")
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
try: readCat(cat, catPath2)
except: print "Patched cat not found."

if "tocRoot" in locals():  dumpRoot(tocRoot)
if "tocRoot2" in locals(): dumpRoot(tocRoot2)
```


If I still try the first script made for SWBF2 beta regardless of modification for NFSP it will not read and extract the patched cas/cat from update folder, keeps saying "Patched cat not found."
## Post #59
- Username: JohnMadden
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 23, 2016 8:45 am
- Post datetime: 2017-11-18T08:55:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Getting the Chunk not found problem. All directories are set to the correct places.
## Post #60
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-18T09:23:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I let it extract until it was done and it resulted in about 15gb extracted files out of ~50 that the game is. Most characters didn't extract (their folders are there but empty). The files that did extract work fine though so i'm not sure what goes wrong. 
I get "Chunk not found" on a lot of entries too, while the folders are set properly.

If it helps i could provide more game files.
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-18T10:47:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from o0Crofty0o
>
> If it helps i could provide more game files.

Can you provide your script after you've set your folders?
## Post #62
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-18T12:18:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> o0Crofty0o wrote:If it helps i could provide more game files.

Can you provide your script after you've set your folders?
Sure, here: [https://cdn.pbrd.co/images/GUddmZD.bmp](https://cdn.pbrd.co/images/GUddmZD.bmp)
## Post #63
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-18T13:04:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

without files i can't say what's wrong

Can you give me example of character (its filename) which didnt dump?

p.s. also good if you can tell me which SB file its in
## Post #64
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-18T14:08:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Examples for character parts would be
bundles\res\characters\heads\heads_kylo (only one texture extracts 't_hair_kylo_02_ns 15c2bb9415242877 0d000000010000000000000000000000.Texture')
bundles\res\characters\hero\rey\rey_01\
bundles\res\characters\hero\rey\rey_02\  (these are all entirely empty)
bundles\res\characters\hero\rey\rey_03\

I'm not sure how to tell which .sb files they are in, but almost all .toc files display thousands of 'Chunk not found.' errors in the python log.
This is the full list of .toc files: [https://jpst.it/17E95](https://jpst.it/17E95)
[They are also here](https://drive.google.com/file/d/12PL0QAcEaPeOTr8ZF9nzNo3hKthBSjLh/view?usp=sharing) if you need them or don't have all of them.
Only chunks0.toc, frontend.toc and the localisation ones extract without any error. I suppose the missing character things are in characters.toc.
## Post #65
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-18T14:28:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

weird. Other people were able to export Rey file with all her files.

can you send your whole script on pastebin?
## Post #66
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-18T15:02:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hmm i don't know what's going wrong then... 
Here's the script [https://pastebin.com/E7FQMZ5B](https://pastebin.com/E7FQMZ5B)
## Post #67
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-18T16:30:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Now its all clear. you dont have to just list CAT names, you need to read them all too.
Here, near the end of a script:

```
try: readCat(cat, catPath)
except: print "Unpatched cat not found."
try: readCat(cat, catPath2)
except: print "Unpatched cat2 not found."
...
try: readCat(cat, catPath8)
except: print "Unpatched cat8 not found."
```
## Post #68
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-18T18:25:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Oh my sorry for the trouble, that fixed it. Thanks so much!
## Post #69
- Username: JohnMadden
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 23, 2016 8:45 am
- Post datetime: 2017-11-18T20:50:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Tried the new version of the dumper, now it's saying:

Unpatched cat3 not found.
Unpatched cat4 not found.
Unpatched cat5 not found.
Unpatched cat6 not found.
Unpatched cat7 not found.
Unpatched cat8 not found.
abilities.toc

Despite, all the paths for the cat files are correct.

Currently reading thread now, maybe my stuff got answered.
## Post #70
- Username: DarthPyro52
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 23, 2017 3:53 pm
- Post datetime: 2017-11-18T23:16:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

#catPath       = r"Data\Win32\installation\space"
#catPath2   = r"Data\Win32\installation\initialexperience" 

catPath       = r"Data\Win32\installation\initialexperience\cas.cat"
updateCatPath = r"Patch\Win32\installation\initialexperience\cas.cat"

---those are the modified lines I used, which extracted all 59GB of files. "catPath" and "updateCatPath" need to be changed for every single cat path; for instance, if you wanted to extract the cat files for the "space" folder, you would change it to:

catPath       = r"Data\Win32\installation\space\cas.cat"
updateCatPath = r"Patch\Win32\installation\space\cas.cat"

---delete the "catPath / catPath2" lines, or add a # in front of them as they appear to be useless, and only caused "no chunk found" errors for me.
## Post #71
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-18T23:53:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from JohnMadden
>
> Tried the new version of the dumper, now it's saying:

Unpatched cat3 not found.
Unpatched cat4 not found.
(...)

Additionally to what you already did, search for 

```
for path in "catPath", "catPath2", "tocRoot", "tocRoot2":
```

and replace it with 

```
for path in "catPath", "catPath2", "catPath3", "catPath4", "catPath5", "catPath6", "catPath7", "catPath8", "tocRoot", "tocRoot2":
```
## Post #72
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-19T10:44:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from o0Crofty0o
>
> 
Additionally to what you already did, search for 
Code: Select all#make the paths absolute and normalize the slashes
for path in "catPath", "catPath2", "tocRoot", "tocRoot2":
and replace it with

Added to the script
## Post #73
- Username: dio3182
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 11, 2016 4:37 am
- Post datetime: 2017-11-19T13:36:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Sorry if it's a dumb question, but how do I use swbf2full? Do I just drop the bf2 exe to fb_zstd.exe?
## Post #74
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-19T21:21:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from dio3182
>
> Sorry if it's a dumb question, but how do I use swbf2full? Do I just drop the bf2 exe to fb_zstd.exe?

no you need python to run the script. I'm not saying this is easy, but its a temporary solution
## Post #75
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-11-20T00:11:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

have you looked into how to decode the new version of ebx for audio/music? i can send samples from both battlefront 2 and nfs payback if needed.
## Post #76
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-20T06:14:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from OrangeC
>
> have you looked into how to decode the new version of ebx for audio/music? i can send samples from both battlefront 2 and nfs payback if needed.

i posted the scripts here is this thread
## Post #77
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-20T07:14:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

What files I need use for face fixing tool of BattleFront2 ( Fb_BF2_faces.exe ) ? meshset?
## Post #78
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-20T07:49:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> What files I need use for face fixing tool of BattleFront2 ( Fb_BF2_faces.exe ) ? meshset?

you need VUR, skeleton and 2 assetbanks: generic (230MB) and small one containing that face
## Post #79
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-20T08:02:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Thank you!
 Where can I find these files, and in what order should I specify them in console for the face fixer parameters?
If you can, write an example.
## Post #80
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-20T08:36:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> Thank you!
 Where can I find these files, and in what order should I specify them in console for the face fixer parameters?
If you can, write an example.

read first post in this thread. Its all written there
## Post #81
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-20T09:27:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

The latest dumper script.

There was a problem with some chunks leading to incorrect (broken) textures. Now with this version it must not happen.

If you already dumped whole game, delete only chunks folder, and re-dump. After that, all textures must convert properly.
[swbf2full.rar](https://xentaxbackup.github.io/file/13566_swbf2full.rar)
## Post #82
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2017-11-21T23:23:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Amazing work!  Has anyone looked at all 32 heads and put blender files of them somewhere?
## Post #83
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-11-22T02:32:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

@daemon

Unfortunatley the audio script you posted doesn't work with nfs payback. haven't tried battlefront 2 but im asuming it uses same ebx format.

It doesn't output anything. just lists the files that its working on in blue, but oither than that, notings being outputted. And i have ealayer3 and xa_decode correctly in the proper directories.
## Post #84
- Username: sin10001
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 16, 2016 2:17 pm
- Post datetime: 2017-11-22T03:57:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

1. Thank you, Daemon, for putting in such hard work on this - it's far more than what most do, but it's SO helpful (and awesome) to have such tools. You deserve lots of credit. 

2. BRB (script ran *very* slow first time, but after restart of pc it's faster?)
## Post #85
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-22T06:12:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from OrangeC
>
> @daemon

Unfortunatley the audio script you posted doesn't work with nfs payback. haven't tried battlefront 2 but im asuming it uses same ebx format.

It doesn't output anything. just lists the files that its working on in blue, but oither than that, notings being outputted. And i have ealayer3 and xa_decode correctly in the proper directories.
it was made specifically for battlefront 2 and its working with battlefront 2. I dont have  nfs payback
## Post #86
- Username: SciBott
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 18, 2016 3:44 pm
- Post datetime: 2017-11-22T23:59:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I seem to not understand how to use swbf2full.py. I installed the Python 2.7.3 x86 version, click open swbf2full.py, a cmd window flashes up, and closes. cms.pyc and noncms.pyc are made in the directory, not finding anything else done. Loading the exe included with the script opens a cmd window that immediately pops up the application has stopped responding dialog. Dragging any of the files onto the python.exe does the same. What am I missing?
## Post #87
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-11-23T01:24:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

i'm in no hurry, but you got a timeframe for future tool testing? @deamon1
## Post #88
- Username: sin10001
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 16, 2016 2:17 pm
- Post datetime: 2017-11-23T03:38:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from SciBott
>
> I seem to not understand how to use swbf2full.py. ...

Run python's "IDLE" (type it in your search bar for Win 10)
Click 'File' > 'Open' > select swbf2full.py
Edit the paths as necessary (props to Crofty: [https://sta.sh/01s1dd3fmnpj](https://sta.sh/01s1dd3fmnpj))
Hit F5 and patiently sleep/wait ...
## Post #89
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-23T16:28:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Sorry, I can not use your tools.
Let's take the step by step.
step one:
unpack the game files:

```
j: \ SWBF2u2 \ chunks \

```

step two:
prepare tools, copy skeletons

```
j: \ mesh tools \ Fb_BF1_mesh.exe
j: \ mesh tools \ Fb_SWBF_faces.exe
j: \ mesh tools \ Fb_SWBF_mesh.exe
j: \ mesh tools \ Fb_SWBF2_faces.exe
j: \ mesh tools \ Fb_SWBF2_mesh.exe
j: \ mesh tools \ walrus_humanmale.ebx
j: \ mesh tools \ walrus_humanmale_1p.ebx
j: \ mesh tools \ walrus_humanmale_1p_masterske.ebx
j: \ mesh tools \ walrus_humanmale_masterske.ebx

```

step three:
copy all * .assetbank of j:\SWBF2u2\bundles\res\animations\antanimations\ to the folder with "vur"

```
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\texture\
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\vur_hansolo_01_bpb\
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\a1_m0lib_ds02_s0200_gp_win32_antstate 0000000000000000.AssetBank
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\a1_m0lib_ds02_s0205_gp_win32_antstate 0000000000000000.AssetBank
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\a1_m0lib_ds02_s0207_gp_win32_antstate 0000000000000000.AssetBank
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\a1_m0lib_ds02_s0215_nis_win32_antstate 0000000000000000.AssetBank
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\a1_m0lib_ds02_s0300_gp_win32_antstate 0000000000000000.AssetBank
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\a1_m0lib_ds02_s0305_se_win32_antstate 0000000000000000.AssetBank
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\a1_m0lib_ds02_s0350_gp_win32_antstate 0000000000000000.AssetBank
....
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\yavin_01_win32_antstate 0000000000000000.AssetBank
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\yavin_012_win32_antstate 0000000000000000.AssetBank
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\vur_hansolo_01.ebx
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\vur_hansolo_01_bpb.ebx
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\hansolo_01.ebx
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\hansolo_01_class.ebx
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\hansolo_01_class_schematics.ebx
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\hansolo_01_jacket.ebx
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\hansolo_01_jacket_clothwrappingasset.ebx
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\hansolo_01_jacket_mesh.ebx
j:\SWBF2u2\bundles\ebx\characters\hero\hansolo\hansolo_01\hansolo_01_mesh.ebx

```


Step four: 
Drag and drop
j: \ SWBF2u2 \ bundles \ ebx \ characters \ hero \ hansolo \ hansolo_01 \ vur_hansolo_01.ebx
on
j: \ mesh tools \ Fb_SWBF2_faces.exe

getting an error

```
  Stopped working

Signature of the problem:
  Event name of the problem: CLR20r3
  Signature of problem 01: fb_swbf2_faces.exe
  Signature of the problem 02: 1.0.0.0
  Signature of the problem 03: 59d92e52
  Signature of problem 04: mscorlib
  Signature of the problem 05: 2.0.0.0
  Signature of the problem 06: 4ca2b851
  Signature of the problem 07: 349e
  Signature of problem 08: e1
  Signature of Problem 09: System.IO.FileNotFoundException
  OS version: 6.1.7601.2.1.0.256.1
  Language code: 1049

Read the privacy statement on the Internet:
  http://go.microsoft.com/fwlink/?linkid=104288&clcid=0x0419

If the privacy statement on the Internet is not available, check out its local version:
  C: \ Windows \ system32 \ en-US \ erofflps.txt
```


  What am I doing wrong?
## Post #90
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-23T16:45:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

copy all * .assetbank  to the folder with tool
## Post #91
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-23T16:54:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Ok thank you!
Now i have "Asset not found in asset banks (2)"
## Post #92
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-23T17:14:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

this means either you put not ALL assetbanks there, or its wrong VUR for his face
## Post #93
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-23T17:20:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Ok, thank you.

The message appears very quickly (1-2 seconds), and some assetbank are very small gamemodes_win32_antstate 0000000000000000 (13).AssetBank - 1 kb.
This is normal?

Have to wait for your pack or tool with a GUI - maybe more luck.
## Post #94
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-23T17:31:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> Have to wait for your pack or tool with a GUI - maybe more luck.

GUI tool will only dump files, not face fixing.

It looks like you're using the OLD face tool, made for alpha of the game. Get the new one.
## Post #95
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-23T17:56:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Link in first post of this theme?
## Post #96
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-23T18:05:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> Link in first post of this theme?
yes
## Post #97
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-23T18:34:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

All right, but for some reason it does not work for me.
Total 215 assetbank's, the total size is 876 MB (919,571,612 bytes)
## Post #98
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-23T18:37:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> All right, but for some reason it does not work for me.
Total 215 assetbank's, the total size is 876 MB (919,571,612 bytes)
2 banks should be enough. i'll check this later
## Post #99
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-23T18:40:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Ok thank you!
## Post #100
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-23T20:08:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Here it is, the first version of UFBE. 



I'll write some help for it soon, or maybe someone even make a tutorial.
Mostly its self-explanatory, but for now, most important notes:

1. this first version is only for SWBF2 full game, and not patch, so select DATA folder
2. no progress bar sorry
3. type something in edit box and press "FilteR" button to select what to dump
3. if you leave "filter" edit box empty, it will dump WHOLE game
4. you need to click "scan bundles" & "scan CAS/CAT" before dumping, but you only need to do this ONCE, after that, bundles & cas info will be hashed
[UFBE_swbf2only.rar](https://xentaxbackup.github.io/file/13583_UFBE_swbf2only.rar)
## Post #101
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-23T20:33:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Awesome! It's saying I have 16100 missing chunks though. When I dump, it works for maybe 10 seconds and crashes on me. I check the dump directory and there's definitely stuff there. Using your audio script, anything need changed other than the folder path? Python just states that the tools are loaded and nothing actually happens when I F5 it.
## Post #102
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-23T21:01:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

since the new tool now outputs chunks with short 16-letter names, i need to change model, texture and audio tools. I planned to rewrite them anyway. 

This is for example, new model tool. It will now support both long and short chunks.
[Fb_SWBF2_mesh.rar](https://xentaxbackup.github.io/file/13584_Fb_SWBF2_mesh.rar)
## Post #103
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-23T21:20:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Thank you! I tried to use it.
I get:

```
125922 EBX, 1582921 duplicates
35662 res, 213177 duplicates
175466 chunks, 590912 duplicates, 172621 unique chunks
334205 total.

Scanning CAS database ...
332966 entries, 29060 precache entries, 893905 duplicated entries.

checking chunks ...
16151 missing chunks.

Dumping files ...
528 files dumped seccessfully.
127 files failed because of chunk not found.

```


assetbank is not at all any.
## Post #104
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-23T21:40:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Note everyone, as i said, the tool is not supposed to run with patched assets yet, so

when selecting game folder, select DATA folder of the game, and not the root game folder.

Those who already did it, remove all extra files from tool folder, and run scans again.
There must be no missing chunks on the check

Patch support will be added later.
## Post #105
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-11-23T21:45:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

i gotta dump all before i run this? it does not extract chunks... right?

for clarity:

i used the main folder. latest patch (it's early trial, but patched). it found everything, but 16100 chunks missing. it extracts ebx and 'res' but no chunks. i tried just the data folder too, but same result.

filters tested "iden", "vader", "assault". i dunno if they are in the data or patch folder.
## Post #106
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-23T23:26:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from episoder
>
> i gotta dump all before i run this? it does not extract chunks... right?

for clarity:

i used the main folder. latest patch (it's early trial, but patched). it found everything, but 16100 chunks missing. it extracts ebx and 'res' but no chunks. i tried just the data folder too, but same result.

filters tested "iden", "vader", "assault". i dunno if they are in the data or patch folder.
I had to delete the program folder, re-extract, pick JUST the DATA folder, and then go through the process again. 0 chunks missing now. Just crashes on me each time.
## Post #107
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-24T03:35:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Here's a very ultra thorough tutorial about archive extraction using UFBE: [https://sta.sh/02dc32j9pq4](https://sta.sh/02dc32j9pq4) (3. to 7. is the main part)
I hope this is newbie proof, if not tell me and i will change stuff. There's no link references in that specific one because it will be part of this: [https://sta.sh/04jxcv9d9o0](https://sta.sh/04jxcv9d9o0) , a set of tutorials so really everyone should be able to extract stuff on their own and fix most common problems when using models.
## Post #108
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-24T06:36:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from kschade45
>
> Just crashes on me each time.

Whats the error message on the crash?
## Post #109
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-24T06:37:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from episoder
>
> i gotta dump all before i run this? it does not extract chunks... right?

No you can either dump all, or just files you need. Yes, it extracts chunks. Either all of them, or specific ones.
## Post #110
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-24T12:07:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> kschade45 wrote:Just crashes on me each time.

Whats the error message on the crash?
It doesn't give an error message, When trying to dump the full game after about 2 minutes it will stop responding and windows will close it. Worked fine when I only dumped ebx files. I'm running Windows 10 64 bit.
## Post #111
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-24T14:42:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

UFBE 0.2 released!

Changes:
- Support for: Battlefield 1, SWBF1, SWBF2 (alpha, beta and full game)
- chunks will have long lowercase names, so all previous tools will work
- fixed crash if some CAS files are missing
- added resource types for BF1

You need to delete all files from tool folder, otherwise it will crash.
[UFBE_0_2.rar](https://xentaxbackup.github.io/file/13590_UFBE_0_2.rar)
## Post #112
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-24T16:11:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Thank you!
Select game or game/data folder?
## Post #113
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-24T16:27:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> Thank you!
Select game or game/data folder?
yes, data. Patch is not supported yet
## Post #114
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-24T16:29:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from kschade45
>
> It doesn't give an error message, When trying to dump the full game after about 2 minutes it will stop responding and windows will close it. Worked fine when I only dumped ebx files. I'm running Windows 10 64 bit.

Hardware or antivirus problem probably. From the tool's point of view, EBX and chunks are the same, so it can't be any difference extracting them. Also other people were able to fully dump it. Check your system/application logs for errors.
## Post #115
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-24T18:20:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

A quick fix (same post above updated)

- chunks will have long lowercase names (so texture tool can find them)
- added resource types for BF1

Now I checked that all my previous mesh tools, texture tool, audio conversion script - all work OK.
## Post #116
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-24T18:51:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Understood with face_fix.
At me it turned out so (win7)
1. call the command line.
2. Use the cd command to go to the exe folder.
 call Fb_SWBF2_faces with the desired vur.
Example

```

```

3. Profit!
Otherwise I get "Asset not found in asset banks (2)" error.
May be a problem in determining the location of the exe and assetbank (how do you do this? GetModuleFileName () function?)?
Thanks again for the tools.
## Post #117
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-24T20:19:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
>  GetModuleFileName () function?)?.

no, i'm searching them in current folder. Which is supposed to be tool folder, if system will not substitute this for your working folder in your "users" folder
## Post #118
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-11-24T20:34:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Is it possible to convert an ebx file to txt in the newer games?
## Post #119
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-24T20:45:04+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from OrangeC
>
> Is it possible to convert an ebx file to txt in the newer games?

sure it is. I corrected ebx2txt for SWBF2. Other games may be different.
## Post #120
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-25T00:44:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> UFBE 0.2 released!

Changes:
- Support for: Battlefield 1, SWBF1, SWBF2 (alpha, beta and full game)
- chunks will have long lowercase names, so all previous tools will work
- fixed crash if some CAS files are missing
- added resource types for BF1

You need to delete all files from tool folder, otherwise it will crash.
Tool works great now, dumped the whole game with no issues. Still having issues with the audio extractor script. Loads the tools and nothing else happens. Is there anything special I need to do or look for?
## Post #121
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-25T01:16:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Tried the script on the Python full game dump and got this error.
```
  File "E:\Kiennen\Games\EXTRACT\swbf2_sounds\fb3decoder.py", line 576, in <module>
    main()
  File "E:\Kiennen\Games\EXTRACT\swbf2_sounds\fb3decoder.py", line 566, in main
    dbx=Dbx(f,relPath)
  File "E:\Kiennen\Games\EXTRACT\swbf2_sounds\fb3decoder.py", line 343, in __init__
    inst=self.readComplex(instanceRepeater.complexIndex,f,True)
  File "E:\Kiennen\Games\EXTRACT\swbf2_sounds\fb3decoder.py", line 369, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "E:\Kiennen\Games\EXTRACT\swbf2_sounds\fb3decoder.py", line 422, in readField
    (typ,length)=numDict[fieldDesc.type]
KeyError: 16685

```
## Post #122
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-25T01:34:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from OrangeC
>
> Is it possible to convert an ebx file to txt in the newer games?
Did you managed to convert ebx2txt for NFS Payback? I still have no luck not even with audio conversion, tools/scripts for SWBF2beta or FULL do not work.
## Post #123
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-25T05:59:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

this is for NFS audio
[fb3audio_nfs.rar](https://xentaxbackup.github.io/file/13592_fb3audio_nfs.rar)
## Post #124
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-25T06:03:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from kschade45
>
> Still having issues with the audio extractor script. Loads the tools and nothing else happens. Is there anything special I need to do or look for?

No, audio script works like before and it extracts the audio. You need to set in/out paths, path to ealayer3.exe as is was in other games, and it should work.
## Post #125
- Username: Hornedal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 10, 2017 9:25 am
- Post datetime: 2017-11-25T13:41:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I used the NFS fb3decoder and it detected everytthing and ran down a list of all the ebx files but there were no audio files extracted...

Edit: this was for the SWBF2 dumps
## Post #126
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-25T13:50:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Hornedal
>
> I used the NFS fb3decoder and it detected everytthing and ran down a list of all the ebx files but there were no audio files extracted...

Edit: this was for the SWBF2 dumps

use SWBF2 decoder for SWBF2 dumps!
## Post #127
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-25T15:17:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I have all the paths set fine. (Using your tool to dump the whole game in folders)

```
dumpDirectory   = r"E:\Kiennen\Games\EXTRACT\SWBF2Dump"
#dumpDirectory   = r"H:\my projects\FrostByte\extracted_data"
targetDirectory = r"E:\Kiennen\Games\EXTRACT\swbf2sound"

#Download Zench's tool so the script can handle EALayer3.
ealayer3Path=r"E:\Kiennen\Games\EXTRACT\ealayer3-0.7.0-win32\ealayer3.exe"
```

Then it just loads the tools and ends, unless I'm not patient enough and something will start to happen in a little.

```
Type "copyright", "credits" or "license()" for more information.
>>> ================================ RESTART ================================
>>> 
XAS1 dll detected.
EASpeex dll not detected.
EALayer3 tool detected.
>>> 

```

Should I try on a different system maybe? My PC always seems to give me weird issues.
## Post #128
- Username: Hornedal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 10, 2017 9:25 am
- Post datetime: 2017-11-25T16:59:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> Hornedal wrote:I used the NFS fb3decoder and it detected everytthing and ran down a list of all the ebx files but there were no audio files extracted...

Edit: this was for the SWBF2 dumps

use SWBF2 decoder for SWBF2 dumps!
Where can I find it?
## Post #129
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-25T17:02:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Hornedal
>
> daemon1 wrote:Hornedal wrote:I used the NFS fb3decoder and it detected everytthing and ran down a list of all the ebx files but there were no audio files extracted...

Edit: this was for the SWBF2 dumps

use SWBF2 decoder for SWBF2 dumps!
Where can I find it?

first post here?
## Post #130
- Username: Hornedal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 10, 2017 9:25 am
- Post datetime: 2017-11-25T17:11:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Still having problems with the decoder. It reads in the EBX files but no sound files appear in the directory. Also got this error:

```
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 576, in <module>
    main()
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 566, in main
    dbx=Dbx(f,relPath)
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 343, in __init__
    inst=self.readComplex(instanceRepeater.complexIndex,f,True)
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 369, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 422, in readField
    (typ,length)=numDict[fieldDesc.type]
KeyError: 16685
```


Update: I manage to extract the lightsaber sound files by specifying the ebx directory to only lightsaber. I assume, error appears becasue not all chunks or ebx files has been extracted...
## Post #131
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-25T17:27:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Hornedal
>
> Still having problems with the decoder. It reads in the EBX files but no sound files appear in the directory. Also got this error:
Code: Select allTraceback (most recent call last):
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 576, in <module>
    main()
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 566, in main
    dbx=Dbx(f,relPath)
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 343, in __init__
    inst=self.readComplex(instanceRepeater.complexIndex,f,True)
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 369, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "H:\Dumpstuff\SWBF2\swbf2 audio converter\fb3decoder.py", line 422, in readField
    (typ,length)=numDict[fieldDesc.type]
KeyError: 16685

Update: I manage to extract the lightsaber sound files by specifying the ebx directory to only lightsaber. I assume, error appears becasue not all chunks or ebx files has been extracted...
no its because some EBX files you have there are NOT audio EBX, and i had no time to fix it.
just remove non-audio EBX
## Post #132
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-26T01:51:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> this is for NFS audio
Thank you, it works nicely, now only thing left is the ability to convert ebx2txt and we are all set hehe.
## Post #133
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-26T07:31:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> daemon1 wrote:this is for NFS audio
Thank you, it works nicely, now only thing left is the ability to convert ebx2txt and we are all set hehe.
hehe
[ebxtotext.rar](https://xentaxbackup.github.io/file/13596_ebxtotext.rar)
## Post #134
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-26T07:56:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> hehe
Thank you that was quick.
so far every line displays the follwong:

```
Unknown field type: 49709 File name: 
```

about 615 lines then this:

```
  File "D:\11-Game ReverseEngineering\NeedForSpeed_2016_UTILITIES\BF3_decoder\ebx2text_nfsp.py", line 422, in <module>
    main()
  File "D:\11-Game ReverseEngineering\NeedForSpeed_2016_UTILITIES\BF3_decoder\ebx2text_nfsp.py", line 45, in main
    createGuidTable()
  File "D:\11-Game ReverseEngineering\NeedForSpeed_2016_UTILITIES\BF3_decoder\ebx2text_nfsp.py", line 62, in createGuidTable
    dbx=Dbx(f,relPath)
  File "D:\11-Game ReverseEngineering\NeedForSpeed_2016_UTILITIES\BF3_decoder\ebx2text_nfsp.py", line 241, in __init__
    self.instances.append( (instanceGUID,self.readComplex(instanceRepeater.complexIndex,f,True)) )
  File "D:\11-Game ReverseEngineering\NeedForSpeed_2016_UTILITIES\BF3_decoder\ebx2text_nfsp.py", line 264, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "D:\11-Game ReverseEngineering\NeedForSpeed_2016_UTILITIES\BF3_decoder\ebx2text_nfsp.py", line 264, in readComplex
    cmplx.fields.append(self.readField(fieldIndex,f))
  File "D:\11-Game ReverseEngineering\NeedForSpeed_2016_UTILITIES\BF3_decoder\ebx2text_nfsp.py", line 271, in readField
    field=Field(fieldDesc,f.tell())
MemoryError
>>> 
```
## Post #135
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-26T08:29:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> daemon1 wrote:hehe
Thank you that was quick.
that was for swbf2

i never had time to correct that old script to properly parse types. maybe some day
## Post #136
- Username: GM000
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 10:02 pm
- Post datetime: 2017-11-26T12:58:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> UFBE 0.2 released!

Changes:
- Support for: Battlefield 1, SWBF1, SWBF2 (alpha, beta and full game)
- chunks will have long lowercase names, so all previous tools will work
- fixed crash if some CAS files are missing
- added resource types for BF1

You need to delete all files from tool folder, otherwise it will crash.

Sorry man, the tools are not working... In the selection window I can't double click BF2 or I didn't put the folders properly but i don't know what the problem is. It says dumping files,,, 0 files dumped succesfully and it just stays there. do you have any tutorials for Battlefront 2?
## Post #137
- Username: JohnMadden
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 23, 2016 8:45 am
- Post datetime: 2017-11-26T13:05:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Dumped BF2 with the new tool.

Now having problems converting the audio. Using the BF2 audio decoder on page 2.

Just stuck at :

>>> 
XAS1 dll detected.
EASpeex dll detected.
EALayer3 tool detected.
>>> 

And then nothing happens.
## Post #138
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-26T13:20:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from JohnMadden
>
> Dumped BF2 with the new tool.

Now having problems converting the audio. Using the BF2 audio decoder on page 2.

Just stuck at :

>>> 
XAS1 dll detected.
EASpeex dll detected.
EALayer3 tool detected.
>>> 

And then nothing happens.

the new tool is putting EBX into "bundles" folder, without "ebx" inside, as its how its supposed to be.
correct EBX path in the script
## Post #139
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2017-11-26T18:06:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> JohnMadden wrote:Dumped BF2 with the new tool.

Now having problems converting the audio. Using the BF2 audio decoder on page 2.

Just stuck at :

>>> 
XAS1 dll detected.
EASpeex dll detected.
EALayer3 tool detected.
>>> 

And then nothing happens.

the new tool is putting EBX into "bundles" folder, without "ebx" inside, as its how its supposed to be.
correct EBX path in the script

Still getting John's error of the script doing nothing even after fixing the ebx path
## Post #140
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2017-11-26T19:00:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from o0Crofty0o
>
> Here's a very ultra thorough tutorial about archive extraction using UFBE: https://sta.sh/02dc32j9pq4 (3. to 7. is the main part)
I hope this is newbie proof, if not tell me and i will change stuff. There's no link references in that specific one because it will be part of this: https://sta.sh/04jxcv9d9o0 , a set of tutorials so really everyone should be able to extract stuff on their own and fix most common problems when using models.

If you don't mind could you include a tutorial for converting audio files. Thanks in advance
## Post #141
- Username: halo08
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 26, 2017 3:58 pm
- Post datetime: 2017-11-26T19:26:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I'm trying to extract the audio files for Kylo Ren's lightsaber.

I run the script 'fb3decoder.py' from swbf2_sounds.rar to do this.

My script appears as follows:



Everything appears to be working OK when I use F5 to run the script:



But at the end of it, it just gives me a prompt and gives me no status.
Nothing happenes after this:



and as you can see, the folder remains empty, sadly 



Any ideas, or help would be appreciated.

Thank you.
## Post #142
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-26T19:40:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

are there chunks in chunks folder? with lowercase names?
## Post #143
- Username: halo08
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 26, 2017 3:58 pm
- Post datetime: 2017-11-26T20:51:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

There was no chunks folder.

I didn't extract the chunks, but I just started to extract all chunks, which I assume is going to be a while.
The filter doesn't quite work for chunks due to the names being pretty random.

Is there a better way to just extract the chunks that I need?
## Post #144
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-26T20:59:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from halo08
>
> There was no chunks folder.

I didn't extract the chunks, but I just started to extract all chunks, which I assume is going to be a while.
The filter doesn't quite work for chunks due to the names being pretty random.

Is there a better way to just extract the chunks that I need?
no for the moment
## Post #145
- Username: halo08
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 26, 2017 3:58 pm
- Post datetime: 2017-11-26T23:25:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Sweet, after extracting all the chunks from the game, I was able to successfully extract all the lightsaber sounds from the game.

Thanks for the advice daemon.
## Post #146
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2017-11-26T23:50:20+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from halo08
>
> Sweet, after extracting all the chunks from the game, I was able to successfully extract all the lightsaber sounds from the game.

Thanks for the advice daemon.

Do you mind sharing what you did ? I have extracted all the chunks yet when i run the script I get nothing in the output folder like you before.
## Post #147
- Username: JohnMadden
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 23, 2016 8:45 am
- Post datetime: 2017-11-27T00:21:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> JohnMadden wrote:Dumped BF2 with the new tool.

Now having problems converting the audio. Using the BF2 audio decoder on page 2.

Just stuck at :

>>> 
XAS1 dll detected.
EASpeex dll detected.
EALayer3 tool detected.
>>> 

And then nothing happens.

the new tool is putting EBX into "bundles" folder, without "ebx" inside, as its how its supposed to be.
correct EBX path in the script

Ah thanks, that did it.

Would just like to note that this dumper was far more complete than the previous. Several thousand more audio files were properly made. Mostly to do with the audio in the planets folder, some additional vehicle effects were added this time like the Resurgent SD.
## Post #148
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-27T04:30:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> 
that was for swbf2

i never had time to correct that old script to properly parse types. maybe some day
Understood, thx.
## Post #149
- Username: GM000
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 10:02 pm
- Post datetime: 2017-11-27T13:09:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

How can I convert the game files: .MeshSet and .Texture, to files like fbx/obj/maya and jpg/dds/png  ? Plz I need help
## Post #150
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-27T14:40:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from GM000
>
> How can I convert the game files: .MeshSet and .Texture, to files like fbx/obj/maya and jpg/dds/png  ? Plz I need help
[Here is basically everything you need](https://sta.sh/04jxcv9d9o0). Blender is a free and pretty small program and from it you can just export to .fbx to open it in other software.
## Post #151
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2017-11-27T17:24:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> halo08 wrote:There was no chunks folder.

I didn't extract the chunks, but I just started to extract all chunks, which I assume is going to be a while.
The filter doesn't quite work for chunks due to the names being pretty random.

Is there a better way to just extract the chunks that I need?
no for the moment

I still get nothing in the output folder when running the script and all chunks have been extracted. Am i doing something wrong? Some help would really be appreciated.
[image3.PNG](https://xentaxbackup.github.io/file/13603_image3.PNG)
## Post #152
- Username: GM000
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 10:02 pm
- Post datetime: 2017-11-27T21:46:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

How can I convert:
.MeshSet to .FBX
.Texture to .DDS
.EBX to .mp3
?
I am extracting with Universal frostbite extractor by daemon, and am working with Battlefront 2 2017
## Post #153
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-28T03:37:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from GM000
>
> How can I convert:
.MeshSet to .FBX
.Texture to .DDS
.EBX to .mp3
?
I am extracting with Universal frostbite extractor by daemon, and am working with Battlefront 2 2017
Crofty already gave all info in tutorial he made, not sure what else you asking for, go back to last post on page 10 and click that link to see what's going on.
## Post #154
- Username: GM000
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 10:02 pm
- Post datetime: 2017-11-28T04:12:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from o0Crofty0o
>
> GM000 wrote:How can I convert the game files: .MeshSet and .Texture, to files like fbx/obj/maya and jpg/dds/png  ? Plz I need help
Here is basically everything you need. Blender is a free and pretty small program and from it you can just export to .fbx to open it in other software.

Supposing it works for the meshes, still, for the texture and ebx files? thanks anyway
## Post #155
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-11-28T06:00:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from GM000
>
> 

Supposing it works for the meshes, still, for the texture and ebx files? thanks anyway
If you read the first page of tutorial you would have seen that it covers textures aswell. It explains how you get rigged models with textures and how to fix their faces. 
Sound i didn't add yet and currently don't know when it will happen. Info how to get them is on the last couple pages in this thread tho.
## Post #156
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-11-28T07:47:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

While trying to extract nfs payback files, i hit the dump button and get error message as "399 files failed because of chunk not found"...
Also while scanning cas/cat, it says 0 cas records found. What am i missing ?
## Post #157
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-28T15:16:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from 8thwond3r
>
> While trying to extract nfs payback files, i hit the dump button and get error message as "399 files failed because of chunk not found"...
Also while scanning cas/cat, it says 0 cas records found. What am i missing ?
wrong game selected
## Post #158
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-28T17:42:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I have problems with extracting SWBF1 models.
I'm using UFE02, set SWBF1 setting, select data folder.
i have 2 complect of game files .
first - 27 gb - scan and extracting normal.

```
29905 EBX, 146337 duplicates
9161 res, 36958 duplicates
33824 chunks, 70558 duplicates, 33131 unique chunks
72197 total.

Scanning CAS database ...
72197 entries, 11934 precache entries, 215365 duplicated entries.

checking chunks ...
0 missing chunks.

```


second - 42 gb - with error 

```
48361 EBX, 358578 duplicates
15151 res, 84575 duplicates
39257 chunks, 160137 duplicates, 38173 unique chunks
101685 total.

Scanning CAS database...
101504 entries, 15414 precache entries, 295352 duplicated entries.

checking chunks...
5535 missing chunks.

Scanning bundles...
48361 EBX, 358578 duplicates
15151 res, 84575 duplicates
39257 chunks, 160137 duplicates, 38173 unique chunks
101685 total.

Scanning bundles...
48361 EBX, 358578 duplicates
15151 res, 84575 duplicates
39257 chunks, 160137 duplicates, 38173 unique chunks
101685 total.

Scanning CAS database...
101504 entries, 15414 precache entries, 295352 duplicated entries.

checking chunks...
5535 missing chunks.


```

why is that?

i use first (small complect).
Extracting meshser, ebx, sceletons, assets is normal, but when I'm using meshtools I'm trying to get the chunks numbers there is an error


```

Unhandled exception: System.IndexOutOfRangeException: The index was out
 boundaries of the array.
   in FB_faceposer.FB_faceposer.Main (String [] args)

L: \ SWBF2u \ 67 \ tools>
```


archive with meshset, ebx and skeletons in attach.

Or, if there is, you can upload the heroes in smd (models and vu corrective smd)?
Everything else can be taken from Frosty.
Thank you
[__send.7z](https://xentaxbackup.github.io/file/13607___send.7z)
## Post #159
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-28T18:13:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> i have 2 complect of game files

why do you even have 2 complets ?

mesh tool for SWBF1 is old style, no auto chunk search. You have to give it meshset & chunk names.
## Post #160
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-28T18:21:20+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I do not have this game, and I just downloaded a couple of different iso from the network.

Can you explain how I can find out the name of the chunk from the meshset? I'm looking through the file in the hex editor.

And how to use Fb_SWBF_faces.exe? like as Fb_SWBF2_faces.exe?
## Post #161
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-28T21:47:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Do any of the actual animations from lets say MEA, DAI, SWBF1/2, BF3/4/1 can be exported in any usable way?
I read the whole thread again, and to be honest its discussed about the assetbanks in animation folder but I am a bit confused if they can be extracted/converted somehow. Maybe I missed something, damn my eyes hurt from al this reading, ill try to read it again, and am not even joking lol lol
## Post #162
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-29T04:49:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> Do any of the actual animations from lets say MEA, DAI, SWBF1/2, BF3/4/1 can be exported in any usable way?
I read the whole thread again, and to be honest its discussed about the assetbanks in animation folder but I am a bit confused if they can be extracted/converted somehow. Maybe I missed something, damn my eyes hurt from al this reading, ill try to read it again, and am not even joking lol lol

in progress [https://facepunch.com/showthread.php?t=1578192](https://facepunch.com/showthread.php?t=1578192)

for now, only cinematic tools...
## Post #163
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-29T07:29:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from o0Crofty0o
>
> ...
Crofty, do you happen to have a working python script for Battlefield 1, I bought the game, and damn it has 36 patched cas.cat files and 36 unpatched cas.cat files, and I cant find one script that works for the full game, and wow it downloaded from Origin a whole 70GB of game data, LOL, that's insane.
## Post #164
- Username: GM000
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 10:02 pm
- Post datetime: 2017-11-29T12:07:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I've seen and tried to use use crofty's tutorials but i feel they are incomplete. He gives tools for blender but they don't work for .MeshSet files.
Texture converter also doesn't.
Could anyone show or explain to me everything please.
and ebx?
## Post #165
- Username: DerBlaueKlaus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 08, 2017 7:49 pm
- Post datetime: 2017-11-29T13:29:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hello there 

I was a lurker here only but now I have a question please.

I have tried to extract Chewbacca from BF2. I got all files converted except one. The haircloth mesh isn't working with the Fb_SWBF2_mesh tool. It crashes immediately. What have I made wrong? Is there something missing in my "work folder"?

Another question is how to get the vehicles and spaceships. I get a smd and an ascii file but it doesn't load into blender. Maybe you can help here too.

Thank you!

PS: please excuse my german accent
## Post #166
- Username: Hashbandit
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 29, 2017 10:08 pm
- Post datetime: 2017-11-29T14:11:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Has anyone successfully ripped the audio files from the game?
If so, any chance of uploading them to mega. 

I want to extract the files myself but it seems like a ton of work and Im noob with all of this stuff.
## Post #167
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-29T15:23:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> o0Crofty0o wrote:...
Crofty, do you happen to have a working python script for Battlefield 1, I bought the game, and damn it has 36 patched cas.cat files and 36 unpatched cas.cat files, and I cant find one script that works for the full game, and wow it downloaded from Origin a whole 70GB of game data, LOL, that's insane.

the new tool i made - UFBE can unpack all unpatched files from Battlefield 1. No need for scripts.
## Post #168
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2017-11-29T17:10:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I know the swbf2 audio decoder is supposed to convert the ebx into to playable .wav/.mp3 files. I followed all the instructions in the thread so far, set input and output paths, the path to ealayer3, and extracted all chunks from the Data folder(and not the patch folder) with 0 missing chunks; I am running python 2.7.3 (32 bit) with xas1 and easpeex dll dectected as well as ealayer3 dectected. I should be getting the decoded audio into the output folder when i run the script but there's nothing in it. Got the mesh and textures with no problem but not the audio. I even posted an image of what the script looks like when i run it (top of page 11).

Sorry again if it seems like I'm spamming.
## Post #169
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-29T18:31:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Say me please, how I can get name of chunks from MeshSet/ebx? for SWBF1
If it can be found in hex form, what is the offset?
## Post #170
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-29T19:15:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> Say me please, how I can get name of chunks from MeshSet/ebx? for SWBF1
If it can be found in hex form, what is the offset?

0xf0  or around that
## Post #171
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-29T19:19:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from boumkwo
>
> I know the swbf2 audio decoder is supposed to convert the ebx into to playable .wav/.mp3 files. I followed all the instructions in the thread so far, set input and output paths, the path to ealayer3, and extracted all chunks from the Data folder(and not the patch folder) with 0 missing chunks; I am running python 2.7.3 (32 bit) with xas1 and easpeex dll dectected as well as ealayer3 dectected. I should be getting the decoded audio into the output folder when i run the script but there's nothing in it. Got the mesh and textures with no problem but not the audio. I even posted an image of what the script looks like when i run it (top of page 11).

Sorry again if it seems like I'm spamming.
do you have lowercase chunks? or upper? are you sure you're running correct script ?
## Post #172
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2017-11-29T20:34:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> boumkwo wrote:I know the swbf2 audio decoder is supposed to convert the ebx into to playable .wav/.mp3 files. I followed all the instructions in the thread so far, set input and output paths, the path to ealayer3, and extracted all chunks from the Data folder(and not the patch folder) with 0 missing chunks; I am running python 2.7.3 (32 bit) with xas1 and easpeex dll dectected as well as ealayer3 dectected. I should be getting the decoded audio into the output folder when i run the script but there's nothing in it. Got the mesh and textures with no problem but not the audio. I even posted an image of what the script looks like when i run it (top of page 11).

Sorry again if it seems like I'm spamming.
do you have lowercase chunks? or upper? are you sure you're running correct script ?

I have uppercase chunks only no lowercase; and I'm using the fb3decoder script from the swbf2_sounds.zip you provided on page 2
## Post #173
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-29T20:47:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from boumkwo
>
> I have uppercase chunks

thats the problem i think. That version only existed for about 30 minutes and then i updated it, because that was wrong. You can use total commander from tutorial to rename chunks to lowercase
## Post #174
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2017-11-29T21:07:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> boumkwo wrote:I have uppercase chunks

thats the problem i think. That version only existed for about 30 minutes and then i updated it, because that was wrong. You can use total commander from tutorial to rename chunks to lowercase

I used total commander to rename the chunks to lowercase but still nothing in the output folder when i run the script.
## Post #175
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-29T21:27:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> erik945 wrote:Say me please, how I can get name of chunks from MeshSet/ebx? for SWBF1
If it can be found in hex form, what is the offset?

0xf0  or around that

Yes, it's work fine.
Thank you again.
## Post #176
- Username: boumkwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 28, 2014 10:09 am
- Post datetime: 2017-11-29T23:55:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from boumkwo
>
> daemon1 wrote:boumkwo wrote:I have uppercase chunks

thats the problem i think. That version only existed for about 30 minutes and then i updated it, because that was wrong. You can use total commander from tutorial to rename chunks to lowercase

I used total commander to rename the chunks to lowercase but still nothing in the output folder when i run the script.

I managed to finally convert the audio. When I first extracted the chunks I didn't use UFBE 0.2 (stupid me), so i re-extracted the chunks (got all lowercase letters this time) and everything works fine. Thanks again for your help and patience   .
## Post #177
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-30T00:05:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> the new tool i made - UFBE can unpack all unpatched files from Battlefield 1. No need for scripts.
Yes sir, I know and its very nice to have it as one option, but was hoping for a script that actually extracts everything including patched/DLCs and all
## Post #178
- Username: GM000
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 10:02 pm
- Post datetime: 2017-11-30T02:51:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I've posted so many times. I extracted the entire Battlefront 2 Game with UFBE and all of useful files are .Meshset  .Texture  and .EBX
Could someone show mw how to convert them to .FBX | .DDs or .Png | .Mp3 or .Wav
Please don't redirect to crofty's website, i've tried or either I did something wrong, which I don't think or it doesn't work

Simple tut and tools anyone?
## Post #179
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-11-30T09:28:04+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Can I somehow use UFBE to unpack SWBF1 patches? For example, rename folders.
Can you explain its logic in the search the files?
## Post #180
- Username: DerBlaueKlaus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 08, 2017 7:49 pm
- Post datetime: 2017-11-30T15:00:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

most of the meshes are working fine but I still get crashes or errors when converting some meshes. I have tried to convert the MC80 main hull and got a crash. same with resurgentclass_stardestroyer. The ascii isn't loading into blender and gives an error msg some smd are loading but some crashing Blender.

What can I do?

Here is the error msg in Blender



Thank you for your help
## Post #181
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-30T15:31:39+00:00
- Post Title: Re: How do i convert files

> Reply from mono24
>
> daemon1 wrote:the new tool i made - UFBE can unpack all unpatched files from Battlefield 1. No need for scripts.
Yes sir, I know and its very nice to have it as one option, but was hoping for a script that actually extracts everything including patched/DLCs and all
as soon as i'll have time, i'll add support for patches
## Post #182
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-30T15:32:53+00:00
- Post Title: Re: How do i convert files

> Reply from GM000
>
> I've posted so many times. I extracted the entire Battlefront 2 Game with UFBE and all of useful files are .Meshset  .Texture  and .EBX
Could someone show mw how to convert them to .FBX | .DDs or .Png | .Mp3 or .Wav
Please don't redirect to crofty's website, i've tried or either I did something wrong, which I don't think or it doesn't work

Simple tut and tools anyone?

crofty's tutorial is very detailed and correct.
We can't help you if you don't say what exactly is not working, what do you do, and what happens.
## Post #183
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-30T15:33:48+00:00
- Post Title: Re: How do i convert files

> Reply from erik945
>
> Can I somehow use UFBE to unpack SWBF1 patches? For example, rename folders.
Can you explain its logic in the search the files?

i have no idea what can happen if you try that. At your own risk.
## Post #184
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-30T15:34:38+00:00
- Post Title: Re: How do i convert files

> Reply from DerBlaueKlaus
>
> most of the meshes are working fine but I still get crashes or errors when converting some meshes

yes i know that

this is a tool problem, i will fix this later.
as temporary solution, you can delete the ASCII sceleton in the beginning of the file (if you know the file format)
## Post #185
- Username: DerBlaueKlaus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 08, 2017 7:49 pm
- Post datetime: 2017-11-30T15:49:04+00:00
- Post Title: Re: How do i convert files

> Reply from daemon1
>
> DerBlaueKlaus wrote:most of the meshes are working fine but I still get crashes or errors when converting some meshes

yes i know that

this is a tool problem, i will fix this later.
as temporary solution, you can delete the ASCII sceleton in the beginning of the file (if you know the file format)

thanks for the fast reply ... I think I'll wait for the update 

So I'll convert the characters first
## Post #186
- Username: Hashbandit
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 29, 2017 10:08 pm
- Post datetime: 2017-11-30T19:38:29+00:00
- Post Title: Re: How do i convert files

Has anybody managed to extract audio files from the game?

can anybody make a turorial on how to do so please or upload the files to MEGA.
## Post #187
- Username: JohnMadden
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 23, 2016 8:45 am
- Post datetime: 2017-12-01T06:15:26+00:00
- Post Title: Re: How do i convert files

> Reply from Hashbandit
>
> Has anybody managed to extract audio files from the game?

can anybody make a turorial on how to do so please or upload the files to MEGA.

Please read the thread.
## Post #188
- Username: GM000
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 10:02 pm
- Post datetime: 2017-12-01T06:38:54+00:00
- Post Title: Re: How do i convert files

> Reply from DerBlaueKlaus
>
> most of the meshes are working fine but I still get crashes or errors when converting some meshes. I have tried to convert the MC80 main hull and got a crash. same with resurgentclass_stardestroyer. The ascii isn't loading into blender and gives an error msg some smd are loading but some crashing Blender.

What can I do?

Here is the error msg in Blender



Thank you for your help

This happened to me too. plz help
## Post #189
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-02T01:15:59+00:00
- Post Title: Re: How do i convert files

Is there any python script for Mass Effect: Andromeda out there?
I've searched high an low and no sing of anything like that.

for instance if I try the last swbf2full script all I get is:

```
Unpatched cat 1 not found or error reading format
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\ayainstallpackage\cas.cat 24309
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\ayainstallpackage\en\cas.cat 24499
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\eosinstallpackage\cas.cat 147771
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\eosinstallpackage\en\cas.cat 148188
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\levelprereqinstallpackage\cas.cat 214663
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\levelprereqinstallpackage\en\cas.cat 214733
Unpatched cat 7 not found or error reading format
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\mecdefaultinstallpackage\cas.cat 215690
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\mppatchinstallpackage\cas.cat 216042
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\multiplayerinstallpackage\cas.cat 248213
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\multiplayerinstallpackage\en\cas.cat 248255
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\restofthegameinstallpackage\cas.cat 478984
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\restofthegameinstallpackage\en\cas.cat 480150
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\spinitialinstallpackage\cas.cat 541995
R:\Origin\games\Mass Effect Andromeda\Data\Win32\streaminginstall\spinitialinstallpackage\en\cas.cat 542423
ambsibling.toc

Traceback (most recent call last):
  File "C:\Users\User\Desktop\swbf2full2\swbf2full.py", line 387, in <module>
    if "tocRoot" in locals():  dumpRoot(tocRoot)
  File "C:\Users\User\Desktop\swbf2full2\swbf2full.py", line 328, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\User\Desktop\swbf2full2\swbf2full.py", line 140, in dump
    toc=cas.readToc(tocPath)
  File "C:\Users\User\Desktop\swbf2full2\cas.py", line 95, in readToc
    return Entry(unXor(tocPath))
  File "C:\Users\User\Desktop\swbf2full2\cas.py", line 37, in __init__
    raise Exception("Entry does not start with \\x82 or (rare) \\x87 byte. Position: "+str(f.tell()))
Exception: Entry does not start with \x82 or (rare) \x87 byte. Position: 1
>>>
```
## Post #190
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-02T11:20:31+00:00
- Post Title: Re: How do i convert files

> Reply from daemon1
>
> 8thwond3r wrote:While trying to extract nfs payback files, i hit the dump button and get error message as "399 files failed because of chunk not found"...
Also while scanning cas/cat, it says 0 cas records found. What am i missing ?
wrong game selected

I successfully extracted the payback cas files with your older "swbf2beta" python script !!
But the mesh extractor tools throw file not found exceptions after "frostbite_faceposer" crash...


Screenshot (82).png (45.91 KiB) Viewed 99 times


Maybe it doesn't identify the chunk file related to the Meshset file. 
Is there any way to identify which chunk file is for which meshset file ??
On the other hand, The texture converter tool identifies the related chunks and converts them to dds successfully..
## Post #191
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-02T12:49:32+00:00
- Post Title: Re: How do i convert files

> Reply from 8thwond3r
>
> But the mesh extractor tools throw file not found exceptions

all games are different. swbf2 mesh will not work with NFS
## Post #192
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-02T16:03:09+00:00
- Post Title: Re: How do i convert files

> Reply from daemon1
>
> 8thwond3r wrote:But the mesh extractor tools throw file not found exceptions

all games are different. swbf2 mesh will not work with NFS
Are you planning to make one for this game too ?
## Post #193
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-02T16:30:35+00:00
- Post Title: Re: How do i convert files

> Reply from 8thwond3r
>
> daemon1 wrote:8thwond3r wrote:But the mesh extractor tools throw file not found exceptions

all games are different. swbf2 mesh will not work with NFS
Are you planning to make one for this game too ?
maybe i will, if someone give me files
## Post #194
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-02T19:20:47+00:00
- Post Title: Re: How do i convert files

UFBE 0.2.1 release, file moved to the first page. It will be updated there from now on.
Just small fixes:
- case-insensitive search
- cloth and other "special" meshes (which require no chunks) will now have a number in its name, allowing mesh tool to convert it
note: you have to delete "cache.dat" and scan bundles after UFBE update, or make clean run

SWBF2 tool updated (first post in the thread), again a few small changes:
- fixed meshes with lots of faces
- static meshes fixed (need no skeleton anymore, ascii format works)
## Post #195
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-03T00:24:53+00:00
- Post Title: Re: How do i convert files

> Reply from daemon1
>
> maybe i will, if someone give me files
they've been posted for a very long time now hehe, assuming those are the ones you need to check
[viewtopic.php?f=16&t=17236](http://forum.xentax.com/viewtopic.php?f=16&t=17236)
## Post #196
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-03T00:27:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> daemon1 wrote:maybe i will, if someone give me files
they've been posted for a very long time now hehe, assuming those are the ones you need to check
viewtopic.php?f=16&t=17236

and there is a sample file included in this post..
## Post #197
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-03T07:35:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

NFS Payback tool added to the first post.


Also I found an error in SWBF2 model tool, please redownload.
## Post #198
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-03T08:20:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> NFS Payback tool added to the first post.
Also I found an error in SWBF2 model tool, please redownload.
works !! thank you so much for listening !!
## Post #199
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-03T09:23:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> NFS Payback tool added to the first post.
Also I found an error in SWBF2 model tool, please redownload.

just tested it...generates ascii and smd files only for meshset files less than 10 or 12 kb..
it gives error for meshset files of 12kb or larger, like the main chassis in your above screenshot.
All other small parts of the car with comparatively less mesh and meshset file size works fine !! 
Maybe an update would surely fix it..
## Post #200
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-03T09:52:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from 8thwond3r
>
> daemon1 wrote:NFS Payback tool added to the first post.
Also I found an error in SWBF2 model tool, please redownload.

just tested it...generates ascii and smd files only for meshset files less than 10 or 12 kb..
it gives error for meshset files of 12kb or larger, like the main chassis in your above screenshot.
All other small parts of the car with comparatively less mesh and meshset file size works fine !! 
Maybe an update would surely fix it..

it works fine on all meshes you sent as examples. Send something that gives error
## Post #201
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-03T12:47:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> 8thwond3r wrote:daemon1 wrote:NFS Payback tool added to the first post.
Also I found an error in SWBF2 model tool, please redownload.

just tested it...generates ascii and smd files only for meshset files less than 10 or 12 kb..
it gives error for meshset files of 12kb or larger, like the main chassis in your above screenshot.
All other small parts of the car with comparatively less mesh and meshset file size works fine !! 
Maybe an update would surely fix it..

it works fine on all meshes you sent as examples. Send something that gives error

I can't extract the "car_acura_rsxs_2004_mesh 08ecbad8521c149f e03a00000000000084020000b000e000.MeshSet" file in the same example..
the one whose chunk is 2.87 mb.
## Post #202
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-03T14:14:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

ah, you need skeleton for it, because it has BONES
i used the default walrus_humanmale.ebx
so you need to have that file in the folder, or car skeleton, whatever its called
## Post #203
- Username: 8thwond3r
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 02, 2017 6:55 pm
- Post datetime: 2017-12-03T23:55:22+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> ah, you need skeleton for it, because it has BONES
i used the default walrus_humanmale.ebx
so you need to have that file in the folder, or car skeleton, whatever its called
I put the "car_acura_rsxs_2004_mesh.ebx" skeleton file in the folder but same error...can you provide your walrus ebx file ?
Can you remove the skeleton reference in the mesh tool ?
I uploaded the skeleton file i used, have a look yourself..
[nfs_ebx.rar](https://xentaxbackup.github.io/file/13642_nfs_ebx.rar)
## Post #204
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-04T04:31:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

if you cant use command line, just rename it to walrus_humanmale.ebx
## Post #205
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-04T16:53:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

ok i had no time in the morning to check EBX files you sent. Those are NOT skeletons.

use this human one from SWBF2 if you can't find car's skeleton
[walrus_humanmale.rar](https://xentaxbackup.github.io/file/13643_walrus_humanmale.rar)
## Post #206
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2017-12-04T19:37:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hey daemon, any idea if it would be possible to swap out those silly kneel down animations that play when a hero dies and replace them with the normal death/ragdoll animations that play for the normal soldiers?  I want to see Yoda/Vader fly through the air, hehe.

That would make Heroes vs Villains at least somewhat playable for me.  Thanks man.  Take care.
## Post #207
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-06T04:27:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

The crazy thing is that, NFSP has same issue with distorted faces on the characters as well, that sucks, ugh
## Post #208
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2017-12-09T20:43:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

When will it have support for Hardline?
And keep up the good work
## Post #209
- Username: JohnMadden
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 23, 2016 8:45 am
- Post datetime: 2017-12-13T19:56:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

New campaign came out for Battlefront 2. Do the audio scripts support the new content?

Also, the audio scripts always screw up at the voice lines outside of droids.
## Post #210
- Username: atilla439
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 14, 2017 10:00 am
- Post datetime: 2017-12-14T02:02:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Using 0.2.1 I am getting an error while checking chunks, what am I doing wrong?

Scanning bundles...
128344 EBX, 1579333 duplicates
35792 res, 212980 duplicates
175650 chunks, 590378 duplicates, 172801 unique chunks
336937 total.

Scanning CAS database...
336603 entries, 29060 precache entries, 893910 duplicated entries.

checking chunks...
17754 missing chunks.
## Post #211
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-14T03:49:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from atilla439
>
> Using 0.2.1 I am getting an error while checking chunks, what am I doing wrong?

Scanning bundles...
128344 EBX, 1579333 duplicates
35792 res, 212980 duplicates
175650 chunks, 590378 duplicates, 172801 unique chunks
336937 total.

Scanning CAS database...
336603 entries, 29060 precache entries, 893910 duplicated entries.

checking chunks...
17754 missing chunks.
Your not doing anything wrong, its how the tool works, you only checked the files, and it gives the actual results.
Assuming that's the only thing you where trying to achieve, if you want to dump the whole thing all you gotta do is select the options like the image I attached, and then click "Dump!"
For example this is how my BF1 looks like.



bf1.JPG (47.26 KiB) Viewed 78 times


Not all files lead to chunks, but also can be due to missing DLCs or updates etc, it depends what kind of region game you have, results vary.
For example I didn't use this tool, instead a python script(it supports update/patch), and I got in comparison to the results the 0.2.1 tool(update/patch not implemented yet) shows.
chunks=123,479 Files
ebx=110,586 Files
res=41,846 Files

a total of 67.4GB got dumped, out of the 72.8GB game has, as you can see, not all gets dumped.
## Post #212
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-14T15:09:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

BF1 must show only 1069 missing chunks. Never use current UFBE with game folder, use only DATA folder.
## Post #213
- Username: atilla439
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 14, 2017 10:00 am
- Post datetime: 2017-12-14T15:23:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> BF1 must show only 1069 missing chunks. Never use current UFBE with game folder, use only DATA folder.

This is for Battlefront 2 and I’m using the data folder.  In the examples I was following all screenshots were shooting 0 missing chunks.  If it’s supposed to have thousands of missing ones and it is correct then I guess I’m ok!

Thanks.
## Post #214
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-14T15:29:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from atilla439
>
> daemon1 wrote:BF1 must show only 1069 missing chunks. Never use current UFBE with game folder, use only DATA folder.

This is for Battlefront 2 and I’m using the data folder.  In the examples I was following all screenshots were shooting 0 missing chunks.  If it’s supposed to have thousands of missing ones and it is correct then I guess I’m ok!

Thanks.
no its supposed to have 0.
## Post #215
- Username: atilla439
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 14, 2017 10:00 am
- Post datetime: 2017-12-14T20:50:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> no its supposed to have 0.ok, that’s what I figured!  What are some things to check for when chunks isn’t zero?
## Post #216
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-15T00:11:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> BF1 must show only 1069 missing chunks. Never use current UFBE with game folder, use only DATA folder.
On DATA folder only, I have this.



bf1_data.JPG (47.27 KiB) Viewed 61 times


So yeah, its not the same for everyone, it depends what you have bought from Origin.
## Post #217
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-15T15:10:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> So yeah, its not the same for everyone, it depends what you have bought from Origin.
must also depend on game version. While I think data folder must not change with updates, but you never know.
## Post #218
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-12-15T16:24:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> mono24 wrote:So yeah, its not the same for everyone, it depends what you have bought from Origin.
must also depend on game version. While I think data folder must not change with updates, but you never know.

it does change. on swbf2 it added a3 and s1 folders (with levels inside - lil messy folder structure). and sp_a3_p2 and s1 to the cas storage. the sb and toc are duplicated in the patch folder, but no cas. this makes a lil sense. it's an initial release/addon.
## Post #219
- Username: DerBlaueKlaus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 08, 2017 7:49 pm
- Post datetime: 2017-12-16T08:40:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hello there,

I have a question maybe a silly one but ...

when I see all the parts for the capital spaceships in BF2 like the MC80 its a pain in the butt to puzzle them all together. As they are one piece in the game there must be a file that put them together ... does that make sense? 

If there was something like that it would make life much easier
## Post #220
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-16T11:01:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from episoder
>
> it does change. on swbf2 it added a3 and s1 folders
ah, that. New levels. ok
## Post #221
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-16T11:02:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from DerBlaueKlaus
>
> As they are one piece in the game there must be a file that put them together ... does that make sense?
sure there is such a file. And its possible to make a tool to put them all together
## Post #222
- Username: DerBlaueKlaus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 08, 2017 7:49 pm
- Post datetime: 2017-12-16T11:05:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> DerBlaueKlaus wrote:As they are one piece in the game there must be a file that put them together ... does that make sense? 
sure there is such a file. And its possible to make a tool to put them all together

That would be great!

Thank you!
## Post #223
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-16T15:50:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from DerBlaueKlaus
>
> That would be great!
maybe, but i'm not going to do it. Too busy with other games.
## Post #224
- Username: DerBlaueKlaus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 08, 2017 7:49 pm
- Post datetime: 2017-12-16T16:41:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> DerBlaueKlaus wrote:That would be great!
maybe, but i'm not going to do it. Too busy with other games.

ohh ... bad news ... but OK ... maybe a bit later?
## Post #225
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-16T17:04:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from DerBlaueKlaus
>
> daemon1 wrote:DerBlaueKlaus wrote:That would be great!
maybe, but i'm not going to do it. Too busy with other games.

ohh ... bad news ... but OK ... maybe a bit later?
i have too many other games to do. So maybe months later ...
## Post #226
- Username: DerBlaueKlaus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 08, 2017 7:49 pm
- Post datetime: 2017-12-16T17:14:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> DerBlaueKlaus wrote:

ohh ... bad news ... but OK ... maybe a bit later? 
i have too many other games to do. So maybe months later ...

no problem
## Post #227
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-17T00:34:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> mono24 wrote:So yeah, its not the same for everyone, it depends what you have bought from Origin.
must also depend on game version. While I think data folder must not change with updates, but you never know.
It changes quite a bit, for instance, the script you made long time ago to work with SWBF it no longer works to extract everything from the game, lots of assets missing and chunks.
For example I am kind of late at the "party" and trying to collect all working scripts and maybe if anyone has new ones, that fully work, for Updates as well not just main game files, you never know.
## Post #228
- Username: PlasmaUK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 18, 2017 3:50 am
- Post datetime: 2017-12-17T21:03:22+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

This is probably a real dumb question but could somebody help me please, I'm trying to run the fb3decoder and I get this:

```
EASpeex dll not detected.
EALayer3 tool detected.
```


How do I install the EASpeex dll?
## Post #229
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-18T00:25:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from PlasmaUK
>
> This is probably a real dumb question but could somebody help me please, I'm trying to run the fb3decoder and I get this:
Code: Select allXAS1 dll detected.
EASpeex dll not detected.
EALayer3 tool detected.

How do I install the EASpeex dll?
Just make sure its copied where the script is, all in same folder.
## Post #230
- Username: Hashbandit
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 29, 2017 10:08 pm
- Post datetime: 2017-12-19T00:04:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from JohnMadden
>
> Hashbandit wrote:Has anybody managed to extract audio files from the game?

can anybody make a turorial on how to do so please or upload the files to MEGA.

Please read the thread.

I have read the entire fourm. There is no clear set insturctions on how to extract the audio files from star wars battlefront 2 from a noobs point of view. 

Can you be of any help to me or not?
## Post #231
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-19T07:16:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

How can I avoid this?



error.JPG (85.03 KiB) Viewed 246 times



```
just-in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.IO.PathTooLongException: The specified path, file name, or both are too long. The fully qualified file name must be less than 260 characters, and the directory name must be less than 248 characters.
   at System.IO.Path.SafeSetStackPointerValue(Char* buffer, Int32 index, Char value)
   at System.IO.Path.NormalizePathFast(String path, Boolean fullCheck)
   at System.IO.Path.GetFullPathInternal(String path)
   at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   at System.IO.FileStream..ctor(String path, FileMode mode)
   at UFBE.Form1.dumpfile(UInt64 key, String outname)
   at UFBE.Form1.bDump_Click(Object sender, EventArgs e)
   at System.Windows.Forms.Control.OnClick(EventArgs e)
   at System.Windows.Forms.Button.OnMouseUp(MouseEventArgs mevent)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ButtonBase.WndProc(Message& m)
   at System.Windows.Forms.Button.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.8762 (QFE.050727-8700)
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework64/v2.0.50727/mscorlib.dll
----------------------------------------
UFBE
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Users/User/Desktop/UFBE_0_2_1/UFBE.exe
----------------------------------------
System.Windows.Forms
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.8653 (QFE.050727-8600)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.8770 (QFE.050727-8700)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.8681 (QFE.050727-8600)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------

************** JIT Debugging **************
To enable just-in-time (JIT) debugging, the .config file for this
application or computer (machine.config) must have the
jitDebugging value set in the system.windows.forms section.
The application must also be compiled with debugging
enabled.

For example:

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

When JIT debugging is enabled, any unhandled exception
will be sent to the JIT debugger registered on the computer
rather than be handled by this dialog box.
```
## Post #232
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-19T17:57:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> How can I avoid this?
System.IO.PathTooLongException: The specified path, file name, or both are too long.

if path is too long, and you can't shorten your dump directory, there's no way to avoid this other than for me to add a handler to skip such files. Or you can extract these with no folders.
## Post #233
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-20T03:45:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> if path is too long, and you can't shorten your dump directory, there's no way to avoid this other than for me to add a handler to skip such files. Or you can extract these with no folders.
But it is so strange, it hasn't happen so far, I test/used it for BF1, SWBF1 one time I used it for SWBF2 then few days later wanting to try once more, I got the error, makes no sense.

On another note, are you planning in near future to support also Updates/Patches and the following games for extraction:
Mirror's Edge Catalyst
Dragon Age Inquisition
Mass Effect Andromeda
Battlefield 3/4/HL
Need for Speed The Run (uses sb/toc only no cas/cat)
Need for Speed Rivals
Need for Speed 2016
Need for Speed Payback
FIFA

then it would truly be a universal frostbite extraction to support them all, 
I can supply if you need any files for testing, just saying, you name it.
## Post #234
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-20T04:43:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> daemon1 wrote:if path is too long, and you can't shorten your dump directory, there's no way to avoid this other than for me to add a handler to skip such files. Or you can extract these with no folders.
But it is so strange, it hasn't happen so far, I test/used it for BF1, SWBF1 one time I used it for SWBF2 then few days later wanting to try once more, I got the error, makes no sense.

On another note, are you planning in near future to support also Updates/Patches and the following games for extraction:
Mirror's Edge Catalyst
Dragon Age Inquisition
Mass Effect Andromeda
Battlefield 3/4/HL
Need for Speed The Run (uses sb/toc only no cas/cat)
Need for Speed Rivals
Need for Speed 2016
Need for Speed Payback
FIFA

then it would truly be a universal frostbite extraction to support them all, 
I can supply if you need any files for testing, just saying, you name it.
it depends on what do you call "near future"
## Post #235
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-20T06:03:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> it depends on what do you call "near future"
Somewhere around or until Christmas of 2018?
No rush, its just sad its limited so far, but I've tested all three functions and its neat, as simple as that.
Yes, BTW, not exporting in folders/subfolders fixes the issue, but damn, what a mess LOL
## Post #236
- Username: Hashbandit
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 29, 2017 10:08 pm
- Post datetime: 2017-12-20T12:52:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

HELP HELP HELP  I am desperate     

3rd post. No help recived. I have read the entire fourum, start to finish, 3 times. WILL LITERALLY PAY SOMEONE FOR HELP

How do i extract the audo files from the game?  I have extracted the entire game and now just have a ton of .ebx files and CHUNK files. How do I convert them to audio files or how do i rip audio files from them? I understand there is an audio script for python. I do not understand how to use this script,. in conjuction with python, to rip audio files. Nobody has listed step by step instuctions on how to do so, yet I keep getting told to read the forum post. 

Why is it so hard to get some help. Croftys tutorial was usfull for getting the files rippped from the game but the rest of their tutorial was all about textures. I strictly want only audio files. 

I am actaully begging for help
## Post #237
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-20T16:12:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Hashbandit
>
> Why is it so hard to get some help

nobody remember where instructions were
but they were somewhere
i have absolutely no time to look for it
i'm busy making tools
## Post #238
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-20T16:14:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> Somewhere around or until Christmas of 2018?

no, but maybe after it. Maybe.
## Post #239
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-20T17:12:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> mono24 wrote:Somewhere around or until Christmas of 2018?

no, but maybe after it. Maybe.
DAMN, so that means well have another unfinished tool like others out there all over internet, all alone an abandoned, lol (unless that was sarcasm hehe)

> Reply from Hashbandit
>
> How do i extract the audo files from the game?
Well. lets see, a step by step you say, ay?

-make sure you have python 2.7.3 32bit installed,
-get this audio script converter [download/file.php?id=13430](http://forum.xentax.com/download/file.php?id=13430)
-extract it somewhere you like, and right click on fb3decoder.py and select Edit with IDLE
-IDLE window opens showing you what the script is about,
-now modify the following black/green lines with where you dumped the game data such as the ebx/res/chunks
-first line is where you have dumped the whole game data

```
dumpDirectory   = r"T:\0research\swbf2"
```

-second line where you want to dump the audio (make sure its not on same HDD where you dumped the game data to avoid HDD read/write errors and such),

```
targetDirectory = r"T:\0research\swbf2snd"
```

-third line is very important as well, make sure to enter the path where you have the ealayer3.exe

```
ealayer3Path=r"H:\my projects\progs\ealayer3.exe"
```

-now make sure you have these folder structures where you dumped the game data the same if not make sure to modify them accordingly,

```
chunkFolder  = r"chunks"
chunkFolder2 = r"bundles\chunks"
```

-last step make sure you have in same folder where fb3decoder.py is both XAS/EASpeex .dll's
-now all you have to do is click F5 on your keyboard, click OK to save script if prompted, another window will open showing you the process, and it should go trough all ebx's to convert what ever has audio in it.

have fun
## Post #240
- Username: DerBlaueKlaus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 08, 2017 7:49 pm
- Post datetime: 2017-12-20T18:29:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hello there ...

got a 'lil problem while extracting BF2 after the season 1 download. Have I made something wrong?



... or will there be an update which supports the season 1 content completely?
## Post #241
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-20T19:25:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from DerBlaueKlaus
>
> Hello there ...

got a 'lil problem while extracting BF2 after the season 1 download. Have I made something wrong?



... or will there be an update which supports the season 1 content completely?
It is normal, not all resources lead to a chunk as daemon1 explained somewhere I think
plus the extraction tool only supports "Data" folder not the whole game with update/patch/DLCs

PS
What Season 1 are we talking here, I have the elite trooper deluxe edition, that already comes with last Jedi heroes pack, or am I missing something else?
## Post #242
- Username: croixrooge
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 21, 2017 2:02 am
- Post datetime: 2017-12-20T19:35:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I have exactly the same problem,
No chunks folder has been created. I retry
## Post #243
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-20T20:23:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> unless that was sarcasm hehe
i dont understand that.
right now i want to make something for dishonored2
then until dawn
then return to UFBE
but you never know what new tasks may appear for me on the way
this is why i said "maybe"
## Post #244
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-20T20:30:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> i dont understand that.
I understand daemon1, trust me I do,no worries, was being silly, a little holiday humor if you will.
I also understand your being bombarded with ton of requests, that's what happen when your a smarty/genius, if some of us would understand a fraction of what you do, things would be lost easier for the whole community, but anyway, glad to see your working on what ever projects are interesting.

> Reply from daemon1
>
> right now i want to make something for dishonored2
that game looks badass especially its map and the detail and everything, wow

cheers
## Post #245
- Username: Hashbandit
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 29, 2017 10:08 pm
- Post datetime: 2017-12-21T11:47:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> Hashbandit wrote:Why is it so hard to get some help

nobody remember where instructions were
but they were somewhere
i have absolutely no time to look for it
i'm busy making tools

Dameon I never expected any help from you. You made the tools, that is enough. I messaged a couple people who said they'd been successfull and extracting the game files but they were no help.
## Post #246
- Username: Hashbandit
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 29, 2017 10:08 pm
- Post datetime: 2017-12-21T11:52:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> daemon1 wrote:mono24 wrote:Somewhere around or until Christmas of 2018?

no, but maybe after it. Maybe.
DAMN, so that means well have another unfinished tool like others out there all over internet, all alone an abandoned, lol (unless that was sarcasm hehe)
Hashbandit wrote:How do i extract the audo files from the game? 
Well. lets see, a step by step you say, ay?

-make sure you have python 2.7.3 32bit installed,
-get this audio script converter download/file.php?id=13430
-extract it somewhere you like, and right click on fb3decoder.py and select Edit with IDLE
-IDLE window opens showing you what the script is about,
-now modify the following black/green lines with where you dumped the game data such as the ebx/res/chunks
-first line is where you have dumped the whole game data
Code: Select alldumpDirectory   = r"T:\0research\swbf2"
-second line where you want to dump the audio (make sure its not on same HDD where you dumped the game data to avoid HDD read/write errors and such),
Code: Select alltargetDirectory = r"T:\0research\swbf2snd"
-third line is very important as well, make sure to enter the path where you have the ealayer3.exe
Code: Select allealayer3Path=r"H:\my projects\progs\ealayer3.exe"
-now make sure you have these folder structures where you dumped the game data the same if not make sure to modify them accordingly,
Code: Select allebxFolder    = r"bundles\ebx" 
chunkFolder  = r"chunks"
chunkFolder2 = r"bundles\chunks"
-last step make sure you have in same folder where fb3decoder.py is both XAS/EASpeex .dll's
-now all you have to do is click F5 on your keyboard, click OK to save script if prompted, another window will open showing you the process, and it should go trough all ebx's to convert what ever has audio in it.

have fun

Thank you very much. Your tutorial was a bit more helpfull. I manged to extract most of the audio files from the game however the files I wanted the most I cannot obtain.THey are at this location 
Sound/VO/MP/Hero/ Ive tired running the script 3 times, but I keep getting the following error


Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.
Sound/VO/MP/Hero/Lando/Core/SW02_VO_MP_Hero_Lando_Core_CallLuke2
sw02_vo_mp_hero_lando_core_callluke3.ebx
Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.
Sound/VO/MP/Hero/Lando/Core/SW02_VO_MP_Hero_Lando_Core_CallLuke3
sw02_vo_mp_hero_lando_core_callluke5.ebx
Error executing EALayer3.
Error executing EALayer3.
Error executing EALayer3.

And it just repeeats for all the EBX files. My output folder is also empty. Do you know of any solution? My last attempt is to re-dump game to ensure there is no damaged files but It looked good to me.
## Post #247
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-21T16:48:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

are you sure you have ealayer3.exe ?
## Post #248
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-21T18:52:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> are you sure you have ealayer3.exe ?
Well, to be honest I tested it as well, exactly four times, and midway I too get same errors, and by the way daemon1, I have tried the original ealayer3 and two versions made by you, always same results no matter what, I even got two keyerrors codes but managed to get them fixed and the results are still the same "Error executing EALayer3."

these included ebx's are some of the samples that wont get converted


 ebx.7z
(108.55 KiB) Downloaded 41 times
## Post #249
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-21T19:18:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> these included ebx's are some of the samples that wont get converted
what about other sounds? at least something works?
## Post #250
- Username: croixrooge
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 21, 2017 2:02 am
- Post datetime: 2017-12-21T19:30:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I have some issues with SWBF2, when extracting, the chunks folder is not on the bundles folder. (the only chunk folder is on the root) So when I try to convert the mesh into smd it crash...
Anyone have the same issues ? Thanks
## Post #251
- Username: Hashbandit
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 29, 2017 10:08 pm
- Post datetime: 2017-12-21T21:36:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> are you sure you have ealayer3.exe ?
It was a bit tricky to find EAlayer3.exe, this where I downloaded it from [https://bitbucket.org/Zenchreal/ealayer3/downloads/](https://bitbucket.org/Zenchreal/ealayer3/downloads/) although it hasn't been updated in a few years so could that possbiely be an issue? 

> Reply from daemon1
>
> mono24 wrote:these included ebx's are some of the samples that wont get converted
what about other sounds? at least something works?

Most of the sounds are extracting yes. I have lightsaber sounds, planet abmbinece/atmosphere, abilty sound effects, light saber sounds, footsteps and so on. I personally wanted all the hero and villan lines, for example kylo ren says "You know what I a"m", Chewbacca does his growl, the emporer says "expereince power" etc. These are the only ones I can't get. 
So far i have 29gb of sound files, which should be mostly everything as I feel textures etc would take up the most space.
## Post #252
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-21T21:40:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> what about other sounds? at least something works?
Yes, I managed to get about half of the whole sounds exported, after fixing couple of keyerrors, so was about in total 30.2GB of wav's only, no mp3's what so ever came out, but that was because I let it run trough all the ebx's not just the sound folder.

> Reply from croixrooge
>
> I have some issues with SWBF2, when extracting, the chunks folder is not on the bundles folder. (the only chunk folder is on the root) So when I try to convert the mesh into smd it crash...
Anyone have the same issues ? Thanks
That's because it is normal, there wasn't supposed to be a chunks folder inside bundle folder in first place, due to duplicates, this tool that daemon1 created makes sure you do not get it thus the size of the dumps is limited to only extracting actual game data with out unnecessary duplicates.

> Reply from Hashbandit
>
> It was a bit tricky to find EAlayer3.exe, this where I downloaded it from https://bitbucket.org/Zenchreal/ealayer3/downloads/ although it hasn't been updated in a few years so could that possbiely be an issue?
Simple answer is NO, because I already tested it with both versions of the tool updated by daemon1, and they all give same results.

> Reply from Hashbandit
>
>  So far i have 29gb of sound files, which should be mostly everything as I feel textures etc would take up the most space.
That has nothing to do with the actual game dump data size, the reason it gets so large in size the audio conversion due to being in wave format, that's all.
## Post #253
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-22T20:07:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> wav's only, no mp3's
it means ealayer3 is not working at all. Ok i will check this asap
## Post #254
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-24T10:11:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> these included ebx's are some of the samples that wont get converted
ok i checked some of these files, and they convert correctly on my side.

Let's try to find whats wrong with your version. Where did you get the script and ealayer3 ?

I'm using the script from the first post in this thread, and the attached version on ealayer3, which i compiled in 2015, probably for SWBF1, and its still working.
[ealayer3.rar](https://xentaxbackup.github.io/file/13727_ealayer3.rar)
## Post #255
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-24T19:42:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> Let's try to find whats wrong with your version. Where did you get the script and ealayer3 ?
I'm using the script from the first post in this thread, and the attached version on ealayer3, which i compiled in 2015, probably for SWBF1, and its still working.
Well, I am using same script as you, yet no ealayer3 is attached where you say, BUT, I had no idea there was a 3rd version compiled by you, I tested the ones built on:
- 3/30/2015 7:50PM
- 4/2/2015 10:53PM
while your version you just attached and never knew about it is:
- 4/13/2015 12:18PM

I am running the script now trough all the ebx's and see what's up
## Post #256
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-24T20:22:12+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

by "the attached version on ealayer3" i meant the one just attached
## Post #257
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-24T22:51:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> by "the attached version on ealayer3" i meant the one just attached
lol, yeah, I realized second time I read the text, I'm like silly me, duuuh, lol
But so far testing it and it still converts, everything comes out right, including NFSPayback, which had same errors as SWBF2, so thank you for the third version of ealayer3.


MERRY CHRISTMAS EVERYONE !!!
## Post #258
- Username: GM000
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 10:02 pm
- Post datetime: 2018-01-04T14:46:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

.Smd and .ascii imports don't work in blender....
## Post #259
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-08T04:24:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> elementofprgress wrote:If you have any updated resTypes or something is wrong, let me know.

Sure:

    0xf04f0c81:".Dx11ShaderProgramDatabase",
    0x9C4FAA17:".HeightfieldDecal"
    0x957C32B1:".AtlasTexture",
    0xC6CD3286:".EnlightenStaticDatabase",
    0xA23E75DB:".TerrainLayerCombinations",
    0xE36F0D59:".HavokClothPhysicsData",
    0x6BDE20BA:".Texture",
    0x9D00966A:".UITtfFontFile",
    0xC611F34A:".MeshEmitterResource",

Here's all your unknown types, if you have something else unknown, let me know.
@daemon1, you happen to know what resType these are? the letters in front are from the games I came across.

```
    0x5E862E05:".DAI_resType5E862E05",
    0x59C79990:".DAI_resType59C79990",
    0x76742DC8:".DAI_resType76742DC8",
    0x41759364:".NFSP_resType41759364",
    0x2EBF5E85:".NFSR_resType2EBF5E85",
    0x8D9E6F01:".MEA_resType8d9e6f01",
    0xAD1AC4FD:".MEA_resTypeAD1AC4FD",
    0xCB8BCD07:".MEA_resTypeCB8BCD07",
    0xBA02FEE0:".MEA_resTypeBA02FEE0",
    0x52EE0D39:".MEA_resType52EE0D39",
```
## Post #260
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-08T06:34:12+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> 
@daemon1, you happen to know what resType these are? the letters in front are from the games I came across.

```
AD1AC4FD	LargeParticleCloud
BA02FEE0	MeshAdjacencyResource
52EE0D39	PlayerPresetResource
41759364	PhysicsResource
5E862E05	LocalizedStringResource
59C79990	FaceFXResource

```

I can't get the others because i dont have these games EXE's right now
## Post #261
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-08T16:37:04+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> I can't get the others because i dont have these games EXE's right now
Now that was fast, thank you.

If I may ask, how you got them from the exe? id like to try the other ones myself, if its not a secret or something as usual lol
Lets say we take:

```
0x76742DC8:".DAI_resType76742DC8",
```

Do I look for the offset:

```
0x76742DC8
```

inside the executable of the game, then in front or after there is a hash of the actual name? what's the size to look for?

EDIT: yeah, I figured its not so easy, there's no such offset in the game, not even a hex value like that, so I guess its a bit more complex?

I'd really like to know for future games how to look for the unknownResTypes,
## Post #262
- Username: Paja913
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 21, 2010 2:19 am
- Post datetime: 2018-01-10T16:14:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I'm looking for a sound extractor with guide. Can you help me?
Because I can't get sound files by UFE0.2.
## Post #263
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-10T16:23:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> inside the executable of the game, then in front or after there is a hash of the actual name?

yes its a hash of the actual name, but you wont find it is the EXE, because its not there. But if you take all string constants from the EXE, and calculate their hashes, some of them will be these numbers. The names are scattered across the data segment, so just hash them all and you'll find what you need. Good idea is to use some tool to do it for you automatically
## Post #264
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2018-01-10T18:23:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Daemon1 , my question is ... you export DX11 texture
Do you export DX12 textures ? As the option exist into the game .. CAS files have them ?

frostbite engine have this entrie if I’m right
0x6BDE20BA: ".Dx12Texture"
## Post #265
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-10T18:31:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from CZW
>
> Daemon1 , my question is ... you export DX11 texture
Do you export DX12 textures ? As the option exist into the game .. CAS files have them ?

frostbite engine have this entrie if I’m right
0x6BDE20BA: ".Dx12Texture"

For your information, 6BDE20BA is just "Texture", not dx12 or anything else
## Post #266
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-11T00:46:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> yes its a hash of the actual name, but you wont find it is the EXE, because its not there. But if you take all string constants from the EXE, and calculate their hashes, some of them will be these numbers. The names are scattered across the data segment, so just hash them all and you'll find what you need. Good idea is to use some tool to do it for you automatically
LOL, you sneaky devil, hehehe, you do realize that just like yourself I too have English as "second" language, like most in here I assume, anyway not like its an excuse, but in past few days, I got as far as looking for and installing Explorer Suite and IDA, because obviously I never even heard of them yet alone know how to use them as should, hehe, but trying to learn, it fascinates me to the point I cant sleep at times from all this stuff.
So been trying to mess around and dump the game executable from Evolve Stage 2 to find the RSA new key that its hidden in the EXE apparently because game files can NOT be extracted any longer with the old method, got to do all of that but to follow the pattern of the old method its not easy because, well, you got to know what your looking for, right? and now I had to Google "hash calculation", "data segment" etc etc etc lol, so you see, most of us who are curious and really want to learn hit all these walls because information is never "clear" and I get it, it needs some sort of "decryption" even from hearing and reading stuff, BUT, if you have some clear point as to what to do exactly, then please at least PM if its too much of a secret, I'm being honest here, I want to try and learn.
Shit, I've even been begging to offer my help to learn how to dump properly the The Crew game, to update the extraction list, no one even wants to point in the right direction, I mean, damn its that big of a secret? anyway

So in conclusion, I know your a busy guy, and its amazing someone like yourself still pays attention to us little guys, we thank you, but when ever you have some free time and your bored id like more info on what can I do to make things work, if not I will continue to research at my own pase an try to learn what I can while hitting wall after wall after wall .......  you get the idea.

> Reply from Paja913
>
> I'm looking for a sound extractor with guide. Can you help me?
Because I can't get sound files by UFE0.2.
What are you talking about?
The tool extracts everything you need, literally everything from the mentioned games gets dumped.
And there's even a script to extract the entire game audios from it, just check the thread carefully and you'll find everything.
Try page 16
## Post #267
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-11T15:23:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> I had to Google "hash calculation"
it seems you know nothing about hashes. ok i can tell you. there are many hash algorythms, but frostbite is not using any standard ones, they did their own, which works like this:

uint hash = 5381;
for (int i = 0; i < name[j].Length; i++)    hash = (hash * 33) ^ (char)(name);

So essentially you start from number 5381, and then multiply it by 33 for every letter of the name, then do "https://en.wikipedia.org/wiki/Exclusive_or" with that letter

after that you get 32-bit hash value

Dont care much about data segments, just find a region in the EXE, which contains a lot of strings, it is usually about 4 MB in size, and extract all strings from it with strings.exe from sysinternals

There may be better ways do to it, but this is what I used
## Post #268
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-13T06:51:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hey guys, those of you that happen to know and came across this issue I'm having and know of an answer please help.

Every time I try to use a python script and if a pair of .toc/.sb archives where .sb archive is 4GB+ in size no matter what it throws this error:

```
  File "D:\BF4_dump\bf4dumper.py", line 244, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "D:\BF4_dump\bf4dumper.py", line 234, in dumpRoot
    dump(fname,targetDirectory)
  File "D:\BF4_dump\bf4dumper.py", line 185, in dump
    LZ77.decompressUnknownOriginalSize(sbPath,entry.offset,entry.size,targetPath)
ArgumentError: argument 2: <type 'exceptions.OverflowError'>: long int too long to convert
>>> 
```

Now if I add this argument as explained by daemon1 in another thread:

```
        if hexlify(entry.id)=="2550ad6e0c4d281384a6bf767bb7a959 <-replace it with the chunk hash that causes the error" : continue
```

and then run the script again to ignore the .chunk with the issue, it doesn't help because the next .chunk up on extraction still throws same error, so on and so forth, now it might be the fact that its the 32bit python in use, but if I want to use the 64bit its not possible because there is no LZ77.dll 64bit version, as far as I know, right? I've looked around and couldn't find one.
So I assume there must be an argument to add in the script, that makes the extraction to continue with out excluding any chunks from the process.

Thank you, cheers.
## Post #269
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-13T08:37:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> So I assume there must be an argument to add in the script, that makes the extraction to continue with out excluding any chunks from the process.

No.

There is no argument in 32-bit .DLL to pass 64-bit offset to it. In theory you can make this, but you have to make a new .DLL for that.

p.s. whats the game using 4gb files?
## Post #270
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-13T23:55:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> There is no argument in 32-bit .DLL to pass 64-bit offset to it. In theory you can make this, but you have to make a new .DLL for that.
Oh, ok, understood, then is there any other .dll I can use you might know of, both 32bit or 64bit, I'd definitely like to try it out?

> Reply from daemon1
>
> p.s. whats the game using 4gb files?
Battlefield Hardline:
-one .sb is 4.32GB
-second .sb is 5.59GB
they are the only two that wont allow the extraction to continue, there for extraction gets disrupted, I'm sure something must be available, just haven't found it, yet.
## Post #271
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-14T07:32:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> then is there any other .dll I can use
no i don't know about any other dll existing
i remember i dumped hardline in 2015 and there was no big SB files
i can make a new dll, but i'd rather support it in UFBE, anyway i dont have time for either now
## Post #272
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-15T01:00:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> i remember i dumped hardline in 2015 and there was no big SB files
I have almost every Frostbite game in my library and all are full editions with every pack, DLC, update you name it, probably that's why.
Battlefield Hardline right now officially from Origin is at:

```
66.3 GB (71,244,451,840 bytes)
760 Files, 118 Folders
```


> Reply from daemon1
>
> i can make a new dll, but i'd rather support it in UFBE, anyway i dont have time for either now
Well that's why I hit so many walls along the way, I am very late at this massive "party", having more options than one is far better, in my opinion, having an updated .dll is not a bad idea either, obviously when you have some free/boring time, hehe.

Was/kind of still am I guess, working on a simple yet as full as possible tutorial on the Frostbite games, so I can post it for those new comers like myself.
About how to dump, and what to use for each game individually, I have collected all tools/utilities/.dlls/scripts/notes/info, you name it, to have a tutorial with out major errors, while using a legit copy of a game of course with all the needed files.
For example I can dump properly the following frostbite games:
- Battlefield 3
- Battlefield 4
- Battlefield Hardline
- Battlefield 1
- Dragon Age: Inquisition
- Mass Effect: Andromeda
- Medal of Honor: Warfighter (don't own it (yet))
- Mirror's Edge Catalyst
- Need for Speed: The Run (so far getting messed up chunk GUIDs, the ones from res wont coincide with chunks extracted, aarrggghhh)
- Need for Speed Rivals
- Need for Speed 2016
- Need for Speed Payback
- Plants vs. Zombies: Garden Warfare (don't own it (yet))
- Plants vs. Zombies: Garden Warfare 2 (except 80% extracted of a 6.58GB .sb file)
- Star Wars Battlefront
- Star Wars Battlefront II
Right now working/testing on all games to fully extract the audios and texture conversion, hoping I can get it all done tested so I can find out what's possible and what's not, or what needs to be updated.

PS: Of course as you know all of that was possible for one main reason Frankelstner script and every modification made by you (daemon1/id-daemon) to have all new and old games work, with out it none of it was doable.
## Post #273
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-01-15T09:28:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Perhaps in the near future there will be a universal model tool for games using Anvil Engine?   
Beacuse the one ArchiveNeXt is a pain to work with and dosen't have support for bones and so on

Games

Scimitar:
Assassin's Creed
Prince of Persia
Shaun White Snowboarding

Anvil:
Assassin's Creed II 
Prince of Persia: The Forgotten Sands
Assassin's Creed: Brotherhood
Assassin's Creed: Revelations

AnvilNext:
Assassin's Creed III
Assassin's Creed III: Liberation
Assassin's Creed IV: Black Flag
Assassin's Creed Rogue

AnvilNext 2.0:
Assassin's Creed Unity
Assassin's Creed Syndicate
Tom Clancy's Rainbow Six Siege
Steep
For Honor
Tom Clancy's Ghost Recon Wildlands
Assassin's Creed Origins

Why are people thank me?
This is a request if anyone is interested to make a tool xD
## Post #274
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-24T01:47:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Faithfullfaun
>
> Why are people thank me?
I only gave you a thumbs up because I couldn't agree more with your comment, thus keeping the thread less messy.

On another note:
When one comes across this type of an error, over and over again, what exactly does it mean?
What do I need to avoid? anyone has a clue?

```
  File "C:\Users\User\Desktop\test\dumper.py", line 419, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Users\User\Desktop\test\dumper.py", line 359, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\User\Desktop\test\dumper.py", line 171, in dump
    toc=cas.readToc(tocPath)
  File "C:\Users\User\Desktop\test\cas.py", line 95, in readToc
    return Entry(unXor(tocPath))
  File "C:\Users\User\Desktop\test\cas.py", line 37, in __init__
    raise Exception("Entry does not start with \\x82 or (rare) \\x87 byte. Position: "+str(f.tell()))
Exception: Entry does not start with \x82 or (rare) \x87 byte. Position: 1
```
## Post #275
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-24T15:25:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> When one comes across this type of an error, over and over again, what exactly does it mean?

It means the file that you are giving to the script is not in the format it expected to be.

Many possible reasons: different engine version, different file layout, wrong file type, file is encrypted. Or anything else.
## Post #276
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-25T05:54:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> Many possible reasons: different engine version, different file layout, wrong file type, file is encrypted. Or anything else.
Thank you for answering.
They do not seem encrypted otherwise they wouldn't work at all.
Engine: frostbite 2, based on sb/toc only, no cas/cat.
They extract ok in perfectly fine folder structure like any other frostbite engine game, however 75% of the resTypes, do not match the GUIDs they have inside with the ones from chunks, makes no sense, frostbite.bms by aluigi does not support superbunles at all, and it makes a mess wrong sizes among other things, and does not add the GUIDs with in super bundles or extracts them as should, but you already know that its limited in extraction.

It might be a quick fix for those that know, I attached the smallest sample files [here](https://mega.nz/#!D1FRRRaS!_Sivm3IQjgRkczdoB5hSNB3Apf0Ff1y1HjAPgdUHc-I) if you have some time to look at it, and maybe update one of the python scripts to try it out, its the only issue I have so far and those chunks I mentioned that are 4GB+ in size, for those it literally needs another .dll, but who knows maybe a solution will surface.
No python script for BF3 out there works, at all, the new python scripts for newer games not even a chance lol

I really hope you can take a look at it, thank you.
## Post #277
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-25T20:40:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> I attached the smallest sample files
not very descriptive name when i have to put it next to dozens of other samples to look at someday
## Post #278
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-25T23:26:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> mono24 wrote:I attached the smallest sample files
not very descriptive name when i have to put it next to dozens of other samples to look at someday
I didn't even realized, I just though of "sample" and that was it, now its renamed SB-TOC_sample_with_out_CAS-CAT.zip

cheers
## Post #279
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-27T06:59:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> daemon1 wrote:mono24 wrote:I attached the smallest sample files
not very descriptive name when i have to put it next to dozens of other samples to look at someday
I didn't even realized, I just though of "sample" and that was it, now its renamed SB-TOC_sample_with_out_CAS-CAT.zip

cheers
you could just say it was nfs run and it would save me time
I already extracted that game before. got no errors extracting.
if you tell me specific SB/toc that gives you error, i can check that
and chunk guids that i checked correspond to chunks
i was using the usual script
audio chunks were "permutated" in some games. maybe this is why you think they do not match
## Post #280
- Username: brennoarts
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 26, 2018 6:35 am
- Post datetime: 2018-01-27T21:09:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Why I get this error? "stopped working" I make all like tutorial, I'm trying get the BF1 models
[Screenshot_1.jpg](https://xentaxbackup.github.io/file/13850_Screenshot_1.jpg)
## Post #281
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-28T00:10:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from brennoarts
>
> Why I get this error? "stopped working" I make all like tutorial, I'm trying get the BF1 models
As daemon1 explained already, make sure you have the .ebx called 3pantskeleton.ebx in same folder, and drop the VisualUnlock on to the tool, read carefully the description in first post all information is there.

> Reply from daemon1
>
> you could just say it was nfs run and it would save me time
I already extracted that game before. got no errors extracting.
if you tell me specific SB/toc that gives you error, i can check that
and chunk guids that i checked correspond to chunks
i was using the usual script
audio chunks were "permutated" in some games. maybe this is why you think they do not match
Once more my apologies, I had a lot of files dealing with and lost track of what I was doing, thus not explaining better, now I have it all sorted out and basically its like this.
The main script that is found here: [http://www.bfeditor.org/forums/index.ph ... -archives/](http://www.bfeditor.org/forums/index.php?/topic/15731-file-dumper-for-sbtoc-archives/)
-extracts everything with out any errors/issues what so ever for the game NFS The Run, but, if I open a file for example:
\bundles\res\_c4\vehicles\nfs\ast_one_77_10\kits\ast_one_77_10_kit00_stream_meshdefault.MeshSet
the python script extracts the chunk for it 0BDAA45B4AD672153913456F15173439.chunk 315KB in size, while frostbite.bms only extracts it as 140KB in size, only the 140KB in size works to be opened in UU3D, 3dsMax scripts by dainiuxxx/Dainius G do not work for the game and there is no other option that I know of, because I usually try every option I can find.
There for I like the python how extracted it all nicely and sorted out, its the only one that can be used even though chunks are missing basically plus not bundles are extracted, while the frostbite.bms is impossible to use because it dos not extract everything, no bundles etc etc etc
-if I try to convert the audios, only a few work while exactly 1190 audio chunks are missing
-if I want to find the chunks for all the characters, chunks do not even exist in either chunks or bundle\chunks folder, regardless of what script I am using.

my only question remains then, what is the usual script that you where using?
## Post #282
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-28T08:05:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

this is what i'm getting from 
\bundles\res\_c4\vehicles\nfs\ast_one_77_10\kits\ast_one_77_10_kit00_stream_meshdefault.MeshSet



0BDAA45B4AD672153913456F15173439.chunk 315KB in size - this is the correct chunk

140KB in size - is wrong chunk and it must NEVER work with that mesh

Attached is my tool version i made to work with NFS Run. (needs veniceantske01.ebx)
[Fb_nfsrun.rar](https://xentaxbackup.github.io/file/13851_Fb_nfsrun.rar)
## Post #283
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-28T08:07:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> my only question remains then, what is the usual script that you where using?
This is the old script i always used for frostbite2
i dont remember where i got it, probably bfeditor.org too

you say it works for you with no errors, it means its probably the same script

the only explanation to chunk size i see is that Luigi did a workaround to get smaller LOD instead of correct LOD0 (which he can't get)
## Post #284
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-29T01:40:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> the only explanation to chunk size i see is that Luigi did a workaround to get smaller LOD instead of correct LOD0 (which he can't get)
Hmmm, interesting, yet not so sure though, check this sample if you will, out of curiosity maybe.
for the \bundles\res\_c4\vehicles\nfs\ast_one_77_10\kits\ast_one_77_10_kit00_stream_meshdefault.MeshSet 23.6kb in size
it holds the following information: from both python and frostbite.bms scripts,

```

LODs: 4
LOD: 0, 0BDAA45B4AD672153913456F15173439.chunk
LOD: 1, 1F33930CC2ABF719DACAAEA40120A52B.chunk
LOD: 2, A5E93B8D20E5BC246C97533C71600551.chunk
LOD: 3, E3E1E8D2572931A0A8F1EE6971F767DD.chunk
```




ast_one_77_10_kit00_stream_meshdefault.MeshSet hex_nfsTheRunSample.JPG (203.66 KiB) Viewed 432 times


from frostbite.bms script the sizes are:

```

LODs: 4
LOD: 0, 0BDAA45B4AD672153913456F15173439.chunk 140kb
LOD: 1, 1F33930CC2ABF719DACAAEA40120A52B.chunk 87.9kb
LOD: 2, A5E93B8D20E5BC246C97533C71600551.chunk 65.4kb
LOD: 3, E3E1E8D2572931A0A8F1EE6971F767DD.chunk this chunk is non existent after extraction
```

from python script the sizes are:

```

LODs: 4
LOD: 0, 0BDAA45B4AD672153913456F15173439.chunk 331kb
LOD: 1, 1F33930CC2ABF719DACAAEA40120A52B.chunk 208kb
LOD: 2, A5E93B8D20E5BC246C97533C71600551.chunk 153kb
LOD: 3, E3E1E8D2572931A0A8F1EE6971F767DD.chunk this chunk is non existent after extraction
```

to test if you'd like:[https://mega.nz/#!7hFEVYKI!g1wWr3vAUbpT ... JeQ3flf6qk](https://mega.nz/#!7hFEVYKI!g1wWr3vAUbpT8cFaYv1-jjwfV2GfKdU_HJeQ3flf6qk)
## Post #285
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-29T01:46:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> 140KB in size - is wrong chunk and it must NEVER work with that mesh
well... the python script results are zero, while the frostbite.bms script results are same as yours.



nfsTheRun_Sample.JPG (136.38 KiB) Viewed 432 times


And the last LOD is non existent as I mentioned, but that is not a big issue, many more chunks are missing, even for LOD0, including characters.
Do you think the script needs maybe another editing/argument to do a deeper scanning/extraction? Just a thought, as it makes no sense why so many chunks missing including the audio ones, you think you can take a look at it please?
No rush of course, its just odd the way it extracts, that's all.

thanks
## Post #286
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-29T15:39:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

ok the explanation is simple:

bms extracts compressed chunks
python extract decompressed chunks

thats why size is different

if you tell me some chunk that is "missing" i can check that
## Post #287
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-31T06:17:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> bms extracts compressed chunks
python extract decompressed chunks
Oh, hmmm, who would have thought, makes sense now, thank you.

> Reply from daemon1
>
> if you tell me some chunk that is "missing" I can check that
Sorry for delay, attached are some of the missing chunks that are missing.


 missing_chunks.zip
(23.98 KiB) Downloaded 33 times
## Post #288
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-04T08:17:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> if you tell me some chunk that is "missing" i can check that
is the text file with missing chunks any good of help to check the script?
## Post #289
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-04T08:41:22+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> daemon1 wrote:if you tell me some chunk that is "missing" i can check that
is the text file with missing chunks any good of help to check the script?
i had no time to check it yet, but it would be better you if you also tell me which files they are linked from

because they can be just unused chunks
## Post #290
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-04T22:05:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> which files they are linked from
You mean from what sb/toc pair are from or what resType files they belong to?
Because besides the audio chunks that the script shows them automatically missing while trying to convert them, I added the others manually based on their respective resTypes, I have no clue how to search for the missing ones with the script.


 resTypes_with_missing_chunks.zip
Some resType samples out of hundreds with missing chunks (33.07 KiB) Downloaded 29 times
## Post #291
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-06T08:39:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hey daemon1,

...since your very busy was wondering if I can try your python script that you extracted NFSTheRun?
Want to give it a try, I've even tried for audio for example, both AudioSuperBundle and ChunksAudio in a separate folder, extracted them,
and results are still zero saying no chunks can be found for conversion using the frostbite2 decoder script, makes no sense.
I want to compare the extracted log from the script with your version and see what am I missing from extraction.
## Post #292
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-06T19:00:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

ok i checked the meshsets you provided, there are only few as i understand, they have only 1 lod, so i think they are just leftovers not used in game

as or audio, it known that audio chunk IDs were specifically encrypted in some games, so no surprise here we have same probably. The old method is not working, so i think they did something else to encrypt them.
## Post #293
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-06T21:13:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> there are only few as I understand, they have only 1 lod, so I think they are just leftovers not used in game
Only a few because it was insane to manually search each and one of them, but its odd because many more are missing even from game asset map, few from cars, so they must be somewhat linked just as you said, might be encrypted or scrambled in a weird way.

may I please have and use the script you have for the game though? I want to give it swirl.

thank you for looking in to it
## Post #294
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-07T15:56:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

ok but in this case in must be like... only a few unused chunks match, which are kind of leftovers, and VAST majority of chunks will NOT match (encrypted)

heres the script, but i dont think it will help at all
[fb3dump.rar](https://xentaxbackup.github.io/file/13891_fb3dump.rar)
## Post #295
- Username: StraightArrow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 08, 2018 2:30 pm
- Post datetime: 2018-02-21T08:31:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

@daemon1 Having a lot of trouble with Battlefield 1 mesh work. You still support it? Getting the faceposer error even after the skeleton in working folder and visual unlock tricks. I really just need some weapon models from xpack 2. I cant seem to find the chunks for the 1p gun models in another program so I am trying this one. Now I can't even open any models with this software. Can someone help pretty please. and thank you
## Post #296
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-21T15:12:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from StraightArrow
>
> @daemon1 Having a lot of trouble with Battlefield 1 mesh work. You still support it? Getting the faceposer error even after the skeleton in working folder and visual unlock tricks. I really just need some weapon models from xpack 2. I cant seem to find the chunks for the 1p gun models in another program so I am trying this one. Now I can't even open any models with this software. Can someone help pretty please. and thank you
yes it still must be supported
probably you're doing something wrong
send me files, i can check them
## Post #297
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-23T05:44:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from StraightArrow
>
> I really just need some weapon models from xpack 2
I checked the files, they are in a patch, and patch is not yet supported. You can get files with python script and then convert models with my model tool
## Post #298
- Username: Nat517
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 25, 2018 5:22 am
- Post datetime: 2018-02-24T22:20:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> daemon1 wrote:mono24 wrote:Somewhere around or until Christmas of 2018?

no, but maybe after it. Maybe.
DAMN, so that means well have another unfinished tool like others out there all over internet, all alone an abandoned, lol (unless that was sarcasm hehe)
Hashbandit wrote:How do i extract the audo files from the game? 
Well. lets see, a step by step you say, ay?

-make sure you have python 2.7.3 32bit installed,
-get this audio script converter download/file.php?id=13430
-extract it somewhere you like, and right click on fb3decoder.py and select Edit with IDLE
-IDLE window opens showing you what the script is about,
-now modify the following black/green lines with where you dumped the game data such as the ebx/res/chunks
-first line is where you have dumped the whole game data
Code: Select alldumpDirectory   = r"T:\0research\swbf2"
-second line where you want to dump the audio (make sure its not on same HDD where you dumped the game data to avoid HDD read/write errors and such),
Code: Select alltargetDirectory = r"T:\0research\swbf2snd"
-third line is very important as well, make sure to enter the path where you have the ealayer3.exe
Code: Select allealayer3Path=r"H:\my projects\progs\ealayer3.exe"
-now make sure you have these folder structures where you dumped the game data the same if not make sure to modify them accordingly,
Code: Select allebxFolder    = r"bundles\ebx" 
chunkFolder  = r"chunks"
chunkFolder2 = r"bundles\chunks"
-last step make sure you have in same folder where fb3decoder.py is both XAS/EASpeex .dll's
-now all you have to do is click F5 on your keyboard, click OK to save script if prompted, another window will open showing you the process, and it should go trough all ebx's to convert what ever has audio in it.

have fun

Thank you so much for the detailed instruction, but I don't have a EASpeedx.dll. This is my log:

Python 2.7 (r27:82525, Jul  4 2010, 09:01:59) [MSC v.1500 32 bit (Intel)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> ================================ RESTART ================================
>>> 
XAS1 dll detected.
EASpeex dll not detected.

Traceback (most recent call last):
  File "C:\Users\liyis\Downloads\swbf2_sounds\fb3decoder.py", line 99, in <module>
    startupinfo.dwFlags |= subprocess.STARTF_USESHOWWINDOW
AttributeError: 'module' object has no attribute 'STARTF_USESHOWWINDOW'
>>> 

where can I find one?
## Post #299
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-25T00:30:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Nat517
>
> where can I find one?
The WHOLE website is full of them in so many attachments, I guess another one wont hurt, yet I wish most of you who join can take some time and do some research, everything is already posted, you name it.


 easpeex.zip
(52.57 KiB) Downloaded 64 times


Although based on your error, something else might be wrong too, not an expert here anyway, but try it and see what's up.
## Post #300
- Username: Nat517
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 25, 2018 5:22 am
- Post datetime: 2018-02-25T00:58:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> Nat517 wrote:where can I find one?
The WHOLE website is full of them in so many attachments, I guess another one wont hurt, yet I wish most of you who join can take some time and do some research, everything is already posted, you name it.
easpeex.zip
Although based on your error, something else might be wrong too, not an expert here anyway, but try it and see what's up.

Sorry about that, and really thank you for the help, I've been feeling lost the whole day until you showed up. I just figured out I always had them in the same folder with the other two, but the fb3decoder.py won't recognize EASpeex.dll and kept saying it is not found.

And about the other error, yes it kept shows up and I have no idea what to do with it. I have python 2.7, which is recommended in this thread. I also tried a newer version of python (3.6), and it just kept saying "invalid syntax".
## Post #301
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-25T03:48:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Nat517
>
> Sorry about that, and really thank you for the help, I've been feeling lost the whole day until you showed up. I just figured out I always had them in the same folder with the other two, but the fb3decoder.py won't recognize EASpeex.dll and kept saying it is not found.
You have to start from scratch and make sure all paths are correct for every asset required, double check, even I who did this tens of times I get lost in it.

> Reply from Nat517
>
> And about the other error, yes it kept shows up and I have no idea what to do with it. I have python 2.7, which is recommended in this thread. I also tried a newer version of python (3.6), and it just kept saying "invalid syntax".
These scripts where meant to work with any python version 2.7.3 and up, not the other variant 3.x.x, ignore any version that is 3 and up, ONLY 2.7.3+.

For what game are you trying to get the audio from and I need to know the EXACT script your using for extraction/conversion, because some scripts have certain arguments disabled.
## Post #302
- Username: arkham45128
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 26, 2017 5:22 am
- Post datetime: 2018-02-25T11:09:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hi everyone!

I would like to have the Castillian Spanish audios of the videogame..... What do I have to do? Can someone explain that to me? Or could someone extract 'em and give'em to me?
Thanks!
## Post #303
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-25T22:52:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from arkham45128
>
> Hi everyone!

I would like to have the Castillian Spanish audios of the videogame..... What do I have to do? Can someone explain that to me? Or could someone extract 'em and give'em to me?
Thanks!
L O L, Seriously, does anyone know how to read these days? WTH???
If you go back on page 16 you'll see what you need to do to get them, DAMN.
## Post #304
- Username: atoqir
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 26, 2018 6:29 am
- Post datetime: 2018-02-25T23:52:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Can somebody but me in the right direction please. I tried for hours.

I have all the files I need and I extract the music files with the Universal Frostbite Extractor with the filter 'music'

In my dump directory is a one 'bundles' directory (no chunks) with lots of subdirs with EBX music files


When I run the Phyton script (I have the right version and DLL's and modified the file accordingly nothing happens. I just get a window that stays there forever and no music files are dropped in my directory I specified.

Any help is appreciated cause I have been looking for hours into this but can't find it. 

Python 2.7.3 (default, Apr 10 2012, 23:31:26) [MSC v.1500 32 bit (Intel)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> ================================ RESTART ================================
>>> 
XAS1 dll detected.
EASpeex dll detected.
EALayer3 tool detected.
>>>
## Post #305
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-26T00:13:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from atoqir
>
> In my dump directory is a one 'bundles' directory (no chunks) with lots of subdirs with EBX music files
And you will continue to stare at the screen for hours because you will never succeed to convert the audios only by EBX extraction.
EBX needs the chunks in order to convert, EBX link to the chunks files.
So go back in UFBE and make sure you do this:
In your filter type "sound" is for every audio that game has or "music" is just for music of the game.
then tick/check for:
-create subfolders, -ebx and -chunks, then do the python for conversion again.
assuming your using SWBF2 game.

oh and if that fails saying missing chunks and nothing from chunks is extracted, might as well dump the whole game to avoid other errors.
## Post #306
- Username: atoqir
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 26, 2018 6:29 am
- Post datetime: 2018-02-26T06:47:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Thanks I tried your suggestions and did a full dump. Chunks en bundles are there now.

The game I am trying is BattleField1. Does that need another script or is this the right one cause the script doesn't seem to be doing much. No errors or no progress. 

I script mentions BF4. Does it need modifications? I feel that I am very very close
## Post #307
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2018-02-26T14:20:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hi! I tried to import car chassis mesh from NFS Payback and the program gives me an error:



Other car parts (like bumpers, fenders, etc.) converts successfully, but car chassis is not. This error applies not only to this file, other car chassis meshes too. I used tools from 1st page (fb_models_faces) and UFBE 0.2.1. Can anyone help me, please? If you'll needs an any file from the game - I'll send it to your PM.
## Post #308
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-26T16:39:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from atoqir
>
> Thanks I tried your suggestions and did a full dump. Chunks en bundles are there now.

The game I am trying is BattleField1. Does that need another script or is this the right one cause the script doesn't seem to be doing much. No errors or no progress. 

I script mentions BF4. Does it need modifications? I feel that I am very very close
the audio script mentions BF4 because it was all started based on that game, and it was kept the same for other games, except other necessary editing that was made along he way to support other games, ignore it its not relevant.
All you have to do now is follow the conversion tutorial again and they should convert.
## Post #309
- Username: atoqir
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 26, 2018 6:29 am
- Post datetime: 2018-02-26T22:19:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I finally got it working however the soundscript extracts few folders and throws WindowsError: [Error -529697949] Windows Error 0xE06D7363

Oh well I just keep my fingers crossed and hope EA will release an official soundtrack like they did for the first DLCs.
## Post #310
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-26T22:31:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from atoqir
>
> I finally got it working however the soundscript extracts few folders and throws WindowsError: [Error -529697949] Windows Error 0xE06D7363

Oh well I just keep my fingers crossed and hope EA will release an official soundtrack like they did for the first DLCs.
That is a nasty error that even I couldn't get rid of or find a solution, only few people can know how to fix those, unfortunately most lost interest in this.

The only work around those errors is for you to remove the EBX that caused it, usually its the LAST file that was trying to be converted in the log before the error block, once you remove that file from the directory restart the conversion process and will continue, so on and so forth.
## Post #311
- Username: drakulaboy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 16, 2017 3:41 am
- Post datetime: 2018-03-15T15:20:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

so, how i extracted BF1 sounds/audio from DLC's
i used only 2 exe's from here swbf_cas.exe and xas_decode.exe
go to Battlefield 1\Data\Win32\installation\xpack2_install (xpack1_install or any map from there)
drag cas_01.cas (cas_02.cas, cas_03.cas etc) on swbf_cas.exe only one file, don't choose more files, and in xpack2_install will appear a lot of files, wait until the CMD window will close, we are interested of files who has extension .exa , drag a file on the xas_decode.exe and in the same folder will appear the audio file, some files won't convert  cheers

P.S.: don't try to unpack from \Battlefield 1\Patch\Win32\installation
you won't get any result
## Post #312
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-15T15:59:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from drakulaboy
>
> so, how i extracted BF1 sounds/audio from DLC's
This is bad idea. And you probably missed the thread. This thread offers proper way to extract and convert ALL audios with proper names. Not the old method from another thread that you used.
## Post #313
- Username: drakulaboy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 16, 2017 3:41 am
- Post datetime: 2018-03-15T16:11:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> drakulaboy wrote:so, how i extracted BF1 sounds/audio from DLC's
This is bad idea. And you probably missed the thread. This thread offers proper way to extract and convert ALL audios with proper names. Not the old method from another thread that you used.
okay, i dumped all files from the game with the Python script, and did not found all the russian DLC voices, now i wait to dump all files with UFE 0.2.1, i hope to get what i want, thank you for the tools
i was able to import meshes to 3ds max, now i want the sounds and that's all 
***
hats off to daemon1, with your tool i have more chunks than with Python script, with python script i haved only 103923 chunks with UFE - 138183 chunks
Dumping files...
322740 file(s) dumped successfully.
23221 file(s) failed because of chunk not found.
aaand UFE is a little bit faster than python script
going to find dlc's sounds/audio
***
EDIT: got all the sounds i was looking for, thank you!
## Post #314
- Username: streetracer23
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 28, 2014 8:51 pm
- Post datetime: 2018-03-17T10:57:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Please take tutorial for UFBE and please take screenshot UFBE at nfs pb before unpacking, i dont understend where add ticks at program . I unpank NFS PB
## Post #315
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-17T11:48:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from streetracer23
>
> Please take tutorial for UFBE and please take screenshot UFBE at nfs pb before unpacking, i dont understend where add ticks at program . I unpank NFS PB
tutorial is on the first page!
## Post #316
- Username: BaronRevan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 22, 2018 12:57 am
- Post datetime: 2018-03-21T18:47:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I'm so sorry... I'm a complete noob to this stuff so reading through all this confuses me so much lol. I'm trying to extract the audio files for vaders lightsaber into a readable audio format.. I have managed to dump the files to the .ebx format but have no idea what to do from here...
## Post #317
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-03-22T04:08:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from BaronRevan
>
> I'm so sorry... I'm a complete noob to this stuff so reading through all this confuses me so much lol. I'm trying to extract the audio files for vaders lightsaber into a readable audio format.. I have managed to dump the files to the .ebx format but have no idea what to do from here...
Even though you say it confuses you so much, it has been explained so many times, in so many ways.
From the looks of it you forgot to dump the chunks as well, ebx files are useless with out the actual audio files from the chunks folder.
If you go on page 16 you'll find your answer there, towards bottom of the page in my comment, very well explained.
If you actually read the WHOLE thing I don't understand how you could have missed that.
## Post #318
- Username: Nomadicus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 03, 2018 11:44 am
- Post datetime: 2018-04-03T23:21:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I am also only looking for the audio from BFII and I've gone through all 22 pages of this topic, including the infamous Page 16, and I'm pretty sure I've followed all of the instructions correctly. As this is practically all Klingon to me there is a chance I overlooked something. The error I am getting, however, is a syntax error when I press F5 in the IDLE script. I haven't seen any other mention of a syntax error by anyone else.
[syntax.jpg](https://xentaxbackup.github.io/file/14164_syntax.jpg)
## Post #319
- Username: BaronRevan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 22, 2018 12:57 am
- Post datetime: 2018-04-03T23:44:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Nomadicus
>
> I am also only looking for the audio from BFII and I've gone through all 22 pages of this topic, including the infamous Page 16, and I'm pretty sure I've followed all of the instructions correctly. As this is practically all Klingon to me there is a chance I overlooked something. The error I am getting, however, is a syntax error when I press F5 in the IDLE script. I haven't seen any other mention of a syntax error by anyone else.

A lot of people on here have been rude and not very helpful honestly. I’ve followed the I tructions to the best of my abilities and I’m just as confused as when my girlfriend speaks portreguese to me lol.
## Post #320
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-04T15:21:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Nomadicus
>
> including the infamous Page 16
really?

this is the quote from page 16:

> Reply from mono24
>
> -make sure you have python 2.7.3 32bit installed,
## Post #321
- Username: BaronRevan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 22, 2018 12:57 am
- Post datetime: 2018-04-04T16:19:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> Nomadicus wrote:including the infamous Page 16
really?

this is the quote from page 16:
mono24 wrote:-make sure you have python 2.7.3 32bit installed,

Honestly though, thank you for all the work you’ve done on these tools. You yourself have always been helpful and willing to be of service. Just that for a newbie this can be really confusing lol
## Post #322
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-04T17:19:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

hey guys:) please help me i don understand i change corectly patch in script but i have traceback
Traceback (most recent call last):
  File "(...my patch...)", line 42, in <module>
    LZ77 = cdll.LoadLibrary("LZ77")
  File "C:\Python27\lib\ctypes\__init__.py", line 443, in LoadLibrary
    return self._dlltype(name)
  File "C:\Python27\lib\ctypes\__init__.py", line 365, in __init__
    self._handle = _dlopen(self._name, mode)
WindowsError: [Error 193] %1 nie jest prawidłową aplikacją systemu Win32
## Post #323
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-04T17:21:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Nomadicus
>
> I am also only looking for the audio from BFII and I've gone through all 22 pages of this topic, including the infamous Page 16, and I'm pretty sure I've followed all of the instructions correctly. As this is practically all Klingon to me there is a chance I overlooked something. The error I am getting, however, is a syntax error when I press F5 in the IDLE script. I haven't seen any other mention of a syntax error by anyone else.

you have wrong python you need 2.7.3
## Post #324
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-04T17:28:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from satan0w
>
> hey guys:) please help me i don understand
you have wrong python you need 32 bit
## Post #325
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-04T19:48:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> satan0w wrote:hey guys:) please help me i don understand
you have wrong python you need 32 bit

Thanks now work perfect:D
## Post #326
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-04T19:58:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> satan0w wrote:hey guys:) please help me i don understand
you have wrong python you need 32 bit

you can explain me why script create folder chunks and other but all folders is empty i have 94 gb free space i see folder names from nfs but all empty please help me i need a teach this:)
## Post #327
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-04-05T05:22:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Hi all
I have been trying to extract from Hardline by using the BF4 script but Perhaps i’m using the wrong one beacuse i can’t Seem to get it working

So do anyone know wich script i need to use or have a link to the script thanks
## Post #328
- Username: Nomadicus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 03, 2018 11:44 am
- Post datetime: 2018-04-05T07:30:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> Nomadicus wrote:including the infamous Page 16
really?

this is the quote from page 16:
mono24 wrote:-make sure you have python 2.7.3 32bit installed,

Ok clearly I didn't look at the version number. I guess that is because I'm pretty sure I downloaded python through a link within this thread so I assumed it was the correct one without looking close enough. Do I have a newer version installed somehow?
## Post #329
- Username: Nomadicus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 03, 2018 11:44 am
- Post datetime: 2018-04-05T07:35:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Nomadicus
>
> daemon1 wrote:Nomadicus wrote:including the infamous Page 16
really?

this is the quote from page 16:
mono24 wrote:-make sure you have python 2.7.3 32bit installed,

Ok clearly I didn't look at the version number. I guess that is because I'm pretty sure I downloaded python through a link within this thread so I assumed it was the correct one without looking close enough. Do I have a newer version installed somehow?

Ah I see, I had gotten to the python website and then went right to the "Downloads" tab which gives one a much newer version. It didn't occur to me that I would need an "obsolete" version of the software as I don't believe anybody had explicitly stated this.

EDIT: after getting around the syntax error with the correct version, I was having a .dll error. While going back through to research this I discovered another comment where it was explained that you need the older version. I don't know how I missed that one except maybe my eyeballs were bleeding by that point after reading 20 pages of this stuff, for the first time ever. Much to my embarrassment, as I hate it when I see posts from people who jump in 20 pages into a thread and say "explain it all to me so I don't have to bother reading anything prior to my own post", and I really thought I had followed everything correctly.
## Post #330
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-05T13:19:04+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

whoever met with chunk not found? I have this message in every frosbite game nfs16 , nfs payback , bf1 ,swbf2:(
i read all but still dont understand this:(
## Post #331
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-05T20:50:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

LoL i am idiot    i read all pages six times and six times i tried set good game and folders and.... FINNALY I UNNDERSTAND   60% but is ok extracted all files from game    thanks for script you best
## Post #332
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-05T23:24:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from satan0w
>
> whoever met with chunk not found? I have this message in every frosbite game nfs16 , nfs payback , bf1 ,swbf2:(
i read all but still dont understand this:(
Or you can just use daemon1's UFBE extractor to save yourself of headache and errors.
## Post #333
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-06T00:40:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

hmm i use all mesh.exe and all give me two files but have 0KB meaby somone have solution for this? i need cars from nfs payback i have all game unpacked and also i tried like tutorial but not work
## Post #334
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-06T00:46:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from satan0w
>
> hmm i use all mesh.exe and all give me two files but have 0KB meaby somone have solution for this? i need cars from nfs payback i have all game unpacked and also i tried like tutorial but not work
What I get from what your saying is that you forgot to have in same folder the skeleton.ebx file, that's why you get 0kb in size, no one can really help and just guess, if you guys don't explain what you did exactly so we can see what's going on.
Go trough the steps once more, follow it carefully and see what's going on.
## Post #335
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-06T18:33:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> satan0w wrote:hmm i use all mesh.exe and all give me two files but have 0KB meaby somone have solution for this? i need cars from nfs payback i have all game unpacked and also i tried like tutorial but not work
What I get from what your saying is that you forgot to have in same folder the skeleton.ebx file, that's why you get 0kb in size, no one can really help and just guess, if you guys don't explain what you did exactly so we can see what's going on.
Go trough the steps once more, follow it carefully and see what's going on.

i have folder working inside working have chunks and textures folders and ebx and mesh file np that car_chevrolet_belair_1955_suspensionr_setorxa_skeleton.ebx i copy all files from folders witch name belair to working and also copy inside folder Fb_SWBF2_mesh and Fb_NFSPB_mesh and when i click on Fb_NFSPB_mesh this give me ascii 0kb and smd 0KB i tryied all tools from mesh tool folder but not working meaby is damaged? dump give me 0 missing files

i tried drop on exe ebx and mesh files this give me files 0kb
i tried run exe but (error and closed) win 10 i tryied with win 7 and admin and also not work
also i tried scripts to 3dmax from bf1 for vehicles or ebx to txt script also not working
## Post #336
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-06T18:47:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

rename
car_chevrolet_belair_1955_suspensionr_setorxa_skeleton.ebx
to 
walrus_humanmale.ebx
## Post #337
- Username: satan0w
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 05, 2018 1:14 am
- Post datetime: 2018-04-06T19:22:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> rename
car_chevrolet_belair_1955_suspensionr_setorxa_skeleton.ebx
to 
walrus_humanmale.ebx

ok i try this but if mazda dont have skeleton what i must?
i go to bundles ->vehicles ->player ->car_mazda_rx7spiritr_2002 and all files for mazda in this folder


[https://imgur.com/a/QNX9W](https://imgur.com/a/QNX9W)
## Post #338
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-07T02:11:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from satan0w
>
> 
ok i try this but if mazda dont have skeleton what i must?
i go to bundles ->vehicles ->player ->car_mazda_rx7spiritr_2002 and all files for mazda in this folder


https://imgur.com/a/QNX9W
Well now that I know what is your talking about, its already been answered, here:
[viewtopic.php?f=16&t=17236&p=138712#p138712](http://forum.xentax.com/viewtopic.php?f=16&t=17236&p=138712#p138712)

BUT, from what I can see in your image, something went wrong with your extraction, there are no .MeshSet extracted to work with, .MeshSet is needed for geometry.
What did you extract it with?
## Post #339
- Username: projectno253
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 13, 2018 2:11 am
- Post datetime: 2018-04-24T04:03:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I was able to extract most of the audio files, thanks to daemon and everyone here who posted their issues and how they were solved.

Does anyone have the z6 riot baton sounds from the a3 folder? I don't get any audio files when running the audio decoder. I think it might be because it's part of the SP addition/update and not the original game. 

Thanks for any help.

***
edit: I was able to get extract the riot baton effects (all 3 of them...) by using the SWBF2full python script on the patch folder. Thanks again for the tools.
## Post #340
- Username: drakulaboy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 16, 2017 3:41 am
- Post datetime: 2018-04-25T16:35:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

i'm able to convert 3d models with "Chunk and Mesh file management tool BF1" and MaxScripts in 3ds max after extracting with python script, but with UFBE and "Fb_BF1_mesh.exe" i fail, 

```

Unhandled Exception: System.IndexOutOfRangeException: Index was outside the bounds of the array.
   at FB_faceposer.FB_faceposer.Main(String[] args)
```


tried with all skeletons from bundles\characters\skeletons\character , still the same
## Post #341
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-25T16:47:04+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from drakulaboy
>
> i'm able to convert 3d models with "Chunk and Mesh file management tool BF1" and MaxScripts in 3ds max after extracting with python script, but with UFBE and "Fb_BF1_mesh.exe" i fail, 
Code: Select allE:\BF1 dump2>Fb_BF1_mesh.exe mp_pigeon01_mesh.MeshSet

Unhandled Exception: System.IndexOutOfRangeException: Index was outside the bounds of the array.
   at FB_faceposer.FB_faceposer.Main(String[] args)

tried with all skeletons from bundles\characters\skeletons\character , still the same
you have to provide chunk name as second parameter
## Post #342
- Username: projectno253
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 13, 2018 2:11 am
- Post datetime: 2018-04-25T19:48:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Is there a way to extract a specific chunk from a patch if I have the chunk name? I've been using the swbf2full script in the patch folder, but nothing so far seems to be getting the right chunk. Lots of "chunk not found" when running the script and occasionally getting to chunks0.toc and extracting chunks for some elements. 

I got the chunk ID for the audio file I'm looking to get by converting the ebx file to text.

***
edit: happened to get the right chunk for the file. Posting in case anyone else wants to know how to get patch files out...
## Post #343
- Username: drakulaboy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 16, 2017 3:41 am
- Post datetime: 2018-04-25T20:09:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> you have to provide chunk name as second parameter

omg, thank you, i thought it will find automaticly from chunk folder
## Post #344
- Username: Scyn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 22, 2018 2:44 pm
- Post datetime: 2018-04-26T05:16:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I'm having an issue with the face poser, I'm getting a "Asset not found in asset banks (2)" error when I try dragging vur_darthmaul_01.ebx onto Fb_SWBF2_faces.exe . When I extracted the files for SWBF2, I got 174 missing chunks. [https://i.imgur.com/Q0SWqE4.png](https://i.imgur.com/Q0SWqE4.png) When I drag it the vur file onto the faces.exe, the cmd prompt shows up for half a second and closes. When I manually try to run it, I get Asset not found in asset banks (2) [https://i.imgur.com/yv6pgED.png](https://i.imgur.com/yv6pgED.png). My files are set up like this
working folder: [https://i.imgur.com/qLMaK0T.png](https://i.imgur.com/qLMaK0T.png)
head folder: [https://i.imgur.com/coqqREw.png](https://i.imgur.com/coqqREw.png)
assetbank folder: [https://i.imgur.com/Z2zW3vh.png](https://i.imgur.com/Z2zW3vh.png)

I was reading the thread and I might have misunderstood, but I gathered the missing chunks are because of the DLCs/patches? I'm not sure if thats completely right. I've brought the folder back to Origin and repaired it and re-unpacked it with the same result. Do you know what I'm doing wrong?
I'm following Croftys tutorial here. [https://sta.sh/04jxcv9d9o0](https://sta.sh/04jxcv9d9o0)
## Post #345
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2018-06-09T17:07:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

i can't covert .ebx files into .wav from NFS payback using the script fb3decoder.py, every time i run the script after some conversion it stops and it says:

```
veh_gear_shift_classic_down.ebx
veh_gear_shift_classic_up.ebx
veh_gear_shift_performance_down.ebx
veh_gear_shift_performance_up.ebx
veh_gear_shift_race_down.ebx
veh_gear_shift_race_up.ebx
veh_gear_shift_sport_down.ebx
veh_gear_shift_sport_up.ebx
veh_gear_shift_stock_down.ebx
veh_gear_shift_stock_up.ebx
nfs18_carhorn.ebx
playerhorn_baseconfig.ebx
veh_horn_audi_a4_0_dualtone_420hz-480hz.ebx

Traceback (most recent call last):
  File "C:\Users\Utente\Desktop\ebx\fb3audio_nfs.py", line 550, in <module>
    main()
  File "C:\Users\Utente\Desktop\ebx\fb3audio_nfs.py", line 548, in main
    dbx.decode()
  File "C:\Users\Utente\Desktop\ebx\fb3audio_nfs.py", line 500, in decode
    decodePcm(currentChunkName, target, 0)
  File "C:\Users\Utente\Desktop\ebx\fb3audio_nfs.py", line 75, in decodePcm
    xas.swapEndianPcm(chunkPath, target, samplesOffset)
NameError: global name 'xas' is not defined
```


What can i do to fix this? Thanks a lot!
## Post #346
- Username: Crageo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 15, 2016 2:28 pm
- Post datetime: 2018-06-10T02:58:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Is this script and the UFBE going to be updated? Since they broke extracting?
## Post #347
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-10T03:57:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from Crageo
>
> Is this script and the UFBE going to be updated? Since they broke extracting?
Unfortunately when comes about Battlefront II game based on recent updates ONLY [Frosty v1.0.4.2](https://frostytoolsuitedev.gitlab.io/downloads.html) can gain access to its contents, for mas extraction of the WHOLE GAME DATA nothing that exists out there will work, who knows maybe in the future it will be supported by UFBE.
## Post #348
- Username: Crageo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 15, 2016 2:28 pm
- Post datetime: 2018-06-10T18:01:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Damn, thats a bummer. Cheers anyway man.
## Post #349
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2018-06-14T19:22:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

i can't covert .ebx files into .wav from NFS payback using the script fb3decoder.py, every time i run the script after some conversion it stops and it says:

```
  File "D:\alisu\Desktop\non usati\-Estrattori suoni + config backup-\estrattore battlefield-rivals\boh\convertitore ebx in wav\prova\fb3audio_nfs.py", line 550, in <module>
    main()
  File "D:\alisu\Desktop\non usati\-Estrattori suoni + config backup-\estrattore battlefield-rivals\boh\convertitore ebx in wav\prova\fb3audio_nfs.py", line 548, in main
    dbx.decode()
  File "D:\alisu\Desktop\non usati\-Estrattori suoni + config backup-\estrattore battlefield-rivals\boh\convertitore ebx in wav\prova\fb3audio_nfs.py", line 500, in decode
    decodePcm(currentChunkName, target, 0)
  File "D:\alisu\Desktop\non usati\-Estrattori suoni + config backup-\estrattore battlefield-rivals\boh\convertitore ebx in wav\prova\fb3audio_nfs.py", line 75, in decodePcm
    xas.swapEndianPcm(chunkPath, target, samplesOffset)
NameError: global name 'xas' is not defined
```


What can i do to fix this? Thanks a lot!
## Post #350
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-06-15T13:17:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Whenever I try to "scan bundles" with UFBE, it finds 0 bundles. I figured something was wrong, but tried dumping anyway. It instantly gave this log:

```
0 EBX, 0 duplicates
0 res, 0 duplicates
0 chunks, 0 duplicates, 0 unique chunks
0 total.

Scanning CAS database...
412406 entries, 36696 precache entries, 1102076 duplicated entries.

Dumping files...
0 file(s) dumped seccessfully.
```

If I try using swbf2full.py, the moment I press run, it says:

```
 RESTART: D:\Program Files\Origin Games\STAR WARS Battlefront II\Tools\swbf2 dumper script\swbf2full.py 
```
 and doesn't do anything.

Any help would be appreciated,
TrumpetPro
## Post #351
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-15T13:27:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from TrumpetPro
>
> Whenever I try to "scan bundles" with UFBE, it finds 0 bundles
in latest update SWBF removed all SB/TOC files. UFBE doesnt support this game currently.

python scripts will not work either
## Post #352
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-06-15T13:29:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> TrumpetPro wrote:Whenever I try to "scan bundles" with UFBE, it finds 0 bundles
in latest update SWBF removed all SB/TOC files. UFBE doesnt support this game currently.

python scripts will not work either
Oh OK. Any plans to fix the tool?
## Post #353
- Username: parzivail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 04, 2016 5:46 am
- Post datetime: 2018-06-17T19:28:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from TrumpetPro
>
> daemon1 wrote:TrumpetPro wrote:Whenever I try to "scan bundles" with UFBE, it finds 0 bundles
in latest update SWBF removed all SB/TOC files. UFBE doesnt support this game currently.

python scripts will not work either
Oh OK. Any plans to fix the tool?

The Frosty editor program is written in .NET, so it should be trivial to decompile it, see how it finds and loads files inside of the archives, and write a script that mimics that functionality to dump every file instead of just specific ones. I'll leave the implementation to the original Python script developers since they've been doing pretty good so far on their own.
## Post #354
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-06-17T23:50:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from parzivail
>
> 

The Frosty editor program is written in .NET, so it should be trivial to decompile it, see how it finds and loads files inside of the archives, and write a script that mimics that functionality to dump every file instead of just specific ones. I'll leave the implementation to the original Python script developers since they've been doing pretty good so far on their own.
[https://frostytoolsuitedev.gitlab.io/news.html](https://frostytoolsuitedev.gitlab.io/news.html)
If you look here, it seems the new SWBF2 uses a sort of filelist.
## Post #355
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-24T08:55:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from TrumpetPro
>
> Oh OK. Any plans to fix the tool?
i doubt i will have time for it this year
maybe in 2019
only maybe!
## Post #356
- Username: mrbeanjoga
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 27, 2018 11:49 am
- Post datetime: 2018-06-27T03:53:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

can i export animations?
## Post #357
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-27T04:13:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mrbeanjoga
>
> can i export animations?No, but I am sure in the future that will be available in some form, there is a lot of interest by many out there, time will tell.
But to answer your question better, any asset the game has, animations included, can be exported, just cant be converted yet to usable formats that are known.
## Post #358
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2018-07-09T00:05:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Trying to get some NFS Rivals 3d map files, I've used bf4dumper python script from bfeditorORG. After +2h and an error, I've got many stuff exctracted (even if not all, due to an error) but not a single meshset file so I could use the MeshFile_Type_Reader... Trying to look every page of the forum, no solution for now. What is my error, folks?

btw. strange thing, walking around for another solution to extract Rivals game map meshes, I went to look for nfs edge. If one of you guys have seen the nfs edge file structure (which is kinda chinese modified nfs rivals), there are no cas/cat files and win32 folder contains .sb and .toc files, even the Data folder has only .das files,
should I forget nfs edge?..
[data.JPG](https://xentaxbackup.github.io/file/14580_data.JPG)
## Post #359
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-09T02:54:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from eyewee
>
> Trying to get some NFS Rivals 3d map files, I've used bf4dumper python script from bfeditorORG. After +2h and an error, I've got many stuff exctracted (even if not all, due to an error) but not a single meshset file so I could use the MeshFile_Type_Reader... Trying to look every page of the forum, no solution for now. What is my error, folks?
The game can be extracted easily with out errors and all assets in order and yes it can take hours, tell me your steps, what you did, what you used exactly and I am more than happy to help you get it all dumped.
Because there are so many scripts variations out there that its not even funny anymore, that is why Daemon wanted to be a universal Frostbite dumper for all games, its just is limited for now, and until then python scripts will do just fine.

> Reply from eyewee
>
> btw. strange thing, walking around for another solution to extract Rivals game map meshes, I went to look for nfs edge. If one of you guys have seen the nfs edge file structure (which is kinda chinese modified nfs rivals), there are no cas/cat files and win32 folder contains .sb and .toc files, even the Data folder has only .das files,
should I forget nfs edge?..
I am sure someday an extractor/dumper will surface by whomever wants to tackle it, until then it cant be extracted, because I too am interested.
## Post #360
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2018-07-09T11:10:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Well, first I used Bf4 Sbtoc Dumper by Frankelstner, than I wait for a while and I get this error :

```
D:\JEUX - GAMES\NFS RIVALS DUMPED/bundles/res/levels/hp2/worldassets/rural/r03/dz1/brdg_r03_kingfisher_construction_platform_ramps/brdg_r03_kingfisher_construction_platform_ramps_mesh 64d29a3d3c053add b01b000000000000fc0000007000c000.mesh
D:\JEUX - GAMES\NFS RIVALS DUMPED/bundles/res/levels/hp2/worldassets/rural/r03/dz1/brdg_r03_kingfisher_construction_platform_ramps/brdg_r03_kingfisher_construction_platform_ramps_part_physics_win32 e83efae03aed4fef 8000000060090000400b0000f8010000.hknondestruction

Traceback (most recent call last):
  File "D:\JEUX - GAMES\FrostBite Tools\BFEDITOR.ORG METHOD\bf4dumper\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "D:\JEUX - GAMES\FrostBite Tools\BFEDITOR.ORG METHOD\bf4dumper\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "D:\JEUX - GAMES\FrostBite Tools\BFEDITOR.ORG METHOD\bf4dumper\bf4dumper.py", line 179, in dump
    writePayload(entry, targetPath, sourcePath)
  File "D:\JEUX - GAMES\FrostBite Tools\BFEDITOR.ORG METHOD\bf4dumper\bf4dumper.py", line 213, in casPayload
    LZ77.decompress(catEntry.path,catEntry.offset,catEntry.size, bundleEntry.originalSize,targetPath)
WindowsError: [Error -529697949] Windows Error 0xE06D7363
```

Whereas +5Gb of the game is already extracted. Not having much choise with this repeating error, I run Bf3_MeshFile_Type_Reader from here on xentax, I click on bf4 (otherwise it doesnt work) and the tool sorts all available chunks and meshes together. That's it, at this final stage I only get .mesh and chunk files, also itexture, which is, as I see, must not a big deal to transform into dds.
Now, what shall I do to get the 3d files with coordinates (talking about 3d map files)? As I've seen here [viewtopic.php?f=10&t=7679&start=75](http://forum.xentax.com/viewtopic.php?f=10&t=7679&start=75)
with nfs the run, map files have coords in the name of the file, which will be quite easy to just use these coords and put every piece in its place in order to assemble the entire map in 3ds max (or blender if not?).


> Reply from mono24
>
> 
The game can be extracted easily with out errors and all assets in order and yes it can take hours, tell me your steps, what you did, what you used exactly and I am more than happy to help you get it all dumped.
Because there are so many scripts variations out there that its not even funny anymore, that is why Daemon wanted to be a universal Frostbite dumper for all games, its just is limited for now, and until then python scripts will do just fine.

I am sure someday an extractor/dumper will surface by whomever wants to tackle it, until then it cant be extracted, because I too am interested.
## Post #361
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-09T15:56:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from eyewee
>
> Well, first I used Bf4 Sbtoc Dumper by Frankelstner
Before you begin make sure to delete what you already dumped to start from scratch.

This is the script you need to make it work, [viewtopic.php?p=116879#p116879](http://forum.xentax.com/viewtopic.php?p=116879#p116879) but it will be a bit tricky so you have to do the following.
Make sure your paths are set correctly here:

```
outputfolder="X:\YOUR PATH\NFSR_dump"

```

On these two lines make sure there is small "p" not capital "P" on PatchedCatName like this patchedCatName, and do not change anything else:

```
patchedCatName=bf4Directory+"\\"+r"Update\Patch\Data\cas.cat" #used only when tocRoot contains "Update"

```

On the next two lines you first run the script like this, to extract updates/patches first:

```
##tocRoot=bf4Directory+"\\"+r"Data\Win32"
```

Now you replace the whole resTypes from here:

```
    0x5C4954A6:".itexture",
    0x2D47A5FF:".gfx",
    0x22FE8AC8:"",
    0x6BB6D7D2:".streamingstub",
    0x1CA38E06:"",
    0x15E1F32E:"",
    0x4864737B:".hkdestruction",
    0x91043F65:".hknondestruction",
    0x51A3C853:".ant",
    0xD070EED1:".animtrackdata",
    0x319D8CD0:".ragdoll",
    0x49B156D4:".mesh",
    0x30B4A553:".occludermesh",
    0x5BDFDEFE:".lightingsystem",
    0x70C5CB3E:".enlighten",
    0xE156AF73:".probeset",
    0x7AEFC446:".staticenlighten",
    0x59CEEB57:".shaderdatabase",
    0x36F3F2C0:".shaderdb",
    0x10F0E5A1:".shaderprogramdb",
    0xC6DBEE07:".mohwspecific"
}
```

With an up to date one like this:

```
    0xC6DBEE07:".AnimatedPointCloud",
    0xD070EED1:".AnimTrackData",
    0x51A3C853:".AssetBank",    
    0x957C32B1:".AtlasTexture",
    0x428EC9D4:".BundleRefTableResource",
    0xAFECB022:".CompiledLuaResource",
    0xF04F0C81:".Dx11ShaderProgramDatabase",
    0xBCC7FB86:".Dx11Texture",
    0xE565EB15:".DxShaderDatabase",
    0x10F0E5A1:".DxShaderProgramDatabase",
    0x5C4954A6:".DxTexture",
    0x85AC783D:".EAClothAssetData",
    0x387CA0AD:".EAClothData",
    0x85EA8656:".EAClothEntityData", 
    0x70C5CB3E:".EnlightenDatabase",
    0xE156AF73:".EnlightenProbeSet",
    0x59CEEB57:".EnlightenShaderDatabase",
    0xC6CD3286:".EnlightenStaticDatabase",
    0x5BDFDEFE:".EnlightenSystem",
    0x59C79990:".FaceFXResource",
    0xEF23407C:".FifaPhysicsResourceData",
    0xE36F0D59:".HavokClothPhysicsData",
    0x4864737B:".HavokDestructionPhysicsData",
    0x91043F65:".HavokPhysicsData",
    0xEB228507:".HeadMorphResource",
    0x9C4FAA17:".HeightfieldDecal",
    0x0DEAFE10:".IesResource",
    0xC78B9D9D:".ImpulseResponse",
    0x36F3F2C0:".IShaderDatabase",
    0xC417BBD3:".ITexture",
    0xAD1AC4FD:".LargeParticleCloud",
    0x86521D6C:".LinearMediaAsset",
    0x5E862E05:".LocalizedStringResource",
    0xBA02FEE0:".MeshAdjacencyResource",
    0xC611F34A:".MeshEmitterResource",
    0x49B156D4:".MeshSet",
    0x1091C8C5:".MorphTargetsResource",
    0x31E779A2:".MovieTexture",
    0xB2C465F6:".NewWaveResource",
    0x30B4A553:".OccluderMesh",
    0xC664A660:".PamReplayResource",
    0x8D9E6F01:".PcaComponentWeightsResource",
    0x41759364:".PhysicsResource",
    0x52EE0D39:".PlayerPresetResource",
    0x3B9D1688:".PSDResource",
    0x319D8CD0:".RagdollResource",
    0x3568E2B7:".RawFileData",
    0x41D57E10:".RenderTexture",
    0x7AEFC446:".StaticEnlightenDatabase",
    0x2D47A5FF:".SwfMovie",
    0x6BB6D7D2:".Terrain",
    0x15E1F32E:".TerrainDecals",
    0xA23E75DB:".TerrainLayerCombinations",
    0x22FE8AC8:".TerrainStreamingTree",
    0x6BDE20BA:".Texture",
    0x9D00966A:".UITtfFontFile",
    0x1CA38E06:".VisualTerrain",
    0xEFC70728:".ZoneStreamerGrid",
}
```

Now you run the script and extraction will start and once it stops and it will show this in the last line:

```
>>>
```

You go back to the script and make this modification ONLY to extract the Data folder to finalize the whole game dump assets:

```
tocRoot=bf4Directory+"\\"+r"Data\Win32"
```

And everything should be dumped nicely, once you see again in the end this line you know its done:

```
>>>
```


> Reply from eyewee
>
> Now, what shall I do to get the 3d files with coordinates (talking about 3d map files)? As I've seen here viewtopic.php?f=10&t=7679&start=75
with nfs the run, map files have coords in the name of the file, which will be quite easy to just use these coords and put every piece in its place in order to assemble the entire map in 3ds max (or blender if not?).
As far as I  know there are no coordinates in any file names for NFSTheRun, if I remember correctly the EBXs hold coordinates for some of the assets not sure about the actual map geometry, but I as well would like to have all NFS games as a map extracted for modding/art rendering and all those good stuff, until that's possible we use what we have already workable.
## Post #362
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2018-07-10T13:30:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> 

This is the script you need to make it work, viewtopic.php?p=116879#p116879 but it will be a bit tricky so you have to do the following.

Unfortunately, I'm getting this error :

```
D:\JEUX - GAMES\NFSR_dump\chunks\0080f1b8dce08bc320ef072a0ec6a849.chunk

Traceback (most recent call last):
  File "D:\JEUX - GAMES\FrostBite Tools\XENTAX V2\BF_Four_Python_Scripts\dumper.py", line 403, in <module>
    main()
  File "D:\JEUX - GAMES\FrostBite Tools\XENTAX V2\BF_Four_Python_Scripts\dumper.py", line 400, in main
    dump(fname,outputfolder)
  File "D:\JEUX - GAMES\FrostBite Tools\XENTAX V2\BF_Four_Python_Scripts\dumper.py", line 231, in dump
    casHandlePayload(entry,chunkPathToc+hexlify(entry.elems["id"].content)+".chunk")
  File "D:\JEUX - GAMES\FrostBite Tools\XENTAX V2\BF_Four_Python_Scripts\dumper.py", line 375, in casHandlePayload
    LZ77.decompressAndWriteUnknownFile(catEntry.filename,catEntry.offset,catEntry.size,outPath)
  File "C:\Program Files (x86)\Python2.7.4 32bit\lib\ctypes\__init__.py", line 378, in __getattr__
    func = self.__getitem__(name)
  File "C:\Program Files (x86)\Python2.7.4 32bit\lib\ctypes\__init__.py", line 383, in __getitem__
    func = self._FuncPtr((name_or_ordinal, self))
AttributeError: function 'decompressAndWriteUnknownFile' not found
```

I think it might be due to something in my python program or library?
[nfs-sb-unpacked_zpscf88d2bc.jpg](https://xentaxbackup.github.io/file/14584_nfs-sb-unpacked_zpscf88d2bc.jpg)
## Post #363
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-10T17:29:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from eyewee
>
> Unfortunately, I'm getting this error :
Code: Select allAttributeError: function 'decompressAndWriteUnknownFile' not found
I think it might be due to something in my python program or library?
Well, you are using a python version between 2.7.3 32bit and up to latest build which is 2.7.15 32bit, which is good, so just uninstall it completely, then install it back but in full in its default location, seems that something is wrong with python installation, might be because its inside Program Files and might have a permission issue, so to avoid speculating just do a full default re-install, otherwise the extraction should have been very smooth.

And about NFSTR, from your screenshot I immediately recognized the extraction was made with the Frostbite.bms script by Luigi, which is NOT recommended as well, that script can NOT extract SuperBundles/BluprintBundles such as in NFSTR, all of those in your screenshot are SuperBundles that have a lot of assets that  needs to be dumped.
And they look like this after proper extraction, the rest of the assets are of course spread out in they're designated location such as EBXs, MeshSets, Textures etc etc etc, only Havok data is in the 885 folders as you can see.
## Post #364
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2018-07-11T19:21:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
>  and might have a permission issue, so to avoid speculating just do a full default re-install, otherwise the extraction should have been very smooth.

Now, everything is fine, successfully extracted all the game, and now, how shall I extract the game mesh and these map files so I could start working with an already textured meshes?

> Reply from mono24
>
> And about NFSTR, from your screenshot I immediately recognized the extraction was made with the Frostbite.bms script by Luigi, which is NOT recommended as well, that script can NOT extract SuperBundles/BluprintBundles such as in NFSTR, all of those in your screenshot are SuperBundles that have a lot of assets that  needs to be dumped.
And they look like this after proper extraction, the rest of the assets are of course spread out in they're designated location such as EBXs, MeshSets, Textures etc etc etc, only Havok data is in the 885 folders as you can see.

You'r right, and as I see, every folder indicates the mesh coordinates in the 3d world? I couldn't find these coords in payback, for instance, even if NFSPB can be opened with FrostyTools...
## Post #365
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-11T23:20:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from eyewee
>
> how shall I extract the game mesh and these map files so I could start working with an already textured meshes?
Now what you want specifically does not exist, such as an already textured meshe conversion, the only thing that I have working on my end is for meshes ONLY, [UU3D](https://www.unwrap3d.com/u3d/index.aspx).
And everything has to be done manually, every texture every material, you name it.
I can pretty much help with extraction as I already did, but the textures, the meshes conversion etc etc, your on your own, I never found a specific conversion tool for a lot of the Frostbite games unfortunately.

Try and do a forum research for the following:
for textures look for: Batch_Itexture_Converter, there are many out there for various Frostbite games try and see what works.
for meshes look for: Chunk and Mesh file management tool or MeshFile_Type_Reader, see what you come up with, there used to be some 3dsMax scripts to work with the games but limited, see if you can find anything, I never dealt with that so I don't know what works.

> Reply from eyewee
>
> You'r right, and as I see, every folder indicates the mesh coordinates in the 3d world? I couldn't find these coords in payback, for instance, even if NFSPB can be opened with FrostyTools...
Those sector/section coordinates or if I can even call them that, are for the HavokPhysicsData, has nothing to do with the actual meshes themselves, those that are more knowledgeable can correct me if I am wrong, I personally only found some coordinates inside EBX files, this is a bit more complex even for me.
Of all the Frostbites games I dumped only NFSTR and MOHW has those kind of folders.

PS: The Frosty Editor developer works on supporting the NFSRivals games among others, and hes working on loading full levels inside the Editor for the supported Frostbite games, but he said he is not decided yet if he will allow full level conversion to known formats such as fbx, obj/mtl, dae etc.
## Post #366
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2018-07-14T13:47:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> 
And everything has to be done manually, every texture every material, you name it.
I can pretty much help with extraction as I already did, but the textures, the meshes conversion etc etc, your on your own, I never found a specific conversion tool for a lot of the Frostbite games unfortunately.

Try and do a forum research for the following:
for textures look for: Batch_Itexture_Converter, there are many out there for various Frostbite games try and see what works.
for meshes look for: Chunk and Mesh file management tool or MeshFile_Type_Reader, see what you come up with, there used to be some 3dsMax scripts to work with the games but limited, see if you can find anything, I never dealt with that so I don't know what works.
eyewee wrote:You'r right, and as I see, every folder indicates the mesh coordinates in the 3d world? I couldn't find these coords in payback, for instance, even if NFSPB can be opened with FrostyTools...
Those sector/section coordinates or if I can even call them that, are for the HavokPhysicsData, has nothing to do with the actual meshes themselves, those that are more knowledgeable can correct me if I am wrong, I personally only found some coordinates inside EBX files, this is a bit more complex even for me.
Of all the Frostbites games I dumped only NFSTR and MOHW has those kind of folders.

PS: The Frosty Editor developer works on supporting the NFSRivals games among others, and hes working on loading full levels inside the Editor for the supported Frostbite games, but he said he is not decided yet if he will allow full level conversion to known formats such as fbx, obj/mtl, dae etc.

I've talked to these genious frosty editor developpers on discord, it seems to be quite impossible to get the coordinates...at least, more than 20%, everything else is hidden, as u've said, in this havok data. In fact, they are working on a map editor tool inside frosty editor, but until then, there'll be no coordinates to recreate the map. The only thing is to wait cause otherwise I'll certainly get a huge difficulty, extracting every single coordinate for every single 3d object. However, I could still use some of the 3d object for any useful purpose.
## Post #367
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-15T05:26:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from eyewee
>
> I've talked to these genious frosty editor developpers on discord, it seems to be quite impossible to get the coordinates...at least, more than 20%, everything else is hidden, as u've said, in this havok data. In fact, they are working on a map editor tool inside frosty editor, but until then, there'll be no coordinates to recreate the map. The only thing is to wait cause otherwise I'll certainly get a huge difficulty, extracting every single coordinate for every single 3d object. However, I could still use some of the 3d object for any useful purpose.
If I've learned anything so far from all of this research over the years is that, its not impossible, it just takes a certain mind and set skills to do it, and most of us do not have those, and some who do have it, are not interested in going that deep, and those who do, it takes time, and for good reason.

But until then at least you have two tools to get geometry/meshes from NFSTR and NFSP, so better something than nothing.
They're made/posted by daemon1 here in one of these pages of this thread, have a look at them and see if it works for your purpose.
## Post #368
- Username: Flandyn
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 12, 2015 9:06 pm
- Post datetime: 2018-07-19T12:32:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Every time I use Fb_SWBF_mesh.exe, it gives me this error:

```

Unhandled Exception: System.IndexOutOfRangeException: Index was outside the bounds of the array.
   at FB_faceposer.FB_faceposer.Main(String[] args)

```

I've tried dumping the files using UFBE and the python scripts, but I still get the same error.

When using Fb_SWBF_faces.exe, it gives me this error instead:

```

Unhandled Exception: System.IO.EndOfStreamException: Unable to read beyond the end of the stream.
   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadUInt64()
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )

```

How do i fix this?
## Post #369
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-19T15:08:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

you're doing something wrong. Read how to use the tool again.

i dont have the game, so i can't check the file you mention
## Post #370
- Username: Flandyn
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 12, 2015 9:06 pm
- Post datetime: 2018-07-19T15:47:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I've fixed the fb_swbf_faces.exe error, but now it gives me this even though I have copied all the .assetbank files in the game into the tool's folder:

```
Asset not found in asset banks (2)
```

As for the fb_swbf_mesh.exe error, I can't seem to fix that. I could send you the files i'm trying to convert if you'd like.

EDIT: Fixed.
## Post #371
- Username: raven154
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 10, 2018 4:25 am
- Post datetime: 2018-08-11T00:20:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> satan0w wrote:
ok i try this but if mazda dont have skeleton what i must?
i go to bundles ->vehicles ->player ->car_mazda_rx7spiritr_2002 and all files for mazda in this folder


https://imgur.com/a/QNX9W
Well now that I know what is your talking about, its already been answered, here:
viewtopic.php?f=16&t=17236&p=138712#p138712

BUT, from what I can see in your image, something went wrong with your extraction, there are no .MeshSet extracted to work with, .MeshSet is needed for geometry.
What did you extract it with?

.MeshSet is in the "res" folder... And how to connect it?
## Post #372
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-08-11T23:09:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from raven154
>
> .MeshSet is in the "res" folder... And how to connect it?
Well, as it was already posted in the NFS Payback thread you follow those instructions and you will get what you want.
What exactly is that you didn't understand? You have to be a bit more specific in order to help more efficiently.
If you follow the instructions in the link in your quote you'll get meshes/geometry converted just fine.

And try to stay on one thread, wondering around asking questions all over makes a mess.
## Post #373
- Username: spectrum
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 27, 2018 11:22 pm
- Post datetime: 2018-10-27T15:36:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> But until then at least you have two tools to get geometry/meshes from NFSTR and NFSP, so better something than nothing.
They're made/posted by daemon1 here in one of these pages of this thread, have a look at them and see if it works for your purpose.

Hello. I've been trying to extract the meshes and textures from NFSTR for some time now. Using QuickBMS and its scripts (frostbite.bms and nfstr_blueprintbundle.bms) works properly, but as I've seen from your reply above, it is not recommended. With that I tried to get some of the Battlefield dumpers to extract the game files, got a few results. The most recent that I could find was from 2014, althought it still give me some errors and I'm unable to get any file working properly. 

I've started to look for a Battlefield tools after reading your reply here: [viewtopic.php?f=10&t=7679&start=105](http://forum.xentax.com/viewtopic.php?f=10&t=7679&start=105)

So, I'm not sure if the source of my dump is just outdated or if it is something else. In that case, would be possible to link me to the lastest updated dumper scripts?
## Post #374
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-10-28T01:11:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from spectrum
>
> would be possible to link me to the lastest updated dumper scripts?
No need to (plus there are no updated scripts anymore), simply use Daemon's UFBE tool and select the SWBF2 option for the game and your good to go.

Note, to make it all extract fast, use a different HDD for extraction than the one your game resides.
After you selected the game and where to extract, select SWBF2
Then click scan Bundles, click ok after done, then click scan CAS/CAT also click ok after done
Also make sure you tick all option besides (show assets names with full path)
now hit DUMP and wait till it extracts/dumps everything.
## Post #375
- Username: spectrum
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 27, 2018 11:22 pm
- Post datetime: 2018-10-28T06:14:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> spectrum wrote:would be possible to link me to the lastest updated dumper scripts?
No need to (plus there are no updated scripts anymore), simply use Daemon's UFBE tool and select the SWBF2 option for the game and your good to go.

Note, to make it all extract fast, use a different HDD for extraction than the one your game resides.
After you selected the game and where to extract, select SWBF2
Then click scan Bundles, click ok after done, then click scan CAS/CAT also click ok after done
Also make sure you tick all option besides (show assets names with full path)
now hit DUMP and wait till it extracts/dumps everything.

Thanks for the info about UFBE. 
However, trying to click on the "scan Bundles" gives me an EndOfStreamException. Am I missing something that I should have installed before?
## Post #376
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-10-29T02:05:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from spectrum
>
> However, trying to click on the "scan Bundles" gives me an EndOfStreamException. Am I missing something that I should have installed before?
UFBE does NOT require any type of prerequisite to run (besides windows OS), its independent.
All you need to make sure is to have correct paths for the location of the game and where to extract.

But issues like those can happen for two main reasons (since I just tried it on latest updated version and all works just fine), you either have a corrupt download and I suggest to repair it in Origin, or you downloaded a pirated version with corrupt/incomplete files.

Note: On rare occasions it may cause errors due to UFBE not having proper permission to access the game if its in Program Files default location.
In that case try UFBE with Admin rights, or move game files to a different HDD, good luck.
## Post #377
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-10-29T14:52:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I have a problem with BF1/SWBF1.
I can't seem to get textures to extract, unsure what I'm doing wrong, but I always get this 1 x 1 message and nothing converts.

GUID = 4874E8BAF65BA4D5300B7D1300001000    t_volcanicbase_rockmedium_01_c 0b000000.Texture  1 x 1
GUID = 8248A3A9F74CA09634E1AEDF00000800    t_volcanicbase_rockmedium_01_h 0b000000.Texture  1 x 1
GUID = 2077D2E2EF6E2A149A92BF4700001000    t_volcanicbase_rockmedium_01_n 0b000000.Texture  1 x 1

-I dumped everything with UFBE.
-I have my bundles/chunks folders set up, then I use the texture converter.
-It finds the Itextures and chunks.
-I get this error when converting. (probably because these chunks do not exist, but I dumped everything - also searched in UFBE, nothing there)

This happens to every single texture.
Any idea what could be causing this?
## Post #378
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-10-29T17:38:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from lolwatt
>
> Any idea what could be causing this?
You could be easily using a wrong version, or a unsupported version for textures on the specified games, there are so many variations out there that even I couldn't get it work on so many games.
Most of those texture converters where made for older games, I think Daemon only supported about two of those tools (I could be wrong) for new games, I no longer know which one or where they are.
## Post #379
- Username: spectrum
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 27, 2018 11:22 pm
- Post datetime: 2018-10-30T01:54:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> spectrum wrote:However, trying to click on the "scan Bundles" gives me an EndOfStreamException. Am I missing something that I should have installed before?
UFBE does NOT require any type of prerequisite to run (besides windows OS), its independent.
All you need to make sure is to have correct paths for the location of the game and where to extract.

But issues like those can happen for two main reasons (since I just tried it on latest updated version and all works just fine), you either have a corrupt download and I suggest to repair it in Origin, or you downloaded a pirated version with corrupt/incomplete files.

Note: On rare occasions it may cause errors due to UFBE not having proper permission to access the game if its in Program Files default location.
In that case try UFBE with Admin rights, or move game files to a different HDD, good luck.

Paths are correct and just repaired it in Origin. I also tried to run UFBE with Admin rights, moved to my other HD and still the same error happened.
My currently OS is Windows 10 and... well, I don't know why this is happening.

Isn't there some kind of log or debug file that I can attach here?
## Post #380
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-10-30T16:33:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from spectrum
>
> Isn't there some kind of log or debug file that I can attach here?
UFBE does not export any type of log but you could easily post the error screen that it displays, and who knows maybe Daemon himself can explain better as to why that happens.
Try to select ONLY the Data folder of the game and NOT the root folder of the whole game that includes updates/patches, just Data folder, and see if that works with out errors.

PS: UFBE will ONLY work with Frostbite 3 engine games, NOT with Frostbite 2 games such as Need for Speed The Run, because Payback should have no issues, at all.
This is what you need for NFSTR: [http://www.bfeditor.org/forums/index.ph ... -archives/](http://www.bfeditor.org/forums/index.php?/topic/15731-file-dumper-for-sbtoc-archives/)
## Post #381
- Username: spectrum
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 27, 2018 11:22 pm
- Post datetime: 2018-10-31T02:29:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> spectrum wrote:Isn't there some kind of log or debug file that I can attach here?
UFBE does not export any type of log but you could easily post the error screen that it displays, and who knows maybe Daemon himself can explain better as to why that happens.
Try to select ONLY the Data folder of the game and NOT the root folder of the whole game that includes updates/patches, just Data folder, and see if that works with out errors.

It still gives the same Exception error.


> Reply from mono24
>
> PS: UFBE will ONLY work with Frostbite 3 engine games, NOT with Frostbite 2 games such as Need for Speed The Run, because Payback should have no issues, at all.
This is what you need for NFSTR: http://www.bfeditor.org/forums/index.ph ... -archives/

So I tried the scripts on that link. It read fines until I get this error:

```
    self.ebxEntries=[bundleEntry(unpack(">3I",f.read(12))) for i in xrange(self.header.numEbx)]
NameError: global name 'bundleEntry' is not defined
```


I'm currently using Python 2.7.6, and this is how I adjusted the paths in dumper.py

```
patchedCatName=r"" #used only when tocRoot contains "Update"

##tocRoot=r"C:\Program Files (x86)\Origin Games\Need for Speed The Run\Update\"
tocRoot=r"C:\Program Files (x86)\Origin Games\Need for Speed The Run\Data\Win32"

outputfolder="F:/test"
```
## Post #382
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-10-31T04:35:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from spectrum
>
> So I tried the scripts on that link. It read fines until I get this error:
Code: Select allFile "C:\Users\spectrum\Desktop\dumper\dumper 4\Bundle.py", line 26, in __init__
    self.ebxEntries=[bundleEntry(unpack(">3I",f.read(12))) for i in xrange(self.header.numEbx)]
NameError: global name 'bundleEntry' is not defined
Make sure bundleEntry has capital B in Bundle.py, like this

```
        self.resEntries=[BundleEntry(unpack(">3I",f.read(12))) for i in xrange(self.header.numRes)]
```

Everything is case sensitive, even if you have an extra or missing space in a line code, you'll get errors, python is very picky.

> Reply from spectrum
>
> I'm currently using Python 2.7.6
I assume 32bit, correct? As 64bit python is NOT supported.
## Post #383
- Username: spectrum
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 27, 2018 11:22 pm
- Post datetime: 2018-11-01T03:39:22+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> spectrum wrote:So I tried the scripts on that link. It read fines until I get this error:
Code: Select allFile "C:\Users\spectrum\Desktop\dumper\dumper 4\Bundle.py", line 26, in __init__
    self.ebxEntries=[bundleEntry(unpack(">3I",f.read(12))) for i in xrange(self.header.numEbx)]
NameError: global name 'bundleEntry' is not defined
Make sure bundleEntry has capital B in Bundle.py, like this
Code: Select all        self.ebxEntries=[BundleEntry(unpack(">3I",f.read(12))) for i in xrange(self.header.numEbx)]
        self.resEntries=[BundleEntry(unpack(">3I",f.read(12))) for i in xrange(self.header.numRes)]
Everything is case sensitive, even if you have an extra or missing space in a line code, you'll get errors, python is very picky.

That solved the problem! Really, thanks a lot! Just a question related to the Paths, currently I have them set up like this:

```
##tocRoot=r"C:\Program Files (x86)\Origin Games\Need for Speed The Run\Data\Win32"
```


So, if I understood correctly, the first one is for the entire game patched, so it will exctract the content under the "Update" folder and then the main game.
The second one, if uncommented, will extract only the data from the main game, without the content under Update folder, right?

Ah, did anyone tried to run those scripts on the PS3 or Xbox360 releases of the game?

> Reply from mono24
>
> spectrum wrote:I'm currently using Python 2.7.6
I assume 32bit, correct? As 64bit python is NOT supported.

That's right!

Also, do I need any special script to handle Need for Speed: The Run meshes, texture and audio files?
## Post #384
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-11-01T23:22:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from spectrum
>
> Just a question related to the Paths, currently I have them set up like this:
Code: Select alltocRoot=r"C:\Program Files (x86)\Origin Games\Need for Speed The Run"
##tocRoot=r"C:\Program Files (x86)\Origin Games\Need for Speed The Run\Data\Win32"
For NFSTR it's irrelevant, because either way updates/patches for it are NOT supported.
If you make path at root folder of the game as you have it above first line, update/patched folder WILL be ignored, ONLY Data will be dumped/extracted no matter what.

> Reply from spectrum
>
> So, if I understood correctly, the first one is for the entire game patched, so it will exctract the content under the "Update" folder and then the main game.
The second one, if uncommented, will extract only the data from the main game, without the content under Update folder, right?
If we take a game that works fully like BF3, it will first dump updates/patches in they're folder structure, once its done and you then extract Data folder it will continue to dump only needed files with out overwriting what was already extracted form updates/patches, thus keeping things neat and no duplicates.

> Reply from spectrum
>
> Ah, did anyone tried to run those scripts on the PS3 or Xbox360 releases of the game?
I've tested PS3 myself and it works same way, X360 should work identically, Data gets dumped while update/patch folder gets ignored due to not being supported.

> Reply from spectrum
>
> Also, do I need any special script to handle Need for Speed: The Run meshes, texture and audio files?
Meshes: [viewtopic.php?p=137476#p137476](http://forum.xentax.com/viewtopic.php?p=137476#p137476) <-NFSTR
Meshes: [viewtopic.php?p=134343#p134343](http://forum.xentax.com/viewtopic.php?p=134343#p134343) <-NFSP
Note: UU3D also works for meshes for those who have a license to export as demo does NOT allow export.
Textures: your on your own, I never found a tool that works.
Audio: there is no script that supports audio conversion of the vehicles.

Search function is your best friend, what ever else you need you'll find it eventually, just think what you need, type it in and search.

good luck
## Post #385
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-11-02T01:39:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Okay, I went back to the thread but didn't find my answer exactly.

Regarding SW:Battlefront (2015), I have the deluxe version of the game (includes DLCs, etc).
When I use UFBE, I get a lot of missing chunks (~20k)

What does that mean? If I go for the python script, will it dump everything right?
Essentially, what is the difference?
## Post #386
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-11-02T04:07:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from lolwatt
>
> When I use UFBE, I get a lot of missing chunks (~20k)
That is normal, meaning not all assets in the game require/have a chunk file to be extracted, that's why you see that missing information.

> Reply from lolwatt
>
> What does that mean? If I go for the python script, will it dump everything right?
Essentially, what is the difference?
Python will ALWAYS create unnecessary duplicates depending on what script your using, if its one edited by Daemon it skips duplicates.
They will both dump same files, once again depending what python script, minus duplicates with UFBE.
10 assets can lead to one chunk, that means python would extract duplicates, while UFBE only one chunk.
I hope I explained it well.
## Post #387
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-11-02T12:13:20+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> lolwatt wrote:When I use UFBE, I get a lot of missing chunks (~20k)
That is normal, meaning not all assets in the game require/have a chunk file to be extracted, that's why you see that missing information.
lolwatt wrote:What does that mean? If I go for the python script, will it dump everything right?
Essentially, what is the difference?
Python will ALWAYS create unnecessary duplicates depending on what script your using, if its one edited by Daemon it skips duplicates.
They will both dump same files, once again depending what python script, minus duplicates with UFBE.
10 assets can lead to one chunk, that means python would extract duplicates, while UFBE only one chunk.
I hope I explained it well.

You explained it very well. Thank you very much.
## Post #388
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-11-29T03:17:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

for new SWBF2 (with manifest) you can use this scripts:
[https://zenhax.com/viewtopic.php?p=40429#p40429](https://zenhax.com/viewtopic.php?p=40429#p40429)
Fb_SWBF2_mesh.exe work fine
but Fb_SWBF2_faces.exe return error 'Asset not found in asset banks (2)'
## Post #389
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-01T00:01:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from erik945
>
> but Fb_SWBF2_faces.exe return error 'Asset not found in asset banks (2)'
That is because they changed some file formats, AssetBanks no longer exist they have been replaced with a new format it seems, that's why the error, it cant find them anymore.
## Post #390
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-16T06:53:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Here's all of the new facefixes. Including Obi-Wan, young Solo and all others.
[swbf2_facefix.rar](https://xentaxbackup.github.io/file/15331_swbf2_facefix.rar)
## Post #391
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-16T06:53:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

...
## Post #392
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-16T11:29:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

And the tool and facefixes for Battlefield V

3p_malesoldier_fb.ebx - is the main skeleton for BFV, tool will expect it
[bf5_tools.rar](https://xentaxbackup.github.io/file/15330_bf5_tools.rar)
## Post #393
- Username: Mendax47
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 09, 2018 11:09 pm
- Post datetime: 2018-12-20T05:19:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Is this tools are working with battlefield 5..?
## Post #394
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-23T16:36:12+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Mirrors Edge Catalyst fixed faces.

Game has 3 main skeletons:  male, female, and female_heels
I don't know which character used which, so i will export them all on all 3

p.s. working on Mass Effect Andromeda

[https://youtu.be/CmhcSO-eXHw](https://youtu.be/CmhcSO-eXHw)


[mec.rar](https://xentaxbackup.github.io/file/15369_mec.rar)
## Post #395
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-26T16:45:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Here're all facefixes for Mass Effect Andromeda: ketts, turians and angara female.
If anything else needs fix let me know.


[mea_fixes.rar](https://xentaxbackup.github.io/file/15384_mea_fixes.rar)
## Post #396
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-31T09:07:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)


## Post #397
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2018-12-31T10:58:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> 

Это круто!!! Настоящий подарок на НГ:)
## Post #398
- Username: padme4000
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 27, 2014 1:46 am
- Post datetime: 2018-12-31T14:52:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

This is really amazing, thank you so much on the work you are doing.
## Post #399
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-01T12:54:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

[hmale.rar](https://xentaxbackup.github.io/file/15407_hmale.rar)
## Post #400
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2019-01-01T13:11:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> 
 у меня нет приличных слов,одни матерные комплименты:)
## Post #401
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-02T12:41:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Main female characters are hardest to get, they are using even more tech to get them looking like in game.
## Post #402
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2019-01-02T12:57:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from daemon1
>
> Main female characters are hardest to get, they are using even more tech to get them looking like in game.

Оооо! Этот взгляд:)
## Post #403
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-03T18:10:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I can't currently get females properly fixed.

But I can grab them from running game. You probably know that if you rip them with existing tools, faces will be distorted. I was able to get them fully fixed and rigged, in the pose from squad selection screen.

[https://www.youtube.com/watch?v=kIuu7KVpr-Q](https://www.youtube.com/watch?v=kIuu7KVpr-Q)
## Post #404
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-05T12:37:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Since I can't get female models properly extracted, complete rigged heads for Cora, Sara and Peebee are published on another site. Because i think xentax is not allowing this.
## Post #405
- Username: budda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 07, 2019 8:23 pm
- Post datetime: 2019-01-07T12:25:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Thanks for all your work on this, it's appreciated.
## Post #406
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-12T12:51:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

Here i gather all of the newest additions to the facefixing project.
- updated facefixes for SWBF2
- mesh tool & facefixes for BFV
- facefixes for Mirrors Edge Catalyst 
- mesh/morph tool for MEA, facefixes for aliens and main characters
- morph tool for DAI
Some of them were posted above, MEA and DAI tools are added now.
I will try to describe everything in details if i have time.
But it seems now all of the "distorted face" games are covered.
[new fb tools.7z](https://xentaxbackup.github.io/file/15453_new fb tools.7z)
## Post #407
- Username: padme4000
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 27, 2014 1:46 am
- Post datetime: 2019-01-12T16:13:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

that is amazing that you got it working with Dragon Age Inquisition as well. I really appreciate all the work you are doing. 

It will mean it will be less daunting porting DAI NPC's. Just a shame we can't access the edited morph files of our custom Inquisitors. But I can still use my previous method to make them. So really thank you as that is a long process so not having to do it for NPC's is bloody amazing.

So much thanks again.

Just a question how would I go about extracting the mesh and morph files for Inquisition and/or Mass Effect Andromeda? I am new to the tool and only see an option for the battlefront games and battlefield.
## Post #408
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-13T01:32:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from padme4000
>
> how would I go about extracting the mesh and morph files for Inquisition and/or Mass Effect Andromeda?
Regardless what Frostbite game you'd like to work on, all mesh tools developed by id-daemon work the same, so the link tutorial by Crofty from first post is still valid and current for anyone's needs, now when comes about the newly developed morph tools for DA:I/ME:A it works as follows.
Lets make this tutorial example for DA:I game:

The Fb_DAI_morph.exe tool needs the following assets to work:
3 parameters:  meshset, skeleton, morphresource
chunk will be found automatically
Usage example:

```
Fb_DAI_morph.exe mt_basa_hf.meshset hf_skeleton.ebx hf_adamant_clarel.MorphResource
```

Basically the string above inside a text file with extension .bat/.cmd will give you the following results.
- It will output a distorted head mesh with distorted face in ASCII/SMD format, and a small SMD fix for it.
- For heads which are not distorted, you can just use 2nd animation frame from SMD fix as a rest pose of a skeleton.
- Non-distorted heads are those made not from "generic" base mesh, but have their own base mesh and most main characters are like this.
- If you're not sure which mesh is used for base, its name is inside of MorphResource file, use any HEX software to find it in the beginning.
NOTE: In case no one knew, BF4 tool Fb_BF4_mesh.exe works for "usual" DA:I meshes.

Make sure you have a fully dumped game with all it's assets in their required file/folder structure.
Now go in your dumped folder and in bundles folder create another new folder, I usually use "_"(underscore) to make sure its at the top, why use a new folder? to keep track of your progress and not get lost.
Now in your newly created folder make sure you have the following assets for the morph tool to work, I will use for this test ElfFemale.
- Fb_DAI_morph.exe
- mt_basa_ef_mesh.MeshSet
- ef_skeleton.ebx <- skeletons are easy to find in the ebx folder, they are named accordingly
- and any .MorphResource you want to extract morphs, you get these from res folder
Now I use the string above like this to do a morph, let's say Briala.

```
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_briala.MorphResource
```

The result will be three new assets:

```
ef_briala.smd <-base head mesh with Briala morph applied in SMD format
ef_briala_ani.smd <- actual skeleton FIX in SMD format
```

Now we go to Blender to make them work.
Import the ef_briala.ascii format, it has correct normals in comparison to the SMD version.
Delete its skeleton, and import the small SMD fix ef_briala_ani.smd skeleton as Make New Armature, it will be imported rotated 90degrees so make sure to rotate it back to match the mesh.
Once you have rotated it properly 90degrees, no more no less, this is important, select ALL meshes, head/eyes/eyelashes and what ever else it has, and while holding CTRL select the skeleton, they need to be in exact order, meshes then select skeleton, now do CTRL+P and click Armature Deform to parent them.
Now you can apply the second frame of the animation and watch how the face gets fixed, easy right?

PS: For other details you can still check Crofty's tutorial, besides how to extract the morphs, applying a face fix is the same for all Frostbite games, and how to apply rest pose and what not.
If you want to do all morphs in a batch for ElfFemale then your .bat/.cmd should look like this. Take notice for 2 differences in base mesh/skeleton.

```
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_briala.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_bulls_charger_dalish_p2.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_bulls_charger_skinner_p2.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_dalishscout_p3.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_emalien_p2.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_fiona.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_hav_assistant_researcher.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_hav_elf_servant_p3.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_hav_minaeve_p4.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_01.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_02.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_03.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_04.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_05.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_06.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_dalish_01.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_dalish_02.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_dalish_03.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_dalish_04.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_dalish_05.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_head_dalish_06.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_inquisitionmessenger_p3.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_inquisitor.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_mastertaniel_p2.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_medic_p3.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_mihris_p3.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_nissa_p2.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_proxy.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_savedelf_p3.MorphResource
Fb_DAI_morph.exe mt_cbt_sera_mesh.MeshSet hf_skeleton.ebx ef_sera.MorphResource
Fb_DAI_morph.exe mt_cbt_sera_mesh.MeshSet hf_skeleton.ebx ef_sera_noears.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_sky_apothecary_p4.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_trainer_assassin_p4.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_trainer_knightenchanter_p4.MorphResource
Fb_DAI_morph.exe mt_basa_ef_mesh.MeshSet ef_skeleton.ebx ef_trainer_reaver_p4.MorphResource
```

have fun
## Post #409
- Username: padme4000
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 27, 2014 1:46 am
- Post datetime: 2019-01-14T15:24:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

Mono24 thank you very much for the help
## Post #410
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-14T15:25:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from padme4000
>
> Just a shame we can't access the edited morph files of our custom Inquisitors
why not?
i was able to grab my custom main character from MEA (Sara)
i think it must be even easier to do it for DAI
## Post #411
- Username: ineteye
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 09, 2008 8:41 pm
- Post datetime: 2019-01-15T23:33:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

HI! Did not understand why dumper only create chunk folder? where is mesh folder, i set true to (dumpResEnabled = True) but still does not help..
## Post #412
- Username: padme4000
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 27, 2014 1:46 am
- Post datetime: 2019-01-16T11:18:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from daemon1
>
> 
why not?
i was able to grab my custom main character from MEA (Sara)
i think it must be even easier to do it for DAI

That is amazing that you got your Custom Ryder from Andromeda.

I have been told often that it was likely impossible due to the Frosty Engine. 

The only way I have managed it is with ninja ripper, transferring the shape onto a mesh that has an armature and then manually moving the bones to make them look like they do in game. Though this can be very time consuming.

So any tips on getting the Custom Inquisitors and Custom Ryders would be greatly appreciated. Though honestly what you have already done is beyond what most people I know thought was possible so long after Inquisition's release.
## Post #413
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2019-01-18T03:59:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

I have downloaded several tools from this thread, none of which seem to have Battlefield 3 support. Can you point me to more certain direction?
## Post #414
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-18T20:11:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from kixpress
>
> Can you point me to more certain direction?
Well, you normally start from page one and keep going one at a time and then, voilà: [viewtopic.php?p=134793#p134793](http://forum.xentax.com/viewtopic.php?p=134793#p134793)
## Post #415
- Username: Whiskey
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 16, 2017 1:05 am
- Post datetime: 2019-02-04T19:37:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from daemon1
>
> padme4000 wrote:Just a shame we can't access the edited morph files of our custom Inquisitors
why not?
i was able to grab my custom main character from MEA (Sara)
i think it must be even easier to do it for DAI

Not sure how I would get a morphset out of save games for either of the games. Instructions on how to do that would be awesome if you have the time for it!

Meanwhile I'm already ecstatic that I can finally work with DAI npcs without having to manually fix broken faces!
## Post #416
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-02-04T20:48:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from padme4000
>
> So any tips on getting the Custom Inquisitors and Custom Ryders would be greatly appreciated.
I had to make my own tool for that. I will pm you.
## Post #417
- Username: Whiskey
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 16, 2017 1:05 am
- Post datetime: 2019-02-04T20:53:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from daemon1
>
> padme4000 wrote:So any tips on getting the Custom Inquisitors and Custom Ryders would be greatly appreciated.
I had to make my own tool for that. I will pm you.

Could you send me the tool also? I'd be very interested to try it!
## Post #418
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-02-06T17:42:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

Custom character test for DAI.
Looks weird without all the makeup, but geometry must be 100% correct
also as in MEA, the mesh has all original weights
## Post #419
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-02-07T16:44:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from Whiskey
>
> Could you send me the tool also? I'd be very interested to try it!
the tool is not ready, i'm only testing it
i not gonna send it to someone just registered here
## Post #420
- Username: Whiskey
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 16, 2017 1:05 am
- Post datetime: 2019-02-07T16:57:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and othe

> Reply from daemon1
>
> Whiskey wrote:Could you send me the tool also? I'd be very interested to try it!
the tool is not ready, i'm only testing it
i not gonna send it to someone just registered here

Fair enough. I'll wait for a public release, didn't mean to butt in like that. I'm just very excited by this making importing custom characters much less of a pain.

Really appreciate your work!
## Post #421
- Username: spectrum
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 27, 2018 11:22 pm
- Post datetime: 2019-02-09T21:59:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> spectrum wrote:Just a question related to the Paths, currently I have them set up like this:
Code: Select alltocRoot=r"C:\Program Files (x86)\Origin Games\Need for Speed The Run"
##tocRoot=r"C:\Program Files (x86)\Origin Games\Need for Speed The Run\Data\Win32"
For NFSTR it's irrelevant, because either way updates/patches for it are NOT supported.
If you make path at root folder of the game as you have it above first line, update/patched folder WILL be ignored, ONLY Data will be dumped/extracted no matter what.
spectrum wrote:So, if I understood correctly, the first one is for the entire game patched, so it will exctract the content under the "Update" folder and then the main game.
The second one, if uncommented, will extract only the data from the main game, without the content under Update folder, right?
If we take a game that works fully like BF3, it will first dump updates/patches in they're folder structure, once its done and you then extract Data folder it will continue to dump only needed files with out overwriting what was already extracted form updates/patches, thus keeping things neat and no duplicates.
spectrum wrote:Ah, did anyone tried to run those scripts on the PS3 or Xbox360 releases of the game?
I've tested PS3 myself and it works same way, X360 should work identically, Data gets dumped while update/patch folder gets ignored due to not being supported.
spectrum wrote:Also, do I need any special script to handle Need for Speed: The Run meshes, texture and audio files?
Meshes: viewtopic.php?p=137476#p137476 <-NFSTR
Meshes: viewtopic.php?p=134343#p134343 <-NFSP
Note: UU3D also works for meshes for those who have a license to export as demo does NOT allow export.
Textures: your on your own, I never found a tool that works.
Audio: there is no script that supports audio conversion of the vehicles.

Search function is your best friend, what ever else you need you'll find it eventually, just think what you need, type it in and search.

good luck

Hi there. Sorry for not replying for so long. I tried to use the tool under the "Fb_nfsrun.rar" however, I had no success. I tried to look around the forum, searched a little about how use daemon1 tools, yet I wasn't able anything that would guide me to use that tool.

Please, can you teach me how to use it?
## Post #422
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-02-10T02:20:04+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from spectrum
>
> Please, can you teach me how to use it?
You quoted whole thing, what a mess.

A lot of info is already available, just requires right combo of words to search for.
Answer: [viewtopic.php?p=138712#p138712](http://forum.xentax.com/viewtopic.php?p=138712#p138712)
Only difference is, for skeleton it needs the Battlefield 3 main skeleton veniceantske01.ebx for conversion to work.
Or simply rename any skeleton form the actual game to veniceantske01.ebx.

have fun

PS.
Also I was wrong about Patches for the game, they are supported, just that the script was designed to dump properly Battlefield 3 game with XPacks contents, and there for it expects the NFSTR to have same folder structure, yet I never managed to make it work, oh well.
## Post #423
- Username: spectrum
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 27, 2018 11:22 pm
- Post datetime: 2019-02-10T14:54:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24
>
> spectrum wrote:Please, can you teach me how to use it?
You quoted whole thing, what a mess.

A lot of info is already available, just requires right combo of words to search for.
Answer: viewtopic.php?p=138712#p138712
Only difference is, for skeleton it needs the Battlefield 3 main skeleton veniceantske01.ebx for conversion to work.
Or simply rename any skeleton form the actual game to veniceantske01.ebx.

have fun

PS.
Also I was wrong about Patches for the game, they are supported, just that the script was designed to dump properly Battlefield 3 game with XPacks contents, and there for it expects the NFSTR to have same folder structure, yet I never managed to make it work, oh well.

Thanks a lot! It worked.
## Post #424
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-02-17T19:26:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Cutsom inquisitor tool is ready. But it will not be published, at least yet.
Those who want to extract cutsom faces, PM me.
## Post #425
- Username: Antieve
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 17, 2019 8:12 am
- Post datetime: 2019-03-02T08:39:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Can someone share BFV faces dds textures please?
## Post #426
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2019-03-05T12:22:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

I'm sure this might sound stupid but... 
Seeing Anthem is made on the Frostbite engine as well, are there any tools right now which can rip the models out ?
I'm not sure if there is another way one could do so (like with ninja ripper or something)
## Post #427
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-03-05T22:41:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from rensole ↑Tue Mar 05, 2019 8:22 pm at Tue Mar 05, 2019 8:22 pm
>
> are there any tools right now which can rip the models out ?
Correct, it is a Frostbite engine game, but now since the devs started messing with the format and changed everything, things got a bit tricky, we will not have any access to the files anytime soon, looks like there isn't much interest, BUT Frosty Tool Suite will have a read only profile for it, so there will be that, but no one knows yet when will be released.
## Post #428
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2019-03-12T14:55:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Is there any way to use a program like Ninjaripper to extract models?
I'm fairly unfamiliar with the frostbite engine and ripping in general, but I thought I'd ask first before buying the game and hitting a dead end.
## Post #429
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-03-13T01:31:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from rensole ↑Tue Mar 12, 2019 10:55 pm at Tue Mar 12, 2019 10:55 pm
>
> 
Is there any way to use a program like Ninjaripper to extract models?
Be patient, that's all what everyone needs to do for now, regardless if it takes a week, a month or a full year, patience.
And no it will NOT work.
## Post #430
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2019-03-13T02:11:20+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from mono24 ↑Wed Mar 13, 2019 9:31 am at Wed Mar 13, 2019 9:31 am
>
> 
rensole wrote: ↑Tue Mar 12, 2019 10:55 pm
Is there any way to use a program like Ninjaripper to extract models?
Be patient, that's all what everyone needs to do for now, regardless if it takes a week, a month or a full year, patience.
And no it will NOT work.

Oh I am I was just wondering as I want to learn ^^
Thanks for the info!
## Post #431
- Username: kaliope
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 01, 2019 5:45 pm
- Post datetime: 2019-04-01T11:57:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

hello and first of all thanks for all the great content here

my question is to get some models working in blender. my progress so far:

Now here are the questions where I am stuck

Any idea where there problem might be?
## Post #432
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-01T17:58:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from kaliope ↑Mon Apr 01, 2019 7:57 pm at Mon Apr 01, 2019 7:57 pm
>
> Any idea where there problem might be?
Wait, there is NO 32-bit python script for the game though, only 64-bit, what script did you use?
Do this: [https://forum.xentax.com/viewtopic.php? ... 30#p146986](https://forum.xentax.com/viewtopic.php?f=10&t=19074&start=30#p146986)
## Post #433
- Username: kaliope
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 01, 2019 5:45 pm
- Post datetime: 2019-04-01T19:27:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

My mistake, I got confused after reading so much about it. Of course I used a correct one from one of the links here in the forum (extracts 120gig data so there shouldn't be an issue) with Python 2.7.15 x64.
## Post #434
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-01T23:08:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

> Reply from kaliope ↑Tue Apr 02, 2019 3:27 am at Tue Apr 02, 2019 3:27 am
>
> don't mind the cube here in the screenshot but the black lines
Ah, you have wrong skeleton loaded it seems, or no skeleton at all? I cant tell.
## Post #435
- Username: kaliope
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 01, 2019 5:45 pm
- Post datetime: 2019-04-02T06:42:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield 1, Battlefront 1, 2)

Okay my mistake thx!
## Post #436
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-02T17:04:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

as i remember, BFV tool needs 2 parameters: meshet and chunk
maybe skeleton as 3rd, but i dont remember
## Post #437
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-13T11:28:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Tool for DAI individual morphs.

It will allow you to extract about 400+ morphs for each type of face.
All kind of face parameters, like eyes/ears/nose size/position etc etc will be there.
Works same as DAI morph tool, just instead of .morphresource, 3rd parameter is .morphtarget resource. For example:

Fb_DAI_morphtarget.exe mt_basa_hf.meshset hf_skeleton.ebx humanfemaletargets.MorphTargetsResource

Many morphs require bone moving (which changes the mesh shape). To do this, you have to apply the small _ani.smd file to the morphed mesh.


[Fb_DAI_morphtarget.rar](https://xentaxbackup.github.io/file/16031_Fb_DAI_morphtarget.rar)
## Post #438
- Username: Mgonzalez14
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 22, 2019 7:48 am
- Post datetime: 2019-04-22T00:03:22+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi @daemon1 I tried to pm you but it's stuck in outbox, if you have discord would you mind adding me and shooting a message so we can discuss: pipoca14#6676
Cheers
## Post #439
- Username: Mgonzalez14
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 22, 2019 7:48 am
- Post datetime: 2019-04-22T07:36:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hey guys, I'm a noob when it comes to hex and 3d mesh stuff but I'm trying to figure out how I can locate and edit the positional data in the .res as for fifa 19 it seems to be inline with the .res and not in the chunk. If anyone knows how to do this please send me a pm to discuss further. Cheers
## Post #440
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-22T15:39:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Mgonzalez14 ↑Mon Apr 22, 2019 3:36 pm at Mon Apr 22, 2019 3:36 pm
>
> how I can locate and edit the positional data in the .res as for fifa 19 it seems to be inline with the .res and not in the chunk. If anyone knows how to do this please send me a pm to discuss further. Cheers
Try the following: [https://frostytoolsuitedev.gitlab.io/](https://frostytoolsuitedev.gitlab.io/)
You will need to use the Editor for any fancy stuff you might be interested in, also there is a Discord server that will help you in your quest.

good luck
## Post #441
- Username: noniac
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 21, 2019 8:44 am
- Post datetime: 2019-06-25T01:03:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi everyone,

Im trying to extract the annihilator model from bf1. I believe ive done eveything correctly, i'll explain: Extracted the game files with the tool UFBE, put the "working" folder in order with the "chunks" folder in it with all the chunks, the Fb_BF1_mesh.exe, the 3pantskeleton.ebx and the thompson files. When i try to drag the meshset file from any of the thompsons (annhilator or m1919) to the exe, a 24kb smd appears which is empty and gives an error when imported to blender or max, no ascii file.

Any ideas?
## Post #442
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-06-25T01:45:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from noniac ↑Tue Jun 25, 2019 9:03 am at Tue Jun 25, 2019 9:03 am
>
> Any ideas?
Everything been already explained in the forum many times, but since your having trouble, lets simplify the task:
[https://frostytoolsuitedev.gitlab.io/](https://frostytoolsuitedev.gitlab.io/)

have fun
## Post #443
- Username: noniac
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 21, 2019 8:44 am
- Post datetime: 2019-06-25T11:15:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Tue Jun 25, 2019 9:45 am at Tue Jun 25, 2019 9:45 am
>
> 
noniac wrote: ↑Tue Jun 25, 2019 9:03 amAny ideas?
Everything been already explained in the forum many times, but since your having trouble, lets simplify the task:
https://frostytoolsuitedev.gitlab.io/

have fun

Thanks a lot mono, it happens i got to know that tool just before checking the thread by a guy who told me about it through steam. Just out of curiosity, does anyone know how to get the animations to 3ds max, well, in a readable format... i suppose they are contained in those ebx files.

Thanks for the quick answer!
## Post #444
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-06-25T13:52:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from noniac ↑Tue Jun 25, 2019 7:15 pm at Tue Jun 25, 2019 7:15 pm
>
> does anyone know how to get the animations to 3ds max, well, in a readable format... i suppose they are contained in those ebx files.
EBXs are not animations or meshes or sounds or any other assets, they are binary files that link assets files to their required chunk actual data.
And no, animations are not supported and wont be any time soon, a lot of research has been made by quite a few people in the past just nothing has been ever published, that I know of.
As usual time will tell what will surface.
## Post #445
- Username: twitkiss
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Apr 02, 2018 10:33 pm
- Post datetime: 2019-07-12T22:29:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I've been following Mono24's post on pg 28 regarding extracting DAI morphs.  I think I am having an issue with creating the text/cmd file.

I keep getting this error -



cmdError.png (57.45 KiB) Viewed 143 times



Sorry for the poor quality.

Can someone tell me what I'm doing wrong?

Thanks!

******
edit :  Okay I just realized that all the files I extracted are 0kb.  I remember seeing someone have the same problem so I'll go back and look for that solution.
## Post #446
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-13T03:16:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from twitkiss ↑Sat Jul 13, 2019 6:29 am at Sat Jul 13, 2019 6:29 am
>
> Can someone tell me what I'm doing wrong?
Retrace your steps, closely, you'll get there, the CMD looks ok though.

Hmm, wait a minute, weren't you the one who asked about the script required for extraction of DAI?
Looks like its gone, DAI requires a specific script that only works with DAI and no other frostbite game, you might have corrupted files if you used something else?
## Post #447
- Username: twitkiss
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Apr 02, 2018 10:33 pm
- Post datetime: 2019-07-13T03:26:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Well I used this script here - [https://www.youtube.com/watch?v=UVUv_L7m4g8](https://www.youtube.com/watch?v=UVUv_L7m4g8)

It was linked from another thread and the only one that actually worked.  But now I just noticed all the files are 0kb
## Post #448
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-13T03:45:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from twitkiss ↑Sat Jul 13, 2019 11:26 am at Sat Jul 13, 2019 11:26 am
>
> Well I used this script here - https://www.youtube.com/watch?v=UVUv_L7m4g8
No wonder your getting no where, that stuff doesn't work.
[viewtopic.php?p=104973#p104973](https://forum.xentax.com/viewtopic.php?p=104973#p104973)
## Post #449
- Username: twitkiss
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Apr 02, 2018 10:33 pm
- Post datetime: 2019-07-13T03:54:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Well like I said, it was the only one that worked - sort of 

Thanks for the link!  I appreciate your help - will check it out now.
## Post #450
- Username: twitkiss
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Apr 02, 2018 10:33 pm
- Post datetime: 2019-07-13T19:35:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Jul 13, 2019 11:45 am at Sat Jul 13, 2019 11:45 am
>
> 
No wonder your getting no where, that stuff doesn't work.
viewtopic.php?p=104973#p104973

Everything works great now.  

Would you happen to know what file holds the ani.smd file for a custom inquisitor?  I've tried several but the result is just the default.
## Post #451
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-13T23:58:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from twitkiss ↑Sun Jul 14, 2019 3:35 am at Sun Jul 14, 2019 3:35 am
>
> Would you happen to know what file holds the ani.smd file for a custom inquisitor?
daemon1 is more indicated to answer that, he knows exactly how it all works.
## Post #452
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2019-07-16T23:14:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Is there a link where I can obj or fbx files from battlefield V, Battlefield 1, and either star wars battlefront game?  I don't need textures or skeletons, just the meshes for 3D modeling.

thx
## Post #453
- Username: oddworld91
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 07, 2019 6:25 am
- Post datetime: 2019-08-06T22:32:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hey guys, sorry if this was already answered or not but i would love to know. So i want to extract the Sound Files from Battlefront 2(2017) i got the "Universal Frostibe Extractor" but i dont now what i have to do know. Because when i select the folder and SCAN and click on DUMP nothing happens. I would really appreciate help thanks.

Total beginner here btw. I just got the Tool
## Post #454
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-06T22:42:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from oddworld91 ↑Wed Aug 07, 2019 6:32 am at Wed Aug 07, 2019 6:32 am
>
> Hey guys, sorry if this was already answered or not but i would love to know.
Yes it has been answered in many ways shape and form, I will not do it again since it will be a waste of time, go back and read this thread and you'll find what you need, even on Battlefield V thread you'll find how to tutorials, regardless of them being different games the steps are same being same game engine, Frostbite.

good luck
## Post #455
- Username: oddworld91
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 07, 2019 6:25 am
- Post datetime: 2019-08-06T22:49:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

OK thanks but i used a tutorial for BF1 did everything in the tutorial but i get this
## Post #456
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-06T22:58:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

UFBE no longer works for what you need, ever since the game was updated to use new format.
How about try: [https://frostytoolsuitedev.gitlab.io/](https://frostytoolsuitedev.gitlab.io/)
## Post #457
- Username: oddworld91
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 07, 2019 6:25 am
- Post datetime: 2019-08-06T23:39:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Wed Aug 07, 2019 6:58 am at Wed Aug 07, 2019 6:58 am
>
> 
UFBE no longer works for what you need, ever since the game was updated to use new format.
How about try: https://frostytoolsuitedev.gitlab.io/

OMG thank you very much my friend  you saved my life
## Post #458
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-06T23:45:04+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from oddworld91 ↑Wed Aug 07, 2019 7:39 am at Wed Aug 07, 2019 7:39 am
>
> OMG thank you very much my friend  you saved my life
Oh dear, I hope your safe and sound now, while playing your favorite sounds using Frosty 
And as you noticed, I assume, there is also a Discord server on that page if you inquire other questions, or end up having other issues.
## Post #459
- Username: fuego777
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 18, 2019 10:54 am
- Post datetime: 2019-08-18T03:01:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

OY GOOD
## Post #460
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2019-08-27T16:05:12+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Before I dive into The Frosty Tool Suite,  does it let me extract meshes? If so what format?
## Post #461
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2019-08-27T17:36:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

It allows export to FBX, OBJ and DAE.
## Post #462
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2019-08-28T00:03:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Awesome. thx
## Post #463
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2019-09-01T15:48:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

hi how i repack file back to game? tnx
## Post #464
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-05T00:17:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from dvoika ↑Sun Sep 01, 2019 11:48 pm at Sun Sep 01, 2019 11:48 pm
>
> 
hi how i repack file back to game? tnx
You cant, and never will, instead use: [https://frostytoolsuitedev.gitlab.io/](https://frostytoolsuitedev.gitlab.io/)
It will help you modify files you desire and build your own mods with it.
## Post #465
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2019-09-06T04:36:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Czech/slovakia team [www.localizace.sk](http://www.localizace.sk) they can with own program but don't communicate much with me...
[https://github.com/majomix](https://github.com/majomix)

And i dont know i used this repacker
## Post #466
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-06T06:42:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from dvoika ↑Fri Sep 06, 2019 12:36 pm at Fri Sep 06, 2019 12:36 pm
>
> 
Czech/slovakia team www.localizace.sk they can with own program but don't communicate much with me...
https://github.com/majomix

And i dont know i used this repacker
I have no idea what is your trying to say.
## Post #467
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2019-09-08T07:42:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Sorry my english is bad  i say, czech team make importer/injector but i dont know how use it, frosty tool not work for ps4 version :/
## Post #468
- Username: manavortex
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 26, 2019 6:36 am
- Post datetime: 2019-12-21T13:59:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hello there, 
thank you for your excellent guides and resources. They have been a huge help already. However, I find myself running into a wall here, so I would appreciate it if someone could give me a pointer. 

I have checked all the linked posts/resources, including Crofty's [sta.sh](https://sta.sh/04jxcv9d9o0), and got past several hurdles, but I'm still stuck when it comes to using the face fixing tool for my custom Inquisitor. 
I've used the Python3 [extraction tools](https://github.com/NicknineTheEagle/Frostbite-Scripts) to do a full dump of Inquisition to my hard drive and [Ninja Ripper](https://gamebanana.com/tools/5638) to grab the warped mesh from the game. I've also run the ebxtoasset-Script. However, looking at the guide: 

> Reply from mono24 ↑Sun Jan 13, 2019 9:32 am at Sun Jan 13, 2019 9:32 am
>
> 
The Fb_DAI_morph.exe tool needs the following assets to work:
3 parameters:  meshset, skeleton, morphresource
chunk will be found automatically
Code: Select allFb_DAI_morph.exe mt_basa_hf.meshset hf_skeleton.ebx hf_adamant_clarel.MorphResource

It seems to me that after the dump I should have .meshset files, but I don't. What am I doing wrong? 

I don't have the .meshset or .MorphResource-files, and I have no idea how to get them. I assume that I need to run some other converter? Google search isn't giving me anything, and searching on the forum just directs me back here.



Could you help me out?
## Post #469
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-12-22T12:06:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from manavortex ↑Sat Dec 21, 2019 9:59 pm at Sat Dec 21, 2019 9:59 pm
>
> 
I don't have the .meshset or .MorphResource-files, and I have no idea how to get them. I assume that I need to run some other converter? Google search isn't giving me anything, and searching on the forum just directs me back here.

Fb_DAI_morph.exe can't be used to get custom Inquisitor
that tool is not public
## Post #470
- Username: manavortex
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 26, 2019 6:36 am
- Post datetime: 2019-12-22T14:44:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sun Dec 22, 2019 8:06 pm at Sun Dec 22, 2019 8:06 pm
>
> 
Fb_DAI_morph.exe can't be used to get custom Inquisitor
that tool is not public

What do I have to do to get it? 


Second question, what would it take to talk you into releasing it?


Originial question still standing - how do I get the MorphResource-files? Do I need the non-public tool?
## Post #471
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-12-22T15:15:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from manavortex ↑Sun Dec 22, 2019 10:44 pm at Sun Dec 22, 2019 10:44 pm
>
> 
What do I have to do to get it? 
Second question, what would it take to talk you into releasing it?
Originial question still standing - how do I get the MorphResource-files? Do I need the non-public tool?

i'm not giving this tool to anyone
i'm not going to release it
MorphResource files are only present for models made with standard morphs, like adamant clarel

as i said before:

> Reply from daemon1 ↑Mon Feb 18, 2019 3:26 am at Mon Feb 18, 2019 3:26 am
>
> 
Cutsom inquisitor tool is ready. But it will not be published, at least yet.
Those who want to extract cutsom faces, PM me.

after 1 year, only 2 people PMed me about it, and last person didn't even reply to my PM when i got the model for him
## Post #472
- Username: manavortex
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 26, 2019 6:36 am
- Post datetime: 2019-12-22T17:59:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sun Dec 22, 2019 11:15 pm at Sun Dec 22, 2019 11:15 pm
>
> 
as i said before:
daemon1 wrote: ↑Mon Feb 18, 2019 3:26 am
Cutsom inquisitor tool is ready. But it will not be published, at least yet.
Those who want to extract cutsom faces, PM me.
I thought, maybe that has changed in the meantime. 

> Reply from daemon1 ↑Sun Dec 22, 2019 11:15 pm at Sun Dec 22, 2019 11:15 pm
>
> 
after 1 year, only 2 people PMed me about it, and last person didn't even reply to my PM when i got the model for him

I have done that a minute ago, and I _will_ reply.
## Post #473
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-12-23T19:07:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from manavortex ↑Sat Dec 21, 2019 9:59 pm at Sat Dec 21, 2019 9:59 pm
>
> I've used the Python3 extraction tools to do a full dump [..........
............................................]
It seems to me that after the dump I should have .meshset files, but I don't. What am I doing wrong? 

I don't have the .meshset or .MorphResource-files, and I have no idea how to get them....
Although that IS the one to go to script, for complete full extraction since it has been thoroughly updated to dump everything from all supported games, patches and DLCs included, after many attempts in trying to explain the dev behind the scripts that old tools depend on proper names extension for resources inside the RES folder, you already have all required files in your dump folder, unfortunately they are all named .res as extension, and knowing which one it is on your own is nearly impossible.
So what I suggest is make a issue on his GitHub page and explain your situation, because there's a chance he might add support for it.

best of luck

Also this will help in getting the names of the files: [viewtopic.php?p=147373#p147373](https://forum.xentax.com/viewtopic.php?p=147373#p147373)
## Post #474
- Username: manavortex
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 26, 2019 6:36 am
- Post datetime: 2019-12-23T19:58:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Tue Dec 24, 2019 3:07 am at Tue Dec 24, 2019 3:07 am
>
> 
So what I suggest is make a issue on his GitHub page and explain your situation, because there's a chance he might add support for it.

best of luck

Hey mono,
thanks for the answer, here I thought I was stupid.  
I have gotten in touch with the people already about dynamic path import, maybe we can tackle the other problem as well between the years. Thank you again!
## Post #475
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-01-06T01:20:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Daemon1, do you have any plans on releasing your Frostbite animation extraction tools? I noticed that the thread was lost along with the Facepunch forums.
## Post #476
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-01-06T07:09:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from TrumpetPro ↑Mon Jan 06, 2020 9:20 am at Mon Jan 06, 2020 9:20 am
>
> 
Daemon1, do you have any plans on releasing your Frostbite animation extraction tools? I noticed that the thread was lost along with the Facepunch forums.
i had only test runs, with manual selection of somethings
completing the proper tool will require more work and i never had time for it
## Post #477
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-01-12T13:20:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hello, how i can extract Mirror`s Edge Catalyst models, i use Crofty tutorial. drop plastic_head_mesh f0c51400.MeshSet on .exe (i try all) only Fb_MEA_mesh.exe
give me plastic_head_mesh.ascii/plastic_head_mesh.smd - size 1kb
maybe what am i doing wrong, need help
[image.jpg](https://xentaxbackup.github.io/file/17333_image.jpg)
## Post #478
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-01-12T14:43:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Crazy31139 ↑Sun Jan 12, 2020 9:20 pm at Sun Jan 12, 2020 9:20 pm
>
> 
Hello, how i can extract Mirror`s Edge Catalyst models
i think i never supported Mirror`s Edge Catalyst models
i just made facefixes for this game
## Post #479
- Username: RalaHawke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 13, 2020 3:52 am
- Post datetime: 2020-01-14T20:54:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sun Dec 22, 2019 11:15 pm at Sun Dec 22, 2019 11:15 pm
>
> 
manavortex wrote: ↑Sun Dec 22, 2019 10:44 pm
What do I have to do to get it? 
Second question, what would it take to talk you into releasing it?
Originial question still standing - how do I get the MorphResource-files? Do I need the non-public tool?


i'm not giving this tool to anyone
i'm not going to release it
MorphResource files are only present for models made with standard morphs, like adamant clarel

as i said before:
daemon1 wrote: ↑Mon Feb 18, 2019 3:26 am
Cutsom inquisitor tool is ready. But it will not be published, at least yet.
Those who want to extract cutsom faces, PM me.


after 1 year, only 2 people PMed me about it, and last person didn't even reply to my PM when i got the model for him

I have sent you a message recently about this topic  But only 2 ppl pmed you? That is not so much ...
## Post #480
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-01-15T18:27:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from RalaHawke ↑Wed Jan 15, 2020 4:54 am at Wed Jan 15, 2020 4:54 am
>
> 
I have sent you a message recently about this topic  But only 2 ppl pmed you? That is not so much ...
you said you're new to this
i'm not sure you can use the model exported
why do you need it?
## Post #481
- Username: RalaHawke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 13, 2020 3:52 am
- Post datetime: 2020-01-15T21:45:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Thu Jan 16, 2020 2:27 am at Thu Jan 16, 2020 2:27 am
>
> 
RalaHawke wrote: ↑Wed Jan 15, 2020 4:54 am
I have sent you a message recently about this topic  But only 2 ppl pmed you? That is not so much ...  

you said you're new to this
i'm not sure you can use the model exported
why do you need it?

I'm new to extracting files, but not working with them  I create pictures with the extracted models. A lot of people upload NPCs, main characters etc. from the DA games to deviantart so others can use them for creating pictures, renders etc. Like this one: [https://www.deviantart.com/alistairanda ... -663324808](https://www.deviantart.com/alistairandanders/art/I-Will-Come-To-You-Tonight-663324808)
I love creating those pics too and it would really help me if my Inquisitor was extracted, of course I would give credit to you  But I cannot get NinjaRipper to work and with Frosti you can only extract meshes from the game that are not the Inquisitor. That is why
## Post #482
- Username: Jon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 04, 2018 7:39 am
- Post datetime: 2020-01-28T08:47:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

It's been years but since Facepunch closed I am not aware of the theme, what happened to the process of extracting animations?
## Post #483
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-01-28T15:42:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Jon ↑Tue Jan 28, 2020 4:47 pm at Tue Jan 28, 2020 4:47 pm
>
> what happened to the process of extracting animations?
As far as I know, only research/tests have been done, yet no tool ever released.
## Post #484
- Username: Adog76
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 31, 2020 7:29 am
- Post datetime: 2020-02-06T04:16:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Is there a tutorial on how to use the 3D models in UE4 after extracting them?
## Post #485
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2020-03-05T12:42:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi everyone,

I'm writing here to ask a question about exporting EASpeex encoded audio from one game and then reimporting it into another one. I'm wanting to export team-specific & player-specific English language commentary lines from 2014 FIFA World Cup Brazil and then reimport them into the English language commentary files for FIFA16. The only information that I can gather from the relevant .sbs & .sbr files is that the audio is encoded using EASpeex and the filetype is .aiff. Can anyone help with this?
## Post #486
- Username: MauMau
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 10, 2020 7:42 am
- Post datetime: 2020-05-09T23:51:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi!
I'm amazed to see that there is a tool that can extract Inquisitor and Ryder headmorphs! I did not think it was possible! :O
I can imagine lots of use for it now that Frosty tools have mesh import function. Great job!
## Post #487
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-11T00:28:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

How do I use this with Need for Speed The Run? Need me that good Christian Hendricks models yo
## Post #488
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-05-16T14:12:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Mon May 11, 2020 8:28 am at Mon May 11, 2020 8:28 am
>
> 
How do I use this with Need for Speed The Run? Need me that good Christian Hendricks models yo

Are you gonna be posting ti where you usually post?
## Post #489
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-16T19:06:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hell yeah pal!

But um, I need to extract their models first and idk how to.
## Post #490
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-06-09T01:35:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Sun May 17, 2020 3:06 am at Sun May 17, 2020 3:06 am
>
> 
Hell yeah pal!

But um, I need to extract their models first and idk how to.

Any luck so far?
## Post #491
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-06-09T13:50:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Sorry no, I haven't downloaded The Run again yet to try ripping anything from it. The instructions for doing so look a little complicated to me as well so I'm not so sure I can even do it tbh. I'm waiting for someone to rip models from Blood and Truth since I don't have a PS4 in the meantime.
## Post #492
- Username: cobaltbluebengal
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 04, 2016 12:15 am
- Post datetime: 2020-07-19T12:47:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi, I got Anthem from the Origin Basic pass as I played on console so figured I'd download it on Origin as I wanted to get the model to try 3D print my Javalin that I use (Sad I know!)

It seems happy to read the Anthem files but then prompts me with a requring an Encryption Key, I assume this is the same sort of AES code that things like Fortnite uses. Anyone know how I can find this key out as I got the game through the subscription rather than outright purchase.

Thanks in advance
## Post #493
- Username: TAB533
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 25, 2018 2:37 am
- Post datetime: 2020-07-31T01:39:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi, I am a complete noob when it comes to file extractions/running scripts/etc.

If I'm wanting audio files from Battlefront 2, am I supposed to use UFBE to extract data first and then run python scripts?

I have the correct Python build, I have all the needed tools and a copy of the full game. It's just unclear to me WHEN exactly to use each tool on what. Keep in mind, I'm just wanting access to audio.
## Post #494
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-07-31T17:25:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from cobaltbluebengal ↑Sun Jul 19, 2020 8:47 pm at Sun Jul 19, 2020 8:47 pm
>
> 
Hi, I got Anthem from the Origin Basic pass as I played on console so figured I'd download it on Origin as I wanted to get the model to try 3D print my Javalin that I use (Sad I know!)

It seems happy to read the Anthem files but then prompts me with a requring an Encryption Key, I assume this is the same sort of AES code that things like Fortnite uses. Anyone know how I can find this key out as I got the game through the subscription rather than outright purchase.

Thanks in advance

Key is the same as FIFA 18.
## Post #495
- Username: TAB533
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 25, 2018 2:37 am
- Post datetime: 2020-08-11T07:24:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

nvm i finally finished reading through all thirty or so pages of this thread. Onto something new.
## Post #496
- Username: DarthPyro52
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 23, 2017 3:53 pm
- Post datetime: 2020-10-02T23:09:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Anyone have a way to extract content from Star Wars: Squadrons?
## Post #497
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-03T05:08:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from DarthPyro52 ↑Sat Oct 03, 2020 7:09 am at Sat Oct 03, 2020 7:09 am
>
> 
Anyone have a way to extract content from Star Wars: Squadrons?
[viewtopic.php?f=10&t=19074](https://forum.xentax.com/viewtopic.php?f=10&t=19074)
## Post #498
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2020-10-12T21:18:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I was on DeviantART yesterday, and someone was able to extract models of Wedge & a TIE Pilot from Squadrons. Don't know how that user did it.
## Post #499
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-12T21:21:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Seriously, both tools and script are posted in here, just search, as well how to fix the faces.

Including this one too.
[viewtopic.php?f=10&t=19074](https://forum.xentax.com/viewtopic.php?f=10&t=19074)
## Post #500
- Username: DarthPyro52
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 23, 2017 3:53 pm
- Post datetime: 2020-11-11T03:11:20+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Eradicon ↑Tue Oct 13, 2020 5:18 am at Tue Oct 13, 2020 5:18 am
>
> 
I was on DeviantART yesterday, and someone was able to extract models of Wedge & a TIE Pilot from Squadrons. Don't know how that user did it.
Those are Stym's renders, he didn't extract them himself, he downloaded them from here:
[https://groinkick.freeforums.net/thread ... -squadrons](https://groinkick.freeforums.net/thread/46/star-wars-squadrons)

Long story short there's a private build of Frosty that only a couple people have.
## Post #501
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-11-12T01:44:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from DarthPyro52 ↑Wed Nov 11, 2020 11:11 am at Wed Nov 11, 2020 11:11 am
>
> 
Eradicon wrote: ↑Tue Oct 13, 2020 5:18 am
I was on DeviantART yesterday, and someone was able to extract models of Wedge & a TIE Pilot from Squadrons. Don't know how that user did it.
Those are Stym's renders, he didn't extract them himself, he downloaded them from here:
https://groinkick.freeforums.net/thread ... -squadrons

Long story short there's a private build of Frosty that only a couple people have.

Thank you. It's great to know the models are already available if you know where to look
## Post #502
- Username: Cornalito
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 19, 2018 5:52 am
- Post datetime: 2021-01-09T15:48:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

These tools works with files from NFS Heat?
## Post #503
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-09T16:03:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Cornalito ↑Sat Jan 09, 2021 11:48 pm at Sat Jan 09, 2021 11:48 pm
>
> 
These tools works with files from NFS Heat?
Nope, as there is no current dumper/extractor for its assets, as its part of same new format that Anthem and PvZBFN games have and are unsupported as well.
## Post #504
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2021-11-22T14:57:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hello, maybe someone have any information about extracting model animations from anthem? I can extract game resources using (anthemtool) and extract models with textures and skeleton (frosty editor) but i need animations
## Post #505
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-11-22T20:00:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Naznarok ↑Mon Nov 22, 2021 10:57 pm at Mon Nov 22, 2021 10:57 pm
>
> 
Hello, maybe someone have any information about extracting model animations from anthem?...
Currently there's no tool out there that supports Frostbite animations. Trust me, i wish.
## Post #506
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-14T11:26:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Working on Battlefield 2042.

Already extracted archives and got models with bones and textures:





Vehicles and weapons also work:
## Post #507
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-14T15:08:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

More like Crapfield 2042 lol.
## Post #508
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-14T20:52:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Fri Jan 14, 2022 11:08 pm at Fri Jan 14, 2022 11:08 pm
>
> 
More like Crapfield 2042 lol.
Regardless, game play has nothing to do with reversing its assets, it has great content no matter what the reviews/players etc have to say, we don't discuss here the quality of a game play, that's a whole different topic for other forums that deal with that mess
## Post #509
- Username: g0rd0nfr33man
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 16, 2022 9:38 am
- Post datetime: 2022-01-16T23:05:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hello guys, first post here. I've been using Frosty's convenience to port from BF4, but I was wondering what program can rip from Battlefield 3 with the model's skeleton?
## Post #510
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-01-26T13:14:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Fri Jan 14, 2022 7:26 pm at Fri Jan 14, 2022 7:26 pm
>
> 
Already extracted archives and got models with bones and textures:
Hello! How can I unpack the game?
## Post #511
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-26T13:47:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Battlefield 2042 tool.

Dumping the game

1. Change paths in the .INI to your folders. Set parameter on the 3rd line to only dump "ebx" "res" or "chunks". If no parameter (empty line), it will dump them all.
2. Place oo2core_8_win64.dll from the game to the same folder
3. Drag any .TOC file onto toc2042.exe, and it will extract everything that was listed in that file

Converting models

bf2042_mesh.exe <meshset>
or 
bf2042_mesh.exe <meshset> <skeleton>

Tool will find the needed chunk automatically in the same folder, "chunks" subfolder, or folder structure created by dumper.
If no skeleton name provided, tool will ask for default _soldierskeleton.ebx skeleton (which you can find in globals.toc)
[2042.rar](https://xentaxbackup.github.io/file/21674_2042.rar)
## Post #512
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-26T14:08:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Now while i'm back to frostbite engine, also adding support for other games.

For example, all latest Need For Speed games, from 2011 "The Run" to 2019s "Heat"
## Post #513
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-01-26T17:56:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 9:47 pm at Wed Jan 26, 2022 9:47 pm
>
> 
Battlefield 2042 tool.

Thank you very much! Now I will try)
## Post #514
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-01-26T22:23:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 9:47 pm at Wed Jan 26, 2022 9:47 pm
>
> 
Converting models

bf2042_mesh.exe <meshset>
or 
bf2042_mesh.exe <meshset> <skeleton>
did not understand how to run it?
## Post #515
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-26T23:02:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 10:08 pm at Wed Jan 26, 2022 10:08 pm
>
> 
Now while i'm back to frostbite engine, also adding support for other games.

For example, all latest Need For Speed games, from 2011 "The Run" to 2019s "Heat"

Does it support the character models from NFS: The Run too by any chance?
## Post #516
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-27T00:18:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Dimka51Rus ↑Thu Jan 27, 2022 6:23 am at Thu Jan 27, 2022 6:23 am
>
> ...did not understand how to run it?
It means you must run it in command prompt, or use a .bat file to run what he described above.

> Reply from Assasinge ↑Thu Jan 27, 2022 7:02 am at Thu Jan 27, 2022 7:02 am
>
> ...Does it support the character models from NFS: The Run too by any chance?
Only one way to find out, and by the way you quoted the whole thing, edit it, it is very messy.
## Post #517
- Username: Kovalsky20456
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 28, 2017 12:24 am
- Post datetime: 2022-01-27T06:16:12+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 9:47 pm at Wed Jan 26, 2022 9:47 pm
>
> 
Battlefield 2042 tool.

Dumping the game

1. Change paths in the .INI to your folders. Set parameter on the 3rd line to only dump "ebx" "res" or "chunks". If no parameter (empty line), it will dump them all.
2. Place oo2core_8_win64.dll from the game to the same folder
3. Drag any .TOC file onto toc2042.exe, and it will extract everything that was listed in that file

Converting models

bf2042_mesh.exe <meshset>
or 
bf2042_mesh.exe <meshset> <skeleton>

Tool will find the needed chunk automatically in the same folder, "chunks" subfolder, or folder structure created by dumper.
If no skeleton name provided, tool will ask for default _soldierskeleton.ebx skeleton (which you can find in globals.toc)

Hey man, Im sorry for asking such dumb questions, but how did you manage to convert textures with Itexture converter included in this thread? I mean, maybe there's more actual version somewhere, which i couldnt find for a reason.
## Post #518
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-27T07:00:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Thu Jan 27, 2022 7:02 am at Thu Jan 27, 2022 7:02 am
>
> 
Does it support the character models from NFS: The Run too by any chance?
Yes, it supports all characters, vehicles and static models in all games.
## Post #519
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-27T09:04:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Mesh tools for Need For Speed:
- The run (2011)
- Rivals (2013)
- Need For Speed (2016)
- Payback (2017)
- Edge (2018)

All of them work as my usual frostbite model tools.










[nfs_2011_2018.rar](https://xentaxbackup.github.io/file/21680_nfs_2011_2018.rar)
## Post #520
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-01-27T10:56:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Thu Jan 27, 2022 8:18 am at Thu Jan 27, 2022 8:18 am
>
> 
It means you must run it in command prompt, or use a .bat file to run what he described above.
Yes, I understood this, I tried it through the .bat file, but nothing happens. (
## Post #521
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-27T11:01:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Kovalsky20456 ↑Thu Jan 27, 2022 2:16 pm at Thu Jan 27, 2022 2:16 pm
>
> 
Hey man, Im sorry for asking such dumb questions, but how did you manage to convert textures with Itexture converter included in this thread? I mean, maybe there's more actual version somewhere, which i couldnt find for a reason.
I know some people were able to get textures. I was not checking their progress, but i know it was all the same, or very similar to previous games.
## Post #522
- Username: Kovalsky20456
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 28, 2017 12:24 am
- Post datetime: 2022-01-27T11:14:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Thu Jan 27, 2022 7:01 pm at Thu Jan 27, 2022 7:01 pm
>
> 
Kovalsky20456 wrote: ↑Thu Jan 27, 2022 2:16 pm
Hey man, Im sorry for asking such dumb questions, but how did you manage to convert textures with Itexture converter included in this thread? I mean, maybe there's more actual version somewhere, which i couldnt find for a reason.

I know some people were able to get textures. I was not checking their progress, but i know it was all the same, or very similar to previous games.

Aight, thank you very much! I'll check if I missed something while trying to convert'em.
## Post #523
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-27T12:06:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

The Frostbite Python scripts here say they only support movies and sounds:

[https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)

How do I unpack the actual assets so I can use the tools posted?
## Post #524
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-27T15:33:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Thu Jan 27, 2022 8:06 pm at Thu Jan 27, 2022 8:06 pm
>
> 
The Frostbite Python scripts here say they only support movies and sounds:
…
How do I unpack the actual assets so I can use the tools posted?
It supports textures too but ONLY on the games under Frostbite 2 engine.

And as the description says on GitHub, you literally went to step three instead of first one, it clearly states for each what they do and what their for.

> dumper - adjust the paths at the start and run it to dump all the contents of superbundles; all the other scripts are meant to be used with the resulting dump
>
> 
>
> ebxtotext - converts EBX files to plain text TXT; useful if you want to view the game's scripts, etc
>
> 
>
> ebxtoasset - runs through EBX files and uses known EBX types to extract assets from chunks, the resulting file takes the EBX name; currently, only sounds and movies are supported
You can’t go to step three with out performing step one first, as step two is only optional.
## Post #525
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-27T16:27:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Thu Jan 27, 2022 11:33 pm at Thu Jan 27, 2022 11:33 pm
>
> 
Assasinge wrote: ↑Thu Jan 27, 2022 8:06 pm
The Frostbite Python scripts here say they only support movies and sounds:
…
How do I unpack the actual assets so I can use the tools posted?

It supports textures too but ONLY on the games under Frostbite 2 engine.

And as the description says on GitHub, you literally went to step three instead of first one, it clearly states for each what they do and what their for.
dumper - adjust the paths at the start and run it to dump all the contents of superbundles; all the other scripts are meant to be used with the resulting dump

ebxtotext - converts EBX files to plain text TXT; useful if you want to view the game's scripts, etc

ebxtoasset - runs through EBX files and uses known EBX types to extract assets from chunks, the resulting file takes the EBX name; currently, only sounds and movies are supported
You can’t go to step three with out performing step one first, as step two is only optional.

Ok sorry, I got it now. I managed to extract the textures but I'm a little confused on how mesh extraction works, where would I find them? The dumper.py worked and I also got to step 3 successfully, I'm just a little uneducated on Frostbite 2's structure of how meshes and skeletons work. I'm currently extracting cars and characters from NFS: The Run.

This is how I'm trying to currently extract a character:



Whenever I drag the meshset onto the tool, it outputs an .smd and .ascii with empty data of 0kb. What am I doing wrong?
## Post #526
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-01-27T17:14:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 9:47 pm at Wed Jan 26, 2022 9:47 pm
>
> 
2. Place oo2core_8_win64.dll from the game to the same folder
Without this file, it does not unpack files at all.
## Post #527
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-01-27T17:15:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge
>
> 
Whenever I drag the meshset onto the tool, it outputs an .smd and .ascii with empty data of 0kb. What am I doing wrong?

I have exactly the same in bf2042
## Post #528
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-27T17:54:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Yeah same here, I tried to follow Crofty's tutorial on Deviantart, I made it this far but I don't know exactly what is holding up the extraction, maybe it's the skeleton? Sam already has her own master skeleton in the ebx directory, but it doesn't seem to work.
## Post #529
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-27T18:18:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Fri Jan 28, 2022 1:54 am at Fri Jan 28, 2022 1:54 am
>
> 
Yeah same here, I tried to follow Crofty's tutorial on Deviantart, I made it this far but I don't know exactly what is holding up the extraction, maybe it's the skeleton? Sam already has her own master skeleton in the ebx directory, but it doesn't seem to work.
master skeleton is wrong skeleton
you need real skeleton, which is not that small
## Post #530
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-27T18:26:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Fri Jan 28, 2022 2:18 am at Fri Jan 28, 2022 2:18 am
>
> 
Assasinge wrote: ↑Fri Jan 28, 2022 1:54 am
Yeah same here, I tried to follow Crofty's tutorial on Deviantart, I made it this far but I don't know exactly what is holding up the extraction, maybe it's the skeleton? Sam already has her own master skeleton in the ebx directory, but it doesn't seem to work.

master skeleton is wrong skeleton
you need real skeleton, which is not that small

And where would I find that? There's several "skeletons" in the dump I have but I don't know which one to use.
## Post #531
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-27T19:51:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Ok so I found a skeleton that is 31 KB, is that the one? Because that doesn't work either, I even renamed it to veniceantske01 and I still get the same output problem.

I ran a cmd prompt and ended up with this:



But when I searched my dump for that chunk apparently I don't even have it, how is that possible?
## Post #532
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-27T20:09:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

@Assasinge, i really need you to learn to edit your posts, or to learn to quote the right way, STOP quoting the WHOLE post, it is very messy, many stop helping others because they refuse to be organized, it is aggravating that to this day most refuse to pay attention.
## Post #533
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-27T21:18:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Fri Jan 28, 2022 3:51 am at Fri Jan 28, 2022 3:51 am
>
> 
But when I searched my dump for that chunk apparently I don't even have it, how is that possible?
As you can see on your screen, the problem is missing chunk
## Post #534
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-27T21:59:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

What are you people talking about? Whenever I quote someone this is all I see:



I literally see no problem with this, I don't know what this "mess" you guys are seeing because I ain't seeing it.
## Post #535
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-27T22:35:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Alright, there are two examples:

Example 1: The right way, you ONLY edit what ever is necessary or it is your responding about:

> Reply from Assasinge ↑Fri Jan 28, 2022 5:59 am at Fri Jan 28, 2022 5:59 am
>
> 
What are you people talking about?...
Neat and clean, right? 

Example 2: The BAD ONE! where a user quotes the WHOLE post, like this:

> Reply from Assasinge ↑Fri Jan 28, 2022 5:59 am at Fri Jan 28, 2022 5:59 am
>
> 
What are you people talking about? Whenever I quote someone this is all I see:



I literally see no problem with this, I don't know what this "mess" you guys are seeing because I ain't seeing it.
See the difference? BAD.

Also, check this link posted on this post: [viewtopic.php?p=181450#p181450](https://forum.xentax.com/viewtopic.php?p=181450#p181450)

On topic:

> Reply from Assasinge ↑Fri Jan 28, 2022 2:26 am at Fri Jan 28, 2022 2:26 am
>
> And where would I find that? There's several "skeletons" in the dump I have but I don't know which one to use.
The reason you cant see it right away, the scripts dump the folder structure by separating RES from EBX.
Inside the "bundles\" folder you'll have three folders "chunks, ebx, res"
EBX and RES have same identical structure the difference is that on EBX folder you will see extra folders with EBXs.
So when you search for a character in the RES folder, the skeleton is in same location BUT this time around in the EBX folder, it is always the larges one, usually *_skel.ebx or *_skeleton.ebx in this case, or for universal use there is a unique skeleton for ALL character, like the venice one.

> Reply from Assasinge ↑Fri Jan 28, 2022 3:51 am at Fri Jan 28, 2022 3:51 am
>
> ...But when I searched my dump for that chunk apparently I don't even have it, how is that possible?
That is because the scripts are using actual GUID format for the *.chunk data, so a chunk GUID name that is like this:

```
000a9fdf-d418-1e85-9563-c150bd5a80df.chunk
```

MUST be converted like this:

```
df9f0a0018d4851e9563c150bd5a80df.chunk
```

As you can see dashes are removed, first 8 bytes must be swapped while the other 8 bytes remain unchanged, i recommend a Regular Expression software or script that would do that for you on the entire chunk folder.
Like this:

```

	Expression:	\A(..)(..)(..)(..)-(..)(..)-(..)(..)-(..)(..)-(.*)\Z
	Replace:	$4$3$2$1$6$5$8$7$9$10$11
	Skip Extension: YES
```

Then, and only then you will be able to convert and see this in Blender:



PS: I was able to quote/respond to multiple posts in one post, keeping it clean, ain't that something?
## Post #536
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-27T23:35:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Oh I see. I wasn't aware, I will try to be clean next time then thank you. And thanks for that last bit as well, I thought I had run the dumper script wrong but it appears not. I don't really understand the last bit though, are you saying I have to program a script from scratch that will rename all the chunk files I currently have into the ones I need? I have no idea how to do that :/
## Post #537
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-28T00:42:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Fri Jan 28, 2022 7:35 am at Fri Jan 28, 2022 7:35 am
>
> ...are you saying I have to program a script from scratch that will rename all the chunk files I currently have into the ones I need? I have no idea how to do that :/
I've said not such thing, what i said is to use the Regular Expression feature above, in a software, or a script or tool or what ever the case may be, that supports that feature called Regular Expressions.

Ok, for past few days I've been testing the following: [https://www.den4b.com/products/renamer](https://www.den4b.com/products/renamer)
It is fast, easy to use, most importantly, gets the job done and it is FREE and/or portable.

You add the Regular Expression rule i mentioned above first, then drag and drop your chunks folders where it tells you to drop, if it asks you to validate the files, click NO, click rename and that's it.
If you still cant convert, and get that "chunk not found" message, it means you might have to move/merge chunks from "root\bundles\chunks" to "root\chunks" folder, if it asks you to overwrite, choose NO, then it should all be fine.

Even so, there's a problem, you first MUST convert the textures, as the ebxtoasset script requires the chunks to have proper GUIDs with those dashes and bytes swapped, then you can rename both .chunk files in the chunks folders and then you can convert the models.

NOTE: Don't ask me why these steps must be followed, because it is NOT my doing, its how it is, Nicknine will never update his scripts to support old tools, regardless what tools are out there, same way in this particular case daemon1 will never update his tools to support Nicknine's scripts, so yeah, let the fun begin
## Post #538
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-28T01:54:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

YOU ABSOLUTE LEGEND!

It worked. Thank you. Finally after all these years...
## Post #539
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-28T03:00:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I just hit a tiny snag, everything works great now but, and I'm not sure if this is specific to The Run in of itself, but the characters don't seem to have their own eye textures, I have a shared eye texture folder. Does FB2 somehow find a way to switch eye colors off of one texture? If there is a way to counter this that'd be neat because I don't think all the characters in the game use a single eye color.
## Post #540
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-28T19:33:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Fri Jan 28, 2022 11:00 am at Fri Jan 28, 2022 11:00 am
>
> ...the characters don't seem to have their own eye textures, I have a shared eye texture folder...
Most games, at least from what i have encountered have common/shared textures, and this is no different, you'll have to use the common/shared textures for eyes, inner mouth, etc and what ever else the game has.
## Post #541
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-29T17:15:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Updated versions for Edge, Rivals & The Run to set parts to their places (wheels, spoilers etc)




[NFS_upd.7z](https://xentaxbackup.github.io/file/21693_NFS_upd.7z)
## Post #542
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-29T22:06:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Jan 29, 2022 3:33 am at Sat Jan 29, 2022 3:33 am
>
> 
Most games, at least from what i have encountered have common/shared textures, and this is no different, you'll have to use the common/shared textures for eyes, inner mouth, etc and what ever else the game has.

You're not entirely wrong but if you look at some of the character renders and some of the in-game cutscenes, you can see the characters have different eye colors in respect to the actors' likenesses, I was wondering how they did that.
## Post #543
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-30T15:07:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Assasinge ↑Sun Jan 30, 2022 6:06 am at Sun Jan 30, 2022 6:06 am
>
> ...you can see the characters have different eye colors in respect to the actors' likenesses, I was wondering how they did that.
I personally never found any of them, individually per character, that tells me its done by materials while using the common/shared assets.

Note:
For those of you that will wonder why the wheel parts are missing (right side) in The Run after proper placement.
Each car has its own body kit, and one set of wheel parts for front left and rear left, and it must be mirrored in your 3d editor and depending how you extracted the game, their located at:

main body kit: \bundles\_c4\vehicles\nfs or: \bundles\res\_c4\vehicles\nfs
other body kits: \bundles\_c4\blueprint\bodykitblueprints or: \bundles\res\_c4\blueprint\bodykitblueprints

Note2:
The wheel parts will have to be pushed slightly outward to fit each bodykit a car might have, yes the positions are all correct you just have to perform that extra step before mirroring them to the right side.
## Post #544
- Username: kiko150
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 31, 2022 11:35 pm
- Post datetime: 2022-01-31T16:31:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 9:47 pm at Wed Jan 26, 2022 9:47 pm
>
> 
Battlefield 2042 tool.

Hey! I've tried to get the textures using the converter, but whenever I hit the "get DDS" button it just shows the number and it doesn't do anything else. 
I also tried to look for the exact chunks that are shown in the converter and I couldn't find them, the only chunks I've found had a similar name. 
Here is an example of the similar chunks:

01010000424F71FCCA19B1CF7AFCED6E - from the converter
424F71FCCA19B1CF7AFCED6E728901C3 - dumped chunk

I'm not really sure if it has something to do with this, because I tried to rename them and it didnt work... Any ideas what could be wrong?
## Post #545
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-31T17:41:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

NFS Heat.

The latest and most advanced game, with lots of cars and character combinations. All static models also supported.
Usage is almost same as 2042 tool, read it here - [viewtopic.php?p=181685#p181685](https://forum.xentax.com/viewtopic.php?p=181685#p181685)
Doesnt matter which oodle version the game uses, just take the one you have, and rename it to oo2core_8_win64.dll

1. Dump the game with TOC tool. If you also want patch, first dump patch with toc_heat_patch.exe, then main game with toc_heat.exe. This is because tool will NOT overwrite files, so patch first, then base game. Dont forget to change path in the .INI for "patch" or "data" folders.

2. Convert models with Fb_NFS_Heat.exe






[nfs_heat.7z](https://xentaxbackup.github.io/file/21737_nfs_heat.7z)
## Post #546
- Username: keegan1999
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 28, 2017 11:01 pm
- Post datetime: 2022-02-03T12:35:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 9:47 pm at Wed Jan 26, 2022 9:47 pm
>
> 
Battlefield 2042 tool.

How i can convert BF2042 textures ?

Edit1: I tried to use Batch_Itexture_Converter_SWBF2 but it doesn't convert textures to dds
Info from converter
GUID = 01010000643F48F0873606537DBEED11    t_wep_rifle__m16a2_handguard_02_cs.Texture  2048 x 2048
GUID = 01010000BBD601879EBE6399CFB4AB9A    t_wep_rifle__m16a2_handguard_02_cs_3p.Texture  512 x 512
## Post #547
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-02-04T09:48:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

unpacked all vehicles from 2042
[https://ibb.co/7Vsz7tV](https://ibb.co/7Vsz7tV)
## Post #548
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-05T17:31:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

NFS Heat tool updated.

Now dumper tools add metadata to resource names, so you can export meshes with inline geometry (not in external chunk, but in meshset itself)
## Post #549
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-08T17:20:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Anthem dump/models tools

Usage is the same as NFS Heat, actually dump tool IS actually same tool, just renamed.






[anthem.7z](https://xentaxbackup.github.io/file/21748_anthem.7z)
## Post #550
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-10T20:01:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Now after all games covered, i decided to look into maps.
Here are some examples.

Payback:



The Run:





Anthem:
## Post #551
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2022-02-13T19:05:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

"Batch_Itexture_Converter_SWBF2.exe" Hello! Can this tool be updated to support Anthem textures?
## Post #552
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-14T12:27:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

A friend of mine made these tools to help dump textures. Haven't tested Anthem .textures but maybe it could work with that title aswell.

The tools rely on id-daemon's RawtexCmd and Microsoft's texconv, attempting to run the tool without those files present will cause errors. RawtexCmd can be downloaded from [viewtopic.php?t=16461](https://forum.xentax.com/viewtopic.php?t=16461) and texconv can be found at [https://github.com/Microsoft/DirectXTex/releases](https://github.com/Microsoft/DirectXTex/releases). Make sure to place both RawtexCmd.exe and texconv.exe in the same folder as BF2042TexTool.exe and NFSHeatTexTool.exe before running them.

Credit revetix  and id daemon  

[](https://ibb.co/Vqt9wDN)
[Frostbite Texture Tools.zip](https://xentaxbackup.github.io/file/21778_Frostbite Texture Tools.zip)
## Post #553
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2022-02-14T14:40:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sharppy ↑Mon Feb 14, 2022 8:27 pm at Mon Feb 14, 2022 8:27 pm
>
> 
Make sure to place both RawtexCmd.exe and texconv.exe in the same folder as BF2042TexTool.exe
Hello, thx! But can you give exact instructions on how to use those tools?
## Post #554
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-14T14:41:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sharppy ↑Mon Feb 14, 2022 8:27 pm at Mon Feb 14, 2022 8:27 pm
>
> ...Make sure to place both RawtexCmd.exe and texconv.exe in the same folder as BF2042TexTool.exe and NFSHeatTexTool.exe before running them...
What exactly is the secret behind this magic, having all assets next to textures, it crashes, running a batch it crashes, drag and drop it crashes, no matter what the error is always:



Capture.PNG (12.86 KiB) Viewed 638 times


Wouldn't hurt to have actual info on how to use it.
## Post #555
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-14T14:54:20+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

You should just drop archive onto tool and it will process them if not maybe running a .bat tool for them ?  and yes EBX and CHUNKS should be in 1 folder. I merged RES with EBX then just placed tool into main folder and it processed. 
[](https://ibb.co/h7Y0yXM)
## Post #556
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-14T15:00:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sharppy ↑Mon Feb 14, 2022 10:54 pm at Mon Feb 14, 2022 10:54 pm
>
> 
You should just drop archive onto tool and it will process them if not maybe running a .bat tool for them ?  and yes EBX and CHUNKS should be in 1 folder. I merged RES with EBX then just placed tool into main folder and it processed.
That's a bad idea to move chunks around, the chunks folder MUST be intact otherwise other conversions will fail, i can understand the EBX/RES merge folders inside bundles folder, but that should be it.
Anyway, i got it working by using the already described if you run just the tool as:

```
tool.exe working directory as second parameter
```

example:

```
NFSHeatTexTool.exe X:\FB\ANTHEM\bundles
```


There is only one problem, it exports only as PNG, very bad, it MUST be exported as DDS as well, or the choice between the two, you think he can update it?

I tested the Heat tool on Anthem, it seems to work, as Heat is same format as Anthem and Plansts vs Zombies Battle for Neighborville, which for those that do now know you can dump that game using either Heat/Anthem dump tool  same procedure.
## Post #557
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2022-02-14T15:03:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sharppy ↑Mon Feb 14, 2022 10:54 pm at Mon Feb 14, 2022 10:54 pm
>
> 
You should just drop archive onto tool and it will process them
Yes, now it works. Except normalMap. Can you please share a source code?
## Post #558
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-14T15:10:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I can also confirm the Heat texture tool works on Plants vs Zombies Battle for Neighborville, except quite a few textures that require alpha channel intact on PNG get ruined, while other normal textures are converted incorrect, it needs to export as DDS, no other processing/conversions.
## Post #559
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-14T15:15:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Yeah i seen this issue im not sure how to go about fixing it.
## Post #560
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-14T15:18:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sharppy ↑Mon Feb 14, 2022 11:15 pm at Mon Feb 14, 2022 11:15 pm
>
> 
Yeah i seen this issue im not sure how to go about fixing it.
Check Nicknine's DDS python code for textures on Frostbite 2 games, and where he took the texture formats from, maybe his example will help:
[https://github.com/NicknineTheEagle/Fro ... te2/dds.py](https://github.com/NicknineTheEagle/Frostbite-Scripts/blob/master/frostbite2/dds.py)
And here at the end it shows how he reads texture header:
[https://github.com/NicknineTheEagle/Fro ... te2/ebx.py](https://github.com/NicknineTheEagle/Frostbite-Scripts/blob/master/frostbite2/ebx.py)
Obviously these new tools you posted are for Frostbite 3 engine but modifications should be minor, if your friend who made the tools knows already what he did I'm sure he will understand that python code and what needs to be changed.
## Post #561
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-14T15:28:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Tool Updated
[viewtopic.php?p=182107#p182107](https://forum.xentax.com/viewtopic.php?p=182107#p182107)

> Reply from mono24 ↑Mon Feb 14, 2022 11:10 pm at Mon Feb 14, 2022 11:10 pm
>
> 
I can also confirm the Heat texture tool works on Plants vs Zombies Battle for Neighborville, except quite a few textures that require alpha channel intact on PNG get ruined, while other normal textures are converted incorrect, it needs to export as DDS, no other processing/conversions.

Would need samples maybe it requires a new tool. .texture along with corresponding .chunk
## Post #562
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-14T15:54:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sharppy ↑Mon Feb 14, 2022 11:28 pm at Mon Feb 14, 2022 11:28 pm
>
> Would need samples maybe it requires a new tool. .texture along with corresponding .chunk
Yeah right now it fails at DX10 format, only the header is exported.
Will gather some samples then and PM you.
## Post #563
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-14T17:36:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Texture tools updated once more.
[viewtopic.php?p=182107#p182107](https://forum.xentax.com/viewtopic.php?p=182107#p182107)
-support for R8G8B8A8 and BC5U formats

NFS: Heat tool works for Anthem and PvZ
## Post #564
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-14T23:35:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sharppy ↑Tue Feb 15, 2022 1:36 am at Tue Feb 15, 2022 1:36 am
>
> 
Texture tools updated once more.
viewtopic.php?f=16&t=17114&start=540
Can you also edit/update link, it is incorrect, proper link is located in the post icon right before your forum name as in screenshot circled in red:



Capture.PNG (13.06 KiB) Viewed 684 times
## Post #565
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-16T09:26:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Map tool for NFS The Run.

First version, may be improved later. Most map objects properly placed, including those using havok and blueprints. Terriain not supported yet.

1. You have to dump the game, for example with this script: [https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts) (use frostbite 2 version).
Then merge chunks with bundles/chunks. Duplicated chunks inside bundles are not needed, so you can skip or overwrite them.
Also merge EBX and RES folders inside bundles, to place them all in the root of bundles folder.

2. Edit the included INI file with paths to your dump.

3. Run fb_maps_run_db.exe tool once, it will scan whole dump for meshsets and blueprints, so later maps can be converted fast, without the need to go into whole tree of assets. This will take a few minutes. After that, 2 files will be created: bp.db & meshnames.txt, which need to stay in the same folder for main tool to work.

4. use fb_maps_run.exe (main map tool) to convert maps. Drop any EBX on it, use in command line with 1 parameter, or create a batch.
Maps are in \_c4\levels\ folder. Most objects (such as roads and buildings) are in "level..." files, but also many objects in "layer..." and other smaller files inside subfolders.






[nfs_therun_maps.7z](https://xentaxbackup.github.io/file/21791_nfs_therun_maps.7z)
## Post #566
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-16T12:25:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

The python script above dumps chunks with dashes. For example: 1015579a-35ae-4827-95f9-71e720fa3ed1.chunk
To make them work with this map tool, you need to rename them after dump (using some automated tool)
or make a little change in the script (dbo.py file), so they will be dumped without dashes, remove these:
## Post #567
- Username: babymammoth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 16, 2020 1:21 am
- Post datetime: 2022-02-18T10:36:22+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

could someone kindly record a quick video of using the bf2042 tool? I think I have swiss cheese holes in the steps to take, so I'm running into unhandled exceptions...
## Post #568
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2022-02-20T11:38:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sharppy ↑Tue Feb 15, 2022 1:36 am at Tue Feb 15, 2022 1:36 am
>
> 
Texture tools updated once more.
viewtopic.php?p=182107#p182107
-support for R8G8B8A8 and BC5U formats
Hello! Thank you for this great tool! Can you add functionality to specify export format DDS/PNG or build separate tools for different format export? Exporting DDS and PNG same time consumes HDD space and time :/
## Post #569
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-02-21T00:49:22+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

BF2042
[](https://ibb.co/7Jmh8d7) [](https://ibb.co/xMc8vhm) [](https://ibb.co/wR4vy2N) [](https://ibb.co/6B1dnZv) [](https://ibb.co/xsCF48p)
## Post #570
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-02-21T15:27:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Daemon1, Thanks for the bf2042 file extraction utilities!
Is it possible to fix the bug by converting .dds textures, they need to be converted again due to unknown compression. (TXD5)
[](https://ibb.co/2qkFtbh)
## Post #571
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-21T15:42:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Dimka51Rus ↑Mon Feb 21, 2022 11:27 pm at Mon Feb 21, 2022 11:27 pm
>
> 
Daemon1, Thanks for the bf2042 file extraction utilities!
Is it possible to fix the bug by converting .dds textures, they need to be converted again due to unknown compression. (TXD5)
i'm not converting textures, no idea what are you talking about
## Post #572
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-02-21T15:44:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Mon Feb 21, 2022 11:42 pm at Mon Feb 21, 2022 11:42 pm
>
> 
Dimka51Rus wrote: ↑Mon Feb 21, 2022 11:27 pm
Daemon1, Thanks for the bf2042 file extraction utilities!
Is it possible to fix the bug by converting .dds textures, they need to be converted again due to unknown compression. (TXD5)

i'm not converting textures, no idea what are you talking about

BF2042TexTool.exe does not convert .dds files correctly
## Post #573
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-21T16:03:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Dimka51Rus ↑Mon Feb 21, 2022 11:44 pm at Mon Feb 21, 2022 11:44 pm
>
> 
BF2042TexTool.exe does not convert .dds files correctly
this is not my tool
## Post #574
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-02-21T17:32:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Tue Feb 22, 2022 12:03 am at Tue Feb 22, 2022 12:03 am
>
> 
Dimka51Rus wrote: ↑Mon Feb 21, 2022 11:44 pm
BF2042TexTool.exe does not convert .dds files correctly

this is not my tool

oh, i thought yours. OK.
## Post #575
- Username: kaliope
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 01, 2019 5:45 pm
- Post datetime: 2022-02-23T00:55:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi,

the ebx dumper is working just fine.

Does anybody have an ebx to txt (or xml) converter for the BF2042 ebx files?
## Post #576
- Username: RickModder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 22, 2020 4:20 pm
- Post datetime: 2022-02-23T04:34:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Dimka51Rus ↑Fri Feb 04, 2022 5:48 pm at Fri Feb 04, 2022 5:48 pm
>
> 
unpacked all vehicles from 2042
https://ibb.co/7Vsz7tV

How did you do this?
I was able to set the meshset in cmd, but it still just generates 0kb ascii and smd.
## Post #577
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2022-02-23T16:03:12+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from RickModder ↑Wed Feb 23, 2022 12:34 pm at Wed Feb 23, 2022 12:34 pm
>
> 
How did you do this?
I was able to set the meshset in cmd, but it still just generates 0kb ascii and smd.
Place all folders and files as in the screenshot.
find the skeleton (_soldierskeleton.ebx) and put it in the same folder.
You can open the .meshset with bf2042_mesh.exe
[](https://ibb.co/Gss6MCR)
## Post #578
- Username: RickModder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 22, 2020 4:20 pm
- Post datetime: 2022-02-23T17:03:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Dimka51Rus ↑Thu Feb 24, 2022 12:03 am at Thu Feb 24, 2022 12:03 am
>
> 
RickModder wrote: ↑Wed Feb 23, 2022 12:34 pm
How did you do this?
I was able to set the meshset in cmd, but it still just generates 0kb ascii and smd.

Place all folders and files as in the screenshot.
find the skeleton (_soldierskeleton.ebx) and put it in the same folder.
You can open the .meshset with bf2042_mesh.exe

Thanks for the reply!
I couldn't find _soldierskeleton.ebx, so I renamed the appropriate ebx and used it, and managed to successfully extract a non-0kb file.

By the way, sorry for the elementary question, but do you know how to convert Ascii to Obj or FBX? It seems to be a very common file format in this community, but I don't know how to handle it at all.
## Post #579
- Username: RickModder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 22, 2020 4:20 pm
- Post datetime: 2022-02-23T17:30:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Thanks for the reply!
I couldn't find _soldierskeleton.ebx, so I renamed the appropriate ebx and used it, and managed to successfully extract a non-0kb file.

By the way, sorry for the elementary question, but do you know how to convert Ascii to Obj or FBX? It seems to be a very common file format in this community, but I don't know how to handle it at all.
[/quote]

I've been browsing for a while and it's solved
## Post #580
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-23T19:45:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from kaliope ↑Wed Feb 23, 2022 8:55 am at Wed Feb 23, 2022 8:55 am
>
> Does anybody have an ebx to txt (or xml) converter for the BF2042 ebx files?

> Reply from kaliopeThu Feb 24, 2022 1:49 am at Thu Feb 24, 2022 1:49 am
>
> ...Do you have any idea how to transform the BF2042 ebx files into something reabable like txt or xml counterparts? My python script from BFV doesn't work (as expected) and I don't know if there is another solution out there.
If there where a solution, it would have been mentioned already, BF2042 has a completely different/new EBX format it seems, i don't know much about it, same as Anthem the EBXs can not be de-serialized either with current or old scripts, no clue when or who if ever will make support for the format.
With that being said, if anyone that would consider support after all would be on below GitHub by Nicknine user who happens to be in this forum as well, you could make a issue and post there, even a sample if you want, your choice:
[https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)
## Post #581
- Username: kaliope
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 01, 2019 5:45 pm
- Post datetime: 2022-02-23T20:41:04+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Thank you for taking the time to explain
## Post #582
- Username: DANNYonPC
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 24, 2022 6:09 am
- Post datetime: 2022-02-23T22:33:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Dimka51Rus ↑Mon Feb 21, 2022 8:49 am at Mon Feb 21, 2022 8:49 am
>
> 
BF2042

Ooooh, nice!
## Post #583
- Username: kayhotic
- Rank: n00b
- Number of posts: 16
- Joined date: Sat May 16, 2020 12:50 pm
- Post datetime: 2022-02-24T14:58:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Dimka51Rus ↑Mon Feb 21, 2022 8:49 am at Mon Feb 21, 2022 8:49 am
>
> 
BF2042

Damn dude, good work!
## Post #584
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2022-02-24T18:05:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from kayhotic ↑Thu Feb 24, 2022 10:58 pm at Thu Feb 24, 2022 10:58 pm
>
> 
Don't ask for assets please.
## Post #585
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-25T14:18:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Working on terrains.
Frostbite terrains use different level of detail for each square.
You can see here how it looks. Each of these squares (from biggest to smallest) is 128x128 height map.
## Post #586
- Username: kloruklass
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Jan 27, 2021 4:30 am
- Post datetime: 2022-03-13T11:25:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I have extracted the EBX, RES, and CHUNKS from Battlefield 2042. Is there a way to convert these EBX into audio?
I used to use the "WaveToAsset" Frostbite Script by locating the folder paths, but it asks for the GuidTable which is missing.
Both the GuidTable and ResTable are generated by the "Dumper" script, but the "2042 Tool" doesn't.

Can someone help?
## Post #587
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-03-13T23:29:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from kloruklass ↑Sun Mar 13, 2022 7:25 pm at Sun Mar 13, 2022 7:25 pm
>
> ...Can someone help?
It is a new format, why is no one reading past messages and find the answers already.
Nicknine has NOT added support for the new format that BF2042 has, i doubt he will do that, why don't you go on GitHub, make an issue and post samples, and ask for support?
[https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)
## Post #588
- Username: b0lt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 25, 2022 11:34 am
- Post datetime: 2022-03-25T10:04:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Feb 16, 2022 5:26 pm at Wed Feb 16, 2022 5:26 pm
>
> 

Hi there, how do I use the fb_maps_run.exe to convert maps? Do I open an EBX with the exe file?
## Post #589
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-03-25T11:45:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from b0lt ↑Fri Mar 25, 2022 6:04 pm at Fri Mar 25, 2022 6:04 pm
>
> 
Hi there, how do I use the fb_maps_run.exe to convert maps? Do I open an EBX with the exe file?
you need to perform all 4 steps, as described in the post you quoted.
## Post #590
- Username: toyowe3569
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 27, 2022 6:14 pm
- Post datetime: 2022-03-27T10:24:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Please tell  which tool extracts models and textures from the BF2042?
## Post #591
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2022-03-27T10:56:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from toyowe3569 ↑Sun Mar 27, 2022 6:24 pm at Sun Mar 27, 2022 6:24 pm
>
> 
Please tell  which tool extracts models and textures from the BF2042?
[viewtopic.php?f=16&t=17114&start=510](https://forum.xentax.com/viewtopic.php?f=16&t=17114&start=510) - extracts models

[viewtopic.php?f=16&p=182107#p182107](https://forum.xentax.com/viewtopic.php?f=16&p=182107#p182107) - Frostbite Texture Tools
## Post #592
- Username: b0lt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 25, 2022 11:34 am
- Post datetime: 2022-03-27T11:40:44+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Fri Mar 25, 2022 7:45 pm at Fri Mar 25, 2022 7:45 pm
>
> 
b0lt wrote: ↑Fri Mar 25, 2022 6:04 pm
Hi there, how do I use the fb_maps_run.exe to convert maps? Do I open an EBX with the exe file?

you need to perform all 4 steps, as described in the post you quoted.

I understand this, but am confused by the instructions of step 4. Are you able to clarify what I do? Am I opening the EBX files by dragging them on top of the fb_maps_run.exe file? Do I do something else?
(Also thank you so much for creating this tool, really appreciate you taking the time to make it and being generous enough to make it publicly available.)
## Post #593
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-03-27T11:42:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from b0lt ↑Sun Mar 27, 2022 7:40 pm at Sun Mar 27, 2022 7:40 pm
>
> 
dragging them on top of the fb_maps_run.exe file?
yes
## Post #594
- Username: b0lt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 25, 2022 11:34 am
- Post datetime: 2022-03-27T11:46:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sun Mar 27, 2022 7:42 pm at Sun Mar 27, 2022 7:42 pm
>
> 
b0lt wrote: ↑Sun Mar 27, 2022 7:40 pm
dragging them on top of the fb_maps_run.exe file?

yes

Alright, when I do that a command prompt window opens for a millisecond then closes, is this meant to be happening? If so, where can I find the outputted file?
## Post #595
- Username: eblansson
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 18, 2021 2:20 am
- Post datetime: 2022-04-06T16:50:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hey, thank you so much for your Frostbite tools! 
Although I have a bit of a problem with The Run, no matter which car mesh I'm trying to convert the app throws an "Unable to read beyond the end of the stream" exception.
Could it be that I've skipped some important step?

1. Dumped the game files using frostbite2 dumper.py script by NicknineTheEagle
2. Merged the root/bundles/chunks folder into root/chunks
3. Renamed all of the chunks in the folder using the mentioned in the thread ReNamer with regex rule
4. Found a .MeshSet and .ebx I need in /ebx and /res/_c4/blueprint/ folders

But it still throws the exception. I've also tried just renaming my .ebx to veniceantske01.ebx and converting a different car mesh alltogether but to no avail.
Maybe I'm using wrong .ebx-es or my dump is bad? I feel dumb
[screen.png](https://xentaxbackup.github.io/file/22063_screen.png)
## Post #596
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-04-07T01:09:47+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from eblansson ↑Thu Apr 07, 2022 12:50 am at Thu Apr 07, 2022 12:50 am
>
> ...Could it be that I've skipped some important step?...
...Maybe I'm using wrong .ebx-es...
Your steps are fine, except your using wrong EBX, every Frostbite game tool that daemon1 (ID-Daemon) made tools for, requires a skeleton
EBX, not just a random or the companion EBX each .MeshSet has, like in your screenshot, ANY skeleton that a character/humanoid has or even the Porsche vehicle skeleton will do, and you perform same cmd in your screenshot by replacing it with that skeleton, any from this location usually ending in *_skel.ebx or *_skeleton.ebx will do.

```
\_c4\ant\assets\...
```


> Reply from eblansson ↑Thu Apr 07, 2022 12:50 am at Thu Apr 07, 2022 12:50 am
>
> ...I've also tried just renaming my .ebx to veniceantske01.ebx...
You only need to performe that rename if you do not want to use the cmd in your screenshot where you add a specific skeleton, and want to have default name of the skeleton which happens to be from Battlefield 3 game and have it next to the tool, it's how the tool was built with that default skeleton name.

And more importantly, do NOT move the assets form their default file/folder structure, as you did at root of the dump, you'll get other errors, only skeleton needs to be next to the tool, and you move them around where the required .MeshSet is you need to convert (or you run in batch if you want), and that's it.
You always convert the assets where they are as the tool needs to load other data from the structure.
## Post #597
- Username: eblansson
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 18, 2021 2:20 am
- Post datetime: 2022-04-08T15:30:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Thu Apr 07, 2022 9:09 am at Thu Apr 07, 2022 9:09 am
>
> 
Your steps are fine, except...
Thank you very much for your help! Everything works like a charm now!
## Post #598
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-04-25T14:24:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Here are 2 more tools for NFS "the Run" I forgot to post.
These are for special DLC cars from XBOX and PS3.


[nfsrun_consoles.rar](https://xentaxbackup.github.io/file/22147_nfsrun_consoles.rar)
## Post #599
- Username: seele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 04, 2019 5:36 am
- Post datetime: 2022-04-25T17:58:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I kinda forgot to post this but, the tool has some interesting side effect. Extracted models have sharps all over the place


those seem to be weak, but the essential ones are defined, Guki's ripped models don't have this issue at all (instead sharps edges are unwelded, which is a two click fix)
so i believe it has to do with the tool itself

They are noticeable from certain angles, which is uhhh



This is totally fixable but takes quite some time
## Post #600
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-04-25T18:09:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from seele ↑Tue Apr 26, 2022 1:58 am at Tue Apr 26, 2022 1:58 am
>
> ...the tool has some interesting side effect...
The tools are fine, you just forgot to delete the shadow meshes, that's all.
Those that have no material names added after the digits you can safely delete them.
## Post #601
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-04-25T18:11:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from seele ↑Tue Apr 26, 2022 1:58 am at Tue Apr 26, 2022 1:58 am
>
> 
I kinda forgot to post this but, the tool has some interesting side effect. Extracted models have sharps all over the place
i have no idea what are you talking about.
the tool has no issues and this was confirmed by Guki.
## Post #602
- Username: seele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 04, 2019 5:36 am
- Post datetime: 2022-04-25T18:33:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Tue Apr 26, 2022 2:09 am at Tue Apr 26, 2022 2:09 am
>
> 
seele wrote: ↑Tue Apr 26, 2022 1:58 am...the tool has some interesting side effect...
The tools are fine, you just forgot to delete the shadow meshes, that's all.
Those that have no material names added after the digits you can safely delete them.
Can you elaborate about shadow meshes?
## Post #603
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-04-25T22:59:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from seele ↑Tue Apr 26, 2022 2:33 am at Tue Apr 26, 2022 2:33 am
>
> ...Can you elaborate about shadow meshes?
What game are you working on? You should have specified that initially.
And the exact internal car name that has those issues you mentioned.
## Post #604
- Username: seele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 04, 2019 5:36 am
- Post datetime: 2022-04-26T01:05:51+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Tue Apr 26, 2022 6:59 am at Tue Apr 26, 2022 6:59 am
>
> 
seele wrote: ↑Tue Apr 26, 2022 2:33 am...Can you elaborate about shadow meshes?
What game are you working on? You should have specified that initially.
And the exact internal car name that has those issues you mentioned.

Need for speed The Run, both PC and Xenon.
Cars and Characters. like pretty much anything. hence I didn't bothered specifying names.

It imports it just like that into blender. There's no other options in the side tab, Maybe it's the plugin?

I legit don't know what else to say.
## Post #605
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-04-26T18:56:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from seele ↑Tue Apr 26, 2022 9:05 am at Tue Apr 26, 2022 9:05 am
>
> ...Cars and Characters...
Everything exports fine, the tool has no issues, also now that i know it is The Run, if i remember correctly it has no shadow meshes.

> Reply from seele ↑Tue Apr 26, 2022 9:05 am at Tue Apr 26, 2022 9:05 am
>
> ...Maybe it's the plugin?...
Sounds like it while in most cases its a user error.

> Reply from seele ↑Tue Apr 26, 2022 9:05 am at Tue Apr 26, 2022 9:05 am
>
> I legit don't know what else to say.
Every detail/step always counts, you could have specified the script your using as well.
Have you tried the following: [viewtopic.php?p=183803#p183803](https://forum.xentax.com/viewtopic.php?p=183803#p183803)

Also, if you encounter un-welded vertices be it cars or characters, it is NOT a tool issue, its how the meshes are. Something you have to manually weld them together, just careful what/how you do it, it can screw up the normals.
## Post #606
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-04-26T19:57:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Wed Apr 27, 2022 2:56 am at Wed Apr 27, 2022 2:56 am
>
> 
Sounds like it while in most cases its a user error.
he's probably using some wrong plugin or wrong settings. I wont be surprised if he's trying to load SMD files (which as we know dont have original geometry structure, and are rebuilding the model randomly with the plugin)
## Post #607
- Username: seele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 04, 2019 5:36 am
- Post datetime: 2022-04-27T00:45:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Wed Apr 27, 2022 2:56 am at Wed Apr 27, 2022 2:56 am
>
> 
seele wrote: ↑Tue Apr 26, 2022 9:05 am...Cars and Characters...
Everything exports fine, the tool has no issues, also now that i know it is The Run, if i remember correctly it has no shadow meshes.
seele wrote: ↑Tue Apr 26, 2022 9:05 am...Maybe it's the plugin?...
Sounds like it while in most cases its a user error.
seele wrote: ↑Tue Apr 26, 2022 9:05 amI legit don't know what else to say.
Every detail/step always counts, you could have specified the script your using as well.
Have you tried the following: viewtopic.php?p=183803#p183803

Also, if you encounter un-welded vertices be it cars or characters, it is NOT a tool issue, its how the meshes are. Something you have to manually weld them together, just careful what/how you do it, it can screw up the normals.
So, it was indeed the wrong plugin


Here just automatically welded everything keeping sharps, yet i wish i knew about this thing before; it would had saved me lots of time.
I guess i'll use this for the traffic cars from now on.
Still, thanks for the info
## Post #608
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2022-04-27T15:44:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Noticed there isn't any smd file for face fixing BFV Misaki in the archives in this thread. She was a dlc character, added later. Anyone got that specific one?
## Post #609
- Username: benbit
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 24, 2022 1:32 am
- Post datetime: 2022-05-23T18:45:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Does anybody know how/if you can convert 2042 .SvgImageData files into I assume normal svgs?
## Post #610
- Username: eblansson
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 18, 2021 2:20 am
- Post datetime: 2022-05-26T03:02:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

So I tried getting meshes from PS3 version of NFSTR, specifically the exclusive Italian Pack DLC cars, but also vanilla cars just to see if the dump is correct.
I dumped the entire thing completely with DLCs and renamed the chunks, but the Fb_nfsrun_ps3.exe tool is trying to find some chunks that don't actually exist in none of the /chunks folders. Basically just "Chunk not found" error.
I'm kind of lost here because I'm doing the same steps as I did for PC and it worked there. 
Does PS3 need to have its chunks named differently or is the dumper not naming chunks properly?
Or most likely I'm just doing something incorrectly.

Edit: ebxtoasset.py locates chunks with textures without any issue, including DLC car textures and vinyls. Could it be a bug in the Fb_nfsrun_ps3 tool?
## Post #611
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-05-26T20:26:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from eblansson ↑Thu May 26, 2022 11:02 am at Thu May 26, 2022 11:02 am
>
> Does PS3 need to have its chunks named differently or is the dumper not naming chunks properly?
The actual DLCs are NOT supported for extraction by the python script developer, for neither X360 or PS3 that's why you get the chunk not found error because it can NOT gain access to something that is not dumped. You can request as well support for it here: [https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)
## Post #612
- Username: eblansson
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 18, 2021 2:20 am
- Post datetime: 2022-05-26T21:18:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Fri May 27, 2022 4:26 am at Fri May 27, 2022 4:26 am
>
> 
The DLCs are NOT supported for extraction by the python script developer, for neither X360 or PS3...
Oh that makes sense, thanks!
But if I understood correctly, the textures are in .chunks too, right? I am actually able to extract DLC textures (car textures and vinyls) with that python "ebxtoasset" script which is hella weird. 
Does that mean that something is indeed being dumped from DLCs?
[ok.png](https://xentaxbackup.github.io/file/22261_ok.png)
## Post #613
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-05-27T18:05:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from eblansson ↑Fri May 27, 2022 5:18 am at Fri May 27, 2022 5:18 am
>
> ...Does that mean that something is indeed being dumped from DLCs?
In a way, yes, the Update/Patch has the updated resources of the DLC, i cant fully confirm what exactly is going on since there was never a proper way to dump ALL assets, BUT, the DLC does have the remaining kits of the DLC of those 8 mentioned cars, so you can consider those updates of the DLC base assets, i suppose. Until full support will surface, i can only speculate at this point as i was confused as well.
## Post #614
- Username: M200is
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 17, 2022 9:52 pm
- Post datetime: 2022-06-17T14:36:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I extracted the ebx file from BF2042, but I don't know how to import the texture file from the .ebx file. I tried Frostbite-Scripts, but I don't know how to use them because I'm not good at English. Is there anyone who can tell me in detail?
## Post #615
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-06-17T22:59:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from M200is ↑Fri Jun 17, 2022 10:36 pm at Fri Jun 17, 2022 10:36 pm
>
> ...I extracted the ebx file from BF2042, but I don't know how to import the texture file from the .ebx file...
You cant that way, you need the WHOLE game dumped in order to convert the textures, not just the EBXs.

> Reply from M200is ↑Fri Jun 17, 2022 10:36 pm at Fri Jun 17, 2022 10:36 pm
>
> ...I tried Frostbite-Scripts...
Those scripts do NOT work with this game, you need the tool posted by daemon and the texture tool posted by Sharppy

You'll find what you need few pages back, just look carefully.
## Post #616
- Username: M200is
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 17, 2022 9:52 pm
- Post datetime: 2022-06-19T10:59:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

System.UnauthorizedAccessException error while trying to run BF2042_Mesh What's the reason?
The read-only status of the folder is checked as -.
## Post #617
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-19T12:03:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from M200is ↑Sun Jun 19, 2022 6:59 pm at Sun Jun 19, 2022 6:59 pm
>
> 
System.UnauthorizedAccessException error while trying to run BF2042_Mesh What's the reason?
The read-only status of the folder is checked as -.
reason must be described in error message, read the full message
## Post #618
- Username: M200is
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 17, 2022 9:52 pm
- Post datetime: 2022-06-19T12:42:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sun Jun 19, 2022 8:03 pm at Sun Jun 19, 2022 8:03 pm
>
> 
M200is wrote: ↑Sun Jun 19, 2022 6:59 pm
System.UnauthorizedAccessException error while trying to run BF2042_Mesh What's the reason?
The read-only status of the folder is checked as -.

reason must be described in error message, read the full message

It says I can't read the folder. So I tried to turn off read-only, and it was still marked with a "-" and nothing changed.
## Post #619
- Username: KlausSh
- Rank: beginner
- Number of posts: 25
- Joined date: Fri May 06, 2022 12:08 am
- Post datetime: 2022-07-05T15:48:24+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

if anyone found a way to dump audio files for anthem , i extracted the ebx , res and chunks but after that idk what to do.
## Post #620
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-07-05T20:59:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from KlausSh ↑Tue Jul 05, 2022 11:48 pm at Tue Jul 05, 2022 11:48 pm
>
> 
if anyone found a way to dump audio files for anthem , i extracted the ebx , res and chunks but after that idk what to do.
Creating multiple posts will NOT solve anything!
[viewtopic.php?p=185584#p185584](https://forum.xentax.com/viewtopic.php?p=185584#p185584)
## Post #621
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2022-07-06T16:38:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Fri Feb 25, 2022 10:18 pm at Fri Feb 25, 2022 10:18 pm
>
> 
Working on terrains.

Hello! Is there any chance that you continue work with this terrain tool and release it for Anthem?
## Post #622
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-07T10:46:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Naznarok ↑Thu Jul 07, 2022 12:38 am at Thu Jul 07, 2022 12:38 am
>
> 
daemon1 wrote: ↑Fri Feb 25, 2022 10:18 pm
Working on terrains.


Hello! Is there any chance that you continue work with this terrain tool and release it for Anthem?
i planned it after star wars bf2
## Post #623
- Username: b0lt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 25, 2022 11:34 am
- Post datetime: 2022-07-14T06:58:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from b0lt ↑Sun Mar 27, 2022 7:46 pm at Sun Mar 27, 2022 7:46 pm
>
> 
daemon1 wrote: ↑Sun Mar 27, 2022 7:42 pm
b0lt wrote: ↑Sun Mar 27, 2022 7:40 pm
dragging them on top of the fb_maps_run.exe file?

yes


Alright, when I do that a command prompt window opens for a millisecond then closes, is this meant to be happening? If so, where can I find the outputted file?

Been trying to follow the instructions as religiously as I can, not sure where I'm going wrong. (Getting stuck when dragging ebx files to the fb_maps_run.exe, all that happens is a command prompt window appears for a millisecond and then nothing happens)

Would anyone have an idea of where I went wrong?
## Post #624
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-14T07:16:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from b0lt ↑Thu Jul 14, 2022 2:58 pm at Thu Jul 14, 2022 2:58 pm
>
> 
Would anyone have an idea of where I went wrong?
Can be anything.
To know exactly what happened, you need to open command window (or any other shell), and run the tool from there.
Or you can check application log from windows event logs.
## Post #625
- Username: b0lt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 25, 2022 11:34 am
- Post datetime: 2022-07-14T07:48:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Thu Jul 14, 2022 3:16 pm at Thu Jul 14, 2022 3:16 pm
>
> 
b0lt wrote: ↑Thu Jul 14, 2022 2:58 pm
Would anyone have an idea of where I went wrong?

Can be anything.
To know exactly what happened, you need to open command window (or any other shell), and run the tool from there.
Or you can check application log from windows event logs.
Here's what Command prompt outputted:
## Post #626
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-14T12:43:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from b0lt ↑Thu Jul 14, 2022 3:48 pm at Thu Jul 14, 2022 3:48 pm
>
> 
Here's what Command prompt outputted:
as you can see, you're running the tool from the folder where your map is. And so tool can't find the file created on previous step.
You can do many different things to fix it.
For example:
run the tool from the folder where the tool is
or
move needed files to where the map is
or
move all files to one folder, doesnt matter which folder it is, or create a new one
## Post #627
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2022-07-17T20:14:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Feb 09, 2022 1:20 am at Wed Feb 09, 2022 1:20 am
>
> 
Anthem dump/models tools

Hello! I noticed that toc_anthem tool not fully export Anthem resources. When i try to export textures, in logs there are a lot of messages about not found CHUNKs and the same situation when unpacking models using fb_anthem tool. Can you help?

[https://www.dropbox.com/s/fyukduje5hhgo ... t.zip?dl=0](https://www.dropbox.com/s/fyukduje5hhgocd/model_export.zip?dl=0)
[https://www.dropbox.com/s/ras058h0804e6 ... t.zip?dl=0](https://www.dropbox.com/s/ras058h0804e66u/texture_export.zip?dl=0)
## Post #628
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-19T10:32:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Naznarok ↑Mon Jul 18, 2022 4:14 am at Mon Jul 18, 2022 4:14 am
>
> 
daemon1 wrote: ↑Wed Feb 09, 2022 1:20 am
Anthem dump/models tools


Hello! I noticed that toc_anthem tool not fully export Anthem resources. When i try to export textures, in logs there are a lot of messages about not found CHUNKs and the same situation when unpacking models using fb_anthem tool. Can you help?

https://www.dropbox.com/s/fyukduje5hhgo ... t.zip?dl=0
https://www.dropbox.com/s/ras058h0804e6 ... t.zip?dl=0
I dont have the game, so i never really tested it.
## Post #629
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2022-07-19T10:40:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Tue Jul 19, 2022 6:32 pm at Tue Jul 19, 2022 6:32 pm
>
> 
I dont have the game, so i never really tested it.

i can share it with you via torrent if you need
## Post #630
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-21T20:16:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)


## Post #631
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-24T07:50:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Whole deathstar level loaded
## Post #632
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-31T06:09:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Anthem maps/terrains are also done.
## Post #633
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-31T10:42:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Map tool for SWBF2.

Most map objects properly placed, including those using havok and blueprints. Also basic terrain support.



1. Dump the game

You can use existing python script, but its slower and dumps almost every texture twice with different names, producing about 30 GB of useless files.

I recommend using attached toc_swbf2.exe - set desired parameters in ufbe.ini and run it.

Parameters are: 
- game path
- dump path
- asset type

Asset type can be "ebx", "res", "chunks" or "all". Anything else (or empty line) is considered as "all".

2. Edit the included FB_MAPS.INI file with paths to your dump.

The other 3 tools need this fb_maps.ini file with 2 parameters: paths to dumped bundles (ebx+res) and chunks.

3. Create database

Run fb_maps_swbf2_db.exe tool once, it will scan whole dump for meshsets and blueprints, so later maps can be converted fast, without the need to go into whole tree of assets. This will take a few minutes. After that, 2 files will be created: bp.db & meshnames.txt, which need to stay in the same folder with EXE for main tool to work.

4. Export maps

Use fb_maps_swbf2.exe (main map tool) to convert maps. Drop any EBX on it, use in command line with 1 parameter, or create a batch.

5. Terrain export

Main terrain data is in .TerrainStreamingTree files for each level. For some levels, these files are small, which means the actual data is in chunks. Sometimes data is in the file itself, in this case it may be big, about 50mb in size.

Drop .TerrainStreamingTree on fb_terrain_swbf2.exe or use command line.

It will export heightmap parts into "hmap" subfolder. As you can see on the pictures above, terrain in frostbite is saved in square parts of different size, organized in a tree-like structure. Some parts may be very detailed, while others not. Tool will only save highest detail level for each square and skip all lower LODs. 

So far this first version terrain tool only exports base (heightmap) layer from these files. But they contain much more data, such as terrain masks, normals, textures etc. I can add support for it later.
[swbf2maps.7z](https://xentaxbackup.github.io/file/22579_swbf2maps.7z)
## Post #634
- Username: seele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 04, 2019 5:36 am
- Post datetime: 2022-08-02T04:15:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

running toc_swbf2.exe gives me this
## Post #635
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-08-03T07:59:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from seele ↑Tue Aug 02, 2022 12:15 pm at Tue Aug 02, 2022 12:15 pm
>
> 
running toc_swbf2.exe gives me this
If you have old game version, use old script or ufbe
## Post #636
- Username: KlausSh
- Rank: beginner
- Number of posts: 25
- Joined date: Fri May 06, 2022 12:08 am
- Post datetime: 2022-08-03T18:12:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sun Jul 24, 2022 3:50 pm at Sun Jul 24, 2022 3:50 pm
>
> 
Whole deathstar level loaded

any plans to create a script that extract sound ? i do have frosty editor but it can only extract one by one file
## Post #637
- Username: Senkay201
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 09, 2022 6:07 pm
- Post datetime: 2022-08-09T20:56:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi,
i wanted to extract some Anthem Files and tried to use the Zipfile with the Toc_anthem files. When i drag the .toc file into the the Toc-anthem.exe i get a dump file with .chunks files.But i need .meshet files to work with right?
[](https://bilderupload.org/bild/2a5177665-anthemproblem)

And is the nfs_therun_maps.7z also for Anthem Maps?
## Post #638
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-08-10T09:10:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Anthem map tool is not released yet. It will also require a fix for both dump tool and mesh tool.
## Post #639
- Username: Senkay201
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 09, 2022 6:07 pm
- Post datetime: 2022-08-10T18:30:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi daemon1,

thanks for the quick reply. Ok i will wait for anthem and look at Battlefield 2042 and other games in that time.
## Post #640
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-08-13T14:26:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Map tool set for Anthem.

Most map objects properly placed, including blueprints. Also basic terrain support.





1. Dump the game

Use the new toc_anthem_v3.exe, it was updated since original anthem dump tool, because i found that some rare chunks were not dumped, and they are needed for maps. So if you have dumped anthem before, you need to redump it.

Set desired parameters in ufbe.ini
Parameters are: 
- game path
- dump path
- asset type
Notice now there must be no "data" or "patch" in the end of "game path".
Asset type can be "ebx", "res", "chunks" or "all". Anything else (or empty line) is considered as "all".

Then you need to run dump tool on all .TOC files from the game. You can do them one by one as there are not too many, or in a batch, but its important that you must first run it on all .TOC files from "patch" folder, then on all .TOC files from "data" folder.

Tool needs oo2core_8_win64.dll or oo2core_7_win64.dll, just rename it to oo2core_8_win64.dll

2. Edit the included FB_MAPS.INI file with paths to your dump.

The other 3 tools need this fb_maps.ini file with 2 parameters: paths to dumped bundles (ebx+res) and chunks.

3. Create database

Run fb_maps_anthem_db.exe tool once, it will scan whole dump for meshsets and blueprints, so later maps can be converted fast, without the need to go into whole tree of assets. This will take a few minutes. After that, 2 files will be created: bp.db & meshnames.txt, which need to stay in the same folder with EXE for main tool to work.

4. Export maps

Use fb_maps_anthem.exe (main map tool) to convert maps. Drop any EBX on it, use in command line with 1 parameter, or create a batch.

In addition to .ascii export with all baked meshes, it will create a text file with a list of all mesh instances and their 3x4 transform matrices. So if you like, you can make a script for your favourite editor or engine (3dmax, maya, blender, unity, unreal) and place all meshes as instances.

5. Terrain export

Same usage as swbf2 terrain:

Drop .TerrainStreamingTree on fb_terrain_anthem.exe or use command line.

It will export heightmap parts into "hmap" subfolder. As you can see on the pictures above, terrain in frostbite is saved in square parts of different size, organized in a tree-like structure. Some parts may be very detailed, while others not. Tool will only save highest detail level for each square and skip all lower LODs.

6. Mesh export tool

Fb_anthem.exe - this was also included to support the new way of dumping meshsets (no metadata in filename, its included inside file). It also saves exported .ascii/.smd files in the original directory tree. Skeletons will be expected in the tool folder, as before.
[anthem_maps.7z](https://xentaxbackup.github.io/file/22637_anthem_maps.7z)
## Post #641
- Username: cashgrany
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 16, 2018 1:26 am
- Post datetime: 2022-09-04T08:51:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hello everyone ; I really need help.
 I can't find how to open or convert the .ascii files obtained with fb_terrain_swbf2.exe .
 please help .
## Post #642
- Username: TheHarryAli
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 08, 2022 5:34 am
- Post datetime: 2022-09-09T12:45:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Tue Feb 01, 2022 1:41 am at Tue Feb 01, 2022 1:41 am
>
> 
NFS Heat.

The latest and most advanced game, with lots of cars and character combinations. All static models also supported.
Usage is almost same as 2042 tool, read it here - viewtopic.php?p=181685#p181685
Doesnt matter which oodle version the game uses, just take the one you have, and rename it to oo2core_8_win64.dl

Hi there everyone! I can't use this tool by Daemoon1. When i open the exe files the command prompt appears and closes without doing anything. Do i need any extra softs or tools to use this? I have NFS Heat downloaded from Origin store.
## Post #643
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-09-09T21:14:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from cashgrany ↑Sun Sep 04, 2022 4:51 pm at Sun Sep 04, 2022 4:51 pm
>
> ...I can't find how to open or convert the .ascii files obtained with fb_terrain_swbf2.exe...
Noesis or Blender can open those converted ASCIIs, as long as you provide to those tools the correct python script to load them, for Blender you can use: [https://github.com/johnzero7/XNALaraMesh](https://github.com/johnzero7/XNALaraMesh)

Also for Blender you can try: [https://github.com/REDxEYE/blender_xna](https://github.com/REDxEYE/blender_xna)
For Noesis: [https://github.com/REDxEYE/noe_xna](https://github.com/REDxEYE/noe_xna)
Both require the following library though to function properly: [https://github.com/REDxEYE/py_xna_lib](https://github.com/REDxEYE/py_xna_lib)

Why is everyone so lazy to use the search function, why oh why 

> Reply from TheHarryAli ↑Fri Sep 09, 2022 8:45 pm at Fri Sep 09, 2022 8:45 pm
>
> ...I can't use this tool by Daemoon1. When i open the exe files the command prompt appears and closes without doing anything...
It is a cmd tool, the developer described already how to use it, in any of his threads/posts he explains how to use his tools, you write his commands in to a text file, change extension from *.TXT to *.BAT then you run that BAT like you would any other executable.

The following is one scenario on how to use it, except you follow the commands given to that respective tool your working with by the developer.
[viewtopic.php?p=186121#p186121](https://forum.xentax.com/viewtopic.php?p=186121#p186121)
## Post #644
- Username: cashgrany
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 16, 2018 1:26 am
- Post datetime: 2022-09-09T22:15:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I would never thank you enough "mono24"  because it's wonderful I can import .ascii; thank you very much again. 
By I still have a little problem when I try to import several files at the same time I have an error? 
So I have to import 1 by 1; would you have an idea?


P.S: I swear I used the search function; I typed ascii but nothing conclusive came out.
## Post #645
- Username: TheHarryAli
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 08, 2022 5:34 am
- Post datetime: 2022-09-10T11:38:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Sep 10, 2022 5:14 am at Sat Sep 10, 2022 5:14 am
>
> 
It is a cmd tool, the developer described already how to use it, in any of his threads/posts he explains how to use his tools, you write his commands in to a text file, change extension from *.TXT to *.BAT then you run that BAT like you would any other executable.

Sorry for being that dumb. But there's only one txt file there and it's types.txt. I tried using UFBE tool, but it's not for NFS Heat and it's parts didn't help for NFS Heat tool. I read this thread from scratch and still don't get what to do. Because everybody else seems doing perfect with just that .7z file. Any videotutorial maybe?
## Post #646
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-09-10T14:39:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from cashgrany ↑Sat Sep 10, 2022 6:15 am at Sat Sep 10, 2022 6:15 am
>
> ...So I have to import 1 by 1; would you have an idea?...
Blender itself has MANY limitations, its a tough pill to swallow as a 3D editor, in my personal opinion, but as far as i know it can not do multiple selections and load them one after another, it requires python scripts for batch import and that's only for standard formats like DAE/FBX/OBJ/etc, for this custom ASCII is limited by the script itself, if who ever wrote the script didn't add support for batch import then it means it will never work that way.

Noesis does have a merger script that can auto load entire folder of any given format i believe that it supports to load. It must be somewere here in the forum, but for large scale imports i would recommend 64-bit Noesis, as 32-bit will crash instantly.

> Reply from TheHarryAli ↑Sat Sep 10, 2022 7:38 pm at Sat Sep 10, 2022 7:38 pm
>
> ...But there's only one txt file there and it's types.txt. I tried using UFBE tool, but it's not for NFS Heat and it's parts didn't help for NFS Heat tool...
Assuming you dumped the full game using the correct tool: [viewtopic.php?p=181813#p181813](https://forum.xentax.com/viewtopic.php?p=181813#p181813)
Yes the instructions are same as the Battlefield 2042 game, but that tool can NOT be used for Heat, just its instructions, hence the dev linking in beginning that link.
I said in a text file, NOT in the types.txt file, in a NEW text file, you write what ever the command is given by the developer for what ever game your trying to work on.
Once you have the game dumped you write in a NEW text file what the dev described:

```
Fb_NFS_Heat.exe <meshset>
```

or

```
Fb_NFS_Heat.exe <meshset> <skeleton>
```

obviously you replace <meshset> with the asset your trying to convert from the game, and <skeleton> with any EBX skeleton that is required by that asset, what ever it may be or your looking for, etc.
## Post #647
- Username: TheHarryAli
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 08, 2022 5:34 am
- Post datetime: 2022-09-10T16:06:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Sep 10, 2022 10:39 pm at Sat Sep 10, 2022 10:39 pm
>
> 
I said in a text file, NOT in the types.txt file, in a NEW text file, you write what ever the command is given by the developer for what ever game your trying to work on.

Now i understand the second part, but still i can't dump the game. In order to dump i should run toc_heat.exe right? But as i said, command prompt appears and doesn't do anything at all.
## Post #648
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-09-10T18:50:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from TheHarryAli ↑Sun Sep 11, 2022 12:06 am at Sun Sep 11, 2022 12:06 am
>
> ...but still i can't dump the game. In order to dump i should run toc_heat.exe right?...
It is described here: [viewtopic.php?p=181685#p181685](https://forum.xentax.com/viewtopic.php?p=181685#p181685)
Except you use the Heat archive you got from here: [viewtopic.php?p=181813#p181813](https://forum.xentax.com/viewtopic.php?p=181813#p181813)
It is the archive attached at the bottom of that post called: nfs_heat.7z
Then you follow what is described in first link on how to dump it.

Just because their different games, the procedure is the same, that's it, just make sure your using the right tool for the right game.
## Post #649
- Username: TheHarryAli
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 08, 2022 5:34 am
- Post datetime: 2022-09-10T21:01:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sun Sep 11, 2022 2:50 am at Sun Sep 11, 2022 2:50 am
>
> 
Just because their different games, the procedure is the same, that's it, just make sure your using the right tool for the right game.

Wow, i have been being stupid this whole time. I thought i should run the toc_heat.exe file. But i should've drag .toc file from game folder to toc_heat.exe. Now i get it. Thank you so much mono24 ! 

Now i have successfully dumped the game. But can you give me any example what to write instead of <meshset> to run Fb_NFS_Heat.exe ?
## Post #650
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-09-10T21:52:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from TheHarryAli ↑Sun Sep 11, 2022 5:01 am at Sun Sep 11, 2022 5:01 am
>
> ...But can you give me any example what to write instead of <meshset> to run Fb_NFS_Heat.exe ?...
That in itself is the example provided by the dev, except you replace with what ever you want to convert, it is impossible for me to guess with out more context, how am i supposed to know what your trying to do exactly to help better?

If i where to convert a vehicle on my end, i would perform the following:
this

```
Fb_NFS_Heat.exe <meshset> <skeleton>
```

means

```
Fb_NFS_Heat.exe car_bmw_m3e46_2003_mesh.MeshSet bmw_s1000rr_2019_skel.ebx
```


Remember, *.MeshSet can be anything while the skeleton MUST be accurate for the required character/weighted asset, and for other static/vehicles it can be ANY *.EBX skeleton you choose, doesn't matter, some rare vehicles have their own skeleton while the rest ANY skeleton can be used.

have fun
## Post #651
- Username: Liadesign
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 16, 2022 2:14 pm
- Post datetime: 2022-09-16T06:50:20+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Guys help to pull the terrain out of NFS Heat. Willing to pay for work.
## Post #652
- Username: Vertexflowrider
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 30, 2022 7:20 pm
- Post datetime: 2022-10-03T11:53:23+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Excuse me, but how would one go, if they decided to extract a piece of nfs 2016 maps?
I have downloaded some of the tools, but I still don't understand how to use them.

Do I have to use the  toc_heat.exe with oo2core dll? I tried it with no luck, the program just exits.
I drag the genesis01.toc on the program, am I on the right path?

I would like to convert a large part of the map, so I could do some rendering stress tests with some advanced and demanding shader techniques. I would like to benchmark the assets, so I can get a rough understanding on how to optimize large scenes in a real-time rendering engine with many lights(quite a challenging task on its own).

If somebody has the whole map exported with UV's and maps then I would be happy to download that, but I'd rather try the tool myself, because I guess the extracted data can be quite huge in terms of size...

Thanks & have a nice day!
## Post #653
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-10-03T15:47:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Vertexflowrider ↑Mon Oct 03, 2022 7:53 pm at Mon Oct 03, 2022 7:53 pm
>
> 
Excuse me, but how would one go, if they decided to extract a piece of nfs 2016 maps?
as i remember, i only did nfs Run, swbf2 and anthem
not 2016
## Post #654
- Username: Extile
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 08, 2022 10:51 pm
- Post datetime: 2022-10-10T11:42:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi!

Is it possible to get the mesh rotation data separately for the meshes contained in the asc files?
## Post #655
- Username: Extile
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 08, 2022 10:51 pm
- Post datetime: 2022-10-12T16:32:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

There seem to be a few alignment issues or parts missing
[Untitled.jpg](https://xentaxbackup.github.io/file/22902_Untitled.jpg)
## Post #656
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-11-26T15:52:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

For those of you curious as to how to dump/convert assets form the new Need for Speed Unbound game.
It shares same engine build as the BD2042 game, same model format, except the cars have the normals same format as the Heat game, so you'll only get the model with broken normals. other than that it seems to be converting fine.

So use the following: [viewtopic.php?p=181685#p181685](https://forum.xentax.com/viewtopic.php?p=181685#p181685)

have fun
## Post #657
- Username: davidperks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 29, 2022 6:00 pm
- Post datetime: 2022-11-30T11:12:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Inspired me to try my hand at deathstar. Very pleased with your tools. Thank you!
## Post #658
- Username: davidperks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 29, 2022 6:00 pm
- Post datetime: 2022-11-30T11:14:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Extile ↑Mon Oct 10, 2022 7:42 pm at Mon Oct 10, 2022 7:42 pm
>
> 
Hi!

Is it possible to get the mesh rotation data separately for the meshes contained in the asc files?

Exactly what I was thinking - need 4x4 matrix for each asset. Translation helps but too much work to manually reorientate all the parts!
## Post #659
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-11-30T20:03:43+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from lohan06 ↑Thu Dec 01, 2022 3:59 am at Thu Dec 01, 2022 3:59 am
>
> 
hey! i dumped the new nfs unbound car models, but i cant extract the textures, they  are all kinda messed, you can help me to rip those textures?
[viewtopic.php?p=182107#p182107](https://forum.xentax.com/viewtopic.php?p=182107#p182107)

PS: There is no need for this type of PM when it could have been posted here  if others have same issue they can see the post and guide themselves
## Post #660
- Username: lohan06
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 01, 2022 3:45 am
- Post datetime: 2022-11-30T20:31:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Sorry! im new to the forum. BTW i tried this before and when i open the NFSHeatTexTool, nothing happens
## Post #661
- Username: lohan06
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 01, 2022 3:45 am
- Post datetime: 2022-11-30T20:34:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

and when i drag any .ebx or .texture my cmd crashes and shows this [https://ibb.co/dLp5fVC](https://ibb.co/dLp5fVC)
## Post #662
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-12-02T01:13:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from lohan06 ↑Thu Dec 01, 2022 4:31 am at Thu Dec 01, 2022 4:31 am
>
> 
Sorry! im new to the forum. BTW i tried this before and when i open the NFSHeatTexTool, nothing happens
It is a cmd prompt tool where you give a proper syntax for it to process what ever is you need, most questions are already answered, this is an example of what you want to achieve using the BF2042 texture tool for Unbound.
if you run the tool in cmd prompt with out any parameter it will even tell how to use it.
[viewtopic.php?p=182112#p182112](https://forum.xentax.com/viewtopic.php?p=182112#p182112)
## Post #663
- Username: eSEke200%
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 02, 2022 6:59 am
- Post datetime: 2022-12-02T23:44:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 9:47 pm at Wed Jan 26, 2022 9:47 pm
>
> 
Battlefield 2042 tool.

Dumping the game

1. Change paths in the .INI to your folders. Set parameter on the 3rd line to only dump "ebx" "res" or "chunks". If no parameter (empty line), it will dump them all.
2. Place oo2core_8_win64.dll from the game to the same folder
3. Drag any .TOC file onto toc2042.exe, and it will extract everything that was listed in that file

Converting models

bf2042_mesh.exe <meshset>
or 
bf2042_mesh.exe <meshset> <skeleton>

Tool will find the needed chunk automatically in the same folder, "chunks" subfolder, or folder structure created by dumper.
If no skeleton name provided, tool will ask for default _soldierskeleton.ebx skeleton (which you can find in globals.toc)

Hey uh, pardon my stupidity, but where should I put the files? in BF2042's folder? what and where should change the paths? And like, can you give me a more detailed guide on doing this? cause I'm pretty much a beginner now heh heh
## Post #664
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-12-03T14:07:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from eSEke200% ↑Sat Dec 03, 2022 7:44 am at Sat Dec 03, 2022 7:44 am
>
> Hey uh, pardon my stupidity, but where should I put the files? in BF2042's folder? what and where should change the paths? And like, can you give me a more detailed guide on doing this? cause I'm pretty much a beginner now heh heh
It does not matter where you keep the files needed for that process, it is a cmd prompt tool and you can run that how ever you want, and no matter if your new here or not, looking in the thread few pages ahead there are so many examples on how to use the tool, so much has been explained already in so many ways, all Frostbite tools here work the same regardless of the game name.

> Reply from Gobyl ↑Sat Dec 03, 2022 4:15 pm at Sat Dec 03, 2022 4:15 pm
>
> 
Hey sorry tp interrupt, I have been trying to rip the texture from bf2042 from by dragging the texture files the tools but only giving "The directory is invalid" error. I am currently trying to do the solution you gave on the forum post but I am still unfortunately confused. Is it possible for you to elaborate on how to do it maybe more casually?
Honestly there's not much to say except what you se here, literally: [viewtopic.php?p=182112#p182112](https://forum.xentax.com/viewtopic.php?p=182112#p182112)
if you use the bundle path folder it means it will convert entire game dump, unless you don't need that whole game converted, you add the path of the folder of the model your trying to convert, that's all there is to it.
The required texture tools you place them at root of your game dump, you wont get any errors.
## Post #665
- Username: Gobyl
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 29, 2022 1:01 pm
- Post datetime: 2022-12-03T15:13:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Dec 03, 2022 10:07 pm at Sat Dec 03, 2022 10:07 pm
>
> 
Honestly there's not much to say except what you se here, literally: viewtopic.php?p=182112#p182112
if you use the bundle path folder it means it will convert entire game dump, unless you don't need that whole game converted, you add the path of the folder of the model your trying to convert, that's all there is to it.
The required texture tools you place them at root of your game dump, you wont get any errors.

Thanks for the help, I have solve it. It turns out you need to drag the whole texture folder you want to compile and not individual files.

Also does PBR texture can be extracted from bf2042?
## Post #666
- Username: Heymac
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 09, 2018 7:14 am
- Post datetime: 2022-12-10T20:07:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

First of all, thank you to daemon1for providing these great tools!

I've been trying to use the BF2042 tools to dump a few meshes from the game. However in the bundles folders created from the various .toc files, it seems like there are whole folders missing for characters and parts missing from the character files that are there. For example I can find some (but not all) .Meshset files for about six different specialists, but nothing for the other six. It's similar for the vehicles and for the weapons. Am I not understanding something or is this just a limitation of the software? I've seen someone post screenshots of all the vehicle models a few pages back, and they seemed to be using the same tools. Thanks.
## Post #667
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-12-10T20:11:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Heymac ↑Sun Dec 11, 2022 4:07 am at Sun Dec 11, 2022 4:07 am
>
> ...Am I not understanding something or is this just a limitation of the software?...
In order to gain access to ALL assets you might think your looking for, you must dump entire game, as some assets are scattered, some in levels, etc.
Somewhere somehow you messed up your extraction process, pay close attention to every step. Start from scratch if unsure.
## Post #668
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2022-12-21T21:39:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Jan 26, 2022 9:47 pm at Wed Jan 26, 2022 9:47 pm
>
> 
Battlefield 2042 tool.

Dumping the game

1. Change paths in the .INI to your folders. Set parameter on the 3rd line to only dump "ebx" "res" or "chunks". If no parameter (empty line), it will dump them all.
2. Place oo2core_8_win64.dll from the game to the same folder
3. Drag any .TOC file onto toc2042.exe, and it will extract everything that was listed in that file

Converting models

bf2042_mesh.exe <meshset>
or 
bf2042_mesh.exe <meshset> <skeleton>

Tool will find the needed chunk automatically in the same folder, "chunks" subfolder, or folder structure created by dumper.
If no skeleton name provided, tool will ask for default _soldierskeleton.ebx skeleton (which you can find in globals.toc)

Guys, what tool using to import (sh*t) format of models? I tried with XnaLara importer for 3ds Max but smooth looking weird and I didn't see LODs. FBX format will be much better and I hope for FrostyEditor - this is much easier, better and quickly tool - will support soon NFS Unbound.
[Bez tytułu.png](https://xentaxbackup.github.io/file/23173_Bez tytułu.png)
## Post #669
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-12-22T21:00:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from zimex25 ↑Thu Dec 22, 2022 5:39 am at Thu Dec 22, 2022 5:39 am
>
> 
...I tried with XnaLara importer for 3ds Max but smooth looking weird...
Stay away from that importer and 3dsMax when comes about the converted assets to ASCII, you need Blender:
[viewtopic.php?p=187182#p187182](https://forum.xentax.com/viewtopic.php?p=187182#p187182)
And also, that BF2042 tool does NOT support normals for the new NFS Unbound game, NFS games under Frostbite engine have a different format for storing normals, while BF2042 has nothing to do with it, that's why your not getting proper exported mesh, i already stated that yet you choose to ignore it and make a entitled comment.
## Post #670
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2022-12-26T22:15:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I don't know if I missed out on a reply to this thread (sorry in advance if I did) but did Battlefield 5 ever have a tool for extracting full bodied game models (other than id-daemon's head deformation fixer)?
## Post #671
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-12-28T03:15:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from artworkplay ↑Tue Dec 27, 2022 6:15 am at Tue Dec 27, 2022 6:15 am
>
> ...did Battlefield 5 ever have a tool for extracting full bodied game models (other than id-daemon's head deformation fixer)?
[viewtopic.php?p=147355#p147355](https://forum.xentax.com/viewtopic.php?p=147355#p147355)
Tool for face fixes has never been releases, it is private, only SMD one frame animation fixes are included in the link above, as well as the BFV tool for mesh conversion.
## Post #672
- Username: g0rd0nfr33man
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 16, 2022 9:38 am
- Post datetime: 2023-01-01T23:59:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi Everyone. I've been scouring through forum after model site after forum for days and I still haven't gotten an answer to this question: How do you rip models from Battlefield 2042? I was hoping someone could shed some light on the subject.
## Post #673
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-02T02:43:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from g0rd0nfr33man ↑Mon Jan 02, 2023 7:59 am at Mon Jan 02, 2023 7:59 am
>
> ...How do you rip models from Battlefield 2042? I was hoping someone could shed some light on the subject.
What is wrong with the tools to extract and then convert, where its already explained? On the following link:
[viewtopic.php?p=181685#p181685](https://forum.xentax.com/viewtopic.php?p=181685#p181685)
## Post #674
- Username: g0rd0nfr33man
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 16, 2022 9:38 am
- Post datetime: 2023-01-02T03:30:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I appreciate it, thank you. Sorry.
## Post #675
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2023-01-03T09:18:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Wed Dec 28, 2022 11:15 am at Wed Dec 28, 2022 11:15 am
>
> 
artworkplay wrote: ↑Tue Dec 27, 2022 6:15 am...did Battlefield 5 ever have a tool for extracting full bodied game models (other than id-daemon's head deformation fixer)?
viewtopic.php?p=147355#p147355
Tool for face fixes has never been releases, it is private, only SMD one frame animation fixes are included in the link above, as well as the BFV tool for mesh conversion.
thanks! your reply is much appreciated!
## Post #676
- Username: izfitz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 07, 2023 10:11 pm
- Post datetime: 2023-01-07T15:19:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

i am not fully understanding all of this, I have the toc_heat application and dragging and dropping the toc files into said app. Yet the command pops up for a split sec and disappears. its not dumping anything i put into it. Am i missing a step or unbound just doesnt work for toc_heat. only issue is that the post states that you need oo2core_8_win64 but unbound uses  oo2core_9_win64, i dont think it makes a difference.
## Post #677
- Username: izfitz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 07, 2023 10:11 pm
- Post datetime: 2023-01-07T16:34:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

[https://ibb.co/syysmr3](https://ibb.co/syysmr3)
after sometime i figured something out and now im stuck with a mess
## Post #678
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-08T02:53:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from izfitz ↑Sat Jan 07, 2023 11:19 pm at Sat Jan 07, 2023 11:19 pm
>
> 
i am not fully understanding all of this, I have the toc_heat application and dragging and dropping the toc files into said app. Yet the command pops up for a split sec and disappears. its not dumping anything i put into it. Am i missing a step or unbound just doesnt work for toc_heat. only issue is that the post states that you need oo2core_8_win64 but unbound uses  oo2core_9_win64, i dont think it makes a difference.
Regardless of what oodle version the game has, the tool was developed with a specific version, in that case version 8 usually renaming the dll to the required version works, and also you seem to be missing lots of steps to achieve in what your trying to do, you need to explain better how or what you did.
Also your using the wrong tool, you didn't even bother to go through the posts to find the right answer.
[viewtopic.php?p=188489#p188489](https://forum.xentax.com/viewtopic.php?p=188489#p188489)
## Post #679
- Username: dantesai
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Feb 09, 2014 10:42 am
- Post datetime: 2023-01-08T09:53:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Sep 10, 2022 5:14 am at Sat Sep 10, 2022 5:14 am
>
> 
cashgrany wrote: ↑Sun Sep 04, 2022 4:51 pm...I can't find how to open or convert the .ascii files obtained with fb_terrain_swbf2.exe...
Noesis or Blender can open those converted ASCIIs, as long as you provide to those tools the correct python script to load them, for Blender you can use: https://github.com/johnzero7/XNALaraMesh

Also for Blender you can try: https://github.com/REDxEYE/blender_xna
For Noesis: https://github.com/REDxEYE/noe_xna
Both require the following library though to function properly: https://github.com/REDxEYE/py_xna_lib

Why is everyone so lazy to use the search function, why oh why 
TheHarryAli wrote: ↑Fri Sep 09, 2022 8:45 pm...I can't use this tool by Daemoon1. When i open the exe files the command prompt appears and closes without doing anything...
It is a cmd tool, the developer described already how to use it, in any of his threads/posts he explains how to use his tools, you write his commands in to a text file, change extension from *.TXT to *.BAT then you run that BAT like you would any other executable.

The following is one scenario on how to use it, except you follow the commands given to that respective tool your working with by the developer.
viewtopic.php?p=186121#p186121
please let me know py_xna_lib place where,thx
## Post #680
- Username: Deckardddd
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 10, 2022 11:54 am
- Post datetime: 2023-01-19T08:59:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hey all, is it possible to use the map tool to extract maps from BFV?
## Post #681
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-20T00:46:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Deckardddd ↑Thu Jan 19, 2023 4:59 pm at Thu Jan 19, 2023 4:59 pm
>
> 
Hey all, is it possible to use the map tool to extract maps from BFV?
No. What ever map tool you saw you can clearly see it being specified as to what game it supports.
## Post #682
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2023-01-28T13:10:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Trying to extract maps for SWBF2

Iv dumped the game, and im trying to extract a map
I open CMD to the folder location of the map tool, i drag in the tool exe and i drag in a ebd and hit enter
It says done immediately but theres no files anywhere for anything

Im not sure what actually files im meant to be looking at
Im after the venator interior
I looked at E:\- SWBF2\Game Dump\bundles\levels\mp\kashyyyk_01\venatorinterior.ebx
and a few other files here has venator in the name but these dont do anything, are these the wrong files to look at?

Anyone have any idea, what is the correct map files im meant to be trying to use with the map tool as theres 1000s of files and none so far are doing much so im guessing im just feeding it the wrong file

Im looking in the level folder but also there are folders with s and a number and there are level folders in there so im checking those but still not getting anything

Any ideas?
## Post #683
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-01-28T13:26:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from speaker60 ↑Sat Jan 28, 2023 9:10 pm at Sat Jan 28, 2023 9:10 pm
>
> 
Any ideas?
whats your bp.db size?
## Post #684
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2023-01-28T13:47:32+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sat Jan 28, 2023 9:26 pm at Sat Jan 28, 2023 9:26 pm
>
> 
speaker60 wrote: ↑Sat Jan 28, 2023 9:10 pm
Any ideas?

whats your bp.db size?

Im just out atm so i cant check, what size should it be roughly, perhaps something when wrong ang i should redo the database scan?

Edit: And the map files should just be any of the ebx files in any of the level folders right?
I assume all levels are broken up into parts (each of the ebx files im seeing)
## Post #685
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-01-28T17:10:18+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from speaker60 ↑Sat Jan 28, 2023 9:47 pm at Sat Jan 28, 2023 9:47 pm
>
> 
Im just out atm so i cant check, what size should it be roughly
about 5 mb
## Post #686
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2023-01-28T22:01:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sun Jan 29, 2023 1:10 am at Sun Jan 29, 2023 1:10 am
>
> 
speaker60 wrote: ↑Sat Jan 28, 2023 9:47 pm
Im just out atm so i cant check, what size should it be roughly

about 5 mb

Mine was 200kb sooo im running it again
## Post #687
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2023-01-29T19:54:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

So after importing a section I can see some placement issues


Its consistently on the right side, left side is fine. This is meant to be symmetrical both sides but you can see on the right walls and floors are off position, is this a known thing.
Any solution to this or why it might happen, or is there just know what around this

Also dose the old Batch_Itexture_Converter_SWBF2 still work on the latest build of the game
I ran it set texture folder to the dump bundle folder and chunk to the dump chunk folder i can see the number count in there 1000s ect The i press get dds and it freeze for a wile then eventually comes back after some time but then nothing no dds anywhere

I saw it wasnt your tool originally just asking or is there another better way to convert textures to dds/png?
## Post #688
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-30T19:51:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from speaker60 ↑Mon Jan 30, 2023 3:54 am at Mon Jan 30, 2023 3:54 am
>
> 
...Any solution to this or why it might happen, or is there just know what around this...
It is a known issue for SWBFII, i too tested the tool and there are quite a few issues with improper placement and/or missing, as i like the map too, i'm sure the dev knows them, once he will have time he might resume the tool, we will have to wait and see.
## Post #689
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2023-01-30T20:42:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Tue Jan 31, 2023 3:51 am at Tue Jan 31, 2023 3:51 am
>
> 
speaker60 wrote: ↑Mon Jan 30, 2023 3:54 am
...Any solution to this or why it might happen, or is there just know what around this...
It is a known issue for SWBFII, i too tested the tool and there are quite a few issues with improper placement and/or missing, as i like the map too, i'm sure the dev knows them, once he will have time he might resume the tool, we will have to wait and see.

Ah okay its odd its just on one said, or rather its nod odd as its consistent so maybe that can tell what the issue might be with flipped assets not being translated right. For the venter here the left side, or i should say the right side of the ship just left in the picture was completely fine all placed right and not missing parts, i dont think parts are missing there just placed wrong so it looks like theres gaps

So do you use another method for getting textures, i tired that older tool but had no luck with it
It never made any dds images after clicking the get dds button, it freezes for a wile but comes back and nothing, if i click the show details option it dose show a bunch of texture names but beyond that nothing else
## Post #690
- Username: yunochloe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 23, 2022 4:32 pm
- Post datetime: 2023-02-01T14:52:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

does it work with Dead Space Remake? i mean i have it for ps5, but i'm only gonna buy it for pc too if i'm able to extract stuff
## Post #691
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-02-06T18:51:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I already made a version to support asset extraction for Dead Space.
Need a little time to support data itself.
## Post #692
- Username: dionaea
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 25, 2021 9:02 pm
- Post datetime: 2023-02-07T14:06:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Tue Feb 07, 2023 2:51 am at Tue Feb 07, 2023 2:51 am
>
> 
I already made a version to support asset extraction for Dead Space.
Need a little time to support data itself.

daemon1 sorry for bothering you but can you please check your pm?
## Post #693
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-02-18T13:45:31+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Dead Space (2023 Remake) tools



Dump the game with toc_dsr.exe
(usage is the same as for all latest games, such as [bf2042 here](https://forum.xentax.com/viewtopic.php?p=181685#p181685))

Convert models with Fb_dsr.exe
(by default, expects human_default_skeleton.ebx but you can set skeleton name as 2nd parameter as usual)
[dsr.7z](https://xentaxbackup.github.io/file/23427_dsr.7z)
## Post #694
- Username: Banner2020
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 23, 2020 6:54 pm
- Post datetime: 2023-02-19T00:01:49+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sat Feb 18, 2023 9:45 pm at Sat Feb 18, 2023 9:45 pm
>
> 
Dead Space (2023 Remake) tools



Dump the game with toc_dsr.exe
(usage is the same as for all latest games, such as bf2042 here)

Convert models with Fb_dsr.exe
(by default, expects human_default_skeleton.ebx but you can set skeleton name as 2nd parameter as usual)

good job!
## Post #695
- Username: lovesdgfr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 22, 2023 4:39 pm
- Post datetime: 2023-02-22T15:47:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Can anyone teach me how to extract the model and texture of the anthem?
## Post #696
- Username: qq1982
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 28, 2023 1:27 am
- Post datetime: 2023-02-27T20:47:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

What is ASCII file after unpacking, I import SMD to blender, but what should I do with ASCII file
## Post #697
- Username: qq1982
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 28, 2023 1:27 am
- Post datetime: 2023-02-27T21:18:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi, for say I have extracted a tank model from 2042, how should I put the texture on it? So far I only have the 2042_mesh tool...
## Post #698
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2023-02-28T08:26:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from lovesdgfr ↑Wed Feb 22, 2023 11:47 pm at Wed Feb 22, 2023 11:47 pm
>
> 
Can anyone teach me how to extract the model and texture of the anthem?

Just use:
Frosty editor: [https://frostytoolsuite.com/](https://frostytoolsuite.com/)
Frosty editor discord: [https://discord.gg/Y22PebTE](https://discord.gg/Y22PebTE)
## Post #699
- Username: lovesdgfr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 22, 2023 4:39 pm
- Post datetime: 2023-03-08T17:09:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

This editor needs a secret key.
## Post #700
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-03-08T19:51:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from lovesdgfr ↑Thu Mar 09, 2023 1:09 am at Thu Mar 09, 2023 1:09 am
>
> 
This editor needs a secret key.
Yes, certain Frostbite games require a key entered in HEX values in order to decrypt assets from that specific game, if you type on google fifa key for frosty or something similar, you'll find it, that key is illegal to share over all out in the open.
## Post #701
- Username: suenwaichit
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 29, 2022 10:17 am
- Post datetime: 2023-03-09T01:44:52+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

This is sort of a step-by-step guide for extracting models and textures from Battlefield 2042, using daemon1's Battlefield 2042 Tool and Sharppy's Frostbite Texture Tools. I wrote this mainly to remind myself of the process, but I figure it is good enough for newbie to save some head-scratching.
The guide is not complete as I am figuring out face mesh fixing. In addition, it includes a table of asset filename matching in-game's equivalent for convenience.

[Step-by-step Guide](https://docs.google.com/document/d/1lbayLB3CzewkF7R0FFoz1lJsf_QYjsUL/)
[Battlefield 2042 Tool](https://forum.xentax.com/viewtopic.php?p=181685#p181685)
[Frostbite Texture Tools](https://forum.xentax.com/viewtopic.php?p=182107#p182107)
## Post #702
- Username: Dimka51Rus
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 28, 2017 11:27 pm
- Post datetime: 2023-03-09T09:03:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from lovesdgfr ↑Thu Mar 09, 2023 1:09 am at Thu Mar 09, 2023 1:09 am
>
> 
This editor needs a secret key.

Anthem encryption key
0B0E04030409080C010708010E0B0B02
## Post #703
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2023-03-13T18:31:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I have a question here how to open these files?
game Army of Two: The Devil's Cartel.
Frostbite 2 game engine.
[https://drive.google.com/file/d/1CoOny7 ... share_link](https://drive.google.com/file/d/1CoOny7UaZnqVchyMPKgEUdzO0oMgYDpZ/view?usp=share_link)
## Post #704
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-03-13T22:40:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Sinnery32 ↑Tue Mar 14, 2023 2:31 am at Tue Mar 14, 2023 2:31 am
>
> 
I have a question here how to open these files?...
I already explained what to do here: [viewtopic.php?p=190355#p190355](https://forum.xentax.com/viewtopic.php?p=190355#p190355)
You seem to have disregard entirely my previous post at same link, your files are extracted WRONG, as i have already specified there are NO tools for the game to convert the meshes, yet the script ebxtoasset from link i posted initially does work for textures/sounds i believe.
## Post #705
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2023-03-14T09:47:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

In this case, I ask for help, because I'm already confused ....
who and how much should be paid to get models and textures of "masks" from this game?
## Post #706
- Username: Nathanael
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 15, 2023 9:12 pm
- Post datetime: 2023-03-15T13:37:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Mon Feb 18, 2019 3:26 am at Mon Feb 18, 2019 3:26 am
>
> 
Cutsom inquisitor tool is ready. But it will not be published, at least yet.
Those who want to extract cutsom faces, PM me.

Hello, I've been looking for a tool for a long time to extract a custom head mesh for the inquisition, Since when trying to do this work with a ninja ripper it is impossible, the structure of the mesh that I extract from the game is damaged, Please tell me, maybe you have already published the tool somewhere? Because I've looked through all the pages of this post but haven't found anything. And I apologize in advance, English is my second language
## Post #707
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-03-15T15:19:19+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

no, i never posted that tool
## Post #708
- Username: Nathanael
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 15, 2023 9:12 pm
- Post datetime: 2023-03-15T16:24:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Mar 15, 2023 11:19 pm at Wed Mar 15, 2023 11:19 pm
>
> 
no, i never posted that tool

Oh thanks for the reply, I was planning on making a mod for Anders and port to D.A:O, Fortunately, your tool is not the only way to do this. In any case, I shouldn't have bothered you.
## Post #709
- Username: jonslynn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 14, 2015 2:03 pm
- Post datetime: 2023-03-18T15:38:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Thank you so much daemon1!  I did a Bespin level first from SWBF2.





Question... Is the Anthem version better in what way?  I have been using other and not sure what the difference is but thanks for all you did and sharing.  I am working on Naboo files now.  Hard part is textures.  I merge the materials with same name.

Well done!  Cheers and thanks again.

[https://drive.google.com/file/d/1ZeGPCP ... share_link](https://drive.google.com/file/d/1ZeGPCPjPdkvduuo294lnwdOFjLHTyBrA/view?usp=share_link)
## Post #710
- Username: calahir
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 14, 2023 11:36 pm
- Post datetime: 2023-03-19T13:04:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Extracting models is working well. Is there a way to extract animations too?
## Post #711
- Username: kloruklass
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Jan 27, 2021 4:30 am
- Post datetime: 2023-03-29T21:30:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I've extracted the TOC files from Dead Space 2023, but how to convert the EBX sound files?
I've tried the Frostbite script "EBX to Asset" but it always asks me for the "GuidTable" which is not available.

Link: [https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)

The "Dumper" inside which should extract all the game files and write the GuidTable is not working at all.

Can someone help me out?
## Post #712
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-03-29T22:02:45+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from kloruklass ↑Thu Mar 30, 2023 5:30 am at Thu Mar 30, 2023 5:30 am
>
> 
I've extracted the TOC files from Dead Space 2023, but how to convert the EBX sound files?
Your best bet is to try/test FrostyToolSuite, no clue how well the game is supported or if even, so check it out.

> Reply from kloruklass ↑Thu Mar 30, 2023 5:30 am at Thu Mar 30, 2023 5:30 am
>
> 
I've tried the Frostbite script "EBX to Asset" but it always asks me for the "GuidTable" which is not available.

Link: https://github.com/NicknineTheEagle/Frostbite-Scripts

The "Dumper" inside which should extract all the game files and write the GuidTable is not working at all.

Can someone help me out?
You are out of luck in this regard using Nicknines scripts, he stopped supporting the Frostbite engine after 2017/2018 games i believe from what i can remember, anything new after and including Anthem, is NOT supported so neither of the scripts in GitHub above will be of any help to you for that game.
## Post #713
- Username: Nathanael
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 15, 2023 9:12 pm
- Post datetime: 2023-04-03T02:16:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Mar 15, 2023 11:19 pm at Wed Mar 15, 2023 11:19 pm
>
> 
no, i never posted that tool

Can I ask you if you are fixing the bones of the head mesh with the tool xna posing studio? It seems to me looking at your screenshot that this is mostly manual work
## Post #714
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-04-03T15:16:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Nathanael ↑Mon Apr 03, 2023 10:16 am at Mon Apr 03, 2023 10:16 am
>
> 
daemon1 wrote: ↑Wed Mar 15, 2023 11:19 pm
no, i never posted that tool


Can I ask you if you are fixing the bones of the head mesh with the tool xna posing studio? It seems to me looking at your screenshot that this is mostly manual work
No, no manual work is involved.
## Post #715
- Username: minaouet
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 05, 2023 2:53 am
- Post datetime: 2023-04-04T19:29:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hello i'm trying to extract some 3D model from BF 2042. Almost of files is correctly export expect all files concerning the Exodus ship.

The bf2042_mesh.exe return the following message :

C:\Users\minaouet\Documents\RIP BF2042\2042_dump>bf2042_mesh.exe imm_shipbody_01_mesh.MeshSet
Chunk not found: BAEBD7C6671B4B6ACE3D0EF3C624590B.chunk

I have already treat every toc files with toc2042.exe

Any one have an idea of what is wrong with these particular files ? 

Thank You
## Post #716
- Username: jinougaf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 01, 2022 11:54 pm
- Post datetime: 2023-04-12T08:00:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Anyone knows where is the audio files for Battlefield 2042 located? I managed to find the mesh and texture but I can not find any audio files.
## Post #717
- Username: kloruklass
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Jan 27, 2021 4:30 am
- Post datetime: 2023-04-18T11:07:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Isn't it possible to make a tool to extract the audio and sound effects from Dead Space Remake, Battlefield 2042, Anthem, and previous games that are made with Frostbite? Everything is about graphics, and it's great for those who are interested. But the audio part is always left behind.
## Post #718
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-04-18T19:24:57+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from kloruklass ↑Tue Apr 18, 2023 7:07 pm at Tue Apr 18, 2023 7:07 pm
>
> 
Isn't it possible to make a tool to extract the audio and sound effects from Dead Space Remake, Battlefield 2042, Anthem, and previous games that are made with Frostbite? Everything is about graphics, and it's great for those who are interested. But the audio part is always left behind.
As i have responded above, you CAN extract ALL audios/sounds/music with proper names and file folder structure a game has on the Frostbite engine including consoles and earlier games as you said, just NOT starting with Anthem game and up due to changes in the format using the script by Nicknine mentioned in link above.
He just didn't and probably never will support the new formats, which is odd giving the fact he is a audio reversing guy first and foremost.
Why don't you ask him directly here in the forum on his account or on github, maybe he changed his mind over time, you never know.

PS. If i am not mistaken, you can use Frosty Suite to dump entire audio/sound folder to XML, then parse each audio/sound XML and rename yourself each and every .chunk to their corresponding converted/de-serialized XML from EBX. A bit of heads up, that is a lot of manual work that can take weeks or months.
## Post #719
- Username: dionaea
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 25, 2021 9:02 pm
- Post datetime: 2023-04-21T15:06:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Wed Mar 15, 2023 11:19 pm at Wed Mar 15, 2023 11:19 pm
>
> 
no, i never posted that tool

so is there still any possibility to ask you to extract custom inquisitor head?
## Post #720
- Username: richardphone
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jan 04, 2023 8:31 pm
- Post datetime: 2023-05-01T19:11:37+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

i'm lookng into extracting animation for anthem did anyone manage to do that ?
## Post #721
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-01T21:16:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from richardphone ↑Tue May 02, 2023 3:11 am at Tue May 02, 2023 3:11 am
>
> 
i'm lookng into extracting animation for anthem did anyone manage to do that ?
There are no tools for animations for games built on Frostbite engine, hopefully in the very far future that will happen.
## Post #722
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-13T18:07:17+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Does anyone have the latest tool that were posted for CnC Generals 2013(Frostbite 2)

I can get the mesh extraction to work but ebx to txt doesn't work and if I use another ext to txt it doesn't import into 3ds max
## Post #723
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-13T20:11:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Sun May 14, 2023 2:07 am at Sun May 14, 2023 2:07 am
>
> Does anyone have the latest tool that were posted for CnC Generals 2013(Frostbite 2)
Never knew this even existed, where?

> Reply from SilverEvo ↑Sun May 14, 2023 2:07 am at Sun May 14, 2023 2:07 am
>
> I can get the mesh extraction to work but ebx to txt doesn't work and if I use another ext to txt it doesn't import into 3ds max
Would've helped but i never knew there where working tools for i game i personally never seen released in anyway?
## Post #724
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-13T23:10:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sun May 14, 2023 4:11 am at Sun May 14, 2023 4:11 am
>
> 
SilverEvo wrote: ↑Sun May 14, 2023 2:07 amDoes anyone have the latest tool that were posted for CnC Generals 2013(Frostbite 2)
Never knew this even existed, where?
SilverEvo wrote: ↑Sun May 14, 2023 2:07 amI can get the mesh extraction to work but ebx to txt doesn't work and if I use another ext to txt it doesn't import into 3ds max  
Would've helped but i never knew there where working tools for i game i personally never seen released in anyway?
[https://ppmforums.com/topic-44642/cc-ge ... pha-tools/](https://ppmforums.com/topic-44642/cc-generals-2-alpha-tools/)

I found some tools here. I remember using some other scripts to get the ebx to txt to work so the skeleton works with the max script plugin, but no luck so far
## Post #725
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-13T23:48:33+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Sun May 14, 2023 7:10 am at Sun May 14, 2023 7:10 am
>
> I found some tools here. I remember using some other scripts to get the ebx to txt to work so the skeleton works with the max script plugin, but no luck so far
I have no clue where such build can be downloaded from to test as well, but have you tried:
[https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)

If i could find the build to test i bet current tools for it must work if its same engine version that i think it may be, not sure though impossible to know with out actual game build.
## Post #726
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-13T23:52:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sun May 14, 2023 7:48 am at Sun May 14, 2023 7:48 am
>
> 
SilverEvo wrote: ↑Sun May 14, 2023 7:10 amI found some tools here. I remember using some other scripts to get the ebx to txt to work so the skeleton works with the max script plugin, but no luck so far
I have no clue where such build can be downloaded from to test as well, but have you tried:
https://github.com/NicknineTheEagle/Frostbite-Scripts

If i could find the build to test i bet tools fro it must work if its same engine version that i think it may be, not sure though impossible to know with out actual game build.

Yes I had to use that ebxtotxt because the one from the originals generals tools didn't work. I can load the mesh fine after hex editing, but either the max script doesn't work properly for loading the skeleton or the ebxtotxt didn't convert it properly. I just don't remember what I used last year to get the skeleton to load   

[](http://epvpimg.com/hwztbab)
## Post #727
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-14T04:24:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Sun May 14, 2023 7:52 am at Sun May 14, 2023 7:52 am
>
> Yes I had to use that ebxtotxt because the one from the originals generals tools didn't work. I can load the mesh fine after hex editing, but either the max script doesn't work properly for loading the skeleton or the ebxtotxt didn't convert it properly. I just don't remember what I used last year to get the skeleton to load
Ok, so from what i noticed this game has slight changes to the format and current tools in this thread that are for Frostbite 2 games do not work, using Nicknine's scripts doesn't seem to work as they do not export metadata needed for daemon's tools, with some luck maybe daemon will make a tool for this Alpha never released game, you never know.

Also from what i could find on my HDD among the old python scripts the following seems to deserialize the EBX's to TXT correctly, give it a try, there's also the chance that the 3dsMax script based on your screenshot above will not work properly on new versions, not sure exactly as those scripts where made/used around 2014-2016 of 3dsMax versions.


 ebx2txt.zip
(3.96 KiB) Downloaded 23 times
## Post #728
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-14T11:23:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sun May 14, 2023 12:24 pm at Sun May 14, 2023 12:24 pm
>
> 
Ok, so from what i noticed this game has slight changes to the format and current tools in this thread that are for Frostbite 2 games do not work, using Nicknine's scripts doesn't seem to work as they do not export metadata needed for daemon's tools, with some luck maybe daemon will make a tool for this Alpha never released game, you never know.

Also from what i could find on my HDD among the old python scripts the following seems to deserialize the EBX's to TXT correctly, give it a try, there's also the chance that the 3dsMax script based on your screenshot above will not work properly on new versions, not sure exactly as those scripts where made/used around 2014-2016 of 3dsMax versions.
ebx2txt.zip

Thank you soo much for this script. I just tested it and it imports the skeleton (using 3ds max 2022)
## Post #729
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-14T11:25:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Sun May 14, 2023 7:23 pm at Sun May 14, 2023 7:23 pm
>
> Thank you soo much for this script. I just tested it and it imports the skeleton (using 3ds max 2022)
That is good to know, have fun!
## Post #730
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-14T11:43:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sun May 14, 2023 7:25 pm at Sun May 14, 2023 7:25 pm
>
> 
SilverEvo wrote: ↑Sun May 14, 2023 7:23 pmThank you soo much for this script. I just tested it and it imports the skeleton (using 3ds max 2022)   
That is good to know, have fun!

Thanks I sure will since I have gotten rusty with hex editing and so far managed to get only vehicle and infantry to load.

[](http://epvpimg.com/SDgdcab)

Might try some chunk tools from here to see if they will help with that.
## Post #731
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-14T13:35:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Lucky me I found a screenshot from an year ago what lines I had to delete for Buildings in the .mesh file for them to load. Still tho if anyone want's to update/make tools for this game I wouldn't mind   

[](http://epvpimg.com/1cWdeab)
## Post #732
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-15T20:17:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Tue May 16, 2023 3:16 am at Tue May 16, 2023 3:16 am
>
> ...Before I managed to pull out buildings when they were completed 



but now I can only extract the buildup mesh 



as_airfield for example the skn buildup mesh is 2.15mb while the as_airfield_mesh is only 2.00kb...
PS Try to ask questions, regardless of their nature when comes about games that can be posted publicly, in case anyone comes across same issue, they might find it helpful and avoid struggling 

To sum it up, i personally never dealt with the 3dsMax setup you are doing on the Frostbite games based on the screenshots above, so i have no idea what is your trying to do, and what workarounds needs to be performed in order to achieve your needed results, but...

The reason you see such difference in sizes, the large one already has the chunk data next in line after the header and its specifications while the small one its just the header if you will and holds specifications as to what *.chunk needs to load in order to import that data with in that *.chunk.

If you open up that small, *.MeshSet in a hex editor, at the top, in front of the FF FF FF FF sequence of bytes, there is a 16byte GUID, that GUID is the first LOD of the *.MeshSet in some cases there is only one LOD while other *.MeshSets can have more LODs, leads to the *.chunk of data that holds the geometry you are looking for.
This example might be clearer: [viewtopic.php?p=135900#p135900](https://forum.xentax.com/viewtopic.php?p=135900#p135900)

Hope that clears it up a bit.
## Post #733
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-15T23:13:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Tue May 16, 2023 4:17 am at Tue May 16, 2023 4:17 am
>
> 
SilverEvo wrote: ↑Tue May 16, 2023 3:16 am...Before I managed to pull out buildings when they were completed 



but now I can only extract the buildup mesh 



as_airfield for example the skn buildup mesh is 2.15mb while the as_airfield_mesh is only 2.00kb...
PS Try to ask questions, regardless of their nature when comes about games that can be posted publicly, in case anyone comes across same issue, they might find it helpful and avoid struggling 

To sum it up, i personally never dealt with the 3dsMax setup you are doing on the Frostbite games based on the screenshots above, so i have no idea what is your trying to do, and what workarounds needs to be performed in order to achieve your needed results, but...

The reason you see such difference in sizes, the large one already has the chunk data next in line after the header and its specifications while the small one its just the header if you will and holds specifications as to what *.chunk needs to load in order to import that data with in that *.chunk.

If you open up that small, *.MeshSet in a hex editor, at the top, in front of the FF FF FF FF sequence of bytes, there is a 16byte GUID, that GUID is the first LOD of the *.MeshSet in some cases there is only one LOD while other *.MeshSets can have more LODs, leads to the *.chunk of data that holds the geometry you are looking for.
This example might be clearer: viewtopic.php?p=135900#p135900

Hope that clears it up a bit.

Will do in the future. I tried that on the link you send me, but couldn't find matching results in the .mesh file. The results I am going for is before I somehow managed to load the completed building with everything in place while now I can just load the skn mesh that is the structure durring its building animation.

Edit. NVM I am a bonehead and figured out how to do this [viewtopic.php?p=135900#p135900](https://forum.xentax.com/viewtopic.php?p=135900#p135900). Everything works as intended thanks for the help
## Post #734
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-16T17:26:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

[](http://epvpimg.com/mWo6eab)

[](http://epvpimg.com/g39heab)

Now I am having issues with the weights when I apply the rig to the mesh   (also tested in 2012 and same issue)
## Post #735
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-16T21:14:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Wed May 17, 2023 1:26 am at Wed May 17, 2023 1:26 am
>
> ...Now I am having issues with the weights when I apply the rig to the mesh   (also tested in 2012 and same issue)
Since in this situation only the author of the script can help with the weights, i can only offer a different suggestion/approach.

From your edited *.MeshSets where you say you have to modify in hex, try the following tools located,
here for the NFSTR game: [viewtopic.php?p=181711#p181711](https://forum.xentax.com/viewtopic.php?p=181711#p181711)
and here for BF3 and MOHWF: [viewtopic.php?p=134793#p134793](https://forum.xentax.com/viewtopic.php?p=134793#p134793)
Since they are all part of same Frostbiet 2 game engine, that way maybe... you'll get lucky and convert them with weights.
## Post #736
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-17T14:27:13+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Yeah sadly none of those worked on the extracted generals 2 files. I am getting this 

[](http://epvpimg.com/Rfkrfab)

And I checked I don't have veniceantske01.ebx in the dump. I tried two different dumps with two scripts and none of them have that.

--------------------Update--------------------------------
[](http://epvpimg.com/Tqj2fab)

Now it seems to work after renaming the ebx to veniceantske01.ebx, but it fails to load the chunk ig.
## Post #737
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-17T19:07:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Wed May 17, 2023 10:27 pm at Wed May 17, 2023 10:27 pm
>
> ...Now it seems to work after renaming the ebx to veniceantske01.ebx, but it fails to load the chunk ig.
That is correct, ANY skeleton that the game might have or specific for that model needs to be renamed to the venice one as its hardcoded in to the tool since its from BF3 game and the rest of Frostbite 2 tools where made based off of that code with modifications for the other games.
Well, since you tried those options best bet would be for a tool to surface, in the near or very far future, who knows.
## Post #738
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-17T20:54:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Thu May 18, 2023 3:07 am at Thu May 18, 2023 3:07 am
>
> 
SilverEvo wrote: ↑Wed May 17, 2023 10:27 pm...Now it seems to work after renaming the ebx to veniceantske01.ebx, but it fails to load the chunk ig.
That is correct, ANY skeleton that the game might have or specific for that model needs to be renamed to the venice one as its hardcoded in to the tool since its from BF3 game and the rest of Frostbite 2 tools where made based off of that code with modifications for the other games.
Well, since you tried those options best bet would be for a tool to surface, in the near or very far future, who knows.

Can you provide me with any python scripts to dump bf3/bf4 so try and dump the game with them ?
## Post #739
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-17T23:07:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Thu May 18, 2023 4:54 am at Thu May 18, 2023 4:54 am
>
> ...Can you provide me with any python scripts to dump bf3/bf4 so try and dump the game with them ?
You already forgot about it: [https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts) ?
Those sets of scripts will dump pretty much any game up till 2018/Anthem, any platform, Frostbite 2 folder is for BF3, etc... while Frostbite 3 folder is for BF4, etc.
## Post #740
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-17T23:15:00+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Thu May 18, 2023 7:07 am at Thu May 18, 2023 7:07 am
>
> 
SilverEvo wrote: ↑Thu May 18, 2023 4:54 am...Can you provide me with any python scripts to dump bf3/bf4 so try and dump the game with them ?
You already forgot about it: https://github.com/NicknineTheEagle/Frostbite-Scripts ?
Those sets of scripts will dump pretty much any game up till 2018/Anthem, any platform, Frostbite 2 folder is for BF3, etc... while Frostbite 3 folder is for BF4, etc.

No. I just want to try different tools to dump the game. There is a difference in the chunks using the github tools and the tools for the game. The games may be running all on frostbite but so far Generals is the only RTS one.
## Post #741
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-17T23:23:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Thu May 18, 2023 7:15 am at Thu May 18, 2023 7:15 am
>
> No. I just want to try different tools to dump the game. There is a difference in the chunks using the github tools and the tools for the game. The games may be running all on frostbite but so far Generals is the only RTS one.
Older scripts that are posted somewhere on this forum, god knows where other forums exactly are fully deprecated and a bad idea.
Check the bottom part of this post, then you'll be all set regarding the chunk naming issue.
[viewtopic.php?p=181740#p181740](https://forum.xentax.com/viewtopic.php?p=181740#p181740)
## Post #742
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-19T23:12:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Thu May 18, 2023 7:23 am at Thu May 18, 2023 7:23 am
>
> 
SilverEvo wrote: ↑Thu May 18, 2023 7:15 amNo. I just want to try different tools to dump the game. There is a difference in the chunks using the github tools and the tools for the game. The games may be running all on frostbite but so far Generals is the only RTS one.
Older scripts that are posted somewhere on this forum, god knows where other forums exactly are fully deprecated and a bad idea.
Check the bottom part of this post, then you'll be all set regarding the chunk naming issue.
viewtopic.php?p=181740#p181740

I searched for quite a while and found some useful older scripts, but I still can't find a script that I think it may work BF3_Vehicle_Skeleton_reader

[https://www.youtube.com/watch?v=VdgwQpWCk84](https://www.youtube.com/watch?v=VdgwQpWCk84)
## Post #743
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-20T13:49:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Sat May 20, 2023 7:12 am at Sat May 20, 2023 7:12 am
>
> ..I searched for quite a while and found some useful older scripts, but I still can't find a script that I think it may work BF3_Vehicle_Skeleton_reader...
I am seriously confused as to what is your looking for exactly now?
Besides that CC Alpha never released game, that has no specific tools for it, the rest of the games already have the tools posted, some on the links i included in one of my posts above, to convert everything you need.
## Post #744
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-20T15:49:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat May 20, 2023 9:49 pm at Sat May 20, 2023 9:49 pm
>
> 
SilverEvo wrote: ↑Sat May 20, 2023 7:12 am..I searched for quite a while and found some useful older scripts, but I still can't find a script that I think it may work BF3_Vehicle_Skeleton_reader...
I am seriously confused as to what is your looking for exactly now?
Besides that CC Alpha never released game, that has no specific tools for it, the rest of the games already have the tools posted, some on the links i included in one of my posts above, to convert everything you need.

The alpha was never released but it was leaked and tools were made by Dainius G. I specifically posted above the script I need. The script I need is found in this video [https://www.youtube.com/watch?v=VdgwQpWCk84](https://www.youtube.com/watch?v=VdgwQpWCk84) for 3ds max named BF3_Vehicle_Skeleton_reader2.ms but the script download link has been taken down.
## Post #745
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-20T17:10:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Sat May 20, 2023 11:49 pm at Sat May 20, 2023 11:49 pm
>
> ...The script I need is found in this video https://www.youtube.com/watch?v=VdgwQpWCk84 for 3ds max named BF3_Vehicle_Skeleton_reader2.ms but the script download link has been taken down.
Why though, the BF3 tool works just fine, skeleton/weights support as well. Hence my confusion at the moment.
## Post #746
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-20T17:15:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

I need to see the max script that loads the vehicles to see if a friend of mine can make it work for generals 2 vehicles and fix the weight problems.
## Post #747
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-20T17:39:55+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from SilverEvo ↑Sun May 21, 2023 1:15 am at Sun May 21, 2023 1:15 am
>
> 
I need to see the max script that loads the vehicles to see if a friend of mine can make it work for generals 2 vehicles and fix the weight problems.
Ah, well, in that case i found these in one of my old HDDs. I personally was never able to use them, so... good luck on them.


 3dsMax_FrostbiteVarious.zip
(45.02 KiB) Downloaded 28 times
## Post #748
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-20T18:10:03+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sun May 21, 2023 1:39 am at Sun May 21, 2023 1:39 am
>
> 
Ah, well, in that case i found these in one of my old HDDs. I personally was never able to use them, so... good luck on them.
3dsMax_FrostbiteVarious.zip

Yes these are the ones.  I sent them to my friend to see if he can load the vehicle weights. Will post the script here if he manages to do it for the others if they want to tinker with Generals 2. Thanks again
## Post #749
- Username: Matheuh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2022 6:25 am
- Post datetime: 2023-05-25T01:12:58+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Deleted
## Post #750
- Username: Matheuh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2022 6:25 am
- Post datetime: 2023-05-25T01:20:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Sat Aug 13, 2022 10:26 pm at Sat Aug 13, 2022 10:26 pm
>
> 
Map tool set for Anthem.

Most map objects properly placed, including blueprints. Also basic terrain support.





1. Dump the game

Use the new toc_anthem_v3.exe, it was updated since original anthem dump tool, because i found that some rare chunks were not dumped, and they are needed for maps. So if you have dumped anthem before, you need to redump it.

Set desired parameters in ufbe.ini
Parameters are: 
- game path
- dump path
- asset type
Notice now there must be no "data" or "patch" in the end of "game path".
Asset type can be "ebx", "res", "chunks" or "all". Anything else (or empty line) is considered as "all".

Then you need to run dump tool on all .TOC files from the game. You can do them one by one as there are not too many, or in a batch, but its important that you must first run it on all .TOC files from "patch" folder, then on all .TOC files from "data" folder.

Tool needs oo2core_8_win64.dll or oo2core_7_win64.dll, just rename it to oo2core_8_win64.dll

2. Edit the included FB_MAPS.INI file with paths to your dump.

The other 3 tools need this fb_maps.ini file with 2 parameters: paths to dumped bundles (ebx+res) and chunks.

3. Create database

Run fb_maps_anthem_db.exe tool once, it will scan whole dump for meshsets and blueprints, so later maps can be converted fast, without the need to go into whole tree of assets. This will take a few minutes. After that, 2 files will be created: bp.db & meshnames.txt, which need to stay in the same folder with EXE for main tool to work.

4. Export maps

Use fb_maps_anthem.exe (main map tool) to convert maps. Drop any EBX on it, use in command line with 1 parameter, or create a batch.

In addition to .ascii export with all baked meshes, it will create a text file with a list of all mesh instances and their 3x4 transform matrices. So if you like, you can make a script for your favourite editor or engine (3dmax, maya, blender, unity, unreal) and place all meshes as instances.

5. Terrain export

Same usage as swbf2 terrain:

Drop .TerrainStreamingTree on fb_terrain_anthem.exe or use command line.

It will export heightmap parts into "hmap" subfolder. As you can see on the pictures above, terrain in frostbite is saved in square parts of different size, organized in a tree-like structure. Some parts may be very detailed, while others not. Tool will only save highest detail level for each square and skip all lower LODs.

6. Mesh export tool

Fb_anthem.exe - this was also included to support the new way of dumping meshsets (no metadata in filename, its included inside file). It also saves exported .ascii/.smd files in the original directory tree. Skeletons will be expected in the tool folder, as before.

Do you think its possible to do that for Battlefield Hardline it will be insane! :O
## Post #751
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-05-25T15:17:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Matheuh ↑Thu May 25, 2023 9:20 am at Thu May 25, 2023 9:20 am
>
> 
Do you think its possible to do that for Battlefield Hardline it will be insane! :O
Absolutely possible. Just it will require time to implement.
## Post #752
- Username: Matheuh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2022 6:25 am
- Post datetime: 2023-05-28T16:59:36+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Thu May 25, 2023 11:17 pm at Thu May 25, 2023 11:17 pm
>
> 
Matheuh wrote: ↑Thu May 25, 2023 9:20 am
Do you think its possible to do that for Battlefield Hardline it will be insane! :O

Absolutely possible. Just it will require time to implement.

I want it ! hahahaha
## Post #753
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-05-29T14:31:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Ok re-doing the process few times and now skeleton for vehicles somewhat working with incorrect bones.

[https://www.youtube.com/watch?v=tWzQYw95fMg](https://www.youtube.com/watch?v=tWzQYw95fMg)

nvm it works only for aircraft....
## Post #754
- Username: Matheuh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2022 6:25 am
- Post datetime: 2023-05-30T13:19:05+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hi! Any ideas where i can find transforms for mesh on BFH maps?
## Post #755
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-30T20:44:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Matheuh ↑Tue May 30, 2023 9:19 pm at Tue May 30, 2023 9:19 pm
>
> Hi! Any ideas where i can find transforms for mesh on BFH maps?
Not sure how many of them are already visible once you deserialize the EBXs to readable text and there you will find transforms in 4x3 matrix values, but for more complex map assets they are hidden inside havok assets, as far as i know there's no way to decompile those to a readable format.
## Post #756
- Username: Matheuh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2022 6:25 am
- Post datetime: 2023-05-30T22:25:14+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Wed May 31, 2023 4:44 am at Wed May 31, 2023 4:44 am
>
> 
Matheuh wrote: ↑Tue May 30, 2023 9:19 pmHi! Any ideas where i can find transforms for mesh on BFH maps?
Not sure how many of them are already visible once you deserialize the EBXs to readable text and there you will find transforms in 4x3 matrix values, but for more complex map assets they are hidden inside havok assets, as far as i know there's no way to decompile those to a readable format.

Alright thanks a lot!
## Post #757
- Username: HotDaniel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 02, 2019 9:41 am
- Post datetime: 2023-06-21T21:05:59+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hey guys, I'm trying to get  extract maps from BF 2042. I have downloaded the 2042.rar and follows the instructions. The questions I have are:
1 - Do I need to extract every single .toc beforehand or can I extract only specific ones?
2 - Once I have extracted either res or chunks, I am not seeing .meshsets in any folders at all. Do I need to set the .ini file to extract all files, not just res or chunks?

I need the meshset to generated meshes of maps, correct? What am I doing wrong in the process? Do I need other tools than the 2042.rar files?
## Post #758
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-21T21:17:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from HotDaniel ↑Thu Jun 22, 2023 5:05 am at Thu Jun 22, 2023 5:05 am
>
> 
Hey guys, I'm trying to get  extract maps from BF 2042.
...
Well, maps from this game are not supported the same way SWBF2 is, but if you where to extract it you need entire game as the assets are scattered through out entire game, so not just res and chunks, in third line inside the *.ini type all or if nothing is written it will extract entire game.
## Post #759
- Username: HotDaniel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 02, 2019 9:41 am
- Post datetime: 2023-06-21T22:17:54+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

If maps are not supported is it stupid to extract the assets? Or will I still be able to recreate parts or full maps from the extracted files? I'm assuming characters and weapons are still able to be extracted, correct?

Also, which .toc would I need to extract for the full game rip? Or do I need to use the tool on each .toc?

I appreciate the help.
## Post #760
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-21T22:42:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from HotDaniel ↑Thu Jun 22, 2023 6:17 am at Thu Jun 22, 2023 6:17 am
>
> 
If maps are not supported is it stupid to extract the assets? Or will I still be able to recreate parts or full maps from the extracted files? I'm assuming characters and weapons are still able to be extracted, correct?...
Why would it be stupid, either way, when comes about Frostbite engine based games best way is to dump/extract entire game.
In order for you to fully re-create the map manually you'd need to reverse on your own the EBXs and other res asset types to extract the matrix transforms and instances for the map assets, not to mention the terrain format, so unless your a reverser, i doubt it.

> Reply from HotDaniel ↑Thu Jun 22, 2023 6:17 am at Thu Jun 22, 2023 6:17 am
>
> ...Or do I need to use the tool on each .toc?...
Yes.
After you've configured your entire setup before extraction just run this batch at root of the game folder:

```
for /r %%a in (*.toc) do tool.exe %%a
```
## Post #761
- Username: Berserker79
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 31, 2019 12:50 am
- Post datetime: 2023-06-29T09:13:28+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hey everyone,

I’m trying to apply to Mass Effect: Andromeda the [process explained here by mono24](https://forum.xentax.com/viewtopic.php?p=147373#p147373) (with Dragon Age: Inquisition as example) in order to use the ME:A morph tool and obtain a non-distorted face mesh from the corresponding morph file.

I had no problem getting the process to work with DA:I, but when I attempted to do the same with ME:A it seems that I have run into some problem, because the mesh I obtained still looks distorted. My suspicion is that I may have “corrupted” files due to using the wrong script to dump the game or maybe I’m not giving the Fb_MEA_morph.exe tool the correct assets to work with.

I will explain below the steps that I followed and hope someone here can spot the mistake or provide some suggestion. If anyone has direct experience using the Fb_MEA_morph.exe tool, your input would really be helpful. Thanks in advance!

Here’s what I did so far:

1) Full dump of the game

I’ve gone through the whole thread several times, but I did not find any explicit mention or reference to a script that is known to dump ME:A. Therefore, I tried using first the swbf2full script and then the fb3dump script (both posted by daemon1 in this thread), but neither seemed to work with ME:A. In each of these scripts, I modified the line bf4Directory=r“[gamepath]” to point to my ME:A install directory (D:\Games\ Mass Effect Andromeda) and modified the outputfolder=“[outputfolderpath]” line to point to an existing folder created to store the dumped files. Next, I loaded the script in IDLE (Python 2.7.6 32-bit), hit F5 and got an error early on. I can post more details about the error if helpful, e.g. if I do need to (re)dump the game using either of these scripts.

Also, I tried to use UFBE 0.2.1 for good measure, but got an error right away once I hit “scan bundles”.

I resorted to using [NicknineTheEagle’s Frostbite scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts), which apparently got the job done. A total of 87.2 GB got dumped, out of the 47.3 GB the game has, specifically:
chunks=164,772 Files
ebx=182,538 Files
res=96,458 Files

I understand the chunks dumped using this script are not named in a way that is compatible with the morph tools, so I followed [mono24’s explanations here to rename the files](https://forum.xentax.com/viewtopic.php?p=181740#p181740) in the two chunks folders that were dumped, using the suggested Regular Expression software (Renamer).

2) Using the Fb_MEA_morph.exe tool

I created a new folder in the bundles folder and placed there the following assets in an attempt to get Suvi’s head morph:
a) Fb_MEA_morph.exe (of course!);
b) bhmf_skeleton.ebx (<- human female skeleton, found in \MEA_dump\bundles\ebx\game\characters\_skeletons);
c) hmf_suvi_morphstatic.res (<- this seems to be the only file that could store Suvi’s morph that was dumped, found in \MEA_dump\bundles\res\game\characters\appearance\heads\global);
d) hmf_head_cora_skinned_mesh.res (<- supposedly the base mesh for Suvi’s morph, found in \MEA_dump\bundles\res\game\characters\human\hmf\0_heads\hmf_head_cora).

Regarding d) above, I did not have the slightest idea of the base mesh to use. While DA:I simply has a base mesh for each race/gender used by 99% of the morph files, it looks like the morph system as implemented in ME:A is a bit more complicated. After looking with FrostyEditor at the resource named “headitem_suvi_morph” under game\characters\appearance\heads\global I decided to give hmf_head_cora_skinned_mesh.res a try, simply because there is a pointer to a “Dynamic Morph” resource named “hmf_head_cora_37yr_dm” which FrostyEditor shows to be in the same folder as hmf_head_cora_skinned_mesh. However, none of the "Dynamic Morph" resource types seem to have been dumped.

BTW, the above “headitem_suvi_morph” resource was not dumped as well and that’s when I noted that several subfolders under game\characters\appearance\heads were also not dumped, in addition to all resources of the type “DynamicMorphHeadData” found in several of the folders under game\characters\human\hmf\0_heads.

With the above resources a) to d) in the folder, I ran the tool with the following command line:

```
Fb_MEA_morph.exe hmf_head_cora_skinned_mesh.res bhmf_skeleton.ebx hmf_suvi_morphstatic.res
```


The result was the following files:

```
hmf_head_cora_skinned_mesh.smd 
hmf_head_cora_skinned_mesh_ani.smd 
```


My suspicions that something went wrong increased, because when I used the morph tool for DAI the three output files had the same name as the morph file (e.g. “hf_adamant_clarel.ascii”, etc) and not that of the base mesh as in this case.

Anyway, I imported hmf_head_cora_skinned_mesh.ascii in Blender and sure enough I got a head mesh with a skeleton:

[](https://ibb.co/4mqV7kq)

Went on with the process and deleted the skeleton, imported hmf_head_cora_skinned_mesh_ani.smd as “Make New Armature”, rotated the imported skeleton 90 degrees to match the mesh, parented all the mesh parts to the imported skeleton, and applied the second frame of the animation to hopefully fix the face. Alas, the face remained pretty much distorted (if not more):

[](https://ibb.co/7vsDXkK)

Any ideas on how to get this to work, please? Maybe the whole problem lies in the dumper script I used? If so, it would be some great help if you can point me in the direction of the correct script to dump ME:A and/or explain if I need to tweak either of the swbf2full or fb3dump scripts to properly dump ME:A.

On the other hand, it is entirely possible that I fed Fb_MEA_morph.exe the wrong resources, in particular I am really unsure that I have used the correct base mesh file. Here too, some input would be particularly useful of anyone has successfully used the MEA morph tool.

Thanks for reading through all this and thanks in advance for any help!
## Post #762
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-30T18:51:34+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Berserker79 ↑Thu Jun 29, 2023 5:13 pm at Thu Jun 29, 2023 5:13 pm
>
> ...Also, I tried to use UFBE 0.2.1 for good measure, but got an error right away once I hit “scan bundles”...
Although at this very moment i do not remember anything at all from the process that was made long time ago, i know for a fact that current posted UFBE does not support MEA, Nicknine's script does not support metadata either up on extraction of the resources that is needed for conversion with daemon's tools for either of the Frostbite games, so all and all i cant figure out based on what you described what could be wrong, yet looking at the *.res extension of your assets that's wrong to begin with.

PS. Thank you for taking the time to post a detailed explanation of your whole process and how it all progressed, if all users would follow such template, things would move along quite faster and get proper responses too and not be totally ignored.
## Post #763
- Username: Berserker79
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 31, 2019 12:50 am
- Post datetime: 2023-07-02T07:59:15+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Jul 01, 2023 2:51 am at Sat Jul 01, 2023 2:51 am
>
> 
Although at this very moment i do not remember anything at all from the process that was made long time ago, i know for a fact that current posted UFBE does not support MEA, Nicknine's script does not support metadata either up on extraction of the resources that is needed for conversion with daemon's tools for either of the Frostbite games, so all and all i cant figure out based on what you described what could be wrong, yet looking at the *.res extension of your assets that's wrong to begin with.

Thanks for your reply mono24. 

Based on the above, at this stage my best option seems that of doing another dump of MEA using a different dumper script, rather than Nicknine's script, and re-try all over again to use the morph tools. I realize that the whole process dates to quite a few years back, but do you remember by any chance which of daemon's dumper scripts supports MEA and if I need to edit something else other than the bf4Directory=r“[gamepath]” and outputfolder=“[outputfolderpath]” lines to get it to work? Thanks!
## Post #764
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-02T14:31:35+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

A made new experimental tools for frostbite game maps, that supports Decima DMF format. 
Here is a video of example level [https://youtu.be/aSYs-iiKw34](https://youtu.be/aSYs-iiKw34)
## Post #765
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-02T16:04:39+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Berserker79 ↑Sun Jul 02, 2023 3:59 pm at Sun Jul 02, 2023 3:59 pm
>
> 
which of daemon's dumper scripts supports MEA
use UFBE. Found its logs from 2019, and i see i used it to dump faces, including Suvi.
I dont remember how morph tool worked for her specifically.
## Post #766
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-07-02T16:10:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Berserker79 ↑Sun Jul 02, 2023 3:59 pm at Sun Jul 02, 2023 3:59 pm
>
> ...but do you remember by any chance which of daemon's dumper scripts supports MEA...
Besides Nicknine's python scripts, there is no legacy python script modified by daemon or anywhere else for that matter that supports MEA, so don't try to look for something that does not exist, i used UFBE, for extraction, the SWBF2 option, you first select the game option then scan bundles, cas/cat then chunks, and you can begin extraction, make sure you tick to create folders or you'll have a mess.
## Post #767
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-02T17:01:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

New experimental tools for frostbite game maps, that supports Decima DMF format. Blender add-on for importing the converted DMF map files is located here: [https://github.com/REDxEYE/decima-dmf](https://github.com/REDxEYE/decima-dmf)

Games supported: Anthem, NFS the Run, SWBF2.

In order to take advantage of all optimizations made, and fast import speeds, Blender 3.5.x and up is highly recommended. Loading time can be 10 times longer or even more if you use older version of blender



Usage has remained the same (see corresponding posts for each game):
Just instead of main tool for map export, use these new ones, and instead of .ASCII export it will generate .DMF

NFS the Run
[viewtopic.php?p=182151#p182151](https://forum.xentax.com/viewtopic.php?p=182151#p182151)

SWBF2
[viewtopic.php?p=186213#p186213](https://forum.xentax.com/viewtopic.php?p=186213#p186213)

Anthem
[viewtopic.php?p=186508#p186508](https://forum.xentax.com/viewtopic.php?p=186508#p186508)

The new format allows for very fast loading times and small file sizes
For example, the Deathstar MP level on the screen above is loading in 5-10 seconds and export is 55mb in size.

Instances support for objects and materials:
each object is exported once as a master object, and instances are based on each master object,
every single master object is located at the center 0,0,0 and hidden by default upon import,
in order to edit/modify/replace/etc a individual object un-hide that object that is located at 0,0,0 and once you make any changes the instances of that object will follow every change made,
once a master object is selected for editing, in the material properties you will see the actual material name of that mesh/sub-mesh it has
[frostbite_maps_dmf.7z](https://xentaxbackup.github.io/file/24014_frostbite_maps_dmf.7z)
## Post #768
- Username: Berserker79
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 31, 2019 12:50 am
- Post datetime: 2023-07-03T20:20:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Mon Jul 03, 2023 12:04 am at Mon Jul 03, 2023 12:04 am
>
> 
use UFBE. Found its logs from 2019, and i see i used it to dump faces, including Suvi.
I dont remember how morph tool worked for her specifically.

Thanks daemon, that's good to know I should use UFBE for dumping. I'll figure out how to use the morph tool to work with Suvi's morph once I get the game properly dumped (BTW, I'll take this chance also to thank you for all these tools, really appreciate your efforts!)

> Reply from mono24 ↑Mon Jul 03, 2023 12:10 am at Mon Jul 03, 2023 12:10 am
>
> 
... i used UFBE, for extraction, the SWBF2 option, you first select the game option then scan bundles, cas/cat then chunks, and you can begin extraction, make sure you tick to create folders or you'll have a mess.

@mono24
Have to admit that I'm a little confused, since both you and daemon say to use UFBE for dumping MEA, but in your earlier reply you wrote that:

> Reply from mono24 ↑Sat Jul 01, 2023 2:51 am at Sat Jul 01, 2023 2:51 am
>
> 
... i know for a fact that current posted UFBE does not support MEA...

Am I correct to think that it is only the currently posted version of UFBE that does not support MEA, but the older version will do? Anyway, going to give the older version a try once I'm working again with the computer where I have already installed the game and report back the result. In the meantime, thank you again for your assistance.
## Post #769
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-03T21:09:12+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Berserker79 ↑Tue Jul 04, 2023 4:20 am at Tue Jul 04, 2023 4:20 am
>
> 
Am I correct to think that it is only the currently posted version of UFBE that does not support MEA, but the older version will do?
No, use latest version. Also it seems MEA toc files must be decrypted first before using UFBE.
## Post #770
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-07-04T01:14:56+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Berserker79 ↑Tue Jul 04, 2023 4:20 am at Tue Jul 04, 2023 4:20 am
>
> ...Have to admit that I'm a little confused, since both you and daemon say to use UFBE for dumping MEA...
Yes indeed i remember clearly when i tested it it was NOT working, for me personally, i have tested many things like you at the time, including trying to edit old legacy scripts, which now that i think about it one old legacy python script in particular worked after some edits, but as i said, this is years ago, i lost track on far too many things.

Anyway, since now the dead Zenhax forum no longer exists,
[the following post by NoFaTe](https://web.archive.org/web/20220310025846/https://zenhax.com/viewtopic.php?p=17974#p17974) which posted an updated script for Fifa 17 at the time, i used it for MEA, its one of the legacy script which Nickine's scripts are based off where he updated to support many more games on his GitHub repo.

[this is what you need to decrypt the TOCs](https://web.archive.org/web/20220310005532/https://zenhax.com/viewtopic.php?p=21957#p21957), otherwise you'll get stuck again, assuming you'll attempt in re-dumping the game using UFBE.

PS: This is the note i came across once again in my old PC which i forgot about where i had tested the following, so yeah, its been a looooong time.

```

BF1 option selected extracts following games:
	Battlefield 1 Incursions Alpha PC
	Battlefield 1 PC/PS4
	Mirror's Edge Catalyst PC/PS4

SWBF1 option selected extracts following games:
	STAR WARS Battlefront

SWBFII option selected extracts following games:
	STAR WARS Battlefront II old format before the change to new format, both PC/PS4.
	Mass Effect Andromeda PC/PS4
	Madden NFL 18 PS4
	Madden NFL 19 PC, PS4 NOT TESTED
	Need for Speed Payback PC/PS4
```
## Post #771
- Username: Berserker79
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 31, 2019 12:50 am
- Post datetime: 2023-07-05T17:28:27+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from daemon1 ↑Tue Jul 04, 2023 5:09 am at Tue Jul 04, 2023 5:09 am
>
> 
No, use latest version. Also it seems MEA toc files must be decrypted first before using UFBE.

Got it, thanks!

> Reply from mono24 ↑Tue Jul 04, 2023 9:14 am at Tue Jul 04, 2023 9:14 am
>
> 
Yes indeed i remember clearly when i tested it it was NOT working, for me personally, i have tested many things like you at the time, including trying to edit old legacy scripts, which now that i think about it one old legacy python script in particular worked after some edits, but as i said, this is years ago, i lost track on far too many things.

That explains it all and I totally understand the problem: unless I take decent notes of what I did for a specific game, chances are that I'll forget about that in a few years. Anyway, I'm working to decrypt the .toc files and then I'll try re-dumping the game with the latest UFBE. Maybe this time I'll manage to properly dump the game, can't say whether the previous attempts with UFBE failed b/c I didn't have decrypted TOCs or because I did something as dumb as pointing UFBE to the wrong folder...  

> Reply from mono24 ↑Tue Jul 04, 2023 9:14 am at Tue Jul 04, 2023 9:14 am
>
> 
this is what you need to decrypt the TOCs, otherwise you'll get stuck again, assuming you'll attempt in re-dumping the game using UFBE.

Thanks so much for this, might have taken me ages to find it! I'll give UFBE another shot and if that fails again I'll see whether I have better luck with that NoFaTe's script you have linked above (BTW, thanks for that too!).

> Reply from mono24 ↑Tue Jul 04, 2023 9:14 am at Tue Jul 04, 2023 9:14 am
>
> 
PS: This is the note i came across once again in my old PC which i forgot about where i had tested the following, so yeah, its been a looooong time.

Yep, I'm bit a late to the party... Back when tools were released by daemon I was content enough to work only with DAI, then all these years later I somehow got the urge to work on MEA.
## Post #772
- Username: Berserker79
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 31, 2019 12:50 am
- Post datetime: 2023-07-08T14:58:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Ok, finally had the time to (re-)dump MEA using UFBE and take another try at using the MEA morph tool (Fb_MEA_morph.exe). 

So, the good news is that - after decrypting the TOCs - I managed to do a full (as far as I can tell) extraction of MEA with UFBE using the SWBF2 option. The bad news is that when I run the morph tool the result is exactly the same obtained when I had used NickNine's script for dumping.   

Details of the process are as follows:

1) Game dump

First thing I did a batch decrypt of all the TOCs in the various folders of the MEA installation directory using the MEATOCDecrypt tool. I think only the TOCs in the "Data" folder were actually required to be decrypted in order to use UFBE for dumping, but for good measure I decrypted all of them, including those in the "Patch" folder. A total of 217 .toc files was thus converted to 217 corresponding .toc_decrypt files. I used [Renamer](https://www.den4b.com/products/renamer) to replace the extension of the original (encrypted) .toc files to .toc_bak and then the (decrypted) .toc_decrypt to .toc.

Next, in UFBE selected the SWBF2 option, selected the MEA 'Data' folder as the 'game folder' and 'Temp/MEA_dump' as the 'dump folder.' Then, pressed scan bundles, scan CAS/CAT and check chunks. Ticked all the boxes and then pressed 'Dump!'. On a first attempt, the dump halted shortly thereafter having extracted about 130 Mb of data with UFBE throwing a .NET 4.5 error complaining about too long file paths. I restarted UFBE, changed my 'dump folder' to 'D:\MEAd', made sure all tick boxes were selected and pressed 'Dump!' again: this time the dump was completed without UFBE throwing any errors. This is what the UFBE window looked like after the dump process was completed:

[](https://ibb.co/D72ymCS)

I seem to recall from previous posts in this thread that it's normal to see some ~20k files fail to extract "because of chunk not found", so I think that's not an issue peculiar to my dump of MEA.

2) Using the Fb_MEA_morph.exe tool

I tried once again to work with Suvi's head morph, so I went looking all over again for the necessary files. According to mon24's tutorial at page 28 of this thread, morph tools for DAI/MEA need the following assets to work: meshset, skeleton, morphresource.

Locating the skeleton was no trouble, bhmf_skeleton.ebx is found under "bundles" in "game\characters\_skeletons".

The only location where the game seems to store what look like morph file(s) for Suvi is under the bundles folder, specifically in "game\characters\appearance\heads\global" and these are all the files I found there referencing Suvi:

```
hmf_suvi_hair_morphstatic a0cf0000.EB228507
headitem_suvi_morph.ebx
headitem_suvi_morph_d9da39b4-55a1-a9e4-ca05-051f4b526070_headvariation.ebx
hmf_suvi_hair_morphstatic.ebx
hmf_suvi_morphstatic.ebx

```


Worked on the assumption that hmf_suvi_morphstatic a0c70300.EB228507 is the MorphResource file, since all other files are EBX or contain "hair" in the filename. I took a look at each of these files (except those with "hair" in the filename) with a HEX editor, to see if they contained any clue about the MeshSet, but found nothing.

As I mentioned in my earlier post of several days ago, the only clue about the MeshSet was found by opening "headitem_suvi_morph.ebx" in FrostyEditor, which points to a resource named "hmf_head_cora_37yr_dm", but there is no .MeshSet file with that name in the dump, only a .ebx file that I found under "bundles" in "game\characters\human\hmf\0_heads\hmf_head_cora". The only .MeshSet found in that same folder is "hmf_head_cora_skinned_mesh b02f0000.MeshSet".

Tried using Fb_MEA_morph.exe with hmf_head_cora_37yr_dm.ebx as base mesh, running the following command and fully expecting it not to work:

```
Fb_MEA_morph.exe hmf_head_cora_37yr_dm.ebx bhmf_skeleton.ebx "hmf_suvi_morphstatic a0c70300.EB228507"
```


As expected, the morph tool returned an error, specifically:

```
Cannot find raw geometry. Missing metadata.
```


Next, tried using using Fb_MEA_morph.exe with hmf_head_cora_skinned_mesh b02f0000.MeshSet as the base mesh:

```
Fb_MEA_morph.exe "hmf_head_cora_skinned_mesh b02f0000.MeshSet" bhmf_skeleton.ebx "hmf_suvi_morphstatic a0c70300.EB228507"
```


This time the morph tool reported

```
.....done.
```


and the output were the same three files I obtained during my earlier attempt when I dumped the game with NickNine's script, i.e. 

```
hmf_head_cora_skinned_mesh.smd 
hmf_head_cora_skinned_mesh_ani.smd 

```


Moved to Blender, imported hmf_head_cora_skinned_mesh.ascii, deleted the skeleton, imported hmf_head_cora_skinned_mesh_ani.smd as “Make New Armature”, rotated the imported skeleton 90 degrees to match the mesh, parented all the mesh parts to the imported skeleton, applied the second frame of the animation and... Same result as the previous attempt, i.e. the head gets even more distorted.

At that point I suspected that the problem could be Suvi's headmorph, so I tried working with other characters, but hit again a wall. I could not find a MorphResource for any of the squad members (e.g. Cora, Liam, Peebee, etc.) and those characters that had a "xxxxxxxx_morphstatic a0c70300.EB228507" file (which I assume is a MorphResource) don't seem to have a base mesh to work with. For example there is one of those files with the extension a0c70300.EB228507 for the salarian female pathfinder, but I can't find any MeshSet file for female salarian characters. 

At this time, my conclusion could any of the following:
1) The file "hmf_suvi_morphstatic a0c70300.EB228507" is not a MorphResource
or
2) The Fb_MEA_morph.exe tool works differently from the corresponding tool for DAI, e.g. maybe it requires some additional assets?
or
3) The way morphs are implemented in MEA is different/more complicated - at least for some characters like Suvi - than DAI.

Whatever the case, for the time being it seems like I'm stuck. If anyone has suggestions/ideas, I'm more than happy to make another attempt to get the tool to work. Also, I suppose it should not be much trouble providing a sample of e.g. "hmf_suvi_morphstatic a0c70300.EB228507" if anyone knows what to look for inside this file and determine if this is a proper MorphResource or not.
## Post #773
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-07-09T00:05:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Berserker79 ↑Sat Jul 08, 2023 10:58 pm at Sat Jul 08, 2023 10:58 pm
>
> ..."hmf_suvi_morphstatic a0c70300.EB228507" if anyone knows what to look for inside this file and determine if this is a proper MorphResource or not.
Yes that is a correct asset, you are using the old text with missing types at the time, any of the later extraction/dump tools few pages back include a updated text with the required extensions for those CRC32 HASH's you see now as extension.

And reading some posts from the past, i am slowly remembering some things about the MEA having something more complex going on than DAI, MEA female face fixes have problems of some sort, if you test anything else other than the human females you should see it will work just for the sake of the whole process and the time you spent thus far, and with anything else in this matter i think daemon will be more indicated to help further, because from everything you wrote in detail you did everything correct  once again thank you for taking the time to describe every step and what you did in order to get some sort of resolution.
## Post #774
- Username: Berserker79
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 31, 2019 12:50 am
- Post datetime: 2023-07-16T10:26:48+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sun Jul 09, 2023 8:05 am at Sun Jul 09, 2023 8:05 am
>
> 
And reading some posts from the past, i am slowly remembering some things about the MEA having something more complex going on than DAI, MEA female face fixes have problems of some sort, if you test anything else other than the human females you should see it will work just for the sake of the whole process and the time you spent thus far

Success! I took up your suggestion to test other characters and can confirm that the MEA morph tool works when the proper assets are used as input. After a successful test with a human male character I realized that the problem I had with Suvi's morph had actually to do with using a MeshSet which was not what the game uses as base mesh, so the tool works on Suvi's mesh if using the correct base mesh. Here's a quick Blender Eevee render I've done of Suvi (left) next to a screenshot from the game (right): the lighting and camera angle are not exactly the same, but as far as can tell the model's geometry is 100% correct.

[](https://ibb.co/NYWcNby)

For future reference, in case anyone else is interested, the tool will work with MEA "morphstatic" files like the one for Suvi mentioned in my previous post and the MeshSet to use as base mesh is (according to gender and species) one of those labelled as "universal" and found in the "morphtarget" subfolders (see below). The third resource required is of course the skeleton (location specified in one of my previous posts above).

The "universal" MeshSet files for use as base mesh that I came across so far are the following:

```
\bundles\game\characters\human\hmm\0_heads\hmm_head_universal\morphtargets\hmm_mb_universal_mesh c02a0000.MeshSet <-base head mesh for human males

```


I'm not even sure there are base head mesh files for other races. Only a limited number of characters in MEA appears to use "morphstatic" files (all humans as far as I can tell) and most of these are minor NPCs, Suvi and a few others (e.g. Addison and Sloane) are probably the most notable exceptions. All companions, basically all asari and many of the more prominent NPCs seem to use a different type of morph system, so I'd say that confirms MEA has something more complex going on than DAI.

> Reply from mono24 ↑Sun Jul 09, 2023 8:05 am at Sun Jul 09, 2023 8:05 am
>
> 
with anything else in this matter i think daemon will be more indicated to help further,

Having managed to get the morph tool working, I suppose there is no need to distract daemon from the work on newer tools and more recent games.   

However, this seems like a good spot to mention that the output files generated by Fb_MEA_morph.exe have the same name as the MeshSet used as base mesh rather than the same name as the MorphResource file, which makes life a little difficult if one wishes to do all morphs in a batch. In fact, I'm afraid the tool will simply overwrite the previously generated files when processing the next morph that uses the same MeshSet. I realize this is a minor issue, but maybe fixing this problem is something quick that can be done without taking away much time? 

> Reply from mono24 ↑Sun Jul 09, 2023 8:05 am at Sun Jul 09, 2023 8:05 am
>
> 
once again thank you for taking the time to describe every step and what you did in order to get some sort of resolution.

No problem, guess this is the least one can do when looking for help. Thank you (and daemon) so much for your assistance and for bearing with me across these several posts!
## Post #775
- Username: Gobyl
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 29, 2022 1:01 pm
- Post datetime: 2023-07-30T06:19:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Is it dump BFV with UFBE?  I tried it but it doesn't scan any bundles. Is there any other way?
## Post #776
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-07-30T23:39:07+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Gobyl ↑Sun Jul 30, 2023 2:19 pm at Sun Jul 30, 2023 2:19 pm
>
> 
Is it dump BFV with UFBE?  I tried it but it doesn't scan any bundles. Is there any other way?
UFBE does NOT work with the three mentioned games below.

When comes about the 3 Frostbite games that share same format after SWBF2 changed the way assets are stored in only CAS/CAT archives and no longer SB/TOC bundles.

Which ever option you use, the following three games can be dumped:
Star Wars Battlefront II 2017
Battlefield V 2018 (if i am not mistaken some problems occur though with daemon's tool for BFV)
Star Wars Squadrons 2020
You can either use GalaxyMan2015 (former lead dev of The Frosty Tool Suite project) python script: [viewtopic.php?p=146986#p146986](https://forum.xentax.com/viewtopic.php?p=146986#p146986)
Or a more updated c# dumper by daemon1 that does not export duplicated textures located at: [viewtopic.php?p=186213#p186213](https://forum.xentax.com/viewtopic.php?p=186213#p186213)
## Post #777
- Username: Gobyl
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 29, 2022 1:01 pm
- Post datetime: 2023-07-31T17:44:50+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Thanks a lot, But how about converting the MeshSet and the Texture files?
## Post #778
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-07-31T18:43:06+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Gobyl ↑Tue Aug 01, 2023 1:44 am at Tue Aug 01, 2023 1:44 am
>
> ...how about converting the MeshSet and the Texture files?
BFV mesh tool is posted somewhere here on this thread, look it up, its posted by daemon1 in one of his posts along side other tools if i remember correctly i cant remember where, for textures only thing i can suggest at the moment is Frosty Tool Suite.
## Post #779
- Username: Gobyl
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 29, 2022 1:01 pm
- Post datetime: 2023-08-01T11:34:10+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Alright right now the problem I have with the BF5 mesh tool is that it will create the smd file but it won't create the ascii file, any solution to that?
## Post #780
- Username: Nickisdedguy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 10, 2022 3:44 am
- Post datetime: 2023-08-01T17:03:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

hello, I ported the model from the bf2042 to blender and for some reason my model broke the mesh and it can not be substituted for the texture



hgfdyehgkjgrdf.jpg (190 KiB) Viewed 80 times
## Post #781
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-08-01T20:08:08+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Gobyl ↑Tue Aug 01, 2023 7:34 pm at Tue Aug 01, 2023 7:34 pm
>
> 
Alright right now the problem I have with the BF5 mesh tool is that it will create the smd file but it won't create the ascii file, any solution to that?
In order to get help with that, one must know your steps performed, and what output your cmd window had during conversion, i can not guess the problem you are facing and what caused it.
## Post #782
- Username: Gobyl
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 29, 2022 1:01 pm
- Post datetime: 2023-08-03T06:44:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Wed Aug 02, 2023 4:08 am at Wed Aug 02, 2023 4:08 am
>
> 
Gobyl wrote: ↑Tue Aug 01, 2023 7:34 pm
Alright right now the problem I have with the BF5 mesh tool is that it will create the smd file but it won't create the ascii file, any solution to that?

In order to get help with that, one must know your steps performed, and what output your cmd window had during conversion, i can not guess the problem you are facing and what caused it.

As for the steps, do it according to the steps provided by the tutorials, I dumped the game step by step, then put the chunks folder in the same folder as the BF5 Mesh tool, the meshset which in this case a weapon model, and the skeleton.

As for the output its seems the tools cannot find the skeleton file
## Post #783
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-08-04T23:23:02+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Please don't quote posts with in posts too, learn to edit them to keep things clean.

> Reply from Gobyl ↑Thu Aug 03, 2023 2:44 pm at Thu Aug 03, 2023 2:44 pm
>
> ...then put the chunks folder in the same folder as the BF5 Mesh tool...
Who told you to move the chunks folder? That's a big nono, the extracted folder structure must be intact.
And the reason it cant find the required files is that you are using the wrong syntax it seems, you didn't even posted what is your doing that made you get that error.
## Post #784
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-08-05T17:32:53+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

When I try to scan CAS files I got an error saying:

> Unable to read beyond the end of the stream.

> Offset and length were out of bounds for the array or count is greater than the number of elements from index  to the of the source collection.

```
System.IO.EndOfStreamException: Unable to read beyond the end of the stream.
   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadUInt64()
   at UFBE.Form1.bScanCAS_Click(Object sender, EventArgs e)
   at System.Windows.Forms.Control.OnClick(EventArgs e)
   at System.Windows.Forms.Button.OnMouseUp(MouseEventArgs mevent)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ButtonBase.WndProc(Message& m)
   at System.Windows.Forms.Button.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)
```


Are there ways to fix this error?
## Post #785
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-08-05T18:38:01+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mrmaller1905 ↑Sun Aug 06, 2023 1:32 am at Sun Aug 06, 2023 1:32 am
>
> 
When I try to scan CAS files I got an error saying:
...
Are there ways to fix this error?
How do you expect help with such a post with out proper details?
## Post #786
- Username: Gobyl
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 29, 2022 1:01 pm
- Post datetime: 2023-08-09T17:44:29+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Aug 05, 2023 7:23 am at Sat Aug 05, 2023 7:23 am
>
> 
Please don't quote posts with in posts too, learn to edit them to keep things clean.
Gobyl wrote: ↑Thu Aug 03, 2023 2:44 pm...then put the chunks folder in the same folder as the BF5 Mesh tool...
Who told you to move the chunks folder? That's a big nono, the extracted folder structure must be intact.
And the reason it cant find the required files is that you are using the wrong syntax it seems, you didn't even posted what is your doing that made you get that error.

I re-dump the game files and let the chunks folder be in the same place by default and still no result.
this is the message i got
## Post #787
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-08-09T18:29:09+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Gobyl ↑Thu Aug 10, 2023 1:44 am at Thu Aug 10, 2023 1:44 am
>
> I re-dump the game files and let the chunks folder be in the same place by default and still no result.

That still does not explain what you did in figuring out why you got that error.
Your syntax must be wrong, because all tools work accordingly.

And do not quote the whole post with in a post, edit it.
## Post #788
- Username: Gobyl
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 29, 2022 1:01 pm
- Post datetime: 2023-08-11T07:29:12+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Thu Aug 10, 2023 2:29 am at Thu Aug 10, 2023 2:29 am
>
> 

That still does not explain what you did in figuring out why you got that error.
Your syntax must be wrong, because all tools work accordingly.

And do not quote the whole post with in a post, edit it.

I just drag the meshset file to the Fb_BF5_mesh tools. 

Could the version of the game impact this?
## Post #789
- Username: Ultra Phoenix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 18, 2023 5:32 am
- Post datetime: 2023-08-17T21:37:26+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Hello, may i have The Run Italian Pack car models?
## Post #790
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-08-18T18:18:42+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from Ultra Phoenix ↑Fri Aug 18, 2023 5:37 am at Fri Aug 18, 2023 5:37 am
>
> Hello, may i have The Run Italian Pack car models?
Hello, can you go back and edit your post? You didn't have to quote the WHOLE thing, making a mess.
## Post #791
- Username: Ultra Phoenix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 18, 2023 5:32 am
- Post datetime: 2023-08-19T23:56:16+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Aug 19, 2023 2:18 am at Sat Aug 19, 2023 2:18 am
>
> 
Ultra Phoenix wrote: ↑Fri Aug 18, 2023 5:37 amHello, may i have The Run Italian Pack car models?
Hello, can you go back and edit your post? You didn't have to quote the WHOLE thing, making a mess.

Sorry. My bad.
## Post #792
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2023-09-06T12:51:25+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Okay, I am not sure what is going on, but all I am getting from toc_heat.exe is

```
Parameter name: startIndex
   at System.ThrowHelper.ThrowArgumentOutOfRangeException(ExceptionArgument argument, ExceptionResource resource)
   at System.BitConverter.ToInt32(Byte[] value, Int32 startIndex)
   at toctest.BinaryReaderBE.ReadInt32()
   at toctest.toctest.Main(String[] args)

```


Trying to extract Need for Speed Unbound, running on Windows 11 22H2.1485.
I ran toc_heat.exe from CMD as follows:

```
toc_heat.exe E:\u\Data\layout.toc
```

EDIT: I also tried drag & dropping layout.toc, a CMD window opens and closes without any output files.

Here is ufbe.ini:

```
D:\Dump\Unbound
ebx res chunks

```


I read the Unbound post ([viewtopic.php?p=188489#p188489](https://forum.xentax.com/viewtopic.php?p=188489#p188489)), the Heat post ([viewtopic.php?p=181813#p181813](https://forum.xentax.com/viewtopic.php?p=181813#p181813)) and the Battlefield 2042 post ([viewtopic.php?p=181685#p181685](https://forum.xentax.com/viewtopic.php?p=181685#p181685)) multiple times, each of them, and followed the instructions as best as I could.

I tried changing the folder paths in ufbe.ini multiple times. I tried placing oo2core_8_win64.dll into the running directory of the executable, into the \Data\ directory of the game and into the \Dump\ folder. None worked.
I used Process Monitor to see what the program is doing and saw it is also searching for toc_heat.ini and toc_heat.exe.Local. Created both, but nothing changed, same errors. It is interesting that Process Monitor reports that toc_heat.exe is not even searching for oo2core_8_win64.dll anywhere.

Any help?
## Post #793
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-09-06T15:18:46+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from antoniu200 ↑Wed Sep 06, 2023 8:51 pm at Wed Sep 06, 2023 8:51 pm
>
> 
Okay, I am not sure what is going on, but all I am getting from toc_heat.exe is
you're using wrong tools. Use bf2042 tools.
## Post #794
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2023-09-06T19:32:38+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

Tried that before, I get the same result:

```
Parameter name: startIndex
   at System.ThrowHelper.ThrowArgumentOutOfRangeException(ExceptionArgument argument, ExceptionResource resource)
   at System.BitConverter.ToInt32(Byte[] value, Int32 startIndex)
   at toctest.BinaryReaderBE.ReadInt32()
   at toctest.toctest.Main(String[] args)

```


Command used:

```
toc2042.exe E:\u\Data\layout.toc
```


oo2core_8_win64.dll is both in toc2042 running directory and file source directory.
Using the same ufbe.ini as for toc_heat.

EDIT: Has anybody here tried running this program in Windows 11 22H2?
## Post #795
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-09-07T19:31:40+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from antoniu200 ↑Thu Sep 07, 2023 3:32 am at Thu Sep 07, 2023 3:32 am
>
> ...Command used:
Code: Select alltoc2042.exe E:\u\Data\layout.toc...
Wrong syntax, if you are plannig on using a batch you do NOT point it to the layout.toc and that's it, it will crass as you see above in your posted error, the tool will read it but there's nothing to extract from it, only the other TOCs the game has you can extract, while making sure your INI file has correct paths.
## Post #796
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2023-09-08T23:10:41+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Fri Sep 08, 2023 3:31 am at Fri Sep 08, 2023 3:31 am
>
> 
Wrong syntax, if you are plannig on using a batch you do NOT point it to the layout.toc [...] there's nothing to extract from it, only the other TOCs the game has you can extract...

Worked, thank you!

Now I have another problem   
fb3decoder is not extracting any sound files from Unbound for me. I have XAS1, EALayer3 and EASpeex present, IDLE opened in Python 2.7.15 32-bit, however the script just cycles through all .ebx files extracted using toc2042 (as reported in Process Monitor) and absolutely nothing is output, neither in Python console, nor as files on storage media, except for messages confirming the dependecies are present:

```
EASpeex dll detected.
EALayer3 tool detected.
```


And that's all. Absolutely no activity from target disk while script is running, only from dump disk. Strangely, activity is both write and read, as reported in Task Manager.

```
targetDirectory = r"E:\Dump\Unbound"


#These paths are relative to the dumpDirectory. They don't need to be changed.
ebxFolder    = r"bundles" 
chunkFolder  = r"chunks"
chunkFolder2 = r"chunks"
```
## Post #797
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-09-09T15:58:21+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from antoniu200 ↑Sat Sep 09, 2023 7:10 am at Sat Sep 09, 2023 7:10 am
>
> ...fb3decoder is not extracting any sound files from Unbound for me...
Your assets are already extracted, that decoder only decodes/converts audios, but not for these new games though, the EBX format is unsupported, there is no other way besides maybe the Frosty software.

And even so, i would NOT recommend that obsolete option we all used when there's a better/proper way to extract all sounds from Frostbite games in native format using Nickine's scripts, yet his scripts do NOT support new games from 2018 and up either, so try and use Frosty.
## Post #798
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2023-09-09T21:40:11+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from mono24 ↑Sat Sep 09, 2023 11:58 pm at Sat Sep 09, 2023 11:58 pm
>
> 
that decoder only decodes/converts audios, but not for these new games though, the EBX format is unsupported

Oh, unfortunate, but good to know.

> Reply from mono24 ↑Sat Sep 09, 2023 11:58 pm at Sat Sep 09, 2023 11:58 pm
>
> 
And even so, i would NOT recommend that obsolete option we all used when there's a better/proper way to extract all sounds from Frostbite games in native format using Nickine's scripts, yet his scripts do NOT support new games from 2018 and up either, so try and use Frosty.

Yeah, I have used Nicknine's scripts successfully for older Frostbite games, but, as you and he mentioned, they don't work anymore. Worst part is they are not compatible with toc2042's style of EBX, so not even with the assets extracted can his scripts help.

I did use Frosty to identify audio chunks, but what I exported are files that contains multiple (110 each?) EALayer3 files one after the other, with no padding before, between or after them. The files start with hex "48 00 00 0C 16 04 BB 80 40", foobar2000 with vgmstream opens them if I use the extension .sps, but only identifies one track.
If I try to export them manually, selecting in HxD from "H" to the next "H", the audio files are properly openable by foobar2000, but with at least 300 files that need to be exported, this is absolutely not doable. I would need a script, and I have no...

Wait... I have C++ knowledge.
Whatever, I am an idiot. I think I figured out what I need to do, thanks!
## Post #799
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-09-10T19:48:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

> Reply from antoniu200 ↑Sun Sep 10, 2023 5:40 am at Sun Sep 10, 2023 5:40 am
>
> ...Wait... I have C++ knowledge.
Whatever, I am an idiot. I think I figured out what I need to do, thanks!
If you don't feel like coding yourself, this is means to an end in mean time: [viewtopic.php?p=174498#p174498](https://forum.xentax.com/viewtopic.php?p=174498#p174498)
## Post #800
- Username: kofing1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 08, 2023 9:26 pm
- Post datetime: 2023-09-29T09:33:30+00:00
- Post Title: Re: Frostbite model tools (Battlefield, Battlefront and others)

sorry，I encountered an issue with Anthem. 
output 76g on TOC 
for the step 3, I created meshnames.txt, but dp.dp did not get created., the following steps were not work, and I couldn't get any output from the ebx.
