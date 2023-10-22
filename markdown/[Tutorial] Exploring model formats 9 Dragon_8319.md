## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T22:04:52+00:00
- Post Title: [Tutorial] Exploring model formats: 9 Dragon

Using this game for reference: [viewtopic.php?f=16&t=8317](http://forum.xentax.com/viewtopic.php?f=16&t=8317)

Intro

This is not a full tutorial. It doesn't show you step-by-step how each section of the file was discovered.
Most of it was done through simple pattern-searching techniques like looking for specific sequences of bytes that repeated themselves (eg: int, int, float, int, repeat).

The tutorial essentially goes through some basics to exploring a model format without any special tools other than a hex editor. You get an idea of some techniques used to help verify that your assumptions are correct. It then demonstrates some simple noesis functionality.

You should not be following the tutorial as a guide to reversing the 9Dragon model format.
You should be focusing on why I decided to look at a particular value, and how I decided that value makes sense.

Tools

*Noesis
*010 editor, or any hex editor that converts values in real-time.
*calculator, windows calc.exe works fine)
*text editor, for writing notes

Tutorial files attached at the end of the post. Contains the following:

*target model that we want
*its textures
*a bunch of smaller models for comparison.
*a noesis python import script template

This is the target model:



Unless I specifically mention another file, all references to "the file" or "the model" is "obj_kjb_fountain.x3d"
You should assume all numbers are in decimal unless I specifically say it is in hex (I use 0x... notation)
I assume you're familiar with some 3D concepts.
This is a pretty basic format but parsing it might take some time to figure out.

Note that I wrote this after I figured out the format, but the general idea is there.

1. Examining the structure

The first step is to decide whether you want to actually look at the format.
Some things that you should check:

-It's a model format
-It's not compressed or encrypted
-Whether it's little-endian or big-endian
-There's a vertex buffer
-There's an index buffer

If you see vertex and index buffers, then your chances are better because now you don't have to worry about how all the data comes together; it's pretty much given to you. 

If the data makes no sense, then it might be compressed or encrypted. If you don't know much about compression or encryption, best thing is to just upload samples and hope someone will figure it out.

Endian-ness is not too hard to figure out. Usually if you look at integers you'll see the order quickly.

Here, just at the top you quickly see a section that looks like a bunch of floats. Probably a vertex buffer.



Similarly, scrolling down some more past all those floats you see a bunch of 2-byte integers. These are likely going to be the face indices.



2. Drafting an outline

You should start writing down whatever you've found. This makes it easier to identify patterns, allows you to remember what you were looking at (if you choose to stop and re-visit it later), and...well, you have your reference available to share if someone asks for it. How you do it is really up to you.

You might start with something like

```
	 ???
	 vertexbuffer?
	 indexbuffer?
	 ???
}

```


Based on your quick skim through the file.

Examining the vertex buffer

The section of floats that we assumed may be a vertex buffer should be something we check first. I mean, if it's not a vertex buffer, then who knows what it could be.

If you look at the bytes before the section of floats, you should notice an integer (0x20 00 00 00)
Why I think this is an integer? Doesn't matter. You may think that it's just 4 random bytes, but we're not here to argue how bytes should be grouped. It makes more sense to assume that it is an integer and see what you can do with it.



If you examine those 4 bytes, you'll find that it is the number 32.
Ok, so now we can assume that this particular mesh has 32 vertices, and consequently it's followed by 32 vertex structs. So let's update the draft.

```
   ???
	 int32 numVerts?
	 vertexBuffer?
	 indexBuffer?
	 ???
}

```

Examining the index buffer

Since we already know that there's an index buffer, then presumably each index will reference one of the vertices associated with this mesh.

Scrolling past the vertex buffer, you should see the indices again. Now look at where the vertex buffer ends, and you'll find another integer. 



Examining its value, you see that it's 48.
Now, just looking at the indices you should quickly see that they are stored as 2-byte integers.

Assuming this is the index count, highlight 48 indices, which should be 96 bytes.



number of vertices?

When you examine your indices, you should note a couple things
-whether it's 0-based or 1-based
-what the largest value is

By determining this, you have an idea how many vertices there are, and you can use this to verify your previous assumptions.

From this index buffer, you can see that 0x1F00 is the largest value, or 31.
You should see that it is 0-based. This would suggest that the largest vertex number is 32, which should sound familiar.

```
   ???
	 int32 numVerts
	 vertexBuffer?
	 int32 numIdx
	 int16[numIdx] index
	 ???
}

```

Vertex struct?

Now we know where the numVerts is, the numIdx is, and where the index buffer is.
We also know that there is nothing but floats in between the numVerts and numIdx. Assuming it is indeed the vertex buffer, we can hope to calculate the size of each vertex.

Select all of the bytes from just after the numVerts up to right before the numIdx.
You should have selected 1280 bytes.

Logically, each vertex should follow the same pattern, so we can assume each vertex is the same size.
Doing some quick calculations, 1280 / 32 = 40. So our assumption here is that each vertex contains 40 bytes.

