## Post #1
- Username: ParsEmAll
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-27T00:45:23+00:00
- Post Title: Very Basic model format conversion (Shaiya).

In this tutorial you will learn the VERY basic way to convert a 3d model into verts that can be loaded into a 3d application.
I hope to expand on these tutorials and use better tools to automate the job and code it completely proper.
for this tutorial you will need a few tools

1. Float 2 text [download/file.php?id=1888](http://forum.xentax.com/download/file.php?id=1888)
2. HxD (free hex editor)
3 excel (2007)
4 Deep exploration (program able to view an obj with just verts
5 some shaiya model files. [download/file.php?id=2187](http://forum.xentax.com/download/file.php?id=2187)

1) Ok so open the model folder after you extract them and open the file demf_boots001.3DC
in the program HxD


2)Now if we know the model format lets see how to break it down

> #Provided from Fatduck
>
> dword       constant00
>
> dword       numBones
>
> struct Bone {
>
>    float_16 Matrix4X4   
>
> }
>
> dword       numVerts
>
> struct Vert {
>
>    float_3  CoordXYZ
>
>    float    Weight
>
>    byte     BoneID01
>
>    byte     BoneID02
>
>    byte     NULL1
>
>    byte     NULL2
>
>    float_3  NormalXYZ
>
>    float_2  TexCoordUV
>
> }
>
> dword       numFaces
>
> struct Face {
>
>    word_3   FaceIndices123
>
> }

3) a dword is 4 bytes
a 32 bit float (these are 32 bit floats) is equal to 4 bytes
float_X is the number of floats in a row so float_2 would be 8 bytes
and a byte is 1 byte
a word is 2 bytes

4) So knowing this lets look at the first line
dword       constant00
this tells us our first 4 bytes are 00 and if we check this they are

5) The next line is 
dword       numBones
so the Number of bones is in the next 4 bytes
which shows us 2C 00 00 00 so that converts into 00 00 00 2C
and 2C in decimal is 44
so now we know we have 44 bones

6) The next part is
struct Bone {
   float_16 Matrix4X4   
}
so this means we have a float which is 4 bytes then the underscore 16 means each bone has 16 floats
so in decimal we do 4 x 16 = 64 then we convert this number to hex which is 0x40
we multiply 0x40 bye the number of bones 2C and we get B00
If you highlight this section you should get a screen looking just like mine
7) The next line is
dword numVerts
this means the next 4 bytes tell us how many verts we will have in our model
so we take AE 01 00 00 and convert it to 00 00 01 AE and that equals 430
so there are 430 vertexes.

8 The next line is the most important for the tutorial
float_3 CoordXYZ
this means we have a float which is 4 bytes and we have 3 in a row representing x , y z coordinates.
so our first set of cordiantes should look like this 
X)FE F8 A1 BE 
Y)00 00 C8 36 
Z)4A CA BF BD

9) The next line
float    Weight
means the next 4 bytes are the weighting information
00 00 80 3F

10) the next 4 lines tell us what bones our weighting information has influence on
byte BoneID01
byte BoneID02
byte NULL1
byte NULL2
22 00 00 00
break these apart byte by byte so this vertex is effected bye bone 22 and 00
you can ignore the NULL parts

11)This next line tells us our normal coordinates
float_3 NormalXYZ
it is a float value so its 4 bytes and it is in a series of 3 so its 12 bytes total
X)08 7D 7D BF 
Y)E2 5A 0D 3E 
Z)AC 99 B1 BC

12) The last line of the vertex definition tells us our UV coordinates.
float_2 TexCoordUV
U)BB DA 08 3F 
V)F2 60 7A 3F
so it is again a float of 4 bytes and there are 2 in a row so it is 8 bytes total

13) The next line tells us how many faces we have
dword numFaces
so it is a dword of 4 bytes
98 01 00 00 so convert it to 00 00 01 98 and in decimal that is 408
so we have 408 Faces

14)The next 2 lines tell us the face structure
struct Face {
word_3 FaceIndices123
}
so we have a word 2 bytes and 3 in a row so thats 6 bytes
so 408 / 3 = 158

15) Now to the converting the vertex part
highlight the whole vertex section and copy it into a new hxd file called vertex.dat
start offset B0C
end offset 4E3B
length 4330

16)now we use float2txt on our dat file 
float2txt.exe vertex.dat vertex.txt 10
we take the arguments float2txt.exe input file output file number of floats
we choose 10 because there are 10 groups of 4 bytes that make up our vertex structure.

17)now we open excel and it will ask is this a delimited file choose tab and space check boxes and hit import.
you will end up with columns a - j
[](http://img85.imageshack.us/i/shaiyapic7.jpg/)
18)delete columns d - j so you are only left with
a b and c
inert a column before a and fill it with the letter v until you reach the end of your vertex list
(line 430)

19) save the file as a csv file
open the file in hxd
do a replace and replace in hex 2C with 20
and save the file as testobj.txt

20)now open your file in wordpad and paste the following header

```
# File Created: 26.09.2009 19:47:31

mtllib test.mtl

#
# object NET
#


```

