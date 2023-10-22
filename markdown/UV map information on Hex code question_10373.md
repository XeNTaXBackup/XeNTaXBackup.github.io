## Post #1
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2013-04-28T04:36:42+00:00
- Post Title: UV map information on Hex code question

the UV map information can be somewhere else that is not in the mesh file? can it be a half float?

the first 3 floats are the vertices:



i've tried every possible combination of the blue portion but the only kind of thing that I got is this:



i've tried every other groups of bytes in the file but i got nothing

help please!!!!
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-28T06:11:36+00:00
- Post Title: UV map information on Hex code question

your vertex buffer looks OK... weird seeing 0x52 byte LE vertices. this a PC game?

next 3 are might be normal, followed by tangents and maybe binormals... don't know can't test.

the last 4 bytes do not appear to be a float, or two half-floats for that matter, it looks more like two shorts to me.
i would render the shorts in a simple obj file and scale them in various ways to find out what the scale parameter is.
way to tell for half-floats is too scroll through all the data in the column you suspect a half float. do you see values close to 0x3C00 (1.0f)? 0xF049 is not a good half float.

UV maps most certainly be stored somewhere else, in fact, all elements can be stored somewhere else (these are non-interleaved vertex buffers and to use them you use slot mechanism of Direct3D). Rise of Nightmares stored UVs in a separate buffer, for example. however, it looks like all your data is there with the exception of blend weights and blend indices (i don't see them).

what really looks wrong with your code is your index buffer setup looks bad he he he.

in the end you just have to keep trying. i've seen some weird shit too, like in RE6 PS3 some vertex formats used half-floats for BLEND INDICES. how fucked up is that lol?
## Post #3
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2013-04-28T13:30:49+00:00
- Post Title: UV map information on Hex code question

this is my second time scripting a importer.

the game is iron man 3 for Ipad/android

this code is a mess XD, i'm writing it as test before write the real one, just to know where the things are, this way is easier for me . I'm not so good on this things, this is the second time that I can find the mesh XD

looking to the game files i dont belive that they have a separete file to the uv map, i only find simple textures and mesh files

if you want to look the file:

this is the full file:
[http://www.mediafire.com/?334ca5fd35ertzj](http://www.mediafire.com/?334ca5fd35ertzj)

and this is the ajusted file that i'm using to test:
[http://www.mediafire.com/?587e21kjzpqt1r3](http://www.mediafire.com/?587e21kjzpqt1r3)

in the second file I removed the block before the vertices information and the block between the vertices and the faces(just for testing)

this is the max script code test so far:

```
	
delete $*
	
	Face_array=#()
	vert_array=#()
	uv_array=#()


	for x=1 to 3792 do(
		p1=readfloat f 
		p2=readfloat f 
		p3=readfloat f 
		p4=readfloat f
		p5=readfloat f
		p6=readfloat f 
		p7=readfloat f 
		p8=readfloat f 
		p9=readfloat f 
		p10=readfloat f
		p11=readfloat f 
		p12=readfloat f 
		p13=readfloat f 
		append vert_array[p1,p2,p3]
		append uv_array[0,0,0]
	)
	
	
	for x = 1 to 4687 do(
		fa= readshort f #unsigned +1
		fb= readshort f #unsigned +1
		fc= readshort f #unsigned +1
		append Face_array[fa,fb,fc]
	)
-- 	
-- 	for x=1 to 1000 do(
-- 		p1=readfloat f 
-- 		p2=readfloat f 
-- 		p3=readfloat f +2
-- 		p4=readfloat f
-- 		p5=readfloat f
-- 		append vert_array[p1,p3,0]
-- 		append uv_array[0,0,0]
-- 	)

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name= "a"
-- convertTo msh PolyMeshObject
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
fclose f
```


with it I got this:



thanks for you help!!!

my english is so bad x.x
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-28T14:59:04+00:00
- Post Title: UV map information on Hex code question

so the last 4 bytes of each vertex, what do uvs look like if you use:

u = signed short/32767
v = signed short/32767
## Post #5
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2013-04-29T00:15:14+00:00
- Post Title: UV map information on Hex code question

man, YOU FIGURED OUT!! thank you so much!!!



but there is another problem, it only works when i dont divide for 32767 and if i dont devide, the texture are to small and it ends up filling by repetition instead only 1 picture
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-29T09:14:26+00:00
- Post Title: UV map information on Hex code question

I your case use something like this to append UV's 

> append uv_array([p15,p14,0]/32767)

Then your UV's will look like that, and it should work fine (don't have any texture to test though)
[uv's.jpg](https://xentaxbackup.github.io/file/6367_uv's.jpg)
