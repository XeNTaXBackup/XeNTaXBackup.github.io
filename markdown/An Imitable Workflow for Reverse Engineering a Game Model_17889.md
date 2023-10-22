## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T02:44:39+00:00
- Post Title: An Imitable Workflow for Reverse Engineering a Game Model

Preface
From what I've seen and heard so far, there're still some people who truely want to learn some skills and help themselves, maybe even others. That's why I'm making this tutorial.
Content
Manual Researching Section
Background Knowledge before Starting
Introduction on Hex2Obj
Analyzing and Extracting a Game Model
Analyzing and Reverse Engineering a Game Archive

Programming Section
Basic BMS Scripting
Learning C
Writing an Obj Convertor in C
Summary
Summary of the workflow
Extended Content
AMR - an Alternative for Mesh Format Research
Advanced Mesh Reaper - Xtreme Edition (AXE)
A Demonstration on Using AXE


If you're completely new to this area, read the above topics in order. If there'd be any questions, comment under the corresponding topic.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T02:47:53+00:00
- Post Title: An Imitable Workflow for Reverse Engineering a Game Model

Part I. Background Knowledge before Starting
Common Data Types
Before you start exploring file formats, you need to understand the following definitions of data types:

byte/char:					unsigned/signed 8 bit interger, the smallest unit of a computer's memory
word/short:  					unsigned/signed 16 bit interger which takes a 2-byte unit
dword/int:					unsigned/signed 32 bit interger which takes a 4-byte unit
ULONG32/long:					unsigned/signed 32 bit interger which takes a 4-byte unit
ULONG64/long long: 			unsigned/signed 64 bit interger which takes an 8-byte unit


float: 							a 4-byte unit used to represent floating point numbers like 3.141593, etc.
double:						an 8-byte unit used to represent more precise floating point numbers like 3.141592653589793
string/char []:				an array/sequence of characters(char) terminated with a null/zero byte

If you don't understand the above definitions, read the introduction in The Definitive Guide to Exploring File Formats, or ask google for help, and come back later.
BTW, you could read the explanation about endianess in advance, still I'll explain it when necessary.

Link: DGTEFF: Terms, Definitions, and Data Structures

Basic Concepts about Simple Models
A simple game model is consisted of the least amount of elements: vertices and face indices, where vertices are composed of the following attributes:
vertex positions,
vertex normal vectors, and
vertex texture coordinates (UVs);

while face indices can be encoded as:
triangle list, or 
triangle strips.

Read the 3D Model Glossary to gain an understanding of these concepts. You don't have to learn all the terms it mentioned at present.
Link: 3D Model Glossary

Return to the main tutorial.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T02:55:23+00:00
- Post Title: An Imitable Workflow for Reverse Engineering a Game Model

Part II. Introduction on Hex2Obj

In this part, I'll briefly explain how [Hex2Obj](http://forum.xentax.com/viewtopic.php?f=29&t=10894) works. You only need to have an overview of the entire process. I'll explain how to use it later.

Main UI (v0.24c):


litE/bigE: Switch of endianness, little endian by default.
Word/DW: Data type of the face indices. Most games use Word/Short for storage of the indices, which can represent up to 65,535 verts. 
When a model contains more than that amount of vertices, it'll need larger 4-byte integer to define the indicies, and that's what we call a Dword (DW).
seq/VB: Two modes for how you want the tool to parse the vertex data. In most of the cases you'll be using the latter.
noStr/Strip: How the vertices are connected: triangles/triangle strips.
std/FFFF: How the tristrips are terminated.
noPtC/PtCld: Whether to display the model as a point cloud or not.
go1: When pressed it displays the indices of the vertices in each face in the lower left window and show the calculated vertex count.
go2: When pressed it displays the values of the UV coordinates.
go3: When pressed it displays the values of the vertex position coordinates, but it's only accessable in seq mode.
mesh: To display the model in the mesh viewer.
UVs: To display the UVs as a flatten mesh.
Data Type Rollout ("Float"): Offering different data types used to define the vertices.

So basically you've known what is needed for building a simple 3D model after you finished your preparation work in [Part I](https://forum.xentax.com/viewtopic.php?p=138999#p138999): vertices coordinates, vertex normals, vertex UVs and face indices.

The necessary info we need to build the model via Hex2Obj includes: the start offset and the count of the vertices, the ones of the face indices, 
and the offset of the UVs, so that Hex2Obj can access to the corresponding data appropriately. That's not hard to understand though.

However the file endianness and varied data types being used will result in different combinations of parameters for correctly using the tool. That's what makes most newbies feel it so hard.

To get the tool work, we just need to fill in all the required info and choose the coresponding parameters.

[Return to the main tutorial.](https://forum.xentax.com/viewtopic.php?p=138998#p138998)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T02:57:41+00:00
- Post Title: An Imitable Workflow for Reverse Engineering a Game Model

Part II. Learning C

It's never a bad idea to teach yourself a real programming language, especially if you don't want to extract all models via Hex2Obj manually.
And C seems to be a good option. It's efficient, and easy to learn. 

There're already a lot of online tutorials available on the Internet, so I won't explore the details here.

[Return to the main tutorial.](https://forum.xentax.com/viewtopic.php?p=138998#p138998)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:59:30+00:00
- Post Title: An Imitable Workflow for Reverse Engineering a Game Model

Summary

So it's time to summarize the entire workflow:
1. Manually research the game archives, gather necessary info for unpacking;
2. Write a BMS script for assets extraction;
3. Analyze the model format with Hex2Obj;
4. Write a model extractor in C.

For compressed data there're also some tips:
1. See if you can recognize the compression;
2. Use Comtype Scanner on the compressed data;
3. If the above methods still don't work, go ask people for help;
4. If it's still too dificult to solve, you might have to leave it alone for now.

Refferences: 
[How to recognize the compression algorithms with your eyes](http://zenhax.com/viewtopic.php?f=4&t=27)
[QuickBMS - Scan all the supported compressions](http://zenhax.com/viewtopic.php?f=4&t=23&hilit=QuickBMS+comtype+scanner+2)

[Return to the main tutorial.](https://forum.xentax.com/viewtopic.php?p=138998#p138998)
