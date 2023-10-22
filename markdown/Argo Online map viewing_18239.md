## Post #1
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-15T11:32:42+00:00
- Post Title: Argo Online map viewing

Hey, despite the fact that five years have passed since the last post of post about Argo Online [viewtopic.php?f=16&t=6393](http://forum.xentax.com/viewtopic.php?f=16&t=6393), I wanted to recognize the other files of this game. I took out my dusty disk with the Russian client of the game and installed it.
I found many useful scripts for bones, 3d models, textures and animations here, which still work. But now I have stopped on maps. It's not about "3D / 2D models", but I don't know where to write.

1) Folder .. \ Resources \ World \ mortalis ("mortalisWorld" in the archive below)
First I tried to get a map from the points that could be represented by float bytes from the *.xRaw file with the title "TERRAIN HEIGTH MAP", but the program gave it:
[](https://radikal.ru) [](https://radikal.ru)


The normal map *.tnm with the title "TERRAIN NORMAL MAP" looks like an image, but I do not know how the map data is stored and I can not extract it.
[](https://radikal.ru)
The EXTRACTED folder contains the texture files * .dds and * .ptobj (I think this is the game engine data) from the internal folder archives that I got using a simple script 
(UPD: The script didn't handle the names correctly. I modified the script from chrrox for the *.tbl2 file to *.tbl files):

```
#ARGO 

open FDDE tbl 1 
get idName long 1
get archiveSize long 1
get someValue long 1 #???
get filesNumber long 1

goto 0x004018 1 

for i = 0 < filesNumber
    get null long 1
    get offset long 1
    get zsize long 1
    get arcnum long 1 
    get name string 1 
    print "%arcnum%" 
        set NAME1 string "file" 
    set MYEXT string arcnum 
    strlen MYEXTSZ MYEXT 
    if MYEXTSZ == 1 
        string NAME1 += "00" 
    endif 
    if MYEXTSZ == 2 
        string NAME1 += "0" 
    endif 
    if MYEXTSZ == 3 
        string NAME1 += "" 
    endif 
    string NAME1 += MYEXT 
    string NAME1 += .data 
    open FDSE NAME1 0 

    Padding 4 1 

	log name offset zsize 
```


2) The folder .. \ resources \ world \ mortalis ("mortalis world" in the archive below), which I got using the chrrox script
 The celldata folder contains five file types: Empty *.cei, *.cma, *.cta, and similar to *.xRaw: *.coh, *.cth.
And also other files that make up the map.
3) The folder .. \ resources \ ui \ texture contains mortalismini.dds. Perhaps it will be necessary too.

My goal is to recreate the map of the game so that I can work with it.
I hope for any help (scripts, advices or tutorials)   
Here is the link to the archive: [http://www.mediafire.com/file/2ygv3jqs1 ... rtalis.zip](http://www.mediafire.com/file/2ygv3jqs19vdexv/Mortalis.zip)
## Post #2
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-06-19T14:37:16+00:00
- Post Title: Argo Online map viewing

Hi man , i'm interested in this game too but can't find a working link.
Do you have download link for this game?
## Post #3
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-19T20:50:44+00:00
- Post Title: Argo Online map viewing

> Reply from Drawing
>
> Hi man , i'm interested in this game too but can't find a working link.
Do you have download link for this game?
I'm a girl   
I already wrote that I have a CD with this game (this was an attachment to the game magazine in 2011). There are no working links for downloading on the network. But you can download it from me: [http://www.mediafire.com/file/wosc494l2 ... Online.zip](http://www.mediafire.com/file/wosc494l2cicwr7/Argo%20Online.zip)
P.S. It will be great if you understand something about it, because I'm a noob.
_______________________________________________________
About progress:
The first 18 bytes is the header, then there are 8 (4 + 4) bytes the number of vertices of width (513) and height (also 513). This gives 26 bytes of meta information in any * .xRaw file. The total number of bytes (1052702) minus meta information (26) gives the number of z vertices (1052676 = 513 * 513 * 4 byte float).
[](https://radikal.ru)

Then I wrote a script to import xRaw into Obj for Blender (Thx to [viewtopic.php?f=10&t=15453](http://forum.xentax.com/viewtopic.php?f=10&t=15453), because I didn't know Python before):

```

filePath = "C:\Onga\ArgoOnline\Resources\World\mortalis\mortalis.xRaw"
with open(filePath, "rb") as bin:
	
	bin.seek(0)
	header = struct.unpack("<BBBBBBBBBBBBBBBBBB", bin.read(18))[0]
	print(header)
	output = '# TERRAIN \n'
	width  = struct.unpack("<I", bin.read(4))[0]
	height = struct.unpack("<I", bin.read(4))[0]

	for x in range(height):
		for y in range(width):
			unk = struct.unpack("<f", bin.read(4))
			output = output + "v %f %f %f\n" % (float(y*1000), float(x*1000), unk[0]*1000)
			y += 1
		x += 1
	f = open(r"C:\Users\PC\Desktop\output.txt", "w")
	f.write(output)
	f.close()
```

And it works (the texture has a similar picture):
[](https://radikal.ru) [](https://radikal.ru)

Remarks: 
1) For a correct display you need to invert z (or just flip).
2) Some maps have an empty header and the number of vertices. Then to get the width and height need subtract 26 from the total number of bytes, divide by 4 and take the root of the resulting number (all maps have the form of a square). This should work.

I still can not understand why the normal map also consists of floating values ​​as an object   
Wherever I looked, the normal map was a picture.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-20T03:11:47+00:00
- Post Title: Argo Online map viewing

> Reply from Exse
>
> ... gives the number of z vertices...Then I wrote a script to import xRaw into Obj for Blender
Not quite sure why you're doing it this way. But regarding that there's such a topic: [Understanding Maps/Terrain](http://forum.xentax.com/viewtopic.php?f=10&t=15453), I guess you're trying to do the same process there as reverse engineering the geometry/model from a height map?

> Reply from Exse
>
> I still can not understand why the normal map also consists of floating values ​​as an object
Not surprisingly, as colors can also be represented by floats as percentages.



nm.jpg (83.65 KiB) Viewed 256 times
## Post #5
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-20T05:52:37+00:00
- Post Title: Argo Online map viewing

> Reply from Bigchillghost
>
> 
Not quite sure why you're doing it this way. But regarding that there's such a topic: Understanding Maps/Terrain, I guess you're trying to do the same process there as reverse engineering the geometry/model from a height map?Yes, I also gave this link in this message.
I want to be able to use all of the resources that are in the game, and I started with maps.

> Reply from Bigchillghost
>
> 
Not surprisingly, as colors can also represented by floats as percentages.Ok, I didn't understand how the colors are stored before, thanks.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-20T06:36:38+00:00
- Post Title: Argo Online map viewing

> Reply from Exse
>
> 
Yes, I also gave this link in this message.
Yeah it's from your message actually.

> Reply from Exse
>
> I want to be able to use all of the resources that are in the game, and I started with maps.
You know the word "map" sometimes can really be confusing, coz you don't know whether it's referring to a 3D or a 2D concept. But according to that topic you discovered, it's pretty much clear now.
However there's still one thing I don't understand. Why are there some vertices missing in your pics? If you view it from the z axis, it should looks like a plane full of points, shouldn't it?
## Post #7
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-20T07:18:38+00:00
- Post Title: Argo Online map viewing

> Reply from Bigchillghost
>
> 
However there's still one thing I don't understand. Why are there some vertices missing in your pics? If you view it from the z axis, it should looks like a plane full of points, shouldn't it?I just made a screenshot in the perspective projection, so the points are distorted. Look at the y axis (the green arrow), it is tilted.

> Reply from Exse
>
>
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-20T07:43:37+00:00
- Post Title: Argo Online map viewing

No, I mean the empty rectangular area inside the map square. There're still some vertices connecting the two point planes that're visible even you're from a perspective view.
## Post #9
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-20T09:09:24+00:00
- Post Title: Argo Online map viewing

> Reply from Bigchillghost
>
> No, I mean the empty rectangular area inside the map square. There're still some vertices connecting the two point planes that're visible even you're from a perspective view.There begins a great height for the mountains (a jump from 0 to 50 000 per 1 square), which is probably the reason that the distortion is so great (I multiplied heights by 1000). The vertices connecting the central rectangle to the right and left have only about 5000.
## Post #10
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-21T20:37:27+00:00
- Post Title: Argo Online map viewing

I have some questions:
1) The height map has 513 vertices in width and 513 in height, the normal map is also 513 * 513. But the number of pixels should be less than the number of vertices in width and in height by 1 (512 * 512), is not it?
2) I tried to add faces to my script, but I get this error every time.

```
        parsing obj file "C: \ Users \ PC \ Desktop \ mmm.obj" ... 10.3129 sec
        loading materials and images ...
        building geometry ...
        verts: 263169 faces: 261633 materials: 1 smoothgroups: 0 ...
Traceback (most recent last call last):
  File "C: \ Program Files (x86) \ Blender Foundation \ Blender \ .blender \ scripts \ import_obj.py", line 1191, in load_obj_ui
    POLYGROUPS.val
  File "C: \ Program Files (x86) \ Blender Foundation \ Blender \ .blender \ scripts \ import_obj.py", line 956, in load_obj
    create_mesh (scn, new_objects, has_ngons, CREATE_FGONS, CREATE_EDGES, verts_loc_split, verts_tex, faces_split, unique_materials_split, unique_material_images, unique_smooth_groups, vertex_groups, dataname)
  File "C: \ Program Files (x86) \ Blender Foundation \ Blender \ .blender \ scripts \ import_obj.py", line 453, in create_mesh
    face_mapping = me.faces.extend ([f [0] for f in faces], indexList = True)
KeyError: 'index out of range'
```

And 3DS Max says that my faces are duplicated.

```
import os
from math import sqrt

heightPath = "C:\Onga\ArgoOnline\Resources\World\mortalis\mortalis.xRaw"
normalPath = "C:\Onga\ArgoOnline\Resources\World\mortalis\mortalis.tnm"
statInfo = os.stat(heightPath)
size = int(sqrt((statInfo.st_size - 26) / 4))
print(size)
with open(heightPath, "rb") as h:
	output = '# TERRAIN \n'
	h.seek(26)

	for x in range(size):
		for y in range(size):
			unk = struct.unpack("<f", h.read(4))
			output += "v %f %f %f\n" % (float(y), float(x), unk[0]*(-1))
			y += 1
		x += 1			
	with open(normalPath, "rb") as n:
		output += "\n# NORMAL \n"
		n.seek(26)

		for x in range(size):
			for y in range(size):	
				red = struct.unpack("<f", n.read(4))
				blue = struct.unpack("<f", n.read(4))
				green = struct.unpack("<f", n.read(4))
				output += "vn %f %f %f\n" % (red[0], green[0], blue[0])
		output += "\n# VERTEX \n"
		global no
		no = 1
		global xn
		xn = 0
		global lineSize
		lineSize = 0
		while no < ((size-1)*(size-1)):
			if lineSize == size:
				lineSize = 0
				no += 1
				xn += 1
			output += "f %d//%d %d//%d %d//%d %d//%d\n" % (no+xn-1, no, no+xn, no, no+xn+size-1, no, no+xn+size, no)
			no += 1
			lineSize += 1
		
		f = open(r"C:\Users\PC\Desktop\mmm.obj", "w")
		f.write(output)
		f.close()
		print("Done!\n")
```

Here's what I get at the output: [http://www.mediafire.com/file/n2vniydup ... rtalis.obj](http://www.mediafire.com/file/n2vniydup8nne99/mortalis.obj)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-22T01:49:38+00:00
- Post Title: Argo Online map viewing

> Reply from Exse
>
> 
I tried to add faces to my script, but I get this error every time.
And 3DS Max says that my faces are duplicated.
For obj format the indices range from 1.

```
output += "vn %f %f %f\n" % (red[0], green[0], blue[0])
```

Actually the RGB should be limitted to the 2D concept. Here for vertex normals, it's Normal x, y and z.

```
output += "f %d//%d %d//%d %d//%d %d//%d\n" % (no+xn-1, no, no+xn, no, no+xn+size-1, no, no+xn+size, no)
```

I'm glad that you' choose to use a natural and more pleasing way to do it. But this line of code is not correct. The way creating a quad is slightly different from creating a triangle. Try this modified one:

```
import os
from math import sqrt

heightPath = "..\mortalis.xRaw"
normalPath = "..\mortalis.tnm"
statInfo = os.stat(heightPath)
size = int(sqrt((statInfo.st_size - 26) / 4))
print(size)
with open(heightPath, "rb") as h:
	output = '# TERRAIN \n'
	h.seek(26)

	for y in range(size):
		for x in range(size):
			unk = struct.unpack("<f", h.read(4))
			output += "v %f %f %f\n" % (float(x), float(y), unk[0])
			x += 1
		y += 1         
with open(normalPath, "rb") as n:
	output += "\n# NORMAL \n"
	n.seek(26)

	for y in range(size):
		for x in range(size):   
			Nx = struct.unpack("<f", n.read(4))
			Ny = struct.unpack("<f", n.read(4))
			Nz = struct.unpack("<f", n.read(4))
			output += "vn %f %f %f\n" % (Nx[0], Ny[0], Nz[0])
			x += 1
		y += 1   
output += "\n# Faces  \n"
lineSize = size - 2
for y in range(lineSize):
	for x in range(lineSize):   
		output += "f %d//%d %d//%d %d//%d %d//%d\n" % (x+y*size+1, x+y*size+1, x+y*size+2, x+y*size+2, x+(y+1)*size+2, x+(y+1)*size+2, x+(y+1)*size+1, x+(y+1)*size+1)
		x += 1
	y += 1
f = open(r"..\mmm.obj", "w")
f.write(output)
f.close()
print("Done!\n")

```

It's still a bit slow though.
This is the result:



shot.jpg (69.83 KiB) Viewed 213 times
## Post #12
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-06-25T01:43:24+00:00
- Post Title: Argo Online map viewing

Hi , thanks for the link 

I tried to unpack it with the script you provided and the one on xentax , I run script and select only file.tbl2 but when i try to extract it I got this message:


```
- open input file C:\Onga\ArgoOnline\Resources\file.tbl2
0
- enter in folder C:\Onga\ArgoOnline\Resources
  coverage file 0     0%   0          11780916   . offset 0000000000000000
- open input file C:\Onga\ArgoOnline\Resources\file0000.data2

- error in src\file.c line 465: fdnum_open()
Error: No such file or directory

Last script line before the error or that produced the error:
  34  open FDSE NAME1 0

Press ENTER or close the window to quit
```
## Post #13
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-25T08:15:58+00:00
- Post Title: Argo Online map viewing

> Reply from Drawing
>
> 
I tried to unpack it with the script you provided and the one on xentax , I run script and select only file.tbl2 but when i try to extract it I got this message
Hi again)
The error says that the script tries to open file file0000.data2. But the script should try to open only the files fileXXX.tbl2, not fileXXXX.tbl2.
Have you changed anything in the script from chrrox?

> Reply from chrrox
>
> Code: Select all#quickbms script
#ARGO
#from chrrox

open FDDE tbl2 1
set arcnum 0


goto 0x10001C 1

for i = 0
    get offset long 1
    get zsize long 1
    get null3 long 1
    get size long 1
    get arcnum long 1
    print "%arcnum%"
        set NAME1 string "file0"
    set MYEXT string arcnum
    strlen MYEXTSZ MYEXT
    if MYEXTSZ == 1
        string NAME1 += "00"
    endif
    if MYEXTSZ == 2
        string name1 - 1
        string NAME1 += "0"
    endif
    if MYEXTSZ == 3
        string name1 - 1
        string NAME1 += ""
    endif
    string NAME1 += MYEXT
    string NAME1 += .data2
    open FDSE NAME1 0


    get null1 long 1
    get null2 long 1

    get name string 1
    Padding 4 1

    get null long 1
if zsize == size
        log name offset zsize
else
clog name offset zsize size
endif
next i
P.S. I gave a script for *.tbl files, not for *.tbl2.
## Post #14
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-06-25T12:04:25+00:00
- Post Title: Argo Online map viewing

Ah sorry I didn't see your script was for .tbl, anyway I tried script from chrrox but I got the same error I posted before.

In resource folder I got : file.tbl2 and a lot of filexxx: from file000.data2 to file148.data2
I realy don't understand what I miss...


Ok I understand the problem. In the folder there are filexxx and not filexxxx.  I tried to rename some of them in filexxxx and the script works fine.
It's a pain the ass to rename every 148 file , so is there a quick way to modify the script? I really don't know how D:
## Post #15
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-25T12:55:52+00:00
- Post Title: Argo Online map viewing

> Reply from Drawing
>
> 
Ok I understand the problem. In the folder there are filexxx and not filexxxx.  I tried to rename some of them in filexxxx and the script works fine.
It's a pain the ass to rename every 148 file , so is there a quick way to modify the script? I really don't know how D:
Oh, I forgot that I changed it. Here is the final script code:

```
#ARGO 

open FDDE tbl2 1 
set arcnum 0 


goto 0x10001C 1 

for i = 0 
    get offset long 1 
    get zsize long 1 
    get null3 long 1 
    get size long 1 
    get arcnum long 1 
    print "%arcnum%" 
        set NAME1 string "file" 
    set MYEXT string arcnum 
    strlen MYEXTSZ MYEXT 
    if MYEXTSZ == 1 
        string NAME1 += "00" 
    endif 
    if MYEXTSZ == 2 
        string NAME1 += "0" 
    endif 
    if MYEXTSZ == 3 
        string NAME1 += "" 
    endif 
    string NAME1 += MYEXT 
    string NAME1 += .data2 
    open FDSE NAME1 0 


    get null1 long 1 
    get null2 long 1 

    get name string 1 
    Padding 4 1 

    get null long 1 
if zsize == size 
        log name offset zsize 
else 
clog name offset zsize size 
endif 
next i  
```
## Post #16
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-06-25T16:19:21+00:00
- Post Title: Re: Argo Online map viewing

Script she posted works perfectly
## Post #17
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-27T22:15:29+00:00
- Post Title: Re: Argo Online map viewing

Hi again. I did not think it would be so difficult to add textures to the map. All that I have at the moment is a list of the images from the file mortalis.xterrain, which are used on the terrain. [http://www.mediafire.com/file/v73wa5kej ... xtures.zip](http://www.mediafire.com/file/v73wa5kejc1c1ca/mortalis%20textures.zip) (The texture of coartare_stone_04.xtex seems to be a 2-Planar RGBG 8 8 8 8. Looks good if reduced)
[](https://radikal.ru)

What else ... I looked at the files from mortalis/celldata. There are 80 files of 5 different formats, so I tried to build a map or image to each format
*.cei files: I built an image of two colors and got it. It seems that these are the points of resurrection for two different races.
[](https://radikal.ru)

*.cta files: I got this height map, taking each byte as high. It looks like a map where the character can walk on the terrain.
[](https://radikal.ru)

*.coh files: This is some kind of projection of the buildings on the map
*.cth: Same, only without buildings
(Here both sets of images without an alpha channel - coh files on the left, cth on the right)
[](https://radikal.ru)

*.cma files: Always empty, same in other terrains, but need to check again

Any idea what I can do with this to add textures...?
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-28T12:54:47+00:00
- Post Title: Re: Argo Online map viewing

> Reply from Exse
>
> Hi again. I did not think it would be so difficult to add textures to the map. All that I have at the moment is a list of the images from the file mortalis.xterrain, which are used on the terrain...Any idea what I can do with this to add textures...?
So this is supposed to be a jigsaw puzzle? It seems you can form larger images using each texture as the component:



lunatia_11.jpg (138.52 KiB) Viewed 103 times


I guess the solution could be related with the UV scaling, and corresponding material groups. But the latter case might be a bit tricky.
## Post #19
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-06-28T15:00:34+00:00
- Post Title: Re: Argo Online map viewing

> Reply from Bigchillghost
>
> 
I guess the solution could be related with the UV scaling, and corresponding material groups. But the latter case might be a bit tricky.
Yes, it seems so. I just did not know what it's called. This can be seen in the mortalismini.dds which I posted in the first message:
[](https://radikal.ru)

Now the question is which image I should use to make a mask out of it for seven textures
## Post #20
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-07-06T22:43:58+00:00
- Post Title: Re: Argo Online map viewing

Ok... I couldn't add textures to the map. The file mortalis.xterrain additionally contains information about the *.lpd file, which is not present inside the unpacked client. Perhaps the problem is this.

But I have other questions
I looked at getting objects here: [MMO ARGO](http://forum.xentax.com/viewtopic.php?f=16&t=6393&start=15), but the finale00 plugin ([Argo xgeom plugin](http://himeworks.com/redirect.php?type=noesis&name=Argos_xgeom)) gives me an error in the case of objects (See case 1 and 3 below).
Here are examples of three types for which I have questions. The number of vertices and the number of faces are located after 40 00 00 00. Then the vertices (red), the normals, the texture coordinates (yellow) in each type. But after them there are bytes that I could not figure out. The faces are located at the end of the file. (Download link: [https://www.mediafire.com/file/06efk3p3 ... xgeoms.zip](https://www.mediafire.com/file/06efk3p3apajeqe/xgeoms.zip))
 I want to know if they contain something important for the models or I can skip them.

Case 1 (10_g_b_21_b_10_g_b_21_b_1.xgeom) - 8 extra bytes:
[](https://radikal.ru)[](https://radikal.ru)

Case 2 (f_animist_202_00_00.xgeom) - 16 extra bytes:
[](https://radikal.ru)

Case 3 (1_g_b_2__1_g_b_2_c.xgeom) - 24 extra bytes:
[](https://radikal.ru)[](https://radikal.ru)

You can get objects in a flat view if you put the beginning of the vertices after the texture coordinates in case 2 and 3. However, I think that this information is unnecessary and takes extra place in the file.
[](https://radikal.ru)
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-07T11:05:32+00:00
- Post Title: Re: Argo Online map viewing

> Reply from Exse
>
> 
I want to know if they contain something important for the models or I can skip them.
Well, both are correct.

For case 1, the extra two floats are just the UV atlas coords.
You can use it as an extra UV channel. Related info [here](https://docs.microsoft.com/en-us/windows/desktop/direct3d9/using-uvatlas).

UV:


UV atlas:


So fo case 1, where FVFsize = 40, the structure is like:

```
{
	float	v[3]
	float	vn[3]
	float	uv1[2]
	float	uvAtlas[2]
}
```

For case 2, where FVFsize = 48, there's a second UV channel which seems to be the same as the first one:

```
{
	float	v[3]
	float	vn[3]
	float	uv1[2]
	float	uvAtlas[2]
	float	uv2[2]
}
```

While for case 3, where FVFsize = 56, probably that's the tangent or binormal vector following the UV atlas, both of which have something to do with the UV. But the remain 1 float is still unknown.

```
{
	float	v[3]
	float	vn[3]
	float	uv1[2]
	float	uvAtlas[2]
	float	tangent[3]
	float	unknown
}
```

Though you can't preserve these extra data through obj format, you can import them into any 3D app that supports them. 
But you can skip them if you need only the basic features.
## Post #22
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-07-07T12:25:48+00:00
- Post Title: Re: Argo Online map viewing

> Reply from Bigchillghost
>
> 
For case 1, the extra two floats are just the UV atlas coords.
You can use it as an extra UV channel. Related info here.
Wherever I looked for the contents of 3D objects, only vertexes, normals, and faces are mentioned. This is  information I was looking for, thanks!
## Post #23
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-07-11T13:44:41+00:00
- Post Title: Re: Argo Online map viewing

Hi, I'm having problems again
I'm trying to add an xml parser to the * .xgeom files in the finale00 script. I'm trying to import ElementTree like this:

```
from xml.etree import ElementTree
```
But it gives me "ImportError: No module named pyexpat"
Then I created the DLLs folder as written in __NPReadMe.txt and put the pyexpat.pyd library from the full version of Python 3.2.1 there. And the following errors that I received: ImportError: DLL load failed: The specified module could not be found and "ImportError: No module named expat; use SimpleXMLTreeBuilder instead". Then I added:

```
etree.XMLTreeBuilder = SimpleXMLTreeBuilder.TreeBuilder
```
But again I catch the error: "ImportError: can not import name SimpleXMLTreeBuilder".

I use ElementTree only once:

```
tree = ElementTree.parse(dirpath + filename + ".xgeom")
```
## Post #24
- Username: Exse
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 24, 2017 2:03 am
- Post datetime: 2018-07-22T08:44:12+00:00
- Post Title: Re: Argo Online map viewing

Hi
I'm sorry that I didn't answer for so long. I didn't find a solution to the problem with importing third-party libraries into Noesis, so I moved to Blender. Now I'm supplementing the Szkaradek123 import script for Argo and War of Dragons models for other formats in the game. At the moment, I rewrote the finale00 script for *.xgeom models and wrote a parser for *.xcd and *.xgeom models that use XML.
