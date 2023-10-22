## Post #1
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2012-10-16T15:26:12+00:00
- Post Title: Half-Life 2

Started off with this [http://www.moddb.com/games/half-life-2/ ... ound-files](http://www.moddb.com/games/half-life-2/tutorials/modding-sound-files)
Have changed and compiled the closecaptions txt.

No matter what I do I simply cannot get the game to use the new files.  Am I missing something?
## Post #2
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2012-10-16T19:36:38+00:00
- Post Title: Half-Life 2

What are you exactly trying to do? Translate the Half-Life 2's strings?
If so, you must translate the closecaption_english.txt first, then compile it into .dat using the captioncompiler.exe which comes with Source SDK.
## Post #3
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2012-10-16T20:12:39+00:00
- Post Title: Half-Life 2

> Reply from rambo919
>
> Have changed and compiled the closecaptions txt.

Yes, I do have the new dat file, no matter where I put it though the subtitles (ingame) refuse to change, same thing for the wav's.

To test if anything is working (changing) I garbled a bit of the subtitles at the beginning of the game and renamed a few of the gman wav's so that his monologue is a bit mixed up audio wise.
## Post #4
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2012-10-18T12:18:31+00:00
- Post Title: Half-Life 2

Did another few tests, switched a few of the pistol sounds for crowbar ones, no change ingame.  Got the sdk and loaded up hammer and used it's browser, gamesounds shows nothing (do not know if that is relavent) and switching to raw everything shows and the changed sounds play correctly. In short everything seems to be as it should be but the game plays the original sounds.
## Post #5
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2012-10-19T13:20:18+00:00
- Post Title: Half-Life 2

Ok I figured it out mostly, the particular emulator/loader I was using was to blaim (I have a strong aversion to using stream so I only load it if I have no other choice, sorry should have mentioned that).  I switched emulators and suddenly the new sounds work.  Now my problem is just getting the game to recognise closecaption_english.dat :/

EDIT: Can't believe it, I copied over the uncompiled closecaption_english.txt and THAT worked.
