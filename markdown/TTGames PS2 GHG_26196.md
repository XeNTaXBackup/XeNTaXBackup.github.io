## Post #1
- Username: xMcacutt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 15, 2023 6:06 am
- Post datetime: 2023-01-15T01:22:45+00:00
- Post Title: TTGames PS2 GHG

Hi all, 
I'm currently considering working on a PC port of Haven: Call of the King. The biggest hurdle to doing this is understanding the model formats that Traveler's Tales used at the time. A lot of work has been done on the PC and New Generation Console versions of the GHG file but little to no effort has been put into the PS2 GHG.

In trying to understand the format, I came across someone called DarkShadow Nemo who was working on the GHG for a Finding Nemo port but he has since stopped working on the game. I don't understand most of what he found but I read through his code, rewrote it to be simpler for myself and here's what I know so far.
(I decided to go with conversion to the obj format for now because of how easy it is to understand but as I begin to work on bones, UVs, etc, I will move to a different format or finally learn the blender api)

The GHG format is a chunk based model format. The chunks have identifiers but there's more than one ID used across the files.
Most main characters use x04/x02/x00/x01.
Most objects use x03/x01/x00/x01
Chunks can almost always be found by searching for x00/x01/x03/x80 which seems to be a universal ending to the chunk ID.
From here, the following byte is double the vertex count for the chunk so if the bytes are x03/x80/x0A then looking at the byte after the universal ID, we have x0A. This means there are 5 vertices to the chunk (A=10 divided by 2 = 5)
I'm unsure of what the following byte is but skipping that, we then start the vertices.
The vertices are structured in groups of 8 floats. The first 3 are the coordinates (vx, vy, vz) the fourth float was labelled by DarkShadowNemo as nz but I don't know what that means. The next 3 floats are the vertex normals (vxn, vyn, vzn) and the final float was labelled by DarkShadowNemo as nzx but I don't know what that means either (there are no comments in his code.) 

Using this knowledge, I created a simple python script which takes in a GHG file and outputs an obj point cloud file. This does successfully create a seemingly accurate point cloud. Both DarkShadowNemo and I have reached this point. The issue comes with trying to figure out the faces.
I think DSN gave up and claimed that the model format is just broken and creates unnecessary faces that have to be cleaned up manually. That seems highly unlikely to me.
Firstly, I tried using triangle strips. I thought that perhaps the vertices within a chunk made up their own triangle strip so I defined a triangle strip for each chunk with the ID of all of the vertices in the chunk under one face. 
For example: for the first chunk in a file with 7 vertices,
f 1 2 3 4 5 6 7
and so on. This does not work and leads to a lot of unnecessary faces as well as faces being missing.
DSN's solution is to assume that essentially all faces are part of one big triangle strip. This does not work either. It ends up with an absurd amount of unnecessary faces to the point that I think one or two of the Haven models were refusing to load into blender for him.
Since neither solution using triangle strips works, I'm inclined to believe there is a face table of some sort in the files. At the end of each chunk there is some sort of list which has the potential to be a face table but it doesn't quite work. The highest numbers don't reach the size of the highest vertex (for Haven's model, the vertex count 2737 is not present in the file anywhere) and if it is vertex IDs within the chunk then some of the numbers in the table go too high for the amount of vertices. 

I'm not experienced at all in terms of 3D model formats. This is new to me but I'm very interested in learning as much as I can and really want to crack this format. It's been unexplored for long enough. If anyone with more experience has any idea about getting the faces to work, I'd love to hear about it. 
Thank you 

Attachments are being weird so I've uploaded like 6 of the GHGs in a zip to my google drive
[https://drive.google.com/file/d/1bJ6T9K ... sp=sharing](https://drive.google.com/file/d/1bJ6T9KZGlABgYOQ25ymmtMcDdVnZuwhx/view?usp=sharing)
## Post #2
- Username: xMcacutt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 15, 2023 6:06 am
- Post datetime: 2023-01-17T12:16:23+00:00
- Post Title: TTGames PS2 GHG

This section of bytes is at the end of the chunk. The section always starts with x01/x01/x00/x01 and almost always ends with x40/x02/x30/x12/x05
I believe this is the face data but I'm not certain about that. I don't quite understand how the faces are stored here. There's a chance it isn't face data but I can't see anywhere else in the entire file that faces would make sense.
I noticed the hilbert numbers which always appear in this section of every chunk in every file but don't know their significance. If anyone has any insight into what might be going on here, do let me know.
## Post #3
- Username: spritdefensive
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 16, 2023 12:35 pm
- Post datetime: 2023-08-16T04:38:36+00:00
- Post Title: TTGames PS2 GHG

Because g3DTZ doesn't have a re-import feature, I utilized offzip to export the font data from the game.dtz file after discovering its location.
This is the offzip command I use: the output of offzip.exe -z -a game.dtz
And all that comes out is a GAME_unpack.A DTZ file contains both font and picture information.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-16T18:24:28+00:00
- Post Title: TTGames PS2 GHG

VIF-tags again - we had that fun already: 
> Reply from shakotay2 ↑Sun May 02, 2021 5:31 am at Sun May 02, 2021 5:31 am
>
> 

This time (captain.ghg) I met a strange occurrence that some vertices of each sub mesh don't "join" the body:
.



Captain-ghg.png (68.18 KiB) Viewed 82 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-16T18:34:58+00:00
- Post Title: TTGames PS2 GHG

Well, maybe I should try use half of the counts? (couldn't believe it)
There's a second block (marked blue) which also gives part of the body and more dislocated vertices:
.



VIF-tags-GHG.png (42.76 KiB) Viewed 81 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-16T18:59:07+00:00
- Post Title: TTGames PS2 GHG

Well, half count looks better but it's not complete. The second blocks gives 49 sub meshes only (block 1: 133):
.



betterButNotComplete.png (42.15 KiB) Viewed 76 times
