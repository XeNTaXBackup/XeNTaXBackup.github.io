## Post #1
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T02:03:15+00:00
- Post Title: [Request]Hob game MDL converter

Hello,

I need your help with MDL 3models in the [Hob](http://www.runicgames.com/hob/) game. Solving this problem would give us ([Torchmodders.com](http://torchmodders.com/forums/index.php) and all community modders of Torchlight) new opportunities to create mods for the Torchlight/Torchlight2 games.

Firstly, if you want to unpack the Hob-archive you need this: [Hob's Pak Extractor](http://www.runicgamesfansite.com/mod_downloads/tools/download-1521-hobs-pak-extractor.html)

Secondly, all "Runic Games" games are made on the OGRE engine, so you will need some tools: [OgreXMLConverters + Ogre Meshy viewer](https://yadi.sk/d/rcyZhyqM3W6ajn)

Problem description and tasks:
1. Previously, all "RG" games used 3models in Mesh format, but this Hob game uses a new MDL-format. As I found out, it's the same format, but slightly modified. These minor modifications do not allow us to use standard OGRE utilities.

a) I opened these Hob MDL files with Hex editor and found 2 types of files:



I do not know the difference, but it made me think that these are ordinary OGRE files. But when I tried to find this MeshSerializer_v1.9, I discovered that it does not exist. I found only 1.41, 1.8 and 1.10(see tools above). OgreSDK 1.9  contains 1.8 MeshSerializer.

b) I tried to rename these files MDL->MESH and tried to open in Ogre Meshy viewer but failed. OGRE does not understand this MeshSerializer.

c) Using the Hex editor, I changed this MeshSerializer_v1.9_o -> MeshSerializer_v1.100



After that you can open it in Ogre Meshy and convert this Mesh into a xml-file using OgreXMLConverters1.100(MeshSerializer_v1.100). Now using this xml-file you can convert the model to any MeshSerializer version.(Torchlight2 required 1.41). 




Also, as I understood, the MDL file contains information about the material (maybe this is the cause of the main problem). But for convertible models it does not matter. OgreXMLConverter just ignores this and after the reconversion this information is lost.



Meanwhile. Hooray, it works I thought but...

d) Later I discovered that this simple method works only for a couple of models. For 99% of models this does not work.   Examples of models in this archive: [HOB_MODELS](https://yadi.sk/d/EtYKO1O53W6iiv) I divided them into convertible and non-convertible.
Also I added TLMeshViewer_v0.8.2.0 - utility to view models from the Torchlight games.

e) I'm looking for a way how to get the compatible MESH models. Any help is appreciated.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-18T08:49:08+00:00
- Post Title: [Request]Hob game MDL converter

The problem might be the difference in vertex block lengths.

The non-convertible models have 88 bytes vertex blocks. Here is batrabbit for example.



While the convertible ones have 32 bytes vertex blocks.



So this might be the reason why the model viewer fails. If you have the model viewer source, this should be an easy fix. Still I don't know the Ogre format at all, so it might very well be something else.

I would suggest you to try and find out the differences between convertible and non-convertible ones. Vertex block lenghts is the first thing I noticed, there might be other differences too.
## Post #3
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T09:22:23+00:00
- Post Title: [Request]Hob game MDL converter

> Reply from akderebur
>
> The problem might be the difference in vertex block lengths.

The non-convertible models have 88 bytes vertex blocks. Here is batrabbit for example.
Oh, this is a great start. Thank you. Now we are one step closer to the final goal. Now I see that there are more differences than I thought.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-18T09:24:11+00:00
- Post Title: [Request]Hob game MDL converter

here is a model from nonconvertible_v1.9_o with FVF size of 32:
what exactly does happen (text of error message for example?) when you change the MeshSerializer_v1.9_o -> MeshSerializer_v1.100 for C_Frogbeast.mdl and try to load it into Qgre Meshy?

The mesh format itself looks simple:



C_Frogbeast.jpg (197.43 KiB) Viewed 264 times


well, see, akderebur was quicker...
## Post #5
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T09:35:19+00:00
- Post Title: [Request]Hob game MDL converter

