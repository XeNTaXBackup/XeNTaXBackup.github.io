## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-03T12:20:16+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

Meh bones are in .oct might reverse next week


```
// Cra0kalo/Mariokart64n/Luxox_18
//PC Little Endian


struct VBufHeader
{
// NOP
}

//ShaderDump VertexStructure

struct GPU_ASM
{
    vs_3_0
    def c0, 4, 1, 0, 1000
    def c1, 0.00100000005, 0, 0, 0
    dcl_blendindices v0
    dcl_blendweight v1
    dcl_normal v2
    dcl_position v3
    dcl_texcoord1 v4
    dcl_texcoord v5
    dcl_texcoord o0.xyz
    dcl_position o1
    dcl_texcoord1 o2
    dcl_texcoord2 o3.xy
    slt r0, v0, -v0
}

// Buffer
// Size 24
struct VBufStruc
{
float vd x
float vd y
float vd z
hfloat TextureU
hfloat TextureV
uint32 unknownPadding
uint32 VertexColor
}


// Buffer
// Stride 16
struct VBufStruc2
{
hfloat vn_x
hfloat vn_y
hfloat vn_z
hfloat vn_w

hfloat vt_x
hfloat vt_y
hfloat vt_z
hfloat vt_w


}



// Index Buffer
// Size 24
struct IndexBufStruc
{
uint16 face1
uint16 face2
uint16 face3
}

```





