## Post #1
- Username: PiotrekPL
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 01, 2008 9:23 pm
- Post datetime: 2008-02-01T15:54:46+00:00
- Post Title: FRONT MISSION 5 Translation Project. HELP!!!

Hi all.
I have a question to you guys. We are making translation to this game here are more info:
[http://boards.gamefaqs.com/gfaqs/genmes ... c=40216520](http://boards.gamefaqs.com/gfaqs/genmessage.php?board=924653&topic=40216520)
And here:
[http://www.romhacking.net/forum/index.p ... 353.0.html](http://www.romhacking.net/forum/index.php/topic,5353.0.html)
Any one who want help is welcome.
Back to my question. I hope  if you guys can help me with localization of a file it looks like this during the game:



I was wonder if PCSX2 could help me with this because it has console in background, and it give me this:



Can this sectors help me with localization of the faile ? If yes what program do I need to use ?

Here how this look:
First i made .ISO of oryginal game disc. Then I used Munge Exprorer to extract files.



Then i can use again Munge Eexp. to extract files from DVD.dat (3,5GB).
When extracted it gives me 10017 files some are tim2 files other are .dat.
I can extract some tim's files from this dat. But in order to do that i must pack these .dat, tim2 files into ISO. by using MagicISO and from that iso file which contain tim2, .dat files unpack them as .bmp type by using TimTool.
It gave me lots of Tim2 files like character photos, menu etc... But i cant find this file i posted before. Could that be stored as text ? Any ideas ?
Ok. this shot I’m looking for is not stable, i mean first when the mission start  there is only map shown (that blue without Japanese words and white background). That white belt starts from right to left and after 2-4 sec. disappear.
BTW is there any hex that can read Japanese characters, coz my windows can't even if i install necessary files.
PLZ HELP
## Post #2
- Username: darkweb
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 13, 2007 12:11 am
- Post datetime: 2008-02-04T19:27:41+00:00
- Post Title: FRONT MISSION 5 Translation Project. HELP!!!

I'm not sure if this can help at all but it's possible that you could use the console to find where the text is.
From the console I'll assume that each sector is 2064 bytes, and you would find the data at address 1642481*2064 = 3390080784 = 0xCA108710.  If you open the ISO in a hex editor you might find the data there.  Also I'm sure there's a program out there that could tell you what file is at what sector to help narrow down the search.
The only problem is, that address is probably the graphical data since the japanese would have already been loaded into memory before displaying it.

My guess is you'd have to watch the console before the text appears and maybe if you're lucky it'll all be stored in the same spot for all text and you can easily find it by watching before every text load. (i.e. a sector read at 1400XXX amongst the 1642XXX)
Please note that this is just a guess as I don't know the PCSX2 emulator or what its output means and I don't know how the FM5 file structure is.
If any of this is wrong hopefully someone can correct me but I hope that it'll help you along the right path.
## Post #3
- Username: PiotrekPL
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 01, 2008 9:23 pm
- Post datetime: 2008-02-08T18:55:11+00:00
- Post Title: FRONT MISSION 5 Translation Project. HELP!!!

Thank you so much for your answer. I will check later and see the results. As you wrote the text is probably sited as a graphical file since i found that menus are stored as TIM 2 file. The only thing is that they are static whereas sentence on the screen (whole white belt with it) is moving. BTW if any one know about that program that find files using sector could you give me address, information where I can find the software ?
Thank You again for your interest "darkweb".
