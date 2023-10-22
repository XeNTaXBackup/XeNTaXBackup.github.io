## Post #1
- Username: AkhiMertail
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 26, 2021 1:58 pm
- Post datetime: 2021-05-26T06:02:31+00:00
- Post Title: 3d file format nightmare

I'm hoping somebody here could help me out. I'm trying to do some character modeling for a game I'm making with some friends. I finally found some good, free software to use, and everything seemed to be good until I figured it could be better. Here is the pipeline I'm using:

Create a model in makehuman 2.5

Export as a mhx file, import into Blender 2.58, clean up some weird faces created during import.

Export as a dae(here's where I need some help)

Import into Fragmotion and animate.

The issue I'm running into is that the skeleton doesn't reach Fragmotion. The Blender Collada exporter doesn't export the armature. I've tried a lot of the formats and none of them work. The directx consistently crashes whenever I export the model. The .fbx is the only one that I've found that exports an armiture, but it doesn't create faces for all the vertices(you see clothes, no person) and the bones are all whacky, idk how to describe it, but in any case it is pretty unusable. I don't really want to download more software and go through more learning curves. I know fragmo pretty well at this point and the only thing I want is to not have to skin and rig the mesh and create a whole new UV map and texture, since makehuman already does this.

In addition, Blender 2.58 uses this new python scripting thing that makes every script that I find useless. "import Blender" fails. it has to "import bpy"

Can anybody shed some light on what I can do to get this pipeline working? Should I just suck it up and learn more Blender?
## Post #2
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-05-26T11:22:22+00:00
- Post Title: 3d file format nightmare

[http://www.makehumancommunity.org/](http://www.makehumancommunity.org/)


Since I'm assuming your referring to this MakeHuman, I would just recommend you install the latest version.

It allows you to export directly to .dae or .fbx.
