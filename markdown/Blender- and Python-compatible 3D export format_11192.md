## Post #1
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-06T09:52:21+00:00
- Post Title: Blender- and Python-compatible 3D export format?

So I've run into a snag with my model ripping experiment that isn't related to the actual format of the files I'm trying to extract models and animations from. I'm having trouble finding a good export format to work with: at first I managed to export models in .OBJ format, but then I discovered .obj doesn't support animation, so I switched to the PyCollada library so I could export them in .DAE format, but PyCollada doesn't actually allow me to export animations, so I'm back to square one.

Does anyone know of a good Blender-friendly format that has animation support and, hopefully, a decent Python library? (I suppose there's nothing stopping me from rewriting my tools in C++ or something if it comes to it, but...)
## Post #2
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-02-06T10:02:14+00:00
- Post Title: Blender- and Python-compatible 3D export format?

Try [Source SMD](https://developer.valvesoftware.com/wiki/SMD). I don't know about Python, but it has a ton of existing plugins and such.
## Post #3
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-06T10:29:36+00:00
- Post Title: Blender- and Python-compatible 3D export format?

Useful, useful. And plain ASCII to boot; it shouldn't be hard to write a Python exporter. :3

Question, though: it says I can only have one animation per SMD file. I'm fairly certain I'll have to export multiple animations; what should I do? Just string 'em all together in the same file, or export a separate file for each animation?
## Post #4
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-02-06T10:32:25+00:00
- Post Title: Blender- and Python-compatible 3D export format?

I'm pretty sure a separate file for each one would be the best plan.
## Post #5
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-02-07T18:20:55+00:00
- Post Title: Blender- and Python-compatible 3D export format?

If you're getting the data from the game using python, why not directly create a blender addon/script using its python api? You could do it for Noesis too.
## Post #6
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-08T00:48:11+00:00
- Post Title: Blender- and Python-compatible 3D export format?

Would it be possible to import data from multiple files at once that way? 'Cause that's what I have to work with. I've got meshes in one, textures in another, skinning data in yet another, what I suspect is vertex-based animations in a fourth, and finally, a big whopper file that I presume contains bones and animations. Note also that not all the meshes have corresponding files for all these data types.

Also, I know this probably marks me as hyper-noob, but what's Noesis?
## Post #7
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-02-08T00:56:24+00:00
- Post Title: Blender- and Python-compatible 3D export format?

It's a universal model viewer, can import/export pretty much anything.

[viewtopic.php?f=33&t=4582](http://forum.xentax.com/viewtopic.php?f=33&t=4582)

EDIT: And jeez, you don't need to go around thanking every single post. All I did was give you a link. 
I certainly appreciate it, but it seems a little extreme.
## Post #8
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-02-08T06:27:53+00:00
- Post Title: Blender- and Python-compatible 3D export format?

> Reply from Ryusui
>
> Would it be possible to import data from multiple files at once that way? 'Cause that's what I have to work with. I've got meshes in one, textures in another, skinning data in yet another, what I suspect is vertex-based animations in a fourth, and finally, a big whopper file that I presume contains bones and animations. Note also that not all the meshes have corresponding files for all these data types.

Yes you can. There are many ways to do it, like having a function that acceps multiple arguments for different files, taking a folder as an argument and read all files inside, accept only one file and then find the other files automatically, etc.

Blender/Noesis API is only to "build" mesh/meshes, how you get the data and pass it to those APIs is up to you, using any method in python you think is best.
I don't think there are many examples around. If you need help with python/blender ask me.
## Post #9
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-02-08T20:57:05+00:00
- Post Title: Blender- and Python-compatible 3D export format?

The fmt_gamebryo_nif.py script that comes with Noesis is a pretty good example of everything you could want to do in that realm, with handling for multiple geometry types, multi-platform texture handling and decoding/untiling, key framed animations, and lots of other crap. Sadly, meaningful documentation for Noesis still only exists in my head.
