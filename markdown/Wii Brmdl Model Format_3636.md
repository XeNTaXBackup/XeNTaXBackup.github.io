## Post #1
- Username: Rimbros
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-06T15:21:54+00:00
- Post Title: Wii Brmdl Model Format

Here is a model converter written bye Kentilan that can read this format and animation files.
This program has no export or import option so I was hoping someone could help out with that.
The forum the author posted at is no longer alive but the author gave me the source code and said I could distribute it or modify it any way I wanted. 
I have attached the code to the post so hopefully something great can come out of this. "custom brawl characters"
Here are some files from the game Arc Rise Fantasia.
The models were originally encrypted but here is a bms script I used to fix that.

```
string HEADER -= 4
string HEADER += \
idstring "RTDP"
endian BIG
get OFF long
get FILES long
get ARCSIZE long
get UNK long
getdstring NULL 0xC
for i = 0 < FILES
set RES_NAME HEADER
getdstring NAME 0x20
string RES_NAME += NAME
get SIZE long
get OFFSET long
math OFFSET += OFF
filexor 0x55
log RES_NAME OFFSET SIZE
filexor ""
next i

```

[](http://img145.imageshack.us/img145/2541/arc1.jpg)

[http://www.MegaShare.com/1311000](http://www.MegaShare.com/1311000)

Thanks in advance 
[files.rar](https://xentaxbackup.github.io/file/2261_files.rar)
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-26T14:12:48+00:00
- Post Title: Wii Brmdl Model Format

I'm interesting in this. Spending a lot of time to find any releases of tool that can convert Brmdl models, and find [this](http://www.facepunch.com/showpost.php?p=11045663&postcount=1287).

There is are source code for converter from wii model format to fbx (it's very native to most popular 3d apps and support bones  ). But source prepared just for Linux and couldn't compiled it on my window7:( 

2 chrrox:
So what can we do with this? Do you know any specialists whose can creating a converter?
## Post #3
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-27T08:06:23+00:00
- Post Title: Wii Brmdl Model Format

I know that Kryal from the SmashBoards almost finished a model importer/exporter for BrawlBox, which is a program he created to assist in hacking various things for Super Smash Bros. Brawl, before he just spontaneously gave up. As of the latest version's source code that he uploaded, it can export MDL0/BRMDL files into a DAE format (which only seem to work with Maya as far as I know).

I'm still kinda surprised that you only need to modify a few bytes in a BRMDL file to be able to convert it to a usable format.

(And that was kind of a large bump, but oh well.)
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-27T09:43:17+00:00
- Post Title: Wii Brmdl Model Format

> Reply from RandomTBush
>
> I know that Kryal from the SmashBoards almost finished a model importer/exporter for BrawlBox, which is a program he created to assist in hacking various things for Super Smash Bros. Brawl, before he just spontaneously gave up. As of the latest version's source code that he uploaded, it can export MDL0/BRMDL files into a DAE format (which only seem to work with Maya as far as I know).

I'm still kinda surprised that you only need to modify a few bytes in a BRMDL file to be able to convert it to a usable format.

(And that was kind of a large bump, but oh well.)
You see,
many games (many-many) games interesting for me (and if quality of those game's models are good it's better for me  ) on wii console use this format, and would be grate if such kind of tool release on windows.
because I know that people on facepunch already use ssbb to fbx converter on linux.

So, RandomTBush, you talking about "modifying a few bytes" ,  any luck to see ssbb to fbx converter on windows?
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-28T10:42:34+00:00
- Post Title: Wii Brmdl Model Format

I've got some interest in this, because console-spanning formats make me happy. Given the source code that's been posted, writing an importer for my Windows toolset (which means export of brmdl to COLLADA/SMD/md5mesh/etc.) should be trivial. I'll add it to the todo list, after I wrap up some loose ends for Tekken 6 and some Capcom formats that I'm currently working on.

Writing an exporter may be less trivial, I won't know until I actually look into the format and see how many details are fully fleshed out in that previewer's code. I have no way to test such a thing, either, since I don't have a way to run modified GameCube/Wii images. So it'd just be a matter of exporting it, seeing if other PC tools can load it, and praying that things are actually set up right for proper games to be able to load it. I imagine custom Smash Bros. characters would be a huge thing for the world to enjoy, though, so it's worth looking into.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-28T13:20:46+00:00
- Post Title: Wii Brmdl Model Format

> Reply from MrAdults
>
> I've got some interest in this, because console-spanning formats make me happy. Given the source code that's been posted, writing an importer for my Windows toolset (which means export of brmdl to COLLADA/SMD/md5mesh/etc.) should be trivial. I'll add it to the todo list, after I wrap up some loose ends for Tekken 6 and some Capcom formats that I'm currently working on.

Writing an exporter may be less trivial, I won't know until I actually look into the format and see how many details are fully fleshed out in that previewer's code. I have no way to test such a thing, either, since I don't have a way to run modified GameCube/Wii images. So it'd just be a matter of exporting it, seeing if other PC tools can load it, and praying that things are actually set up right for proper games to be able to load it. I imagine custom Smash Bros. characters would be a huge thing for the world to enjoy, though, so it's worth looking into.

Oh,_it's_grate_news!_Actualy_Smash_Bros_already_modifying_on_smashboars_and_facepunch_forums  

p.s.:_i'm_interesting_in_tekken_6_game_models_to  

p.p.s.:_already_start_buying_wii-games  

p.p.p.s.:_sorry_for_my_---(_)---style,_on_this_computer_don't_work_spacebar
## Post #7
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-28T22:34:20+00:00
- Post Title: Wii Brmdl Model Format

So there's already an exporter? Then, why did you resurrect this thread? The exporter is Linux-only or something?
## Post #8
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-29T01:11:42+00:00
- Post Title: Wii Brmdl Model Format

Weren't the Twilight Princess models packaged in brmdl format? 

Isn't there likewise a program named brmView or something?
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-29T14:49:54+00:00
- Post Title: Wii Brmdl Model Format

> Reply from MrAdults
>
> So there's already an exporter? Then, why did you resurrect this thread? The exporter is Linux-only or something?

Yes export ONLY on Linux systems, i asking everywhere and everyone, no one haven't windows compatible converter.

By the way, i found game-list with mdl0 models:
Animal Crossing: City Folk
- (The models are packed in ARC files and need to be exported with an external program.)
Arc Rise Fantasia
- (The models are compressed and either need to be decompressed using this QuickBMS script, or dumped from Dolphin's memory.)
Arkanoid Plus [WiiWare]
Bomberman Blast [WiiWare]
- (The models are packed in ARC files and need to be exported with an external program.)
Bleach: Versus Crusade
- (Models are almost the right size. They need to be scaled 1.3x-1.55x their original size.)
Bubble Bobble Plus [WiiWare]
- (Files are compressed strangely and need to be extracted using a memory dump from Dolphin.)
Captain Rainbow
Case Closed: The Mirapolis Investigation
Castlevania Judgment
- (Models are small and need to be scaled to 11x [?] their original size.)
Cooking Mama
Dead Rising: Chop 'Till You Drop
- (Read this post for more info on that.)
Dewey's Adventure
- (The models are packed in ARC files and need to be exported with an external program.)
Dragon Ball: Revenge of King Piccolo
- (The models all have generic filenames, and are packed in uncompressed *.BIN files. A full list of what they actually are is on this post.)
Dragon Quest Swords: The Masked Queen and the Tower of Mirrors
- (The models are packed in FPK files and need to be exported using an external program. Also, the MDL0 doesn't really need to be corrected?)
Elebits
Final Fantasy Crystal Chronicles: My Life as a Dark Lord [WiiWare]
Final Fantasy Crystal Chronicles: My Life as a King [WiiWare]
Final Fantasy Fables: Chocobo's Dungeon
- ("Just delete the first 8 bytes in red but DON'T delete the others. Then, add 8 F's instead of 12." - Me_Aludes)
Fullmetal Alchemist: Daughter of the Dusk
Fullmetal Alchemist: Prince of the Dawn
Furu Furu Park
- (The models are packed in *.BIN files, but they're not compressed. Also, the models don't need any hexing other than Step 5.)
Kamen Rider: Climax Heroes W
Klonoa
Mario and Sonic at the Olympic Winter Games
- (The models are packed in CPK files and need to be exported with an external program. Also, the heads are separate from the bodies for the mid/high-poly models, and both the textures and material properties need to be modified to make them not so dark.)
Mario Kart Wii
- (Normals seem to be screwed up, though.)
Monster Hunter Tri
My Pokemon Ranch [WiiWare]
- (Files are compressed strangely and need to be extracted using a memory dump from Dolphin.)
Naruto: Clash of Ninja Revolution
Naruto: Clash of Ninja Revolution 2
Naruto Shippuden: Gekitou Ninja Taisen! EX 3
- (Models are small and need to be scaled to 11x their original size.)
Naruto Shippuden: Ryujinki
New Super Mario Bros. Wii
- (The models are packed in ARC files and need to be exported with an external program. Also the models are large need to be scaled to 0.25x [?] their original size.)
NiGHTS: Journey of Dreams
Oneechanbara: Bikini Zombie Slayers
Pokemon Rumble [WiiWare]
- (Files are compressed strangely and need to be extracted using a memory dump from Dolphin.)
Pokepark Wii: Pikachu's Big Adventure?
- (The list of Pokemon in this game is on this post.)
Rainbow Islands: Towering Adventure [WiiWare]
Resident Evil: Darkside Chronicles
Resident Evil: Umbrella Chronicles
- (The models are packed in ARC files and need to be exported with an external program. This post has a listing of what each model is.)
Samba de Amigo
Simple Wii Series Vol. 6: The Waiwai Combat [Confirmation, please? They apparently have to be extracted from Dolphin's memory dump.]
Sin & Punishment 2: Successor to the Sky
- (The models are packed in ARC files and need to be exported with an external program.)
Soul Eater: Monotone Princess
Space Invaders Get Even [WiiWare]
- ("Just delete the first 8 bytes in red but DON'T delete the others. Then, add 8 F's instead of 12." - Me_Aludes)
Super Smash Bros. Brawl
Suzumiya Haruhi no Gekidou
- (The characters' parts are in separate MDL0s -- body, skirt, hair, left eye, right eye, mouth and eyebrows.)
Tales of Symphonia: Dawn of the New World
- (The bone tree seems to be really screwed up, but it works fine when exporting.)
Tatsunoko vs. Capcom
- (The models are packed in FPK files and need to be exported using an external program. Also, the models are small and need to be scaled to 11x [?] their original size.)
Tenchu: Shadow Assassins
Toshinden
Trauma Center: New Blood
Wario Land: Shake It/The Shake Dimension
- (The files need to be extracted from the game's GFA files. Looking into how to do so right now. Also unconfirmed for the moment.)
Wario Ware: Smooth Moves
Wii Fit Plus
- (Wii Fit might also use MDL0s?)
Wii Sports Resort
Yu-Gi-Oh! 5D's Wheelie Breakers
Zack & Wiki: Quest for Barbaros' Treasure
- ("Just delete the first 8 bytes in red but DON'T delete the others. Then, add 8 F's instead of 12." - Me_Aludes)

List of known games that DO NOT have MDL0 files:

A Boy and His Blob (Obviously, the game's 2D!)
Bleach: Shattered Blade (*.ACT, *.AI, *.SMS)
Boom Blox
Bully: Scholarship Edition (*.MXD)
Crash of the Titans (*.P3D)
Dead Space: Extraction (Unfamiliar file formats)
De Blob
Donkey Kong Barrel Blast (*.DAT)
DragonBall Z: Budokai Tenkaichi 3
ExciteBots
Final Fantasy Crystal Chronicles: The Crystal Bearers (Packed in *.DAT/*.POS files)
Final Fantasy Crystal Chronicles: Echoes of Time (Unfamiliar file formats)
Godzilla: Unleashed (*.BDG)
Guitar Hero: Aerosmith (*.NGC)
Harvest Moon: Animal Parade (*.CMP)
Harvest Moon: Magical Melody (*.CDT)
Indiana Jones and the Staff of Dreams (*.WII)
Kung-Fu Panda (*.APK/*.LXB)
Kung-Fu Panda: Legendary Warriors (*.SBK/*.WII)
The Legend of Spyro (*.KRV)
LostWinds [WiiWare]
MadWorld (*.DAT w/ cryptic names)
Mario and Sonic at the Olympic Games (CDDATA.DIG)
Marvel Super Hero Squad (*.TRB)
Metroid Prime 3: Corruption (*.PAK)
Nicktoons: Globs of Doom (*.TRB)
No More Heroes
No More Heroes 2: Desperate Struggle (GCT0?)
NyxQuest [WiiWare]
Okami (Packed in *.AFS files)
One Piece: Unlimited Adventure (*.AAR)
One Piece: Unlimited Cruise Episode 1 (*.AAR)
One Piece: Unlimited Cruise Episode 2 (*.AAR)
Pokemon Battle Revolution (*.FSYS)
Pikmin 2 (*.SZS/*.BDL?)
Pirates vs Ninjas Dodgeball
Punch-Out!! (*.DATA)
Rayman: Raving Rabbids: TV Party 
Rune Factory Frontier (*.MOD)
Sam & Max: Season One (*.TTARCH)
Sega Superstars Tennis (Everything is in one PAC file)
Silent Hill: Shattered Memories (DATA.ARC/IGC.ARC)
Sonic and Sega All-Stars Racing (*.SIF/*.SIG)
Sonic and the Black Knight (*.ONE)
Sonic and the Secret Rings (*.ONE)
Sonic Riders: Zero Gravity (*.CVMH)
Sonic Unleashed (*.ONZ)
Soul Calibur Legends (*.TOM/*.FIM)
Super Monkey Ball: Banana Blitz
Super Mario Galaxy (*.BDL)
Super Mario Galaxy 2 (*.BDL)
Super Paper Mario (*.DATA)
Super Robot Wars NEO
Suzumiya Haruhi no Heiretsu
Star Wars: The Force Unleashed
Strong Bad's Cool Game For Attractive People [WiiWare]
Tales of Graces (Can't find any model files)
Tales of Monkey Island [WiiWare]
Teenage Mutant Ninja Turtles: Smash-Up (*.PAC, but not the same as Brawl's PAC files)
The Legend of Zelda: Twilight Princess (*.BMD)
## Post #10
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-05-29T15:46:02+00:00
- Post Title: Wii Brmdl Model Format

their is already a window BRRES package viewer / exporter on windows  ported by Kentilan

brmdl is a part of the brres wii package and describe geometry 
brres can also contain brtex (texture in wii format)
brres can also contain branm (animations)
etc...

the actual version can load the brres package , list it content, display the geometry with textures and play animations
it allow export to psa/psk and/or md5mesh format actually..

older version + source can be found here :
[http://forums.ngemu.com/dolphin-discuss ... mping.html](http://forums.ngemu.com/dolphin-discussion/123061-model-dumping.html)
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-29T16:32:35+00:00
- Post Title: Wii Brmdl Model Format

> Reply from shadowmoy
>
> their is already a window BRRES package viewer / exporter on windows  ported by Kentilan

brmdl is a part of the brres wii package and describe geometry 
brres can also contain brtex (texture in wii format)
brres can also contain branm (animations)
etc...

the actual version can load the brres package , list it content, display the geometry with textures and play animations
it allow export to psa/psk and/or md5mesh format actually..

older version + source can be found here :
http://forums.ngemu.com/dolphin-discuss ... mping.html
Yes, i know this page, I've being there, but nothing from this page can't export models to psa/psk and/or md5mesh, even mdlviewer_v14_source.rar. But.. maybe i wrong, and you correct me?
## Post #12
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-29T17:34:13+00:00
- Post Title: Wii Brmdl Model Format

> Reply from Satoh
>
> Weren't the Twilight Princess models packaged in brmdl format? 

Isn't there likewise a program named brmView or something?Twilight Princess's models are actually BMD/BDL, which is the other known GameCube/Wii format. I've checked, and there are no relation between the two formats.

> Reply from Tosyk
>
> By the way, i found game-list with mdl0 models:

*insert list here*Hah hah, that's my list from the SmashBoards. There certainly are a lot of games with the same model format, aren't there? 

You could probably just simplify the list to this, though, taking out all the notes and the games that don't have MDL0s:
Animal Crossing: City Folk
Arc Rise Fantasia
Arkanoid Plus [WiiWare]
Bomberman Blast [WiiWare]
Bleach: Versus Crusade
Bubble Bobble Plus [WiiWare]
Captain Rainbow
Case Closed: The Mirapolis Investigation
Castlevania Judgment
Cooking Mama
Dead Rising: Chop 'Till You Drop
Dewey's Adventure
Dragon Ball: Revenge of King Piccolo
Dragon Quest Swords: The Masked Queen and the Tower of Mirrors
Elebits
Final Fantasy Crystal Chronicles: My Life as a Dark Lord [WiiWare]
Final Fantasy Crystal Chronicles: My Life as a King [WiiWare]
Final Fantasy Fables: Chocobo's Dungeon
Fullmetal Alchemist: Daughter of the Dusk
Fullmetal Alchemist: Prince of the Dawn
Furu Furu Park
Kamen Rider: Climax Heroes W
Klonoa
Mario and Sonic at the Olympic Winter Games
Mario Kart Wii
Monster Hunter Tri
My Pokemon Ranch [WiiWare]
Naruto: Clash of Ninja Revolution
Naruto: Clash of Ninja Revolution 2
Naruto Shippuden: Gekitou Ninja Taisen! EX 3
Naruto Shippuden: Ryujinki
New Super Mario Bros. Wii
NiGHTS: Journey of Dreams
Oneechanbara: Bikini Zombie Slayers
Pokemon Rumble [WiiWare]
Pokepark Wii: Pikachu's Big Adventure
Rainbow Islands: Towering Adventure [WiiWare]
Resident Evil: Darkside Chronicles
Resident Evil: Umbrella Chronicles
Samba de Amigo
Simple Wii Series Vol. 6: The Waiwai Combat
Sin & Punishment 2: Successor to the Sky
Soul Eater: Monotone Princess
Space Invaders Get Even [WiiWare]
Super Smash Bros. Brawl
Suzumiya Haruhi no Gekidou
Tales of Symphonia: Dawn of the New World
Tatsunoko vs. Capcom
Tenchu: Shadow Assassins
Toshinden
Trauma Center: New Blood
Wario Land: Shake It/The Shake Dimension
Wario Ware: Smooth Moves
Wii Fit Plus
Wii Sports Resort
Yu-Gi-Oh! 5D's Wheelie Breakers
Zack & Wiki: Quest for Barbaros' Treasure
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-29T17:42:09+00:00
- Post Title: Wii Brmdl Model Format

> Reply from RandomTBush
>
> Satoh wrote:Weren't the Twilight Princess models packaged in brmdl format? 

Isn't there likewise a program named brmView or something?Twilight Princess's models are actually BMD/BDL, which is the other known GameCube/Wii format. I've checked, and there are no relation between the two formats.
Tosyk wrote:By the way, i found game-list with mdl0 models:

*insert list here*Hah hah, that's my list from the SmashBoards. There certainly are a lot of games with the same model format, aren't there?

Yes, you right, list is very useful. So, right now we need just a converter
## Post #14
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-29T17:55:26+00:00
- Post Title: Wii Brmdl Model Format

> Reply from Tosyk
>
> Yes, you right, list is very useful. So, right now we need just a converterAs for a converter, like I had said earlier, [Kryal's BrawlBox v0.64 (beta)](http://www.mediafire.com/download.php?nyrmmgzhtnm) (combined with [fortwaffles's model hexing/correcting program](http://www.mediafire.com/?ngdj2yznyt2)) makes it so you can preview the models and export them to DAE. While it can't port them directly to FBX, the DAE files can always be converted.

Take, for example, the Chocobo from Final Fantasy Fables: Chocobo's Dungeon.


There's a preview from in BrawlBox...


And here's the same model after being exported, in 3DS Max, in wireframe mode to show the bones more easily. Although not shown, the model does, in fact, keep all of its rigging.

While this is for Windows, I'm pretty sure there's a way to get the programs working on Linux.
## Post #15
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-29T18:47:20+00:00
- Post Title: Wii Brmdl Model Format

So just to clarify this...

Brawlbox is a working converter for brmdl models that works on windows.

Correct? Did I read it wrong or is this solved and I can swipe models from TvC now?
## Post #16
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-29T19:29:51+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Satoh
>
> So just to clarify this...

Brawlbox is a working converter for brmdl models that works on windows.

Correct? Did I read it wrong or is this solved and I can swipe models from TvC now?Yes, BrawlBox is a working converter. However, there's a weird glitch where you have to preview the model before exporting it to get it to put the vertices in the right spot, but other than that, it works really well.


(Please excuse the few errors in the render. It's a rough pose I set up in a few minutes.)

So, yeah, you can get the models from Tatsunoko vs. Capcom now.
## Post #17
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-29T20:36:57+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from RandomTBush
>
> Satoh wrote:So just to clarify this...

Brawlbox is a working converter for brmdl models that works on windows.

Correct? Did I read it wrong or is this solved and I can swipe models from TvC now?Yes, BrawlBox is a working converter. However, there's a weird glitch where you have to preview the model before exporting it to get it to put the vertices in the right spot, but other than that, it works really well.


(Please excuse the few errors in the render. It's a rough pose I set up in a few minutes.)

So, yeah, you can get the models from Tatsunoko vs. Capcom now.
Yes, seems everything works fine. Just testing, from Dead Rising Chop Till You Drop:

[](http://s58.radikal.ru/i161/1005/59/ff717afe8858.jpg) [](http://i058.radikal.ru/1005/89/ec43bef0ed0b.jpg)

but, to do this we need at least four program  + texture converter.
So maybe MrAdults have some ideas how to make converting process more shorter?
## Post #18
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-29T22:44:58+00:00
- Post Title: Re: Wii Brmdl Model Format

Now I just need to get a copy of Tatsunoko v Capcom... and figure out how to read the disc... and... figure out how to find the right models... I'm already 5% there!
## Post #19
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-29T22:54:47+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Tosyk
>
> Yes, seems everything works fine. Just testing, from Dead Rising Chop Till You Drop:

 

but, to do this we need at least four program  + texture converter.
So maybe MrAdults have some ideas how to make converting process more shorter?Well, what format would you need to convert the textures to? Because BrawlBox can convert them to PNG, TGA, TIFF, BMP, JPG or even GIF. If it's something like VTF, then yeah, you'd need another texture converter.

Anyway, glad you were able to get it working, because a few individuals at the SmashBoards who asked for my assistance never got it working, even when I gave them a step-by-step.
## Post #20
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-29T23:17:56+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from RandomTBush
>
> Tosyk wrote:Yes, seems everything works fine. Just testing, from Dead Rising Chop Till You Drop:

 

but, to do this we need at least four program  + texture converter.
So maybe MrAdults have some ideas how to make converting process more shorter?Well, what format would you need to convert the textures to? Because BrawlBox can convert them to PNG, TGA, TIFF, BMP, JPG or even GIF. If it's something like VTF, then yeah, you'd need another texture converter.

Anyway, glad you were able to get it working, because a few individuals at the SmashBoards who asked for my assistance never got it working, even when I gave them a step-by-step.

The tool is really awesome  But the problem is not in textures, tga it's perfect, problem is on 3 small additional program (i'm talking about mdl0headerfix.exe, mdl0matfix.exe and mdl0polyfix.exe).
Maybe there is a way insert them directly into the BrawlBox, because i need working with all this tools to converting model just one into dae-format.
One more thing: default exporting texture format is png, how can i change this to tga. Or maybe i can extract all textures in one/two click?
## Post #21
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-29T23:25:44+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Tosyk
>
> The tool is really awesome  But the problem is not in textures, tga it's perfect, problem is on 3 small additional program (i'm talking about mdl0headerfix.exe, mdl0matfix.exe and mdl0polyfix.exe).
Maybe there is a way insert them directly into the BrawlBox, because i need working with all this tools to converting model just one into dae-format.
One more thing: default exporting texture format is png, how can i change this to tga. Or maybe i can extract all textures in one/two click?The only program out of those three that needs to be used to be able to export models is MDL0HeaderFix.exe. The other two (MDL0PolyFix.exe and MDL0MatFix.exe) are only used for converting the models so that they can be used in Super Smash Bros. Brawl, so you don't really need to run those.

And as for extracting all of the textures at once, you can click on the top where it has the red icon with "BRES" on it and the name of the file and select "Export All". That will extract all of the textures (in PNG, though) and the MDL0 file into a folder of your choice. If you want them in TGA, just select one texture at a time (which might be tedious for models with several textures and put ".TGA" at the end. I'll see if I know how the source code works and make it export to TGAs by default.
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-29T23:33:10+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from RandomTBush
>
> Tosyk wrote:The tool is really awesome  But the problem is not in textures, tga it's perfect, problem is on 3 small additional program (i'm talking about mdl0headerfix.exe, mdl0matfix.exe and mdl0polyfix.exe).
Maybe there is a way insert them directly into the BrawlBox, because i need working with all this tools to converting model just one into dae-format.
One more thing: default exporting texture format is png, how can i change this to tga. Or maybe i can extract all textures in one/two click?The only program out of those three that needs to be used to be able to export models is MDL0HeaderFix.exe. The other two (MDL0PolyFix.exe and MDL0MatFix.exe) are only used for converting the models so that they can be used in Super Smash Bros. Brawl, so you don't really need to run those.

And as for extracting all of the textures at once, you can click on the top where it has the red icon with "BRES" on it and the name of the file and select "Export All". That will extract all of the textures (in PNG, though) and the MDL0 file into a folder of your choice. If you want them in TGA, just select one texture at a time (which might be tedious for models with several textures and put ".TGA" at the end. I'll see if I know how the source code works and make it export to TGAs by default.

Only grate news today   Thank you.
## Post #23
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-30T19:49:31+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Satoh
>
> Now I just need to get a copy of Tatsunoko v Capcom... and figure out how to read the disc... and... figure out how to find the right models... I'm already 5% there!
I can upload all extracted characters from Tatsunoko Vs Capcom Ultimate All Stars.
## Post #24
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-05-30T23:41:33+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Tosyk
>
> ...I can upload all extracted characters from Tatsunoko Vs Capcom Ultimate All Stars.

With bones???
## Post #25
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-31T00:10:14+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from grotesque
>
> Tosyk wrote:...I can upload all extracted characters from Tatsunoko Vs Capcom Ultimate All Stars.

With bones???

of course, with bones, source models only. You need only convert them.
## Post #26
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-05-31T01:23:12+00:00
- Post Title: Re: Wii Brmdl Model Format

But for convert I have to use linux, it's right?
I'm new about this "work", sorry
## Post #27
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-31T01:49:24+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from grotesque
>
> But for convert I have to use linux, it's right?
I'm new about this "work", sorry

I don't know about Linux, because i'm windows user, so i can include all necessary tools (all for windows):

FPKextractor.exe - for extracting .fpk files
BrawlBox - for open and converting .brres files
mdl0headerfix.exe - for fixing header of .brres files

1. extract .fpk files of character that you want to convert
2. open .brres file of character with small app mdl0headerfix.exe to modifying it header. For example:

```
\chr\bat\0000_fpk\chr\bat\0000.brres
```
3. open .brres with BrawlBox
4. Export all stuff you need from BrawlBox by clicking Right Mouse on what you want to convert. For example, model (sorry for non-English windows  ):
[](http://s53.radikal.ru/i142/1005/8b/2bcc7d867b1a.jpg)
5. you get .dae model with bones and textures

Alex
[](http://s45.radikal.ru/i109/1005/1d/25e8287e657c.jpg)

Add:
[All characters and programs](http://www.sendspace.com/file/feslzm)
## Post #28
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-05-31T12:46:43+00:00
- Post Title: Re: Wii Brmdl Model Format

Thanks Tosyk, downloading now  

EDIT:

I have a little problem, I think is a mdl0headerfix.exe problem.
I run this program only with double click, and after a little program close.
In 3ds max I see .dae like this
[](http://img707.imageshack.us/my.php?image=immagine1ju.jpg)
## Post #29
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-01T04:52:35+00:00
- Post Title: Re: Wii Brmdl Model Format

Use the mdl0headerfix program on the brres file, not the DAE.

I've noticed some models don't like to load in Maya. Zero doesn't want to open, but I suppose that's fine since I have his X8 model anyway.

In Maya, I don't know if it's true for max or not, but the models have broken skeletons. The rigging is lost upon loading in Maya.

This is all about TvC I should mention. In any case: Thank you very much Tosyk.
## Post #30
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-01T07:38:19+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from grotesque
>
> Thanks Tosyk, downloading now  

EDIT:

I have a little problem, I think is a mdl0headerfix.exe problem.
I run this program only with double click, and after a little program close.
In 3ds max I see .dae like this
I think there is no problem here, you need select all in scene, delete first frame of animation (it help hide bounding boxes) and zooming what you have in scene.

NOTE: When I import to 3d max from collada .dae I see the same what you see.
## Post #31
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-01T14:39:19+00:00
- Post Title: Re: Wii Brmdl Model Format

here is what you are all searching to export/view wii brres,arc and brmdl files (renamed brres files)
thanks to Kentilan , yes she does a great work ^^

please read the readme.txt 

[http://www.sendspace.com/file/15lhuu](http://www.sendspace.com/file/15lhuu)
## Post #32
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-06-03T20:54:49+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from shadowmoy
>
> here is what you are all searching to export/view wii brres,arc and brmdl files (renamed brres files)
thanks to Kentilan , yes she does a great work ^^

please read the readme.txt 

http://www.sendspace.com/file/15lhuu
Ah, that seems to work well, and probably would have a better range of 3D modelling programs that would support that format (PSK/MD5). So that would be a better choice for those of you who want to extract the models.
## Post #33
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-16T02:51:03+00:00
- Post Title: Re: Wii Brmdl Model Format

Very nice thanks for share
## Post #34
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-09-04T13:09:58+00:00
- Post Title: Re: Wii Brmdl Model Format

Sorry to wake up this topic, but is there any progress on a 3D-Format to MDL0 converter yet?
Just wondering...
## Post #35
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-07T15:32:19+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from shadowmoy
>
> here is what you are all searching to export/view wii brres,arc and brmdl files (renamed brres files)
thanks to Kentilan , yes she does a great work ^^

please read the readme.txt 

http://www.sendspace.com/file/15lhuu

I'd just like to thank you for this. It is so much easier to use than the messy DAE of Brawlbox.
## Post #36
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2010-09-20T17:47:50+00:00
- Post Title: Re: Wii Brmdl Model Format

that is how I will find this model

[http://images1.wikia.nocookie.net/__cb2 ... Trophy.jpg](http://images1.wikia.nocookie.net/__cb20080723001244/ssb/images/5/5d/Naked_Snake_Trophy.jpg)

may be in the format pac
## Post #37
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-12-15T00:42:48+00:00
- Post Title: Re: Wii Brmdl Model Format

Just one question    Suzumiya Haruhi no Gekidou use brres files but Suzumiya Haruhi no Heiretsu use brres files too??
## Post #38
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-15T18:50:02+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from FEATHER
>
> Just one question    Suzumiya Haruhi no Gekidou use brres files but Suzumiya Haruhi no Heiretsu use brres files too??
Ok
## Post #39
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-12-15T22:04:10+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from FEATHER
>
> Just one question    Suzumiya Haruhi no Gekidou use brres files but Suzumiya Haruhi no Heiretsu use brres files too??I don't think it does. I did a memory dump of the game using Dolphin, and I found no trace of "MDL0" anywhere in the file.

Anyway, to bring this topic up to date, in addition to the ones listed on the 9th post in this topic, these games also use the Wii's common model format:

Ivy the Kiwi?
Kamen Rider: Climax Heroes OOO
Kirby: Epic Yarn
Mario Sports Mix
Metroid: Other M
Naruto Shippuden: Gekitou Ninja Taisen SP
Sonic Colors / Sonic Colours
Teenage Mutant Ninja Turtles: Smash-Up
Wii Music
Wii Party
Wii Play
Wii Sports
Xenoblade

For a few of them (like TMNT Smash-Up and Mario Sports Mix), the best way to obtain them is through memory dumps, as the files are compressed otherwise.
## Post #40
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-12-15T22:22:19+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from youngmark
>
> FEATHER wrote:Just one question    Suzumiya Haruhi no Gekidou use brres files but Suzumiya Haruhi no Heiretsu use brres files too?? 
Ok
I think that pic is from Suzumiya Haruhi no Gekidou... In that game there isn't Kyon model...
## Post #41
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-12-16T08:33:01+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from FEATHER
>
> I think that pic is from Suzumiya Haruhi no Gekidou... In that game there isn't Kyon model...Yes, it is. I recognize that model when I had looked through all of them a few months back.
## Post #42
- Username: bigBear
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Oct 09, 2009 2:51 am
- Post datetime: 2010-12-16T15:37:43+00:00
- Post Title: Re: Wii Brmdl Model Format

Ontopic, its really nice to see people are using their time
with this kinda coding/programmerings.
Consoles/handhelds have more games than the PC.
So it would be awesome to get the models/contents from the consoles.

Offtopic, why the japs are so obsessed with these anime with big eyes and weird cloths?
Like the above one.
## Post #43
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2010-12-16T22:49:55+00:00
- Post Title: Re: Wii Brmdl Model Format

sky crawlers innocent aces also uses .brmdl I ripped all the models if anyone wants them
## Post #44
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-12-22T09:47:23+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from bigBear
>
> 
Offtopic, why the japs are so obsessed with these anime with big eyes and weird cloths?

Maybe because Osamu Tezuka love so much WALT DISNEY, but it's just my opinion

> Reply from viperzerofsx
>
> sky crawlers innocent aces also uses .brmdl I ripped all the models if anyone wants them

Nice news other game for the list, are there only airplanes models in game?

Just for add one note the models of the Fullmetal Alchemist: Daughter of the Dusk are in FPK containers just google for find the extractor.    

And other random question any "MDL0" in the files of WII Simpsons Game?
## Post #45
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-12-22T10:40:16+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from FEATHER
>
> And other random question any "MDL0" in the files of WII Simpsons Game?I'm gonna say right now that I'm 99% sure that it will not have MDL0s, because of the following rules:

1. It has to be from a Japanese developer.
1b. Either that, or it's a game of a Japanese franchise.
2. It has to be a Wii-exclusive game, not a port of a PlayStation 2 game (such as Okami and DBZ: Budokai Tenkaichi 3).
3. If it's based off of a Gamecube-era engine (like Twilight Princess), then it's most likely gonna have BMD instead.

Every game that has been checked at the Smash Boards has followed these rules. However, so far, Teenage Mutant Ninja Turtles: Smash-Up is the only exception to this rule, mainly because it was developed by Game Arts (the same team that helped make Super Smash Bros. Brawl).
## Post #46
- Username: Xaimill
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 25, 2010 2:35 am
- Post datetime: 2010-12-24T18:54:50+00:00
- Post Title: Re: Wii Brmdl Model Format

Sorry to bother... I know little about all the technicalities spoken here, but I'm interested in model ripping (posing would be optional) for papercraft making... I modelled a basic Zero armor on Maya, but I'd like to give it a shot to Zero's armor from tatsunoko.  Is there some tutorial somewhere that I can learn all that's spoken here?  Thanks in advance

I love how under my name it says Ultra-N00b... it denotes my n00bness on the topic ^^U
## Post #47
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-04T18:13:45+00:00
- Post Title: Re: Wii Brmdl Model Format

Tosyk tell this:
Arc Rise Fantasia
- (The models are compressed and either need to be decompressed using this QuickBMS script, or dumped from Dolphin's memory.)
Have you the QuickBMS script to this files or a post abouth how to dump from Dolphin's memory?

Thanks man.
## Post #48
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-01-04T19:56:42+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Rimbros
>
> Tosyk tell this:
Arc Rise Fantasia
- (The models are compressed and either need to be decompressed using this QuickBMS script, or dumped from Dolphin's memory.)
Have you the QuickBMS script to this files or a post abouth how to dump from Dolphin's memory?

Thanks man.It's right on the very first post of this topic.

Anyway, Okami, Party Fun Pirate/Pop-Up Pirate and Tetris Party also use the MDL0 file format, so that brings the total of games using the common format up to 80.
## Post #49
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-04T20:02:03+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from RandomTBush
>
> Rimbros wrote:Tosyk tell this:
Arc Rise Fantasia
- (The models are compressed and either need to be decompressed using this QuickBMS script, or dumped from Dolphin's memory.)
Have you the QuickBMS script to this files or a post abouth how to dump from Dolphin's memory?

Thanks man.It's right on the very first post of this topic.

Anyway, Okami, Party Fun Pirate/Pop-Up Pirate and Tetris Party also use the MDL0 file format, so that brings the total of games using the common format up to 80.

I download Arc Rise Fantasia, by something reason i can open brresview the textures, but the models cant be openend, the file format of this game its .vol files any idea how to unpack or wath i need rename to read the files?
## Post #50
- Username: kidda11
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 08, 2011 10:04 am
- Post datetime: 2011-01-08T02:11:47+00:00
- Post Title: Re: Wii Brmdl Model Format

where can i download suzimiya haruhi no gekidou models?
## Post #51
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2011-01-08T17:29:43+00:00
- Post Title: Re: Wii Brmdl Model Format

as far as downloading models, this is not the forum/nor the site for which you can "download" models. this forum was specifically made for reverse engineering/modding/tech info sharing. rant aside, well you can get it for yourself. 

via; game disc>iso>wiiscrubber>characterfiles>hexeditor>brresviewer>convert to obj/fbx/dae>your 3d application. there are tons, of ways how, just search the forum how, backread threads.

goodluck!
## Post #52
- Username: serenedays9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 31, 2010 7:43 am
- Post datetime: 2011-01-09T18:31:21+00:00
- Post Title: Re: Wii Brmdl Model Format

yea, pretty much followed those steps to even get it into something like GMod, not perfect but it's in.
[](http://img266.imageshack.us/i/gmtpvpmeadow0000.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)
## Post #53
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-01-10T03:56:49+00:00
- Post Title: Re: Wii Brmdl Model Format

Wow, this was actually some very cool and useful stuff here! Using BRRES viewer+David Najar's PSA toolkit is pretty useful with multiple animation files for a single model. I tested it out and got a pretty perfect PSK and PSA, all textures worked. Thanks a lot for getting all this info. Other than BRMDL, what other Wii model formats can be exported to a fairly global format with animation, texture mapping, and bone data intact? I honestly didn't think this was possible until now.
## Post #54
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-10T06:05:45+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Rimbros
>
> the file format of this game its .vol files any idea how to unpack or wath i need rename to read the files?
are you trying this script in the attach?
[vol_extract.7z](https://xentaxbackup.github.io/file/3786_vol_extract.7z)
## Post #55
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-01-11T11:13:51+00:00
- Post Title: Re: Wii Brmdl Model Format

The Klonoa game is pretty much accessible and models work fine without trouble, however some textures (like for Klonoa's body, the texture for the Moo, etc) are stored in a BRRES file that is in turn inside a BIN file (texture.bin). Removing the extra stuff before "BRRES" proved fruitless and the results are the same using the BMS script geared towards extracting BRRES files.

Throwing this info out there, possibly compressed or encrypted. May need to dump with Dolphin.

Edit: Dumping+Chrrox's brres BMS script gets the decompressed file.
## Post #56
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-01T19:22:26+00:00
- Post Title: Re: Wii Brmdl Model Format

Sorry to bump/double post but might note that Bomberman Blast has problems with the BRRES files/models, possible encryption or scrambling. mdl0headerfix does not repair it.

I can give an example if needed. I have performed a memory dump with dolphin and using the BMS, had to remove a lot of junk data in the dump as well with a hex editor, this gets decrypted brres files. I load them up in brresviewer, and the model is not there and can't export anything but the bones, can load the model in BrawlBox though, but that can only export to DAE which has been a very picky format to convert to other things with data intact for me. Probably is a problem in brresviewer, sad thing there.

Yeah, apparently the models do not like to convert well.
## Post #57
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-02-01T21:37:20+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Darkfox
>
> Sorry to bump/double post but might note that Bomberman Blast has problems with the BRRES files/models, possible encryption or scrambling. mdl0headerfix does not repair it.

I can give an example if needed. I have performed a memory dump with dolphin and using the BMS, had to remove a lot of junk data in the dump as well with a hex editor, this gets decrypted brres files. I load them up in brresviewer, and the model is not there and can't export anything but the bones, can load the model in BrawlBox though, but that can only export to DAE which has been a very picky format to convert to other things with data intact for me. Probably is a problem in brresviewer, sad thing there.

Yeah, apparently the models do not like to convert well.Bomberman Blast? Try using [this program](http://www.smashboards.com/showthread.php?t=234139) to decompress the files, then run the MDL0HeaderFix on the decompressed file. I've been able to get the models to show up in both BrawlBox and the BRRESViewer.
## Post #58
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-02T00:21:38+00:00
- Post Title: Re: Wii Brmdl Model Format

Woah, is that Gary!? Old faces pop up all the time. XD  Anyways, thanks for this, I'll test it out now.

Edit: Awesome! It works, thanks! =D I guess information was lost when using the script.
## Post #59
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:53:26+00:00
- Post Title: Re: Wii Brmdl Model Format

thanks form the list
## Post #60
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-10T09:19:58+00:00
- Post Title: Re: Wii Brmdl Model Format

I'll point this out: LZ77Ex works on the CXD and VLD files for Arc Rise Fantasia, they seem to be mega-archives that contain other VOLs. This includes enemy/player battle models.

Throwing this out there for those interested. Also, it will not decompress everything. Compressed places are marked with a 10, some decomp data, and a BTEM. As seen here. These are usually preceded by many 0s. This is btl_enemy.vld

Edit: The BTEMs I think have the enemy name or are just titled. Either way it is convenient.

Edit2: The CXDs are often with only one LZZ compressed chunk, the VLDs contain several. I wonder how the game locates this data... hm... also, like Bomberman Blast, a memory dump from Dolphin will not work, you'll be missing the model in BRRESViewer. The way I have is slow but gets you everything. Unless a script/program to find and extract these compressed chunks exists, this is the best way.

Edit3: Here's a listing of enemies in order within btl_enemy.vld

```
2. Imperial Knight
3. Imperial Officer
4. Imperial Undead
5. Castle Watch
6. Imperial Guard
7. Imperial Elite
8. Imperial Amazon
9. Imperial Knight (2)
10. Imperial Officer (2)
11. Imperial Undead (2)
12. Castle Watch (2)
13. Imperial Guard (2)

14. Zealot
15. Zealot Watch
16. Zealot Paladin
17. Lady Zealot
18. Zealot Watch (2)
19. Zealot Paladin (2)

20. Republic Soldier
21. Republic Capt
---Assassin Girls---
22. Uno
23. Dos
24. Tres
25. Nihil
26. Septem
27. Octo
28. Novem
---Sauroids---
29. Sauroid
30. Undead Sauroid
31. Green Sauroid
32. Kanher
---Thief Types---
33. Thief
34. Rogue
35. Burglar
36. Mamon
---Turtle Types---
37. Turtle
38. Lava Turtle
39. Emeraldas
40. Oceanus
---Nautilus Types---
41. Veratite
42. Philtite
43. Tronbower
44. Zephyampo
---Shooter Fish Types---
45. Gakthis
46. Deep Frost
47. Vanguard
48. Mackerel
---Flying Fish Types---
49. Flying Fish
50. Desert Fish
51. Catfish
52. Remora
---Frog Types---
53. Frog
54. Desert Frog
55. Flame Frog
56. King of Kings
57. Snow Frog
---Bat Types---
58. Bat
59. Vampire Bat
60. Blood Sucker
61. Fortuna
---Vulture Types---
62. Vulture
63. Snow Vulture
64. Bird of Hell
65. Benuu
---Beak Types---
66. Beak
67. Hybrid Beak
68. Forest Beak
69. Catherine
70. Mike
---Chick Types---
71. Chick
72. Hybrid Chick
73. Forest Chick
74. Diana
---Pelican Types---
75. Prin-temp
76. Ee-tee
77. Oat-onne
78. Y-verr
---Treant Types---
79. Treant
80. Terror Treant
81. Nabra Treant
82. Racie
---Flower Types---
83. Mad Plant
84. Poison Plant
85. Cannibal Plant
86. Jack Lantern
---Mandragora Types---
87. Mandragora
88. Flora
89. Rafflesia
90. Sun Flora
---Eye Plant Types---
91. Forest Eye
92. Oak Eye
93. Four-leaf
94. Hime
---Funger Types---
95. Funger
96. Nabra Funger
97. Venom Funger
98. Hundred-Eyes
---Doll Types---
99. Visc Doll
100. Elizabeth
---Cage Guy Types---
101. Slave Larva
102. Bogey
103. Banshee
104. Leanan-sidhe
---Skeleton Types---
105. Slave Bone
106. Bone Knight
107. Bone Rook
108. Thanatos
---Reaper Types---
109. Slave Wight
110. Lich
111. Charon
112. Hades
---Devil Types---
113. Erebus
114. Nyx
---Bear Types---
115. Bear
116. Ice Claw
117. Mample
118. Callisto
---Wolf Types---
119. Cyon
120. Lykos
121. Garm
122. Naberius
---Squirrel Types---
123. Belka
124. Kul-eeth
125. Kutune Sirka
126. Carbuncle
---Behemoth Types---
127. Whiss
128. Flamis
129. Behemoth
130. Amaltea
---Cat Types---
131. Grapplecat
132. Cat-sidhe
133. Assassin Cat
134. Big Ear
135. Samiad
---Bee Types---
136. Bee
137. Killer Bee
138. Death Hornet
139. Titania
---Moth Types---
140. Mos-seeder
141. Mos-laus
142. Mos-leef
143. Beelzebub
---Mantid Types---
144. Scythe
145. Cobalt Scythe
146. Crimson Scythe
147. Death Scythe
---Caterpillar Types---
148. Nospillar
149. Caucus
150. Kikimora
151. Habetrot
---Beetle Types---
152. Scissors
153. Metal Scissors
154. Ladybird
155. Coccinella
---Wyvern Types---
156. Marid
157. Djinn
158. Efreet
159. Dao
---Ground Dragon Types---
160. Allocer
161. Separ
---Golem Types---
162. Tartalos
163. Talos
164. Imaginal Gear
165. Adaman Gear
---Mimic Types---
166. Mimic
167. Lucy Mimic
168. Mercy Mimic
169. Dendro Mimic
---Gargoyle Types---
170. Gargoyle
171. Fake Statue
172. Virsago
173. Gorgon
---Elemental Crystal Types---
174. Gnome
175. Undine
176. Salamander
177. Sylpheed
---Slime Types---
178. Slime
179. Apple Slime
180. Grape Slime
181. Berry Slime
---Possessed Weapon Types---
182. Poltergeist
183. Living Arms
184. Living Battler
185. Epetam
---Robot Types---
186. Lascardes
187. Vercts
---Spinning Blade Types---
188. Imaginal Sabre
189. Real Sabre
190. Lascarde Sabre
191. Verct Sabre
---Balancing Animal Types---
192. Selkie
193. Roane
194. Kelpie
195. Cu-sith
====Bosses====
---Wyvern Types---
196. Wyvern
197. Allwise
---Great Dragon Types---
198. Jormungandr
199. Fafnir
---Carnivorous Plant Types---
200. Vifrons
201. Baal
---Giant Shrimp Types---
202. Afanc (Second Form)
203. Leviathan
204. Afanc (First Form)
---Chimera Types---
205. Chimera
206. Abaddon

207. Eesa
---Rogress Bosses---
208. Simmah
209. Girtab
210. Papirusagu
211. Allul
212. Absin
213. Gula
214. Squill
215. Kudoan
216. Urgula
217. Banchu
218. Rufunga
219. Mashgar

220. Ignacy
221. Ignacy (2)
222. Paula
223. Paula (2)
224. Luna
225. Luna (2)
226. Deathchanter
227. Deathchanter (2)
228. Dynos
229. Hosea
230. Weiss
231. Clyde
232. Clyde (2)
233. Clyde (3)
234. Adele
235. Adele (2)
236. Alf
237. Alf (2)
238. Alf (3)
239. Luze
240. Luze (2)
241. Leslie
242. L'Arc
243. Ryfia
244. Serge
245. Rastan
246. Cecille
247. Leslie (2)
248. Lucia
249. Vanessa
250. Saki
===Boss End===
---Generic Types---
251. P-00 (Generic Tree)
252. P-01 (Generic Flower)
253. P-02 (Generic Mushroom)
254. A-00 (Generic Turtle)
255. A-01 (Generic Nauticulus)
256. A-02 (Generic Flying Fish)
257. A-03 (Generic Frog)
258. M-00 (Generic Golem)
259. M-01 (Generic Gargoyle)
260. M-02 (Generic Slime)
261. M-03 (Generic Possessed Weapons)
262. B-00 (Generic Bear)
263. B-01 (Generic Wolf)
264. B-02 (Generic Behemoth)
265. B-03 (Generic Cat)
266. D-00 (Generic Dragon 1)
267. D-01 (Generic Dragon 2)
268. D-02 (Generic Dragon 3)
269. D-03 (Generic Dragon 4)

270. Raystone
```

[BTEM.png](https://xentaxbackup.github.io/file/3890_BTEM.png)
## Post #61
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-12T05:24:25+00:00
- Post Title: Re: Wii Brmdl Model Format

Wow that is a nice enemy list darkfox
Thanks a lot
## Post #62
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-15T02:20:57+00:00
- Post Title: Re: Wii Brmdl Model Format

Here's an almost complete list of models in Resident Evil: Darkside Chronicles, this does not include environment objects or weapons/items which are in ITEMS.arc and under the prefix of "W".

```
EAN1 - White Ant
EAN2 - White Ant (Lower poly)
EAN3 - Red Ant
EAN4 - Red Ant (Lower poly)
EAX0 - Alexia Ashford Tentacle
EAX1 - Alexia Ashford Form 1
EAX2 - Alexia Form 2
EAX3 - Alexia Form 3 (Dragonfly)
EAX4 - Alexia Tentacle 2
EAX5 - Alexia's Flower Withering
EBS1 - Bandersnatch
EBT0 - Bat
EBT1 - Lower Poly Bat
EBT2 - Mutated Bat
EBT3 - Lower Poly Mutated Bat
ECB1 - Cerberus
ECHS - Crimson Head Animations
ECR1 - Crow
EFK1 - Pirahna
EFZ1 - Steve's Father Zombie
EG01 - G-Larvae
EG02 - G-Creature
EGF1 - William Birkin Form 1
EGF2 - William Birkin Form 2
EGF3 - William Birkin Form 3
EGF4 - William Birkin Form 4
EGF5 - William Birkin Form 5
EGF6 - William Birkin Form 5 Tentacle
EGF7 - Thrown Bear In Door
EGZ1 - G-Virus Zombie? O_o
EHL1 - Hilda
EHT1 - Hunter
EHT2 - Sweeper
EHT3 - ...froggy hunter...
EIV1 - Plant 43 (Ivy)
EIV2 - Alternate Textures
EIV3 - Ivy + YX
EKK1 - Small Spider
EKK2 - Small Spider Lower Poly
ELK1 - Licker Stage 1
ELK2 - Licker Stage 2
ELR1 - Large Roach
ELR2 - Large Roach Lower Poly?
ELU0 - Lurker
EMB1 - Caterpillar
EMB2 - Moth Larva
EMB3 - Lower Poly Caterpillar
EMJ1 - Giant Gypsy Moth
EMJ2 - Giant Luna Moth
EMS1 - Monster Steve
EMS2 - Steve's Axe
EMS3 - Jabberwock
EMZ1 - Cop Zombie
ENS1 - Alexander Ashford "Nosferatu"
ENS2 - Nosferatu claws
EPC1 - Plague Crawler
EPR1 - Anubis (PR?)
ESI1 - Toucan Sam
ESW1 - Gulp Worm (ESW may refer to Sand Worm)
ETF1 - Tofu
ETF2 - Tofu Messy Texture
ETF3 - Tofu Fried
ETY1 - T-103 Mr. X
ETY2 - T-103 Form 3
ETY3 - T-103 Form 2
EVC1 - Javier
EWS1 - Web Spinner
EWS2 - Black Widow
EWS3 - Jumping Maneater

ITEMS - Various item and weapon models

PAF1 - Alfred Ashford
PAN1 - Annette Birkin
PAX1 - Alfred Ashford (Alexia Mode)
PBE1 - Ben Bertolucci Dead
PBE2 - Standing Animation
PBE3 - Ben Living Texture
PCL1 - Claire
PCL1RE - Claire arms (First Person)
PCL2 - Claire, no vest
PCL3 - Claire, red vest, pants, belt
PCL4 - Claire alternate outfit 3
PCL4RE - First person arms for outfit 3
PCL5 - Cowgirl Claire
PCR1 - Chris
PCR2 - Chris Outfit 2
PCR3 - Chris Western Outfit
PJT1 - Guide (James Tucker/James Tiberius we call him XD)
PKR1 - Krauser
PKR2 - Bloodied arm Krauser
PKR3 - Beret Krauser
PKR4 - Disco Krauser
PLO1 - Leon
PLO2 - Camo Pants Leon
PLO3 - Bandaged Leon
PLO4 - RE4 Leon Jacket
PLO5 - Leon Alt 4 (Brown jacket with many pockets)
PLO6 - Tourist Leon
PMA0 - Male Animations
PMA0RE - Male Arme Animations
PMA0_r000 (and so on) - Environmental/event related animations
PMA1 - Manuela
PMA2 - Manuela Burnt dress with no wrappings on arm
PMA2A - Additional animations like fire toss
PMB1 - Dying cop (Marvin Branagh)
PRK1 - Robert Kendo
PRK1A - Extra standing animation
PSH1 - Sherry Birkin
PSH1S - Sherry Birkin Animations
PSH1_r???? - Extra animations, interaction/scene
PSH2 - Sherry Birkin with Claire's vest
PST1 - Steve Burnside
PST2 - Cowboy Steve Burnside
PWA0 - Female Animations
PWA0RE - First Person Female Animations

```


The PMA0 and PWA0 are for player characters, but can also work on some NPCs which is fun to think of. Doesn't work on zombies and such though, sadly.

In the list above, what I found weird was EGZ1, which I don't recall at all, a G-Virus zombie? It is a zombie, with no legs, mutated, and has a G-Virus eye. Weird.
## Post #63
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-15T02:29:11+00:00
- Post Title: Re: Wii Brmdl Model Format

Wow great list
Thanks
## Post #64
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-15T19:34:09+00:00
- Post Title: Re: Wii Brmdl Model Format

Looking through Resident Evil - Umbrella Chronicles I couldn't find the player animations. Does anyone know where the game stores these?

Edit: Wow, didn't notice it but it totally lacks player animations other than counters. All animations are just cutscenes. Bummer. What of Resident Evil 4 Wii Edition? It uses BRMDL, yes?
## Post #65
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-02-15T20:30:44+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from Darkfox
>
> What of Resident Evil 4 Wii Edition? It uses BRMDL, yes?As far as I know, Resident Evil 4 uses a completely different model format.
## Post #66
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2011-02-16T19:24:00+00:00
- Post Title: Re: Wii Brmdl Model Format

Games that are cross-platform almost never use platform specific formats like the wii's format. Games that use the BRMDL format are usually from japan and made exclusively for the wii. If its a Nintendo game then that is probably the case.
## Post #67
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-02-16T23:46:04+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from invisghost
>
> Games that are cross-platform almost never use platform specific formats like the wii's format. Games that use the BRMDL format are usually from japan and made exclusively for the wii. If its a Nintendo game then that is probably the case.On that note, Teenage Mutant Ninja Turtles: Smash-Up is the only exception, since it was released for the PS2 as well...
## Post #68
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-16T23:57:45+00:00
- Post Title: Re: Wii Brmdl Model Format

Nice info random t bush
## Post #69
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-17T04:34:34+00:00
- Post Title: Re: Wii Brmdl Model Format

Ah, if that is true then that would mean there's no support for the models plus animation data. Thanks anyways.

Edit: Probably uses the PMDs which seems to only have import support for static models only. Oh well, was just interested in goofing around with HUNK and Wesker for a little thing between me and a friend is all. Was why I went to Umbrella Chronicles first. I will post any info on further digging in other games that use brmdl.

Edit2: Turns out I just needed to rename the bones to get the Umbrella Chronicles models working with Darkside Chronicles animations. Fun!
## Post #70
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-04-06T01:46:08+00:00
- Post Title: Re: Wii Brmdl Model Format

does anyone know how to view darkside chronicle models on brawlbox 0.64 beta ? D:
the models work in brawlbox 0.63 but ionno if it can export to dae

thx
## Post #71
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-04-06T03:58:22+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from protosk8
>
> does anyone know how to view darkside chronicle models on brawlbox 0.64 beta ? D:
the models work in brawlbox 0.63 but ionno if it can export to dae

thx

Dunno but kentilan's viewer works great and also there is an actorx importer por 3dsmax.
## Post #72
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-04-07T02:39:56+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from maniacoloco
>
> protosk8 wrote:does anyone know how to view darkside chronicle models on brawlbox 0.64 beta ? D:
the models work in brawlbox 0.63 but ionno if it can export to dae

thx

Dunno but kentilan's viewer works great and also there is an actorx importer por 3dsmax.

yea tried it yesterday but when i import to max tha bones come out all weird
works but they look all funky lol

well thanks for tha info anyway :3
## Post #73
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-04-07T18:38:30+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from protosk8
>
> maniacoloco wrote:protosk8 wrote:does anyone know how to view darkside chronicle models on brawlbox 0.64 beta ? D:
the models work in brawlbox 0.63 but ionno if it can export to dae

thx

Dunno but kentilan's viewer works great and also there is an actorx importer por 3dsmax.

yea tried it yesterday but when i import to max tha bones come out all weird
works but they look all funky lol

well thanks for tha info anyway :3

You can use Noesis and convert the psk to dea.
## Post #74
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-04-11T08:31:35+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from RandomTBush
>
> ...because of the following rules:

1. It has to be from a Japanese developer.
1b. Either that, or it's a game of a Japanese franchise.
2. It has to be a Wii-exclusive game, not a port of a PlayStation 2 game (such as Okami and DBZ: Budokai Tenkaichi 3).
3. If it's based off of a Gamecube-era engine (like Twilight Princess), then it's most likely gonna have BMD instead.

"Fragile Sayonara Tsuki no Haikyo" is the exception of these rules, the ISO contain weird containers with out any file Extension, i use the HexEditor but  i can't find any brres

The game was develop by tri-Crescendo the same guys of "Eternal Sonata"
## Post #75
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-04-11T15:46:35+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from FEATHER
>
> RandomTBush wrote:...because of the following rules:

1. It has to be from a Japanese developer.
1b. Either that, or it's a game of a Japanese franchise.
2. It has to be a Wii-exclusive game, not a port of a PlayStation 2 game (such as Okami and DBZ: Budokai Tenkaichi 3).
3. If it's based off of a Gamecube-era engine (like Twilight Princess), then it's most likely gonna have BMD instead.


"Fragile Sayonara Tsuki no Haikyo" is the exception of these rules, the ISO contain weird containers with out any file Extension, i use the HexEditor but  i can't find any brres

The game was develop by tri-Crescendo the same guys of "Eternal Sonata"

I didn't know this game, immm...there are some beautiful models.
Have you try to search "mdl0" with the hex editor?
## Post #76
- Username: jangoclone
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:52 am
- Post datetime: 2011-10-17T22:43:10+00:00
- Post Title: Re: Wii Brmdl Model Format

Hi can anyone send me the file that shadowmoy uploaded with the Tatsunoko Vs. Capcom chars?, I tried to convert this models with no luck, the Brawlbox doesn't show me any preview and the .dae file is corrupted, even whit the header fix, sorry to revive an old post...
## Post #77
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-10-21T15:38:48+00:00
- Post Title: Re: Wii Brmdl Model Format

> Reply from jangoclone
>
> Hi can anyone send me the file that shadowmoy uploaded with the Tatsunoko Vs. Capcom chars?, I tried to convert this models with no luck, the Brawlbox doesn't show me any preview and the .dae file is corrupted, even whit the header fix, sorry to revive an old post...

what version of brawlbox do u have? Anyway use brresviewer
## Post #78
- Username: killeromar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 04, 2011 11:26 am
- Post datetime: 2012-01-30T07:09:54+00:00
- Post Title: Re: Wii Brmdl Model Format

hi well im new to hexing (i dont know anything about it someone mentioned about extracting the btem from the vld i have the vld cause i extracted it using the wiiscrubber (i extracted the wbfs from the disc using cfg usb loader 70 then used the wii manager to convert to iso   )

i am a dumm dumm xD i would love to get simmah in fortune street i hate all of the mario cast  i would love to add some arc rise fantasia characters to it. 
also to know how to in case if FS cant be done then ill find some other game that can .

ps:thnx in advance
## Post #79
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-23T10:00:01+00:00
- Post Title: Re: Wii Brmdl Model Format

lol at the link spammers
## Post #80
- Username: Jakoza
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 23, 2014 9:12 am
- Post datetime: 2014-11-23T01:23:53+00:00
- Post Title: Re: Wii Brmdl Model Format

Thanks you  !!!
