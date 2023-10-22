## Post #1
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2016-08-01T14:16:02+00:00
- Post Title: 3D model format used by BabylonJS?

First of all, hi!
As some of you have probably noticed, Microsoft now offers customized Xbox One controllers on their 'Xbox Design Lab' page: [https://xboxdesignlab.xbox.com/en-US/customize](https://xboxdesignlab.xbox.com/en-US/customize)
As you can see, there's a pretty live 3D preview of the selected colors on that page as well, a kinda high-quality one even.
Sadly, the meshes consituting the controller model are compressed and/or encrypted, then stored in a proprietary format only used by BabylonJS ([http://www.babylonjs.com](http://www.babylonjs.com)).
Has anyone worked with this before? And are there other, better ways of ripping models from WebGL pages? I have tried the WebGL Inspector plugin for Chrome, but it kept crashing, so I got rid of it again.

FWIW, I put all the important files in a ZIP archive available [here](https://bubbelsearch.de/files/xbone_controller_webgl.zip). They are weirdly numbered, but they should all be there.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-01T20:19:15+00:00
- Post Title: 3D model format used by BabylonJS?

controller.64_Front_Case.64_Front_Case.babylonbinarymeshdata  



controller.64_Front_Case.64_Front_Case.babylonbinarymeshdata.png (46.47 KiB) Viewed 180 times



the only file info is in the 20 byte footer
0x140124 - number of vertices
0x14012c - number of faces

to find the UV start address, multiply the number of vertices by 8 then
go to the face indices start address and go backward that amount

i think this thread will get more attention in the "3D/2D models" section
## Post #3
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2016-08-02T02:34:24+00:00
- Post Title: 3D model format used by BabylonJS?

Thanks, that's already super helpful!
That hex2obj tool looks promising, but I can't get it to work for the life of me. Never having worked with model files in-depth before, the tutorial goes right over my head.
Instead, I've started writing a Python script to help me understand what's going on, but I ran into some problems.

Let's take that controller.64(...).babylonbinarymeshdata file.
Assuming that there are 27635 vertices right at the start of the file, vertex data should start at 0x0 and go to 0x50f64.
(vertex count = 27635, times 4 because they're floats = 110540, times 3 because they're 3D vertices = 331620 == 0x50f64)

hex2obj even displays the last few floats on the left side, which confirms to me that I got everything concerning the vertices:


Compare that with the last three floats my script gave me:

```
-4.110263347625732, 0.6286904811859131, 2.081153631210327
```

Now, there are 0x50f64 other bytes that fill the space between the vertex data and what seems to be the UV data. What are those bytes?
I'm gonna go out on a limb here and guess that those are the normals...?
Right after that comes the UV data and after that the face indices.

Is all of that really needed when constructing an .obj file from scratch? hex2obj doesn't seem to mind, given the complete absence of the word "normals" in its UI.

It's very probable that the above is complete nonsense, but I feel confident, considering I've never done this before.

Thanks again for helping a beginner out.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-02T02:56:04+00:00
- Post Title: 3D model format used by BabylonJS?

nice, it looks like you're picking it up quickly!   
yeah those unused bytes here are likely the normals but Hex2obj doesn't deal with
normals so we just skip that data and fix any messed up normals in your favorite 3d software.
## Post #5
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2016-08-02T03:50:32+00:00
- Post Title: 3D model format used by BabylonJS?

I mean, I am a programmer, so it was only a matter of time :p

Still, I can't figure out how the UVs are stored. They seem to be 4 byte floats, but I'm unsure on how many there are.
According to hex2obj, they start at 0xa1ec8 and end at 0xbd638. Then what's the data between 0xbd638 and 0xd7e60, where the indices are?
It seems those are floats as well, because my script will happily read up to 0xd7e60 and treat the data as (correct-looking, ie. not hilariously out-of-bounds) floats without a hitch. 
They even look like another set of UVs, what with every float being in the range of 0.0-1.0, but I have no idea what to do with them.

Edit: Even if those other floats aren't needed, like the normals, I still don't know how to calculate the length of the UV data block.
Currently I'm just doing

```
file_length - texcoord_data_start - FOOTER_LENGTH - index_count * 4
```

where index_count is the number of indices. Obviously, this isn't good enough. Can you come up with a better way by chance? 

Edit 2: Actually, I've been misinterpreting hex2obj's output. The UV data doesn't end at 0xbd638, but at 0xbd650. Hmm.

Edit 3: Same thing with the indices. There are 27635 indices in that file, but hex2obj only counts up to 14066. Where does it get its data from?
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-02T06:31:52+00:00
- Post Title: 3D model format used by BabylonJS?

the size of the UV block is vertices * 8

the UV block starts at 0xa1ec8 and ends at 0xd7e5f


all data is accounted for unless i'm really bad at math   

vertex block
27635 * 12 = 331620
+
normals block
27635 * 12 = 331620
+
UV block
27635 * 8 = 221080
+
face indices
106671 * 4 = 426684
+
footer
20 bytes
_____________
1311024 bytes
## Post #7
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2016-08-02T13:13:05+00:00
- Post Title: 3D model format used by BabylonJS?

Oh. Guess hex2obj was psyching me out.
There's only one thing remaining then, and that's getting all this data into a format that's easy to work with.
My primitive obj exporter has some weird issues though.
Here's my code so far: [https://gist.github.com/SamusAranX/6342 ... 9b1422f1f1](https://gist.github.com/SamusAranX/6342684293dd9e5bab08a29b1422f1f1)

If I just let my script write out everything, the resulting model looks like this:

Before that, I wrote everything into the obj file, but accidentally commented out the first vertex.
Weirdly enough, the model looked fine then (if you ignore that long, misplaced polygon and the fact the the normals seem to be hecked up)

Also, it seems that OS X's obj parser is a lot more lenient than Blender's. Blender won't even load these abominations. 

I'm pretty sure that the issue is that I don't really understand the OBJ format, and with hex2obj's mesh exporter constantly failing on me, I have nothing to compare my result to.
Could you help me with that again?
## Post #8
- Username: Acewell
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-02T14:34:07+00:00
- Post Title: 3D model format used by BabylonJS?

Topic moved as requested
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-02T16:20:15+00:00
- Post Title: 3D model format used by BabylonJS?

> Reply from GordenF
>
> and with hex2obj's mesh exporter constantly failing on me,I don't see where the problem should be - File/SaveAs mesh results in an obj file (controller.64_Front_Case.64_Front_Case_0.obj) which can be imported into blender for example:



controller_64_Front.JPG (73.91 KiB) Viewed 152 times
## Post #10
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2016-08-02T16:49:03+00:00
- Post Title: 3D model format used by BabylonJS?

I always get the message that MSVCR100.dll is missing when hitting the appropriate buttons.
I have installed every VC++ redistribution imaginable, but apparently, that isn't enough.
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-02T21:34:54+00:00
- Post Title: 3D model format used by BabylonJS?

i made a Noesis python script to open your babylonbinarymeshdata model samples  


 fmt_BabylonJS.zip
(944 Bytes) Downloaded 26 times



it works with all of them, but controller.48_R_Thumsticktop.48_R_Thumsticktop.babylonbinarymeshdata
was a special case and had a 40 byte footer so i added a condition just for that one so all could be opened  

edit
anyone know how to flip the UV data in Noesis python?
i need to flip it on U to get it lined up with the textures
## Post #12
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2016-08-03T12:55:12+00:00
- Post Title: 3D model format used by BabylonJS?

I thank you for your efforts, and while I'd love to use your script, my Windows 10 installation just nuked itself after this Anniversary Update. So much for that, I guess.
Though, while Windows was busy self-destructing, I went through the BabylonJS GitHub repos on my phone and found [a C# program](https://github.com/BabylonJS/Babylon.js/blob/master/Tools/ConvertToBinary/Program.cs) made to convert "regular" models into the babylonbinarymeshdata format.
Interestingly enough, that 20 byte "footer" actually consists of 5 ints of submesh information and can appear multiple times (as it does in that 48_whatever file) if there are multiple submeshes!
Also, I took a closer look at the controller.binary.babylon file that I previously ignored (because it looked like a bunch of scene setup gibberish to me), and lo and behold, it actually contains a bunch of useful information.
Major derp on my part  
Every object in that JSON file has a key called "_binaryInfo" that contains the offsets and lengths of every important data block. Formatted for readability, here's 48_R_Thumsticktop's _binaryInfo:

```
  "subMeshesAttrDesc": {
    "offset": 456032,
    "dataType": 0,
    "count": 2,
    "stride": 5
  },
  "uvsAttrDesc": {
    "offset": 198600,
    "dataType": 1,
    "count": 16550,
    "stride": 2
  },
  "indicesAttrDesc": {
    "offset": 264800,
    "dataType": 0,
    "count": 47808,
    "stride": 1
  },
  "normalsAttrDesc": {
    "offset": 99300,
    "dataType": 1,
    "count": 24825,
    "stride": 3
  },
  "positionsAttrDesc": {
    "offset": 0,
    "dataType": 1,
    "count": 24825,
    "stride": 3
  }
}
```
I'm not sure how that submesh business is supposed to work, but using all this to parse the regular models should be easy enough.
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-08-03T17:34:25+00:00
- Post Title: 3D model format used by BabylonJS?

A subMesh is defined by the following JSON:

{
    "materialIndex": int,
    "verticesStart": int,
    "verticesCount": int,
    "indexStart": int,
    "indexCount": int
}
## Post #14
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-08-03T19:23:21+00:00
- Post Title: 3D model format used by BabylonJS?

GordenF,

The line of a face command contains the enumerations of the points in the face, as 1-based indices into the list of points, in the order they occurred in the file. For example, the following describes a simple triangle:

# Simple Wavefront file
v 0.0 0.0 0.0
v 0.0 1.0 0.0
v 1.0 0.0 0.0
f 1 2 3
## Post #15
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2016-08-04T09:19:39+00:00
- Post Title: 3D model format used by BabylonJS?

I have pretty much given up on my script. 
I'll probably come back to it in a week or so to clean it up, but right now it's a mess.
It would probably be easier to just wade through the thousands of files on the BabylonJS repo and copy their importer.
Anyway,

@AceWell: Finally got around to setting up a Windows VM. Your script worked flawlessly, thanks. 


@Karpati: If I remember correctly, the number of vertices and indices is different in each model.
How would I handle that?
## Post #16
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-08-04T11:00:51+00:00
- Post Title: Re: 3D model format used by BabylonJS?

> Reply from GordenF
>
> Oh. Guess hex2obj was psyching me out.
There's only one thing remaining then, and that's getting all this data into a format that's easy to work with.
My primitive obj exporter has some weird issues though.
Here's my code so far: https://gist.github.com/SamusAranX/6342 ... 9b1422f1f1

You can fix your exporter easily.

Just add 1 to all face indexes when you create the 'f' lines.
## Post #17
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2017-09-29T17:38:34+00:00
- Post Title: Re: 3D model format used by BabylonJS?

Sorry for the big bump, but neither the program nor Noesis script work on the Xbox Avatar Marketplace models.



[http://puu.sh/xLVcy.babylonbinarymeshdata](http://puu.sh/xLVcy.babylonbinarymeshdata)
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-30T00:55:48+00:00
- Post Title: Re: 3D model format used by BabylonJS?

because the structure is slightly different in your sample, you can still convert it with Hex2obj though.  



new_BabylonJS_sample.png (21.78 KiB) Viewed 52 times
## Post #19
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2017-10-01T01:23:39+00:00
- Post Title: Re: 3D model format used by BabylonJS?

> Reply from AceWell
>
> because the structure is slightly different in your sample, you can still convert it with Hex2obj though.  
new_BabylonJS_sample.png
would it be too much to ask for an updated noesis script as well?
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-04T01:27:36+00:00
- Post Title: Re: 3D model format used by BabylonJS?

in this case yes, the info i need looks missing from your sample, too chaotic for my experience level, sorry.
