## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-22T23:12:32+00:00
- Post Title: 3D model reversing compilation

[3D model formats index](http://wiki.xentax.com/index.php/3D_Model_Formats)
[3D model guide](http://wiki.xentax.com/index.php/3D_Model_Guide)

Now something is coming together.

> Reply from finale00
>
> We should probably add something similar to the definitive guide to exploring file formats, for 3D models.
The layout would be similar, in particular listing some common patterns that are usually observed. It would then diverge into different "types" of formats, as I would imagine models for console games would be much different from models for PC games for various reasons.

Though, I'm not sure if people actually check the wiki
## Post #2
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-10T12:54:58+00:00
- Post Title: 3D model reversing compilation

Good idea!
Every 3d formats has some bare minimum things. vertices, primitives such as triangles and tristrips, materials, textures, matrices, bones, etc.

Any ideas how to start though?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T17:23:06+00:00
- Post Title: 3D model reversing compilation

Rather than a tutorial approach, which requires you to know what you're actually talking about, maybe simply a listing of common things to look out for, what they represent, and what kind of clues you might see. Then someone else can add whatever they see fits.

The introduction of any 3D format would probably be a good start, like what a vertex is, what a face is, what materials are, etc.

Common vertex/index storage design.
Maybe some common file structures.

And then later on have some "techniques" on how to figure out the structure of a format.
## Post #4
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-10T17:53:54+00:00
- Post Title: 3D model reversing compilation

I've been into 3d game programming so I could write about how things work internally and what values they can be represented with.

I don't have too much experience on common things to look for, you'll have to write most of that, until others join that is.

EDIT: Here is something for start:

> Please read the Definitive Guide to Exploring File Formats before starting this guide, which is aimed specifically for 3d file formats.
>
> 
>
> No knowledge in 3d is needed, however, any experience in 3d modelling or 3d programming will help. No advance math knowledge is used in 3d formats, though it is in 3d programming, but those are usually hidden inside 3d libraries you use, like your 3d engine or your 3d modeller's scripting language. You should be able to understand what vectors and matrixes are though.
>
> 
>
> We should first understand the basics of how 3d data is represented.
>
> 
>
> The building block of 3d data is the vertex. A vertex is a point in 3d space. So a vertex needs 3 values: x, y and z position. The position values are usually represented as 4 byte floats, though not always.
>
> 
>
> Two vertices (“vertices” is the plural for “vertex”) can connect and form a line.
>
> 
>
> Three vertices can connect and form a triangle. Although more vertices can connect and form more coplex polygons like quads (4 vertices), triangles are the most common. In fact, the GPU needs to break more complex polygons down to triangles before processing them, so 3d formats are likely to always use triangles.
>
> But how are triangles stored in files? Three vertices (3*3 position values)  are enough to create a triangle. But this is not how triangles are always generated from the vertex data in the 3d files.
>
> Triangles can also be represented as what is called a “tristrip”, or triangle strip. In a triangle strip, the first three vertices form a triangle, then every new vertex creates a new triangle by connecting with the previous two.
>
> Tristrips are performance optimization for some GPUs.
>
> 
>
> There are other ways to connect vertices, like linestrips or trifans (short for “triangle fan”, each new vertex after the 1st one creates a new triangle, by connecting with the previous and the very 1st vertex). However these are less common.
>
> 
>
> Some 3d formats will use what is called an “index buffer” (index list), together with the “vertex buffer” (vertex list). Index buffer is basically a list of (usually integer) numbers which tells which vertices connect with each other by their index in the vertex buffer.
>
> 
>
> A collection of triangles or tristrips is called a “Mesh” or “Surface”. Each file you explore will likely have more than one of these.
>
> 
>
> Now we have a basic understanding on how 3d graphics work.
>
> GPU's main job is to process vertices. They are very good at it. It is possible to store and render 3d graphics using other methods, like voxels. But 99.9% of modern GPUs are only good for rendering 3d graphics from the data we described above and most games need the GPU to run, as CPU is too slow for rendering 3d graphics in realtime, polygonal or voxel based.
>
> 
>
> 
>
> We still don't know enough about how 3d data is stored though. We talked about vertices, but we didn't talk about vertex colors, vertex normals, vertex UV maps, materials and other common data which is used in just about every game. We didn't talk much about vertex and index buffers and we also don't know how 3d animations work, what are bones and vertex weights and how they are represented.
>
> 
>
> ...
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T18:49:07+00:00
- Post Title: 3D model reversing compilation

I've never worked with any 3D and the only experience I have is looking at the formats.

You'll probably have a better idea what the data would represent. That would be useful because if I were given a set of values stored in a particular location (eg: when defining the mesh), I wouldn't know what it could be.

So a glossary would be useful.

Anyways

[http://wiki.xentax.com/index.php/3D_Model_Guide](http://wiki.xentax.com/index.php/3D_Model_Guide)
[http://wiki.xentax.com/index.php/3D_Model_Glossary](http://wiki.xentax.com/index.php/3D_Model_Glossary)

The guide would be the tutorial-like page, while the glossary is a list of stuff that engines might use.

The guide itself will be fairly simplistic. I mean, it's not that much different from trying to reverse any other format, and you can only go so far. An explanation of how all the stuff works would eventually take up the majority of the page.

The glossary will be the main focus, cause I can quickly identify a struct, but have no clue what the struct holds.

You can handle the structure of the glossary. Maybe you might group it by concept (mesh, material, animation, etc) or alphabetically (though that might not be as useful).

Some things that I would find useful:

Simple transformations like rotating, scaling, and transforming. How the vectors look and possibly why that is the case (though that is more mathematical so maybe it's not too important)

Bones and stuff. Never played around with 3D editor so never made a model. Not really sure how stuff ties in with one another.

Animation. There are keyframes I guess? That's all I know lol
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T19:27:55+00:00
- Post Title: 3D model reversing compilation

lol 3Dmax costs $3500 for a license!!!   

Noesis it is.
## Post #7
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-10T19:35:20+00:00
- Post Title: 3D model reversing compilation

Blender is kind of cheap if you want.

Also "The role of the GPU" is not necessary. I just wanted to explain that modern GPUs work on vertices, so it is very very unlikely a game will use non-polygonal way of representing models (like voxels).
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T20:00:54+00:00
- Post Title: 3D model reversing compilation

I've tried writing an import script using blender with my Sanae 3D model converter and it sort of worked (I could import and render any model format I had written a plugin for successfully, but I couldn't apply textures), but then I got kind of lazy and just left it there ([viewtopic.php?p=58523#p58523](http://forum.xentax.com/viewtopic.php?p=58523#p58523))

As someone that's probably only interested in reversing a model, I only need tools that do the bare minimum. So for example a model editor is a tool that comes with all sorts of features I don't need and doesn't make it any easier for me.
## Post #9
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-11T08:52:31+00:00
- Post Title: 3D model reversing compilation

I added everything I knew. There's nothing else I can add.

Why is this in the Holy Cow senction? Please repost in the 3D section.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-11T09:20:03+00:00
- Post Title: 3D model reversing compilation

> Reply from gjinka
>
> Why is this in the Holy Cow senction? Please repost in the 3D section.

I moved the topic, and while I was at it, took the liberty of stickying it as well; if anyone disagrees with it being stickied for whatever reason, feel free to tell me. =)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-11T21:52:46+00:00
- Post Title: 3D model reversing compilation

Now all we just need is a main 3D page and an index, and then it's all set up for creating pages for 3D formats and also linking them together.

[http://wiki.xentax.com/index.php/3D_Model_Formats](http://wiki.xentax.com/index.php/3D_Model_Formats)

Maybe someone can add this to the frontpage. It will be the index, with some other stuff at the top.

Also are there any standards for writing formats?
Should there be standards?

Also, in the event that people actually use the wiki to share information about various formats, there probably will need to be some sort of article naming standard.

For example, some game XYZ might have 5 different resource formats (model, sound, images, archive, save game). Some questions would immediately arise

1: should all of the information be grouped together under one article for that particular game? So the article would just be the name of the game.

2: Maybe we should have separate articles for each resource? Maybe something like XYZ_Audio. Mediawiki supports subpaging as well, so maybe we can just create an article called XYZ and then for any resources related to XYZ, we just toss them in a subpage.
## Post #12
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-12T08:05:28+00:00
- Post Title: 3D model reversing compilation

I don't know if creating a new page for only 3d models is a good idea.

And add the links to your first post.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-12T18:40:20+00:00
- Post Title: 3D model reversing compilation

The GFFC's central theme is file formats, and I suppose listing all sorts of information regarding formats for various software.

I treat it like a DB, and would design the pages as such. If a user is wondering which game has 3D model formats available, and there's a page that lists all that information very straightforwardly, it is probably more useful than another page that lists all of the games that have *some* format available, and perhaps indicates which formats are available.

Grouping on resource is reasonable because there are typically only a few resources that make up some software, and typically only a few resources that people actually care about.
## Post #14
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-12T20:20:39+00:00
- Post Title: 3D model reversing compilation

I think most people prefer format specifcations instead of scripts. You aren't expected to know 3 languages to understand the wiki. I understand why you made that page but I think people will think we are encouraging them to post a link to a script instead of writing proper specifications in the appropriate place.

BTW, guys please add some info to the wiki. All I wrote was from my experience of few 3d formats. It's nowhere complete.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-12T20:44:43+00:00
- Post Title: 3D model reversing compilation

Each format page will contain specs, as well as links to existing scripts for those that just want scripts.
Similar to the archive formats.

I'm sure people aren't going to be as excited about writing documentation anyways
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-12T23:31:59+00:00
- Post Title: Re: 3D model reversing compilation

There's no format for the wiki that's set in stone, really, but you can get a good idea of what we're generally going for by looking at some existing pages.

Each format should have its own page - if a game has its own audio, 3D model, and archive format, for example, each of those should be documented on a separate page.

Naming is something I've been struggling with, and I keep coming back to one basic strategy: use the extension the format uses, followed by the name of the game in parentheses (e.g. if the game "Skis on Wiis" had a custom image format that used the extension "swg", the article would be named something like "swg (Skis on Wiis)"). This isn't perfect - there are exceptions that have to be dealt with - but in general, I think it *should* work.
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-12T23:49:27+00:00
- Post Title: Re: 3D model reversing compilation

I like grouping it by game title and following the subpage structure for article names.

ie:

MyGame/Archive
MyGame/Model
MyGame/Sound
MyGame/Image

Of course a single game could have multiple archive formats, or multiple model formats, etc but that could be handled as well.
This makes it easier to link articles together, and especially if subpaging were available, you could just use relative links to refer to each article rather than an absolute link.
## Post #18
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-01-13T16:24:04+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from finale00
>
> lol 3Dmax costs $3500 for a license!!!   

Noesis it is.
Yes, and student licenses are free  I'd say the majority of people that have max tend to have those these days. Since autodesk finally realised that the best way to get people in industry to use max and mostly max is to have it accessible from the ground up.
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-14T23:23:23+00:00
- Post Title: Re: 3D model reversing compilation

Hmm, what are some ways to learn how to do the stuff.

I guess simple ones are

1: familiarizing themselves with the API. Always useful....and one reason why I don't recommend blender for this because it's a little hard to separate the rendering from the parsing. Doesn't matter if I can write a parser for it or not, I simply can't figure out what functions to call to get the stuff into blender properly   

2: writing import scripts for formats that already have existing importers. Some people think that they should only work on formats that haven't been done before and that it's a waste of time to work on something that's already been done. Well we've all probably written a "hello world" program at some point in our lives....

3: expand knowledge about 3D. More you know, better idea of what's going on. I'm lazy so my knowledge of 3D is pretty much at a stand-still.
## Post #20
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-15T08:18:01+00:00
- Post Title: Re: 3D model reversing compilation

I could write a tutorial for Blender, specifically targeted at importers. The API has a lot of functions which are junk to us.
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-15T18:20:41+00:00
- Post Title: Re: 3D model reversing compilation

Tutorial for blender would be great.
I just want to be able to map textures!
## Post #22
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-15T20:27:21+00:00
- Post Title: Re: 3D model reversing compilation

I wondering if we could add it to a wiki. It's a specific tutorial for people writing importers/exporters.

Got something for a start:

> BLENDER PYTHON FOR AN IMPORTER/EXPORTER WRITER
>
> 
>
> This document is meant for Blender importer/exporter writers.
>
> It explains all you need to know: how to create a mesh, add it to an object, add vertices, faces, vertex colors, UVs, normals, create and assign materials and textures to vertex groups, create bones, assign bones to vertices and add bone weights.
>
> 
>
> Blender is a powerful 3d modeller. Blender is a great choice if you want to write an importer/exporter as anyone can use your script because the program  is completely free, unlike very expensive tools like Max and Maya. In fact users of these expensive tools shouldn't complain, because they can just reexport the data from Blender to a format their own program understands, something which Blender users can't do with Max/Maya scripts without paying. And doing that will require only basic understanding of the Blender GUI.
>
> 
>
> However Blender scripts are comparably more difficult to write than Max/Maya scripts, especially if you have no experience in programming. The main reason is Blender uses an actual general-purpose programming language called “Python”. What “general-purpose” means is that the language can be used to write any kind of program, from web applications to video games, unlike MaxScript and MEL, which are only used by and inside these 3d modellers. The good news is Python is a very simple language compared to other general-purpose programming languages like C++.
>
> 
>
> Frankly we don't even need to understand most of Python and most of Blender's Python library to be able to write an importer/exporter.
>
> 
>
> Firstly, you'll need to learn some Python. Make sure you understand “variables”, “functions”, “lists/tuples”, “dictionaries” and have at least some idea of “classes”.
>
> This is a good tutorial: http://www.swaroopch.com/notes/Python
>
> 
>
> Next all is left to do is to learn the needed functions and classes of Blender's Python library (“library” means collection of modules).
>
> A full list is available here:
>
> B2.4:   http://www.blender.org/documentation/249PythonDoc/
>
> B2.5+: http://www.blender.org/documentation/bl ... pi_2_61_2/
>
> 
>
> These are full lists of classes and functions you can use.  You don't need to be a programmer to use a computer, the same way you don't need to know more than 5% of these to create an importer/exporter.
>
> 
>
> As you noticed there are two links, one for Blender 2.4, one for Blender 2.5 and above. The reason is everything was rewritten in Blender 2.5, including the Python library. 2.4 is quickly becoming deprecated, so you should go with Blender 2.5. This tutorial will list the commands for both of them, though.
>
> 
>
> Also note that Blender 2.4 uses Python 2, Blender 2.5 and above use Python 3. These languages are almost the same, but do some things differently. The main differences are:
>
> “print” statement doesn't exist in Python 3, only print() function
>
> “xrange()” doesn't exist in Python 3, “range()” does the same
>
> strings are handled differently
>
> 
>
> For both you will need to import and use the module “struct”. “struct” is a module for converting data read from file to the needed type, like integer, short, long or float.
>
> 
>
> So let's begin. We will start with explaining the functions and classes of Blender 2.5+ which we need, then we will explain the equivalent Blender 2.4  functions and classes in a separate section.
>
> 
>
> Blender 2.5+
>
> 
>
> Creating vertices, edges, faces.
>
> The usual way to create vertices, edges and faces is creating lists of vertex positions, list of edge indexes and list of face indexes and passing them as arguments to the function mesh.from_pydata() . Note that you can pass empty lists for edges and faces if you want.
>
> As you see, from_pydata() is a method (method - function belonging to class) of the Mesh class. So you'll need to make a Mesh object (object - instance of Mesh class first). If these terms (“ method”. “class”, “object”, “instance”) confuse you, then you should probably learn some more on classes in Python.
>
> 
>
> Example:
>
> 
>
> vertices = [[x, y, z], [x, y, z], [x,y,z], [x,y,z]] # replace “x,y,z” with actual numbers
>
> faces = [[0,1,2], [3,4,5], [6,7,8], [9,10,11]] 
>
> 
>
> mesh = bpy.data.meshes.new('name')
>
> mesh.from_pydata(vertices, [], faces) # [] is in place of edges, is an empty list 
>
> 
>
> The first two lines create Python lists. vertices list contains sublists with 3 numbers, which will be used as x,y,z positions for the vertices. faces list is a collection of indexes, which tells how the vertices in the first list will connect and create triangles.
>
> The 3rd line creates a Mesh and third adds vertices and faces to the Mesh from the data we have in our lists.
>
> 
>
> Like anything else in Blender (like Lights, Curves and Armatures), Meshes need to be assigned to “Objects”. Objects are like nodes. Everything in the 3d scene of Blender are Objects. However the Objects can contain different things, one can contain a Mesh, the other a Light. This allows everything in the 3d scene to the treated the same way, like a Light can be moved around the same way as a Mesh.
>
> 
>
> So to actually see your Mesh you'll need to create a new Object, assign the Mesh to it and add (“link”) the Object to the scene:
>
> 
>
> mesh = bpy.data.meshes.new('name') # again
>
> object = bpy.data.objects.new('name', mesh)
>
> bpy.context.scene.objects.link(object) # link object to scene 
>
> 
>
> And you should be able to see your Mesh, unless you used some odd values for your vertices and faces lists (even then you should at least see a dot which is the pivot of the Object.
>
> 
>
> Vertex colors
>
> To assign vertex colors, you will need to create a “VertexColor layer” for you mesh, then loop through your faces and add the colors to all vertices of each face, like this:
>
> 
>
> mesh.vertex_colors.new(name = 'VertexColor')
>
> index = 0
>
> for face in mesh.vertex_colors[0].data:
>
> 	face.color1 = colors[index]
>
> 	face.color2 = colors[index + 1]
>
> 	face.color3 = colors[index + 2]
>
> 	index += 3
>
> 
>
> Where colors is a list of sublists containing RGB colors, like so:
>
> 
>
> colors = [[R,B,G],[R,G,B],[R,G,B]] 
>
> 
>
> Note that colors in Blender are float numbers in the range (0.0, 1.0). if you have an integer in the range (0, 255), just divide your number by 255.
>
> 
>
> TODO
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-15T21:06:13+00:00
- Post Title: Re: 3D model reversing compilation

[http://wiki.xentax.com/index.php/Blender_Import_Guide](http://wiki.xentax.com/index.php/Blender_Import_Guide)

?   

Just choose an appropriate title.
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-19T00:02:24+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from finale00
>
> I like grouping it by game title and following the subpage structure for article names.

ie:

MyGame/Archive
MyGame/Model
MyGame/Sound
MyGame/Image

Of course a single game could have multiple archive formats, or multiple model formats, etc but that could be handled as well.
This makes it easier to link articles together, and especially if subpaging were available, you could just use relative links to refer to each article rather than an absolute link.
Some formats are shared between games, though (this is especially common between different games in a series, or games that use the same engine). The format itself should come first, and the game should be a distant second, used only as needed, when naming and disambiguating format pages.
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-19T05:22:35+00:00
- Post Title: Re: 3D model reversing compilation

Yes, that's always been one of the major criticisms of subpaging schemes; what if multiple articles just happen to share the same content? Do we subpage under this article? or that article? Let's just not bother at all!

Obviously, redundancy is bad, so the last time I was like "how about let's just duplicate stuff" it was shot down quickly.
In the end there was never a resolution to it.

I'll see how I can fit the articles into the ext (game/engine) format.

For disambiguation, ya, it'd be pretty easy to say "did you mean, for this game?"

How about this scenario:
someone creates an article for "mdl" format. Common model extension used in hundreds of games.
Some weeks later, someone else decides to create an article for another game with the same extension.

Would the original "mdl" be renamed to "mdl (game)" in order to be consistent?
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-19T21:07:03+00:00
- Post Title: Re: 3D model reversing compilation

Actually, pages that are just named after extensions are meant to be disambiguation pages for all formats known to use that extension, e.g. [PAK](http://wiki.xentax.com/index.php?title=PAK). Generally speaking, a page dedicated to a single format should never be named with just the extension.

I really didn't word my previous comment as well as I should have. If a format is known to have an "official" name (e.g. if there are published specifications in which it's clearly named, such as BMP, or it's widely known with a certain name, e.g. RAR), that's the name we want to go with, otherwise we just work through the following list until we find one that works: name of engine, name of developer, name of first game known to use the format, name of game we're looking at that uses the format.
## Post #27
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-01-29T16:59:35+00:00
- Post Title: Re: 3D model reversing compilation

OK, I wrote the Blender Import Guide: [http://wiki.xentax.com/index.php/Blender_Import_Guide](http://wiki.xentax.com/index.php/Blender_Import_Guide)
Few things are missing, add them if you can.

@mods: next time you ban someones account because it's listed in bugmenot.com, do us a favor and check that it actually works, will ya!?
Seems like someone likes me...
## Post #28
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-30T04:59:40+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from gjinka2
>
> @mods: next time you ban someones account because it's listed in bugmenot.com, do us a favor and check that it actually works, will ya!?
Seems like someone likes me...

You're gonna have to be more specific than that; are you referring to a block I did on the wiki? Because all of those were bot accounts that posted spamming gibberish on their own userpages.
## Post #29
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-01-30T14:40:31+00:00
- Post Title: Re: 3D model reversing compilation

I mean the forum

[http://www.bugmenot.com/](http://www.bugmenot.com/)
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-30T15:34:11+00:00
- Post Title: Re: 3D model reversing compilation

Good tutorial.
Maybe now I can actually finish writing my blender importer.

Something else I've been wanting to do: put my python 3D converter on google app engine. Since it's written in pure python it would be a great candidate for resource hogging.

And then while I'm at it, figure out HTML5's 3D rendering capabilities and put it there as well.
har har

I didn't know people posted forum accounts on bugmenot. Especially when registration is unrestricted.
## Post #31
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-01-30T19:19:35+00:00
- Post Title: Re: 3D model reversing compilation

Can we have these pages linked from the wiki's main page?

Kinda hard to find the tut unless people see your forum post in this thread.
## Post #32
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-30T21:59:54+00:00
- Post Title: Re: 3D model reversing compilation

I would like a link to the tutorial category somewhere so anyone can access all tutorials quickly.

Then I'd like a spot for 3D stuff under the "Game formats and specifications" section rather than clumping it with just "Game File Formats"
## Post #33
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-30T22:15:02+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from gjinka2
>
> I mean the forum

http://www.bugmenot.com/
Okay, but which account? The only ones bugmenot has listed for the forum are "bm1", "bmn", "bugmenott", and "abcpoker".
## Post #34
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-01-31T07:53:13+00:00
- Post Title: Re: 3D model reversing compilation

> You have been permanently banned from this board.
>
> 
>
> Please contact the Board Administrator for more information.
>
> 
>
> Reason given for ban: Added his account to bugmenot
gjinka
## Post #35
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-31T08:12:08+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from Dinoguy1000
>
> The only ones bugmenot has listed for the forum are "bm1", "bmn", "bugmenott", and "abcpoker".
This is for [forum.xentax.com](http://www.bugmenot.com/view/forum.xentax.com) on bugmenot; [xentax.com](http://www.bugmenot.com/view/xentax.com) is blocked. Do you know if the username "gjinka" was listed under "xentax.com" before "xentax.com" was blocked? If so, I'll just unblock it; otherwise, I'm going to have to find out who actually blocked you and ask them what's going on with it.
## Post #36
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-01-31T10:34:25+00:00
- Post Title: Re: 3D model reversing compilation

Dunno. Maybe. Ive given my login to a friend once, maybe it was a joke.

Anyway, how about linking the 3d stuff from the main wiki page?
## Post #37
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-31T18:46:05+00:00
- Post Title: Re: 3D model reversing compilation

The main page needs a lot of work. One of these days I'm going to have to sit down and rewrite the whole thing, I think, but I keep putting it off. =D
## Post #38
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-31T23:36:49+00:00
- Post Title: Re: 3D model reversing compilation

I can do it if if I'm given the appropriate permissions.
## Post #39
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-02-01T00:23:49+00:00
- Post Title: Re: 3D model reversing compilation

I knocked the protection down to semi (meaning registered users can edit it), so you should be able to work on it now. Now, here's hoping the vandals don't come en masse...
## Post #40
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-01T06:31:12+00:00
- Post Title: Re: 3D model reversing compilation

lol it got trashed within 12 hours.
Well I've made my changes. The security can go back up.
## Post #41
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-02-01T07:43:48+00:00
- Post Title: Re: 3D model reversing compilation

All right, will-do.
## Post #42
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-05T19:42:01+00:00
- Post Title: Re: 3D model reversing compilation

Getting started with model reversing can be an easy or hard task depending on the kind of skills the user already has, how quickly she can learn the tools and ideas, etc.

Well at least for me, although I understood hex pretty quickly and the basics of 3D easily since there are text formats to work with, I imagine a lot of people probably can't get their heads around the hex reading. Asking a couple peers to try to identify a format shows that probably a lot of people will stare at it as a wall of stuff, and then analyze it one byte at a time rather than looking at the big picture and grouping stuff together.

Maybe we should rank formats based on their relative level of difficulty with respect to core 3D concepts.

For example, given the metasequoia 3D format (plain text file), it only defines materials, meshes, and their vertices/faces. That's PROBABLY as minimal as it gets for a usable format that can generate all sorts of cool things. It doesn't even support normals or bones/weights unless you include plugins which then makes it messy.

Shaiya Online model has been used in tutorials, and I'd say it is also fairly basic.

Then you have chunk-based formats which one may argue that they are also simple because you just have to identify that it's chunk-based.

A set of criteria can be developed to help with the ranking.

Any format that contains a bunch of "other" information typically used by the game engine and other things would probably make it a little harder than "basic".

We shouldn't consider things like encryption/compression/other methods to obscure the data, cause that has nothing to do with the actual 3D model.

3D model formats will then be categorized in the wiki under the difficulty levels.
## Post #43
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-09T23:32:54+00:00
- Post Title: Re: 3D model reversing compilation

I've updated the model reverse guide by moving the descriptive explanations to a glossary page.
Logically that should be separated from a guide that's supposed to tell you how to do things and what you're looking for, not understanding the concepts behind it.
## Post #44
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-02-11T13:47:16+00:00
- Post Title: Re: 3D model reversing compilation

Maybe it should be in a separate page, I don't know. I know the Definitive Guide to Exploring File Formats explains some concepts itself, like what bits, bytes, strings, hex numbering, signed and unsigned, bitwise operators, compression and encryption, common archive types and common types of fields like filesize, fileoffset are.
I think because you are not supposed to know all that before starting actually exploring it. Same goes to this guide. You probably know some of these concept, but not necessarily, but even if you do, you might still not know how they are represented in the file (like if you have some experience with bones in 3d modellers, you probably never thought of them as matrices or even know what matrices are).
Actually I think if you know the concepts and you know how they are represented in the file, there isn't much left to learn. Sure, we can explain what tools can be used, but other than that there isn't much. DGTEFF mainly explains concepts itself.

Either way, I see no difference in having the explanations in another page. But I think a section instead of another page would still work.
## Post #45
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T15:43:51+00:00
- Post Title: Re: 3D model reversing compilation

From personal experience, a guide with full working samples that explains what is going on is more useful than theory.
I mean, most people get stuck at reading hex (maybe that's the problem, they are reading it and not just grouping stuff together).

We've all developed techniques that get things done (whether it's disassembling something or just whipping out a calculator), and maybe quickly, and if people know them it should make things a lot easier.

Maybe we should get someone that has some programming ability but no 3D reversing experience and tell them to figure out a simple format using a set of guidelines lol
## Post #46
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2012-09-04T05:54:25+00:00
- Post Title: Re: 3D model reversing compilation

In my case I've found that a lot of mesh data has a similar visual pattern when viewed as an image, particularly as a 8bpp image with an arbitrary color palette (such as viewed in GGD by default)

It's not always an accurate way to tell where things are, but it is a lot easier on the eyes than scanning a bunch of monochromatic text. It gives a fairly good indication of when files are compressed or where certain blocks of data begin and end as well.

Viewing as an image helps to highlight the patterns, and as I work with files, patterns are very important toward figuring out what is what.
## Post #47
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-11-16T15:49:35+00:00
- Post Title: Re: 3D model reversing compilation

Reversing/translating into obj are preferable, it save you a load heck of formats war, just my 2cents.
## Post #48
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2012-12-21T09:52:58+00:00
- Post Title: Re: 3D model reversing compilation

Sorry to pop in here but I must take a stab argument against OBJ. Its a very basic format, which is both its charm and ultimately its greatest flaw. OBJ will not save rigging or skinning which would defeat the purpose of reversing most models as they would be unusable if you wanted to put them back into the game at a later point. I think preservation should be as important as convenience. FBX is a better choice if you want to go the way of a supported format, it keeps rigging, skinning, and has animation support.

There are also a number of other thoroughly documented game formats that are also good intermediaries. ActorX and MD5 for example.

All choices here give a lessened amount of data loss in translation and are convenient alternatives to the lossy OBJ format.

Edit: Sorry again, it is just a pet peeve of mine with people still referencing the archaic OBJ as the best 3D choice. What it can't do turns me off in the grand scheme except in regards to very early 3D, static meshes, or map geometry. Those three are only good reasons I can see for OBJ.
## Post #49
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-01-04T08:49:57+00:00
- Post Title: Re: 3D model reversing compilation

Darkfox, don't worry I agree with you totally. Obj is only good for static meshes because you have to recreate everything as you say. I love fbx but the problem is there are so many versions and it keeps changing so hard to unify it. But hopefully the tools become better and more unified so people will use it as the first choice
## Post #50
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2013-01-08T04:07:51+00:00
- Post Title: Re: 3D model reversing compilation

That is true. I lost track of the revisions on FBX. I guess one can hope a standardized version will be agreed upon. I know there are other formats out there, though.
## Post #51
- Username: vladikkgg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 01, 2011 8:44 pm
- Post datetime: 2014-09-07T20:42:12+00:00
- Post Title: Re: 3D model reversing compilation

Someone,help please with convertation file js to obj. [https://www.whiteclouds.com/sites/defau ... ort.js.txt](https://www.whiteclouds.com/sites/default/files/models/2003__Dodge_Ram_1500_Quad_Cab_Sport.js.txt) this file
## Post #52
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-14T20:49:50+00:00
- Post Title: Re: 3D model reversing compilation

u should have posted in a suiting thread. Here your post seems to have been overlooked.  
o0DemonBoy0o found the basic structure for such models using tris and quads (search for webgl in the forum).

Anyway these webgl-type models are rather useless without uv data:



dodge_webgl.JPG (51.39 KiB) Viewed 681 times
## Post #53
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-09-02T19:35:20+00:00
- Post Title: Re: 3D model reversing compilation

@shakotay2  not helper not good 
more showoff not fuuly help
## Post #54
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2016-12-22T11:45:40+00:00
- Post Title: Re: 3D model reversing compilation

Need extract files from this unity packages in .obj or .fbx formats
If i try Assetsbundleextractor or unityEx - compressed meshes are not supported
UPD: Nobody helped me. Well, i did it by myself.
I used unitystudio 0.5.0.0 for meshes (body and hand weights unfortunately not saved), and unityex 1.5.7 and pvrtextool for textures.
Models scaled up to 60.
[](http://www.imagebam.com/image/df993e522874093) 
DL: [http://rgho.st/6x2Jsvwn7](http://rgho.st/6x2Jsvwn7)
[packages.zip](https://xentaxbackup.github.io/file/12105_packages.zip)
## Post #55
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2017-02-16T18:52:31+00:00
- Post Title: Re: 3D model reversing compilation

Can someone please take a look on this file. I tried hex2obj and unsuccessful. Apparently i am more than n00b. xD
File is from SGW3 which run on CryEngine. It's different from other CGF files from latest CE games. I hope it's not encrypted.

Some data looks fine to me but I can't correctly process them. Only some scrambled shapes.

This is what I got so far  

Shape is ok but faces are messed up.
[muzzle_brakesgw3.zip](https://xentaxbackup.github.io/file/12453_muzzle_brakesgw3.zip)
## Post #56
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-17T04:35:35+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from GRiNDERKILLER
>
> Can someone please take a look on this file.



osv_96_muzzle_brake_01_fp_cgf.png (37.05 KiB) Viewed 190 times


the counts (4bytes) are stored 16 bytes before each start address and the stride (4bytes) is stored right after the count
## Post #57
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2017-02-17T11:52:05+00:00
- Post Title: Re: 3D model reversing compilation

Holly s*hit! I thought you did it as first.
But anyway thank you very much for provided infos. 

EDiT: I think this time I succeeded. Once again thank you Ace!

Maya render.

[rifle.jpg](https://xentaxbackup.github.io/file/12459_rifle.jpg)
## Post #58
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2017-02-17T19:11:37+00:00
- Post Title: Re: 3D model reversing compilation

Just last question AceWell. How to flip UV's verticaly? I mean through hex2obj. 

Thanks!
## Post #59
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-17T23:22:22+00:00
- Post Title: Re: 3D model reversing compilation

you don't, you have to do that in your 3d program of choice
## Post #60
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-21T19:21:57+00:00
- Post Title: Re: 3D model reversing compilation

I need your assistance conditional, I spent a lot of time on this, but I can not find a solution, I can read any file with using hex2obj but their project contains of several thousand, I decided to explore the noesis but I did not get to do one-stop solution for all model files ((
Here I made a template, you can help me fix it to read model with names of the textures.
This file is a container it can contain and textures, but I have learned to extract textures using QuickBMS Script from AceWell


Sample Models: [https://www.dropbox.com/s/qucdzdy26xz7v ... s.zip?dl=0](https://www.dropbox.com/s/qucdzdy26xz7vek/3dModels.zip?dl=0)



```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("TestScriptGame", ".img")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

NOEPY_HEADER = "IMGE"
	
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 8:
      return 0
   if bs.readBytes(8).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    fileName = rapi.getLocalFileName(rapi.getInputName()).rstrip(".img")
    rapi.rpgSetName(fileName)
    bs.seek(0x4, NOESEEK_ABS)
    VBytes = 36            
    VCount = bs.readUInt() // VBytes
    VBuf = bs.readBytes(VCount * VBytes)
    skip = bs.readBytes(8)
    FCount = bs.readUInt() // 2
    IBuf = bs.readBytes(FCount * 2) 
    rapi.rpgBindPositionBufferOfs(VBuf, noesis.RPGEODATA_SHORT, VBytes, 0)   
    rapi.rpgBindUV1BufferOfs(VBuf, noesis.RPGEODATA_SHORT, VBytes, 28)   
    rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_USHORT, FCount, noesis.RPGEO_TRIANGLE, 1) #SHORT for word indices
    mdl = rapi.rpgConstructModel()                                                          
    mdlList.append(mdl)
    rapi.rpgClearBufferBinds()
    return 1
```
## Post #61
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-04T23:53:12+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from blackracer
>
> I decided to explore the noesis but I did not get to do one-stop solution for all model files ((Seems you didn't even get the solution for loading one img file.
in def noepyCheckType(data):
it's
if bs.readBytes(4).decode,
so (4) not (8)

why do you try to get VCount from address 0x0004?
bs.seek(0x4, NOESEEK_ABS)
VBytes = 36            
VCount = bs.readUInt() // VBytes

Your reading the VBuf then IBuf, though IBuf comes first in wheel_rays_te37.img,
your reading short instead of float, you're reading triangles, though you used Strip with hex2obj,
guess you don't know what you're doing with that script, do you?

There's a basic tutorial from chrrox here: [viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760)
Here's your modified script that does import the wheel only, counts set manually:

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("TestScriptGame", ".img")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

NOEPY_HEADER = "IMGE"
   
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 8:
      return 0
   if bs.readBytes(4).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    fileName = rapi.getLocalFileName(rapi.getInputName()).rstrip(".img")
    rapi.rpgSetName(fileName)
    print(fileName)
    bs.seek(0xFE3, NOESEEK_ABS)

    #FCount = bs.readUInt() // 2
    FCount = 513
    IBuf = bs.readBytes(FCount * 2) 

    bs.seek(0x20C0, NOESEEK_ABS)
    VBytes = 36            
    #VCount = bs.readUInt() // VBytes
    VCount = 200
    VBuf = bs.readBytes(VCount * VBytes)
    #skip = bs.readBytes(8)

    rapi.rpgBindPositionBufferOfs(VBuf, noesis.RPGEODATA_FLOAT, VBytes, 0)   
    rapi.rpgBindUV1BufferOfs(VBuf, noesis.RPGEODATA_SHORT, VBytes, 28)   
    rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_USHORT, FCount, noesis.RPGEO_TRIANGLE_STRIP, 1) #SHORT for word indices
    mdl = rapi.rpgConstructModel()                                                          
    mdlList.append(mdl)
    rapi.rpgClearBufferBinds()
    return 1
```


> Here I made a template, you can help me fix it to read model with names of the textures.
Getting textures is the next step. Try to get the models first.
## Post #62
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-05T00:11:57+00:00
- Post Title: Re: 3D model reversing compilation

Yes, I really do not quite understand, thank you very much for the modification of the script in the first place I need to understand the structure of hex.
Next step I will try to read all meshes in this format.
I have been studying this tutorial
## Post #63
- Username: zaphiri
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 22, 2018 9:10 am
- Post datetime: 2018-09-26T20:10:02+00:00
- Post Title: Re: 3D model reversing compilation

Would you convert the ''obj ou 3d'' in ''SKI'' ?
## Post #64
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2018-12-06T09:12:50+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from finale00
>
> 3D model formats index
3D model guide

Now something is coming together.
finale00 wrote:We should probably add something similar to the definitive guide to exploring file formats, for 3D models.
The layout would be similar, in particular listing some common patterns that are usually observed. It would then diverge into different "types" of formats, as I would imagine models for console games would be much different from models for PC games for various reasons.

Though, I'm not sure if people actually check the wiki

HI, finale00
Do you know what software does this? [viewtopic.php?f=16&t=8347](http://forum.xentax.com/viewtopic.php?f=16&t=8347)  I need to get the file in. dat I do not know english. I tried reversing but it was too hard. If you know let me know. Thanks you
## Post #65
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-04-28T13:06:05+00:00
- Post Title: Re: 3D model reversing compilation

Hi, I'm a newbie in parsing 3d model. I'm learning to write my own Noesis script. I have a question:

Based on my knowledge in using shakotay's hex2obj, I know that we have 3 ways to get the vertex count:
- It is defined in the data
- Divide vertex block length by 1-vertex stride length
- Max face index

Unfortunately, the files that I'm working on don't have defined vertex count inside itself but in another file. As far as I know, Noesis scripts must have VCount and FCount. Since I'm a newbie, I just want to work with a single format only. Is there any solution for this case? Thank you    

P/s: Also, regarding to the files that have vertex count defined in them, how can we recognize "vertex count" exactly?
## Post #66
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-27T10:34:18+00:00
- Post Title: Re: 3D model reversing compilation

> Reply from andy97 ↑Sun Apr 28, 2019 9:06 pm at Sun Apr 28, 2019 9:06 pm
>
> I just want to work with a single format only. Is there any solution for this case? Thank youTry to use rapi.loadPairedFile()
.
such like this (untested!):

```
    data = NoeBitStream(xData)
    data.seek(0x08, NOESEEK_REL)# replace 0x08 by real offset
    vCount = data.readInt()  # read vertex count
```
## Post #67
- Username: 3drussiangrabber
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 27, 2020 12:12 am
- Post datetime: 2020-04-01T21:01:25+00:00
- Post Title: Re: 3D model reversing compilation

Can someone please take a look on this file package (three bin files)?
Sourse: monsieurnossDOTcom

Thank's!!!1

[https://dropmefiles.com/kb55G](https://dropmefiles.com/kb55G)
## Post #68
- Username: 3drussiangrabber
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 27, 2020 12:12 am
- Post datetime: 2020-04-23T19:55:39+00:00
- Post Title: Re: 3D model reversing compilation

> {
>
> 
>
> "metadata":
>
> {
>
> "sourceFile": "",
>
> "generatedBy": "Blender 2.65 Exporter",
>
> "formatVersion": 3.1,
>
> "vertices": 6857,
>
> "normals": 6857,
>
> "colors": 0,
>
> "uvs": 0,
>
> "triangles": 7102,
>
> "materials": 1
>
> },
>
> 
>
> "materials": [
>
> {
>
> "DbgIndex" : 0,
>
> "DbgName"  : "02 - Default",
>
> "colorDiffuse"  : [0.0000, 0.4353, 0.0196],
>
> "colorAmbient"  : [0.0000, 0.4353, 0.0196],
>
> "colorSpecular"  : [0.9000, 0.9000, 0.9000],
>
> "transparency"  : 1.0,
>
> "specularCoef"  : 10.0,
>
> "vertexColors" : false
>
> }
>
> 
>
> ],
>
> 
>
> "vertices": [-176.133..............................

Xentax please Help! How to get 3d model from it ???
[https://dropmefiles.com/xp7T0](https://dropmefiles.com/xp7T0)

js JSON ?
how JSON convert to example to OBJ ????
Blender OLD plugin don't work to import JSON, only work SAVE to  JSON (export)
## Post #69
- Username: Beridow
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 03, 2020 6:33 pm
- Post datetime: 2020-11-01T21:03:30+00:00
- Post Title: Re: 3D model reversing compilation

What are you thinking about such technologies [https://www.it-jim.com/blog/tessact-lib ... iguration/](https://www.it-jim.com/blog/tessact-library-configuration/) for example, I would like trying OCR system. I think that it's live up to my expectations because it's a brilliant idea.
## Post #70
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-03-28T11:07:30+00:00
- Post Title: Re: 3D model reversing compilation

I have a question, i wanna find out the right xyz coordinates of the Objects to reconstruct a level, so anyone know where i can find it?
## Post #71
- Username: Ayla658
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 06, 2023 6:04 am
- Post datetime: 2023-09-13T03:45:55+00:00
- Post Title: Re: 3D model reversing compilation

The guide could be divided into two sections: a general section that covers the common patterns found in 3D model files, and a section that covers specific file formats.
## Post #72
- Username: Erupuran
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 20, 2023 11:53 am
- Post datetime: 2023-10-20T04:05:19+00:00
- Post Title: Re: 3D model reversing compilation

I want to view .mdl files in Blender, but I learned on the internet that in order to view .mdl files in Blender, you have to decompile them to .smd with Crowber.
When I try to decompile a .mdl file, an error message appears and I cannot decompile it.
The error message had the words "gold source" in it.
What does this mean?
