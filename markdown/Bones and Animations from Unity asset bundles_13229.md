## Post #1
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-08-21T11:03:39+00:00
- Post Title: Bones and Animations from Unity asset bundles

Hi, I have loads of .assetbundles from a game called FusionFall Heroes (free2play) that I have extracted using DisUnity, and the mesh and textures extract fine. However, all of the bones and animations are there but in .bin files. I managed to get some rigs using a skeleton combin script and a maxscript to import it made by zaramot, but I can't add the mesh after, and each character has seperate meshes. Here are some examples of this:
[http://imgur.com/a/6boUc](http://imgur.com/a/6boUc)

Does anybody know if I can get those animation files to work and the rig?
here are all the files:
[https://drive.google.com/file/d/0B_-GS3 ... sp=sharing](https://drive.google.com/file/d/0B_-GS3PsP41CNE5yRzA5UkRCQU0/view?usp=sharing)

Thanks a lot guys:)
## Post #2
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2015-08-21T14:37:26+00:00
- Post Title: Bones and Animations from Unity asset bundles

The best thing for that is to merge the whole thing yourself.

Usually in games each mesh has it's own rigged skeleton even if it's the same, specially when it's the kind of character with switchable meshes.

Try to do a maxscript that calls both the mesh script and the rig script, so you can put both together at the same time, i don't really know where the vertex weight data is, but if you manage to get both in the scene that way you can just find the mesh in the scene and start rigging it.
## Post #3
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-08-21T19:35:16+00:00
- Post Title: Bones and Animations from Unity asset bundles

> Reply from Seyren
>
> The best thing for that is to merge the whole thing yourself.

Usually in games each mesh has it's own rigged skeleton even if it's the same, specially when it's the kind of character with switchable meshes.

Try to do a maxscript that calls both the mesh script and the rig script, so you can put both together at the same time, i don't really know where the vertex weight data is, but if you manage to get both in the scene that way you can just find the mesh in the scene and start rigging it.

thanks for the reply but I don't know how to make a maxscript ;/ what about animations? all the bone movement data is there, do you think its possible to salvage them?
