## Post #1
- Username: FoeChopper
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 30, 2021 11:27 pm
- Post datetime: 2023-10-03T18:25:10+00:00
- Post Title: Hugo Wild River / Hugo 6 - .BIG file

Hello, i try to unpack the .big file, but nothing works, i tried to use quickbms, but no success. Also tried dragon unpacker, same thing. Any ideas?
I can include the file if necessary.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-10-03T21:58:19+00:00
- Post Title: Hugo Wild River / Hugo 6 - .BIG file

If it's EA BIG file, then maybe one of these may work:
[https://forums.nba-live.com/downloads.p ... l&df_id=14](https://forums.nba-live.com/downloads.php?view=detail&df_id=14)
[https://www.moddb.com/downloads/final-big-editor](https://www.moddb.com/downloads/final-big-editor)
[http://www.ctpax-x.org/index.php?goto=f ... =3&lang=en](http://www.ctpax-x.org/index.php?goto=files&show=3&lang=en)
[https://github.com/GlitcherOG/SSX-Collection-Multitool](https://github.com/GlitcherOG/SSX-Collection-Multitool)
[https://aluigi.altervista.org/bms/ea_big4.bms](https://aluigi.altervista.org/bms/ea_big4.bms)
## Post #3
- Username: FoeChopper
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 30, 2021 11:27 pm
- Post datetime: 2023-10-04T07:32:36+00:00
- Post Title: Hugo Wild River / Hugo 6 - .BIG file

Unfortunately, none of these work :/
This file is from "Hugo Wild River" game. (Hugo 6)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-10-04T15:15:38+00:00
- Post Title: Hugo Wild River / Hugo 6 - .BIG file

Ok, so it is not standard EA BIG file. Please upload a sample BIG file to some hosting server like mega.nz, google drive etc. and share a public link here, so everyone can check it out.
## Post #5
- Username: FoeChopper
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 30, 2021 11:27 pm
- Post datetime: 2023-10-04T20:45:26+00:00
- Post Title: Hugo Wild River / Hugo 6 - .BIG file

Sure thing:

[https://mega.nz/file/Ifpm3CrD#rPmfOCL1d ... bSKB9YwqDg](https://mega.nz/file/Ifpm3CrD#rPmfOCL1ds1xe3TWMCEyHMpBTTGFhL7U5bSKB9YwqDg)
## Post #6
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-10-04T23:43:07+00:00
- Post Title: Hugo Wild River / Hugo 6 - .BIG file

Here's the QuickBMS script for your file:

```
## For use with QuickBMS

IDString "BIGFILE"
get TOC_OFF long
get BIG_SZ asize
goto TOC_OFF
for i = 0
	savepos TOC_CURRPOS
	if TOC_CURRPOS >= BIG_SZ
		break
	endif
	
	getdstring NAME 260
	get OFFSET long
	get SIZE long
	log NAME OFFSET SIZE
next i

```
## Post #7
- Username: FoeChopper
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 30, 2021 11:27 pm
- Post datetime: 2023-10-05T04:40:20+00:00
- Post Title: Hugo Wild River / Hugo 6 - .BIG file

It works perfectly! Thank you very much!
