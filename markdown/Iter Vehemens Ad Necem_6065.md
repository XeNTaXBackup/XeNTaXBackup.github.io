## Post #1
- Username: DarkStar88
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 16, 2011 12:32 am
- Post datetime: 2011-02-15T17:00:31+00:00
- Post Title: Iter Vehemens Ad Necem

My favorite roguelike game of all time, except for two little problems: 

1. The savegame files are HUGE for such a simple game; an extended game can grow your save folder to hundreds of Megabytes. Since they compress to almost nothing I suspect the fault is with the game itself.

2. It is quite possible to overload the engine and permanently have attributes like 'invisible' or 'confused'. This can be quite a pain, especially the former as it means you can't trade with shopkeepers as they can't see you!

Could someone could give me a hand in finding where the game stores what in the save files? Even just being able to turn on/off the aforementioned attributes would be great - a full editor (add/remove items, change stats, etc.) would be icing on the cake.

Original homepage, including source downloads:

[http://ivan.sourceforge.net/download.html](http://ivan.sourceforge.net/download.html)

The most active (and possibly only) homepage/fansite:

[http://www.attnam.com/](http://www.attnam.com/)

EDIT: A basic course in IVAN's scripting. Well worth a read.

[http://ivan.sourceforge.net/script/](http://ivan.sourceforge.net/script/)
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-02-19T04:35:30+00:00
- Post Title: Iter Vehemens Ad Necem

Nice to see the source is available for the game; I could probably track down the code that actually reads/writes the save files. I may look at this sometime, but not now - I've got too many other things going on ATM.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-02-19T09:31:29+00:00
- Post Title: Iter Vehemens Ad Necem

@dino: like building the dome.
## Post #4
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-02-19T18:17:52+00:00
- Post Title: Iter Vehemens Ad Necem

> Reply from Mr.Mouse
>
> @dino: like building the dome.
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-22T22:30:07+00:00
- Post Title: Iter Vehemens Ad Necem

well game::Save (game.cpp, 770) makes the save:

it writes a bunch of player attributes,
the equipment,
attributes,
dungeons,
gods,
teams,
current level/wilderness,
other player stats

as a guess, the dungeons are huge.

edit

the states hold if you're invisible or not. these are handled with bitflags:

```
#define INVISIBLE (1 << 6)

```


not sure where these states are stored with the player though
## Post #6
- Username: DarkStar88
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 16, 2011 12:32 am
- Post datetime: 2011-03-03T01:43:04+00:00
- Post Title: Iter Vehemens Ad Necem

The dungeons themselves aren't that big, going by roguelike standards, but it probably seems that way due to how IVAN reads/writes the files. 

Do states handle other attributes, such as teleporting or polymorphing?
