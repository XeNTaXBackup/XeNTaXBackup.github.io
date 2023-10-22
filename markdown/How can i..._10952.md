## Post #1
- Username: Bitonius
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 04, 2013 4:53 am
- Post datetime: 2013-11-11T05:36:48+00:00
- Post Title: How can i...?

I have been extracting some files to obj format since its easy format but if i wanted to get bones data and the sort,
what format should i learn to extract that data to? preferably for importing to max.
Also been trying to flip dds images but whitout much success how could i accomplish this?.
Thanks
## Post #2
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-11-11T14:15:00+00:00
- Post Title: How can i...?

You need weights in the mesh data (usually in a per vertex basis: each vertex has a reference to which bones affects it and by how much (0-255 or 0-1) ) You can start by that.

Once you're importing meshes with weights, you can import the skeleton. 
For each bone you at least need to look for:
*an index
* a parent index (if no parents, usually is -1)
* a transform matrix , which varies a lot depending on the skeleton format (maybe position, scale and rotations are given separately and you have to calculate it yourself) 
* Info if the transform matrix/rot-scale-pos for each bone is given relative to it's parent or relative to skeleton/world space. This is useful also depending on how 3ds max handles bones transforms.

I'd recommend just looking some existing 3ds max script, I only remember one recent about RE6 for capcom's .mod, which has the skeleton structure pretty much all figured out. 

> Also been trying to flip dds images but whitout much success how could i accomplish this?

You shouldn't flip the image itself, only the UVs, but it's also not necessary at least in blender, you can just use mapping.scale[y] = -1, which has the same effect. Probably there's something similar in Maya/Max
## Post #3
- Username: Bitonius
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 04, 2013 4:53 am
- Post datetime: 2013-11-11T18:39:25+00:00
- Post Title: How can i...?

Mmm Very nice indeed, guess it was about time i figured what the other bytes in a vert struct could be for.
Also the image flip was for when its a CG from the game rather than a texture model since they may come upside down, manually flipping each of them on photoshop is no fun.
I thought it would just need to have its bytes inverted so that the final byte becomes the first one but it didnt work. any thoughts on it?
