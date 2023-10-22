## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-06T12:22:09+00:00
- Post Title: LODs - Level Of Detail

This in fact is my question. 
Lately I have dealing with one custom 3D file which apparently has several LOD's in itself. LODs are the iteration of the same 3D model but with decreased number of polygones (detail) in order for the game engine use the most detailed model when seen from close and less one when from far away. 

My question is: how in the 3D files structure those LODs are most commonly annotated?  And even perhaps more purplexing question: how you physically make such an assembly in 3D editor before even saving or exporting to  graphic 3D format. Is it that you need to "stuff" each LOD on each other with the common center point, or else?
## Post #2
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-03-08T08:50:27+00:00
- Post Title: LODs - Level Of Detail

> Reply from Xela
>
> how in the 3D files structure those LODs are most commonly annotated?

Although I'm guessing this might differ from format to format, as far as I know (provided that the the LOD system requires manually created models for each level as opposed to being automatically calculated by the engine), the commonly used parameters needed are: number of LOD levels, the ranges at which these different levels "kick in" and which models to display for each level. There might also be some hardcoded limitation as to the polycount of each LOD.

> Reply from Xela
>
> how you physically make such an assembly in 3D editor before even saving or exporting to  graphic 3D format. Is it that you need to "stuff" each LOD on each other with the common center point, or else?

Again, this might differ from format to format, but I think it's pretty safe to say (again provided they need to be manually created), that regardless all models would require the same center point (or pivot point) in order for them to be aligned properly and the transitions between them are made in a smooth seamless fashion.

The basic way to do this that I know of is to create the highest poly model (the "near" LOD if you will) first and then create the lower poly LOD's from copies of that and by removing detail. The challenge being to create a similar "contour" for all LOD levels, regarding of which one you use and from which angle it is viewed.

Sorry that I can't be of more help.

Cheers

N
## Post #3
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-07-16T06:31:14+00:00
- Post Title: LODs - Level Of Detail

In regards to the second thing-- I believe that's actually what's done. A few programs like 3DS MAX let you name meshes/objects, etc. contained within a  single file. I think they just jam it all together in one big mess of polygons. The RTS game Dawn of War actually does this for different weapons/heads, etc. on unit models.
## Post #4
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-07-20T11:51:50+00:00
- Post Title: LODs - Level Of Detail

It's hierarchal.

Root->
-Mesh_01->
--Sub_Meshes
-Mesh_02->
--Sub_Meshes
-Mesh_03->
--Sub_Meshes

At least for most Models.

Within that most are also Chunk Based. Where each chunk holds different data. Typically Verts List, Vert Index, Triangle List, Triangle Index, Material List, Material Index, Morph List, Morph Index, etc etc etc....
