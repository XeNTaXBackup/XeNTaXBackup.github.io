## Post #1
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-07-17T05:06:19+00:00
- Post Title: DX Ripper

Hi there, Xentax's community!
Let me introduce you to the old-new russian tool for ripping 3D-models from games:
[DX Ripper](http://blackninja2000.narod.ru/rus/directx_ripper.html) (working tittle) by black_ninja!
The main difference from Ukrainian 3D Ripper DX is that this tool captures the scene before the shaders transform it, and characters remains in the T-pose. Other geometry also captures without rotation or deformation.

This project is two years old and remain mostly unknown to community before HaCKer_UTD started a topic about this tool in Tosyk's [forum](http://cgig.ru/forum/viewtopic.php?f=5&t=38).
Four days later black_ninja appears in topic with suggestion to improve this tool if somebody interested and helps with testing.

For this moment work suspended again, because black_ninja is busy with other project and don't have a time and motivation to continue  develop this tool. Maybe someday in future.

How this tool works:

You'll need a copy of MilkShape 3D, because ripped meshes can be opened only through plugin for MS3D (included with ripper's package). It's main disadvantage of that tool i think.

There's two different ways to inject ripper in game:
1. Automatic but not so efficient - start injector.exe from folder where you unpack ripper, a window appears:

where:
"Exe:" - path to target game's executable, "Arg:" - game command line options if need, "Dir:" - folder for save captured geometry and textures.
After this small setup you'll press big "Run" button and game starts, ready for ripping (or fails ).
2. Advanced and complicated a little - copy intruder.dll and settings.ini to target game's folder (where main executable is) then rename intruder.dll to d3d9.dll and start game as usual.