```
   40 bytes
}

struct File {
   ???
	 int32 numVerts
	 numVerts Vertex
	 int32 numIdx
	 int16[numIdx] index
	 ???
}

```

Examining the vertex

Assuming each vertex is 40 bytes, you can now look at what those 40 bytes might represent.
You suspect they are floats, so just look at all of them and verify that they are all floats that make sense.

Makes sense means that they should be fairly reasonable numbers. Nothing like 2.843e-30. Remember these are vertices, and so you should have some idea what kind of values you are looking for.

So for example, the first 3 floats have values greater than |1|, so they can't be normals or UV's. This suggests that the first 3 floats are vertex coords. The next 7 floats have values less than |1|, so they could be normals or UV's.

Either way, at least you have an idea where the coords are.

```
   float[3] vx, vy, vz
	 float[7] ???
}

struct File {
   ???
	 int32 numVerts
	 numVerts Vertex
	 int32 numIdx
	 int16[numIdx] index
	 ???
}

```

Testing your assumptions

Up until now, everything is theory. You don't know whether what you've wrote down is actually correct or not.
This is when you use noesis or some other 3D tool.

Noesis makes it convenient because all you have to worry about is parsing the data.
It's also convenient because I've already prepared templates to use, so just copy the template into noesis python plugins folder and edit it in a text editor or some IDE.

Noesis has a "reload plugins" function under the tools menu that makes it easy to reload the plugin if you make changes.

Start by filling in the "registerNoesisTypes" function by replacing "game" and ".ext" with the appropriate values ("9 Dragon" and ".x3d")

Type checking is not too important right now.

Next you want to fill in the "parse_file" method.

We've skipped a bunch of data at the very beginning, and our reference only shows that we know where the numVerts is.
We can hardcode values since we're just testing a single model right now, so look at where the numVerts is and go to that offset.

Now you are pretty much just following the outline you wrote

```
	'''Main parser method'''

	#skip unknown stuff, hardcoded value
	self.inFile.seek(215)
	
	#get numVerts and parse vertex buffer
	numVerts = self.inFile.readUInt()
	self.parse_vertices(numVerts)

```


Now you write the "parse_vertices" method, knowing that each struct is 40 bytes and there are numVerts of them.
You want to bind the vertBuff, knowing that the coords are the first three floats (so at offset 0 of each vertex struct)

```
        
	vertBuff = self.inFile.readBytes(numVerts*40)
	
	#bind the buffer
	rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 40, 0)
	
	#plot the points
	rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, numVerts, noesis.RPGEO_POINTS, 1)

```


And finally, you plot the points to see if it makes any sense.



Hard to tell, but at least it doesn't seem too random.

Maybe we should try getting the faces in.
Following the outline above, you just fill in the indices.

```
	'''Main parser method'''

	self.inFile.seek(215)
	numVerts = self.inFile.readUInt()
	self.parse_vertices(numVerts)
	
	#get indices and parse index buffer
	numIdx = self.inFile.readUInt()
	self.parse_faces(numIdx)

```


And of course, the "parse_faces" function, where you are drawing the faces

```
        
	idxBuff = self.inFile.readBytes(numIdx*2)
	rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)

```


And now you should get this:



Which sort of looks like part of the model we want.

Next steps

At this point, you've already figured out where the vertex and index buffers are.
All you have to do is figure out how to parse the file to 

1: skip data that you don't know
2: get data that you want

It may take some time just to figure out the pattern, but once you get the pattern you should be able to write a parser for it.

Things to look out for:

-strings. How do you determine the length of a string? maybe there's a number that tells you how long a string is?

-start and end of sections. Just like how the numIdx appeared right after the end of the vertex buffer, and how the index buffer appeared right after the numIdx, the rest of the file probably has similar patterns. For example, right after the index buffer, you might see another integer that tells you what the next piece of data will be like.

-patterns. If you do a quick skim through the file, you might find yourself seeing the same types of data again and again. So for this model, you should see vertex buffers and index buffers several times. You can use this to calculate the number of meshes there are, and determine where that number is stored.

Not only should you look at the file in general, but you should also look at specific sections of data for patterns. It doesn't hurt to cut out a section of the data and paste it into another file to look at it more closely.

-compare files. It is often useful to compare different files that are similar to determine whether the patterns hold. If they do, then you're probably right. However, note that the extra files I uploaded are in act a slightly different format, but you should be able to apply the same techniques to figure out their format. Or at least, the numVerts, vertex buffer, numIdx, and index buffer.

You can get more models from the main game thread at the top of the post.

Comments

Obviously, we know nothing about what the data represents initially.
It's not like I disassembled some libraries to examine the algorithm used to parse the file.

You have to think flexibly and search for any patterns.
Some things should be fairly obvious what they are after awhile, while other things you just have to figure out how to skip, and then re-visit when you've isolated them from the rest of the file.
[tutorial.7z](https://xentaxbackup.github.io/file/5080_tutorial.7z)
