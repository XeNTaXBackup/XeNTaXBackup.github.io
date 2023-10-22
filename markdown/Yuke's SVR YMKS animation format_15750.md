## Post #1
- Username: eatrawmeat391
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Dec 06, 2016 5:51 pm
- Post datetime: 2017-01-17T04:25:16+00:00
- Post Title: Yuke's SVR YMKS animation format

Animations from SVR 2006 and 2011 (Legends of Wrestlemania as well) are contained in the YMKS format which is reverse-engineered.There are 3 types of animation in it:
- Type 1a: Used in Create A Moveset Screen (In all SVR PS2 games)
- Type 1b: Used in Create A Moveset Screen (In some SVR PSP games)
- Type 2: Used in game (Compatible with all games)
Here is the structure of my extracted animation file format:
- 01 00 00 00 : There are 1 animation in there
- 16 bytes header
+ 2 bytes: Part
+ 2 bytes: ID
+ 4 bytes: Start Address
+ 4 bytes: Header Size
+ 4 bytes: ???
- After that is the animation data
+ The last byte contains the selling animation ID(the painful animation of the receiver)
Attached below is the animations of the Normal Punch 
* PS2 group: (same animation)
- PS2_MOT_: Type 1a animations
- PS2_MOTP: Type 2 animations
* PSP group:
- PSP_MOT_: Type 2 Animation
- PSP_MOTP: Type 1b Animation
I am trying to convert Type 2 animations to Type 1a and Type 1b since their animations are the same if they are together
[0C0E-Angle Punches.7z](https://xentaxbackup.github.io/file/12241_0C0E-Angle Punches.7z)
## Post #2
- Username: eatrawmeat391
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Dec 06, 2016 5:51 pm
- Post datetime: 2019-05-11T17:15:50+00:00
- Post Title: Yuke's SVR YMKS animation format

I have done reverse-engineered it!
See this topic if you want to know about the structure 
[https://www.tapatalk.com/groups/legends ... t4123.html](https://www.tapatalk.com/groups/legendsofmodding/svr-2007-2011-ymks-animation-format-structure-t4123.html)