> Reply from shakotay2
>
> when you change the MeshSerializer_v1.9_o -> MeshSerializer_v1.100 for C_Frogbeast.mdl and try to load it into Qgre Meshy?
Well, nothing happens. 

LOG:
Creating resource group InternalPermanentMeshGroup
Added resource location 'Resources/Models' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/Fonts' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib/GLSL' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib/GLSLES' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib/HLSL' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib/Cg' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Initialising resource group InternalPermanentMeshGroup
Parsing scripts for resource group InternalPermanentMeshGroup
Parsing script Axis.material
Parsing script BoneMesh.material
Parsing script Grid.material
Finished parsing scripts for resource group InternalPermanentMeshGroup
Creating resources for group InternalPermanentMeshGroup
All done
Creating resource group ShaderGeneratorResourceGroup
Added resource location 'C:/Users/****/AppData/Roaming/OgreMeshy/RTShaderCache/' of type 'FileSystem' to resource group 'ShaderGeneratorResourceGroup'
Creating resource group InternalMeshGroup
Destroying resource group InternalMeshGroup
Unloading resource group InternalMeshGroup
Finished unloading resource group InternalMeshGroup
Creating resource group InternalMeshGroup
Added resource location 'F:\HOB\Xentax\MODELS\nonconvertible_v1.9_o\C_FROGBEAST' of type 'FileSystem' to resource group 'InternalMeshGroup'
Parsing scripts for resource group Autodetect
Finished parsing scripts for resource group Autodetect
Creating resources for group Autodetect
All done
Parsing scripts for resource group General
Finished parsing scripts for resource group General
Creating resources for group General
All done
Parsing scripts for resource group Internal
Finished parsing scripts for resource group Internal
Creating resources for group Internal
All done
Parsing scripts for resource group InternalMeshGroup
Finished parsing scripts for resource group InternalMeshGroup
Creating resources for group InternalMeshGroup
All done
Parsing scripts for resource group ShaderGeneratorResourceGroup
Finished parsing scripts for resource group ShaderGeneratorResourceGroup
Creating resources for group ShaderGeneratorResourceGroup
All done
Mesh: Loading C_FROGBEAST.MESH.
Texture: Grid.png: Loading 1 faces(PF_A8R8G8B8,32x32x1) Internal format is PF_A8R8G8B8,32x32x1.

And LOG for the convertible model C_BIRD:

Creating resource group InternalPermanentMeshGroup
Added resource location 'Resources/Models' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/Fonts' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib/GLSL' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib/GLSLES' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib/HLSL' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Added resource location 'Resources/RTShaderLib/Cg' of type 'FileSystem' to resource group 'InternalPermanentMeshGroup'
Initialising resource group InternalPermanentMeshGroup
Parsing scripts for resource group InternalPermanentMeshGroup
Parsing script Axis.material
Parsing script BoneMesh.material
Parsing script Grid.material
Finished parsing scripts for resource group InternalPermanentMeshGroup
Creating resources for group InternalPermanentMeshGroup
All done
Creating resource group ShaderGeneratorResourceGroup
Added resource location 'C:/Users/****/AppData/Roaming/OgreMeshy/RTShaderCache/' of type 'FileSystem' to resource group 'ShaderGeneratorResourceGroup'
Creating resource group InternalMeshGroup
Destroying resource group InternalMeshGroup
Unloading resource group InternalMeshGroup
Finished unloading resource group InternalMeshGroup
Creating resource group InternalMeshGroup
Added resource location 'F:\HOB\Xentax\MODELS\convertible\C_BIRD' of type 'FileSystem' to resource group 'InternalMeshGroup'
Parsing scripts for resource group Autodetect
Finished parsing scripts for resource group Autodetect
Creating resources for group Autodetect
All done
Parsing scripts for resource group General
Finished parsing scripts for resource group General
Creating resources for group General
All done
Parsing scripts for resource group Internal
Finished parsing scripts for resource group Internal
Creating resources for group Internal
All done
Parsing scripts for resource group InternalMeshGroup
Finished parsing scripts for resource group InternalMeshGroup
Creating resources for group InternalMeshGroup
All done
Parsing scripts for resource group ShaderGeneratorResourceGroup
Finished parsing scripts for resource group ShaderGeneratorResourceGroup
Creating resources for group ShaderGeneratorResourceGroup
All done
Mesh: Loading C_BIRD_v1.100_Original.MESH.
Skeleton: Loading MEDIA/CHARACTERS/C_BIRD/C_BIRD.skeleton
OGRE EXCEPTION(6:FileNotFoundException): Cannot locate resource MEDIA/CHARACTERS/C_BIRD/C_BIRD.skeleton in resource group InternalMeshGroup or any other group. in ResourceGroupManager::openResource at G:/SDK/OgreLatest/OgreMain/src/OgreResourceGroupManager.cpp (line 757)
Unable to load skeleton MEDIA/CHARACTERS/C_BIRD/C_BIRD.skeleton for Mesh C_BIRD_v1.100_Original.MESH. This Mesh will not be animated. You can ignore this message if you are using an offline tool.
Can't assign material c_bird_mat_DELETEME to SubEntity of MeshEntity because this Material does not exist. Have you forgotten to define it in a .material script?
Texture: Grid.png: Loading 1 faces(PF_A8R8G8B8,32x32x1) Internal format is PF_A8R8G8B8,32x32x1.
## Post #6
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T10:21:05+00:00
- Post Title: [Request]Hob game MDL converter

