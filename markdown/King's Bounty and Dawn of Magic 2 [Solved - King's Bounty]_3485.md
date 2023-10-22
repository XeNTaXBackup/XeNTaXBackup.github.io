## Post #1
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-05-16T12:29:59+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

The contents of this post was deleted because of possible forum rules violation.
[KB2.rar](https://xentaxbackup.github.io/file/2063_KB2.rar)
## Post #2
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-05-25T13:50:30+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

Update: The game engine is pretty flexible. Deleting the Animation.kfs file disables all the animations, putting the models in T-Pose. However, any specific game action like NPC interaction freeze's it up.

So geometry capturing with GA or 3DR is possible.
## Post #3
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-25T15:15:39+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

I suspect you are talking about the remake of King's Bounty, called: King's Bounty: The Legend.  As I'm a big fan of Might&Magic universe I'll follow this topic. But can help right now, as I'm very busy with june exams and want to finnish cmp images for darkfox before.

Anyway best luck with this.

P.D: I couldn't analyze those models cause rapidshare is always "already taken" in my student's residence.
## Post #4
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-05-25T18:38:27+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

Yep, thats the game, corrected it, been a M&M fan myself for a while.

Uploaded a smaller sample in the Topic Post.

Also, another thing. Geometry ripping with GA and 3DR during gameplay is no go. For some reason, during combat the rippers freeze, but work normally with the 'world' models.
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-26T22:31:01+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

I did a SilkRoad-Online(SRO) maxscript years ago! I think the source code had lost but I just found the maxscript!

So if you are lucky you should be able to import BMS mesh into 3DSMax! Should works with MAX3+ version!

PS: Don't ask me for any further, I don't interested anymore and I am busy ATM!

Good Luck!
[Bms_Importer.rar](https://xentaxbackup.github.io/file/2066_Bms_Importer.rar)
## Post #6
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-05-27T09:49:26+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

Wow, fatduck! I did extreme research on Google for the SRO converters/importers and never saw this one. Extremely useful, thank you! Bones, here I come!

Update: Tested fatducks importer on KBL, it says "Invalid Integer".
## Post #7
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-27T14:38:50+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

So the formats are different. But they may be only slightly different. If fatduck has 5 minutes he can take a look at it to determine thos divergences, I think.
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-27T19:40:44+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

Unfortunately, 5 mins is not enough for this format!

This format is completely different form SRO, although the file extension are the same!!! (Same engine but upgraded version??)

From what I can tell, they use long integer(4-bytes) as chunk header!? 

0x5535B is material.

0x867C6B is vertices data, each vert is 24 bytes each! The first 6 bytes are 3 short integer for the XYZ coordinates.

0x141FB is face indices, in word format, 3 indices per faces!

0xAA057 is collision/LOD data?

0x50E957 is collision/LOD face indices, same as face indices.

0xA1EB17 is collision/LOD vertices, only 12 bytes each, again the first 6 bytes are XYZ coordinates.

These shoud give you enough infos. for 3D models conversion!
## Post #9
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-02-02T19:50:56+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

Update, I found another game which is from the same company and uses the same files! Dawn of Magic 2.

I decided to upload them as well incase someone takes a stab at them. Once I get Armored Princess, I'm sure I'll upload a sample from them too incase something else did change.

Files in attachment.
[DOM2.zip](https://xentaxbackup.github.io/file/2763_DOM2.zip)
## Post #10
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-05-25T20:22:21+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

The contents of this post was deleted because of possible forum rules violation.


Update 2014-07-02:

- use for Blender 249 (not newer)
- support: uv,weighting,skeleton,animation,autotexturing

[http://www.mediafire.com/download/qj35p ... BPC%5D.zip](http://www.mediafire.com/download/qj35plh192ee58c/King%27sBounty%5BPC%5D.zip)
[amelie.jpg](https://xentaxbackup.github.io/file/3072_amelie.jpg)
## Post #11
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-05-28T17:13:01+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

Nice!

Thanks alot mate for taking time on it. Much appreciated, especially with the whole bells and whistles (bones).

Thank you very much my kind sir.

EDIT: Forgot to ask, what type of models don't open up? Are they random or specific file size?
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-15T18:42:43+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-12-09T20:25:01+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

I have the same error executing the script in line 26

Code:
Draw.PupBlock("bma files",block) 

Is there a reason/solution for this?

EDIT:

Nevermind, I got it to work,

I'm not sure why it resolved itself, but after re-installing blender 2.49 and double-clicking the .blend file itself to open blender it worked.
## Post #14
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-12-10T19:51:31+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

Error: line 26 .
Please check console:
If  there is "ValueError: sequence cannot have more than 120 elements" ,
please to have no more than 120 files in one folder.
## Post #15
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-12-12T23:41:44+00:00
- Post Title: King's Bounty and Dawn of Magic 2 [Solved - King's Bounty]

Thank You, 

Now I got it!
## Post #16
- Username: zini4Grunt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 10, 2011 4:25 pm
- Post datetime: 2011-03-10T08:34:16+00:00
- Post Title: Re: King's Bounty and Dawn of Magic 2

Hello everyone.
Can anyone tell me: did the process of extracring/impotring models/animations have been stuck, or not?
And one more thing: can anyone resubmit files from the first post?
Thanx.
## Post #17
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2011-09-30T23:25:47+00:00
- Post Title: Re: King's Bounty and Dawn of Magic 2

Here fix for error 26 

13 extends=['bma','bms']
14 dir = os.getcwd()
15 dir = "D:\\x"

add line 15 to your script and place models in d:\x

2 Szkaradek123 thx for your work ...

May be you fix script for import .bma files from data.kfs  (mine_bridge.bma on example - good static walls & etc ...) ?

P.S. Here sources for exporter to obj from bma/bms - [http://rghost.net/23726731](http://rghost.net/23726731)
## Post #18
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2015-03-22T18:40:53+00:00
- Post Title: Re: King's Bounty and Dawn of Magic 2

Hi just wanted to test the latest script for KingsBounty by Szkaradek123, and I cannot understand what's happening.

the error I keep getting is
File "KingsBounty.py", line 1, in <module>
ImportError: No module named newGameLib

I have reinstalled both python 2.6.2 and blender 2.49b
and have unzipped the file into the Kings Bounty Armored Princess Demo folder

It contains a folder called newGameLib, the .blend file, and KingsBounty.py
the example files gudrida.blend works perfectly fine btw.

Any Ideas about my issue?

EDIT: OOPS, nevermind, forgot to copy newGameLib into newly installed blender directory.
