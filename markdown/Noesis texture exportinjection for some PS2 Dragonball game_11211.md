## Post #1
- Username: Phaleg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 12, 2012 11:08 am
- Post datetime: 2014-02-16T06:25:31+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

This guy posted a request to extract/inject textures for some crappy PS2 Dragonball game. Then he was too much of a silly person to bother posting that his request was filled, or share the tool. Here lies the script that MrAdults has written to mod whatever this crappy game is. See attached file below.

PS- The guy says it's actually a Naruto game, but he won't even name it, so he could be full of crap.
## Post #2
- Username: RangerRus
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Apr 19, 2011 1:17 am
- Post datetime: 2014-02-16T13:31:19+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

Need more information about this *.dat structure.
If you have not, well, need more files to analyze, big and small.
## Post #3
- Username: Phaleg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 12, 2012 11:08 am
- Post datetime: 2014-02-16T19:40:20+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

> Reply from RangerRus
>
> Need more information about this *.dat structure.
If you have not, well, need more files to analyze, big and small.

I don't have a data structure, since I don't exactly know how these texture works
## Post #4
- Username: RangerRus
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Apr 19, 2011 1:17 am
- Post datetime: 2014-02-17T13:40:41+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

Ok. Working on it by easy stages.
UPD1: Got point about structure. Working on conversion...
UPD2: Files successfully separated...
## Post #5
- Username: Phaleg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 12, 2012 11:08 am
- Post datetime: 2014-02-17T20:24:43+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

> Reply from RangerRus
>
> Ok. Working on it by easy stages.
UPD1: Got point about structure. Working on conversion...
UPD2: Files successfully separated...

Amazing :O wow
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-02-18T20:00:38+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

Phaleg, why do you need this?
## Post #7
- Username: Phaleg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 12, 2012 11:08 am
- Post datetime: 2014-02-18T20:21:26+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

> Reply from Mr.Mouse
>
> Phaleg, why do you need this?
To modify these textures, that is
## Post #8
- Username: RangerRus
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Apr 19, 2011 1:17 am
- Post datetime: 2014-02-18T20:37:46+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

Got unswizzled textures...
## Post #9
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-02-18T21:35:55+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

From the images I'd say it's a DragonBall game...
Note the Kanji (GO, satori): [http://dragonball.wikia.com/wiki/File:G ... shback.png](http://dragonball.wikia.com/wiki/File:GokuDefeatsRecoomeFlashback.png)
## Post #10
- Username: LUBDAR
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-02-26T06:15:33+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

I just saw this thread. 100 for an hour of writing crappy script? That's more like it.

Attached is a Noesis script to extract/view the textures and inject textures back into the bin. To use:

1) Get latest Noesis.
2) Unzip .py script into your Noesis\plugins\python directory.
3) Browse to the .bin file in Noesis, right-click and hit Export to extract the contents or double-click it to view the images in preview.
4) Go modify your images and do whatever to them, but leave the numbers after the names intact to make reinjecting easy on yourself. (I would modify db_tex_01.tga and save it as db_tex_mod_01.tga or something)
5) Right-click the .bin file in Noesis and select "Inject DB Game Tex Bin".
6) Browse to your db_tex_mod_01.tga in the dialog that comes up and hit OK.
7) If you didn't change the name, the suggested injection texture index will already be correct, so you can just hit OK.
 The .bin file is now modified with the injected texture. Be careful, it modifies the bin you select. (as the first prompt warns you)

Throw money here: [http://www.richwhitehouse.com/index.php ... _about.php](http://www.richwhitehouse.com/index.php?content=inc_about.php)

This works on the .bin you posted. I make no guarantees about other bins.
[fmt_somedragonballgame_bin.zip](https://xentaxbackup.github.io/file/7042_fmt_somedragonballgame_bin.zip)
## Post #11
- Username: RangerRus
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Apr 19, 2011 1:17 am
- Post datetime: 2014-02-26T23:22:57+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

It's done already...
## Post #12
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-02-27T01:26:59+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

Are you trying to tell me I wasted a good hour of my time because you sacksuckers couldn't be assed to update this thread? Because if that's what you're trying to tell me, I will end you.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-02-27T08:18:41+00:00
- Post Title: Noesis texture export/injection for some PS2 Dragonball game

> Reply from MrAdults
>
> Are you trying to tell me I wasted a good hour of my time because you sacksuckers couldn't be assed to update this thread? Because if that's what you're trying to tell me, I will end you.

It would seem that way. I will therefore close this thread. I was asked to delete it yesterday, but apparently a little too late,  since the problem was already solved at that time,and there were multiple solutions... I am not going to delete however. I will close it. I am sure that there was no intention to misguide, but that Phaleg and RangerRus forgot to update this thread accordingly. I understand that Phaleg does wish to reach out to MrAdults, so you can take that offline in the PM. Cheers, chaps!
