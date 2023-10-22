## Post #1
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2018-09-11T16:11:16+00:00
- Post Title: mysterious texture maps in FFXV

A lot of the FFXV texture map formats have been documented by modders, but a number of maps (particularly ones with the NPCs) have yet to be explained.  I'm wondering if anyone here might know how some of these work.  There are two types in particular that are baffling.

1. the "_mm" maps.  [https://imgur.com/a/HimUI6t](https://imgur.com/a/HimUI6t)

These look like recolor maps to me and are clearly meant to be overlayed on the diffuse texture in some way, but I'm not sure how.  Keep in mind the ModOrganizer (which only takes FBX) cannot make use of any Blender Cycles nodes or PBR nodes in general, so I need to find a way to make use of these in Blender render.

2. the "_noto" maps. [https://imgur.com/a/Rvx7ROd](https://imgur.com/a/Rvx7ROd) 

These maps appear with many of the npcs and appear to have all textures, including the normals, stacked into one file, but I'm not certain how to extract/decompose them properly. 


I've linked imaged of each file with their original file name.  Any thoughts would be much appreciated.  Thanks!
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-11T22:36:59+00:00
- Post Title: mysterious texture maps in FFXV

those _mm look like merged rgb channels. it usually contains roughness and metalness and wtf all in one texture, just in the r, g and b channels. all good.

the 'not to' do texture contains a normal map and some other stuff in the blue channel. the nottodothat stuff is the texture compression with multiple and different uv channels and data. it's messing up the fragment compression. i know dice compresses and fucks up their battleshit data like that, but you should not do that. it breaks normals or any data at the data 'collision edges'. looks like garbage.
