## Post #1
- Username: alera
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-16T02:38:40+00:00
- Post Title: Street Fighter 4 (PC)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-20T09:48:08+00:00
- Post Title: Street Fighter 4 (PC)

> were loaded into ram and then I dumped the ram contents
I love this trick so much >>>>
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-08T09:38:03+00:00
- Post Title: Street Fighter 4 (PC)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-11T05:35:50+00:00
- Post Title: Street Fighter 4 (PC)

Any progress with a model viewer, the files have a header of bsr but I cant find a viewer for it.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-11T13:02:27+00:00
- Post Title: Street Fighter 4 (PC)

I don't have the skill to write a model viewer but 3dripper dx works great on this game.
just look in the file and delete any bone names you see bye overwriting them with 00
this will make them in t-pose.
## Post #6
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-14T11:00:00+00:00
- Post Title: Street Fighter 4 (PC)

> Reply from chrrox
>
> I don't have the skill to write a model viewer but 3dripper dx works great on this game.
just look in the file and delete any bone names you see bye overwriting them with 00
this will make them in t-pose.

Thanks I'll try that, haven't had much luck with the model files dumped by 3dripper as yet. anyways here's the full Zangief mod I've been working on:
[zangieffinal2.jpg](https://xentaxbackup.github.io/file/2189_zangieffinal2.jpg)
## Post #7
- Username: Krysia
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 05, 2009 5:11 am
- Post datetime: 2009-07-31T11:51:37+00:00
- Post Title: Street Fighter 4 (PC)

> Reply from chrrox
>
> I don't have the skill to write a model viewer but 3dripper dx works great on this game.
just look in the file and delete any bone names you see bye overwriting them with 00
this will make them in t-pose.

Hi chrrox. What do you mean by "look in the file and delete any bone names you see"? You mean by opening it with... what?
When opening with notepad I can see just a mess.
## Post #8
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2009-09-28T01:27:29+00:00
- Post Title: Street Fighter 4 (PC)

A HexEditor most likely.  Its like notepad but for binary data.
I can think of "HexWorkshop" and "010 Hex editor". those are stand alone hex editors but non are free 

Hex editors usualy have 2 views. one that is like notepad and one in hexadecimal numbers. look for a bone name.. what ever that will be. say "Bone1" or "Pelvis". look for the name in the ASCII view(the one that looks like notepad) and then highlight it to know where does it correspond in the Hex view. in the hex view you should overwrite the selected bytes with "00" that will simply set all bytes to null.

The hex view will have number ranging from 0 to "F" and 10 is not ten. it is actually 16 

BTW Cool Mod!