and at the end of your file put 

```

```

ok now save your file as test.obj

21)Open your file in deep exploration and see the boots 

[boots.rar](https://xentaxbackup.github.io/file/2379_boots.rar)
## Post #2
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-09-27T00:47:52+00:00
- Post Title: Very Basic model format conversion (Shaiya).

Hope to see this completed.

Now, converting models into a usable file is one thing, but how about converting them back to their original file?

Then we'd be good.

Unless there's a tutorial on this and I can't see it.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-27T01:20:13+00:00
- Post Title: Very Basic model format conversion (Shaiya).

I will attempt to make more tutorials this one is done for now.
and I will try to teach people how to do this in max script
or a simple model viewer code.
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-09-28T14:38:37+00:00
- Post Title: Very Basic model format conversion (Shaiya).

This is really great info. Probably easy to use because you showed all commands from fatduck but maybe hard to do by your own from scratch  But still, impressive
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-02T01:55:24+00:00
- Post Title: Very Basic model format conversion (Shaiya).

I will write a max script import tutorial soon for shaiya so you can see how it is done.
[](http://img202.imageshack.us/img202/3402/shaiya1.jpg)
## Post #6
- Username: ParsEmAll
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 15, 2009 4:57 am
- Post datetime: 2009-10-14T21:43:30+00:00
- Post Title: Very Basic model format conversion (Shaiya).

Thanks you for this tutorial.

> Reply from chrrox
>
> 
14)The next 2 lines tell us the face structure
struct Face {
word_3 FaceIndices123
}
so we have a word 2 bytes and 3 in a row so thats 6 bytes
so 408 / 3 = 158
looks like this should be: we have 408 faces, which have 408 * 3 = 1224 vertex index numbers in total of a length of 2 bytes each.

Looking forward for your next tutorial about importing it to max, since I had some issues with the converter:
- I had to trow away the first vertex (v), vertex uv's (vt) and vertex normal (vn) in order to get the mesh loaded visually correct.
- I needed to flip the uv verticaly too

Thank you again  (and Fatduck of curse)

Just for fun I made a command line tool to automate this.
Here are some some results:
## Post #7
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-18T04:29:13+00:00
- Post Title: Very Basic model format conversion (Shaiya).

Thanks for tutorial.  
As i understand, this method can be used for exploring file format. Right?   
I can check if some portion of data represents vertexes, but how about triangles, bones and normals? Then we'd be good.

Also.

> 19) save the file as a csv file
>
> open the file in hxd
>
> do a replace and replace in hex 2C with 20
There is a better way to do this. Just choose space delimeter instead of comma when you save file as csv.

P.S. Moar tutorials like this please
## Post #8
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-20T16:01:15+00:00
- Post Title: Very Basic model format conversion (Shaiya).

DEAR chrrox please insert the images in full size , because for saving the tutorials , for offline reading !
## Post #9
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-10-30T03:14:46+00:00
- Post Title: Very Basic model format conversion (Shaiya).

Any word on a maxscript for this?
## Post #10
- Username: huckleberrypie
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-06T02:34:34+00:00
- Post Title: Very Basic model format conversion (Shaiya).

Here is a max script that will work on these files

```
fname = "C:\\temp\\test.3dc"  --file name
f = fopen fname "rb"   --open file in read only format
Vert_array = #()    --define arrays for verts, normals, UV and Faces
Normal_array = #()
UV_array = #()
Face_array = #()
Weight_array = #()
Bone_array = #()
fseek f 4 #seek_cur
bray = readlong f
	 
for i = 1 to bray do (   --* number of Bones
b1 = readfloat f 
b2 = readfloat f
b3 = readfloat f
b4 = readfloat f
b5 = readfloat f
b6 = readfloat f
b7 = readfloat f
b8 = readfloat f
b9 = readfloat f
b10 = readfloat f
b11 = readfloat f
b12 = readfloat f
b13 = readfloat f
b14 = readfloat f
b15 = readfloat f
b16 = readfloat f
)
vray = readlong f
for i = 1 to vray do (
vx = readfloat f     --read xyz coordinates
vy = readfloat f
vz = readfloat f
append Vert_array [vx,vy,vz] --save verts to Vert_array
w1 = readfloat f
bo1 = readbyte f
bo2 = readbyte f
bo3 = readbyte f
bo4 = readbyte f
--append Weight_array [w1,bo1,bo2,bo3,bo4]
nx = readlong f    --read Normal
ny = readlong f
nz = readlong f
append Normal_array [nx,ny,nz] --save normals to Normal_array
tu = (readfloat f) * 1     --read UV float value
tv = (readfloat f) * -1 
append UV_array [tu,tv,0]  --save UVs to UV_array
)
nray = readlong f
for i = 1 to nray do (
f1 = (readshort f) + 1   --read face indices, games are start form 0, but Max start from 1
f2 = (readshort f) + 1   --so we add 1 to each index
f3 = (readshort f) + 1
append Face_array [f1,f2,f3] --save faces to Face_array
)
fclose f     --close file
msh = mesh vertices:Vert_array faces:Face_array   --build mesh
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

```
## Post #11
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-06T09:01:32+00:00
- Post Title: Very Basic model format conversion (Shaiya).

