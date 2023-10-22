## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-25T08:12:50+00:00
- Post Title: Ghostbusters: The Video Game

Ghostbusters: The Video Game skeletal model extraction tools.

Usage: unpack .bfm files from model.pod and .skb files from common.pod
    then drag .bfm file onto the tool.




[Ghostbusters_skelet.rar](https://xentaxbackup.github.io/file/11388_Ghostbusters_skelet.rar)
## Post #2
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-06-25T09:22:13+00:00
- Post Title: Ghostbusters: The Video Game

Incredible! You are amazing!
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-25T14:34:46+00:00
- Post Title: Ghostbusters: The Video Game

First version of the tool. If you save debug output from console, you can see all materials listed. Put the corresponding DDS and it must work. Or just correct it all manually. I was too lazy to put all 8 textures here, so he's a little messed up.
## Post #4
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-06-25T16:59:26+00:00
- Post Title: Ghostbusters: The Video Game

here's what i did:
- using the "Gibbed.Ghostbusters.Unpack.exe" to unpack the .POD files
- grabbed the Ghostbusters_skelet.exe into one of the skeletal folders (...skeletal/ghostbuster for example)
- drag & drop a bfm file onto it
- "filnename.mesh.ascii" has been created

however if i try the "XnaLara Converter" 3dsmax script, i can't open that file. says "undefined in type: float"

may you can tell me what i'm doing wrong here?
the Overwatch .ascii files work like a charm with that 3dsmax script though.
using 3dsmax 2014.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-25T17:05:56+00:00
- Post Title: Ghostbusters: The Video Game

Sorry I forgot to tell how it works. In addition to  W32MODEL.POD, you have to unpack COMMON.POD to get  SKB files too.
## Post #6
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-06-25T17:13:36+00:00
- Post Title: Ghostbusters: The Video Game

hmm. i did that. the common.POD was actually the first one i extracted. i also extracred all of the remaining .POD files into the same folder to have the folder structure intact.
let's take the gb_player for example, stored in ..skeletal/ghostbuster
for that one there's: .bfm .jug .sbs .skb
so it should be all there. am i maybe missing something?
did you used the same tool for unpacking the game files? and also the slightly old xnalara 3dsmax script?

Edit: updating the 3dsmax xnalara converter script didn't help either.
## Post #7
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2016-06-25T18:10:38+00:00
- Post Title: Ghostbusters: The Video Game

Amazing work here!   

However I have the same problem like TheMask85 i used and old version of xnalara script and a new one but i get the same problem.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-25T18:19:29+00:00
- Post Title: Ghostbusters: The Video Game

send me the ASCII file you're getting and I'll try it in blender. I don't have 3dmax.
## Post #9
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-06-25T18:24:29+00:00
- Post Title: Ghostbusters: The Video Game

If anyone can point me in the direction of texture converter that works, I'd greatly appreciate it!
## Post #10
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-06-25T18:25:57+00:00
- Post Title: Ghostbusters: The Video Game

i just tried the blender mesh.ascii script for blender 2.49
that works. well kind of. i can load up the model and export as fbx.
however that fbx file crash any 3d program i try to import (Noesis, C4D, 3DSMax)
[http://www.mediafire.com/download/lzzb4scafh1uyqt](http://www.mediafire.com/download/lzzb4scafh1uyqt)

@trexjones

[viewtopic.php?f=18&t=4392](http://forum.xentax.com/viewtopic.php?f=18&t=4392)

create a bat file and place the bat file, along with the tex2dds.exe
into the art folder. type the following into your bat file:

FOR /F "tokens=*" %%G IN ('dir /b /S *.tex') DO tex2dds.exe "%%G" 

and run it. it'll batch convert all .tex files to .dds files (even in subfolders)
## Post #11
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2016-06-25T19:09:17+00:00
- Post Title: Ghostbusters: The Video Game

All Right opened with Blender and works fine and managed to export the model with the Xnalara/Xps (.ascii/.mesh/.xps) Expoter/Importer

Then Use the Xnalara Importer/Expoter for 3D Max Studio.

Works perfect again thanks men. 
[janine.PNG](https://xentaxbackup.github.io/file/11112_janine.PNG)
## Post #12
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-06-25T19:16:08+00:00
- Post Title: Ghostbusters: The Video Game

i guess that's a workaround.
Janine works by default as exported fbx file though.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-25T19:39:29+00:00
- Post Title: Ghostbusters: The Video Game

i never worked with max scripts. Is there any way we can find on which line that error occurs?
## Post #14
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-06-25T19:50:19+00:00
- Post Title: Ghostbusters: The Video Game

Every time I try to run the texture converter, the .exe file disappears saying this:



tool.JPG (23.32 KiB) Viewed 893 times



Any suggestions?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-26T10:17:35+00:00
- Post Title: Ghostbusters: The Video Game

The only difference in ASCII files here I can think of, is that Ghostbusters use material names with backslashes, like 

weap\proton_pack_light_static
spengler_eyes
spengler
jumpsuit_pack
weap\proton_pack
jumpsuit_gloves
GB_Logo
spengler_hair
gb_lens
gb_hose
weap_goggle_lens

So I put them in xnalara files as they are. May it be a problem?
## Post #16
- Username: IGNOREME
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 16, 2015 1:46 pm
- Post datetime: 2016-06-26T11:53:03+00:00
- Post Title: Re: Ghostbusters: The Video Game

Wow, this is perfect!  I was just about to ask if anyone knew a bfm converter.
Great work!  However, is there another converter to, say, .fbx files?
Awesome job, nonetheless.
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-26T12:03:20+00:00
- Post Title: Re: Ghostbusters: The Video Game

I tried FBX, but this format is too complex in a way how it handles skeletons. Maybe some day I'll be able to export to it, but not now.
## Post #18
- Username: IGNOREME
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 16, 2015 1:46 pm
- Post datetime: 2016-06-26T12:07:42+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from daemon1
>
> I tried FBX, but this format is too complex in a way how it handles skeletons. Maybe some day I'll be able to export to it, but not now.

That's too bad.  Guess I'll just work with .ascii.  Thank you for the converter, again.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-27T19:57:31+00:00
- Post Title: Re: Ghostbusters: The Video Game

Working on getting additional models from PS3 version. I've been told they are only on consoles.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-01T20:26:10+00:00
- Post Title: Re: Ghostbusters: The Video Game

New version for PS3 models.
## Post #21
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-26T21:02:43+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from daemon1
>
> New version for PS3 models.is there any special technique to obtain models out of ps3?
I'm getting this error:



gb_ps3_issue.jpg (129.19 KiB) Viewed 272 times
## Post #22
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2016-07-27T01:17:52+00:00
- Post Title: Re: Ghostbusters: The Video Game

Finally managed to get the ps3 files but just like Tosyk just crash doesn't matter wich file i test.
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-27T05:47:22+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from Tosyk
>
> daemon1 wrote:New version for PS3 models.is there any special technique to obtain models out of ps3?

No, it must work. Send me example files.
## Post #24
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-27T09:20:35+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from daemon1
>
> Tosyk wrote:daemon1 wrote:New version for PS3 models.is there any special technique to obtain models out of ps3?

No, it must work. Send me example files.sure, here:
[http://www.mediafire.com/download/nvkad ... samples.7z](http://www.mediafire.com/download/nvkad8v5ct2y9ae/ghostbusters_ske%3Betal_samples.7z)

every file in this archive causes crash on converting after few seconds of process.
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-27T09:30:29+00:00
- Post Title: Re: Ghostbusters: The Video Game

Some mistake in release. Get the latest version, must work.
## Post #26
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-27T17:55:05+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from daemon1
>
> Some mistake in release. Get the latest version, must work.thanks, they converted now, unfortunately the weights are broken.
I would not bother with ps3 models if not the unique ctaracter models.
[spengler_ps3_error.jpg](https://xentaxbackup.github.io/file/11404_spengler_ps3_error.jpg)
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-27T18:13:02+00:00
- Post Title: Re: Ghostbusters: The Video Game

i'll check that later
## Post #28
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-27T19:57:14+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from daemon1
>
> i'll check that laterthanks in advanced.
btw I noticed that all the models along with their skeleton are fliped by X axis. I can flip it by X in 3d software but it is hard to animate this type of models because of wrong (after their physically fliped) transformations. If you could make this by code in your tool that would be great.
## Post #29
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2017-06-14T20:31:25+00:00
- Post Title: Re: Ghostbusters: The Video Game

Hi daemon1 and thanks for your tools for this game. I found that the game Silent Hill Book of Memories use the same format (.bfm and .skb) and them are packed inside .pod files that I could extract with the bms sript by aluigi. If you have the time/inclination I'd be happy to provide samples for if you don't have anything else lined up. Thanks in advance!
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-15T15:07:22+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from CaxUchiha
>
> if you don't have anything else lined up.

I have lots of things lined up.
## Post #31
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2017-06-26T18:35:38+00:00
- Post Title: Re: Ghostbusters: The Video Game

Hi again daemon, I understand. Anyway here are some samples for test when you have time. Thanks in advance!

[https://mega.nz/#!0gkmGa6D!FHyZxZ09vsLX ... LWwKYcGxdA](https://mega.nz/#!0gkmGa6D!FHyZxZ09vsLX5j6p7E6M7MCRtdL5WDKtSLWwKYcGxdA)
## Post #32
- Username: rayp83
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 23, 2017 8:24 am
- Post datetime: 2017-11-23T01:33:42+00:00
- Post Title: Re: Ghostbusters: The Video Game

Hi.

Anybody knows a way to convert SMB files ?
For example Ecto1b_chassis.smb ?
BloodRhyne Tools wont work 

Thank you.

BTW: Great tool, thanks for that.
## Post #33
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2019-06-26T19:17:39+00:00
- Post Title: Re: Ghostbusters: The Video Game

Is there any chance we can get a means to extract the PS2 version's models and textures properly? It's a different style of the game and has different models included, exclusive to this version. Here's a simple sample of both that coordinate to each other.

[https://www.dropbox.com/s/mxfnifcejeq1a ... m.zip?dl=0](https://www.dropbox.com/s/mxfnifcejeq1a6o/bookworm.zip?dl=0)
## Post #34
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-03-24T03:39:28+00:00
- Post Title: Re: Ghostbusters: The Video Game

A tragedy the maps will never be extracted from this, especially the iconic Firehouse. Anyone else willing to take this up and maybe try to rip levels?
## Post #35
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-02-22T16:01:48+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from Tosyk ↑Thu Jul 28, 2016 3:57 am at Thu Jul 28, 2016 3:57 am
>
> 
daemon1 wrote:i'll check that laterthanks in advanced.
btw I noticed that all the models along with their skeleton are fliped by X axis. I can flip it by X in 3d software but it is hard to animate this type of models because of wrong (after their physically fliped) transformations. If you could make this by code in your tool that would be great.

Did you ever find a workaround for this?

Edit: Solution found, in Blender when you import the model and stuff, select everything including the skeleton and hit Ctrl+M, and then press X, then click off and it'll mirror the model correctly with weights.
## Post #36
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2022-07-24T02:15:32+00:00
- Post Title: Re: Ghostbusters: The Video Game

Wow, amazing stuff! I haven't looked around at these game files in many years but I have a couple questions! Is it possible to edit a model and repack it into a POD for use in the game again? I'd be interested (and I'm sure many others would be too) to edit the player body's arm patch to remove the GB1 patch pasted over the GB2 patch in singleplayer. 

I'd also really love to get a copy of the mayor and ghoul heads with uv mapping in some max friendly format. I have the BFM files of those two but don't have Blender either so have been unsuccesful converting them but I guess I also need the textures. Not sure where those went, all I can find is the BFM files of them. Would anyone be kind enough to help? 

Thanks bunches!
## Post #37
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-07-26T20:34:11+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from Trancelikestate ↑Sun Jul 24, 2022 10:15 am at Sun Jul 24, 2022 10:15 am
>
> 
Wow, amazing stuff! I haven't looked around at these game files in many years but I have a couple questions! Is it possible to edit a model and repack it into a POD for use in the game again? I'd be interested (and I'm sure many others would be too) to edit the player body's arm patch to remove the GB1 patch pasted over the GB2 patch in singleplayer. 

I'd also really love to get a copy of the mayor and ghoul heads with uv mapping in some max friendly format. I have the BFM files of those two but don't have Blender either so have been unsuccesful converting them but I guess I also need the textures. Not sure where those went, all I can find is the BFM files of them. Would anyone be kind enough to help? 

Thanks bunches!

Eh for the first part modding the game is not possible sadly as far as I know. As for the mayor I can provide you with him but I don't have the ghoul heads. Shoot me a PM.
## Post #38
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2022-07-26T21:02:43+00:00
- Post Title: Re: Ghostbusters: The Video Game

Thank you so much Axel! I will shoot you a PM. I think modding it on some level is possible as there is that one mod from about 15 years ago for the original PC version that unlocks the GB2 suit and gold pack but obviously it's just a texture mod. I guess model editing which may be what you were referring to is not possible. There's a couple other "mods" for the remastered version I've seen that allow you to play as one of the other characters in only the library level for some reason so there's some types of POD repackers out there.
## Post #39
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-07-27T19:24:28+00:00
- Post Title: Re: Ghostbusters: The Video Game

> Reply from Trancelikestate ↑Wed Jul 27, 2022 5:02 am at Wed Jul 27, 2022 5:02 am
>
> 
Thank you so much Axel! I will shoot you a PM. I think modding it on some level is possible as there is that one mod from about 15 years ago for the original PC version that unlocks the GB2 suit and gold pack but obviously it's just a texture mod. I guess model editing which may be what you were referring to is not possible. There's a couple other "mods" for the remastered version I've seen that allow you to play as one of the other characters in only the library level for some reason so there's some types of POD repackers out there.

Oh dang, wasn't aware of that last bit there, that's rather interesting! Too bad it's not as common as I wish it'd be as I'd love to mod the game on a larger scale as well.
## Post #40
- Username: tianjiegao
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 02, 2021 9:40 pm
- Post datetime: 2022-11-17T08:32:45+00:00
- Post Title: Re: Ghostbusters: The Video Game

BloodRayne bfm file using the tool, get 0kb ascii
## Post #41
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-11-28T18:44:52+00:00
- Post Title: Re: Ghostbusters: The Video Game

The 3d models, like many of the props and pieces used to assemble the map are stored as .smb format, same format Bloorayne 1 and 2 use. Is anyone willing to look more into this? I can supply sample files.
## Post #42
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2023-06-09T18:30:00+00:00
- Post Title: Re: Ghostbusters: The Video Game

kinda late if someone wants model from the multiplayer or from the singleplayer send me a pm to send them also i have modded the remaster version so if you want any help with any game file also send me a pm