Maybe for MeshSerializer_v1.9_o models we can find out why they are not converted?
Can we parse the structure of binary files and find the differences?
All files have a clear structure.
[Hex4.jpg](https://xentaxbackup.github.io/file/14373_Hex4.jpg)
## Post #7
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T11:19:11+00:00
- Post Title: [Request]Hob game MDL converter

Ok, it looks like I've found a way to beat these "nonconvertible_v1.9_o" models.
1. I copied the beginning from another model C_BIRD_v1.100_Reconverted.MESH
from start to vertex count
2. Deleted the beginning in "nonconvertible_v1.9_o" C_FROGBEAST.MESH
from start to vertex count
3. Paste the beginning of one file to another. 
Ta-da! Now this is being converted.
## Post #8
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T11:36:51+00:00
- Post Title: [Request]Hob game MDL converter

The second  "nonconvertible_v1.9_o" model from example.



It looks like this method works.  

now we need to beat the "nonconvertible_v1.9" files! Any ideas?
## Post #9
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T12:15:52+00:00
- Post Title: [Request]Hob game MDL converter

Another model for the test. This "copy-paste" method works fine for "nonconvertible_v1.9_o" models.
## Post #10
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T12:27:55+00:00
- Post Title: [Request]Hob game MDL converter

> Reply from akderebur
>
> The problem might be the difference in vertex block lengths.

The non-convertible models have 88 bytes vertex blocks. Here is batrabbit for example.
Ok, I have a question. Can we convert these 88 bytes blocks into 32 bytes blocks? In theory?
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-18T12:28:14+00:00
- Post Title: [Request]Hob game MDL converter

I will take a wild guess here. I think only "1.9_o" works because it has the same length as "1.100", 5 bytes each. So when you change "1.9" to "1.100" you are swifting all the positions by 2 bytes. 

Like I said I don't know how this format works, but it seemed like a possibility to me. Try deleting 2 bytes from some part that isn't necessary to see if it will make a difference.
## Post #12
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T12:30:44+00:00
- Post Title: [Request]Hob game MDL converter

> Reply from akderebur
>
> Try deleting 2 bytes from some part that isn't necessary to see if it will make a difference.
I've tried this before. This does not work. This "material" part, we can cut it as we wish.
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-18T12:31:46+00:00
- Post Title: [Request]Hob game MDL converter

> Reply from Kva3imoda
>
> 
Ok, I have a question. Can we convert these 88 bytes blocks into 32 bytes blocks? In theory?
It is possible to write a script/program that takes the first 32 bytes of each block and deletes the rest, if that is what you mean by converting.
## Post #14
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T12:35:49+00:00
- Post Title: [Request]Hob game MDL converter

> Reply from akderebur
>
> It is possible to write a script/program that takes the first 32 bytes of each block and deletes the rest
These 56 bytes are empty? The necessary information will be preserved? 
It might work.
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-18T13:03:05+00:00
- Post Title: [Request]Hob game MDL converter

> Reply from Kva3imoda
>
> 
These 56 bytes are empty? The necessary information will be preserved? 
It might work.
They are not empty, so you might lose some data, but it is also possible that the data in those bytes are not necessary for ogre tools or torchlight. I can't say anything for sure since I don't know what those bytes represent.

Anyway here is the batrabbit model with 32 bytes blocks. You can give it a try  at least.


 batrab.rar
(39.57 KiB) Downloaded 18 times
## Post #16
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T13:12:54+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from akderebur
>
> They are not empty, so you might lose some data, but it is also possible that the data in those bytes are not necessary for ogre tools or torchlight. I can't say anything for sure since I don't know what those bytes represent.

Anyway here is the batrabbit model with 32 bytes blocks. You can give it a try  at least.
Thanks akderebur. I tried this. The "Copy-Paste" metod does not work for this. It is sad.
[Error1.jpg](https://xentaxbackup.github.io/file/14375_Error1.jpg)
## Post #17
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T13:21:38+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from Kva3imoda
>
> The "Copy-Paste" metod does not work for this.

It looks like I'm deleting/changing the information about buffer vertex size in this MDL type. Your model without changes does not give this error.
## Post #18
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T13:45:56+00:00
- Post Title: Re: [Request]Hob game MDL converter

I think this is about such information:
<vertexbuffer positions="true" normals="true" texture_coord_dimensions_0="float2" texture_coords="1">
This can be found at the beginning of of any xml file.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-18T14:57:22+00:00
- Post Title: Re: [Request]Hob game MDL converter

the uvs for C_Batrabbit.mdl are at FVF pos 52 (dec). The FVF size (=vertex declar.?) is at file offset 0x648: 58 00 (8 bytes before start of vertices).

It's claimed to be a skinned mesh so weights to be expected in the FVF block. But it looks like there's normals only (bi, or tangent, whatever) at offsets 12, 28 and 40 (dec).

When decreasing the FVF block you'll at least have to write a 0x20 to offset 0x648 and copy the uvs (8 bytes from pos 52-59 to pos 24-31).
## Post #20
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T20:20:56+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from shakotay2
>
> 
When decreasing the FVF block you'll at least have to write a 0x20 to offset 0x648 and copy the uvs (8 bytes from pos 52-59 to pos 24-31).
Yeah exactly. This is an excellent remark. I tried it, but failed.

It is a pity that among us there is no OGRE specialists. What if these 88 byte blocks are another OGRE standard? This means that we are on the wrong track. Now we just do not know why the the OGRE tools not understand these files.
## Post #21
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T20:36:25+00:00
- Post Title: Re: [Request]Hob game MDL converter

> In OGRE, the HardwareBuffer class represents a vertex buffer. The HardwareBufferManager singleton allows you to create new hardware buffers.
>
> 
>
> Creating a vertex buffer is quite simple, you call the createVertexBuffer method and tell it the following pieces of information:
>
> 
>
> How you plan to use the buffer
>
> The number of bytes that represent each vertex
>
> The number of vertices in the buffer
As I understand it, in Ogre we set/select the block size.
## Post #22
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T20:50:25+00:00
- Post Title: Re: [Request]Hob game MDL converter

Ok, while we are struggling with this "88byte" files, can anyone create a utility for  "nonconvertible_v1.9_o" files?

This is a fairly simple utility that should find a pattern - "vertex count", delete "the wrong header" and paste "the correct header".
## Post #23
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-18T21:12:19+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from Kva3imoda
>
> 
It is a pity that among us there is no OGRE specialists. What if these 88 byte blocks are another OGRE standard? This means that we are on the wrong track. Now we just do not know why the the OGRE tools not understand these files.
The problem is trying to get them to work with the existing tools really. The format is actually not complicated. It might even be easier to make a new tool that finds and loads the mesh/skeleton data, but since you need to import these stuff back, I guess you need the existing tools.

The problem is mostly data sizes/offsets imo. Like shakotay said 0x648 is where the block size is. Also 2 bytes later at 0x64C there is the offset to the next data, which is actually block size * vertex count + 6 = 88 * 1245 + 6 = 109566. There is also another offset like this before the indices, which will direct you to the skeleton data. So if you are trying 32 bytes blocks, you need to change these accordingly.

I tried the opposite of what you are doing, and copied the indices and vertices from the Batrabbit to the Fish. It came out like this.



I copied the skeleton too, but the animation is messed up. I didn't expect it to work anyway  I am not sure if 32 bytes is necessary though. It feels like the 88 bytes files can also work with proper header/offsets.

Anyway I will leave the file here, in case you are interested. I don't think I have much left to contribute. I suggest you to try to understand how the file is loaded. There might be some documentation on this format. It seems like "v1.9" files have some missing/extra info that prevents them from getting loaded by the standard tools. You can try finding that. Good luck figuring it out.
[C_BATRABBIT.rar](https://xentaxbackup.github.io/file/14376_C_BATRABBIT.rar)
## Post #24
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T21:39:25+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from akderebur
>
> 
I tried the opposite of what you are doing, and copied the indices and vertices from the Batrabbit to the Fish.

> Reply from akderebur
>
> Anyway I will leave the file here, in case you are interested.
## Post #25
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-18T21:55:48+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from akderebur
>
> I didn't expect it to work anyway
I did not expect that we will understand all this. And that someone will help me.   
You guys rock! Today is my birthday and this is the best gift for me.
## Post #26
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-19T04:13:47+00:00
- Post Title: Re: [Request]Hob game MDL converter

akderebur сan you tell us in more detail how you converted 88 bytes blocks into 32 bytes? I tried to figure out what you deleted, and it looks like you used this scheme: 16 + 28 + 8 + 28 +8

Can you share the utility and the code that you used?

Also, can we create a fully automatic model converter? Can we find a pattern, recalculate the offset data and change the header?
## Post #27
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-19T06:07:17+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from Kva3imoda
>
> akderebur сan you tell us in more detail how you converted 88 bytes blocks into 32 bytes?
I used : 24 + 28 + 8 + 28 

I will be outside whole day and get back home late. I will post the code tomorrow.
## Post #28
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-19T06:41:26+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from akderebur
>
> I will post the code tomorrow.
Ok, thanks. 
I'll try to find a programmer in our community who will create tools for us.

Hob era has begun!
## Post #29
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-24T18:35:30+00:00
- Post Title: Re: [Request]Hob game MDL converter

Well, all my familiar programmers are busy now. But we can always try to make scripts for a Hex editor.

akderebur I still need more details about your changes.
## Post #30
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-25T07:52:45+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from Kva3imoda
>
> 
akderebur I still need more details about your changes.
You already have all the details actually  Here is the code.

```
{
    int vertCount = 1245;

    FileStream newFs = new FileStream("conv_mesh.mesh", FileMode.Create);
    BinaryWriter writer = new BinaryWriter(newFs);

    FileStream fs = new FileStream("C_BATRABBIT.MDL", FileMode.Open);
    BinaryReader reader = new BinaryReader(fs);

    writer.Write(reader.ReadBytes(1608));
    writer.Write(new byte[] { 32, 0 });

    reader.ReadBytes(2);
    writer.Write(reader.ReadBytes(2));
    writer.Write(vertCount * 32 + 6);

    fs.Seek(1616, SeekOrigin.Begin);
    for (int i = 0; i < vertCount; i++)
    {
        writer.Write(reader.ReadBytes(24));
        fs.Seek(28, SeekOrigin.Current);
        writer.Write(reader.ReadBytes(8));
        fs.Seek(28, SeekOrigin.Current);
    }
}

```


This is just the code implementation of what we talked about above. Of course it will only work "BATRABBIT" as the offsets and counts are hard coded.
## Post #31
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-25T09:38:48+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from akderebur
>
> You already have all the details actually

I know, but I do not have experience in such stuff. Honestly, I used a hex editor more than 10 years ago and this is my first binary 3d models. I also need to explain to my friends what I need and how to do it and they also have a very vague idea of how this all works.   This is the reason why I asked for more details.

P.S. Oh, we made a small trial mod using these models: [https://steamcommunity.com/sharedfiles/ ... 1392044956](https://steamcommunity.com/sharedfiles/filedetails/?id=1392044956)
I think I need to add information about you guys and about Хentax. What do you think about it? I'm not sure if you need fame.
## Post #32
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2018-05-30T11:52:30+00:00
- Post Title: Re: [Request]Hob game MDL converter

Оk, guys. This weekend we finished the converted utility. Many thanks to our friend @V for coding.  
[Hob MDL to OGRE MESH Converter(v1.0.0.0)](https://yadi.sk/d/TbFfvCeMQ0CKPA) (update Sep 16, 2020)

Remember this utility converts MDL files into OGRE MESH(v1.100) files, but this is only part of the necessary process. If you want to use these 3D models for your mods in Torchlight/Torchlight2 game. Then you need to take a few more steps.

In addition, you will need this: [OgreXMLConverters + Ogre Meshy viewer](https://yadi.sk/d/rcyZhyqM3W6ajn)

Basic Usage
-----------
1. Place all the converters in any separate folder.
2. Drag and drop a .MDL file onto the HobMdlToMesh.exe converter (or a shortcut to it, if you prefer)
3. Take the resulting .MESH file and drag and drop it onto OgreXMLConverter 1.100.
4. Open the resulting .XML file. Correct the material and the skeleton sections (remove the extra path like this: MEDIA/CHARACTERS/M_SCUTTLECRAB/M_SCUTTLECRAB.skeleton).  Change "float2" to "2" (texture_coord_dimensions_0="float2") and save changes.
(At this point you can use this XML file as you want - if you have the appropriate plugins, then you can import it(for example) into Blender)
5. Take the edited XML-file and drag and drop it onto OgreXMLConverter 1.41 (this converter is included in Ogre Command Line Tools v. 1.7.2). This will result in a TL2-compatible .MESH model. (Technically, you are downgrading a 3d model in v1.41). 
6. Convert the Hob TGA textures to a DDS or PNG textures. Create a .material file. (You can take any standard .material from any suitable model and change it to your own needs) Create a .animation file if you need it (Use GUTS or any text editor). Use the model as you want.

P.S. It requires .net 4.6.1 or higher.
## Post #33
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-05-11T18:53:26+00:00
- Post Title: Re: [Request]Hob game MDL converter

Hello

I have been testing the tool with the latest version and it seems to work for most models barring those in the Characters\!Player folder along with the player accessories.

Errors:
Unhandled Exception: 
System.ArgumentOutOfRangeException: Index was out of range. Must be non-negative and less than the size of the collection.
Parameter name: startIndex
   at System.ThrowHelper.ThrowArgumentOutOfRangeException(ExceptionArgument argument, ExceptionResource resource)
   at System.BitConverter.ToInt32(Byte[] value, Int32 startIndex)
   at HobMdlToMesh.DeSerializers.HobOneNineO.ConvertMdlToMesh(String mdlPath)
   at HobMdlToMesh.Program.ProcessFile(String mdlPath)
   at HobMdlToMesh.Program.Main(String[] args)

Some of the models with this error:
MEDIA\CHARACTERS\!PLAYER\PLAYER.mdl
MEDIA\CHARACTERS\!PLAYER\WARP\WARP_PLATE02.mdl
MEDIA\CHARACTERS\M_CONSTRUCT_HERO\M_CONSTRUCT_HERO.mdl
MEDIA\CHARACTERS\!PLAYER_ROGUE\PLAYER_ROGUE_CLONE.mdl

From what I understand this is due to byte differences between some models, is there an easy way to resolve this?
## Post #34
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-05-19T02:58:24+00:00
- Post Title: Re: [Request]Hob game MDL converter

I found this game 3 days ago (haven't beat it yet, no spoilers) and I found this thread this morning. @Kva3imoda and @akderebur, you may be my new favorite people. seriously, I love what you guys have done. I desperately want to help with this! so far I have taken many of the .MDL files and used your converter to turn them into .MESH files, but that's where I get lost. I would be happy to post the .mesh files if it would help you guys, but I feel like you have probably already moved further along than needing those. Also if you know how to take a .MESH file and make it a .OBJ or .STL I'd love to learn that. Attachment is one of the files I turned into a mesh with your handy tool.
[PLAYER_NOGLOVE.mesh.zip](https://xentaxbackup.github.io/file/18173_PLAYER_NOGLOVE.mesh.zip)
## Post #35
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-05-19T03:08:41+00:00
- Post Title: Re: [Request]Hob game MDL converter

4. Open the resulting .XML file. Correct the material and the skeleton sections (remove the extra path like this: MEDIA/CHARACTERS/M_SCUTTLECRAB/M_SCUTTLECRAB.skeleton).  Change "float2" to "2" (texture_coord_dimensions_0="float2") and save changes.


here's where I get lost
## Post #36
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-05-19T19:12:53+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from ecwhite01 ↑Tue May 19, 2020 11:08 am at Tue May 19, 2020 11:08 am
>
> 
4. Open the resulting .XML file. Correct the material and the skeleton sections (remove the extra path like this: MEDIA/CHARACTERS/M_SCUTTLECRAB/M_SCUTTLECRAB.skeleton).  Change "float2" to "2" (texture_coord_dimensions_0="float2") and save changes.


here's where I get lost

That means to remove the red part from the text in the XML file.
## Post #37
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-05-19T19:44:47+00:00
- Post Title: Re: [Request]Hob game MDL converter

yeah, but where? in the log file? in meshy? in the hex editor?
## Post #38
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-05-19T19:47:00+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from ecwhite01 ↑Wed May 20, 2020 3:44 am at Wed May 20, 2020 3:44 am
>
> 
yeah, but where? in the log file? in meshy? in the hex editor?

In the XML file that is generated, if one does not generate then the model may not convert.
## Post #39
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-05-20T20:18:51+00:00
- Post Title: Re: [Request]Hob game MDL converter

Pre converted models and audio, not all converted.
<Link removed due to site policy>
<Link removed due to site policy>
## Post #40
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-05-20T21:19:56+00:00
- Post Title: Re: [Request]Hob game MDL converter

what is the batchConvertHob.ps1 file?
## Post #41
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-05-21T00:43:00+00:00
- Post Title: Re: [Request]Hob game MDL converter

duckdeer_m stl
[DUCKDEER_M STL.zip](https://xentaxbackup.github.io/file/18182_DUCKDEER_M STL.zip)
## Post #42
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-05-21T15:44:22+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from ecwhite01 ↑Thu May 21, 2020 5:19 am at Thu May 21, 2020 5:19 am
>
> 
what is the batchConvertHob.ps1 file?
Powershell script i made for automating the conversion process.
## Post #43
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-06-16T22:18:31+00:00
- Post Title: Re: [Request]Hob game MDL converter

Damn, more than 2 years have passed. Hi guys. I am glad that it became interesting to someone. Sorry for not responding on time.  

> Reply from 09williamsad ↑Thu May 21, 2020 4:18 am at Thu May 21, 2020 4:18 am
>
> 
Pre converted models and audio, not all converted.
Oh, did you convert audio? That would be very helpful.

About your question about non-convertible models. I will try to see what is there, but I already forgot how and what I did.   Also my friend programmer is busy right now.
## Post #44
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-06-20T02:43:31+00:00
- Post Title: Re: [Request]Hob game MDL converter

Well, it looks like this is the 3rd type of Mdl-file. 


CONSTRUCT_BLADE.MDL

As you can see, this type of MDL has FVF size 48 (Other 2 types 32 and 88). This means that our converter does not know how to convert this MDL Type3. We need a new algorithm.
## Post #45
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-06-22T17:44:34+00:00
- Post Title: Re: [Request]Hob game MDL converter

have any of you made any progress towards converting the player into a usable mesh?
## Post #46
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-06-23T02:21:41+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from ecwhite01 ↑Tue Jun 23, 2020 1:44 am at Tue Jun 23, 2020 1:44 am
>
> 
have any of you made any progress towards converting the player into a usable mesh?
Well, I did it a long time ago, at the beginning.




Maybe not completely. There are some nuances with hand upgrades.
## Post #47
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-08-29T15:36:42+00:00
- Post Title: Re: [Request]Hob game MDL converter

any chance you ncould share those lovley mesh files or share your conversion process?
## Post #48
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-09-16T02:03:02+00:00
- Post Title: Re: [Request]Hob game MDL converter

Ok, we have a new converter. This should work with non-convertible models.
Now I tried Win7 version - it works fine.



HobMdlToMesh_Windows7_Framework4.6.1 : [https://yadi.sk/d/TbFfvCeMQ0CKPA](https://yadi.sk/d/TbFfvCeMQ0CKPA)
## Post #49
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-09-16T09:27:43+00:00
- Post Title: Re: [Request]Hob game MDL converter

Yep, i tested it in batch on the models that did not initially convert and it worked.
Updated model extract <Link removed due to site policy>
## Post #50
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-09-18T00:24:23+00:00
- Post Title: Re: [Request]Hob game MDL converter

Thanks for the update @09williamsad   

Well, I have a request for you. Can you convert the MEDIA/LEVELSETS directory? This directory contains level elements, I would like to try to move this to GUTS(the Torchlight2 editor).

I know I should try your PowerShell script, but your MEGA archive is so convenient.
## Post #51
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-09-19T09:51:35+00:00
- Post Title: Re: [Request]Hob game MDL converter

Levelsets have been converted <Link removed due to site policy>
## Post #52
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-09-20T11:25:47+00:00
- Post Title: Re: [Request]Hob game MDL converter

@09williamsad thank you very much for your work. Now all Hob 3d models converted.
## Post #53
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-09-20T14:45:26+00:00
- Post Title: Re: [Request]Hob game MDL converter

converted to what file type?
## Post #54
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-09-20T14:49:01+00:00
- Post Title: Re: [Request]Hob game MDL converter

FBX
## Post #55
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-09-23T00:05:10+00:00
- Post Title: Re: [Request]Hob game MDL converter

If you are curious, I put some Levelsets models in the Torchlight2 editor(GUTS).




And found this cute prototype Hob character. (LEVELSETS\WIDGETS\PLAYER_STAND_01)



There is still a lot of work to do with levelsets here. I need to make thousands of materials. I don't know if I'll ever end this. 
It works anyway, and it's good.
## Post #56
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-09-23T06:50:52+00:00
- Post Title: Re: [Request]Hob game MDL converter

@09williamsad I modified your script(I don't know how to write scripts, so not perfect, but it works   ) a bit and put this in my OGRE tools archive. Maybe this will help someone convert MDL-files to Torchlight2 meshes directly.
## Post #57
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-09-24T14:21:49+00:00
- Post Title: Re: [Request]Hob game MDL converter

can any of you fine fellows find a way to make an .STL file out of the character? love that prototype too, btw
## Post #58
- Username: Kva3imoda
- Rank: beginner
- Number of posts: 38
- Joined date: Sun May 29, 2016 7:12 am
- Post datetime: 2020-09-24T22:35:39+00:00
- Post Title: Re: [Request]Hob game MDL converter

Hey @ecwhite01, you can use any fbx2stl online converter like this: [https://anyconv.com/fbx-to-stl-converter/](https://anyconv.com/fbx-to-stl-converter/)



But I found that some fbx 3d models have bugs - some normals are turned in the wrong direction. I think this occurs with subtle fabric-like elements.



both models:
[https://yadi.sk/d/3oGZsVEG9368Rg](https://yadi.sk/d/3oGZsVEG9368Rg)
[https://yadi.sk/d/i34JVnApzjCKCA](https://yadi.sk/d/i34JVnApzjCKCA)
## Post #59
- Username: ecwhite01
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:02 am
- Post datetime: 2020-09-29T14:02:07+00:00
- Post Title: Re: [Request]Hob game MDL converter

Kva3imoda, you're a benevolent god. thank you
## Post #60
- Username: Morrow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 16, 2021 9:46 pm
- Post datetime: 2021-09-16T13:49:24+00:00
- Post Title: Re: [Request]Hob game MDL converter

> Reply from Kva3imoda ↑Tue Jun 23, 2020 10:21 am at Tue Jun 23, 2020 10:21 am
>
> 
ecwhite01 wrote: ↑Tue Jun 23, 2020 1:44 am
have any of you made any progress towards converting the player into a usable mesh?

Well, I did it a long time ago, at the beginning.




Maybe not completely. There are some nuances with hand upgrades.

What software are you using to preview the animations here? I've been trying to import the .skeleton animations into blender to no avail.
