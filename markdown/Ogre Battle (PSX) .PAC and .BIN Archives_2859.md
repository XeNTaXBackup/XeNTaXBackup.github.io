## Post #1
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-11-29T20:26:17+00:00
- Post Title: Ogre Battle (PSX) .PAC and .BIN Archives

EDIT: The .PAC files aren't compressed. The .BIN files in the next post are most likely compressed, however.

Hello, all! This time around I'm beginning to explore an old PSX-era game called Ogre Battle, which seems to contain lots of .PAC archives. Judging from directory names, the .PACs are used to compress 2D image and TMD model files. 

Any ideas on what compression routine is being used in the attached samples? I understand that Atari once created STAD images with RLE compression that had the .PAC file extension, but I think the graphics used in Ogre Battle are far too sophisticated for these to be Atari .PACs -- plus, Atari didn't have anything to do wtih the development of this game, I don't think.
[Ogre Samples.zip](https://xentaxbackup.github.io/file/1404_Ogre Samples.zip)
## Post #2
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-11-29T20:38:07+00:00
- Post Title: Ogre Battle (PSX) .PAC and .BIN Archives

Also, I'm seeing a very interesting type of .BIN archive that might hold character sprites. When viewed in a hex editor, the .BIN archives start with the ASCII identifier: [blink] 

To my understanding, when an archive starts with an ASCII string like that, it's sort of like an identifier left by the developer that made the archives in the first place. Anyone ever come across anything like this before?

EDIT: I'm not sure if the BLINK Archiver will be of any help here at all; the hex examples I've seen seem to indicate that Blink Archive files should start with with BLINK D.T.S. and not [blink]. In any case,  the time stamps on the Ogre Battle .BINs are in August 1996, but the BLINK Archiver seems to have been released in 1997. Still, if anyone wants to help me look into that possibility:
[http://www.geocities.com/SiliconValley/ ... loadd.html](http://www.geocities.com/SiliconValley/4505/downloadd.html)

UPDATE: It looks as if the .PAC archives in the above post are really just files smushed together with no compression or encryption at all. Some .PACs contain 2D TIM images, others TMD models that I've succeeded in viewing. However, the [blink] BIN archives are still proving difficult; I suspect they're compressed sprite sheets.
[Ogre Samples 2.zip](https://xentaxbackup.github.io/file/1405_Ogre Samples 2.zip)
## Post #3
- Username: fastelbja
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 09, 2007 3:05 am
- Post datetime: 2007-12-10T19:58:46+00:00
- Post Title: Ogre Battle (PSX) .PAC and .BIN Archives

hi,

the .pac file are not compressed. 

u can look at them with GDD (sorry it's in japanese)

u'll find a good tutorial on how to use it here :

[http://randomselect.i-xcell.com/forum/i ... ic=132.180](http://randomselect.i-xcell.com/forum/index.php?topic=132.180)

cya
[GGD.rar](https://xentaxbackup.github.io/file/1406_GGD.rar)
## Post #4
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-12-12T20:19:03+00:00
- Post Title: Ogre Battle (PSX) .PAC and .BIN Archives

Hey, thanks for looking into it. I've actually been meaning to try out that graphics viewer to see what its advantages are over TileMolester, so thanks for that as well.

I'm fairly certain there's some compression going on with the .BIN archives; seems I saw a consistent pointer following the first [blink] tag pointing to a position 12 bytes or so before the start of the next [blink] tag. However, I still have to do more investigation to make sure this is the case across ALL the blink'ed BINs.
