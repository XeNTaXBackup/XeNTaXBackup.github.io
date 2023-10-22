## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2020-04-04T20:16:56+00:00
- Post Title: How to get rid of seams visible on terrain mesh?

I have a Noesis script that unpack terrain data. It's all sorted out except that there are visible tile seams.




The data is actually just a vertex cloud and no face information so I had to generate it myself. I'm not sure if this is the right way of doing it. It seems that there might be duplicates.

Here is my code for reference:



Since in the source game the terrain doesn't have seems so I'm guessing it's not the UV/texture and normals. Most like an issue with how I generated the faces. But I just can't figure it out.
## Post #2
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2020-04-04T21:37:27+00:00
- Post Title: How to get rid of seams visible on terrain mesh?

I've also tried to look into texture WrapMode and set it to NTEXFLAG_WRAP_CLAMP, NTEXFLAG_WANTSEAMLESS but both didn't make a difference.



Here is the terrain without texture:
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-04-06T03:31:24+00:00
- Post Title: How to get rid of seams visible on terrain mesh?

> Reply from majidemo ↑Sun Apr 05, 2020 4:16 am at Sun Apr 05, 2020 4:16 am
>
> 
Here is my code for reference:

...

Since in the source game the terrain doesn't have seems so I'm guessing it's not the UV/texture and normals. Most like an issue with how I generated the faces. But I just can't figure it out.
It'd be easier if you just attach the code instead of an image.  
Your problem lies on the way that you handled the data as discrete tiles rather than an integrated whole. So the "seams" are the physical edges of each tile and you can't get rid of that.

It's kinda confusing of the data structure since in your code you got a loop to traverse (width * height) tiles but each tile uses 10 vertices? Might just consider using a 2x width and height.
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-04-06T18:51:40+00:00
- Post Title: How to get rid of seams visible on terrain mesh?

Hello, from what I've seen, it looks like UV channel is leaking due low res texture. I don't know how textures looks like, so it's just an assumption.
From the screen without textures, it looks like issue with normals, I'm not a Noesis expert, but I had similar issue when model had implicit (smoothing groups) normals instead of explicit ones (but that was for 3ds max, i'm not sure, if noesis uses smoothing groups, but I believe it does), thus those nasty seams.
## Post #5
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2020-04-08T12:40:43+00:00
- Post Title: How to get rid of seams visible on terrain mesh?

Thank you for the response guys. But what fixed it was actually just changing the texture wrap to clamp. It didn't work on Noesis but on another 3d program it did. So all is good.
