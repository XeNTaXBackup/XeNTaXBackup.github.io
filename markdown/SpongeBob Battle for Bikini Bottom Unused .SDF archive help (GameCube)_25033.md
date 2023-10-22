## Post #1
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2022-02-09T21:53:53+00:00
- Post Title: SpongeBob Battle for Bikini Bottom Unused *.SDF archive help (GameCube)

Hello, this game has been fully cracked as the actual used archives of the game that are HIP/HOP have been fully figured out and even have a level editor for them, but no one has really talked about the leftover *.SDF archives that seem to contain data as well. These *.SDF files are ignored by the game, but I'd like to see if they reveal anything useful as well, and would love some help in seeing if they are an actual archive file. Thanks if you can help! 

Samples here: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1lR-ZISWmnAsZ7OCMVyfAo-rrUdNzMD_c?usp=sharing)

thanks!
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-09T22:34:47+00:00
- Post Title: SpongeBob Battle for Bikini Bottom Unused *.SDF archive help (GameCube)

Those SDF files don't look like archives to me. They seems to be containers for some structures for changing game logic (like triggers, environemnt variables, events etc.)


Look on those strings for example:

```

TRIG_SFX_SPRINGBOARD
TRIG_SFX_SPRINGBOARD_05
EnterPlayer
SPRINGBOARD PROP SFX 05
Play


TRIG_SFX_SPRINGBOARD_05
ExitPlayer
SPRINGBOARD PROP SFX 05
Stop
```

It is some logic for playing music in game.

Data is not encrypted or compressed so you can view it in hex editor.
## Post #3
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2022-02-09T22:38:56+00:00
- Post Title: SpongeBob Battle for Bikini Bottom Unused *.SDF archive help (GameCube)

Alright, I see. Thank you for helping though!
## Post #4
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2022-02-09T22:43:42+00:00
- Post Title: SpongeBob Battle for Bikini Bottom Unused *.SDF archive help (GameCube)

Was also just told that the SDF files were probably makefiles for the HIP/HOP building. This makes sense.
