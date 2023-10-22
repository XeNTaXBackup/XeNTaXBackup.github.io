## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-05T13:10:14+00:00
- Post Title: Battleborn tools

I'm not going to make a new Umodel. But since gildor is not going to support this game, I will just make a set of simple tools to extract all models and textures.

You can extract .skeletalmesh from UPK packages with gildor's Extract.exe

Drag .skeletalmesh file onto Battleborn_model.exe and it will extract model into 3formats: .OBJ, .SMD and .ASCII. Only SMD file will have proper skeleton connected to bones. If NameTable.txt produced by Extract.exe will be in the same folder, bones will have proper names.

Drag .TFC file onto battleborn_tfc.exe and it will extract all textures (in game internal format)

Put Battleborn_dds.exe into that folder and run. This will convert all textures to DDS. BC7 textures (normal maps mostly) will be converted to DX10 DDS files which are only supported by newest viewers. Like Visual studio 2015 or texconv covertor.

Texture numbers for most characters:

```
SK_C002_GentSniper		Marquis	- 84
SK_C003_MachineGunner	Montana	- 65
SK_C004_ModernSoldier		Oscar Mike - 119
SK_C005_Deathblade		Rath	- 48
C006_TribalHealer		        Miko	- 184	
SK_C007_RogueCommander	Reina	- 297
SK_C010_AssaultJump		Caldarius  - 160
SK_C011_RocketSoldier		Benedict   - 317
SK_C012_MageBlade		Phoebe 	- 247
SK_C013_DwarvenWarrior		Boldur	- 365
SK_C014_ChaosMage		Orendi	- 220
SK_C015_SunPriestess		Ambra	- 270
SK_C016_BoyAndDjinn_Aurox	Shayne & Aurox  - 345
SK_C016_BoyAndDjinn_Shayne	Shayne & Aurox  - 349
SK_C017_SpiritMech		ISIC	- 392
SK_C018_SoulCollector		Atticus	- 437
SK_C019_Blackguard		Galilea 	- 496
SK_C020_IceGolem		Kelvin	  - 563
SK_C021_PenguinMech		Tobi	- 548
SK_C022_LeapingLuchador		El Dragon - 638
SK_C023_RogueSoldier		Whiskey Foxtrot	- 455
SK_C024_PapaShotgun		Ghalt	- 518
SK_C025_MutantFist		Mellka  - 14 (prologue)
SK_C026_DarkAssassin		Deande  - 60 (prologue)
SK_C027_TacticalBuilder		Kleeze	- 616

```

