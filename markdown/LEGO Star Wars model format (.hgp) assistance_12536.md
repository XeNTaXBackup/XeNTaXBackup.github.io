## Post #1
- Username: Leftmostcat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 04, 2014 9:14 pm
- Post datetime: 2015-01-23T14:46:11+00:00
- Post Title: LEGO Star Wars model format (.hgp) assistance

I've been working on figuring out this format for some time now, but I'm still quite new to reversing model formats and have had little success. I would greatly appreciate it if someone would be willing to help me out, particularly someone willing to talk me through what they're doing. So far all I've managed to figure out is that vertices seem to be separated into meshes stored rather late in the file. (In the gonkdroid.hgp file from the demo, available at [http://www.gamewatcher.com/mods/lego-st ... -wars-demo](http://www.gamewatcher.com/mods/lego-star-wars-mod/lego-star-wars-demo), the first of these is at 0xF000.) Each vertex has 36 bytes. The first 24 bytes are six floats representing position and what I believe to be the vertex normal. I've been able to pick out a single mesh and render it as points to largely confirm the positions. However, I have been unable to determine how the file encodes where meshes are found, how the textures (stored inline as DDS) are found or linked to vertices, etc. Any help you guys could provide would be much appreciated.
