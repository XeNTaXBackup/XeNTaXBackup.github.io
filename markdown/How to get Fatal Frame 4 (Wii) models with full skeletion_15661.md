## Post #1
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2016-12-29T16:57:38+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

Can someone teach me how to extract ISO and import to convert game models?
I just want rip some ghosts from this game.
## Post #2
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2016-12-30T04:05:08+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

Files can be extracted with Dolphin emulator. (RMB - Properties - File System or something like that)

(Archivers can't open Wii ISOs, right?)

Then it depends on what's inside.
## Post #3
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2016-12-31T12:06:52+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

> Reply from zheneq
>
> Files can be extracted with Dolphin emulator. (RMB - Properties - File System or something like that)

(Archivers can't open Wii ISOs, right?)

Then it depends on what's inside.

Apologize for my late replying
Followed your tutorial, I extracted the ROM.
it's content some format files:
*.BIN ---> I think this is game models. However, I just found 30 files totally 4mb - 151kb/file
*.RSL ---> Textures
*.THP ---> Movies
*.ARC ---> Game language settings
*.BRSTM ---> Sounds (It's been contented in a folder with name "SND". This folder and "Movie" folder are biggest size of whole the game) 
*.IMG ---> Unknown. Content one file only, "Apploader.img" 239kb
*.BRSAR ---> Sounds

I just guess

Sorry, my English is not good

For sample files:
[http://www.mediafire.com/file/8sac643ne ... rame_4.rar](http://www.mediafire.com/file/8sac643nea7j5ly/Samples_for_Fatal_Frame_4.rar)

If you wanted, I could send you full of files I have extracted, they are up to >800mb (Uncompress)
## Post #4
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2016-12-31T13:47:18+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

THP (movie), BRSTM (audio stream), BRSAR (sound archive) and ARC (generic archive) can be opened with Brawl Box. (Home Button menu is a special pause menu that must be in every Wii game AFAIK)

I guess RSL is some kind of universal container. I seems to be used only in Grasshoppers Manufacture games. BIN file in the archive seems to have the same structure. There were guys who extracted text and images from the game but that's all.
## Post #5
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2016-12-31T15:24:50+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

> Reply from zheneq
>
> THP (movie), BRSTM (audio stream), BRSAR (sound archive) and ARC (generic archive) can be opened with Brawl Box. (Home Button menu is a special pause menu that must be in every Wii game AFAIK)

I guess RSL is some kind of universal container. I seems to be used only in Grasshoppers Manufacture games. BIN file in the archive seems to have the same structure. There were guys who extracted text and images from the game but that's all.

Um... Does that mean no way to get full rigging ingame models?
## Post #6
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2016-12-31T15:45:47+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

I guess there is no existing solution.
## Post #7
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2016-12-31T16:07:52+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?


## Post #8
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2017-01-01T13:14:58+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

> Reply from ngovandang
>
> 

Don't worry you can extract the 3d models with bones, if i remember well. The game uses mdl0 format, and they have ben extracted in the past, just take a look at the older tread of the forum, or on the web.
(u can even ripp the models in t-pose using the usual ripping tools like ninja ripper, 3dvia printscreen, and so on) in opengl mode, using the emulator.)
Another solution fast and easy if u are struggling to have those models is to go on xnalara site or devianart and downlod the rigged models, then you can convert the xnalara format (xps format if i remember well) with a script for 3ds max , (there should be even a script for blender and noesis, but i'm not so sure) just search with google. and you have the models. Happy newyear!
## Post #9
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-01-01T14:50:16+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

If the models are really in mdl0 format, they should be easy to spot.

Ngovandang, can you upload some more files?
## Post #10
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-01-09T00:43:44+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

> Reply from Ares722
>
> ngovandang wrote:

Don't worry you can extract the 3d models with bones, if i remember well. The game uses mdl0 format, and they have ben extracted in the past, just take a look at the older tread of the forum, or on the web.
(u can even ripp the models in t-pose using the usual ripping tools like ninja ripper, 3dvia printscreen, and so on) in opengl mode, using the emulator.)
Another solution fast and easy if u are struggling to have those models is to go on xnalara site or devianart and downlod the rigged models, then you can convert the xnalara format (xps format if i remember well) with a script for 3ds max , (there should be even a script for blender and noesis, but i'm not so sure) just search with google. and you have the models. Happy newyear!
^^ Thank you, I'm a Xnalara worker. I want port ghosts from this game, but no one had ripped them. Capture 3D scene programs are good, but I have to meet the characters I want to port ingame. That take alot of time to play.
## Post #11
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-01-09T00:46:44+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

> Reply from zheneq
>
> If the models are really in mdl0 format, they should be easy to spot.

Ngovandang, can you upload some more files?
^^ forgive my late, I didn't think new replies will be posted here
Here you go:
[https://drive.google.com/uc?id=0B9ok-RJ ... t=download](https://drive.google.com/uc?id=0B9ok-RJUXFeAanljS1M3TFVxUUE&export=download)
## Post #12
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-01-15T04:42:37+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

Nope, models are stored in another format. I managed to extract vertices but I can't even figure out where faces are.

I can post what I have, in case somebody wants to help.
## Post #13
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-01-15T13:38:51+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

> Reply from zheneq
>
> Nope, models are stored in another format. I managed to extract vertices but I can't even figure out where faces are.

I can post what I have, in case somebody wants to help.

;-; post it please!
Btw, I think *.RSL format FF4 is similiar to No more heroes 2
Someone had released plugin for Blender to import *.RSL NMH2, but link has been removed
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-15T20:58:48+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

the mesh seems to consist of digitized data (laserscanned object).



CMNGN-RSL.JPG (79.62 KiB) Viewed 566 times


Autocreated faces don't work, but there should exist some algo to connect the points in the different parallel planes.
## Post #15
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-01-15T23:58:43+00:00
- Post Title: How to get Fatal Frame 4 (Wii) models with full skeletion?

That's what a mesh block looks like: [pic](https://yadi.sk/i/2CeGlf4u39EG8i)
Three blocks of data, then references to them, and then - draw lists?

Noesis plugin is here: [https://github.com/Zheneq/Noesis-Plugins](https://github.com/Zheneq/Noesis-Plugins) (to view point clouds, though not all of them seem to work)

> Reply from shakotay2
>
> the mesh seems to consist of digitized data (laserscanned object).
At least some meshes don't look that way.



2017-01-16_02-33-06.png (25.18 KiB) Viewed 561 times



> Reply from ngovandang
>
> Btw, I think *.RSL format FF4 is similiar to No more heroes 2
Someone had released plugin for Blender to import *.RSL NMH2, but link has been removed
Yep, these games are by the same developer. Where did you find the plugin?

UPD: Found it [viewtopic.php?f=18&t=6546](http://forum.xentax.com/viewtopic.php?f=18&t=6546)
## Post #16
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-01-16T04:48:22+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> That's what a mesh block looks like: pic
Three blocks of data, then references to them, and then - draw lists?

Noesis plugin is here: https://github.com/Zheneq/Noesis-Plugins (to view point clouds, though not all of them seem to work)
shakotay2 wrote:the mesh seems to consist of digitized data (laserscanned object).
At least some meshes don't look that way.
2017-01-16_02-33-06.png
ngovandang wrote:Btw, I think *.RSL format FF4 is similiar to No more heroes 2
Someone had released plugin for Blender to import *.RSL NMH2, but link has been removed
Yep, these games are by the same developer. Where did you find the plugin?

UPD: Found it viewtopic.php?f=18&amp;t=6546

Um... Thank you
But NMH2 plugin is removed ;-;
Btw, I found some info of RSL
[https://gbatemp.net/threads/rsl-data-containers.149429/](https://gbatemp.net/threads/rsl-data-containers.149429/)
[https://gbatemp.net/threads/wii-game-gr ... ts.206726/](https://gbatemp.net/threads/wii-game-graphic-assets.206726/)
## Post #17
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-10-17T07:52:10+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

Is this thing still needed?
[2017-10-17_10-28-41.png](https://xentaxbackup.github.io/file/13447_2017-10-17_10-28-41.png)
## Post #18
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-10-27T07:54:29+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

Welp, I'm working on it in any case =P
[2017-10-26_17-36-54.png](https://xentaxbackup.github.io/file/13496_2017-10-26_17-36-54.png)
## Post #19
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-10-29T19:07:13+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

So, the plugin is [here](https://github.com/Zheneq/Noesis-Plugins).

Opens models (both characters and rooms) and texture archives.

I didn't look into the animations but I can if anybody needs them.
[2017-10-29_22-01-19.png](https://xentaxbackup.github.io/file/13505_2017-10-29_22-01-19.png)
## Post #20
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-29T23:24:37+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> So, the plugin is here.

Opens models (both characters and rooms) and texture archives.

I didn't look into the animations but I can if anybody needs them.

Thanks a lot for this! 
Do you think you could support No More Heroes 2 RSL too? Currently they only load up one texture so i suppose the format might be slightly different. I can upload samples if needed.
## Post #21
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-10-31T08:41:36+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> So, the plugin is here.

Opens models (both characters and rooms) and texture archives.

I didn't look into the animations but I can if anybody needs them.

*O* you really did it
thank you
## Post #22
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-11-01T21:49:48+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from o0Crofty0o
>
> Do you think you could support No More Heroes 2 RSL too?

No More Heroes uses a different format for models and animations -- RSL is just a container. It doesn't seem totally different though.
## Post #23
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2017-11-04T13:14:37+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> So, the plugin is here.

Opens models (both characters and rooms) and texture archives.

I didn't look into the animations but I can if anybody needs them.

thank you
## Post #24
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-12-15T04:18:47+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> So, the plugin is here.

Opens models (both characters and rooms) and texture archives.

I didn't look into the animations but I can if anybody needs them.

Alright i am the one of who is interested in it.
Can you add the function of animation export ?
## Post #25
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-12-15T13:17:56+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from z22901206
>
> Can you add the function of animation export ?

I think I can, but I'm really busy atm.

Also I believe I set bone weights the wrong way so probably I'll have to crack No More Heroes 2 format first (it's simpler).
## Post #26
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2017-12-25T13:39:32+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> z22901206 wrote:Can you add the function of animation export ?

I think I can, but I'm really busy atm.

Also I believe I set bone weights the wrong way so probably I'll have to crack No More Heroes 2 format first (it's simpler).

does the scripts can use for fatal frame 2(Wii)?
## Post #27
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-12-26T14:03:51+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from phay008
>
> does the scripts can use for fatal frame 2(Wii)?

I doubt that. But if it does have .rsl files in it, the format shouldn't be much different.
## Post #28
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2017-12-29T08:49:34+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> phay008 wrote:does the scripts can use for fatal frame 2(Wii)?

I doubt that. But if it does have .rsl files in it, the format shouldn't be much different.

I use your script to import the .rsl file. the model is good. hut the face don't have bones???and some.rsl file can't import.ex:EJD00    ENB00   ETG00.JNU00.NNB00.MASKA01/00.
BTW,can you make a script to rip the models from fatal frame 2 WII when you have time?
## Post #29
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-10-28T19:56:04+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

please help, i have put  the fatal frame and nintex script in python folder, but noesis still can't open the files
## Post #30
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2018-10-30T05:31:59+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

If it doesn't recognize .rsl files, then something is wrong with your setup. If it fails to open them, post the error message.
## Post #31
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-10-30T09:09:28+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> If it doesn't recognize .rsl files, then something is wrong with your setup. If it fails to open them, post the error message.
it is the standart
 when trying to view the error is "file could not be previewed"
 when trying to export the error is "file could not be determined"
it does not even appear in noesis' list of known  format

on your fatal frame  plugin page I clicked raw  and  save the script to my noesis' python folder, but the  plugin was saved as  fmt_fatalframe_rsl.py.txt( a txt file) instead of fmt_fatalframe_rsl.py
## Post #32
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2018-10-31T08:42:36+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

Remove the ".txt" or redownload it but pick "All files *.*" type this time.

Or if you have done it, the problem may be in the specific file (like, it contains neither models nor textures).

UPD: I fixed a crash on models with no geometry.
## Post #33
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-10-31T11:45:48+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

i checked it on sykoo.rsl, the one you usedas an example
i selected all file and it is still saved as .txt
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-31T14:59:54+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

man, I'm serioulsy asking myself what the problem might be. Is it your operating system, the language  or something else?

You need to download fmt_fatalframe_rsl.py, correct?

This is how it looks for me and the .py is saved as .py to my pc:



save_py.png (3.73 KiB) Viewed 322 times



Or,  even simpler, rename fmt_fatalframe_rsl.py.txt to fmt_fatalframe_rsl.py
## Post #35
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-10-31T21:50:10+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

turned out chrome was the problem. I used firefox and it saved the plugin correctly as .py. the script works now, thanks all.

> Reply from shakotay2
>
> 

Or,  even simpler, rename fmt_fatalframe_rsl.py.txt to fmt_fatalframe_rsl.py
i wasn't able to rename the plugin  because  the .txt is not part of the name. when i tried to  rename the  file it just shows "fmt_fatalframe_rsl.py".  thankfully the problem is already solved  now
## Post #36
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2018-11-12T14:42:04+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

I forgot to post this. I updated the script on Jul 27, 2018, added morph targets and fixed a bug that could result in incorrect geometry/weights in rare cases.
## Post #37
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2019-01-05T23:07:32+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq
>
> I forgot to post this. I updated the script on Jul 27, 2018, added morph targets and fixed a bug that could result in incorrect geometry/weights in rare cases.
Haha.  Thank you for updating. This is cool
## Post #38
- Username: Nik
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 30, 2019 8:32 pm
- Post datetime: 2019-11-30T13:33:39+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

So yeah I know this is an old thread but im gonna go ask for help anyways.
What I want to do is simply replace the splash screen main menu logo with a English logo I found on the internet
What I manage to do: 
Open the .RSL container file using Noesis
View the models 
Export .png files of the main menu textures (including the logo I want to replace)

so how do you replace the textures in the rsl files?
## Post #39
- Username: Ryoutukankiti
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 17, 2020 2:10 pm
- Post datetime: 2020-03-17T06:24:20+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

Hi.I want to rip motion from RSL.
Some files looks like motion files.(For example,JNA00.RSL and JNAA00.RSL RUK00.RSL and RUKA00.RSL)
Maybe, this "A" means "Animation".
I loaded in noesis,but these can't load.So, how can you rip character's motion from these files?
I want to export psa or something.



fda.jpg (238.51 KiB) Viewed 230 times
## Post #40
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2020-03-25T22:10:30+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

Those are animation files indeed and they are not supported at this point.
## Post #41
- Username: Ryoutukankiti
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 17, 2020 2:10 pm
- Post datetime: 2020-03-31T04:05:57+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq ↑Thu Mar 26, 2020 6:10 am at Thu Mar 26, 2020 6:10 am
>
> 
Those are animation files indeed and they are not supported at this point.

Oh.It's sorry to, but your script is very good,if you okay please make it when you have time.
## Post #42
- Username: U653748
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 05, 2015 5:33 am
- Post datetime: 2020-09-07T19:54:16+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq ↑Tue Oct 30, 2018 1:31 pm at Tue Oct 30, 2018 1:31 pm
>
> 
If it doesn't recognize .rsl files, then something is wrong with your setup. If it fails to open them, post the error message.

when opening R204.rsl and a few others i get this error message (REDACTED = part of file path on my HD, omitted for privacy)

> Detected file type: Grasshopper Manufacture Container
>
> @0x1c0
>
> Loading RMHG
>
> @0x40
>
> Cannot parse SCR0
>
> @0x6380
>
> Loading RMHG
>
> @0x40
>
> Loading CGMG
>
> Traceback (most recent call last):
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_fatalframe_rsl.py", line 95, in rslLoadModel
>
>     RSLFile(NoeBitStream(data), mdlList).load()
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_fatalframe_rsl.py", line 110, in load
>
>     self.root.load()
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_fatalframe_rsl.py", line 177, in load
>
>     x['data'].load()
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_fatalframe_rsl.py", line 177, in load
>
>     x['data'].load()
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_fatalframe_rsl.py", line 238, in load
>
>     self.loadMeshes()
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_fatalframe_rsl.py", line 590, in loadMeshes
>
>     self.readBuffers(bufferHeaders, boneId, chunkHeader['length'], chunkBoneGroupListList[chunkBoneGroupTable.index(chunkHeader['boneAddr'])] if chunkHeader['boneAddr'] else None)
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_fatalframe_rsl.py", line 648, in readBuffers
>
>     bs.seek(bufferHeaders[j]['addr'] + idx * self.sizes[typ])
>
>   File "[REDACTED]\Noesis\plugins\python\inc_noesis.py", line 181, in seek
>
>     self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
>
>   File "[REDACTED]\Noesis\plugins\python\inc_noesis.py", line 177, in fromUnpacker
>
>     self.setOffset(self.byteOfs)
>
>   File "[REDACTED]\Noesis\plugins\python\inc_noesis.py", line 80, in setOffset
>
>     noesis.bsSetOfs(self.h, ofs)
>
> RuntimeError: Tried to set offset beyond buffer size. (5344152 > 5056800)

Also in another error some of the UV's for some of the rooms come out scrambled
 example
## Post #43
- Username: Temporariamentchi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 18, 2021 1:48 am
- Post datetime: 2021-11-18T00:18:21+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq ↑Thu Mar 26, 2020 6:10 am at Thu Mar 26, 2020 6:10 am
>
> 
Those are animation files indeed and they are not supported at this point.

I know it's been a year from now, so sorry for that, but could you make the script compatible with them? Your script is great for ripping the models, and I'm really wanting those animations files, so I searched everywhere on how to rip .rsl files but no success. I know nothing of coding too, so I'm kinda stuck
## Post #44
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2021-11-18T03:29:17+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

please Animation support
## Post #45
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2021-11-25T06:53:20+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletio

> Reply from zheneq ↑Thu Mar 26, 2020 6:10 am at Thu Mar 26, 2020 6:10 am
>
> 
Those are animation files indeed and they are not supported at this point.

Once you got free time, will you check out Fatal Frame 2 Wii too?
I really want to get all the Fatal Frame ghosts and human characters from every part of the series
## Post #46
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2021-11-25T20:22:53+00:00
- Post Title: Re: How to get Fatal Frame 4 (Wii) models with full skeletion?

Will there ever be No More Heroes 1 and 2 support?
