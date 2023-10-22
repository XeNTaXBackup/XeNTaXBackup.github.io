## Post #1
- Username: TheDude
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-21T00:14:37+00:00
- Post Title: Folklore (PS3) Noesis Script

Here is a folklore import script for noesis.
Imports 3d models with
Materials
bones
weights.

[fmt_folklore_bi5.7z](https://xentaxbackup.github.io/file/6789_fmt_folklore_bi5.7z)
## Post #2
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2013-11-21T04:24:37+00:00
- Post Title: Folklore (PS3) Noesis Script

thax for Script. and i'm srry about noob. how to you extract arc file FolkLore PS3?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-21T11:00:53+00:00
- Post Title: Folklore (PS3) Noesis Script

> Reply from lumekano
>
> thax for Script. and i'm srry about noob. how to you extract arc file FolkLore PS3?
quickbms script

```
open FDDE fht_ 0
open FDDE bin_ 1
get files asize
math files / 0x28
for i = 0 < files
getdstring name 0x20
get size long
get offset long
log name offset size 1
next i
```
## Post #4
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-11-21T18:34:18+00:00
- Post Title: Folklore (PS3) Noesis Script

Hey Chrrox i really apreciate that Noesis Script also i see in the picture the Chrismas custom from the DLC so iam curius how do you 
managet to get the Bi5_ file from the edat file?

Also some files dont load properly the texture (just a few) and the LMapxxx.bi5_ and mbxxx.bi5_ dont load.

Any way thanks for that script for the game i can finally fully rip every character.
## Post #5
- Username: The Chief
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-21T20:33:55+00:00
- Post Title: Folklore (PS3) Noesis Script

using TrueAncestor EDAT Rebuilder 1.42
you can decrypt them with the key

```
47656D75726970614D4353747564696F
```
## Post #6
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-11-21T22:19:11+00:00
- Post Title: Folklore (PS3) Noesis Script

Thanks for the reply chrrox i managet to get all the meshes now.  

[](http://imageshack.us/photo/my-images/17/eiz3.png/)
## Post #7
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-12-20T11:06:57+00:00
- Post Title: Folklore (PS3) Noesis Script

any idea for .sgb_ for sound
## Post #8
- Username: Blank9
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 10, 2012 11:09 pm
- Post datetime: 2015-02-25T06:38:22+00:00
- Post Title: Folklore (PS3) Noesis Script

How do I run the script in Noesis to open the files?
## Post #9
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2015-02-25T16:28:02+00:00
- Post Title: Folklore (PS3) Noesis Script

> Reply from Blank9
>
> How do I run the script in Noesis to open the files?

Copy the file fmt_folklore_bi5.py to the folder python that folder (python) is inside of the folder plugins.
## Post #10
- Username: Blank9
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 10, 2012 11:09 pm
- Post datetime: 2015-03-08T13:21:24+00:00
- Post Title: Folklore (PS3) Noesis Script

Im viewing the models now. Thank you so much, you guys are amazing. There is a unique Folk in the files that I have never seen unlocked in the game O_O

How do I get the dlc edat files off of the PS3 onto a usb?
## Post #11
- Username: OperateSystemP
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 04, 2015 9:26 am
- Post datetime: 2015-06-04T12:15:06+00:00
- Post Title: Folklore (PS3) Noesis Script

I can not thank you enough for this but i have noticed a few little problems.
1: Auto-rigging its good but sometimes bones rig wrong so they need to be manually fixed. Just a minor thing that can be fixed manually.
2:  It can't load any LMap and mb files. But it does load models well.
Aside from those problems, this is something i've wanted for quite a while and as i said, i can not thank you enough with words.
