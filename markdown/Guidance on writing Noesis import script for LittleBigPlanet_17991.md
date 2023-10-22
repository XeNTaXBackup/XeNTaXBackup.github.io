## Post #1
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2018-04-17T19:29:15+00:00
- Post Title: Guidance on writing Noesis import script for LittleBigPlanet

Hi there!

I'm currently in the process of writing a tool set in Java for manipulating and extracting the various formats in the LittleBigPlanet games on PS3, PS4 and PS Vita. I've got a lot of it down but models are still up in the air. I'm unfamiliar with both 3D Model formats and Python, so I figure this is the best place to come to learn a little bit of both!

I figure having a Noesis script that can convert the meshes with bones would be a good learning experience & a good resource for my tool as it would help me understand the format better. I've read some tutorials and watched some tutorial videos online but I think the best learning experience for me personally is if someone could help me write a Noesis script specifically for this game & explain what it all means, because I already understand most of this game's formats and adding this to my arsenal of knowledge would be great  

So anyway, what I do know, is that the models are compressed and are done so as follows:

(And I didn't say in the image but there's also a dependency table at the bottom of the file. It's used to preload assets the model requires in the game's engine, like textures and materials. It's irrelevant in our case though, that gets too complicated as it searches for each UID in a huge database and it's a headache. Maybe down the line!)

And there is a thread about using Hex2OBJ on the decompressed data here: [viewtopic.php?f=16&t=12646](http://forum.xentax.com/viewtopic.php?f=16&t=12646)

Here are some samples, from all 3 games:
[http://puu.sh/A5cXe.zip](http://puu.sh/A5cXe.zip)

Thanks if anyone can help me out!
