## Post #1
- Username: SpiritedSpy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 02, 2018 12:34 am
- Post datetime: 2018-05-20T15:49:46+00:00
- Post Title: Ghostbusters the video game firehouse level

Hi, I'm kinda new to this whole game ripping thing and i ran into a snag with one of the levels from ghostbusters the video game. i managed to get all the textures for the firehouse, but actually getting the firehouse seems to be its own problem. see its in a .lvl .sec and .dante format while i can find .lvl decompilers, non of them work with the file and trying to find out what the hell a .sec and .dante are giving me little to no results. so i figured i would reach out to the community for help. seeing as this same website helped me get the ghostbusters out of the game with textures and all, i figured they would have some answers for my problem. here is a .zip with all of the formats that i could get out of the game: 

 firehouse.lvl.zip
Heres The .lvl .dante and .sec files (152.4 KiB) Downloaded 24 times

 

Edit: i should probably mention i have tried using ninja ripper yet it seems to yield incomplete results if anything.
Edit2: with more ripping and digging i have found one more firehouse file, a .bst file. searching yeilded me odd results, but opening it in a text editor gave me a bunch of weird symbols and non-sensical jargain part of me hopes this is mesh data. although i really should give up hope at this point  as ive ripped everything so far and im out of .pod files to extract.
edit3: upon opening a .fbx file in notepad it yeilded similar results to the .bst. the only thing left is trying to see if someone knows how to convert this kind of crap. unfortunately i dont know a single person who does that kind of thing.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-20T18:36:51+00:00
- Post Title: Ghostbusters the video game firehouse level

Hi,

.dante , .lvl and .sec contain ASCII text (open them in wordpad for example) but I can't seem to find mesh data:

```

1  // File version
1684  // VM data size
34631  // VM code size

//-----------------------------------------------------------
BEGIN ASSUMPTIONS
M "(void(@CCharacter,String)) SScriptWalkInfo::eventFunction" 40
M "@CActor SDamageInfo::whoFired" 40
M "@CActor SScriptWalkInfo::destActor" 24
M "bool SScriptWalkInfo::cancelScriptControl" 44
M "EDamageType SDamageInfo::damageType" 4
M "float SDamageInfo::continuousStrength" 20
M "float SDamageInfo::strength" 16
M "float SScriptWalkInfo::atDestTol" 28
M "float SScriptWalkInfo::facingTolInRadians" 36
M "float SScriptWalkInfo::runDistTol" 32
M "float Vector::x" 0
M "float Vector::y" 4
M "float Vector::z" 8
S "sizeof(CActorGroup)" 1068
S "sizeof(SDamageInfo)" 308
S "sizeof(SMaterialVariable)" 72
S "sizeof(SScriptWalkInfo)" 48
M "Vector SDamageInfo::wSourceOfDamage" 24
M "Vector SScriptWalkInfo::orient" 12
M "Vector SScriptWalkInfo::wDest" 0

END ASSUMPTIONS

//-----------------------------------------------------------
BEGIN STRINGS

00000000 "msgmachine"
00000004 "ecto1_lights"
00000008 "void checkpoint_FromIntro()"
0000000C "void checkpoint_Basement()"
00000010 "void checkpoint_fromTimesSquare()"
00000014 "void checkpoint_fromLibrary()"
00000018 "void checkpoint_fromParade()"
0000001C "void checkpoint_fromLostIsland()"
00000020 "void checkpoint_fromAbyss()"
00000024 "None"
00000028 "character/ghostbuster/water_fountain_drink"
0000002C "gadget/proton_beam/ice_beam"
00000030 "gadget/proton_beam/shotgun_fire"
00000034 "character/ghostbuster/vox_shower_react"
...
```

.lvl

```
set-filename = firehouse.pst
Dependencies = <
	animations\\ghostbuster_mocap\\spengler\\facefx\\gb_spengler.fxa
	animations\\ghostbuster_mocap\\stantz\\facefx\\gb_stantz.fxa
	animations\\ghostbuster_mocap\\venkman\\facefx\\gb_venkman.fxa
	animations\\ghostbuster_mocap\\zeddemore\\facefx\\gb_zeddemore.fxa
	animations\\npc\\human\\Ilyssa\\facefx\\ilyssa.fxa
	animations\\npc\\human\\janine\\facefx\\janine.fxa
	art\\_default_env_cube.tga
	art\\_flat_bump.tga
...
```


.sec

```
set-filename = firehouse.pst
Dependencies = <
	animations\\ghostbuster_mocap\\stantz\\facefx\\gb_stantz.fxa
	art\\_default_env_cube.tga
	art\\_flat_bump.tga
	art\\_swatch_gray_000.tga
	art\\blackcube.tga
	art\\invalid_360_texture.tga
	art\\lights\\default_fake_spot.tga
	art\\lights\\default_fake_spot_falloff.tga
	art\\lights\\default_light.tga
	art\\lights\\default_omni_falloff.tga
	art\\lights\\default_spot.tga
	art\\lights\\default_spot_falloff.tga
	art\\lights\\falloff_flashlight.tga
	art\\lights\\spot_flashlight.tga
	art\\lights\\uv_light_falloff.tga
...
```
## Post #3
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-02-27T13:57:01+00:00
- Post Title: Ghostbusters the video game firehouse level

Probably because the mesh, at least most of the props for the firehouse and other levels are stored as .smb format and no one's cracked that.
