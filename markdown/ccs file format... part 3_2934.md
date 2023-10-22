## Post #1
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-02-11T18:05:40+00:00
- Post Title: ccs file format... part 3

*Sigh* This just doesn't end.

I figured out how to get the textures, how the archive is structured and I even know where the models are, but I can't read them.
[Here's](http://phorte.ph.ohost.de/ccs/barrier0.tmp) what I think is a model (cut out from the archive).

The archive refers to this as "MDL" and it's the biggest file in there (apart from the texture).

The first 24h bytes seem to be the header. If it's the "barrier" I think it is, it's nothing more than a big box or plane but reading the bytes as float or double doesn't produce any sensible results, so I think this is not actually a list of vertices? What else could it be?("list of vertices" is the only thing I know -.-)
## Post #2
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2009-01-01T00:23:02+00:00
- Post Title: ccs file format... part 3

I've decided to work on it some more so if someone has the time, [Here's](http://phorte.ph.ohost.de/ccs/ccs.pdf) the summary of everything I know about this file format (last page explains my problem).
## Post #3
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-01-08T04:07:04+00:00
- Post Title: ccs file format... part 3

BREAK in the file. I have managed to take your assumtion on the CCCC0800 chunk you suggested might be the MDL info, and decipher what I believe to be XYZ and UV data. IE: Verteces and texture coordinates

Look at this file, starting at offset 0x00000268, if I'm correct, the first three bytes are in fact X, Y, Z, followed by U, and V texture coords, followed by a 00 byte and then the next XYZUV.

Granted this file is from //Quarantine, since it's all I had with me when I was looking through. Also, I've determined that MDL_'s are not simply models, but individual mesh objects contained within a single model. 

This file is a standard katana like the Kotetsu Sword. I have ripped this type of sword from PCSX2, and know it's basic shape and construction... Unfortunately the ripped models are heavily distorted due to the way the camera's depth is rendered... so the ripped models are largely useless-BUT, they give us an accurate vertex/polycount to work with.

As far as I've seen from the comparison between the cmp and tmp, they seem to be the exact same format, all of the data in the documentation you made fits with the cmp. This is what leads me to believe this is a relevant discovery.


Also, each 'object' listed under the initial file list, contains a trailing byte that determines exactly which file it belongs to. This byte is found exactly two bytes before the start of the next 'object' name. This byte is a number equal to the files as they are listed in order. This numbering system begins with 01, NOT 00.

All objects are listed once for every file they relate to, such as the OBJ_ objects in character models. These I've determined are bones, as they are listed once for the model file (../max/filename.max) and each of the animation files (../anm/animnam.max)


All I really need to do now is plot the numbers in a modeling program, though I'm not sure how yet, and then compare what I learned to the GU series files for final verification. I hesitate to say it, but I think I may have cracked my very first format...
[cw2hkt00_1.rar](https://xentaxbackup.github.io/file/2698_cw2hkt00_1.rar)
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-01-19T23:46:20+00:00
- Post Title: ccs file format... part 3

> Reply from Satoh
>
> BREAK in the file. I have managed to take your assumtion on the CCCC0800 chunk you suggested might be the MDL info, and decipher what I believe to be XYZ and UV data. IE: Verteces and texture coordinates

Look at this file, starting at offset 0x00000268, if I'm correct, the first three bytes are in fact X, Y, Z, followed by U, and V texture coords, followed by a 00 byte and then the next XYZUV.

Granted this file is from //Quarantine, since it's all I had with me when I was looking through. Also, I've determined that MDL_'s are not simply models, but individual mesh objects contained within a single model. 

This file is a standard katana like the Kotetsu Sword. I have ripped this type of sword from PCSX2, and know it's basic shape and construction... Unfortunately the ripped models are heavily distorted due to the way the camera's depth is rendered... so the ripped models are largely useless-BUT, they give us an accurate vertex/polycount to work with.

As far as I've seen from the comparison between the cmp and tmp, they seem to be the exact same format, all of the data in the documentation you made fits with the cmp. This is what leads me to believe this is a relevant discovery.


Also, each 'object' listed under the initial file list, contains a trailing byte that determines exactly which file it belongs to. This byte is found exactly two bytes before the start of the next 'object' name. This byte is a number equal to the files as they are listed in order. This numbering system begins with 01, NOT 00.

All objects are listed once for every file they relate to, such as the OBJ_ objects in character models. These I've determined are bones, as they are listed once for the model file (../max/filename.max) and each of the animation files (../anm/animnam.max)


All I really need to do now is plot the numbers in a modeling program, though I'm not sure how yet, and then compare what I learned to the GU series files for final verification. I hesitate to say it, but I think I may have cracked my very first format...

I read you post and you are right about a few things, but to clarify:
The vertexes do begin at off set 268, but those are only the vertexes there. Four bytes back there is B6 or 182, which is the number of vertexes.
The vertexes like most PS1 games, and some PS2 games are 32 Bit Signed Integer. Which means they can take both Positive and Negative Values. So its
2ByteX, 2ByteY, 2ByteZ for each vertex. Most games (but not this one) that use the 32 Bit Signed, have a null 00 00 after each vertex to make it 8 bytes for better processing.
Here is a quick 2d plot of the vertexes of the sword in Excel

and the Excel spread sheet that provides a rough conversion of 32bitsigned to decimal.
[http://ps23dformat.wikispaces.com/file/view/2BYTESS.xls](http://ps23dformat.wikispaces.com/file/view/2BYTESS.xls)
## Post #5
- Username: Chueco
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 21, 2010 11:58 am
- Post datetime: 2010-01-27T02:05:33+00:00
- Post Title: ccs file format... part 3

I'm in the process of writing up a document on what all I've found on the CCS file format, as well as a program that can open and view the models/textures from them.

I was just wondering, have you figured out how the triangles are stored yet?
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-01-27T20:12:06+00:00
- Post Title: ccs file format... part 3

> Reply from Chueco
>
> I'm in the process of writing up a document on what all I've found on the CCS file format, as well as a program that can open and view the models/textures from them.

I was just wondering, have you figured out how the triangles are stored yet?

Okay, I'm not 100% sure about this, but if this is like other games I've seen then what I am saying is correct:
After all of the 6byte vertex array, there is an 4byte array for each vertex. The fourth byte in each array is the "Connection" byte which only takes on the values of either 00 or 01.
If the Connection byte is 01 then you connect that vertex with the vertexes right before it and right after it.
If the Connection byte is 00 then do not connect this vertex with the next vertex.
So the Model is sets of Tristripes with separated with either double end zeros ( ....00 ...... 00).
I think you still connect the Connections with only one zero, you only do not connect if there are 2.
A similar tristrip model format is used in 'Godzilla Unleashed" (but with floats for the vertexes).
I want to show you the mesh, but I need to find a way to batch convert the Signed integers into floats so that Ogre3d/Blender can read them.
## Post #7
- Username: Chueco
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 21, 2010 11:58 am
- Post datetime: 2010-01-28T05:43:22+00:00
- Post Title: ccs file format... part 3

Yup, that's it. took me forever to figure it out though. I wrote a giant python script which reads the CMP file and converts the meshes to a plain text format which I then import into 3dsMax with a custom maxscript. If I had blender I could probably whip up an importer which could take a CMP file directly.
## Post #8
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-02-13T14:14:35+00:00
- Post Title: ccs file format... part 3

Awesome, and thanks for PMing me Satoh.

tmp is indeed almost the same as cmp and the triangles/quads (tmp uses both) are stored similarly to what FurryFan described, but instead the "connection" byte can be 00, 01 or 02 (and possibly other values):
02, 02, 00 = triangle using these vertices
02, 02, 00, 00 = quad(/two triangles) using these vertices
01, 01, 00, 00 = quad(/two triangles) using these vertices, but inverted order

Characters and other big models seem to have a slightly different format, but I haven't really looked into it yet. 
Other stuff is looking good though, like the arena's monitor:
## Post #9
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-02-14T16:45:15+00:00
- Post Title: ccs file format... part 3

ZOMG Why did I stop getting my email alerts on this thread!!? There's been REAL progress and NOW you stop sending the alerts!? Xentax you cruel cruel woman!  



Anyway, this is absolutely awesome... 

So, it seems we can grab some scenery objects, yes? What about weapons, they should be fairly simple... at least they seem un-complex compared to characters. Also, by any chance could I get my hands on those aforementioned scripts? 

I know even less about writing import export scripts than I do about file exploration.

Either way, I'll have to look back through the files and see what I can learn with this new info...


> Reply from Forte
>
> Awesome, and thanks for PMing me Satoh.
No problem. I didn't want to keep any info to myself since I'm so bad at this type of thing XD
## Post #10
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-02-15T00:53:56+00:00
- Post Title: ccs file format... part 3

Yeah, most weapons work fine, too.
It also looks like there's more data for each vertex, but I can't even tell if it's somehow UV related or not. A simple file would be again barrier.tmp (added as attachment):

0008CCCC is located at 0x0D88, amount of vertices(=34) is at 0x0DB4 and after xyz (6 * 34 bytes), there's the connection thing (by the way, any ideas what the other three bytes of that stand for?), size being 34*4 bytes. 
After that, there's 34*4 bytes of some data mostly consisting of the values 64, 128, etc and at the end,  there're 34*4 bytes again, but they don't make sense to me either <_<

By the way, here's a simple program to extract the meshes as obj files:
[http://www.forte.spacequadrat.de/upload/CCS2OBJ.rar](http://www.forte.spacequadrat.de/upload/CCS2OBJ.rar)

If it shows "File xxx processed" but you don't see any obj files, it most likely means that the program encountered some kind of error while trying to parse the data.

Edit: So yeah, the last block of data is indeed texture coordinates, but I can't figure that out exactly. 
So there's two bytes for u and two bytes for v, but how can I convert them to float values that make sense? It works fine for weapons because they only use one byte per u/v component, so dividing that value by 256 gives me good floats, with the overall result being:



But barrier, for example, uses both bytes for u and v (tex coords start at 0x0F94) but they don't make sense no matter how I convert them (without breaking the weapon's uv that is)
[barrier.rar](https://xentaxbackup.github.io/file/2782_barrier.rar)
## Post #11
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-02-16T00:49:27+00:00
- Post Title: ccs file format... part 3

well... it hardly seems necessary to ask, but are there any preceding or trailing bytes between the UV coords... or are there unknown UV header segments?

If so I'd bet that's what determines the UV map type... it's probably different for static objects... most games use different formats for scenery vs. active objects... Though I would have expected the files to be more different in this case...


Also I should remind that the Barrier object had an animated texture... I've seen games that store animated tex's in the models instead of using code to change them... So that's another possibility...

Tried looking at the viewscreen UV's? I doubt it'll have animated textures... Either way I suggest investigating some other model...but I can't think of a perfect example right off.


And now I'ma check out this OBJ converter...
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-02-16T03:01:10+00:00
- Post Title: ccs file format... part 3

Sounds like half floats you can convert half floats with 
[http://www.fox-toolkit.org/ftp/fasthalf ... ersion.pdf](http://www.fox-toolkit.org/ftp/fasthalffloatconversion.pdf)
## Post #13
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-02-16T11:19:53+00:00
- Post Title: ccs file format... part 3

Eh, damn. They do use the normal u(and v) = (byte_0 / 256 + byte_1) format, but I always viewed them through a program I made which had a problem with texture coordinates being over 1.0, barrier and (most) others works fine with blender for example.

I've updated the obj extractor to include texture coordinates in the obj and extract the textures as well. (still doesn't work properly because some MDLs are unhandled)

2ova01.tmp has a pretty big MDL chunk at 0x135B0, but the vertex count is nowhere to be found(it doesn't seem to be 337 (value at 0x135F0))
[2ova01.rar](https://xentaxbackup.github.io/file/2785_2ova01.rar)
## Post #14
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-02-16T21:38:49+00:00
- Post Title: ccs file format... part 3

> Reply from Forte
>
> Eh, damn. They do use the normal u(and v) = (byte_0 / 256 + byte_1) format, but I always viewed them through a program I made which had a problem with texture coordinates being over 1.0, barrier and (most) others works fine with blender for example.

I've updated the obj extractor to include texture coordinates in the obj and extract the textures as well. (still doesn't work properly because some MDLs are unhandled)

2ova01.tmp has a pretty big MDL chunk at 0x135B0, but the vertex count is nowhere to be found(it doesn't seem to be 337 (value at 0x135F0))

I recently dealt with Sonic Adventure DX's models for the PC, they had an interesting structure that when exported to OBJ, left each section of verts weighted to a bone separated as individual objects... (Meaning the elbows would be separate objects from wrists and shoulders, etc etc...)

Also, looking through the IMOQ character files, it seems each body part has a separate mdl that are all linked together in some way...

This could be the same with Ovan there. It could be that the character model header has more info than other models, including a bone count, character identifier, any other extra data characters may have...

I can't imagine what 337 could be referring to though...

EDIT:
However! Ovan has several soft body rigged clothing pieces, it could be that those are handled in there as well... for instance it could be that 337 is the weight or falloff of the softbody rig, or that it refers to root verts that don't get displaced by soft rigging... any number of things... I would suggest using someone like Bordeaux who doesn't have that kind of clothing...

EDIT: Also the UV dump function seems to be a bit off...

That doesn't look like w2dgn00's texture at all... (and it should since UVs are dropped on top of textures...)
Also, a lot of textures aren't dumping at all.

Also EDIT:

It seems the UV's on some are dumping correctly, and some textures are as well... However, it seems the UV's are dumping incorrectly but in similar shapes to the objects they represent... It could be that there is an issue separating the UVs into different meshes and they are getting massively distorted because of it... I've been dumping directly from CCS, I'll try TMP dumping shortly.

Also also EDIT: TMP dump made no difference...
## Post #15
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-02-17T17:59:01+00:00
- Post Title: ccs file format... part 3

The problem isn't really what 337 stands for (I've ignored almost all values in the header of each mdl and they still come out fine), but how to read the chunk. And every character/avatar has that strange structure 2ova01 has. 
I'm expecting the vertex count at 0x135D8 (start of chunk + 0x24), but instead there's some huge int (look like indices to something) and the whole format seems to be different than other mdls' anyway.

Also, most of the bugs are fixed and the program will now extract every non-character/avatar/etc obj and every texture(although separately for now). (there was a problem with trailing zeros if the vertex count * 6 is not a multiple of 4, which messed up about everything)
## Post #16
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-02-18T23:45:41+00:00
- Post Title: Re: ccs file format... part 3

> Reply from Forte
>
> 
Also, most of the bugs are fixed and the program will now extract every non-character/avatar/etc obj and every texture(although separately for now). (there was a problem with trailing zeros if the vertex count * 6 is not a multiple of 4, which messed up about everything)

'Fraid not. The textures DO seem to all dump properly. But some of the models are still not working.

For instance Sophora's weapon, W2DSWA3L will not produce an OBJ, however the texture does dump.

W2DGN00 's model is only the blade, previously it was only the gun, texture is ok.
W2DGN01 's model won't dump, texture is OK.

Also some models still have weird UV's, W22SW08 is one of them.

I'm beginning to think weapons aren't in any way uniform...
## Post #17
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-03-30T19:08:45+00:00
- Post Title: Re: ccs file format... part 3

Ok, I doubt it'll help much, but I have Endrance's model...

I extracted it from the Crystal.CCS... however that only gives me his geometry with no rigging... but I suppose it could be used to compare relative values...


I'm gonna look through the thread and try to understand the vertex format... it would be so much easier if it were in a document...


Also, the CCS format that .hack//Link uses is identical to the .tmp format of extracted CCS folders...

The extractor will work on static models just as it does for static GU models... however the extractor will not even touch IMOQ series files...

Hackstract will not work on Link's files as they are raw tmp files (despite being named .CCS).

That's all the progress I have for now... If I could see the source for Forte's extractor I might be able to attempt writing a converter for any information I find but as it stands I have no idea how to read a file byte by byte...

In any case I'm going to try completely relearning everything from scratch...

EDIT: Assuming GU uses single weighted vertexes (verts only weighted to one bone at a time)
The indices you think you have could be some format of this data...

The number of bones, the bones' IDs, the start of the vertexes offset, the number of vertexes per the bone with the name [ID].


So it would be:

#of bones
Starting offset of verts
Bone #1 (this would be defined with a name like nut00 or spine01 or something elsewhere)
# verts from the starting offset that are attached to bone #1
Bone #2
# verts from the starting offset that are attached to bone #2
etc.
Then the offset of the Verts starts here.

That's one possibility...


Wait wait... The bone weightings are separated into individual mdl chunks... characters' heads are separate from their torsos etc...

Anyway I'm looking for clues as to how the headers are read...
## Post #18
- Username: raz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 31, 2010 8:29 pm
- Post datetime: 2010-04-02T15:49:20+00:00
- Post Title: Re: ccs file format... part 3

Anyone still have the ccs.pdf that Forte posted up some time ago? I can't no longer find it on the link he/she posted.

Also Forte, thanks for the ccs2obj, it works like a charm!
## Post #19
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-02T16:35:50+00:00
- Post Title: Re: ccs file format... part 3

The contents of this post was deleted because of possible forum rules violation.
## Post #20
- Username: raz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 31, 2010 8:29 pm
- Post datetime: 2010-04-02T16:43:14+00:00
- Post Title: Re: ccs file format... part 3

Hey Satoh!

Thanks once again! and no worries at least it's a starting point for me to learn. (trying to figure out on the image portion first)
## Post #21
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-02T18:25:33+00:00
- Post Title: Re: ccs file format... part 3

in layman's terms, the texture portion is this, the CLUT(Color Look-Up Table, IE Palette).

The CLUT has a 28 byte header, starting with 0x00 04 CC CC every time. Some info in the header is known, but irrelevant for what I'm gonna tell you.

The color table is easy to spot usually, it most of the time starts with 3 random bytes followed by 0x80, that is the Red Green and Blue levels and the alpha (0x80 = 128, which is treated fully solid.) Most colors will end in 0x80...

the 16 color palettes will be 64 bytes long (not including the header), if there are more 4 byte values ending in 0x80 after that, it'll be a 256 color palette, and will be 1024 bytes + the header. 

This is the at a glance version of the CLUT identification technique I use.

the image format itself I don't know right off, but generally they are recognizable by strings of single byte values that are the same or similar... and generally a lot of them in patches... (This is the data relating to colors on the palette. Each byte is one pixel in the image the values of the bytes refer to the number of the color in the CLUT... 01 would be the first color, 02 the second, etc etc... 00 is usually the control color which has the transparency if the image needs one.)

Hope that helps.
## Post #22
- Username: raz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 31, 2010 8:29 pm
- Post datetime: 2010-04-03T03:12:34+00:00
- Post Title: Re: ccs file format... part 3

Yup it does, Thanks!

I noticed that Forte tool does not extract all the models in link tmp file, after some digging I noticed that it fails on the first model on xr2pai1.tmp @ 000031DBh which is a model/mesh chunk (assuming from the CCCC0800).

Perhaps link does not store some model/mesh the same way as other hack games?   

If you are interested, below is the link to the xr2pai1.tmp file
[http://www.sendspace.com/file/zbe0i9](http://www.sendspace.com/file/zbe0i9)
## Post #23
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-03T03:52:02+00:00
- Post Title: Re: ccs file format... part 3

Forte's converter does not support character models yet. XD

EDIT: fixed typo...

EDIT2: and sorry, Yes. The models in Link seem to be in the same format as GU's models.
## Post #24
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-05T01:34:26+00:00
- Post Title: Re: ccs file format... part 3

```
Deleted, wrong, check newer posts...
```


If anyone has anything to add, I'm all for it...
## Post #25
- Username: raz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 31, 2010 8:29 pm
- Post datetime: 2010-04-05T08:41:20+00:00
- Post Title: Re: ccs file format... part 3

Might not be related but I recently re-download Forte CCS2OBJ and there's a new ignore MDL option.
## Post #26
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-05T20:13:36+00:00
- Post Title: Re: ccs file format... part 3

Does anyone have all of the backlogged files? Some of the versions could rip certain models that don't rip properly anymore.

I keep three versions currently, I have one from a few weeks back, one slightly later and one that's the newest... I wish I'd kept them all instead of overwriting them. Then I'd have maximum compatibility...Oh well...
On a side note, OBJ is a REALLY simple format... I could probably write one by hand...

The vertex coords are stored in CCS as 2 byte signed int's correct? that means... everything up to 32767, and down to -32767, right?

I'm considering trying to get geometry from some of these small MDL chunks I'm seeing in 2bcfz0... Oh, by the way, the average character model should have (give or take) 1500 triangles. (I got that my looking at the Endrance statue part of the Crystal.CCS rip... I found something in 2bcfz0 that seemed to be about 1700... I'm not certain if that's a full model or some random data... and I forgot where it was in the file... it may have been the CMP chunk... I should look into the CMP chunks of some weapon models...

Ok, here is what I know so far... (Not including CCS PDF Info)

```
[0xNumbers in braces] indicate Hexadecimal offsets, or the values stored at those offsets.
0xNumbers out of braces are actual hexadecimal values

MDL Chunk Definitions:
Assuming this chunk starts at [0x0]

[0x0] 4 bytes, title	CCCC0800 (0x0008CCCC)
[0x4] 4 bytes, #*4 = size of chunk starting from 0x8	(0x39, 57)
[0x8] 4 bytes, # = Chunk ID Number	(0x43, 67)

[0x24] 4(2?) bytes, # = number of vertices	(0x08, 8)
[0x28] 4 bytes, #*4 = size of block starting at [0x4]'s data	(0x90, 144)
[0x2C] start of Vertex pool... Length of vertex pool is [0x24]*6 (=0x30, 48)
[0xEnd of Vertex Pool](0x5C) Start of Connection Pool... Length is the rest of the Chunk


Vertex Pool Block definitions:
Assuming the start of each vertex is [0x0]...

[0x0] 2 bytes, X coord
[0x2] 2 bytes, Z coord
[0x4] 2 bytes, Y coord

(This is correct as this game uses Z-Y transposition coordinate system, common in many PS2 era games)

Connection Pool Block definitions:
Assuming the start of each connection is [0x0]...

[0x0] 2 bytes, index of vertex. Ranges from 0x0 to 0xThe number of vertices-1 (0x0-0x7 in this case)
[0x2] Connection type.


??? Chunk Definitions:
Theory, Bounding box?

[0x0] 4 bytes, title	CCCC2300 (0x0023CCCC)
[0x4] 4 bytes, #*2 = size to end of block from 0xC? 
[0x8] 4 bytes, Chunk ID
[0xC] Start of...? Looks like a Vertex pool... Possibly the Bone Pool...	(ends at 0x38) 
[0xEnd of ??? Pool] Another familiar pool, looks like a Connection Pool...	(ends at end of chunk)

CMP Chunk Definitions:
Theory - CMP is the definition for the Skeleton of the model...
Assuming this chunk starts at [0x0]

[0x0] 4 bytes, Name, CCCC0900	(0x0009CCCC)
[0x4] 4 bytes, #*4 = size of chunk from [0x8]
[0x8] 4 bytes, Chunk-belongs-to ID
[0xC] Start of ??? connection pool
[0xEnd of pool] Start of ??? Vertex? pool...

```


[s]Ok wait... every model has a CMP... so maybe CMP is the UV data and it just isn't documented...? I'm confused! Forte! Where did you get the UV data!?[/s]
Found it... it's in the MAT... duh...

ok, ANM header is CCCC0A00, and I think that's for effect animation. Weapon models (which seem to contain things for effects) have many of these... CCS.PDF has CCCC0700 as an ANM header, this is likely for skeletal animation...

Chunks labeled with dummy in the name are most likely placeholders so that different animations can be linked to those names...



I should note that I'm not posting this because I'm researching Animations or such, I'm merely noticing things and making sure it's documented somewhere, this just happens to be the best place, as my files could get lost, but the forum will still have the info.
## Post #27
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-09T23:44:43+00:00
- Post Title: Re: ccs file format... part 3

Ok, I'm thoroughly stumped, frustrated, and otherwise not happy at all with this CCS format...

I managed to bash my head on the keyboard enough to write a crude file converter only to discover that I know absolutely nothing that I thought I knew... 

For instance, I don't have clue #1 how to find the offset that writes out the actual polygons that belong to the vertices...

I had assumed it would be directly after the vertex pool like in static model files, but apparently there is something else going on...

I managed to dump a few of the shadow body parts from the GU and IMOQ character models, but the rest of the models are complete nonsense to me...

Anyone care to post their documentation?
## Post #28
- Username: Seraphil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 02, 2010 2:44 am
- Post datetime: 2010-04-10T13:17:59+00:00
- Post Title: Re: ccs file format... part 3

Images are available? If yes, could you post them, please?
## Post #29
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-10T17:04:10+00:00
- Post Title: Re: ccs file format... part 3

They're literally just wonky cubes... Not worth looking at...

I you want something to be impressed by, download Forte's CCS2OBJ and use it on any of the non-character models...
## Post #30
- Username: raz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 31, 2010 8:29 pm
- Post datetime: 2010-04-10T18:53:41+00:00
- Post Title: Re: ccs file format... part 3

Can't the sequential vertices form up a triangle in which 2 triangle form up a polygon?

Actually I am not sure what I am saying here, is there any trailing values right after the vertices data?
the character model do seem to have a different way if storing the 3d model [I am assuming due to other information like animation?] comparing to the normal models.

I am/had been trying to figure out the character model by comparing it with normal model data to see if something strikes out. If something does, then perhaps by skipping that values/bytes we would be able to export out the character model (without the extra animation/bone/linking/etc).

All that I know right now is character model is also broken into parts face/body/weapon instead of a single model file.
## Post #31
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-11T06:16:46+00:00
- Post Title: Re: ccs file format... part 3

> Reply from raz
>
> Can't the sequential vertices form up a triangle in which 2 triangle form up a polygon?

Actually I am not sure what I am saying here, is there any trailing values right after the vertices data?
the character model do seem to have a different way if storing the 3d model [I am assuming due to other information like animation?] comparing to the normal models.

I am/had been trying to figure out the character model by comparing it with normal model data to see if something strikes out. If something does, then perhaps by skipping that values/bytes we would be able to export out the character model (without the extra animation/bone/linking/etc).

All that I know right now is character model is also broken into parts face/body/weapon instead of a single model file.

That's about the extent of what I've been thinking... I discovered that weapons seem to have a peculiar structure compared to static objects as well... I suppose since Forte's busy I'll have to scrutinize the source for his exporter... 

Unfortunately I'll have to go find some more scrute for that... Luckily it seems to look enough like C# that I can understand the syntax and maybe(?) rewrite it... or at least glean the structure of weapons and in turn learn something about characters in the process... I wish MA were helping with this... he'd have this cracked in a number of days no doubt...
## Post #32
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-04-11T20:54:14+00:00
- Post Title: Re: ccs file format... part 3

> Can't the sequential vertices form up a triangle in which 2 triangle form up a polygon?
That wouldn't work, you really have to work with the tristrips.

> If something does, then perhaps by skipping that values/bytes we would be able to export out the character model (without the extra animation/bone/linking/etc).
There's extra info right in the header. The rest of the chunk seems somewhat similar to the normal format, but exporting it as-is doesn't turn out well.

I'll try documenting the format. 
A dword(integer) is 4 bytes and float is two bytes.

To calculate a float (byte0 and byte1 are signed bytes):
float f = ((byte0 & 0xFF) / 256f) + byte1

Basic format:

```
dword chunkID //0xCCCC08000
dword chunkSize

struct Unknown0 {
byte unknown
} unknown0[20]
dword mdlType //assuming it's not 0x80000000 in which case the following structure is different
struct Unknown1 {
byte unknown
} unknown1[12]
dword vertexCount

//MeshData
//Vertices
struct Vector3f {
float x
float z
float y
} v[vertexCount]

if ((vertexCount % 2) == 1) { //ignore trailing zeroes that appear if the space used by the vertices is not multiple of 4
word trailingZero
}

//TriStrips
struct VertexConnection {
byte unknown0
byte unknown1
byte unknown2
byte connect
} vc[vertexCount]

//Unknown
struct Unknown2 {
dword unknown
} unknown2[vertexCount]

//UV
struct Vector2f {
float u
float v
} uv[vertexCount]
```


The connection byte in VertexConnection can either have 0, 1 or 2 as value.
2: reverse vertex connection
1: normal vertex connection
0: TriStrip end

You can count the zeroes to find out how many triangles there will be.

Now, the usual format is something like "1 or 2, 1 or 2, 0, 0". Let's assume the vertices these connections belong to are called A, B, C and D respectively.

For 1, 1, 0, 0:
Triangle1: ABC
Triangle2: CBD

For 2, 2, 0, 0:
Triangle1: BAC
Triangle2: BCD

If there is no 0 after the first 0:
For 1, 1, 0:
Triangle1: ABC

For 2, 2, 0:
Triangle1: BAC

As far as I'm aware, combinations like 1, 2, 0, 0 or 2, 2, 0, 0, 0 are not possible.

Now, there are three major problems at the moment:
1. Deal with chunks which have mdlType = 0x80000000
2. Deal with character models
3. Find rotation/scaling info

1. seems easy enough, but I haven't really checked yet.
2. I have no idea what to do about this. Even if I ignore the extra info, the models turn out completely wrong.
3. Haven't really looked into it yet; the info should be in the chunk header somewhere.
Examples would be the bird (proportions of body are wrong, and the wings' rotation seems to be wrong) and the bike (either the wheel is way to big or the main body is too small)
(Sorry, don't have the exact file names at the moment)
## Post #33
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-04-25T23:15:28+00:00
- Post Title: Re: ccs file format... part 3

> Reply from Satoh
>
> raz wrote:Can't the sequential vertices form up a triangle in which 2 triangle form up a polygon?

Actually I am not sure what I am saying here, is there any trailing values right after the vertices data?
the character model do seem to have a different way if storing the 3d model [I am assuming due to other information like animation?] comparing to the normal models.

I am/had been trying to figure out the character model by comparing it with normal model data to see if something strikes out. If something does, then perhaps by skipping that values/bytes we would be able to export out the character model (without the extra animation/bone/linking/etc).

All that I know right now is character model is also broken into parts face/body/weapon instead of a single model file.

That's about the extent of what I've been thinking... I discovered that weapons seem to have a peculiar structure compared to static objects as well... I suppose since Forte's busy I'll have to scrutinize the source for his exporter... 

Unfortunately I'll have to go find some more scrute for that... Luckily it seems to look enough like C# that I can understand the syntax and maybe(?) rewrite it... or at least glean the structure of weapons and in turn learn something about characters in the process... I wish MA were helping with this... he'd have this cracked in a number of days no doubt...

I am pretty sure some data could be in Binary format that looks funny because the values for a say vertexes (as an example) could be spread between bytes. For example I know a few PS1 games like Spyro the Dragon and atleast one PS2 game (The Golden Compass) store vertexes X,Y and Z as something like the following:
 11 SignedBits for the X (eg one full byte plus two Bits from the next byte) 11 SignedBits for the Y and  9 SignedBits (not a typo) for the Z plus a null bit, for a grand total for 32Bits=4 whole Bytes.
This is very unsymmetrical, and noncommunitive compared to simple 4byte floating point values for each vertex.
The advantage is that each vertex takes up only 1/3 the space of floats.
Please send me a sample character model file, and I'll see what I can do.
Even better would be an emulator save state, so I can manipulate each bit and deduce by seeing for far each vertex moves for each bit.
## Post #34
- Username: Null2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 18, 2010 7:18 am
- Post datetime: 2010-05-19T20:49:37+00:00
- Post Title: Re: ccs file format... part 3

Hmm so how does someone, who doesn't know a lic or terminlogy explain what he's asking. Alright I know this maybe repetative but can someone explain this CCS format. I've extract them using the quickbms program but never seen anything like it before. I'm trying to get images from them. What else do I need to do. Also is there a tutorial? It doesn't matter how hard the work is I'd need to do I just want to understand what I'm doing. (Because it bugs me to all hell when I don't.) Is there a way to covert code into bmp? Can someone explain?
## Post #35
- Username: raz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 31, 2010 8:29 pm
- Post datetime: 2010-05-20T00:48:19+00:00
- Post Title: Re: ccs file format... part 3

If you just wanted to extract the image files, just use forte's tool. Otherwise it's more about reading the binary CLUT and exporting it out? (Need to refer to my notes back home)

Forte Tool
[viewtopic.php?p=35504#p35504](http://forum.xentax.com/viewtopic.php?p=35504#p35504)


CLUT Explanation
[viewtopic.php?p=36522#p36522](http://forum.xentax.com/viewtopic.php?p=36522#p36522)
## Post #36
- Username: Null2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 18, 2010 7:18 am
- Post datetime: 2010-05-20T23:25:34+00:00
- Post Title: Re: ccs file format... part 3

Thanks, for me it's both. I want the images because that's mainly what "this" game is about. However I'm also here because I'd like to understand about file format, and conversion. I doubt it's something I'd carry beyond this but it makes me feel at ease when I can be more flexible with something because I know it. (Plus just looking at some of that mess inside the tmp files just ticked me off. It was like the haha of not being able to go further.)
## Post #37
- Username: Anomy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 04, 2007 3:04 pm
- Post datetime: 2010-07-19T06:35:59+00:00
- Post Title: Re: ccs file format... part 3

Did any of you end up making any progress on this?
## Post #38
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2012-04-19T09:18:27+00:00
- Post Title: Re: ccs file format... part 3

I hate to revive such an old thread, but several people PM'd me already about the CCS2OBJ tool (since the link is long dead), so I'm reattaching it here.
No progress on it since the last post though.
[CCS2OBJ.rar](https://xentaxbackup.github.io/file/5323_CCS2OBJ.rar)
