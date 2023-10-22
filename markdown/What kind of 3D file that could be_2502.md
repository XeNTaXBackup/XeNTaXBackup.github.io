## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-03-09T12:48:56+00:00
- Post Title: What kind of 3D file that could be?

Here is some snipet from the text file which is suppose to be 3D.
It sits in "geometry" folder. 

> 0,54,
>
> 1,8,
>
> 0,1,
>
> 1,111,
>
> 2,54,
>
> 1,8,
>
> 2,1,
>
> 1,117,
>
> 3,258

And here is another ,but in "data" folder which could be also a candidate for 3D but I  not sure. Bothe files are not related. First is "canopy" ad second "left flap".  

> {0,18,19 }, {1,19,4 }, {5,21,6 }, {23,6,22 }, {7,6,23 }, {8,7,24 },
>
> 	{25,8,24 }, {9,8,25 }, {18,9,25 }, {0,10,9 }, {0,1,10 }, {1,11,10 },
>
> 	{1,2,11 }, {2,12,11 }, {2,3,12 }, {3,13,12 }, {3,4,13 }, {4,20,14 },
>
> 	{14,26,15 }, {28,15,27 }, {16,15,28 }, {30,16,29 }, {5,16,30 },
>
> 	{17,9,10 }, {17,14,15 }, {17,15,16 }, {18,0,9 }, {21,5,31 },
>
> 	{24,7,23 }, {26,14,20 }, {29,16,28 }, {31,5,30 }, {46,47,48 },
>
> 	{49,46,50 }, {51,49,50 }, {50,52,51 }, {53,47,54 }, {55,53,54 },
>
> 	{56,55,54 }, {56,57,58 }, {19,1,0 }, {20,4,19 }, {3,2,4 }, {4,2,1 },
>
> 	{22,6,21 }, {4,14,13 }, {27,15,26 }, {17,5,6 }, {17,16,5 }, {17,6,7 },
>
> 	{17,7,8 }, {17,8,9 }, {17,10,11 }, {17,11,12 }, {17,12,13 },
>
> 	{17,13,14 }, {48,50,46 }, {46,54,47 }, {47,59,48 }, {57,56,54 },
>
> 	{19,18,33 }, {33,32,19 }, {23,22,35 }, {35,34,23 }, {25,24,36 },
>
> 	{36,37,25 }, {18,25,37 }, {37,33,18 }, {28,27,39 }, {39,38,28 },
>
> 	{30,29,41 }, {41,40,30 }, {21,31,43 }, {43,42,21 }, {24,23,34 },
>
> 	{26,20,45 }, {45,44,26 }, {29,28,38 }, {38,41,29 }, {31,30,40 },
>
> 	{40,43,31 }, {27,26,44 }, {44,39,27 }, {20,19,32 }, {32,45,20 },
>
> 	{22,21,42 }, {42,35,22 }, {34,35,46 }, {46,49,34 }, {49,51,36 },
>
> 	{37,36,51 }, {51,52,37 }, {33,37,52 }, {52,50,33 }, {39,44,47 },
>
> 	{47,53,39 }, {38,39,53 }, {53,55,38 }, {41,38,55 }, {55,56,41 },
>
> 	{43,40,58 }, {58,57,43 }, {40,41,56 }, {56,58,40 }, {32,33,50 },
>
> 	{50,48,32 }, {35,42,54 }, {54,46,35 }, {44,45,59 }, {59,47,44 },
>
> 	{45,32,48 }, {48,59,45 }, {42,43,57 }, {57,54,42 }, {24,34,36 },
>
> 	{36,34,49 }

The last one looks like a triplets of coordinates. I think those two are part of OpenGl model, but I have no idea how to open it , view it or  neither convert to anything else.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-10T01:48:28+00:00
- Post Title: What kind of 3D file that could be?

Seems similar to the OFF ASCII format as used in the Treyarch game Die By the Sword.

Otherwise I'm not sure. Tell me, what is this from? A jet sim?
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-03-10T03:16:36+00:00
- Post Title: What kind of 3D file that could be?

> Tell me, what is this from? A jet sim?
It is a model from the jet sim, but I have no idea where from. I think it is "home made" development, I got just a model.
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-03-10T03:17:57+00:00
- Post Title: What kind of 3D file that could be?

But , how come there is no materials , no textures etc., etc ?
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-10T05:15:12+00:00
- Post Title: What kind of 3D file that could be?

That is weird. Unless the game uses a seperate script to do that for it. Possibly the jet's object script determines the textures used. Or the textures are associated by the name of the part. Just some thoughts.
