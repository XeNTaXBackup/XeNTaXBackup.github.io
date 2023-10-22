## Post #1
- Username: NickRepins
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 17, 2021 6:23 am
- Post datetime: 2021-08-15T17:57:24+00:00
- Post Title: Matrices help

Hi. I'm dealing currently with reanimating old Defiance Game to other engine, expermientally : ), I have some progress so far with textures, model conversions, collision system and map positions, 

[https://www.youtube.com/watch?v=BCsSTfn38zY](https://www.youtube.com/watch?v=BCsSTfn38zY)
[https://www.youtube.com/watch?v=8fl0OLpSDZE](https://www.youtube.com/watch?v=8fl0OLpSDZE)
However !

One thing currently brings me sleepless nights. I managed to convert matrices from submatrices, multiple instanced objects such as generic (mainly):


But these 256B entries are problematic:
yellow = hashed objects ids





I'm not into matrices much, just worked with 4x4 during conversion of data from GTA LCS/VCS PS2 which wasn't hard.

I got fine translations, but rotations doesn't work to in many cases.

This stuff is much more complicated.

I hope for hints/help. Sorry if the topic might be not appropriately written.

//EDIT: found [https://www.euclideanspace.com/maths/ge ... /index.htm](https://www.euclideanspace.com/maths/geometry/affine/matrix4x4/index.htm) topic, but not sure if it is the right thing.
OK, I'll see if the multiplication did the work, but don't close the topic.
## Post #2
- Username: NickRepins
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 17, 2021 6:23 am
- Post datetime: 2021-08-31T12:01:16+00:00
- Post Title: Matrices help

I am still having problem with that complex matrix. Could someone help?

Here's the picture with data.



matrix.png (34.35 KiB) Viewed 49 times
## Post #3
- Username: NickRepins
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 17, 2021 6:23 am
- Post datetime: 2021-09-05T09:56:45+00:00
- Post Title: Matrices help

For the future problems like that one, these three unknown numbers (there are supposed to be three floating point numbers) above translation are stored as radians, X Y Z rotations. It is a bit embarrassing no one bothered to help.
