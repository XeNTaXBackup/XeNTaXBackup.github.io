## Post #1
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2018-05-30T15:55:16+00:00
- Post Title: [Help] Noesis  left-hand coordinate to right-hand coordinate

I am trying to write a Noesis python script to display Rebellious Million Arthur 《叛逆性百万亚瑟王》 models.
So far I can load 99% of the models and bones in Noesis.
But my problem is the left and right side flipped!

Is there any simple way or command to change the left-hand coordinate to right-hand coordinate?
[Noesis_help2.jpg](https://xentaxbackup.github.io/file/14412_Noesis_help2.jpg)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-30T16:07:42+00:00
- Post Title: [Help] Noesis  left-hand coordinate to right-hand coordinate

> Reply from Shine
>
> 
But my problem is the left and right side flipped!
Can't you just invert the X-Axis then?
## Post #3
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2018-05-30T16:26:07+00:00
- Post Title: [Help] Noesis  left-hand coordinate to right-hand coordinate

Thanks for the reply.

Because Noesis had a well made mesh container, I just need to pass the block data and Noesis do the rest!
If I inverse the x data myself, I will end-up with losing the mesh container!
And also bones coordinate are in matrix4X4. I have no idea how to "flip" these matrices!!!
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-30T16:44:38+00:00
- Post Title: [Help] Noesis  left-hand coordinate to right-hand coordinate

> Reply from Shine
>
> 
If I inverse the x data myself, I will end-up with losing the mesh container!
I am not really familiar with Noesis and it's limitations, so I can't propose a workaround for this.

> Reply from Shine
>
> 
And also bones coordinate are in matrix4X4. I have no idea how to "flip" these matrices!!!


Depending on if the matrix is column major or row major, the translation (X, Y, Z) would be either a41, a42, a43 or a14, a24, a34. If I remember correctly it was a41, a42, a43 for Rebellious Million Arthur. So you would invert a41 if you want to invert the translation in the X-Axis.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-05-30T21:57:05+00:00
- Post Title: [Help] Noesis  left-hand coordinate to right-hand coordinate

just load the matrix with the .inverse() at he end.

boneMtx = NoeMat44.fromBytes(bs.readBytes(64)).toMat43().inverse()
