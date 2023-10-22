## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-09-02T14:57:33+00:00
- Post Title: Darkwind: War on Wheels - ogg variant

Hi everybody!
I'm having problems getting the music from Darkwind: War on Wheels. No idea what kind of oggs these are. You can download the client here: [http://www.dark-wind.com/doDownloads.php?file=exe](http://www.dark-wind.com/doDownloads.php?file=exe). Maybe you have to register.
Here's a screenshot of the header:

Any help is appreciated!
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-09-05T02:40:23+00:00
- Post Title: Darkwind: War on Wheels - ogg variant

Just add 0x23 to each byte, I'll crank out a vgmstream for this in a few.

Done, up in r999.  I wasn't able to get a file to test, let me know how it works.  It's possible they only mess with the setup headers.
## Post #3
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2012-09-08T08:34:10+00:00
- Post Title: Darkwind: War on Wheels - ogg variant

Either r999 or r1000 didn`t help to solve that problem, I did even attempt using command-line decoder to become sure.
Here`s sound folder structure, I can upload any of root directory files (they`re most definitely music tracks) for testing. However some jingles/stingers may happen to be in other folders as well but these 6 OGGs are wanted way more than those possible musical cues.

crashes\	        <DIR>
engines\	        <DIR>
environment\	<DIR>
explosions\	<DIR>
gui\	                <DIR>
pain\	        <DIR>
skids\	        <DIR>
voice\	        <DIR>
weapons\	        <DIR>
a666.ogg	4 184 631
bishibashi.ogg	5 739 564
dust.ogg	856 480
mashhead.ogg	4 057 205
pushTheButton.ogg	3 947 601
riseAndFall.ogg	6 381 967
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-09-10T01:52:26+00:00
- Post Title: Darkwind: War on Wheels - ogg variant

It's quite possible that there is a different key for each file, if you could post a hex dump of the beginning of a nonworking file I could see if that's the case.
## Post #5
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2012-09-11T03:12:10+00:00
- Post Title: Darkwind: War on Wheels - ogg variant

Hope this helps.
[a666.ogg](http://img89.imageshack.us/img89/2309/a666k.jpg)
[bishibashi.ogg](http://img43.imageshack.us/img43/1892/bishibashi.jpg)
[dust.ogg](http://img4.imageshack.us/img4/1929/dustab.jpg)
[mashhead.ogg](http://img826.imageshack.us/img826/6706/mashhead.jpg)
[pushTheButton.ogg](http://img835.imageshack.us/img835/7182/pushthebuttonl.jpg)
[riseAndFall.ogg](http://img838.imageshack.us/img838/9649/riseandfall.jpg)
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-09-11T06:28:57+00:00
- Post Title: Darkwind: War on Wheels - ogg variant

Hm, crap, they all have the same header. Is there a OggS string anywhere in the file? I may have to figure out the header size and just "decrypt" that.
## Post #7
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2012-09-11T21:09:34+00:00
- Post Title: Darkwind: War on Wheels - ogg variant

Unfortunately no, at least in those 6 files posted.
## Post #8
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-09-11T23:42:35+00:00
- Post Title: Darkwind: War on Wheels - ogg variant

It looks like every 100 (decimal) bytes the key changes. It starts off as 0x23, then 0x31.  Somewhere in the middle of the file it looks like there's 200 bytes that use the same key (0x2E).  I haven't figured out how this is generated yet, always seems to be in the range of 0x20 to 0x3F but I'm not certain.  I'm guessing a LCG with multiplier 7 but I don't have a lot to back that up.

Heh, I just realized I could brute force it with the CRCs in the Ogg headers.  Don't have time to look into it now, maybe later in the week.
