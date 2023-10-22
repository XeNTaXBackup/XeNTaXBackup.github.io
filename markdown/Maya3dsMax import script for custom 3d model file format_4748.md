## Post #1
- Username: djoscar
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Dec 17, 2009 4:59 pm
- Post datetime: 2010-07-13T14:25:15+00:00
- Post Title: Maya/3dsMax import script for custom 3d model file format

Hello

I would like to write a script or plugin for either Maya or 3ds Max to import a 3d model from one game.
I do have programming experience using several languages and experience in 3d modelling, how ever I've never tried writing any scripts or plugins for any of that software.

I'm sure at least some of people here know how to do it. Could you please point me to the right direction, or link me to some tutorials or something?
I tried googling, but can't seem to find any documentation on writing importers for custom 3d model files 

Thanks
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-13T17:16:16+00:00
- Post Title: Maya/3dsMax import script for custom 3d model file format

post your 3d model you want to import and then weather you want to make a script for blender or 3ds max and someone can point you in the right direction.
## Post #3
- Username: djoscar
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Dec 17, 2009 4:59 pm
- Post datetime: 2010-07-13T18:35:34+00:00
- Post Title: Maya/3dsMax import script for custom 3d model file format

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-14T02:00:39+00:00
- Post Title: Maya/3dsMax import script for custom 3d model file format

those models are from runescape i found a model viewer for those [http://www.moparscape.org/smf/index.php?topic=385295.0](http://www.moparscape.org/smf/index.php?topic=385295.0)
## Post #5
- Username: djoscar
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Dec 17, 2009 4:59 pm
- Post datetime: 2010-07-14T08:06:08+00:00
- Post Title: Maya/3dsMax import script for custom 3d model file format

I know.. That's what I said in the first post that there are plenty of viewers and converters for this format, but all of them convert to formats like .mqo and .3ds, so only the mesh is converted.

I want to write a 3dsMax import script or something which would import the model WITH skeletal and everything, not just mesh. That's why I posted this topic lol. 

I've been trying to write the script all day today, but I fail for several reasons. First of all I don't have enough knowledge, and second of all the format is somewhat different from other model formats... Info like vert, face count etc. is stored in footer instead of header, and the whole thing is just plain weird. E.g. if model has 1917 verts (077D in hex), I'd look for the reverse of that (7D07) using hex editor, but it's not reversed there and it's stored normally like 077D... That fucks everything up when I try to make maxscript read the vert count, because when it reads it, it reads it in reverse order, so instead of reading 077D it reads 7D07 which is not the right vert count :S
uhh this gives me headache
## Post #6
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-07-15T10:33:00+00:00
- Post Title: Maya/3dsMax import script for custom 3d model file format

[out]
## Post #7
- Username: djoscar
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Dec 17, 2009 4:59 pm
- Post datetime: 2010-07-15T12:53:38+00:00
- Post Title: Maya/3dsMax import script for custom 3d model file format

The old and new format is almost the same. Footer of the new format might have few extra things but other than that it's same.
My friend wrote a tool a while ago which converts the models to .3ds using the information above and the tool works perfectly fine with old AND new models
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-07-15T23:01:00+00:00
- Post Title: Maya/3dsMax import script for custom 3d model file format

[out]
