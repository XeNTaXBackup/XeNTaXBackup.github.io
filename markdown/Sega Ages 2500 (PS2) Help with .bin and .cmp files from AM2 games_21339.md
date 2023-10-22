## Post #1
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-11-04T04:12:21+00:00
- Post Title: Sega Ages 2500 (PS2) Help with .bin and .cmp files from AM2 games

Hello,
I wanted to rip models and textures from games like Fighting Vipers,Virtua FIghter 2, and Last Bronx. I tried using ninja ripper on the arcade versions but that went nowhere so I was wondering if anyone could help me with the model extraction from their PS2 Sega Ages versions? I posted samples for you to take a look.

[https://drive.google.com/open?id=1O7VzQ ... Pzm1ElLirN](https://drive.google.com/open?id=1O7VzQGxALnRCcOAwEaijb4Pzm1ElLirN)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-04T13:04:05+00:00
- Post Title: Sega Ages 2500 (PS2) Help with .bin and .cmp files from AM2 games

decompression unsolved so far:

> Reply from biggestsonicfan ↑Thu Dec 27, 2018 10:49 am at Thu Dec 27, 2018 10:49 am
>
>
## Post #3
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-11-04T15:22:00+00:00
- Post Title: Sega Ages 2500 (PS2) Help with .bin and .cmp files from AM2 games

> Reply from shakotay2 ↑Mon Nov 04, 2019 9:04 pm at Mon Nov 04, 2019 9:04 pm
>
> 
decompression unsolved so far:
biggestsonicfan wrote: ↑Thu Dec 27, 2018 10:49 am

For both file types?
## Post #4
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2019-11-09T22:10:57+00:00
- Post Title: Sega Ages 2500 (PS2) Help with .bin and .cmp files from AM2 games

> Reply from MarioSonicU ↑Mon Nov 04, 2019 12:12 pm at Mon Nov 04, 2019 12:12 pm
>
> 
Hello,
I wanted to rip models and textures from games like Fighting Vipers,Virtua FIghter 2, and Last Bronx. I tried using ninja ripper on the arcade versions but that went nowhere so I was wondering if anyone could help me with the model extraction from their PS2 Sega Ages versions? I posted samples for you to take a look.
I can't really help with ripping from the game files themselves but I have had some success with ripping models via the Nebula SEGA Model 2 Emulator. Results are mixed depending on the game but using NinjaRipper or 3D Ripper DX seem to work reasonably well.
## Post #5
- Username: biggestsonicfan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 27, 2018 9:31 am
- Post datetime: 2019-11-15T07:35:20+00:00
- Post Title: Sega Ages 2500 (PS2) Help with .bin and .cmp files from AM2 games

Hello,

Textures can be ripped with ElSemi's Model2 emulator using the "Dump Texture Cache" function.

As for models, well that isn't really the case. ElSemi's emulator only uses DirectX to render the textures onto the models, so things such as NinjaRipper or 3D Ripper DX shouldn't work as the emulator uses it's own type of rendering engine for polygons.

The ability to debug Fighting Vipers and Sonic the Fighters allows us better insight for game engine decompilation, but no models can be extracted at this time fromt he binaries.

I am working on it though, I hope to have something in the next year. Macross PS2 is going to be our best bet.