is there any script or MEL for maya that works in similar way ?
   thanks
## Post #12
- Username: djoscar
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Dec 17, 2009 4:59 pm
- Post datetime: 2010-03-20T13:02:31+00:00
- Post Title: Very Basic model format conversion (Shaiya).

Wow thanks a lot of this!

What I would also love is a nice tutorial on writing an import maxscript for 3d models
## Post #13
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-08-02T22:36:10+00:00
- Post Title: Very Basic model format conversion (Shaiya).

This can also apply to any 3D format once you know its structure, right?
## Post #14
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-24T20:43:17+00:00
- Post Title: Very Basic model format conversion (Shaiya).

Thanks so much for the tutorial! You are awesome! I still suck at most of this, but having things spelled out with lots of pictures helps a whole lot.
## Post #15
- Username: linpost
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 21, 2011 1:37 pm
- Post datetime: 2011-07-21T06:09:05+00:00
- Post Title: Very Basic model format conversion (Shaiya).

i dont understand how you know 2C meens 44 bones, i have 3C an i dont see anywhere a number or i dont know
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T13:01:39+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

> Reply from linpost
>
> i dont understand how you know 2C meens 44 bones, i have 3C an i dont see anywhere a number or i dont know

He followed the format and the format says those 4 bytes represent an integer for the number of bones, and 2C 00 00 00 is 44 in decimal (little endian)

The guide assumes you know the terminology used in the format (dword, word, byte, float) and endian-ness, amongst other things.
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-22T19:12:06+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

Forget endianness and data types, it sounds like linpost doesn't even understand how hexadecimal works.
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-07-25T07:16:06+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

Time to read this first, linpost: [http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF)
## Post #19
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T15:43:27+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

when you say "now if we know the file format" what does that mean? if we know how a file is structured? what if all i know is the file type - FLEV - but not much else. I know the 3D data must be in there. I don't know why some FLEVs are .flev and some .flv and I dont know why some have text data within the hex data.
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T22:18:46+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

> Reply from hatyn
>
> when you say "now if we know the file format" what does that mean? if we know how a file is structured? what if all i know is the file type - FLEV - but not much else. I know the 3D data must be in there. I don't know why some FLEVs are .flev and some .flv and I dont know why some have text data within the hex data.

First you have to know what you're looking at.
If you don't even know that, you're probably not going to get anywhere.

Try looking for 3D data in an image (picture) file; doesn't work.
But what if I use "jpg" for my model extension?

Extensions. You should just forget them since they mean nothing aside from being a name.

An extension is only good for separating files from one another since people at least do that most of the time. I guess you can type it into some search engine, but then you end up with dozens of potential modders looking at something completely irrelevant and making great discussion about nothing cause they noticed that their format ZXY is used in "My Dummy Application That Only I Use" and think that my application might have anything to do with their stuff.

Once you have some idea what the file might contain, you can focus on looking for things that match what you already know.

If you know everything, your job will be easier.
If you know nothing, you're probably not going to get anywhere.
If you know a little, then you might be able to get somewhere.

FLEV doesn't mean anything. It could be an idstring used to verify that the file is what is expected. How someone chooses their extensions might be based on some standard they choose, or just randomly choosing things. I could call my model extension ".LOL" and some people might spend lots of time wondering what that might mean. They could spend years to publish papers about it and then maybe I will break the news and tell them how I came up with the extension.

If two models use two different extensions, then it probably reflects the changes in their content. For example you have static and skeleton meshes; they might name them differently (eg: sm and skem as in Tales of Fantasy)

There is no real difference between "text data" and "hex data". It just happens that you can read one  and probably not the other. It is all parsed and handled appropriately. Your role would be to determine how it is used, and whether you need it or not. If you don't know, just skip it. If at the end you get nothing, maybe the stuff you skipped might be important. Or not.

You figure out a file structure as you go. You start from the top and work your way down and find patterns. Once you find a pattern that gets you in and gets you out, there's your file structure. Then you just have to refine it so it looks less like a black box.
## Post #21
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T23:36:44+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

well having a try with the older flver files that supposedly worked with the blender importer might shed me some light on how to modify the script...so getting that psp game now.
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T23:42:44+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

If you can use the script to trace the file manually you can probably find where the structures are changing.
So for example if it's expecting a name and you're not seeing a name, then you know something is different.
## Post #23
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-09T12:06:39+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

not sure how to manually scan the file with the importer python script, my bad. Whenever I import I get some python errors like value shouldnt be negative or string expected should be 64 bits
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-09T12:45:42+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

You basically look at where the parsing begins, and then try to look at what it's reading.
Although when I tried looking at it, I got lost lol

But ya it looks like the flv format for the two games seem completely different.
## Post #25
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-09T13:24:15+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

ah well..will figure it out someday
## Post #26
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-29T23:58:05+00:00
- Post Title: Re: Very Basic model format conversion (Shaiya).

Could you please reupload the images?
