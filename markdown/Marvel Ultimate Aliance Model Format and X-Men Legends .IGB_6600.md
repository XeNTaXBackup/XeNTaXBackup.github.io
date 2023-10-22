## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-05-11T19:55:12+00:00
- Post Title: Marvel Ultimate Aliance Model Format and X-Men Legends .IGB

This its sample files of Marvel Ultimate Aliance PC game
i hope anyone can make a importer, i think mesh, animations and textures are in the same files.
Sample Files, the files are .IGB.
[http://www.megaupload.com/?d=LIGVA7UY](http://www.megaupload.com/?d=LIGVA7UY)

Interesting X-Men Legends ROA have the same format IGB FILES


SAMPLE FILES
[http://www.megaupload.com/?d=OIBRRMFP](http://www.megaupload.com/?d=OIBRRMFP)
## Post #2
- Username: reboot31
- Rank: MIT cheater
- Number of posts: 10
- Joined date: Mon Apr 18, 2011 2:41 pm
- Post datetime: 2011-05-12T11:45:51+00:00
- Post Title: Marvel Ultimate Aliance Model Format and X-Men Legends .IGB

Hi Rimbros, I'm newbie here... I played this game and I really enjoy this...
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-05-27T22:33:46+00:00
- Post Title: Marvel Ultimate Aliance Model Format and X-Men Legends .IGB

Yes this games are amazing and have all the marvel comics models, but the .IGB Compresed are very profesional packed system, not easy to make a script.
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-29T21:41:26+00:00
- Post Title: Marvel Ultimate Aliance Model Format and X-Men Legends .IGB

Something idea abouth the IGB format?
## Post #5
- Username: Noelemahc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 08, 2011 1:46 pm
- Post datetime: 2011-08-08T05:53:49+00:00
- Post Title: Marvel Ultimate Aliance Model Format and X-Men Legends .IGB

You might want to visit marvelmods.com, which is a site devoted almost entirely to modding this series of games.

For clarification, IGB files are Alchemy engine (which is what these games use) model/animation files, but the animations and models are stored separately =)

XXX_charactername.igb are animation skeletons, XXXYY.igb are character models, where XXX is a two or three-digit number (to simplify internal referrers) assigned within a particular game to a character (some numbers are shared between games, such as Wolverine being 03, some move from place to place -- Deadpool is 44 in XML2, but 17 in MUA1 and MUA2) and YY is model number (01-09 usually being reserved for outfits, 21-29 for special outfits, if applicable, and 11-19 for additional models such as weapons or removable body parts).

While we can't directly affect the files (except for texture injection), we do possess the means to rip the models into editable formats and reimport them into a format compatible with the PC versions of XML2 and MUA1. Nothing can be done about the animations, sadly.

All of the versions of the engine have been well-documented, researched and modded except for the DS version of MUA2 (because it uses a different engine) and the PS3 and X-BOX360 versions of MUA2 (because they use complicated file encryption on top of the usual gobbledygook). For the PC version, anything can be modded, edited and replaced - sounds, music, models, textures, scripts, everything but making new animations and levels is possible. For the other versions, slightly less so - we can't affect PSP models other than edit their textures, same goes for PS3 and X360 models.
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-08-08T23:57:21+00:00
- Post Title: Marvel Ultimate Aliance Model Format and X-Men Legends .IGB

This its a Old post abouth Alchemy Exporter

[viewtopic.php?f=16&t=2915](http://forum.xentax.com/viewtopic.php?f=16&t=2915)

the question its this, every game have diferent skeletal or bones structure, on this old post i see a death link to Alchemy Exporter, but how i can know or load the right bones structure of the Marvel Ultimate Aliance Models? and how i can changue and inject back the models to the game? cause y search the exporter and only found death links, i see the marvel mods but a lot of this mods looks like Textures Edited using the same morphs of the original game, maybe i wrong but that its i found a this time.
## Post #7
- Username: Noelemahc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 08, 2011 1:46 pm
- Post datetime: 2011-08-09T11:40:33+00:00
- Post Title: Marvel Ultimate Aliance Model Format and X-Men Legends .IGB

Search the marvelmods forums, the bone structure for MUA was described in several different places.

You rip the models to edit them with DX Ripper or any other similar software that can "steal" models loaded into system memory, edit them with your 3d editor of choice, then export them with the Alchemy Exporter (which should still be available via the marvelmods forums, if it's not, write about it over there, please). The resulting IGB file will be compatible with XML2 and MUA PC and X-Box (not 360) versions.

And of all the Alchemy-based games, all of the games in the Marvel series (XML1-2, MUA1-2) use the same approach and scale for their models and skeletons, so once you have a basic skeleton set up once, you just need to stick to it.

All the texture edits (instead of model edits) are because the model edits take more time and skill, so most people avoid that. Also, it's the only way for non-PC versions of the game to have mods at all, so...
## Post #8
- Username: Roseweave
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 26, 2019 6:43 am
- Post datetime: 2019-10-29T03:53:00+00:00
- Post Title: Marvel Ultimate Aliance Model Format and X-Men Legends .IGB

Did anyone find a way to convert these models directly? I'm trying to get a rip of the Blink model to use as a base.
