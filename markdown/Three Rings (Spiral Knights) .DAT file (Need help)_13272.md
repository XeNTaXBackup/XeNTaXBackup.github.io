## Post #1
- Username: Xan the Dragon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 30, 2015 6:37 am
- Post datetime: 2015-09-01T11:23:48+00:00
- Post Title: Three Rings (Spiral Knights) .DAT file (Need help)

Hey! Visiting here from the abyss of the future?
This tool is actually done and functional. [https://github.com/EtiTheSpirit/ThreeRingsSharp](https://github.com/EtiTheSpirit/ThreeRingsSharp)

The Original Thread

I posted a thread about my PROJECT in the 2D/3D modelling section (Meaning the release of the project), however I need bit of help - Some collaborative thoughts about how I can finish up this project.

Allow me to explain everything about these .DAT files and what I want to do with them.

The Three Rings's version of a .DAT is a binary storing a 3D model (Vertices and triangles), a texture-mapping function, bone data, classes for multiple "types" of models (Particle systems, stuff like that, though it also stores animations sometimes), and places for attaching external .DAT file models/effects.

There's a program that someone tied-together called [Spiral Spy](http://spiral.onyxbits.de/download/) that uses the [open source code that Three Rings supplies](https://www.threerings.net/code/) (The first four libraries at the top) to view these models. I have taken advantage of one of the features in this code in my project already, and that's reading the XML files that the code will spit out from the .DAT.
--
If I pull up Spiral Spy, I can view my model and open a basic editor for it, you can see that there's a lot of things to play with:





From what I've noted, a lot of this is tailored to be easily read by Java, and of course, that's what the source code is written in.

So what do I want to do with them?
My goal is to be able to extract and convert these .DAT files to OBJ or FBX

As for OBJs, I need the model (of course), but I also need to get the texture mapping function from the .DAT and use that to modify the texture PNG file that it reads so that I can treat the model+texture like a UV.

I don't quite know how FBX works, but I chose it because of what it can store. I feel that using an FBX will allow me to get more out of the .DAT file

Thanks for reading! If you have anything regarding this, be sure to let me know!
