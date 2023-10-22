## Post #1
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2012-01-08T20:41:44+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

I'm trying to get the models out of the "Xiaolin Showdown" Xbox game; I think I've found the files that contain the models, but I have no idea how to open them.

Each character is in a different folder, and each has a .msh and a .skl file. I think .msh are meshes, .skl are the bones... There's also .at and .anm. .at files I think are textures, and .anm are animations.

For example there's:
Dojo.msh
Dojo.skl
Dojo_tex0.at
ScriptAnims_Dojo.anm.

I'm just interested in getting the meshes and textures; I've looked into the formats but other games that use them don't seem to support the Xiaolin format.

I think the PS2 version has different formats, but I've not even managed to open the archives. On the Xbox disc there's also .chr files; I know these can be opened with 3DS Max, but when I try they're apparently unreadable, so I'm not sure if they're any use to me.

Anyone know of anything that could help me out? I could upload a file if anyone's willing to look at it.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T21:48:39+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

Upload the files anyways. Someone might be interested and want to look at it a couple months later but you might be long gone by then.
## Post #3
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2012-01-08T21:55:05+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T22:43:59+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

Should probably post a couple more, to compare different files.

Meshes located in msh
Uses a chunk-based format (chunk, chunkSize, data)

FORM, MESH, INFO, TVX0, MAT1, TEX1, SKN2, VTX1, SVX0, PAD0.
I don't see any index buffers, and SKN2 is the largest section.

textures are those .at files, but I don't know graphic formats although it looks simple.

The mesh and skeleton file references some path: "P:\Xiaolin\Artwork\Characters\SkinFiles\Dojo\Dojo.mb"
I don't know if that is the archive that you extracted these files from or not.
## Post #5
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2012-01-08T22:57:06+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-01-10T20:37:44+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

In the last set of files you uploaded the Reptile.msh contains the mesh, it appears they ported the xbox version from the PS2 version as it look fairly similar to PS2 games (many PS2 games have models that have similar structure because the/a PS2 development kit can make tristrip meshes that use VIF headers). As for the reference to P:Xiaolin\....Reptile.mb  this is the original model that was made in the 3d design program called Maya. mb is the Maya binary format. I have seen this is some other games too, that created the models in Maya.
Here is the rough format of the SKN2 section:
SKN2 which in hex is (53 4B 4E 32)
4ByteIntegerSizeofSection which in this file is 88 8f 02 00 or 28f88 in length
4ByteIntegerNumberOfSubMeshes (which in this case is 94 00 00 00 or 0x94 or 148 submeshes)

Rough format of each Submesh (Reptile.msh has 148 submeshes, though some games might never explicitly say how many because they only have a stop mesh header, this game does say the number see above) the SKN2 section:
....... (Some headers I do not know the format of)
00 80 XX 68 (XX is the number of vertexes in a given submesh)
4ByteFloatingPointVertexes(X,Y,Z)
00 80 XX 68 (This repeat header is not a typo)
4ByteFloatingPointNormalMappings (tells how to reflect light off of the mesh)
00 80 XX 64
4ByteFloatingPointTextureUVMappings(U,V) (Tells how to put textures on each mesh)
00 C0 XX 6E
Uncertain But Probably Color Tints 1ByteColorMappings(Red,Green,Blue)+FF
00 C0 XX 6C
Uncertain but is 4ByteFloatMappings(#1,#2,#3,#4)
00 00 00 14
End of submesh
Here is a picture of Reptile (Chase_Reptile) probably chase in reptile form)


