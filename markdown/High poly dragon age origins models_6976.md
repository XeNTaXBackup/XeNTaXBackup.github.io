## Post #1
- Username: trumpdog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 15, 2010 11:28 am
- Post datetime: 2011-07-15T06:04:54+00:00
- Post Title: High poly dragon age origins models

Ive been trying to get a model ingame. The problem is the model has ALOT of polys and there seems to be a vertex limit for the weighting.Causing the model to explode ingame. example here [http://s759.photobucket.com/albums/xx23 ... t=3859.jpg](http://s759.photobucket.com/albums/xx237/trumpdog01/?action=view&current=3859.jpg)
I know it can be done, i just cant figure it out. I use blenders msh import/export scripts.Manual weight painting is pretty much out of the question for me...well out of my skill range.
Ive even tried eshmes import/export scripts for gmax and cant get anything working.As far as i can tell there is nothing physically wrong with the model [http://s759.photobucket.com/albums/xx23 ... lver-1.jpg](http://s759.photobucket.com/albums/xx237/trumpdog01/?action=view&current=silver-1.jpg)
Any advance would be appreciated.
## Post #2
- Username: drunkenchipmunk
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 24, 2009 4:05 pm
- Post datetime: 2011-07-15T09:40:54+00:00
- Post Title: High poly dragon age origins models

> Reply from trumpdog
>
> Ive been trying to get a model ingame. The problem is the model has ALOT of polys and there seems to be a vertex limit for the weighting.Causing the model to explode ingame. example here http://s759.photobucket.com/albums/xx23 ... t=3859.jpg
I know it can be done, i just cant figure it out. I use blenders msh import/export scripts.Manual weight painting is pretty much out of the question for me...well out of my skill range.
Ive even tried eshmes import/export scripts for gmax and cant get anything working.As far as i can tell there is nothing physically wrong with the model http://s759.photobucket.com/albums/xx23 ... lver-1.jpg
Any advance would be appreciated.

Game engines typically have a limit of 65535 vertices per render batch, and also a very limited number of bones, usually less than 40.

Sometimes, these constraints can be overcome by splitting the mesh into more render batches, where each render batch meets that requirement.

Doing this is quite complex, and since most of the time, game assets are not going to reach that limit (game artists are always being told NOT to reach these limits) then there's no need to prepare tools able to support this... so most tools will convert the mesh blindly without checking the limits.

The typical export process of large meshes for videogames is this:

- you create an expandable array of vertex / index buffers  (each vertex/index buffer is a render batch)
- you begin filling the first vertex/index buffer, checking all the time that you have not reached the 65535 limit
- once you reach the limit, you close the current vertex/index buffer, and add new empty ones to continue filling.

So, lets say you have a mesh with 200.000 polygons, given all of it is made of a single material, you should end with at least 4 render batches.

In practice there's many more rules to apply, like coherence of materials, bone weight usage, etc.  If you are creating a vertex buffer with bone weights, the moment you detect you're reached the limit of bone indices used within that vertex buffer, you have to close it and begin a new vertex buffer, even if the number of vertices is less than 65535.

Game engines indeed do a lot of trickery to make things done

Cheers
## Post #3
- Username: trumpdog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 15, 2010 11:28 am
- Post datetime: 2011-07-17T04:15:52+00:00
- Post Title: High poly dragon age origins models

Im not sure i understand what your saying lol. The model is split up in pieces. 1 piece has 5818 verts, 1 has 7715, 1 has 12177, 1 has 2316 and the last one has 2008 verts. The final total is 30034 verticies. less than half of the vert limit that you mentioned.12300-12500 verts seems to be the limit for the total vert count for me. anything higher causes this problem.Not sure why that is.
## Post #4
- Username: trumpdog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 15, 2010 11:28 am
- Post datetime: 2011-07-19T02:49:47+00:00
- Post Title: High poly dragon age origins models

I got it ingmae finally. Had to weight the model in blender and export it from gmax since the blender tools cant seem to export the model correctly.
