## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-07T16:05:36+00:00
- Post Title: Sanae3D - 3D format converter

Downloads: [Mediafire folder](http://www.mediafire.com/?s54wfhm6le23t)

I wrote a simple tool in python that can help people figure out formats (at least, the geometry. No bones. Maybe in the future. I will need some more tools for that, like a simple way to draw the skeleton) I want to try to get pyOpenGL to work though, so that you can just view the model without downloading anything else.

This post will explain how to use it.

It's designed so that you don't have to understand how to write the code to read a file, nor do you need to worry about export functions, though you would need to have basic working knowledge of python syntax.

It's plugin based, so you only need to concern yourself with writing a plugin for the format you're interested in.

It uses command-line for input (since it's designed for batch conversion), though I've used unix-style options cause I'm using a deprecated library lol

Requirements

Python (should be compatible with most versions since I don't use anything special).
And 3.x also, once I fix all of my print statements.

Usage:

Sanae.py [-options] file1 [, file2, file3, ... ]

You might need to type "python" before that if it doesn't work.

Some preparation

1. I have provided a template (binaryParsertemplate.py).

Copy that into a new file and replace all "temp" with a class name of your choice.

2. The definitions function tells the engine how to identify your format. My auto-detection scheme is pretty weak right now so it only checks for the header (I've limited to first 8 bytes for now) and the extension.

The first string is the header
Second string is the extension (without the period)
Third string is just a description (maybe for a help interface later)

3. The read_file function is what the engine will call from the appropriate plugin.

The only thing you have to change is the "temp", but if you did a replace-all earlier then you're fine. It assumes you're reading a binary file, so if you're not you might want to change that to something else.

4. The write_file function is what the engine will call when exporting the object. You don't need to worry about this (and I haven't written anything suitable for it either). 

5. I have a Model3D class that will store the data that make up the 3D object, as well as a bunch of methods that allow you to get info in and out. You should use these methods instead of directly accessing the object, though it doesn't really matter if you're just using this to help figure out formats.

6. StructReader is just a class that implements various struct reading methods so you can say "file.read_float()" or "file.read_long()". It doesn't implement every possible method, but I haven't thought about how I would deal with this.

Writing your plugin

The parse_file method in the class is really all you need. You will need to familiarize yourself with the methods defined in Model3D and StructReader, but once that's done all you need to worry about is the file format.

I'll use chrrox's [shaiya 3DC tutorial](http://forum.xentax.com/viewtopic.php?f=29&t=3739) to demonstrate how you would go about writing the parse_file method.

Here's the format:

```
dword constant00
dword numBones
struct Bone {
	float_16 Matrix4X4 
}
dword numVerts
struct Vert {
	float_3 CoordXYZ
	float Weight
	byte BoneID01
	byte BoneID02
	byte NULL1
	byte NULL2
	float_3 NormalXYZ
	float_2 TexCoordUV
}
dword numFaces
struct Face {
	word_3 FaceIndices123
}

```


You can read it from top to bottom and write the appropriate method calls.

We see that there's no magic word in the header besides a 0, which is probably not very unique, so our definition would be

```
return "", "3DC", "Shaiya 3DC file"
```


0. We note that nowhere does it indicate the mesh names, so you will need to create one yourself.
My data structures require mesh names, so you can just make one at the beginning

```
self.create_object(meshName)

```


1. Now we begin. First is a dword 0, so we can just read it, or skip it using seek.

```
#self.inFile.seek(4, os.SEEK_CUR)

```


2. We then get the number of bones, which is also a dword. You want to store it. Note that all of the value-reading methods use struct.unpack, and that thing returns a tuple, so you will need to get the first value in the tuple.

```

```


3. Next is the bone struct, and the format implies that there are numBones of these (which is why we stored it earlier)
As mentioned, I don't support bones yet, so we don't do anything else with it.

```
	boneStuff = self.inFile.read_float(16)   #read 16 floats

```
 

4. Now we get the number of vertices

```

```


5. and then the vert structure. Just call the appropriate methods based on the format.
Note that I am storing all of this information in my model3D object

```
	vx, vy, vz = self.inFile.read_float(3)
	weight = self.inFile.read_float()
	b1, b2, null1, null2 = self.inFile.read_byte(4)
	nx, ny, nz = self.inFile.read_float(3)
	tu, tv = self.inFile.read_float(2)
	
	#now store them. I don't support bones yet.
	self.create_vertex(meshName, i)
	self.add_coords(meshName, i, [vx, vy, vz])
	self.add_vert_normals(meshName, i, [nx, ny, nz])   #normals stored with vertices
	self.add_vert_uv(meshName, i, [tu, tv])            #uv stored with vertices

```


6. read the number of faces

```

```


7. parse faces, and store them. Note that materials are not specified anywhere.
This is because each model contains only one mesh, and all faces use the same material, so it would
be material index 0. Texture name is the same as the model filename, but I don't care about that here.

```
   v1, v2, v3 = self.inFile.read_short(3)
	 
	 self.create_face(meshName, i)
	 self.add_face_verts(meshName, i, [v1, v2, v3])
	 self.add_face_material(meshName, i, 0)

```


And now you're done. All you have to do is put this module in the plugins folder, then pass a shaiya 3DC object to sanae.
If successful, you will get an MQO file (this is default behavior, I haven't worked on this yet).

Open it with metasequoia (free download: [http://www.metaseq.net/english/](http://www.metaseq.net/english/)) to see the results.
You might have to zoom in cause I don't do any scaling (although the option "--scale n" can scale it by a factor of n...but only for single-mesh models right now)



Everything I've used up there is pretty much all you need for simple formats:

-create the object
-create vertices, and fill them with data
-create faces, and fill them with data

I have included the 3DC plugin with the download for reference, as well as a sample 3DC file.

Downloads: [MF folder](http://www.mediafire.com/?s54wfhm6le23t)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-07T18:20:40+00:00
- Post Title: Sanae3D - 3D format converter

I just found out about the array module, which is apparently faster than struct, but I'm not sure if it makes a difference in this situation cause we're constantly reading different types of values.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T23:58:08+00:00
- Post Title: Sanae3D - 3D format converter

Updated the engine and StructReader class.

StructReader now no longer returns a tuple if you are only unpacking one value (ie: value = read_float(), whereas previously you needed to say value = read_float()[0])

This should be more intuitive and easier to work with, although it does take a performance hit I guess, but this is just an instructional tool so performance is not my concern (it's faster than doing it manually!)

Since plugins no longer rely on hard-coded indices, it should be easier to adjust in the future.

The engine now converts all extensions to uppercase. Of course, I've found that some companies like to use all lower-case or all upper-case, but trying to deal with that is a headache. Plus some companies like to use both, and I don't want to make the definition entries complicated. So just make it uppercase.

[MF folder](http://www.mediafire.com/?s54wfhm6le23t)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-11T15:32:07+00:00
- Post Title: Sanae3D - 3D format converter

Here's a .x txt parser.

I know there are many .x parsers out there, but for instructional purposes I wrote my own.
I've tried to make it flexible cause I've gotten several .x files that have ALL SORTS of coding preferences.

For example, it specifies that a template should be written as

```
   ...

```


But you can place the { wherever you want.

```
{
   ...

```


Apparently you could even add stuff before the brace

```
E {
   ...

```


So I basically build a list of templates available (currently hardcoded, cause there are some things I want to avoid and haven't found a nice solution), and then parse the file.

Whenever I see a template, I add it to a stack. Whenever I run into an open brace, I grab the template that's currently at the top of the stack and then call the appropriate method.

When I see a close brace, the template is done so I can pop it off the stack.
I have to take into consideration nested templates (ie: Mesh --> meshtexturecoords or Frame --> Frame --> Frame) so the stack idea seemed pretty nice.

Though, it still assumes certain patterns about the templates. If a .x file had something like

```
   50;   #vertCount
   MeshNormals {
      ...  #does this even work? It goes against the template definition at the top
   }
   100;  #faceCount
   ...

```


I can't parse it properly because I assume

```
   vertCount
   verts
   FaceCount
   faces

   #YOUR OTHER TEMPLATES. You know, like how its defined properly#

```


Anyways give it a try.
Since it's a text parser it shouldn't rely on anything else, so it should work for older versions of some of my modules.

[moved here](http://forum.xentax.com/viewtopic.php?p=56495#p56495)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-12T01:43:44+00:00
- Post Title: Sanae3D - 3D format converter

Sanae plugin for [Youyou kengeki musou](http://forum.xentax.com/viewtopic.php?f=16&t=6958)

Parses geometry for characters and maps, and assigns materials.

Will require 2011-07-11 version of Sanae as I've changed the Model3D class somewhat.


[kengekiMusou_mdl.7z](https://xentaxbackup.github.io/file/4475_kengekiMusou_mdl.7z)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-14T02:10:26+00:00
- Post Title: Sanae3D - 3D format converter

A: I re-structured the program so that only plugins are in the plugin folder, while stuff like ModelObject and StructReader are in their own "lib" folder.

Since the location of the files are changed you need to update every plugin to import from the correct location.

It will also not be compatible with old plugins...mainly due to the import statement. But ya, that's about it, so any plugins I write from now on will be based on the new structure.

B: Ok so today I threw some more .x files at my parser and it failed (logically).

1: some .x files define all materials first and then refer to them in the material list
2: some .x files define material templates inside the material list
3: some .x files don't have headers

The parser is template-based so it will parse the material templates correctly, but depending on which case you're dealing with the material-assignment will fail.

If material references are used, the mat numbers defined in the material list is local to the list of materials that are used, not the global list of materials. This means that all of them could be pointing to material at index 0, just cause every mesh uses one material. That clearly messes things up.

So ok, I wrote some ugly logic to deal with this (in addition to ugly logic that has to deal with every type of material list definition) and got it working, and then found that version 0302 .x files tend to use mat references while version 0303 define them with the mesh (maybe it is mentioned in the SDK, I don't know. Never read it).

Now, I check the header and set a flag depending on whether it is version 0302 or not.
But then some files DON'T HAVE HEADERS. what? Ok that doesn't even follow the specs, so those files are ignored.

So now I am determining which type of material auto-assignment to use based on version number. Hopefully this holds for all cases (ignoring the ones that don't follow the specs).

I could always parse the template definitions and then figure out what it does...but some files don't even have template definitions! And those are version 0302 as well, so this looks like a good criteria to use.

Since I modified it today, it uses the new file paths, so you will need to download the 07-13 version.
For some reason, if you run it in command line like

```
Sanae.py [...]
```


it doesn't work, but if you put "Python" before that it does. Don't know what the problem is.

C: still trying to figure out how to work with matrix transformations.
D: still no support for frames, bones, animations, etc.
[directx_parser.zip](https://xentaxbackup.github.io/file/4489_directx_parser.zip)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-14T17:53:09+00:00
- Post Title: Sanae3D - 3D format converter

Looked at some more files, and the version number is not a good indicator of how the material references are done.
I changed the logic so that when parsing "template" templates, it will verify that the "Material" template is defined, and then set the matReference flag accordingly.
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-07-20T21:40:13+00:00
- Post Title: Sanae3D - 3D format converter

Your MF folder is set to private
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T15:46:55+00:00
- Post Title: Sanae3D - 3D format converter

Really, the folder is public.. hmm weird maybe there's a global security setting that I missed..

EDIT: ah, it was set to "basic" sharing. I didn't think I had to change that.
Clearly no one is interested (from another forum) since I haven't gotten any messages regarding sharing  
(though I did post direct links, so maybe that's why)
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-28T17:35:49+00:00
- Post Title: Sanae3D - 3D format converter

It occurred to me that metasequoia doesn't show vertices unless it is used by one of the faces.
So I added a small testing function that will create the minimum number of triangles required to use all vertices for each mesh in the model.

You can use it by specifying the "--join" option.
Could be useful if you want to check that the vertices actually represent something.

Just turn off the faces (fc) and enable vertices (pt) to hide my random triangles
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-05T19:24:21+00:00
- Post Title: Sanae3D - 3D format converter

From [viewtopic.php?p=57533#p57533](http://forum.xentax.com/viewtopic.php?p=57533#p57533)

> Reply from youngmark
>
> Is that something that I should solve

I had two *.pyc files(__init__.pyc & UCGundamnOnline_det.pyc) but no mqo_parser.pyc & obj_parser.pyc.

Please forgive my poor English.

It seems like those plugins aren't being compiled for some reason.
I am not too sure why that is. 

Run it in command-line and then post a screenshot of any error messages. If the plugins are failing to load properly then it should throw an error immediately.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-05T19:59:23+00:00
- Post Title: Sanae3D - 3D format converter

To work with normals, I made a choice between two options:

1 - get a model viewer that supports normals and can allow me to draw the object. Several options were available, but they all required some time to figure out how to get it to work. I looked at cgkit for awhile cause it was a very small library and had could load up obj objects and show the coords and normals, but it was kind of hard to work with.

2 - use an existing program with a format that's pretty much figured out. For this, I refer to the first tool that got me into the whole 3D and modding scene: [SB3U](http://www.hongfire.com/forum/showthread.php/112039-SB3Utility-Releases-and-Discussion-%28latest-v0.9.18%29).

It uses the ogre viewer, and the xx model format supports normals and bones amongst other things, so I can use this to look at my results. 

All of the tools involved have command-line interfaces so I just need to pass the files through a batch file.
I wrote up an xx exporter which produces the minimal requirements to get it to load up properly.



This addition will allow me to better verify my results and produce more accurate file formats. Is it quite significant as now I can verify coords, normals, and UV's are correct. Bones can also be done, but skin weights would need another tool.

This one attached is a PMD model. I will probably use a couple formats for reference while implementing some bone functionality, even if that is a rather poor way of doing things.
[sb3u_reimu.JPG](https://xentaxbackup.github.io/file/4583_sb3u_reimu.JPG)
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-08T16:46:45+00:00
- Post Title: Sanae3D - 3D format converter

Recently decided to take a shot at bone-related data, but ended up basing it on the xx format. It supposedly supports 4 bones per vertex, but the struct only stores 3 weights(?)

However, the issue with this approach is that different formats have different ways to storing this information, with possibly different limits for the number of bones and weights allowed per vertex.

This format also limits me to a skeleton structure that is already built, so I don't need to worry about connecting it together myself.

Now the real issues come up: how to build the skeleton? I will need a set of functions to do this.

Looks like just being able to parse bones isn't enough.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-16T15:09:34+00:00
- Post Title: Sanae3D - 3D format converter

Alright, this problem has been stumping me for awhile.

Take a look at the common obj, mqo, or .x formats. They first define coords, normals, and tex coord, and then the faces will index into these lists to pick out which ones they need.

But then there are many formats that define a single vertex with coords, normals, and uv's stored, and then the faces index which vertex to use.

Now the issue is to export the format that indexes normals and uv's separately to a format that stores them with the vertex, while optimizing the number of vertices created.

In the worst case, assuming 3 vertices are used per face, we can simply create numFaces * 3 vertices, which is quite a lot AND may include many duplicates (as indexing each field separately would eliminate all duplicate values).

I can't come up with a way to minimize duplicates.

EDIT: here is the implementation I decided on.

If the normal and UV is stored with the face, I would naturally store it with the Face object.
The bare minimum required for a vertex are the coords, so we have the following information for a single Face

-the list of vertices
-the uv
-the normals

From here, we can build new vertices and then re-map the face indices.
To try to minimize duplicate vertices, I would hash on the vertex number, the vert UV, as well as the normals. This way, if the hash table is written well, I should be able to minimize and eliminate duplicates.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-27T00:19:07+00:00
- Post Title: Sanae3D - 3D format converter

Some updates:

-I've switched from the old getopt library to the (also old) optparse library for parsing options. I like optparse because it is convenient. I might switch to argparse (newer and supported) in the future. Just a fun fact.

-Directory structure has been modified (I finally understand how relative imports work). All plugins import statements must be updated to use relative importing in the next release.

-As a consequence of this change in directory structure, the new structure looks like this:

```
   Sanae3D\
      lib\
      plugins\
      utility\
      engine.py
   sanae.py

```


Basically, the main program is stored in Sanae3D, and you don't have to touch it. The main point of execution is the sanae.py file, which contains 3 lines of code that simply runs the engine. I could change it so the engine is outside, but I'm not too concerned about such minor details at the moment.

-I take the directory of the input file and store it in the engine. This way, when creating the file, I can put it in the same directory as the input. Easier to organize your stuff rather than placing everything in the same folder as the engine.

-Although not common (right now), some plugins might create files of their own. They will have to make sure the files are placed in the proper directory themselves. I can only deal with the output model file since it goes through the engine.

Finally, I am adding a blender export function (or I guess you could say I'm adding a Sanae 3D plugin to blender, up to you).

Thanks to Szkaradek123's blender scripts, I've quickly found the classes and functions that I need and have managed to put something together.

I am starting with adding Sanae 3D plugin to 2.49, since that is the version he uses. Later on I will be adding support for 2.5x (I'm not sure if there are differences between 2.57, 2.58, and 2.59). Well, that will come after I get a working importer for 2.49.

For some reason, relative imports in blender is not the same as it is when I run it outside of blender. I don't know why this is the case.

Things I want to add support for since it should be easy with blender:

-geometry (uv textured)
-bones/weights
-animations (my library doesn't have anything for this yet. I will have to look at animations some more)

I also want to include a Sanae 3D export plugin as well, which would basically take all the data and create a Model3D object, which would then export to whatever I have. Of course, I could just go ahead and write blender scripts directly and skip the whole Sanae 3D thing cause it's just some rough scripts that support the bare minimum in 3D graphics (and not very efficiently as well), but in any case any plugins that are written for sanae 3D is automatically available for blender, so there's no real drawback there.

Currently the textures aren't showing up, as shown below:

[](http://i.imgur.com/FRoBN.jpg)
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-28T17:46:31+00:00
- Post Title: Re: [Tutorial] Sanae - 3D format converter

Alright, with some help from blenderartists.org I managed to get the plugin system working for blender 2.5x as well.

Now that the plugin system can register Sanae3D in both 2.49 and 2.5x, I still have to make some decisions

Do I write separate import functions (for 2.49 and 2.5x), and somehow determine which version of blender the user is using?

I also had to suck it up and change all the import statements to reference "Sanae3D.lib" rather than "..lib" because for some reason I can't get the .. method working. This means it actually depends on the directory structure now, but I don't think I will be changing it anymore.

As of now, all plugins I've written that is loaded through Sanae.py (and not blender) can simply be dropped into the plugins folder in the blender directory and loaded as well, so no need to develop multiple sets of the same script.

For blender 2.49, it is still under development, so if it doesn't load everything that you expect, that's because I didn't do it yet (ie: textures)

It is available in my MF folder if anyone wants to try it out. I've included some updated plugins, though you might not have any samples for them.
## Post #17
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-04-04T09:15:00+00:00
- Post Title: Re: [Tutorial] Sanae - 3D format converter

Let me ask what is this error ??
[Untitled.png](https://xentaxbackup.github.io/file/15996_Untitled.png)
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-04-04T22:20:33+00:00
- Post Title: Re: [Tutorial] Sanae - 3D format converter

Please use forum search:

> Reply from finale00 ↑Wed Apr 23, 2014 3:49 am at Wed Apr 23, 2014 3:49 am
>
> 
It looks like you have an old version of the library. Especially that engine.py thing I don't even remember what that is. And it looks like it's using python2 syntax, so presumably that is the one that I was using when I first started with metaseq conversion.

The latest version just has a single sanae.py file inside the Sanae3D folder and is written to use Noesis API.
## Post #19
- Username: PlsSendHelp
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 13, 2022 12:58 am
- Post datetime: 2023-08-04T18:24:55+00:00
- Post Title: Re: [Tutorial] Sanae - 3D format converter

> Reply from shakotay2 ↑Fri Apr 05, 2019 6:20 am at Fri Apr 05, 2019 6:20 am
>
> 
Please use forum search:
finale00 wrote: ↑Wed Apr 23, 2014 3:49 am
It looks like you have an old version of the library. Especially that engine.py thing I don't even remember what that is. And it looks like it's using python2 syntax, so presumably that is the one that I was using when I first started with metaseq conversion.

The latest version just has a single sanae.py file inside the Sanae3D folder and is written to use Noesis API.
can you reupload the latest version of Sanae3D somewhere please? I tried to find it but i only found the Sanae 2011-08-28 from the original Mediafire link which still had the engine.py file.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-04T19:34:56+00:00
- Post Title: Re: [Tutorial] Sanae - 3D format converter

That's nearly 10 years ago that I had that folder:

> Reply from shakotay2 ↑Wed Apr 23, 2014 12:04 am at Wed Apr 23, 2014 12:04 am
>
> 

Plus I'm not the author of that script. Try here [https://himeworks.com/noesis-plugins/](https://himeworks.com/noesis-plugins/)
The XNALara script for .xps contains class SanaeParser(object)

Maybe you can copy/paste it to use it with other scripts that require Sanae?
