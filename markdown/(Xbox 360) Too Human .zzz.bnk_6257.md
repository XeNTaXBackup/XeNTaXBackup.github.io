## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-03-20T18:03:00+00:00
- Post Title: (Xbox 360) Too Human .zzz/.bnk

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Annatar
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 18, 2011 1:17 am
- Post datetime: 2011-03-21T18:41:10+00:00
- Post Title: (Xbox 360) Too Human .zzz/.bnk

Yes, this game is good, wonderful mix of fiction and mythology. They completely rebuilt Unreal Engine, and call it Silicon Knights Engine. I also interested in this game, it would be cool if someone could extract meshes.
## Post #3
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-03-29T20:41:16+00:00
- Post Title: (Xbox 360) Too Human .zzz/.bnk

yes, the game is built on UE3.
[viewtopic.php?f=21&t=3914](http://forum.xentax.com/viewtopic.php?f=21&t=3914)
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-03-30T06:55:24+00:00
- Post Title: (Xbox 360) Too Human .zzz/.bnk

Hi! Before I create topic here, I spoke with Gildor about Too Human, and that's what he said: "Hello. Should disappoint you I have not seen in this engine absolutely nothing from Unreal. Support for this game with umodel is impossible." So this is not Unreal game - that's for sure!
## Post #5
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-03-30T18:45:38+00:00
- Post Title: (Xbox 360) Too Human .zzz/.bnk

Google Silicon Knights vs Epic in relation to Unreal Engine Costs and Damages. Also, extract the files from the Too Human disk (as I have) and you'll see the same file structure as all UE games, as well if you look through the config files, not only are they in UE3 format but the indexes for Unreal editor are contained within. For example, these are the files contained in the main Config folder:
TH1Combat.ini
TH1Editor.ini
TH1Engine.ini
TH1Game.ini
TH1Input.ini
I have included them in an attachment, extract the rar and open the .ini 's in notepad or an equivalent.
[TooHuman Config Folder.rar](https://xentaxbackup.github.io/file/4139_TooHuman Config Folder.rar)
## Post #6
- Username: gildor
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 25, 2010 5:15 am
- Post datetime: 2011-06-18T07:13:48+00:00
- Post Title: (Xbox 360) Too Human .zzz/.bnk

This game do not use any code from the Unreal engine.
## Post #7
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2013-07-15T02:17:24+00:00
- Post Title: (Xbox 360) Too Human .zzz/.bnk

Hello  

Any new for this game?

Files. ZZZ contains references for unreal code:

[quote]FUnrealFaceFXMaterialParameterNode
FUnrealFaceFXMaterialParameterNode
FxCombinerNode
FxBonePoseNode[/quote]

standard Unreal shader:
[quote]..."FUnrealFaceFXMaterialParameterNode...\............MAT_Left_Smile_Line......?€........................Left_Smile........linear........?
.......ÿÿÿÿ............Earth........linear........
?.......ÿÿÿÿ..................Material_Slot_Id......
[/quote]

[quote]....AccLightColours.................AccLightDirections.LocalToWorld.................SkyColor.«««................
TimeInfo.«««................UserScalarInputs.UserTextures.««................UserVectorInputs.«««................ps_3_0.2.0.6995.0.««............[/quote]


EngineLOC

Startup.int
[quote][General]
Run=Run!
FirstTime=Unreal Engine First-Time Configuration
SafeMode=Unreal Engine Safe Mode[/quote]


Core.Int
[quote]
[General]
Product=Unreal
Engine=Unreal Engine
Copyright=Copyright © 2001-2005 Epic Games, Inc. All Rights Reserved.
True=True
False=False
None=None
Yes=Yes
No=No
[/quote]

This game is weird, standard compression UE3 seems to have been replaced by SK "Zlib".

Sorry for my bad English.
## Post #8
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2013-07-15T16:07:51+00:00
- Post Title: (Xbox 360) Too Human .zzz/.bnk

Forum's Rules.
