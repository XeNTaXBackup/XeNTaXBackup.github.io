## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-11T02:51:56+00:00
- Post Title: Dawngate .snap

Here is an extractor for these files.

[https://www.waystonegames.com/betaSignup/intro](https://www.waystonegames.com/betaSignup/intro)


```
idstring "pans"
comtype SNAPPY
get NBASE asize
get VERSION long
get FILES long
get TMP long
math NBASE - TMP
set FBASE NBASE
set TMP FILES
math TMP * 0x20
math FBASE - TMP
for i = 0 < FILES
goto FBASE
get NOFF long
math NOFF + NBASE
get SIZE long
get ZSIZE long
getdstring NULL 0xC
get OFFSET longlong
savepos FBASE
goto NOFF
get NAME string
if SIZE == ZSIZE
log NAME OFFSET SIZE
else
clog NAME OFFSET ZSIZE SIZE
endif
next i

```
## Post #2
- Username: Geri0n
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 27, 2013 6:38 am
- Post datetime: 2013-06-27T21:40:19+00:00
- Post Title: Dawngate .snap

This worked perfectly. However i have hit another roadblock. The .bmdl files. Do you have any idea if there is a converter or a way to open the bmdl files in a 3d software?
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-03T08:44:12+00:00
- Post Title: Dawngate .snap

Maybe it has been a little long to reopen this post, but chrrox, I must ask, how can you view these bmdl files?

T.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-03T12:57:52+00:00
- Post Title: Dawngate .snap

Model Script.

[viewtopic.php?f=16&t=11348&p=93413](http://forum.xentax.com/viewtopic.php?f=16&t=11348&p=93413)
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-03T20:13:59+00:00
- Post Title: Dawngate .snap

Hey man thnx, must have overlooked it 

T.
## Post #6
- Username: GDelscribe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 16, 2014 7:15 pm
- Post datetime: 2014-08-16T11:17:58+00:00
- Post Title: Dawngate .snap

This is what I've been looking for for a long time, mainly in the hopes of making some custom skins for fun.
Thank you very much!
## Post #7
- Username: Cypherous
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 25, 2014 10:55 pm
- Post datetime: 2014-08-25T15:01:20+00:00
- Post Title: Dawngate .snap

Hi there,

Just trying to poke around these files but noticed the pasted BMS script still leads to some unusable files, how owuld i actually use the .ogg files that it extracts, i've tried ww2ogg and that gives me an error about a missing RIFF, these are all located in the Audio_Wwise after running the BMS script on the .snap files, any help is appreciated
