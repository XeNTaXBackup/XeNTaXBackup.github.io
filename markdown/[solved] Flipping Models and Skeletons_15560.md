## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-12-01T07:14:52+00:00
- Post Title: [solved] Flipping Models and Skeletons

Hello,

I have been asking questions here for awhile now about unpacking 3d model files and bones and have successfully done them with help.

But today, after 2 months of working on this, I realized that all the files I unpacked are flipped.

This is an example taken from the actual game:



You'll notice that the weapon, and animation is on the right hand.

While this is the result from the data I extracted (put into WebGL or OpenGL):



The weapon and the animation of holding it is on the left side.

I do realize that flipping the mesh/3d model would require me to multiply -1 to the axis where I want to flip. (axis * -1)
But it isn't as easy for the bone/skeleton.

So my question is: How do I flip the bones and animation? so that the animation/holding of weapon is on the right side?

Additional Info:
The bone matrices are local to heirarchy. 
The animation frame matrices are also local to heirarchy.

I also tried loading my files into Noesis just to check if it is an WebGL/OpenGL issue but I got the same flipped result: (I'm assuming Noesis uses DirectX)
## Post #2
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-12-01T13:28:25+00:00
- Post Title: [solved] Flipping Models and Skeletons

I tried multiplying the x-axis of the vertices with -1. So `vx, vy, xz * -1`.

Which gave me this result:



I noticed that the face is getting culled, so it must due to the backface culling. So I reversed the order of the faces, instead of "f1, f2, f3" I made it "f3, f2, f1".

Which gave me this result:




But now the problem is that the skeleton/bones is facing the other direction. (still can't figure this out)
## Post #3
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-01T15:59:08+00:00
- Post Title: [solved] Flipping Models and Skeletons

For a ghetto solution you could invert the axis in your vertex shader after applying the skinning, before applying the other transforms.
## Post #4
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-12-01T16:04:16+00:00
- Post Title: [solved] Flipping Models and Skeletons

Hello,

I did try this. Which actually works, after changing the rendering side to BackFace/Side. But I would like to fix this on my file itself and outside the application. So the application just reads the data directly.
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-12-01T18:45:34+00:00
- Post Title: [solved] Flipping Models and Skeletons

[out]
## Post #6
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-12-01T22:55:32+00:00
- Post Title: [solved] Flipping Models and Skeletons

Thank you  I have one question though, whats the formula for converting the bone matrices to worldspace? Or modelspace? And back?
## Post #7
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-01T23:59:19+00:00
- Post Title: [solved] Flipping Models and Skeletons

To get a bone's world transform, you multiply a bone's local transform by its parent's world transform (if the bone doesn't have a parent, copy the local transform to the world transform).

For the other way around, you multiply the bone's world transform by the inverse of the parent's worldtransform (any copy world to local for parentless bones).
## Post #8
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-12-02T03:34:00+00:00
- Post Title: [solved] Flipping Models and Skeletons

Great, I'll try this out tonight and give you guys feedback
## Post #9
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-12-03T09:53:20+00:00
- Post Title: [solved] Flipping Models and Skeletons

I negated the values as told by sir Wobble,

I did it like so:

```
                (      modelMatrix[0],       modelMatrix[1],  -1 *  modelMatrix[2],        modelMatrix[3]  ), 
                (      modelMatrix[4],       modelMatrix[5],  -1 *  modelMatrix[6],        modelMatrix[7]  ), 
                ( -1 * modelMatrix[8], -1 *  modelMatrix[9],  -1 *  modelMatrix[10], -1 *  modelMatrix[11] ), 
                (      modelMatrix[12],      modelMatrix[13], -1 *  modelMatrix[14],       modelMatrix[15] ) 
            ))
```

While it did correct the handedness of the bones, it messed align some. Figured here:


Some bones are in the correct position, while one bone is too long, and the hands are a on a narrower angle. Did I make a mistake on the negation?

----------------------------------
UPDATE (fixed rest pose)

I did make a mistake, I realized negating modelMatrix[10] wasn't necessary. Correcting that, fixed the whole thing. Thanks a bunch
