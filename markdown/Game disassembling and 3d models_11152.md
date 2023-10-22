## Post #1
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-22T18:14:43+00:00
- Post Title: Game disassembling and 3d models

Hi all   ,

I have a personal project where I'm trying to extract the 3d models from Silver (see [viewtopic.php?f=16&t=11097](http://forum.xentax.com/viewtopic.php?f=16&t=11097) ). As you can see the models are not easily readable (compressed according to TaylorMouse). Now I've tried ripping the models directly from the Game using 3D Ripper DX, ninja ripper, 3dvia printscreen and pretty much every ripper i could find and they all produced nothing / produced empty files, probably because the game uses old DirectX6.1... I did the same on the Dreamcast version of the game and couldn't get anything worthwhile because of backface culling   .

From what I've read, my last option is to disassemble the game exe to try and learn how it loads those models. I know it's a tedious task and it could take a long time but I really don't care if it will take 6 months I just want the models. I've done a little NASM assembly in school but I was wondering if any of you had experience with this. I know where the 3dmodel files are so I assume it will be easier to locate the functions responsible for loading/decompressing them but I don't really know how to start? Is there any tuts on ollydbg and game reversing (info on how to find model related stuff would be cool).

Thanks

EDIT: I've uploaded some .CHR models here [http://nerd.perso.sfr.fr/silver/](http://nerd.perso.sfr.fr/silver/) and the game exe and dlls here [http://nerd.perso.sfr.fr/silver/exe/](http://nerd.perso.sfr.fr/silver/exe/) in case anyone wants to take a look at it. Doing a quick referenced string search in the executable, Ive found things such as "loadbody.c", "Shape_list", "SILVER\CHARS\" (the directory where models are) and "load_silver_character" (method name here ?). if someone needs more files just ask and I'll upload them.
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-22T20:07:52+00:00
- Post Title: Game disassembling and 3d models

post some examples, so other people that don't have the game can take a look at it.

T.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-23T00:50:01+00:00
- Post Title: Game disassembling and 3d models

@nerdyluke:
try setting breakpoints here:
0046D220  |. B8 34ED5700    MOV EAX,silver.0057ED34   ;  ASCII "Opening File '%s' in 'load_character_anim'"

0046D850  |. B8 68ED5700    MOV EAX,silver.0057ED68   ;  ASCII "Opening File '%s' in 'load_silver_character'"

good luck...
