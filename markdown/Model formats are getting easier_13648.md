## Post #1
- Username: adhest50
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 10, 2015 11:37 am
- Post datetime: 2015-12-10T03:40:08+00:00
- Post Title: Model formats are getting easier?

So I've been looking at a lot of PC games and find that MMO's and other PC games tend to have...pretty simple model formats.
It looks like a lot of PS3 and 360 games have been getting out as well.

Then I see games for PSP, PS2, and PS1...and those generally come with all sorts of headaches.
And then the older consoles.......lol

How come it seems like things are getting easier as newer stuff comes out compared to old stuff?
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-12-10T07:52:35+00:00
- Post Title: Model formats are getting easier?

RAM grows devs get lazy as they have a lot of room to work with for example back before on older games they had to pack to save bytes for example the UVs or even verticies are packed into uint16's now they don't really need to worry about that and can store it as pure 4byte floats.

This is just one example.
## Post #3
- Username: Bastien
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-12-10T14:37:57+00:00
- Post Title: Model formats are getting easier?

Mostly standards. There's one right way to do everything on most newer hardware, and the right thing to do isn't going to change that much in most cases dependent on per-game circumstances. Back when you didn't have hardware T&L or even a real fixed function pipeline, you were basically given a 2D triangle renderer and told to do the rest yourself, naturally every developer invented their own version of the wheel. This was reflected down in the binary standard too, as many ways to process and feed data to the hardware means many ways to store that data. Even the PS2 allowed a great deal of flexibility in how you wanted to store, unpack, and process data thanks to the general necessity to leverage custom VU microcode effectively in order to fully leverage the hardware. Games that really make use of the PS3's SPU's for things like skinning/transforms and culling can also store data in all kinds of interesting and proprietary ways, but Sony cut that off near the stem by offering Edge. There wasn't a whole lot of justification to roll your own once it was offered, which isn't a case of developers being lazy, and rather a case of firstparty doing all the work for everyone to help prevent them from inventing their own less-tested and less-optimized wheels. This all basically comes down to meaning that on the latest hardware, if your data doesn't resemble everyone else's, either you're doing something super-special or you don't know what you're doing.

As rendering hardware becomes more flexible and we're free to do things like raycast against all kinds of custom data/structures, this is going to reverse course and dictate that understanding data from more sophisticated 3D games/applications is actually somewhat challenging again. I don't expect this to happen until after the PS4/XBOne console era.

In the world of MMO's, it's true that most of the devs are just shitty, though. They probably aren't trying very hard to make the most of their minspec, and most MMO codebases are just cobbled-together middleware that's been crapped all over by dozens of cheap contractors.
## Post #4
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2015-12-11T17:22:29+00:00
- Post Title: Model formats are getting easier?

Only Marvel Ultimate Alliance (Gold Edition (360) & 2) couldn't make it. 

Though the second game model still in progress. But no news about it.
