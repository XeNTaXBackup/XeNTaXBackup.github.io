## Post #1
- Username: DarkStar18
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 24, 2019 3:58 am
- Post datetime: 2019-10-23T20:50:44+00:00
- Post Title: [PC] Tanktics

[http://en.wikipedia.org/wiki/Tanktics_(1999_video_game)](http://en.wikipedia.org/wiki/Tanktics_%281999_video_game%29)

This was our favorite obscure title back in the day. A unique combination of real-time strategy/combat, inventory management and puzzle aspects...topped off with absolutely murderous difficulty and no in-game saving. Yikes!

I recently broke out the CD and wondered if the 3D models for things like the component parts of the vehicles, the overhead 'cranes' and the various terrain pieces could be extracted. Will be glad to share my .ISO as the developer (DMA Design Limited, now Rockstar North) is an ESA member but the game is not protected since 2010.
## Post #2
- Username: DarkStar18
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 24, 2019 3:58 am
- Post datetime: 2019-11-26T08:33:25+00:00
- Post Title: [PC] Tanktics

Took me a bit to dig it up, but here as promised.

[https://drive.google.com/open?id=1GuTEp ... JDQqXIa1AR](https://drive.google.com/open?id=1GuTEp2l_UzpvfU4HXhC8B6JDQqXIa1AR)

And also, my old campaign save with all the levels cleared! Just drop it in the "saves" folder in the root directory.

[https://drive.google.com/open?id=1BCJFk ... R1lIlu0k2n](https://drive.google.com/open?id=1BCJFkRpe7goSvE7b6i2T_OR1lIlu0k2n)

Amazingly it installs on Windows 7 without any fuss. The directory structure couldn't be simpler. In the "Data" folder there are two subfolders, "Audio" with plain old .wav jingles that play when you win or lose a level. All the cutscenes are avi files in the "movies" folder. 

Everything else is in "tankdata.bin": 

[https://drive.google.com/open?id=1mh3a- ... Km4s6Pn7UV](https://drive.google.com/open?id=1mh3a-iBns6hTRfEWCnTO_JKm4s6Pn7UV)

Opening it in a hex editor shows "KALI" as the first few bytes and farther down the text displayed onscreen during tutorial missions. Everything else is a bunch of unknown gobbledeygook.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-26T15:43:03+00:00
- Post Title: [PC] Tanktics

100s of point clouds, hard to handle:
.



tankdata_bin.png (46.8 KiB) Viewed 26 times



You could use these 6 lines in an H2O file as another starting point for point clouds (FVFsize= 25) :

0x0 500
Vb1
25 99
0x62E426 5713
020400
0x0 255
## Post #4
- Username: DarkStar18
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 24, 2019 3:58 am
- Post datetime: 2019-11-26T16:00:08+00:00
- Post Title: [PC] Tanktics

Yikes! That looks nasty indeed!

What about running the game and using a tool to rip the models from RAM?
