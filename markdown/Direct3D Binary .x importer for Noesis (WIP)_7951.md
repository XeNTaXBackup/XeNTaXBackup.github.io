## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-29T01:51:48+00:00
- Post Title: Direct3D Binary .x importer for Noesis (WIP)

This is a general noesis plugin that should parse any (uncompressed) binary .x format that follows the specs [here](http://msdn.microsoft.com/en-us/library/windows/desktop/bb173014%28v=VS.85%29.aspx) correctly. That includes custom templates.

I don't know how to decompress the compressed formats (lzw or zip), but if someone knows and tells me I might be able to add that to it.

Script: [http://xtsukihime.webs.com/Noesis%20Plu ... tX_xbin.py](http://xtsukihime.webs.com/Noesis%20Plugins/fmt_DirectX_xbin.py)
Will require latest version of the Sanae interface cause I keep adding meaningless things to it. Like checking whether a file exists or not (self.file_exists(path) vs. rapi.checkFileExists(path))

[](http://i.imgur.com/OTacp.jpg)[](http://i.imgur.com/d4Zmi.jpg) [](http://i.imgur.com/dBZbF.jpg) 

Nanoha;Fate, from magical Battle Arena (left)
Big Rose, from Ran Online (right)


This will be slow for sufficiently large files because it is written rather inefficiently.
Actually I am quite surprised I have managed to write such inefficient code lol
For files that are like 5 MB, it already takes about 5 seconds to parse.

*Currently assumes materials are defined with their meshes. Some formats define all used materials first before the meshes are defined. Have not decided how I should handle those.

*For the MeshMaterialList template, I currently assume the faces are sorted by material used (ie: [0, 0, 0, 1, 1, 1, 2, ... ]), but I know some formats don't follow this and just put whatever number they want in whatever order. That would force me to assign faces one at a time which is not hard! But annoying and will slow things down even further.

*For texture names, I strip off the directory path and assume everything is the same folder as the model.

Test it on various binary .x files and if there are issues send me the file.

============= Implementation details that can be ignored. ======
If you have any ideas for improving the parsing speed (aside from writing it in C++) let me know. I couldn't think of anything besides this.

It uses a tree design, where each node in the tree represents a template object.
Each template object will have a name, a list of templates, and a list of tokens.

The name is just for me to quickly identify what template I'm looking at.
The tokens store all of the record-bearing tokens associated with this template.
The templates are a list of templates that are contained in this template.

So the first step of the parsing takes the .x file and builds this tree.

I then traverse the tree, node by node, and organize the data from the templates. For now I've only put together the meshes and materials, so here I used a dictionary to store all of the data for a particular mesh (I use a dictionary because some files may not use certain things).

And then finally I go to that dictionary and build all of the meshes.

So a 3-step parsing in hopes of writing a generic bin .x parser.
At least it works for the .x files I found in my archives so far.

I haven't done anything with bones or animation, but the design should be flexible enough to add those without any problem.
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-10T19:16:11+00:00
- Post Title: Direct3D Binary .x importer for Noesis (WIP)

Amazing advance finale   , question its, support weights or skinin?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T19:56:50+00:00
- Post Title: Direct3D Binary .x importer for Noesis (WIP)

Nope. I've parsed the data, I just don't know what to do with it lol
## Post #4
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-10T20:02:15+00:00
- Post Title: Direct3D Binary .x importer for Noesis (WIP)

I don't know about x format, but it should probably have a 64byte 4x4 transform matrix for each bone (position, rotation, scale), 1-4 bone weights for each vertex (bone weight is a float value from 0.0 to 1.0 telling how much the vertex is influenced by that bone) and 1-4 bone indexes or bone names for each vertex (which is used to specify which bones affect each vertex).