Here is the mesh but only plain vertexes not UV/Normals or anything else
[http://ps23dformat.wikispaces.com/file/ ... tile.blend](http://ps23dformat.wikispaces.com/file/view/ssreptile.blend)
you can use the free program blender to open it up.
I converted the mesh by finding the headerstrings and keeping just the vertexes, I used microsoft word but a good hex editor program could also do it. I then pasted the vertexes in a file that had the tristrip vertex index all ready setup, so I just pasted the vertexes in using the program cheat engine as a hex editor.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T20:43:05+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

lol I looked at the extraction guide on that wiki and I'm amazed people can do all that with Word.

Which page has the index information that a lot of these PS2 formats use?
I don't see any index buffers in the file so I'm guessing the file only needs to store the vertex info and then just use some other algorithm to draw them.
## Post #8
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2012-01-10T21:42:39+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

> Reply from FurryFan
>
> In the last set of files you uploaded the Reptile.msh contains the mesh, it appears they ported the xbox version from the PS2 version as it look fairly similar to PS2 games (many PS2 games have models that have similar structure because the/a PS2 development kit can make tristrip meshes that use VIF headers). As for the reference to P:Xiaolin\....Reptile.mb  this is the original model that was made in the 3d design program called Maya. mb is the Maya binary format. I have seen this is some other games too, that created the models in Maya.
Here is the rough format of the SKN2 section:
SKN2 which in hex is (53 4B 4E 32)
4ByteIntegerSizeofSection which in this file is 88 8f 02 00 or 28f88 in length
4ByteIntegerNumberOfSubMeshes (which in this case is 94 00 00 00 or 0x94 or 148 submeshes)

Rough format of each Submesh (Reptile.msh has 148 submeshes, though some games might never explicitly say how many because they only have a stop mesh header, this game does say the number see above) the SKN2 section:
....... (Some headers I do not know the format of)
00 80 XX 68 (XX is the number of vertexes in a given submesh)
4ByteFloatingPointVertexes(X,Y,Z)
00 80 XX 68 (This repeat header is not a typo)
4ByteFloatingPointNormalMappings (tells how to reflect light off of the mesh)
00 80 XX 64
4ByteFloatingPointTextureUVMappings(U,V) (Tells how to put textures on each mesh)
00 C0 XX 6E
Uncertain But Probably Color Tints 1ByteColorMappings(Red,Green,Blue)+FF
00 C0 XX 6C
Uncertain but is 4ByteFloatMappings(#1,#2,#3,#4)
00 00 00 14
End of submesh

I thought it was a port from PS2, a lot of the files are the same, but I couldn't open the archives of the PS2 version. I think textures in the PS2 version is .tga format rather than .at, not sure though.

The P:\Xiaolin\... paths seem to be common in characters that were created in Maya, or so I've seen... The Crash Tag Team Racing models also had a path to their original models, and they were created in Maya.

That's amazing, how you figure this stuff out is beyond me. The way you extracted Reptile.msh, do the other .msh files follow the same extraction format? I'm assuming they do.
## Post #9
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-01-11T00:17:44+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

I forgot to mention, the Faces are formed by implicit Tristrips:
What you do is connect each vertex in a submesh to the next two vertexes in a row:
So if a submesh contains 5 vertexes this would be the index:
00,01,02
01,02,03
02,03,04

If a submesh contains 7 vertexes this would be the index:
00,01,02
01,02,03
02,03,04
03,04,05
04,05,06

What I do is just have one long string and then between submeshes I just put a vertex of all 00 zero's, and then in blender delete the vertexes at 0,0,0 and it would do the samething.
## Post #10
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2012-01-11T06:51:21+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

Is there any way for me to be able to extract all the characters like you did?
## Post #11
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-01-11T18:33:16+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

Yes, I'll write up exactly how I did it. The steps will be similar to this (but different) to give you an idea of what it involves:
[http://ps23dformat.wikispaces.com/file/ ... action.txt](http://ps23dformat.wikispaces.com/file/view/CTTRModelExtraction.txt)
## Post #12
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2012-01-11T19:16:21+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

Ah that's good... I extracted the models from CTTR using your guide a while ago, so hopefully it won't be that hard... Thanks!
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-11T22:16:13+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

> Reply from FurryFan
>
> I forgot to mention, the Faces are formed by implicit Tristrips:
What I do is just have one long string and then between submeshes I just put a vertex of all 00 zero's, and then in blender delete the vertexes at 0,0,0 and it would do the samething.

In the image up there seems to have some odd lines here and there. 
Is this just a blender thing?
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-12T03:05:58+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

> Reply from finale00
>
> FurryFan wrote:I forgot to mention, the Faces are formed by implicit Tristrips:
What I do is just have one long string and then between submeshes I just put a vertex of all 00 zero's, and then in blender delete the vertexes at 0,0,0 and it would do the samething.

In the image up there seems to have some odd lines here and there. 
Is this just a blender thing?

Its triangles (faces) with only 2 sides x and y. error in extraction.
## Post #15
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-01-15T23:03:58+00:00
- Post Title: [XBOX] Xiaolin Showdown .msh .skl .at Files

Here are the steps to convert the .msh files from the xbox version:
[http://ps23dformat.wikispaces.com/file/ ... action.txt](http://ps23dformat.wikispaces.com/file/view/xiaolinshowdownXboxModelExtraction.txt)
## Post #16
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2012-01-15T23:57:00+00:00
- Post Title: Re: [XBOX] Xiaolin Showdown .msh .skl .at Files

> Reply from FurryFan
>
> Here are the steps to convert the .msh files from the xbox version:
http://ps23dformat.wikispaces.com/file/ ... action.txt

Thank you so much! This means a lot!
## Post #17
- Username: rslifemanu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 23, 2012 11:35 am
- Post datetime: 2012-02-23T09:12:34+00:00
- Post Title: Re: [XBOX] Xiaolin Showdown .msh .skl .at Files

There's a couple of different characters in that one.
