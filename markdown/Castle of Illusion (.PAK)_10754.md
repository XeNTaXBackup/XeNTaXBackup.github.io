## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-05T15:29:35+00:00
- Post Title: Castle of Illusion (*.PAK)

PAK does not contain file names, only hash like MD5

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype lz4

goto 0x8
get FILES long
get SUBFILES long
goto 0xaa0a

for i = 0 < FILES
	getdstring NAME 32
	get ZSIZE long
	get SIZE long
	get OFFSET long
	get UNKNOWN1 long
	get UNKNOWN2 long
	get UNKNOWN3 long
	
	if ZSIZE == SIZE
		log NAME OFFSET SIZE
	else
		clog NAME OFFSET ZSIZE SIZE
	endif
next i
```
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-05T18:27:35+00:00
- Post Title: Castle of Illusion (*.PAK)

cool, thx ekey. models and textures protected on this one ?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-05T18:29:58+00:00
- Post Title: Castle of Illusion (*.PAK)

> Reply from howfie
>
> cool, thx ekey. models and textures protected on this one ?
Textures in TGA format. Dunno about models.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-05T19:04:31+00:00
- Post Title: Castle of Illusion (*.PAK)

can you pm me just one model please? if it looks good i'll get the game from steam and give it the old one-two.

if you cant tell which is a model file, dont worry about it and thanks .
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-05T19:14:21+00:00
- Post Title: Castle of Illusion (*.PAK)

i dont know sorry
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-09-06T04:37:08+00:00
- Post Title: Castle of Illusion (*.PAK)

Thanks for the bms, but.. data.pak it's 786mb's and unpacked it's 672Mb's, is correct?
## Post #7
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-09-06T08:44:04+00:00
- Post Title: Castle of Illusion (*.PAK)

I have 1,07GB after unpacking.  
Do you have latest QuickBMS?
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-09-06T09:29:31+00:00
- Post Title: Castle of Illusion (*.PAK)

Upgraded quickbms, now i have more data, thanks!
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-09-10T14:57:37+00:00
- Post Title: Castle of Illusion (*.PAK)

The 360 version's data.pak returns the following error:



Error.jpg (92.61 KiB) Viewed 312 times
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-10T16:34:34+00:00
- Post Title: Castle of Illusion (*.PAK)

Because console version seems use endian big
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-10T18:19:44+00:00
- Post Title: Castle of Illusion (*.PAK)

models are not protected; however, it uses a scene graph format similar to binary XML spanning multiple files, kind of similar to Project Diva PSP. pain in the ass format. might pass on this one .
## Post #12
- Username: MestreNight
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 14, 2011 1:21 am
- Post datetime: 2013-10-01T01:47:06+00:00
- Post Title: Castle of Illusion (*.PAK)

You can compress again after extracted?
Thanks!
## Post #13
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-01-18T15:00:11+00:00
- Post Title: Castle of Illusion (*.PAK)

People, help unpack data.pak from xbox 360 version of the game.
