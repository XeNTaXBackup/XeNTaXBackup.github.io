## Post #1
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2011-09-12T07:00:31+00:00
- Post Title: Modding RDR save game (Adventure)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-09-12T16:53:13+00:00
- Post Title: Modding RDR save game (Adventure)

Just to be clear, you almost never find savegame formats that can be edited with a text editor; it's far easier to store the information in such a way that a hex editor or custom savegame editor is required to edit the files.

You're also not going to see anything like "Change this value to give yourself max money!!!" Reverse-engineering a savegame format takes patience, and usually consists of changing one thing at a time in-game (e.g. picking up or dropping some money) and seeing what changed as a result in the save file.

All that being said, it looks like you're wanting to modify a multiplayer savegame file. For a game like Red Dead: Redemption, there are almost certainly systems in place to check for modified savegames in multiplayer and prevent their use when they're found, so I have to ask what you're wanting to change and why?
## Post #3
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2011-09-12T18:35:30+00:00
- Post Title: Modding RDR save game (Adventure)

> Reply from Dinoguy1000
>
> Just to be clear, you almost never find savegame formats that can be edited with a text editor; it's far easier to store the information in such a way that a hex editor or custom savegame editor is required to edit the files.

You're also not going to see anything like "Change this value to give yourself max money!!!" Reverse-engineering a savegame format takes patience, and usually consists of changing one thing at a time in-game (e.g. picking up or dropping some money) and seeing what changed as a result in the save file.

All that being said, it looks like you're wanting to modify a multiplayer savegame file. For a game like Red Dead: Redemption, there are almost certainly systems in place to check for modified savegames in multiplayer and prevent their use when they're found, so I have to ask what you're wanting to change and why?

i don't really know what's on the savegame, i wanted to see the files in text so i can know what i can mod, can you help me do this like giving me some helpful links
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-09-14T20:19:29+00:00
- Post Title: Modding RDR save game (Adventure)

Not really. As I said above, it's incredibly unlikely that there is going to be much of anything worth changing that's stored in plaintext in the save files, and even if there was, you'd have to figure out how the string length is determined (is it Pascal-style? C-style? something else?). Before you're able to change *anything*, you also have to determine whether the save file is hashed or checksummed to prevent modding (though this is thankfully much easier; once you know of a particular value's purpose, you can just change it by one or whatever, and see if the game still loads the save file). The best you could do is search around the internet to see if anyone else has already done any work on the format.
## Post #5
- Username: godzcheater
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 04, 2012 3:37 am
- Post datetime: 2012-02-03T19:48:28+00:00
- Post Title: Modding RDR save game (Adventure)

I had RDR when it was released, and I researched the format([http://godzcheater.net/Research/index.p ... Redemption](http://godzcheater.net/Research/index.php/Red_Dead_Redemption)), but my m8 how still has the game says its encrypted.
If the above format isn't right can you send me your save.
## Post #6
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2012-02-15T09:13:44+00:00
- Post Title: Modding RDR save game (Adventure)

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: godzcheater
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 04, 2012 3:37 am
- Post datetime: 2012-02-15T11:05:17+00:00
- Post Title: Modding RDR save game (Adventure)

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2012-02-15T13:08:23+00:00
- Post Title: Modding RDR save game (Adventure)

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: godzcheater
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 04, 2012 3:37 am
- Post datetime: 2012-02-15T17:36:47+00:00
- Post Title: Modding RDR save game (Adventure)

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2012-02-15T22:49:31+00:00
- Post Title: Modding RDR save game (Adventure)

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: godzcheater
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 04, 2012 3:37 am
- Post datetime: 2012-02-16T10:04:57+00:00
- Post Title: Modding RDR save game (Adventure)

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2012-02-17T19:39:34+00:00
- Post Title: Modding RDR save game (Adventure)

yeah bro i opened the save of course  but it doesn't work, i don't know maybe the problem is my be cause of my pc
## Post #13
- Username: godzcheater
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 04, 2012 3:37 am
- Post datetime: 2012-02-17T23:40:06+00:00
- Post Title: Modding RDR save game (Adventure)

> Reply from pro spy
>
> yeah bro i opened the save of course  but it doesn't work, i don't know maybe the problem is my be cause of my pc
Your using the files you sent me?
There STFS files, not the saves, there is a difference.
Use a STFS tool such as horizon to extract the save.
## Post #14
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2012-02-18T10:43:21+00:00
- Post Title: Modding RDR save game (Adventure)

> Reply from godzcheater
>
> pro spy wrote:yeah bro i opened the save of course  but it doesn't work, i don't know maybe the problem is my be cause of my pc
Your using the files you sent me?
There STFS files, not the saves, there is a difference.
Use a STFS tool such as horizon to extract the save.

oh my god man it worked after extracting it with horizon you're genuis

so i extract "gbGameProgression" from RDR2ZOMBIESAVE0.SAV and i opened with Hex editor 

In the game i got 5.00% of 100% 
and the Hex Editor says "0000 0001"

so i want to change it to 100% i mean how do you do the math
## Post #15
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2012-02-19T02:05:52+00:00
- Post Title: Modding RDR save game (Adventure)

Another question bro, is it possible to extract something from RDR2ZOMBIESAVE0.SAV like gWeatherManager and inject it to another file like RDR2MPSAVE.SAV
## Post #16
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2012-02-19T11:04:47+00:00
- Post Title: Re: Modding RDR save game (Adventure)

Edit: i got 8.00% and 10.00% and it's still the same Value which is "0000 0001",  that's really wired

i also tried to insert gWeatherManager from RDR2ZOMBIESAVE0.SAV to RDR2MPSAVE.SAV, it won't let me
## Post #17
- Username: Cpt Putang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Feb 28, 2013 1:35 am
- Post datetime: 2013-02-27T23:03:11+00:00
- Post Title: Re: Modding RDR save game (Adventure)

> Reply from pro spy
>
> 
Oh my god man it worked after extracting it with horizon you're genuis

so i extract "gbGameProgression" from RDR2ZOMBIESAVE0.SAV and i opened with Hex editor 

In the game i got 5.00% of 100% 
and the Hex Editor says "0000 0001"

so i want to change it to 100% i mean how do you do the math

Without being able to see the original posts in the topic and from seeing the remainder of posts that have not been edited You will need to edit.

gRDR2_Stats
gPlayerData
giSaveLoadFlags

> Reply from pro spy
>
> Another question bro, is it possible to extract something from RDR2ZOMBIESAVE0.SAV like gWeatherManager and inject it to another file like RDR2MPSAVE.SAV

Short Answer: Not as Simple as simply Injecting.
## Post #18
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-07-15T03:35:30+00:00
- Post Title: Re: Modding RDR save game (Adventure)

hmm this should be as easy as injecting after editing the save then rehash and resign to your account (your xbox account)
once your done that try it out if it doesn't work the save is encrypted but there are save editors for the xbox 360 here is one 

[http://www.mediafire.com/download/ywc65 ... l+v2.5.rar](http://www.mediafire.com/download/ywc65kxsawki471/RDR+Mod+Tool+v2.5.rar)