After injecting you can use F10 key for full scene capture, F9 to capture only textures and F11 for shaders only. Keys can be changed by manually editing key codes in settings.ini with notepad. Key codes can be found [here](http://craftyjs.com/api/Crafty-keys.html) for example.

If rip succesful, a subfolder _ripper\frames\frame00 (then _ripper\frames\frame01, _ripper\frames\frame02, etc.) created in your target folder for rips if you use launcher, or in game folder where renamed intruder.dll is:
 

There's no special messages on screen like in 3D Ripper DX, so you'll need to Alt-Tab from game and check out result.

One rip creates one folder about 50-200 megabytes in size, so make sure you have enough space on hdd.

Important note: If you quit from game after making some rips, then start ripping again, captured folders overwrites, so good practice is to rename them after capture session like i did here:

(i add a number to "frames" folder after each session)


Importing to MilkShape:

Copy included plugin msripimp2.dll to MilkShape 3D main folder.
Start MS3D and go to File > Import > RIP Importer 2
a window pops up:

where:
"Folder:" - path to rip's folder, "File(s):" - numbers of meshes to import, "ClockWise Face" - option to invert normals if need, "Texture Level" - numberof texture layer, "Position" and "Normal" - rarely used options for handling geometry, "TexCoord" - options to fix UV map placement in 0-100 range.

Usually you don't need to change anything, press "..." button, select folder containing captured geometry (.rip files), type numbers of meshes to import in 0-12 or 1, 3, 15 format and press "Import" button.

Unfortunately sometimes you import series of meshes like 12-31 they imports messed up, but if you import these meshes one-by-one all go fine.

Numbers in texture names equivalent to numbers in names of meshes, but textures not duplicates for every mesh that uses this texture, only for first captured.
So if you found character body texture with number 0002 in name and next texture have number 0007, you can surely import meshes 2-6 for getting body model.

Noesis import plugin [here](http://forum.xentax.com/viewtopic.php?f=16&t=9266).
## Post #2
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2012-07-17T18:58:19+00:00
- Post Title: DX Ripper

Hi, 

The tool worked quite well for me as far as ripping all the geometry, textures and shaders, but I had no luck with T-pose  

I'm not sure if I'm doing something wrong or if it's the game itself.

BTW (Only tried it on Disnay HS Musical3)

Any help?
## Post #3
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-17T20:42:02+00:00
- Post Title: DX Ripper

I follow the tuto but i cant rip anything =/ i tested Ghostbusters/Deus Ex human revolution/RE4 and Dolphin
and on Ghosbusters give some violation access error code
## Post #4
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-07-17T23:01:16+00:00
- Post Title: DX Ripper

> Reply from Modman69
>
> Hi, 

The tool worked quite well for me as far as ripping all the geometry, textures and shaders, but I had no luck with T-pose  

I'm not sure if I'm doing something wrong or if it's the game itself.

BTW (Only tried it on Disnay HS Musical3)

Any help?
Not all games captures in t-pose, only animated with shaders i think. Some captured with bugs, like LOST game (cubic t-pose), there nothing we can do...

> Reply from The Chief
>
> I follow the tuto but i cant rip anything =/ i tested Ghostbusters/Deus Ex human revolution/RE4 and Dolphin
and on Ghosbusters give some violation access error code
Only DX9 games supported, and second variant of injection works way better for me.

I'm not programmer of this tool, and cannot help in compatibility issues 

Some compatibility/uncompatibility lists from Tosyk's forum:
Rips Ok (full rip with t-pose):
    The Saboteur
    Star Wars: The Force Unleashed I/II
    MX vs. ATV Reflex
    Assassin's Creed(s)
    Ghostbusters: The Video game
    Fuel
    Overlord 2
    James Bond 007 - Blood Stone
    The Hunter
    Call Of Juarez The Cartel
    The Club
    Batman Arkham City

Rips partially:
    Lost: Via Domus (full rip with t-pose, distorted models)
    Driver: San Francisco (full rip with t-pose, except characters)
    L.A. Noire (no textures, props ok, maybe t-pose chars)
    Pure (full rip with t-pose, no UVs)
    Call of Duty: Black Ops (no t-pose, no UVs)
    Call of Duty: Modern Warfare 2 (no t-pose, no UVs)

Don't rips:
    Dolpine Emulator (crashed with error)
    Battlefield: Bad Company 2 (ripped only some objects and textures)
    Blur (crashed with error)
    Call of Duty Modern Warfare 3 (unknown bug)

* If you have FRAPS in autostart, and rips empty folders - unload FRAPS and restart game. *
## Post #5
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-17T23:51:49+00:00
- Post Title: DX Ripper

OK i tested agian and i managet to get T pose models from NCIS The Video Game , but i cant open Ghost Busters the video game =/
any way thanks for posting this awesome tool here , i will test on other games.
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-07-18T07:07:37+00:00
- Post Title: DX Ripper

what I think can happen is that you are trying to force games to be dx9 when in fact they are dx10 or dx11. It will not start then because there should be errors. So, finding dx9 gamelist is probably the way first
## Post #7
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-07-18T07:45:51+00:00
- Post Title: DX Ripper

Awesome tool! As I have seen on his site it also works with DX5-7 and DX8 games, however the intruder.dll needs more work (it's missing some components seems). Do you have any idea if he's going to release source (to not let it as 3d ripper dx died)? Anyway I had no luck with DRIV3R so far, but I will continue trying.

EDIT: I just used Noesis with the plugin and I am just speechless, it ripped all the peds, Tanner, the cars and objects in T-pose!! 

EDIT2: I confirm that it works with Dolphin!
## Post #8
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-18T16:10:39+00:00
- Post Title: DX Ripper

> Reply from RacingFreak
>
> Awesome tool! As I have seen on his site it also works with DX5-7 and DX8 games, however the intruder.dll needs more work (it's missing some components seems). Do you have any idea if he's going to release source (to not let it as 3d ripper dx died)? Anyway I had no luck with DRIV3R so far, but I will continue trying.

EDIT: I just used Noesis with the plugin and I am just speechless, it ripped all the peds, Tanner, the cars and objects in T-pose!! 

EDIT2: I confirm that it works with Dolphin!

Wich version of dolphin do you test ? i test dolphin 3.0 x64 on windows 7 x64 but didnt work or i did some thing wrong XD

Also this tool works very well on:

Jurassic Park The Video Game
NCIS The Video Game 
CIS Deadly Intent 
Back to the future 

All of them in  T pose.
## Post #9
- Username: AceVentura
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jul 15, 2012 11:22 am
- Post datetime: 2012-07-19T01:14:13+00:00
- Post Title: DX Ripper

im testing it on Assassins Creed. The files are created in _ripper folder, DDS looks ok (although flipped) but if  I import them in MilkShape nothing happens.

here is an example capture. [http://www.mediafire.com/?n35qioinyr2nj10](http://www.mediafire.com/?n35qioinyr2nj10). Could someone try it to import to MilkShape or Noesis. Btw where can i download Noesis?
Thanks
## Post #10
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-19T02:18:50+00:00
- Post Title: DX Ripper

> Reply from AceVentura
>
> im testing it on Assassins Creed. The files are created in _ripper folder, DDS looks ok (although flipped) but if  I import them in MilkShape nothing happens.

here is an example capture. http://www.mediafire.com/?n35qioinyr2nj10. Could someone try it to import to MilkShape or Noesis. Btw where can i download Noesis?
Thanks

You dont need this tool for any of the Assassins Creed games just go here and download ForgeX tool

[http://www.tbotr.net/modules.php?mod=Do ... 4&sort=hot](http://www.tbotr.net/modules.php?mod=Downloads&req=viewsubcat&catid=9&subcatid=14&sort=hot)

And for Noesis you can download here

[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)
## Post #11
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-07-19T06:46:56+00:00
- Post Title: DX Ripper

I can tell it's hell easier with the Noesis plugin... just located the folder and start digging. I tested Driv3r, works INSANELY well (Tanner in T-Pose, NO normals loss or problems), not so well on Driver: Parallel Lines (just needs manual rescalling, I think by 100% on H side in Zmodeler), not so well on Man In Black: Alien Crisis for Wii on Dolphin (200% rescalling on H side in Zmodeler), The cars from Resident Evil: Darkside Chronicles ripped perfect, perfect ripping on the Camaro: Wild Ride. Now I will test all my games I have for Wii and Gamecube and make a list here.

I've been ripping using 3D Ripper DX and Dolphin for ages, but I can tell DX Ripper is the way better way, there's no rotation, scaling, FOV and so on you have to worry about and everything is in T-Pose (although Dolphin comes with free look hack, not always good result). And I never used the 3.0 release, just get the latest SVN builds... doesn't work with all games but I have almost all SVN Builds with notes what game on what release works better. For example with some James Bond games.

Have anyone tried with other emulators yet? I tried with PCSX2, failure. But I will try others.
## Post #12
- Username: AceVentura
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jul 15, 2012 11:22 am
- Post datetime: 2012-07-19T10:48:23+00:00
- Post Title: DX Ripper

> Reply from The Chief
>
> 
You dont need this tool for any of the Assassins Creed games just go here and download ForgeX tool

http://www.tbotr.net/modules.php?mod=Do ... 4&sort=hot

Thanks! I try to install the dlls but no success
## Post #13
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-19T16:53:18+00:00
- Post Title: DX Ripper

Do you install .NET Framework 3.5 ? 

And i already test on many versions of pcsx2 but not luck =/

I still need to test more games.
## Post #14
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-07-19T16:57:57+00:00
- Post Title: DX Ripper

> Reply from RacingFreak
>
> I've been ripping using 3D Ripper DX and Dolphin for ages, but I can tell DX Ripper is the way better way, there's no rotation, scaling, FOV and so on you have to worry about and everything is in T-Pose (although Dolphin comes with free look hack, not always good result).

So wait, it'll T-Pose Dolphin stuff too?
## Post #15
- Username: AceVentura
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jul 15, 2012 11:22 am
- Post datetime: 2012-07-19T17:25:35+00:00
- Post Title: DX Ripper

> Reply from The Chief
>
> Do you install .NET Framework 3.5 ?

Im running Win7 32Bit, which includes 2.0/3.0/3.5, plus SP1 for 3.5.
Can someone please take a look at  this [frame](http://www.mediafire.com/?n35qioinyr2nj10.) if it loads in Milkshape or noesis. I had no luck with it.
## Post #16
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-07-19T17:58:38+00:00
- Post Title: Re: DX Ripper

> Reply from Teancum
>
> RacingFreak wrote:I've been ripping using 3D Ripper DX and Dolphin for ages, but I can tell DX Ripper is the way better way, there's no rotation, scaling, FOV and so on you have to worry about and everything is in T-Pose (although Dolphin comes with free look hack, not always good result).

So wait, it'll T-Pose Dolphin stuff too?
Correct, however not on all games will come out properly (you might only need to scale it up). I noticed there's problem occuring with strip/fan connections (3D Ripper DX has option to remove these), does anyone know how to get rid of this automatically without having to manually remove it (is annoying especially on high detailed meshes). However I got outstanding results in games like GTI Club. Tried with James Bond games too, perfect extracts here, no strip/fan connections atleast here
## Post #17
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-19T18:03:51+00:00
- Post Title: Re: DX Ripper

> Reply from AceVentura
>
> The Chief wrote:Do you install .NET Framework 3.5 ? 


Im running Win7 32Bit, which includes 2.0/3.0/3.5, plus SP1 for 3.5.
Can someone please take a look at  this frame if it loads in Milkshape or noesis. I had no luck with it.

The rips load fine on Noesis , in A pose , abouth the ForgeX tool sorry i cant help much i myselft cant runit either on windows 7 x64
so i use windows xp =/
## Post #18
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-07-19T20:00:07+00:00
- Post Title: Re: DX Ripper

I confirm that it works perfectly with Driver: San Francisco. You'd need to paste intruder.dll (rename it to d3d9.dll and settings.ini) in order to make successfull captures however. Only weird thing is normals, the look like projection, but that's easy to fix after Calculating them in either Zmodeler 2 or 1. I also tried with Onimusha 3 and it didnt work (however works with 3D Ripper DX).
## Post #19
- Username: AceVentura
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jul 15, 2012 11:22 am
- Post datetime: 2012-07-19T20:52:03+00:00
- Post Title: Re: DX Ripper

> Reply from The Chief
>
> 
The rips load fine on Noesis , in A pose , abouth the ForgeX tool sorry i cant help much i myselft cant runit either on windows 7 x64
so i use windows xp =/

Ok maybe im waiting something whats not even there. Which mesh should i look at? For me looks all like junk: missing parts, no texture, or i cant see nothing at all. Where are the buildings, trees ect? With 3d Ripper DX i could rip from some games the whole scene's wireframe,  without textures or shaders, though.

[](http://postimage.org/image/beiu3z901/)
[](http://postimage.org/image/pzxv520cd/)
## Post #20
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-19T20:59:55+00:00
- Post Title: Re: DX Ripper

That´s normal it happend to me to on some games i test (all models braked in pieces) just export one by one and then open them in
Maya/Max studio or what ever 3D program do you have.
## Post #21
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-07-19T21:18:35+00:00
- Post Title: Re: DX Ripper

The models are indeed separated, but that way its a lot easier to work with. What I usually do in Noesis is to look at bigger sized files, and then scrolling up or down the other pieces are here. I found a solution for the fan/strip connections and it's one special max script I got for GTA LCS.

PS
I have posted some of my model rips all done using DXRip right [here](http://gtr.uk.pn/forum/showthread.php?p=6211#post6211).
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-25T14:54:50+00:00
- Post Title: Re: DX Ripper

> Reply from RacingFreak
>
> Teancum wrote:RacingFreak wrote:Tried with James Bond games too, perfect extracts here, no strip/fan connections atleast herewhat did u do to rip models from james bond games in t-pose?
## Post #23
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-25T17:29:23+00:00
- Post Title: Re: DX Ripper

Hey RacingFreak just curius wich games do you test on Dolphin ? 

Also i been testing more games , and with good results , the only isue are the models breaked in pieces but oh well
i cant complain that´s better than nothing.
## Post #24
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-07-25T21:58:25+00:00
- Post Title: Re: DX Ripper

I will make list asap, but I mainly rip car models, so dunno about characters.
## Post #25
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-08-21T15:55:51+00:00
- Post Title: Re: DX Ripper

Tool totally rewritten and renamed to [Ninja Ripper](http://cgig.ru/forum/viewtopic.php?f=5&t=224)...
## Post #26
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-08-21T16:12:45+00:00
- Post Title: Re: DX Ripper

> Reply from Andrakann
>
> Tool totally rewritten and renamed to Ninja Ripper...It's not working with emulators though
## Post #27
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-09-07T18:20:04+00:00
- Post Title: Re: DX Ripper

So can this Ninja Ripper DX extract 3D from DirectX 7.0 games?
## Post #28
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-09-08T02:30:23+00:00
- Post Title: Re: DX Ripper

> Reply from Mirrorman95
>
> So can this Ninja Ripper DX extract 3D from DirectX 7.0 games?it can't, as i know, maybe in the future
## Post #29
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-09-16T10:46:18+00:00
- Post Title: Re: DX Ripper

Very good to hear it's still active project! Will source code be released at some point? I hope Dolphin and emulators support will be added aswell (for Dolphin and PCSX2)
## Post #30
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-09-28T15:17:16+00:00
- Post Title: Re: DX Ripper

I just want to say thanks for the tools. After struggling with Game Assassin for a while, I found this and have a lot of success with rips. I've gotten some nice models from Dark Sector, I Am Alive, and Inversion. I look forward to using it with more games.
## Post #31
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-09-28T15:33:18+00:00
- Post Title: Re: DX Ripper

dragbody, nice to read that
## Post #32
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-05T15:24:18+00:00
- Post Title: Re: DX Ripper

I'm experiencing a problem. Like I've said, I've had great luck with dx ripper with several games. However, for the game I'm currently using it with, none of the models are keeping their UVs. I've seen this with other games where many copies of the same model are  duplicated and many of them will not keep their UVs, but at least one will. However, I can find none with UVs preserved in my current game. Is there any trick that I'm missing? Or is there a way to fix the UVs when the rip file is already made?
## Post #33
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-05T15:42:21+00:00
- Post Title: Re: DX Ripper

> Reply from dragbody
>
> I'm experiencing a problemu can change uv parameters (numbers) on the importer panel, anyway all information including uv is in .rip file
## Post #34
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-05T15:50:47+00:00
- Post Title: Re: DX Ripper

> Reply from Tosyk
>
> dragbody wrote:I'm experiencing a problemu can change uv parameters (numbers) on the importer panel, anyway all information including uv is in .rip file

Thanks for your reply. I'm not sure I know how to change UV parameters as you say though. I'll try to figure it out, but could you please explain? I appreciate the help.
## Post #35
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-05T15:57:47+00:00
- Post Title: Re: DX Ripper

> Reply from dragbody
>
> could you please explain?like on the image:


just choose manual mode and by changing TexCoords parameters find out correct uv
## Post #36
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-05T16:00:05+00:00
- Post Title: Re: DX Ripper

I see. I'm using the Noesis plugin from finale00. Is there a way I can fix UVs still? Or do I need to use the program you're showing?
## Post #37
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-05T16:10:43+00:00
- Post Title: Re: DX Ripper

> Reply from dragbody
>
> I see. I'm using the Noesis plugin from finale00. Is there a way I can fix UVs still? Or do I need to use the program you're showing?you can't get correct uv with noesis, you have to use 3ds max for that, the image i showed to you it's a window of a script for 3ds max
## Post #38
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-05T16:26:39+00:00
- Post Title: Re: DX Ripper

Is that true for dx ripper, not ninja ripper? And I do not have 3ds max. Could I send you the files for correction? Then you could have them too   It's not a very large amount.
## Post #39
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-05T16:54:42+00:00
- Post Title: Re: DX Ripper

> Reply from dragbody
>
> Is that true for dx ripper, not ninja ripper? And I do not have 3ds max. Could I send you the files for correction? Then you could have them too   It's not a very large amount.sorry, i have no time for this, and i advise you to get 3ds max
## Post #40
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-05T19:40:25+00:00
- Post Title: Re: DX Ripper

I understand. Thanks anyway  Ive got some friends with 3ds max. I'll ask them to take a look at it. I would love to have it too but my trial has expired and I cannot afford to purchase it.
## Post #41
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-05T23:20:07+00:00
- Post Title: Re: DX Ripper

just sign up for education version.
## Post #42
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-06T05:27:46+00:00
- Post Title: Re: DX Ripper

> Reply from chrrox
>
> just sign up for education version.

I have a doubt here, can you have any version of max you want or just the newest one??

See ya
## Post #43
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-10-06T16:39:58+00:00
- Post Title: Re: DX Ripper

> Reply from dragbody
>
> I see. I'm using the Noesis plugin from finale00. Is there a way I can fix UVs still? Or do I need to use the program you're showing?
Hey, I am using the Noesis plugin aswell and everything works just fine. I use the -flipuv (Flip UV) on export options.
## Post #44
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-09T02:16:55+00:00
- Post Title: Re: DX Ripper

I found the UV on the models I was having trouble with. After using the noesis plugin to convert the rip to obj, then after importing the obj into Blender, I went to UV/Image Editor. It turns out that the UV map was absolutely HUGE and in X and Y coordinates 5000+. It took a lot of adjusting, but at least it wasn't distorted. I'm glad to say it's working just fine now
## Post #45
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-09T02:22:22+00:00
- Post Title: Re: DX Ripper

> Reply from dragbody
>
> I found the UV on the models I was having trouble with. After using the noesis plugin to convert the rip to obj, then after importing the obj into Blender, I went to UV/Image Editor. It turns out that the UV map was absolutely HUGE and in X and Y coordinates 5000+. It took a lot of adjusting, but at least it wasn't distorted. I'm glad to say it's working just fine nowah yeah, i forgot about that kind of issue, glad you were able to solve your issue
## Post #46
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-17T13:46:29+00:00
- Post Title: Re: DX Ripper

Hello!

I have a problem with DX ripper and Ninja Ripper. I tried extract models from Alan Wake, but when I try run program I get message:

"intruder.dll
Can't open log file".
## Post #47
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-18T04:39:52+00:00
- Post Title: Re: DX Ripper

You have to rename intruder to the correct name for the game. Probably d3d9.
## Post #48
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-18T10:47:57+00:00
- Post Title: Re: DX Ripper

Thanks! Anyway tool doesn't work with Alan Wake and Alan Wake American Nightmare xd
## Post #49
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-18T11:59:42+00:00
- Post Title: Re: DX Ripper

> Reply from Kamillho
>
> Thanks! Anyway tool doesn't work with Alan Wake and Alan Wake American Nightmare xdit's working for me, even old version of ripper (3d ripper one), i'm sure everything should work with ninja ripper also

try to rip torrent version of the game
## Post #50
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-18T12:39:36+00:00
- Post Title: Re: DX Ripper

> Reply from Tosyk
>
> Kamillho wrote:Thanks! Anyway tool doesn't work with Alan Wake and Alan Wake American Nightmare xdit's working for me, even old version of ripper (3d ripper one), i'm sure everything should work with ninja ripper also

try to rip torrent version of the game

I DL and nothing... I click on F10/F9 and game Ninja Ripper don't save models ;/
## Post #51
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-18T12:48:15+00:00
- Post Title: Re: DX Ripper

> Reply from Kamillho
>
> I DL and nothing... I click on F10/F9 and game Ninja Ripper don't save models ;/wich way you loading game? and wich mode did you use?
## Post #52
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-18T19:15:32+00:00
- Post Title: Re: DX Ripper

Well I check the file .exe in main folder. And which mode should I choose? I play on admin account.
## Post #53
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-10-19T01:30:11+00:00
- Post Title: Re: DX Ripper

+1 vouch on this tool. Might try this some time when I convert stuff from other games.
## Post #54
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-19T12:37:24+00:00
- Post Title: Re: DX Ripper

> Reply from Kamillho
>
> Well I check the file .exe in main folder. And which mode should I choose? I play on admin account.in case of ninja ripper there is a 2 mode:

wrapper (dx9/dx8) - .dll will be copied into games directory and you can close ripper and play game as usual
no wrapper - you start game through the ripper and it trying to inject into game by his own

first try to use 'no wrapper', if it doesn't work change ripper's mode to 'wrapper'

after that you should get a log file in a ripper folder, and if you have a problem with ripping do attach log file in here, or in the [official thread](http://cgig.ru/forum/viewtopic.php?f=5&t=224) and autor and will trying to help you
## Post #55
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-10-19T17:23:46+00:00
- Post Title: Re: DX Ripper

I have question, will it be possible to increase support to older DDRaw and D3D6 wrappers? Would be simply awesome, I managed to rip models from old russian games that use D3D8 just fine 

PS
Is there a proper way to adjust / correct the UV map? The only problem I ever encounter. And normals problem in few games aswell.
## Post #56
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-20T16:37:33+00:00
- Post Title: Re: DX Ripper

> Reply from Tosyk
>
> Kamillho wrote:Well I check the file .exe in main folder. And which mode should I choose? I play on admin account.in case of ninja ripper there is a 2 mode:

wrapper (dx9/dx8) - .dll will be copied into games directory and you can close ripper and play game as usual
no wrapper - you start game through the ripper and it trying to inject into game by his own

first try to use 'no wrapper', if it doesn't work change ripper's mode to 'wrapper'

after that you should get a log file in a ripper folder, and if you have a problem with ripping do attach log file in here, or in the official thread and autor and will trying to help you

Still doesn't work, but anyway I tested on other games and work good:D
## Post #57
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-24T08:43:00+00:00
- Post Title: Re: DX Ripper

this thread is obsolete and discussion moving [here](http://forum.xentax.com/viewtopic.php?f=33&t=9782)
## Post #58
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2013-04-19T21:59:29+00:00
- Post Title: Re: DX Ripper

> Reply from Tosyk
>
> this thread is obsolete and discussion moving here
When I use dx ripper & ninja ripper for Beyond Good & Evil PC, It doesn't rip the characters in T-Pose
## Post #59
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2013-04-20T06:55:57+00:00
- Post Title: Re: DX Ripper

> Reply from RacingFreak
>
> I have question, will it be possible to increase support to older DDRaw and D3D6 wrappers? Would be simply awesome, I managed to rip models from old russian games that use D3D8 just fine
I endorse this request - it's will be great to have old DX5-7 support!
## Post #60
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-06-23T00:35:00+00:00
- Post Title: Re: DX Ripper

I don't mean to bump but I am hoping to get a little help here.

 1. which version of Dolphin does DX ripper11  work with? someone else asked and never got an answer on this tread and as someone working with gamecube models I need help to figure that out.

2. ninja ripper isn't ripping vehicles despite them being in 3rd person mode view and being in the frame. it never used to not do that but it is now out of the blue.

3. ninja ripper stops ripping frames after a time for no seeming reason. I get one maybe two actual frame rips out of a set of 5. the other three folders will be empty. why is this?

 Ninja ripper seems like it's getting less and less effective for my needs. dx ripper11 seems promising but I need to know which dolphin it works with and under what settings.

 also the newest ninja ripper .mesh files do import into 3d max except they are invisible and I can't make them visiable at all and it does say I've imported models with geomytry but they don't show up at all. it's like they are both there and not there at the same time. and again it's all out of the blue that it's doing all these things.
