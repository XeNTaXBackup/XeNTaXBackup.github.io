## Post #1
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-07-26T11:51:19+00:00
- Post Title: Raiders of the broken planet BETA

Got key for closed beta, really interested in getting models from this game, Mercury Steam has really pretty artwork in their recent games.
Thus, we have 9 gigs of preload with archives in .packed format. I think it's same name as for Scrapland and Jericho- their previous games, but i had no chance to get models out of them for now.
Let me know if you are interested in research)
## Post #2
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-07-28T23:10:39+00:00
- Post Title: Raiders of the broken planet BETA

Is anyone interested?
Game looks pretty
## Post #3
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-07-29T00:46:49+00:00
- Post Title: Raiders of the broken planet BETA

There's no point in asking if people "are interested". The reason why your thread was most likely ignored was because you don't have any samples provided up front, so people just skip right over you and move on. Please upload sample files.
## Post #4
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-07-29T09:15:06+00:00
- Post Title: Raiders of the broken planet BETA

I wasn't sure if it's okay, so i'd rather be contacted in PM for that.

Here's link to folder on google drive. All files gonna be uploaded there eventually

[https://drive.google.com/open?id=0BwjLo ... XprYjZVY2s](https://drive.google.com/open?id=0BwjLo5mL2ME5bTl0LXprYjZVY2s)
## Post #5
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-07-29T14:11:26+00:00
- Post Title: Raiders of the broken planet BETA

Script for QuickBMS:

```
# Written By Anex For QuickBMS

idstring "BFPK"
get NULL long
get NULL long
get FCOUNT long

for i = 0 < FCOUNT
	get FNSZ long
	getdstring NAME FNSZ
	get SIZE long
	get OFFSET long
	get NULL long
	log NAME OFFSET SIZE
next  i

```
## Post #6
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-07-29T20:20:55+00:00
- Post Title: Raiders of the broken planet BETA

Again, thank you, i've replied you on zenhax.
Here's sample folder of some models 
[https://drive.google.com/open?id=0BwjLo ... Xc5OW0zVG8](https://drive.google.com/open?id=0BwjLo5mL2ME5Z25aYXc5OW0zVG8)
## Post #7
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-09-30T00:12:00+00:00
- Post Title: Raiders of the broken planet BETA

Updated script:

```
# Written By Anex For QuickBMS

idstring "BFPK"
get CHECK long
if CHECK  != 0x100
get NULL long
endif

get FCOUNT long

for i = 0 < FCOUNT
   get FNSZ long
   getdstring NAME FNSZ
   get SIZE long
   get OFFSET long
   get NULL long
   # getdstring SKIP 0x8 		#uncomment if ripping from any other version other than beta!
   log NAME OFFSET SIZE
next  i

```

Should support now beta + present version archives.
## Post #8
- Username: Big Boss
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 31, 2020 9:10 am
- Post datetime: 2020-03-12T21:51:25+00:00
- Post Title: Raiders of the broken planet BETA

Does anyone here know how to recreate a .packed file with more files inside?
