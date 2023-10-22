## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-21T04:47:57+00:00
- Post Title: Zone 66 (PC/DOS) - *.Z66

Ah, nastalgia. Yes, again digging up an old one. Some people still play this game (including me). It is a scrolling shooter/bomber from back then.

I have realised that all files are put in *.Z66 and they seem compressed or at least seemingly. I will attach samples to see if that is indeed the case.

The game is old yet still fun and would be an excellent candidate to modify (eg, add own ships, music, etc) and that seems possible with the way they are structured.
[ZONE66stuff.rar](https://xentaxbackup.github.io/file/1067_ZONE66stuff.rar)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-21T05:27:58+00:00
- Post Title: Zone 66 (PC/DOS) - *.Z66

very compressed.

but atleast i can tell the first longword contains length of the unpacked data!

other than that....im screwed =D
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-21T05:44:51+00:00
- Post Title: Zone 66 (PC/DOS) - *.Z66

Thanks, thats step one, next comes figuring out the compression used. And I think that would require Deniz or john_doe. I'll see if I can catch Deniz about this if he has time after Cyberbykes. He like me is getting ready for exams near the end of the month or so. Hands tied and all.

I dunno, my area is modding, not compression and only very minor data extraction >_<

But I have managed to modify ship data but it too is compressed, unamed stats like armor and speed...

Thanks for the confirmation in ant case
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-22T03:53:41+00:00
- Post Title: Zone 66 (PC/DOS) - *.Z66

All files use the same compression it seems. But at least I managed to do this: [Ship Data Research](http://www.geocities.com/shindarkfox/Zone66ShipData.html) (Better image if you replace JPG with PNG)

I believe those chunks that are composed of FE, F4, and etc. may be some form of compressed text or graphics even though before each ship stat is the ID for the image used by the ship (mentioned in the info under the image).

The Z66 files are pretty easy to tell what is in them. MUZ is music, GRFX is graphics, DAT is data, PREFS is preferences. Pretty self explanitory.

The problem though is that they are compressed. I do wonder if to read the data they would have to be recompressed... hm... in any case if anybody wishes to pick up on it I can give a link to the demo: [http://www.dosgamesarchive.com/download/game/182](http://www.dosgamesarchive.com/download/game/182)

I checked, the data is the same but not as much as the full version that I have.

Edit: XD I think I'll leave reverse engineering to the professionals, I'll just wait. Don't have a means to write a program. But I wanted to see if I could understand it.

-Darkfox
