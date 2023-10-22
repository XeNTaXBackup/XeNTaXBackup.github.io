## Post #1
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-04T10:45:30+00:00
- Post Title: Witcher Wild Hunt (request)

I try extract 3d models from Witcher Wild Hunt. Sources (*.bundle, *.cache) been unpack with QuickBMS script.
As simple example i use model of Ciri's sword. It seems 3d model consist of a few files.
*.w2ent - base record  about of type model. Has link to *.w2mesh
*.w2mesh - header of model and some data. Has link to *.w2mesh.X.buffer and *.xbm
*.w2mesh.X.buffer - data of models. Perhaps it is data about vertex, uv and face array.
But file has strange data. This is not correct float or double values. I don't can understand what is this. May be specific format, compressed or encoding data etc.
*.xbm - some data about textures.

Can anybody help me with it?
[ciri_sword.zip](https://xentaxbackup.github.io/file/9256_ciri_sword.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-04T12:39:06+00:00
- Post Title: Witcher Wild Hunt (request)

looks like another tedious task
this is a point cloud I got:



sword__ciri.JPG (17.34 KiB) Viewed 556 times

(From the face indices I guess there might be 6 submeshes, but not sure about that.)
## Post #3
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-04T15:29:09+00:00
- Post Title: Witcher Wild Hunt (request)

Ok, thank you. Look like as correct UV coordinates.
 This is hex2obj?
Can you show config of the tools?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-04T17:55:04+00:00
- Post Title: Witcher Wild Hunt (request)

> Reply from erik945
>
> Ok, thank you. Look like as correct UV coordinates.why do you think so?
This is some xbm:



sword__ciri_a01-2AA.JPG (41.52 KiB) Viewed 535 times



> This is hex2obj?
>
> Can you show config of the tools?
just a wild guess: H2O file, point cloud
0x0 1
Vb0
0x8
0x3CC0 972
020200
0x8 255
## Post #5
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-04T18:24:49+00:00
- Post Title: Witcher Wild Hunt (request)

I don't know. Just look similar. You read this array with offset  0x3CC0, right? What format? half-float?
I think xbm is very lov resolution textures.  Full resolution textures unpack too, but without names and directory structures.This hodge-podge.

upd, yes half-float. Lenght of array is around 1944 vertex (0x3CC0 - 0x5b20).
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-04T20:42:57+00:00
- Post Title: Witcher Wild Hunt (request)

this looks interesting (from the wireframe there seem to be parts of a sword):



notAsword.JPG (42.34 KiB) Viewed 522 times
## Post #7
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-04T22:25:02+00:00
- Post Title: Witcher Wild Hunt (request)

Yes, you right. This is faces indices. I been right too. First block (0x3CC0 - 0x5b20) - UV coordinates.  
It remains to understand where the coordinates of the vertices in 3D space.

Incidentally, the data blocks is cyclically repeated. Look offset 0xCE80. Maybe it submesh.

upd. first array (0x0 - 0x3CC0), has strange format, but if this is something about vertices, on record is 8 bytes. (8 * 1944 = 15552d = 0x3CC0). Don't know what is it. 
Next submesh start on offset 0x97E0. 0x97e0 - 0x5b20 = 3CC0. another block 8x1944. Don't know where 3d coordinates. Float - does not fit. May be half-float?
[ciri.png](https://xentaxbackup.github.io/file/9261_ciri.png)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-05T08:59:51+00:00
- Post Title: Witcher Wild Hunt (request)

> Reply from erik945
>
> I been right too. First block (0x3CC0 - 0x5b20) - UV coordinates.  
It remains to understand where the coordinates of the vertices in 3D space.great!  
Maybe tell us which face indices u used? Then it might be easier to get the vertices.

These are the supposed face indices blocks:
addr   size................FI count vertex count
1A400 46FE: 18174/2= 9087 -> 1944 verts
1EAFE  666:  1638/2=  819 -> 263
1F164 20A6:  8358/2= 4179 -> 1088
2120A  504:  1284/2=  642 -> 152
2170E  C96:  3222/2= 1611 -> 542
223A4

> Incidentally, the data blocks is cyclically repeated.yup, I know.
For the uvs maybe it's used for multiple texturing?

> Don't know where 3d coordinatesfor me it seems there are parts of the sword in the block from 0x0 to 0x3CBF
## Post #9
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-05T14:30:02+00:00
- Post Title: Witcher Wild Hunt (request)

face indicies has offset (as you say) 0x1A400. 3 * unsignded short int. I find 2850 faces.
(fragment on maxscript)

```
fseek f 0x1A400 #seek_set 	
for j = 1 to 2850 do (
	i1 = (readshort f #unsigned ) + 1
	i2 = (readshort f #unsigned ) + 1
	i3 = (readshort f #unsigned ) + 1 
	append Face_arrays[i1,i2,i3]
	)


```
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-05T15:41:07+00:00
- Post Title: Witcher Wild Hunt (request)

thx! Seems I've a bug with the uv's blocksize in uv preview of hex2obj. 

(so with a VBsize=8 and UVB=4 it skips the 2nd (identical) t-verts what it shouldn't)
## Post #11
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-05T15:46:51+00:00
- Post Title: Witcher Wild Hunt (request)

it happens   
I try find 3d coordinates so far unsuccessfully.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-05T16:13:40+00:00
- Post Title: Witcher Wild Hunt (request)

the mesh is very likely to be found in the block from 0x0 to 0x3CBF. Try shorts, not half floats:



sword.JPG (14.19 KiB) Viewed 472 times

To get rid of the squared structures try subtracting/adding half value of the bounding box values.
(that's how I did it in former versions of hex2obj using the 'cut' feature, iirc)

(some fiddeling will be required, but I'm off for jogging now...)
## Post #13
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-05T18:50:55+00:00
- Post Title: Witcher Wild Hunt (request)

Everything is very simple. This is unsigned short value  
I tried to pick up not standard mantis and exponent... Facepalm...

```
for j = 1 to 1944 do (
	x = readshort f #unsigned
	y = readshort f #unsigned
	z = readshort f #unsigned
	print ("x: " + (x as string) + " 0x" + ((bit.intAsHex(x))as string) + "	||y: " + (y as string) + " 0x" + ((bit.intAsHex(y))as string) + "	||z: " + (z as string) + " 0x" + ((bit.intAsHex(z))as string))
	qq = readshort f
	append vertex_array[x,y,z]
	)

```


```
"x: 32463 0x7ecf	||y: 32747 0x7feb	||z: 65371 0xff5b"
"x: 32655 0x7f8f	||y: 32701 0x7fbd	||z: 65519 0xffef"
"x: 32639 0x7f7f	||y: 32595 0x7f53	||z: 65525 0xfff5"
"x: 32770 0x8002	||y: 32701 0x7fbd	||z: 65528 0xfff8"
"x: 32770 0x8002	||y: 32595 0x7f53	||z: 65535 0xffff"
"x: 32901 0x8085	||y: 32595 0x7f53	||z: 65525 0xfff5"
"x: 32885 0x8075	||y: 32701 0x7fbd	||z: 65519 0xffef"
"x: 33108 0x8154	||y: 32595 0x7f53	||z: 65376 0xff60"
"x: 33078 0x8136	||y: 32747 0x7feb	||z: 65371 0xff5b"
"x: 33108 0x8154	||y: 32595 0x7f53	||z: 65376 0xff60"

```


Model greatly scaled but quite recognizable. It is necessary to find the values ​​of scaling. I think it is in *.w2mesh

upd. scales is rough proportional x: 23; y: 100; z: 690
[ciri2.png](https://xentaxbackup.github.io/file/9265_ciri2.png)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-05T21:08:21+00:00
- Post Title: Witcher Wild Hunt (request)

same result as with hex2obj ver 0.22c, 'cut' on (obsolete):



sword_022c.JPG (39.64 KiB) Viewed 441 times
## Post #15
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-09T21:01:04+00:00
- Post Title: Witcher Wild Hunt (request)

Work with .w2mesh
offset of 0xC77 contain 25-byte records of submesh:
offset vertex coordinates, offset UV, offset unknown datablock (array located after UV array), some unknown bytes and number of submesh's vertex.

```
	b_offset = ftell fm
	vertex_offset_start = readlong fm #unsigned
	uv_offset_start = readlong fm #unsigned
	un1_offset_start = readlong fm #unsigned
	qq2 = readlong fm #unsigned
	qq3 = readlong fm #unsigned
	qq4 = readlong fm #unsigned
	qq5 = readshort fm #unsigned
	number_vertex = readshort fm #unsigned
	qq6 = readlong fm #unsigned
	qq7 = readlong fm #unsigned
	qq8 = readbyte  fm #unsigned	
	print ("b_offset: " + (b_offset as string) + " 0x" + ((bit.intAsHex(b_offset))as string) + "	||vertex_offset_start: " + (vertex_offset_start as string) + " 0x" + ((bit.intAsHex(vertex_offset_start))as string) + "	||uv_offset_start: " + (uv_offset_start as string) + " 0x" + ((bit.intAsHex(uv_offset_start))as string) + "	||un1_offset_start: " + (un1_offset_start as string) + " 0x" + ((bit.intAsHex(un1_offset_start))as string)+ "	||number_vertex: " + (number_vertex as string) + " 0x" + ((bit.intAsHex(number_vertex))as string))
	)

```


result

```
"b_offset: 3228 0xc9c	||vertex_offset_start: 38880 0x97e0	||uv_offset_start: 40992 0xa020	||un1_offset_start: 42048 0xa440	||number_vertex: 263 0x107"
"b_offset: 3265 0xcc1	||vertex_offset_start: 44160 0xac80	||uv_offset_start: 52864 0xce80	||un1_offset_start: 57216 0xdf80	||number_vertex: 1088 0x440"
"b_offset: 3302 0xce6	||vertex_offset_start: 65920 0x10180	||uv_offset_start: 67136 0x10640	||un1_offset_start: 67744 0x108a0	||number_vertex: 152 0x98"
"b_offset: 3339 0xd0b	||vertex_offset_start: 68960 0x10d60	||uv_offset_start: 73296 0x11e50	||un1_offset_start: 75472 0x126d0	||number_vertex: 542 0x21e"
"b_offset: 3376 0xd30	||vertex_offset_start: 79808 0x137c0	||uv_offset_start: 0 0x0	||un1_offset_start: 0 0x0	||number_vertex: 2207 0x89f"

```

Last submesh hasn't uv and unknown array, i check it. May be it is collision or shadowbox or someone other.
## Post #16
- Username: Ladyofpayne
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 03, 2015 3:41 am
- Post datetime: 2015-07-03T04:30:26+00:00
- Post Title: Re: Witcher Wild Hunt (request)

Please can ypu finish the extractor? We, Witcher fans, need to extract models for Xnlalra to make pictures with our favorite heroes.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-03T07:18:53+00:00
- Post Title: Re: Witcher Wild Hunt (request)

try this one:
[http://jlouisb.users.sourceforge.net/](http://jlouisb.users.sourceforge.net/)

It's from Jean-Louis (JLouisB) from the Witcher forum.
## Post #18
- Username: Ladyofpayne
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 03, 2015 3:41 am
- Post datetime: 2015-07-03T11:30:33+00:00
- Post Title: Re: Witcher Wild Hunt (request)

THank you. When he supposed to make rigging available?
## Post #19
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-07-04T17:10:57+00:00
- Post Title: Re: Witcher Wild Hunt (request)

shakotay2 thank you, I know about it.

I wrote script based on this sources of JLouisB: 
[http://jlouisb.users.sourceforge.net/](http://jlouisb.users.sourceforge.net/)

I wanted to understand, and I do not really like to overtake 3d models through a third-party software - are sometimes lost some details. Plus always there's the opportunity to patch something.

Usage - standart, first line ( tex_path = "K:\\W3tup" )- path to directory with unpacked textures
skin - don't supported, I'm working on it.
[w3u5.7z](https://xentaxbackup.github.io/file/9384_w3u5.7z)
## Post #20
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-07-12T10:43:11+00:00
- Post Title: Re: Witcher Wild Hunt (request)

little update:
fix creating "empty material" and work with chunk's some models:
[w3u6.7z](https://xentaxbackup.github.io/file/9414_w3u6.7z)
## Post #21
- Username: den130628
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 19, 2015 1:21 am
- Post datetime: 2015-08-09T07:32:50+00:00
- Post Title: Re: Witcher Wild Hunt (request)

> Reply from erik945
>
> little update:
fix creating "empty material" and work with chunk's some models:

If you use your script gives an error  "No ""+"" function for undefined". How can I fix?
## Post #22
- Username: VoliPanda
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 07, 2015 4:49 am
- Post datetime: 2015-09-08T20:03:00+00:00
- Post Title: Re: Witcher Wild Hunt (request)

> Reply from erik945
>
> little update:
fix creating "empty material" and work with chunk's some models:

I've got an error while trying to execute your MaxScript. Looks like an issue while trying to convert variables.
This error happens while trying to open one of Geralt's models.


and the + function error, while I tried to open Ciri's. 
Gonna try the other w2mesh.1.buffer files later on.
## Post #23
- Username: spy0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 10, 2010 5:22 pm
- Post datetime: 2016-03-29T18:11:41+00:00
- Post Title: Re: Witcher Wild Hunt (request)

Anyone managed to get a character models that have physic effects? (eg: triss DLC outfit), all aviable tools i've tested omit those parts on models