[bbtools.rar](https://xentaxbackup.github.io/file/12071_bbtools.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-05T13:12:53+00:00
- Post Title: Battleborn tools

An example of extracted Chaos mage (Orendi):
## Post #3
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2016-06-06T14:26:42+00:00
- Post Title: Battleborn tools

thanks daemon1!
## Post #4
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-06-07T02:46:52+00:00
- Post Title: Battleborn tools

This is great!

Forgive me, but where can I grab this extract.exe? I googled, but go nothing. :/

Thanks
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-07T15:32:24+00:00
- Post Title: Battleborn tools

[http://www.gildor.org/downloads](http://www.gildor.org/downloads)
## Post #6
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-06-08T03:09:49+00:00
- Post Title: Battleborn tools

Thank you!
## Post #7
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-06-08T14:40:58+00:00
- Post Title: Battleborn tools

Awesome tools, thanks!

On another note would it be possible for your next project if you could take a look at the Marvel Heroes .tfc format? Gildor had tried it for a number of years but had failed in creating extraction support for it. Hopefully fresher talent like you would finally get the textures properly?
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-08T15:13:21+00:00
- Post Title: Battleborn tools

> Reply from artworkplay
>
> Hopefully fresher talent like you would finally get the textures properly?

Maybe I will. But I'm not a fresh talent in any way. I was just lurking on the dark side for too long...
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-12T20:32:48+00:00
- Post Title: Battleborn tools

> Reply from artworkplay
>
> if you could take a look at the Marvel Heroes .tfc format?
[viewtopic.php?f=18&t=14460](http://forum.xentax.com/viewtopic.php?f=18&t=14460)
## Post #10
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-06-13T08:01:22+00:00
- Post Title: Battleborn tools

Hey Daemon1, since I loved your stuff on Overwatch I've been looking at "other" stuff you did :p

Since I'm not really into packages and textures, I've got a little question: 

how would you convert the BC7 textures to a format before DX10, or is this because the format from offered by the game has this as a standard, wrapped into a custom format? 
Cause like you said, only supported by Visual Studio, texconv or PhotoShop ( I checked that) 

T.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-13T13:29:21+00:00
- Post Title: Battleborn tools

I'm not sure what are you asking about, but yes, many modern games use BC6 & BC7 compression, that can't be extracted into DX9 formats just because they are new DX10 formats.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-18T11:39:37+00:00
- Post Title: Battleborn tools

Tools updated to support this monstrous thing. 250k+ vertices, 230k+ faces.
## Post #13
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2016-10-01T21:44:28+00:00
- Post Title: Battleborn tools

Hey, I need some help. I can't get the file I need myself, due to not being able to afford battleborn at the moment, so I was wondering if someone could get me the current versions of the following files:

"Character_Textures.tfc" "GD_CornerSneaker_DefaultSkin.dpk" and "GD_CornerSneaker_DefaultSkin.upk"
## Post #14
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2016-10-26T18:31:51+00:00
- Post Title: Battleborn tools

Thanks daemon1, it works great. Is there any way to get the bones?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-26T19:19:20+00:00
- Post Title: Battleborn tools

Sure its possible, but for that, I need to write more code. Do you have the game files? Better if you have the latest update.
## Post #16
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2016-10-26T22:39:31+00:00
- Post Title: Re: Battleborn tools

Yes I do. Is there anything in particular that you need?
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-27T15:13:38+00:00
- Post Title: Re: Battleborn tools

As I understand, this game still not supported by umodel? 

I'll send you a PM
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-31T17:31:00+00:00
- Post Title: Re: Battleborn tools


## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-31T19:35:17+00:00
- Post Title: Re: Battleborn tools

Getting the skeletons
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-01T17:49:15+00:00
- Post Title: Re: Battleborn tools

and textures
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-01T19:51:30+00:00
- Post Title: Re: Battleborn tools

Bones work.
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-09T17:20:17+00:00
- Post Title: Re: Battleborn tools

all files decrypted.
## Post #23
- Username: redtank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 28, 2016 3:15 am
- Post datetime: 2016-12-13T19:34:18+00:00
- Post Title: Re: Battleborn tools

great work dude! but how we can get latest tools?
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-13T20:23:57+00:00
- Post Title: Re: Battleborn tools

sorry i forgot to post them. give me some time
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-17T07:16:01+00:00
- Post Title: Re: Battleborn tools

Model tool updated. 

It now extracts model into 3 formats: .OBJ, .SMD and .ASCII. Only SMD file will have proper skeleton connected to bones. If NameTable.txt produced by Extract.exe will be in the same folder, bones will have proper names.
## Post #26
- Username: redtank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 28, 2016 3:15 am
- Post datetime: 2017-01-05T19:20:05+00:00
- Post Title: Re: Battleborn tools

It that animation can be export as well? I got branch of .animsequence files after extract, but have no idea how to handle them.
Battleborn_model.exe not works with anim files.

got .animset files as well, seem they orgnaized on a typical Unreal3 way, if i can re-pack them into UPK may work but don't know how...

looking for someone help!
## Post #27
- Username: redtank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 28, 2016 3:15 am
- Post datetime: 2017-01-06T15:13:53+00:00
- Post Title: Re: Battleborn tools

> Reply from daemon1
>
> Model tool updated. 

It now extracts model into 3 formats: .OBJ, .SMD and .ASCII. Only SMD file will have proper skeleton connected to bones. If NameTable.txt produced by Extract.exe will be in the same folder, bones will have proper names.
123
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-21T19:12:23+00:00
- Post Title: Re: Battleborn tools


## Post #29
- Username: redtank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 28, 2016 3:15 am
- Post datetime: 2017-01-26T18:47:22+00:00
- Post Title: Re: Battleborn tools

> Reply from daemon1
>
> 
can you point me out how to export animations?
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-26T18:56:27+00:00
- Post Title: Re: Battleborn tools

this is not possible now
## Post #31
- Username: KV5
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 05, 2017 7:37 am
- Post datetime: 2017-02-14T18:42:02+00:00
- Post Title: Re: Battleborn tools

I can't seem to find Beatrix's model in the files. Can find everyone else just fine.
## Post #32
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-20T09:45:33+00:00
- Post Title: Re: Battleborn tools

I can't find Beatrix either, along with Alani, Kid Ultra, Ernest and Pendles, which is weird. Any chance someone could help?

EDIT: Well I've found Kid Ultra in SR_0014 files, Pendles in SR_0007 files and Ernest in SR_0010 files, dunno about textures yet and can't get Beatrix or Alani yet either.
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-20T15:16:15+00:00
- Post Title: Re: Battleborn tools

Beatrix files are still encrypted.
## Post #34
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-20T15:36:37+00:00
- Post Title: Re: Battleborn tools

Is Alani's files encrypted too? I saw you posted a pic of her along with the other 3 I couldn't find at first on the last page.
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-20T15:42:15+00:00
- Post Title: Re: Battleborn tools

> Reply from TRDaz
>
> Is Alani's files encrypted too?

Sorry, I don't remember. But surely I could post pics, because I can decrypt files.
## Post #36
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-20T15:46:19+00:00
- Post Title: Re: Battleborn tools

That's okay, I might have just overlooked her files, thanks anyway!
## Post #37
- Username: pirana
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 04, 2017 8:07 am
- Post datetime: 2017-05-04T02:55:36+00:00
- Post Title: Re: Battleborn tools

Hey I can't find the texture or model files(skeletal mesh files) for any of the dlc characters so any help in this matter would be much appreciated.
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-05T15:47:09+00:00
- Post Title: Re: Battleborn tools

they may encrypt them again. Any new characters or what?
## Post #39
- Username: pirana
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 04, 2017 8:07 am
- Post datetime: 2017-05-06T02:00:32+00:00
- Post Title: Re: Battleborn tools

I'm referring to the characters Alani, pendles, beatrix, kid ultra, and ernest but like I say I have no idea where the model or texture files are for these characters unless I'm searching in the wrong place but I can find the other characters just fine.
## Post #40
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-05-10T07:47:24+00:00
- Post Title: Re: Battleborn tools

They are in unnamed files, I found Kid Ultra, Pendles and Ernest but never managed to get Alani or Beatrix since they were encrypted I believe.
Pendles - SR_0007
Ernest - SR_0010
Kid Ultra - SR_0014
Unpack those files and one of them will have what you want.
## Post #41
- Username: ZeichenZwerg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 07, 2021 1:58 am
- Post datetime: 2021-01-20T16:15:23+00:00
- Post Title: Re: Battleborn tools

Hello, I'm new here.
I know this is already a few years old but since they were shutting down Battleborn on the 25th of January i wanted to save me a few of the characters for things like VRChat and stuff like this. That was also the main reason why I created a account here.
Extracting the characters and textures worked well - thanks for that so far.

But there is one thing - Is it possible to also get the meshes from .StaticMesh data? Because for some of the characters their weapons and stuff is just saved as .StaticMesh.

I already looked around but didn't found a tool here that could do it or for which im not stupid   
So i just wanted to ask - is there even a tool or a possibility to get the meshes out of these files? Or am I wasting my time with it?

Thanks in advance