DL
[http://cra0kalo.com/public/Disney%20INF ... ractor.zip](http://cra0kalo.com/public/Disney%20INFINITY%20Model%20Extractor.zip)
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-03T19:28:46+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

Nice work!

It seems normals are easy, you probably figured them out already.
After the first VB block described by you there are groups of 16bytes per vertex that contain normals and tangents as half floats (x y z w).

Here's a short maxscript to demonstrate:

```
(
	ashort = readShort binstr #signed
	nx = (bit.shift (bit.and ashort 0x8000) 16)+(bit.shift (bit.and ashort  0x7fff) 13)+(bit.shift (127 - 15) 23) 
	nx = bit.intAsFloat nx
)

iarr = #()
varr = #()
tarr = #()
narr = #()
farr = #()

IB = getOpenFileName types:"*.ibuf|*.ibuf"
if IB != undefined do
(
	IBsize = getFileSize IB
	
	f = fopen IB "rb"
	do append iarr (readshort f #unsigned) while (ftell f) < IBsize
	fclose f
	
	VB = substituteString IB ".ibuf" ".vbuf"
	if doesFileExist VB do
	(
		f = fopen VB "rb"
		
		for v=1 to (amax iarr) + 1 do
		(
			vx = readfloat f
			vy = readfloat f
			vz = readfloat f
			append varr [vx, -vz, vy]
			
			tx = readHalf f
			ty = readHalf f
			append tarr [tx, 1-ty, 0]
			
			fseek f 8 #seek_cur
		)
		
		for v=1 to (amax iarr) + 1 do
		(
			nx = readHalf f
			ny = readHalf f
			nz = readHalf f
			append narr [nx, -nz, ny]
			
			fseek f 10 #seek_cur
		)
		fclose f
		
		for i=1 to iarr.count/3 do
		(
			i1 = iarr[i*3-2] + 1
			i2 = iarr[i*3-1] + 1
			i3 = iarr[i*3] + 1
			append farr [i1, i2, i3]
		)
		
		max modify mode -- open mod panel for edit_normals to work
		cui.expertModeOn()
		disableSceneRedraw()
		amesh = mesh vertices:varr faces:farr
		meshop.setMapSupport amesh 1 true
		setMesh amesh tverts:tArr
		
		--set smoothing group of all faces to 1 to get one normal per vertex
		for face = 1 to amesh.numfaces do setFaceSmoothGroup amesh face 1
		--set normals via edit normals modifier
		select amesh
		addmodifier amesh (Edit_Normals ()) ui:off
		amesh.Edit_Normals.MakeExplicit selection:#{1..nArr.count}
		EN_convertVS = amesh.Edit_Normals.ConvertVertexSelection
		EN_setNormal = amesh.Edit_Normals.SetNormal
		normID = #{}
		--apply normals
		for v = 1 to nArr.count do
		(
			free normID
			EN_convertVS #{v} &normID
			for id in normID do EN_setNormal id nArr[v]
		)
		collapseStack amesh
		cui.expertModeOff()
		enableSceneRedraw()
	)
)
```

And the result, in order: without normals (autoshmooth by max), with normals and normals themselves
[](http://www.imagebam.com/image/82889a305759103) [](http://www.imagebam.com/image/c60a3b305759097) [](http://www.imagebam.com/image/8b6da7305759095)
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-04T07:08:07+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

> Reply from Chipicao
>
> Nice work!

It seems normals are easy, you probably figured them out already.
After the first VB block described by you there are groups of 16bytes per vertex that contain normals and tangents as half floats (x y z w).

Here's a short maxscript to demonstrate:
Code: Select all-snip-

And the result, in order: without normals (autoshmooth by max), with normals and normals themselves

Yep I figured that out after scrolling down. It's really werid how they split the structure like that though. After the normal info that stuff might be bone weights and links not sure though I think the bone matrixes are stored in those .oct files I'll have a look today.

If anyone else is curious to take a look here is an example model (.oct/.vbuf/.ibuf/.bent/.mtb)
[http://cra0kalo.com/public/research/wr_vanellope.zip](http://cra0kalo.com/public/research/wr_vanellope.zip)
## Post #4
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-04T10:51:26+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

No, the part after normals are definitely tangents (or binormals). And if imported as vertices they create a sphere, as expected for normalized vector coords.
[](http://www.imagebam.com/image/b3924c305863045) [](http://www.imagebam.com/image/b2902f305863056) 

I think bone indices and blend weights are in the first vertex block, specifically what you identified as "unknown padding" and "vertex color".
That "padding" looks like 4 uint8 bone indices. They are 0 at the beginning, but they start to have values afterwards.
[](http://www.imagebam.com/image/f0aebd305863066) 

The next 4bytes are definitely not vertex colors, because they would look like this:
[](http://www.imagebam.com/image/e37999305863074)
I think they are 4 weights stored as uint8 and need to be converted to floats, probably dividing by 255.


> Reply from cra0
>
> It's really weird how they split the structure like that though.I've seen it before in a few games, it must be some sort of optimization.
These buffers should be defined in one of the other files, with the exact number of indices, vertices, and also the number of vertex data blocks (there could be more than 2 in other models) and what elements they contain.
Have you figured out any of these, or are you just importing the raw data?

Also I see you assigned head and torso textures. Did you split the mesh manually or did you find information about material IDs?
## Post #5
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-04T13:24:09+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

> Reply from Chipicao
>
> No, the part after normals are definitely tangents (or binormals). And if imported as vertices they create a sphere, as expected for normalized vector coords.
  

I think bone indices and blend weights are in the first vertex block, specifically what you identified as "unknown padding" and "vertex color".
That "padding" looks like 4 uint8 bone indices. They are 0 at the beginning, but they start to have values afterwards.
 

The next 4bytes are definitely not vertex colors, because they would look like this:

I think they are 4 weights stored as uint8 and need to be converted to floats, probably dividing by 255.

cra0 wrote:It's really weird how they split the structure like that though.I've seen it before in a few games, it must be some sort of optimization.
These buffers should be defined in one of the other files, with the exact number of indices, vertices, and also the number of vertex data blocks (there could be more than 2 in other models) and what elements they contain.
Have you figured out any of these, or are you just importing the raw data?

Also I see you assigned head and torso textures. Did you split the mesh manually or did you find information about material IDs?

I think i found the vertex count for Bob open the .oct file and go to 

0x1D710

0x1D7D4

should be 5558 I applied them manually the .mtb i think has the drawcall/vertex structure for each mesh piece on a different material have to look into it. Need to find that table to figure out the Submeshes
## Post #6
- Username: yocarinha
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 27, 2012 11:33 pm
- Post datetime: 2014-02-06T15:31:58+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

test
## Post #7
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-06T17:48:20+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

Not to mention some missing limbs   
It seems Hellen's files actually contain 3 index buffers and 3 vertex buffers one after another.

IB1: 18777 indices
IB2: 4806 indices
IB3: 2013 indices

VB1: 3784 vertices
VB2: 952 vertices
VB3: 410 vertices

[](http://www.imagebam.com/image/fe27ee306303666) 

This is why we really need to figure out the structure of .oct files in order to read meshes properly.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-06T18:07:24+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

if you want to send me a sample i can look.
## Post #9
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-06T19:16:12+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

Here you go:

> Reply from cra0
>
> If anyone else is curious to take a look here is an example model (.oct/.vbuf/.ibuf/.bent/.mtb)
http://cra0kalo.com/public/research/wr_vanellope.zip

The oct file looks like some sort of database with string values at the beginning and data afterwards.
uint32 at offset 0x0C indicates the size of the string portion
next uint32 is the size of the rest of the file
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-06T19:20:05+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

indeed, OCT files must be parsed for proper mesh information. OCT = scene graph format though. have fun. i parsed a few nodes and stopped. confusing has hell to put the tree together (hard to determine what the structures are for each node). some, like Translation nodes are easy to determine, but others... not so.

```
     // 46 00 - 03 00 0B 0C SubNetwork
     // 47 00 - Name
     // 48 00 - 0B 0C RB_lowerBody_Mesh
     // 49 00 - Type
     // 4A 00 - 01 0C Scene
     // 4B 00 - 05 10 BasisPool
     // 4C 00 - 03 00 0B 14 49 00 Basis
     // 4D 00 - 0B 14 - Geometry3d
     // 4E 00 - Behavior
     // 4F 00 - 05 10 - 4C 00 - Root
     // 50 00 - 0B 14 - 47 00 - 48 00 - 1B 14
     // 51 00 - 00 0B 14 4E 00
     // 52 00 - 05 10 4C 00
     // 53 00 - 0B 14 49 00
     // 54 00 - 0B 14 4E 00 4F 00 0A 0C
     // 55 00 - 02 48 00
     // 56 00 - 1A 0C
     // 57 00 - 02 00 01 1A 0C
     // 58 00 - 04 00 01 01 01 01 0C
     // 59 00 - 05 10
     // 5A 00 - 03 00 1B 14
     // 5B 00 - 02 0B 14 49 00
     // 5C 00 - 1B 14
     // 5D 00 - 01 1B 14
     // 5E 00 - 00 01 14
     // 5F 00 - 12 18
     // 60 00 - 03 - 00 00 00 00 - E1 4D 68 3F - 00 00 00 00 - 01 0C - Translation
     // 61 00 - 01 0C - ProcessorNodePool
     // 62 00 - 01 10 - BasisConversionPool
     // 63 00 - 1B 14 - BasisConversion
     // 64 00 - 01 1B 14 - FromBasisRef
     // 65 00 - 00 1B 14 - ToBasisRef
     // 66 00 - 00 01 0C - DataNodeRef
     // 67 00 - 01 0C - ComponentFamilyPool

```
## Post #11
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-01T15:48:24+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

What version of Infinity are we talking about here, the Wii, PS3, ... other?

T.
## Post #12
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2014-05-03T01:39:41+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

PC, I believe.
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-05-23T22:26:09+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

very nice, thanks a lot for all supporters, thats great, only maximport remain
## Post #14
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-25T12:21:20+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

Yeah, that mesh import with multiple submeshes, like Misses Incredible, is a pain, 
on the other hand I found that the .tbody files can easily renamed to .dds  and you have the texture 

Any progress on the OCT files?

T.
## Post #15
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2014-10-04T22:41:52+00:00
- Post Title: [REL] Disney INFINITY Model Extractor

I am trying to extract some models. but I get unexpected results with the obj file.
I do not know what I'm doing wrong. Smd with MilkShape gives the same problem...



1.jpg (240.49 KiB) Viewed 830 times
## Post #16
- Username: jayd00
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 10, 2014 8:30 am
- Post datetime: 2014-11-10T00:54:36+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

thank you! 
but how to extract textures?.. I'm still searching how..
## Post #17
- Username: Mystie
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 11, 2014 1:38 am
- Post datetime: 2014-11-14T02:50:47+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Really cool program!

BTW, are you considering support for Infinity 2.0 models?
## Post #18
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-22T11:30:45+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

post samples from 2 if they don't work I may take a look depending on free time
## Post #19
- Username: Mystie
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 11, 2014 1:38 am
- Post datetime: 2014-11-28T21:48:15+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

All righty, here ya go.
[sample.zip](https://xentaxbackup.github.io/file/8161_sample.zip)
## Post #20
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-04-23T20:45:30+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

no progress on this ?

T.
## Post #21
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2015-06-22T22:08:34+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

This doesn't seem to be working. Anything I convert just comes out as a completely jumbled and worthless mess of random polygons. I tried Syndrome and a few others with no luck...
## Post #22
- Username: KingKilluaX3
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 31, 2015 9:43 am
- Post datetime: 2015-09-20T18:19:30+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

anyone happen to have textures from the tangled models?
## Post #23
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2015-10-30T14:11:05+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

The files from version 3 has an unknown format. Is it possible to view the new models with the tool from previous versions?
## Post #24
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2015-11-02T15:25:49+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Using the aluigi script you can extract all the content. When I try to visualize some figures with the tool of cra0 these are all broken. 



1.jpg (33.67 KiB) Viewed 166 times


Someone of you have the same problem or you can view them properly?
## Post #25
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2015-11-03T19:58:52+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

not try but interessing
## Post #26
- Username: kangaroo78
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Sep 29, 2015 6:24 pm
- Post datetime: 2015-11-05T10:25:09+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from jmgg
>
> Using the aluigi script you can extract all the content. When I try to visualize some figures with the tool of cra0 these are all broken. 
1.jpg
Someone of you have the same problem or you can view them properly?

I used the aluigi script too, but I cant visualize them even with cra0 tool. I got most of the textures though. I also tried Szkaradek123 importer but not luck either.
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-11-05T21:00:43+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

As a non programmer i have to say this is the perfect format to learn Hex2Obj with because the two data types you need are separated for you and it makes it easy to see where the data starts and what length it is plus it shows what you might would look for in other formats. The vbuf contains your vertex stuff and the ibuf contains your face index. If you combine the contents of both files into one you can open that in H2O and convert the bytes to obj.
## Post #28
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-11-05T23:04:50+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Where did you get that file from??

I have Infinity 3 on my PC, but all I got are these weird unnamed files ( am I missing something ?? )

T.
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-11-05T23:32:46+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

That was from a sample uploaded by jmgg on ZenHAX, the bms script by aluigi to extract the files is here
[http://aluigi.altervista.org/bms/disney_infinity.bms](http://aluigi.altervista.org/bms/disney_infinity.bms)
## Post #30
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-11-06T06:49:23+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

I was hoping szkaradek's blender importer worked so I could grab the models with bones but it seems the format changed since 2.0. I would have no idea what you enter into hex2obj to get the models xD

EDIT: Thanks to AceWell's image of his setup for Darth Maul's model, i managed to grab a model myself! 

This helps alot in understanding how to get other models with hex2obj too.
## Post #31
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-11-06T11:33:44+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Strange, I downloaded Aluigi's Script, saved it as DisneyInfinity3.bms and tried this:

```
quickbms.exe "DisneyInfinity3.bms" "D:\Games\Disney Infinity 3.0"


```


I got this as a result:

```
QuickBMS generic files extractor and reimporter 0.5.24b
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
        (Aug 11 2013 - 11:27:41)

                  http://quickbms.aluigi.org
               http://twitter.com/luigi_auriemma

- start the scanning of the input folder: D:\Games\Disney Infinity 3.0
- open input file D:\Games\Disney Infinity 3.0\.\asset-cache\base\image\assets\05855c35\c01282e8
- open script DisneyInfinity3.bms
- c_structs: "xmath" "OFFSET" "OFFSET + (ENTRIES * 4)"

Error: invalid command "xmath" or arguments -1 at line 35


```


??? Any help please :/

T.
## Post #32
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2015-11-06T16:14:56+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

T
"What's the exact command-line you are using?
The correct one is: quickbms -D script.bms input_folder output_folder
You can even create a shortcut to quickbms.exe with -D appnded in the Target property"
Says Aluigi in zenhax

AceWell/TRDaz
I've tried hex but is   difficult. Can you explain the method and how combine ibuf and vbuf? 
Thanks
## Post #33
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-11-06T20:02:30+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from TaylorMouse
>
> QuickBMS generic files extractor and reimporter 0.5.24b
You should probably update QuickBMS also, i use 0.6.7a




> Reply from DarthphoeniX
>
> Can you explain the method and how combine ibuf and vbuf?
H2O can't parse 2 files at once this is why you need to combine the two. When i say combine the vbuf and ibuf i simply mean copy the content of one into the other so you are working with one file rather than two, you are just appending both data types, like most model files are anyway. This also means the start address for either the verts or face index will always be 0x0 depending on which data type is first in the combined file. All other settings should remain the same, but there is always possibility for a model having a different FVF or something.

here is a bms script that will append the vbuf and ibuf for you

```
append # enable the append mode for concatenating them
log "Vbuf_Ibuf.comb" 0 SIZE
```


run the script and select both files, starting with the ibuf first
that will put the vbuf data first and this will make the vertex startaddr 0x0 in step3 of H2O
the script will generate a new file named Vbuf_Ibuf.comb, this is the file you will open with H2O
all that is left is finding the face index start address and length which should be pie because you can just look into the original ibuf and get the length and see what you need to search for in the Vbuf_Ibuf.comb file for the startaddr.
## Post #34
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-11-07T13:14:44+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Yes, Acewell, I just downloaded the latest version and used the -D option to get it to work 

Thank you, extracting as we speak 

T.
## Post #35
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2015-11-07T15:26:31+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

thanks AceWell!
## Post #36
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-11-08T14:08:12+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Yes it works, here is my piece of (MAX) script I did to import the yoda model, not sure it works on all the models though

NOte, for the YOda model, use the * 30 multiplier, for the cane and lightsabre I used * 100 ( like in the code below )

T.


```
fileVertexBuffer = @"G:\Game Dev\3D Models\tcw_yoda_cane_0.vbuf"

theName = getfilenamefile fileIndexBuffer

/* INDICES */
    size = getFileSize fileIndexBuffer

    nbrIndices = (size) / 2 / 3.0--> 2 bytes per index = short

    ibuf = fopen fileIndexBuffer "rb"

    faces = #()

    nbrVertices = 0

try
(
    for i=1 to nbrIndices do
    (
        a = (readShort ibuf) +1
        b = (readShort ibuf) +1
        c = (readShort ibuf) +1
        
        if ( a > nbrVertices ) then nbrVertices = a
        if ( b > nbrVertices ) then nbrVertices = b
        if ( c > nbrVertices ) then nbrVertices = c
            
        append faces [a,b,c]
    )
)
catch ( PRINT "MOVING ON" )

    fclose ibuf

/* VERTICES */
    size = getFileSize fileVertexBuffer
    
    vertexSize = size / nbrVertices
    
    vertices = #()
    
    vbuf = fopen fileVertexBuffer "rb"
    
    for v=1 to nbrVertices do
    (
        
        x = readFloat vbuf * 100
        y = readFloat vbuf * 100
        z = readFloat vbuf * 100
        
        readFloat vbuf
        
        
        append vertices [x,-z,y]
        
    )

    
    fclose vbuf
    
    theMesh = mesh vertices:vertices faces:faces name:theName


```

[di_yoda.PNG](https://xentaxbackup.github.io/file/9980_di_yoda.PNG)
## Post #37
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-11-08T18:34:57+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Szkaradek released a new import script too for Blender   
[http://zenhax.com/viewtopic.php?p=9429#p9429](http://zenhax.com/viewtopic.php?p=9429#p9429)
## Post #38
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-11-08T21:56:50+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

just implemented this into my own modelviewer, about 85% of the models are acurate 

just by combining the ibuf and vbuf, those that go wrong are the onces with multiple submeshes I guess

T.
[disneyInfinitySS.png](https://xentaxbackup.github.io/file/9983_disneyInfinitySS.png)
## Post #39
- Username: jangoclone
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:52 am
- Post datetime: 2015-11-19T01:32:20+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Hi, when I Run the Puthon Script in Blender says: "python script error: check console" and this is what appears...
[Error.jpg](https://xentaxbackup.github.io/file/10036_Error.jpg)
## Post #40
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-11-19T06:08:39+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

jangoclone   

install 32-bit Python [https://www.python.org/download/releases/2.6.6/](https://www.python.org/download/releases/2.6.6/) and check console (3 line )for "checking for installed Python..."
## Post #41
- Username: jangoclone
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:52 am
- Post datetime: 2015-11-19T17:59:18+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from Szkaradek123
>
> jangoclone   

install 32-bit Python https://www.python.org/download/releases/2.6.6/ and check console (3 line )for "checking for installed Python..."

It Worked great ! ! Thank you...
## Post #42
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-11-28T22:36:42+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Hi guys, made my model viewer downloadable: Download 3D Model Viewer by Taylor Mouse

read all about it on my blog: Taylor Mouse Game Dev Blog

Enjoy

T.
## Post #43
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2015-11-29T11:54:32+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Awesome!!! It's posible add a batch?
## Post #44
- Username: saeba4554
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 04, 2016 8:14 am
- Post datetime: 2016-01-04T00:44:43+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Hello everybody

and thanks for your jobs ^^


can you help to do 2 things ?


1)   I try to extract the TFA models ( the force awakens)  to disney infinity 3.0 on pc 



I already own the playsets on playstation 4, so I can make them appear on the PC version with their codes (on maps figurines) 

but apparently after extract the ibuf/vbuf files, characters and accessories of TFA are not already in the games, and I would not pay for DLC /addon to i have already...

there is a way to i can capture them with ninja ripper or 3D ripper DX or else software (to i don't know) ? (w7 64-bit basic edition in mac bootcamp partition)


2)  after extract model, i don't know how to add her the bones (.oct files) i am really beginner, can you explain how to proced ?


thank you ^^

(french translate to goole and english knowledge)

happy new year ^^
## Post #45
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2016-01-10T20:35:32+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from TaylorMouse
>
> Hi guys, made my model viewer downloadable: Download 3D Model Viewer by Taylor Mouse

read all about it on my blog: Taylor Mouse Game Dev Blog

Enjoy

T.

When i extract only appear for me textures, files .ibuf with models dont appear, why?
## Post #46
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-17T10:20:44+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Anyone know why The Force Awakens models aren't extracting when you use the quickbms script?

I get out Original Trilogy and Clone Wars models but not TFA when clearly they are there cause i used ninjaripper on the demo you get when just downloading the free game off steam and got the models out but the ones i wanted like the First Order Star Destroyer Ninjaripper put the model at like zero on all X,Y and Z and i don't want that cause the hallways and bridge are all at those cords.

Anyways i went back on steam and bought the TFA playset and character pack and re-extracted everything and again it didn't get out TFA stuff only the stuff from the first extract.

So what's going on here does the bms script need updated or something?
## Post #47
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-17T12:45:33+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from JakeGreen
>
> So what's going on here does the bms script need updated or something?
could be, the devs might have caught wind of everyone extracting their stuff and decided to throw a wrench into the thing
## Post #48
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-17T23:34:19+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from AceWell
>
> JakeGreen wrote:So what's going on here does the bms script need updated or something?
could be, the devs might have caught wind of everyone extracting their stuff and decided to throw a wrench into the thing

Well i noticed when batch extracted all the files that be bms script skips i'd say like 20+ files and than dumps like over a half a million of .dat and anno files.
## Post #49
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-01-20T06:21:13+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

would be nice if we worked together to map the 3.0 file system to cut down on guess work. I've spent 3 weeks going file to file and found mostly textures but some useable model files i could convert.  if not that then we need an unpdate to the tools so that we can look inside the files we are extracting to see their file names and know what we are extracting cause right now there is a crap ton files to extract and we are extracting blindly. and that's not okay.
## Post #50
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2016-01-20T11:48:35+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from octaviousrex
>
> would be nice if we worked together to map the 3.0 file system to cut down on guess work. I've spent 3 weeks going file to file and found mostly textures but some useable model files i could convert.  if not that then we need an unpdate to the tools so that we can look inside the files we are extracting to see their file names and know what we are extracting cause right now there is a crap ton files to extract and we are extracting blindly. and that's not okay.

But, are you find any caracter models? Because i didnt find.
## Post #51
- Username: kangaroo78
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Sep 29, 2015 6:24 pm
- Post datetime: 2016-01-21T04:02:16+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

I have found lots of textures that don't have character models, amongst them the TFA. So I don't understand what is going on.
## Post #52
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2016-01-21T15:08:16+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from kangaroo78
>
> I have found lots of textures that don't have character models, amongst them the TFA. So I don't understand what is going on.
I have the same problem.
## Post #53
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-01-23T16:21:01+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

some of the top folders are nothing but textures.  if you skip some of them and keep digging using the quick bms script I promise you'll find the two model files you need to make one model as desribed earlier on in this thread.  I've found jack sparrow but I am sorry I don't remember exactly which file in3.0 I found him in. I also found peices of scenery.

 now from what I've gathered just downloading 3.0 basic won't yeild you the TFA models. you have to purchase the sets...I've read that for 15 bucks you can get all the starwars playsets off ebay but right now my focus is on one of the peices of dlc I bought which is darkwing duck.

 I've tried using a graphic anylizer program that has allowed me to get models from games that were normally locked out. but it crashes the game trying to capture any scene. I've read that some were able to pull models out of the game using ninja ripper but I cannot even get disney infinity to start when I run it through ripper so I don't know what some of these forums are talking about.

 My point, which seemed to go over the forums head, was it would take less time to find models if you could look inside each disney infinity file BEFORE you extract it. right now you have to open quickbms>select script (in this case disney infinity)>choose the file to extract>select the location to extract to. and you have to do this EVERY time for EVERY file. and those who have the downloaded version of pc version of DI should understand how fucking tedious that is. there has to be a way to make a program to look INSIDE the files BEFORE extracting them and be able to look inside the files as easy as one looks into a folder on their desktop not open QBMS>pick script...etc...etc.

 because other wise we working blind. either that or figure out how to take 3d snapshots while playing the game and then get the models we want there. right now it's almost too tedious to be worth the effort. but I've spent real money to gain access to models I've always wanted to ref model. for the time being it's just too tedious for the time I have to put into looking.
## Post #54
- Username: Jimbo13
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 13, 2016 5:47 am
- Post datetime: 2016-03-01T20:02:43+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

So between Ninjaripper & QuickBMS I can find most anything I'm interested within 3.0, that said is there any method for injecting a edited .tbody(dds texture) back in to the game?  This was rather simple in 2.0
## Post #55
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2016-04-26T02:33:05+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Anyway to extract the audio from the game?
## Post #56
- Username: StormBrE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 29, 2016 7:52 pm
- Post datetime: 2016-09-09T06:35:58+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from cra0
>
> Meh bones are in .oct might reverse next week
http://cra0kalo.com/public/Disney%20INF ... ractor.zip

[http://prntscr.com/cfwe55](http://prntscr.com/cfwe55)   not working link to download resources Disney INFINITY Model Extractor. Help share the working link to download the program
## Post #57
- Username: Flandyn
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 12, 2015 9:06 pm
- Post datetime: 2016-09-10T14:06:17+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from StormBrE
>
> cra0 wrote:Meh bones are in .oct might reverse next week
http://cra0kalo.com/public/Disney%20INF ... ractor.zip


http://prntscr.com/cfwe55   not working link to download resources Disney INFINITY Model Extractor. Help share the working link to download the program

Try this: [https://web.archive.org/web/20160706151 ... ractor.zip](https://web.archive.org/web/20160706151140/http://cra0kalo.com/public/Disney%20INFINITY%20Model%20Extractor.zip)
## Post #58
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-09-11T01:39:04+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

I actually just need the stitch texture, can someone help me?
(Stitch from lilo&Stitch)
## Post #59
- Username: xavi64520
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 16, 2016 9:13 pm
- Post datetime: 2016-10-16T13:17:56+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Hi,

Is there someone who has the model of Ahsoka Tano with textures in OBJ format please?
## Post #60
- Username: blckgold
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 18, 2016 3:07 pm
- Post datetime: 2016-10-18T07:31:25+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Would someone be so kind as to help me get these models from the game Luke skywalker, obi wan and Captain America, all from 3.0, Ive been trying for the whole night to work out how to do this, but I can't even get the game installed on my PC. im running into so many issues.

I'm open to finding some sort of trade I have most of the characters from 2.0 as OBJ files already.

Any help is much appreciated.
## Post #61
- Username: csjirt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 25, 2016 12:48 am
- Post datetime: 2016-11-24T17:21:44+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from cra0
>
> Meh bones are in .oct might reverse next week

Code: Select all//Disney Infinity Research
// Cra0kalo/Mariokart64n/Luxox_18
//PC Little Endian


struct VBufHeader
{
// NOP
}

//ShaderDump VertexStructure

struct GPU_ASM
{
    vs_3_0
    def c0, 4, 1, 0, 1000
    def c1, 0.00100000005, 0, 0, 0
    dcl_blendindices v0
    dcl_blendweight v1
    dcl_normal v2
    dcl_position v3
    dcl_texcoord1 v4
    dcl_texcoord v5
    dcl_texcoord o0.xyz
    dcl_position o1
    dcl_texcoord1 o2
    dcl_texcoord2 o3.xy
    slt r0, v0, -v0
}

// Buffer
// Size 24
struct VBufStruc
{
float vd x
float vd y
float vd z
hfloat TextureU
hfloat TextureV
uint32 unknownPadding
uint32 VertexColor
}


// Buffer
// Stride 16
struct VBufStruc2
{
hfloat vn_x
hfloat vn_y
hfloat vn_z
hfloat vn_w

hfloat vt_x
hfloat vt_y
hfloat vt_z
hfloat vt_w


}



// Index Buffer
// Size 24
struct IndexBufStruc
{
uint16 face1
uint16 face2
uint16 face3
}





DL
http://cra0kalo.com/public/Disney%20INF ... ractor.zip


Download address can not be used Who can provide a new?
## Post #62
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-24T17:43:19+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

[viewtopic.php?p=122391#p122391](http://forum.xentax.com/viewtopic.php?p=122391#p122391)
## Post #63
- Username: csjirt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 25, 2016 12:48 am
- Post datetime: 2016-11-26T10:13:08+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from AceWell
>
> viewtopic.php?p=122391#p122391

   think you
## Post #64
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2016-12-11T07:45:34+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from AceWell
>
> That was from a sample uploaded by jmgg on ZenHAX, the bms script by aluigi to extract the files is here
http://aluigi.altervista.org/bms/disney_infinity.bms
With new gold edition of the game we visualize all content in folders! the problem is all the psx_*.zip files extract in *dat format. It may be necessary to update the bms script. Someone can take a look at this?
## Post #65
- Username: gemini82
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 08, 2017 10:22 am
- Post datetime: 2018-03-24T00:10:45+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Model Extractor for Disney Infinity.

[https://archive.org/details/DisneyINFIN ... lExtractor](https://archive.org/details/DisneyINFINITYModelExtractor)
## Post #66
- Username: DiMickfoxed65
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Feb 13, 2020 12:41 pm
- Post datetime: 2020-02-19T17:09:07+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Hello, i need help with these tool because i tryed to port mickey mouse (3.0) but only appears the model broken, so somebody can help me??
i need to port other models too!!!
[Fuckx2.png](https://xentaxbackup.github.io/file/17517_Fuckx2.png)
## Post #67
- Username: DiMickfoxed65
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Feb 13, 2020 12:41 pm
- Post datetime: 2020-02-19T17:16:00+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

And if someone want know what as the models i trying port, here is all the Zip crypted files:
[https://drive.google.com/file/d/161pFiD ... sp=sharing](https://drive.google.com/file/d/161pFiDcfrR5UwAghJa4PwOcFrdu3xn_-/view?usp=sharing)
## Post #68
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-19T22:07:43+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Where did u get the tbx_classicmickey_0.ibuf from? (It's not in the zip file you've uploaded, afaics.)

Anyways, the problem seems to be the endianness, I assume.

There's other ways to get the meshes from vbuf/ibuf files: using hex2obj or the blender script (Blender249[DisneyInfinity][PS3][oct][2014-11-30]) from Mariusz Szkaradek (which uses .oct files).
The script is for PS3 (big endian) which I couldn't fully modify for little endian:
.



oct,vBuf,iBuf.png (115.05 KiB) Viewed 173 times
## Post #69
- Username: DiMickfoxed65
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Feb 13, 2020 12:41 pm
- Post datetime: 2020-02-21T21:42:05+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Im get it from Disney Infinity 3.0 (Gold edition) Cracked :v
And i tryed use HextoObj, but is very hard 

and u can convert these mickey, well because u know how use these tool?
## Post #70
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-21T22:22:11+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

> Reply from Diego6mick ↑Sat Feb 22, 2020 5:42 am at Sat Feb 22, 2020 5:42 am
>
> And i tryed use HextoObj, but is very hardSome people say so, yes.

But the vBuf/iBuf thingie is very simple, afair. Upload tbx_classicmickey_0.vbuf and tbx_classicmickey_0.ibuf, then I can show how to solve this.
## Post #71
- Username: DiMickfoxed65
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Feb 13, 2020 12:41 pm
- Post datetime: 2020-02-22T04:06:18+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Hey, i send you a private message, you are already read it??
## Post #72
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-22T21:15:52+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

yes, thanks!  
well, the truth is, seems things (vbuf/ibuf) are not as simple as I remembered from here:

> Reply from shakotay2 ↑Sun Jun 23, 2019 3:15 am at Sun Jun 23, 2019 3:15 am
>
> 
(in fact, I didn't remember, it was some kind of "deja vue", so I just searched for "copy /b"  )

I got a damxxd point cloud only.
So I sticked back to Mariusz' blender script for getting the skeleton (and maybe more, some day  ):
.



classic_Mickey_skel.png (65.73 KiB) Viewed 134 times
## Post #73
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-23T12:15:18+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

another try with hex2obj (had to extract "magic table" values from the .oct file for such):
.



classicmickey_no_uvs.jpg (134.51 KiB) Viewed 122 times
## Post #74
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2020-03-07T12:41:50+00:00
- Post Title: Re: [REL] Disney INFINITY Model Extractor

Any luck with 3.0? Would like to extract the Arendelle Racing Rink from it if possible.
