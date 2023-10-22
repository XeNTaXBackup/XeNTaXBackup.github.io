## Post #1
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-01T10:34:25+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

Hi,

I'm trying to extract the 3D models from Silver (1999) by Spiral House. It is a 2.5D RPG with prerendered backgrounds and low poly 3D models. I've already been able to extract the game backgrounds, sound fx and most of the sprites so I guess it shouldn't be too complicated aswell. It seems each model is a .CHR file and has a .ANM file when it has an animation. If it can help, the .CHR header always begins like this:

00 80 00 00 XX XX XX XX
where X's are file size in bytes.

I've uploaded 3 models that should be simple enough, and 3 unrelated animation files. Can anyone help with these please?
Here are the files: [http://nerd.perso.sfr.fr/silver/](http://nerd.perso.sfr.fr/silver/)

Thank you !
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-02T09:12:21+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

LOVED THAT GAME, I even bought it recently from GOG.COM !

Btw, what did you use to get these backgrounds and sounds?

I'll take a look at the models this evening

T.
## Post #3
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-02T10:20:53+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

Hi T. Mouse & thx for quick reply 

Yes that game was my very first RPG, have really fond memories of it  the music was really good too. There seems to be three different versions: the regular one with a silver folder on each CD that contains the folders 'chars', 'levels', 'sprites' and 'sound'; the US version in which the silver folder only contains fat1.nob/fat2.nob and data1.nob/data2.nob; and the GOG version which is similar to the first version except that the silver folder from the CDs is copied in the Program Files\GOG.com\silver\data folder. The sound fx are mostly in the sound folder, and the 2D backgrounds are in the .PAK files in the 'levels' subfolders. Those PAK files must be deRNC'd first and then at the start of the file there's a 256color palette + pixel data after that. I suspect the rest of the .PAK contains collision (perhaps a 3d invisible mesh of the background)/z-index information (the game is 2.5D, so there are static backgrounds but you could still go behind/in front of certain parts of the backgrounds and collide with them (eg. David's house below). I can clean up my little extractor's code and send it to you if you're interested (can split silver's fat/nob files, extract .RAW images (for the menu background and world map), level backgrounds and about 75% of the static 2D sprites (rest seem to be animated sprites that I've not yet been able to understand the format   )  ?
## Post #4
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-10T17:12:42+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

Sry to bump but has anyone had a look at those CHRs? Does anyone know how they are structured?
## Post #5
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-19T16:20:05+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

edited, found something interesting
## Post #6
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-24T23:15:36+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

While browsing the game archive again I've found a "anims/SHAPES" directory I didn't see at first. It contains 67 *.AS files eg "SH2224.AS" and sometimes the .AS file has a .S3D file with it. The .AS files are plain text, here's SH2224.AS:

```
Named object: "LCalf"
Tri-mesh, Vertices: 11     Faces: 14
Mapped
Vertex list:
Vertex 0:  X:12     Y:-6.999949     Z:69.999977     U:0.498397     V:0.49062
Vertex 1:  X:22     Y:3.000033     Z:69.999977     U:0.811542     V:0.49062
Vertex 2:  X:12     Y:13.000027     Z:69.999977     U:0.498397     V:0.49062
Vertex 3:  X:2     Y:3.000033     Z:69.999977     U:0.185253     V:0.49062
Vertex 4:  X:12     Y:-6.999982     Z:18.000586     U:0.498397     V:0.008954
Vertex 5:  X:20     Y:1.000015     Z:17.999973     U:0.748913     V:0.008951
Vertex 6:  X:12     Y:9.000015     Z:17.999969     U:0.498397     V:0.008951
Vertex 7:  X:4     Y:1.000015     Z:17.999973     U:0.247882     V:0.008951
Vertex 8:  X:28     Y:9.000024     Z:56.999969     U:0.999429     V:0.370203
Vertex 9:  X:-4     Y:9.000024     Z:56.999969     U:-0.002634     V:0.370203
Vertex 10:  X:12     Y:25.000029     Z:56.999966     U:0.498397     V:0.370203
Face list:
Face 0:    A:4 B:5 C:8 AB:1 BC:1 CA:0
Material:"DVD LEG F"
Smoothing:  2
Face 1:    A:0 B:8 C:1 AB:0 BC:1 CA:1
Material:"DVD LEG F"
Smoothing:  2
Face 2:    A:8 B:5 C:6 AB:1 BC:1 CA:0
Material:"DVD LEG K"
Smoothing:  1
Face 3:    A:1 B:10 C:2 AB:0 BC:1 CA:1
Material:"DVD LEG K"
Smoothing:  1
Face 4:    A:10 B:6 C:7 AB:1 BC:1 CA:0
Material:"DVD LEG K"
Smoothing:  1
Face 5:    A:2 B:9 C:3 AB:0 BC:1 CA:1
Material:"DVD LEG K"
Smoothing:  1
Face 6:    A:9 B:7 C:4 AB:1 BC:1 CA:0
Material:"DVD LEG F"
Smoothing:  2
Face 7:    A:0 B:3 C:9 AB:1 BC:1 CA:0
Material:"DVD LEG F"
Smoothing:  2
Face 8:    A:8 B:0 C:4 AB:0 BC:1 CA:0
Material:"DVD LEG F"
Smoothing:  2
Face 9:    A:8 B:6 C:10 AB:0 BC:1 CA:1
Material:"DVD LEG K"
Smoothing:  1
Face 10:    A:9 B:2 C:10 AB:0 BC:1 CA:1
Material:"DVD LEG K"
Smoothing:  1
Face 11:    A:9 B:4 C:0 AB:0 BC:1 CA:0
Material:"DVD LEG F"
Smoothing:  2
Face 12:    A:10 B:1 C:8 AB:0 BC:1 CA:1
Material:"DVD LEG K"
Smoothing:  1
Face 13:    A:10 B:7 C:9 AB:0 BC:1 CA:1
Material:"DVD LEG K"
Smoothing:  1
```


There is no mention of ".AS" in the disassembled exe, so I'm assuming those .AS files are leftover which werent meant to be included in the game archive (which would explain why it starts at SH2224 and there are only 67 of those) ? I'm not familiar with 3d model animation formats, but has anyone seen this kind of plain text file before?

EDIT: Also I think "DVD" stands for DAVID, which is the main character in the game, and it seems every .AS file contains part of david's model (DVD_LEG, DVD_HILT, DVD_FOOT etc). Could those .AS be the unpacked david model by any chance?
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-26T11:21:16+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

Did you convert it to a model ?

T.
[silver.PNG](https://xentaxbackup.github.io/file/6957_silver.PNG)
## Post #8
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-26T12:23:53+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

yeah, theyre 3D Studio .ASC files, also they're not in the later dreamcast version, I think they included it by mistake (there's only david's .AS files and a bunch of .S3D, there's also a .bat there that probably wasn't meant to be included either   . Taking a look at the 3DS chunk-based format, it seems that the .CHR also has 'chunks' eg if you look up david.chr ( [http://nerd.perso.sfr.fr/silver/david.chr](http://nerd.perso.sfr.fr/silver/david.chr) ), there seems to be chunks of floats at offsets 196, 984 1764 etc, which I believe are all part of david's model (head, foot etc, each chunk corresponding to a .AS file). But so far I've failed to recognize the vertices from the .AS in david.chr (don't know much about 3d models, but they could be scaled ?). I've uploaded all the .AS and .S3D in a zip file here if you'd like to take a look: [http://nerd.perso.sfr.fr/silver/SHAPES.zip](http://nerd.perso.sfr.fr/silver/SHAPES.zip)
I think we're making progress
## Post #9
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-26T18:44:08+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

ok, I've confirmed the first floats in the float array are the vertices, I've plotted the vertices from CHEESE.CHR (see attachment). The remaining floats in the chunk must be the UV. Now on to find faces  
edit: also found vertice count
[s.png](https://xentaxbackup.github.io/file/6959_s.png)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-29T00:33:39+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

> Reply from nerdyluke
>
> edit: also found vertice countHow do you think someone could help you if you don't give the details, eh?
So this
# 0xa4: verts= 10
v 0.000000 0.000015 -48.600006 
v 40.500000 -0.000015 32.399994 
v 16.199997 -0.000015 40.500000 
v -16.199997 -0.000015 40.500000 
v -40.500000 -0.000015 32.399994 
v 0.000000 51.840012 -48.599991 
v 40.500000 51.839996 32.400009 
v 16.199997 51.839996 40.500000 
v -16.199997 51.839981 40.500000 
v -40.500000 51.839981 32.400009 
f 2 7 6
f 3 8 7
f 4 9 8
f 5 10 9
f 1 6 10
f 7 8 9
f 5 4 3

doesn't give a perfect cheese; some faces missing and I'm not sure of the vertices start address.
## Post #11
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-29T05:50:26+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

Thanks Shakotay, I've also been frustrated by face count but I think they're not triangles, they seem to be polygons, because if you start at offset 367, you have this structure:

```
(8 bytes ??) 1 0 34 0 2 0 34 0 7 0 34 0 6 0 34 0
(8 bytes ??) 2 0 34 0 3 0 35 0 8 0 35 0 7 0 34 0
(8 bytes ??) 3 0 35 0 4 0 35 0 9 0 35 0 8 0 35 0
(8 bytes ??) 4 0 34 0 0 0 34 0 5 0 34 0 9 0 34 0
(8 bytes ??) 5 0 34 0 6 0 34 0 7 0 34 0 8 0 34 0 9 0 34 0
(8 bytes ??) 0 0 33 0 4 0 33 0 3 0 33 0 2 0 33 0 1 0 33 0
```


now if you take the 0th, 4th, 8th and 12th number on each line you get this for polygons:

```
1 2 7 6
2 3 8 7
3 4 9 8
4 0 5 9
5 6 7 8 9
0 4 3 2 1
```


which gives you a perfect cheese. But it looks kind of weird, is it common to store faces that way? (it's an old game after all)
## Post #12
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-29T07:36:16+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

because they are probably not stored by line;

0 1 6 5
1 2 7 6
2 3 8 7
3 4 9 8
4 0 5 9
5 0 7 0 0
0 4 3 2 1

but like this
0 1 6 
5 1 2 
7 6 2 
3 8 7
3 4 9 
8 4 0 
5 9 5 
0 7 0 
0 0 4 
3 2 1

although the  0 0 4 and  0 7 0 look pretty weird :/

T.
## Post #13
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-01-31T08:20:12+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

edit: nvm I made a mistake in my previous post, corrected it, I'll try out your suggestion TaylorMouse
## Post #14
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-02-03T18:06:46+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

Okay, I spent the last weekend studying the format and here are my notes:

```

20							long					N
32 + N						long					# of chunks (model parts) in this file
44 + N						long					first chunk size in bytes (add 8 bytes to include up to this byte)
60 + N						long					first chunk vertice count (V)
64 + N						long					first chunk polygon count (P, seems to be repeated twice)
80 + N						float[3]				origin (center of mesh ?)
156 + N						float[3 * V]			vertices
156 + N + 12 * V			float[3 * P]			normals
156 + N + 12 * (V + P)		(struct polygon)[P]		byte ??, byte polygon index, byte # of vertices in polygon, byte ??, long ??, in the following bytes one byte out of 4 is the vertex index

```

I've written a little extractor that follows those specs, and this is what I've come up with so far (APPLE.CHR, CHEESE.CHR and TREASURE.CHR). As you can see, the first two models are fine, but the parts making up the chest are misplaced. It seems to be the case for all models that contain independently animated meshes (the apple and cheese have an animation, but it moves the entire apple, whereas with the chest, only the cover moves. And it is the same for characters (David, Fuge etc)).

Here are the generated .obj making up the parts of TREASURE.CHR:

Box:

```
v 65.000000 0.000000 40.000137
v -65.000000 0.000000 40.000137
v -65.000000 -0.000015 -40.000122
v 65.000000 -0.000015 -40.000122
v 75.000000 80.000000 50.000061
v -75.000000 80.000000 50.000061
v -75.000000 80.000107 -50.000046
v 75.000000 80.000107 -50.000046
#faces
f 1 4 3 2
f 7 8 5 6
f 8 4 1 5
f 5 1 2 6
f 6 2 3 7
f 7 3 4 8

```


Cover:

```
v -75.000000 0.000000 99.999985
v -75.000000 -0.000031 -0.000015
v -75.000000 35.000015 15.000000
v -75.000000 50.000000 49.999954
v -75.000000 35.000000 85.000000
v -75.000000 -0.000000 50.000000
v 75.000000 0.000000 99.999985
v 75.000000 35.000000 85.000000
v 75.000000 -0.000031 -0.000015
v 75.000000 35.000015 15.000000
v 75.000000 50.000000 49.999954
v 75.000000 -0.000000 50.000000
#faces
f 6 2 3 4 5 1
f 8 7 1 5
f 9 10 3 2
f 8 11 10 9 12 7
f 11 8 5 4
f 10 11 4 3
f 2 1 7 9

```


lock:

```
v 10.000000 0.000000 -0.000000
v -10.000000 0.000000 -0.000000
v -15.000000 -24.999969 -0.000000
v 7.000000 -39.999969 -0.000000
v 15.000000 -24.999969 -0.000000
v -7.000000 -39.999985 -0.000000
#faces
f 5 4 6 3 2 1

```


Also I've found three sets of floats after the textures (at the end of the .CHR) which I believe are somehow responsible for positionning the parts because each of them is prefixed with a (part?) index (0-2):

```
0 80  -50
0 0  100

```

I've tried lots of combinations but I can't get the parts to be placed properly (cover over box, lock next to the box etc)

For the textures, I've confirmed they're included in the CHR file towards the end (there's a big section with bytes corresponding to what I've extracted using the PIX debugger, will work on that asap).
[apple.PNG](https://xentaxbackup.github.io/file/6993_apple.PNG)
## Post #15
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-02-04T05:58:14+00:00
- Post Title: Silver 3d models and animations (CHR and ANM files)

I've confirmed my assumptions that the floats towards the end are used for placement of the parts by replacing each of those floats by 0 and looking at how the game reacts. With all floats at 0, the chest parts are misplaced. Now it's only a matter of figuring out how those coordinates are used.
[screen.png](https://xentaxbackup.github.io/file/6994_screen.png)
## Post #16
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-02-12T22:34:26+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Does the treasure chest animate ?
If so, maybe there is a reference to a bone or something, so that the cover of the chest is placed relevant to that position.

Btw, nice progress

T
## Post #17
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-02-22T16:46:53+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Yes, the chest has an animation. Idont know anything about bones however... do u know some tut that explains what it is and/or what to look for when reversing them? Its so annoying to be so close and still not be able to understand how the damn format works. Actually the section I do not understand has indices that seem to be mesh indices and those are followed by floats, does that sound like bone structure to you?

Also there seems to be a structure, the section always goes like this:

```
<mesh index> <float x> <float y> <float z>
<mesh index> <float x> <float y> <float z>
...
```


And judging from the order of the indices I'm guessing there is hierarchy in the order they appear.

Also sometimes there's just that and sometimes there's a "FF FF FF FF" separator and then another section. like this for example:

```
<mesh index> <float x> <float y> <float z>
<mesh index> <float x> <float y> <float z>
...
FF FF FF FF
<mesh index> <float x> <float y> <float z> // Sometimes the mesh index has already been mentioned earlier in the section, which is strange
<mesh index> <float x> <float y> <float z>
<mesh index> <float x> <float y> <float z>
...
```


Btw ill be on vacation soon so ill have more time to look into this
## Post #18
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-02-24T22:05:16+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

I think the MeshIndex x y z refers to bones?

T.
## Post #19
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-02-26T17:39:45+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

> Reply from TaylorMouse
>
> I think the MeshIndex x y z refers to bones?

T.
ty for help. Btw sry for my ignorance but is bone description alone sufficient to place the cover over the chest or eg a foot at the end of a leg?
## Post #20
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-02-26T20:09:21+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

probably not, you should have some vertex weights somewhere, with an index to one or more bones, probably a fixed number of bones but not more than 4


T.
## Post #21
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-02-27T11:40:36+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

I have a very weak 3d background, but is what you're telling me related to this [http://www.misfitcode.com/misfitmodel3d ... tails.html](http://www.misfitcode.com/misfitmodel3d/olh_jointdetails.html) ?

> A bone joint is is an object that forms one part of a model's skeletal structure. The root bone joint has no parent joint, all other joints have one parent. A parent joint may have multiple children.
>
> 
>
> Vertices and points may be attached to bone joints to control their movements during skeletal animations. When a vertex or point's movement is controlled by a bone joint, the bone joint is said to be an "influence". Vertices and points may have up to four influences.

I have trouble finding a simple explanation about bones/joints and how they work
## Post #22
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-03-01T23:56:29+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Continuing research... I've tidied up my (incomplete) CHR specification if anyone wants to have a look at the format.

```

0x8000: Root chunk
	+4   long   chunk size
	
	0x18000: unknown purpose chunk
		+4   long   chunk size

		0x7f01: unknown purpose chunk
			+4    long      chunk size
			+8    long      N
			+12   long[N]   unknown long array

		0x7f03: Model chunk (contains submeshes)
			+4    long   chunk size
			+8    long   submesh count
			+12   long   model ID (first submesh ID)
			
			0x7f02: Submesh
				+4                      long                   chunk size
				+8                      long                   1
				+12                     long                   submesh ID
				+16                     long                   0
				+20                     long                   vertice count VC
				+24                     long                   polygon count PC
				+28                     long                   PC again ?
				+32                     long                   unknown
				+36                     long                   unknown
				+40                     float[3]               submesh center
				+52                     char[64]               unknown (sometimes contains a string eg. "amera02" or "C:\3DS4")
				+116                    float[3 * VC]          vertices
				+116 + 12 * VC          float[3 * PC]          normals
				+116 + 12 * (VC + PC)   (struct polygon)[PC]   {char unknown, char polygonIndex, char pVerticeCount, char unknown, long unknown, (long vertexIndex, long unknown, long unknown, long unknown) * pVerticeCount}

		0x7f04: Model texture

		0x7f05: Bones ?
			+4    long         chunk size
			+8    long         unknown
			+12   long         unknown
			+16   byte[4]      0
			+32   (struct)[]   {long index, float x, float y, float z}, the structs are sometimes interleaved with FF FF FF FF and 12 null bytes inbetween...
			
		0x7f06: unknown purpose chunk (seems to be groups of submeshes)


```
## Post #23
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-03-04T19:38:27+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

I'm trying to understand the 057f and 067f sections and things are getting very tricky   . For TREASURE.CHR it's quite simple:

TREASURE.CHR, 057f:

```
1: 0, 80, -50
2: 0, 0, 100

```

and the 067f:

```
3578
3577

```

The values above are submesh IDs, when offsetting the submeshes in this order, relative to the previous submesh (ie 3576 offset with (0, 0, 0), 3578 offset with (0, 80, -50) and 3577 offset with (0, 80, 50)) then the cover and the lock are placed perfectly. But when looking at BAT.CHR things are not as easy:

BAT.CHR, 057f:

```
1 :  0      0.3     -0.7
2 :  0      0.17    32.5
3 :  0      0       7.6
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
2 :  13.5   -0.22   -1.7
24:  21     0.1     16.1
2 :  -12.3  -0.3    -2
26:  -22    0.6     17.2
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
-1:  0      0       0
25:  28.7   0.1     7.75
27:  -28.5  -0.35   6.6

```

and the 067f:

```
19 * null
11873
11872
11869
11868
16 * null
11870, 11871
11866, 11867

```


I'm not even posting the values for DAVID.CHR because it's even messier... I don't think this structure looks like a bone matrix    has anyone seen something like this in another format ? Looks like somekind of C array since there are sizes before both sections but I just can't make sense of it because the indexes don't make sense, apart from the fact that contiguous indexes (24,25,26 etc) seem to have to do with parenting... Halp please
## Post #24
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-06-08T17:27:10+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Gave it another shot today, been focusing on UVs. I know where they are and I have these UVs for the face of the "inside" of the chest:

```
D0 C6 3B 00 7A 1C 00 00 
D0 C6 3B 00 68 E3 1D 00 
F4 38 00 00 68 E3 1D 00
```

I've also managed to extract the texture:



Now from this texture, the real coords should be something like this (the order may be wrong but the numbers are the correct ones):

```
160,0
160,30
100,30
```

Now does anyone know how to convert the ints I've found to the real coords? thx
## Post #25
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-06-08T20:18:56+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

absolute pixel coordinate, mate!
## Post #26
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-06-08T21:35:10+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

> Reply from fatduck
>
> absolute pixel coordinate, mate!
I'm not sure I understand what you mean:

F4 38 00 00 7A 1C 00 00 = 14580, 7290
D0 C6 3B 00 7A 1C 00 00 = 3917520, 7290

How do I get to 100, 0 and 160, 0 from there ? its not even proporsional
## Post #27
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-06-09T10:55:00+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

He means that the values you got are absolute pixel coordinates, meaning that you need to convert them to uv coordinates

ex. If the texture is 256 wide, and you pixel coordinate is 160 then the uv coordinate is 160/256 = 0,625

T.
## Post #28
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-06-09T11:13:06+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

> Reply from TaylorMouse
>
> He means that the values you got are absolute pixel coordinates, meaning that you need to convert them to uv coordinates

ex. If the texture is 256 wide, and you pixel coordinate is 160 then the uv coordinate is 160/256 = 0,625

T.
yes sure I understand that, but the values I posted (100, 0; 160, 0 etc) are the pixel values I SHOULD find, but the corresponding values in the CHR are 14580, 7290; 3917520, 7290 etc and I don't know how to convert those to absolute pixel coords. Sorry if I'm missing something here but I can't find how to do that
## Post #29
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-06-12T19:18:56+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Ah, ok, I think that we both misunderstood you.

What makes you think that the data should point to the texture coordinates?

T.
## Post #30
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-06-14T11:48:58+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

nvm
## Post #31
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-08-26T10:26:57+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Hey,
Months of hard work seem to have finally paid off 








I'll upload a model viewer/extractor when I have time
## Post #32
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-09-03T21:54:40+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

For the interested, I'm close to release, here are screenshots:





This program can view/export: CHRs (3d models), PAK files (contain level backgrounds), SPR (sprites), RAW (some images like the map) and SMK videos
## Post #33
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-09-05T10:53:47+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

OMG OMG OMG !!!!

You did it dude!!

SUPER, can't wait to check it out!!

Make sure there is an export button :p

T.
## Post #34
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-09-05T21:15:55+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

> Reply from TaylorMouse
>
> OMG OMG OMG !!!!

You did it dude!!

SUPER, can't wait to check it out!!

Make sure there is an export button :p

T.
Thanks, finishing it up will upload soon.
There's no button but ctrl-S exports to obj so no worries ^^, one thing though their format is very unconventional and doesn't really use bones so no bones unfortunately
## Post #35
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-09-09T12:30:30+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

And here it is: https://silvie.googlecode.com/svn/trunk/silvie.jar   

You need Java8 which you can get from http://www.oracle.com/technetwork/java/ ... 33155.html
and Java3D from https://java3d.java.net/binary-builds.html

Project page: https://code.google.com/p/silvie/
Code is under GPLv3 so anyone can modify it.


EDIT: new project URL (no Java required) : https://github.com/othias/silvie
## Post #36
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-09-14T08:48:50+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Has anyone tested this on windows please? I dont have access to a windows box and would like to be sure
## Post #37
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-10-05T11:27:24+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Okay, I just tested it myself on windows and if anyone's interested, run it that way to be able to view the CHRs:

```
java -Djava.library.path=<path to java3d dll> -jar silvie.jar
```
## Post #38
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-10-11T13:40:50+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Fixed a bunch of bugs in rev8, plz redownload.
I'll try to work on the .ENG format (dialog files) when I have some time, anyone wants to help?
## Post #39
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-10-17T21:11:12+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Can you share the code ? cause I don't want make my pc dirty and install Java 

T.
## Post #40
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2014-10-22T18:31:18+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Like I said in an earlier post, code is under gplv3 on the project's github https://github.com/nerdouille/silvie (just moved)

My knowledge of java is by no means perfect so if you want to improve stuff you're perfectly welcome  

EDIT: new project URL (no Java required) : https://github.com/othias/silvie
## Post #41
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2015-06-09T15:55:36+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Not that it has anything to do with 3d models but I've reversed the dialog files aswell (view+export as .txt) :p
[dialog.png](https://xentaxbackup.github.io/file/9284_dialog.png)
## Post #42
- Username: GlassFuge
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 16, 2016 6:21 am
- Post datetime: 2016-09-15T22:44:36+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Hello

first of all sorry for necroposting, i know this thread is 1 year old, but finally i found what i was looking for. I always wanted to export some of the models, sprites, and images of this game. Unfortunatley i didnt undestand how to do so. My knowlege of coding is below 0.  There is a chance you can make an .exe file for windows? Or explain how to make the program work with a step by step giude?

Thank you


P.S. Nice work, you made one of my dream come true!
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-16T08:38:24+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Java is required and you need to install Java3D in case you didn't so far from [https://java3d.java.net/binary-builds.html](https://java3d.java.net/binary-builds.html)
You need nerdyluke's silvie.jar, then in windows console enter
java -Djava.library.path=<path to j3dcore-ogl.dll> -jar silvie.jar

where you must replace <...> by D:\Java3D\bin for example. 

D:\JAVA3D is MY path, so your's will be different. (And don't enter the <>.  )

(For 64-bit windows j3d-1_5_2-windows-amd64.zip is required, even for intel processors.)



turtle.jpg (54.1 KiB) Viewed 47 times



well, I see, nerdyluke explained most of this before.

Seems you didn't READ this thread, did you?
## Post #44
- Username: GlassFuge
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 16, 2016 6:21 am
- Post datetime: 2016-09-16T14:21:25+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Thank you for the reply, i read the posts but i never used java before so was a bit difficult to understand, at the end i managed to open the program  

Thank you
[opndnslvr.png](https://xentaxbackup.github.io/file/11714_opndnslvr.png)
## Post #45
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2018-03-02T09:50:06+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

I am currently in the process of rewriting it entirely in C with clear struct definitions for each format for future reference, should be done in a week or two. I have also managed to get nodes working properly for models, which means animations are now possible! The new tool exports models to .3ds so you can open them in the free version of 3ds max 5 from discreet. Also there will only be a single statically linked executable so no more java hassle.
## Post #46
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2018-08-08T18:58:43+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Done ! Sorry it took slightly longer than expected. Here is the new github url: [https://github.com/othias/silvie](https://github.com/othias/silvie)

Any further contribution is more than welcome.

I've uploaded a binary release as well so just a simple executable, no more java or other library is required. And here's a pretty cool screenshot of the robot boar boss at the end of the game for fun 
[Rend.png](https://xentaxbackup.github.io/file/14719_Rend.png)
## Post #47
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2022-01-09T03:05:41+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

> Reply from nerdyluke ↑Thu Aug 09, 2018 2:58 am at Thu Aug 09, 2018 2:58 am
>
> 
Done ! Sorry it took slightly longer than expected. Here is the new github url: https://github.com/othias/silvie

Any further contribution is more than welcome.

I've uploaded a binary release as well so just a simple executable, no more java or other library is required. And here's a pretty cool screenshot of the robot boar boss at the end of the game for fun

Hey, nerdyluke.

Any possibility in making the tool compress the xml back to eng?
Cheers.
## Post #48
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2022-04-11T20:12:57+00:00
- Post Title: Re: Silver 3d models and animations (CHR and ANM files)

Hello, it's been a while  a few people have messaged me over the last few years about this tool so here's an update. Due to lack of motivation/personal issues I haven't worked on this as much as I would have liked, but I might give it a shot in the near future. My dream goal would be to extract 3d model animations, "level" (terrain) meshes, and understand the scripting of levels. Then once this is done, a reimplementation of the game à la openmw or gemrb would be doable. But it's all wishful thinking for now   

xml->eng conversion might be possible, although there are still quite a few unknowns in the format. I'll add the feature if I can get it to work, maybe   . Thanks all for your kind words.
