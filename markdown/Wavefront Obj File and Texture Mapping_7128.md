## Post #1
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2011-08-06T11:44:50+00:00
- Post Title: Wavefront Obj File and Texture Mapping

Hey everyone,

i need some information about obj files. I was able to extract a model with textures from a game file. The extracted file looks like this.

```
v 0.053712 0.020744 -0.039279
v 0.061784 0.008303 -0.013566
v 0.053478 0.007107 -0.034874
v 0.024713 0.154537 0.04836
vt 0.175401 0.654691
vt 0.169565 0.67048
vt 0.175952 0.67048
vt 0.107216 0.547805
f 4 1 3
f 2 3 1

```


Now my Questions:
1. The vertex texture command defines how a texture is mapped on the object, right?
2. The face command defines the triangles from the object. What about the vt command, must they have a face definition?
3. How can i include the texture in the obj file? I wanna open the obj 
(Blender, Max,..) and see the complete textured object.
4. Are more information necessary for mapping a texture to a object?
## Post #2
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-08-06T12:34:10+00:00
- Post Title: Wavefront Obj File and Texture Mapping

Hi,Riigel.

> 1. The vertex texture command defines how a texture is mapped on the object, right?
Right. vt = Texture vertices uv.

> 2. The face command defines the triangles from the object. What about the vt command, must they have a face definition?
vt command are not the meanings about meshs. they meaning Vertices.

> 3. How can i include the texture in the obj file? I wanna open the obj
>
> (Blender, Max,..) and see the complete textured object.
you will make MTL file.
and write mtllib/usemtl command in obj file.

> 4. Are more information necessary for mapping a texture to a object?
I recommend you to examine OBJ/MTL fileformat.
[http://www.cs.clemson.edu/~dhouse/cours ... ormat.html](http://www.cs.clemson.edu/~dhouse/courses/405/docs/brief-obj-file-format.html)
[http://www.fileformat.info/format/material/](http://www.fileformat.info/format/material/)

however, I am noob and Jap talker, I might be wrong. :p
## Post #3
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2011-08-06T13:38:54+00:00
- Post Title: Wavefront Obj File and Texture Mapping

I have read about the mdl file but it doesn't work for me.
Maybe someone can help me.

I think my example must look like:

```
g Mesh 0
v 0.053712 0.020744 -0.039279
v 0.061784 0.008303 -0.013566
v 0.053478 0.007107 -0.034874
v 0.024713 0.154537 0.04836
vt 0.175401 0.654691
vt 0.169565 0.67048
vt 0.175952 0.67048
vt 0.107216 0.547805
usemtl tex
f 4 1 3
f 2 3 1

```


But what is about the mtl file. The object has only one texture in dds format (no Reflection Map, Ambient Occlusion or Normal map). 

1. Do i need the the Ka, Kd, Ks statements for a single textured object?
2. If yes, how i get the values for Ka,Kd,Ks? Must they stored in the model file?
3. Can i use dds format for textures?

```
Ka 0.0435 0.0435 0.0435
Kd  0.5922  0.0166  0.0000
Ks  0.5974  0.2084  0.2084
map_Ka tex.dds

```
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-06T16:47:59+00:00
- Post Title: Wavefront Obj File and Texture Mapping

[http://en.wikipedia.org/wiki/Wavefront_.obj_file](http://en.wikipedia.org/wiki/Wavefront_.obj_file)

Most of your questions are answered there.
IMO, it is summarized nicely and orderly.

It is an overview of the full specs, which is also available in an external link.

> 2. The face command defines the triangles from the object. What about the vt command, must they have a face definition?

There are 4 different face definitions.

1: f v1 v2 v3 - just coords
2: f v1/vn1 v2/vn2 v3/vn3 - coords + normals
3: f v1/vn1/vt1 v2/vn2/vt2 ... - coords + normals + tex coords
4: f v1//vt1 v2//vt2 ... - coords + tex coords

You can see how the omit the normals if you don't need them.

I didn't read much about the materials, but a texture map is optional, so you don't necessarily have to specify the stuff for the other properties.
## Post #5
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-08-06T17:16:26+00:00
- Post Title: Wavefront Obj File and Texture Mapping

Thank you for your complement to my bad explanation, finale00.
Your post are informative for me, too.
## Post #6
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2011-08-11T15:48:36+00:00
- Post Title: Wavefront Obj File and Texture Mapping

I have another question about texture mapping.

I have extracted a game Model (soccer ball). It's using 2 textures, one normal and one alpha texture. The problem is, that both use different 
texture coordinates(vt). Is it possible to use both textures with the obj fileformat?

@finale00
thx for your hints, they helped me alot.
There is a little mistake in your post.

> Reply from finale00
>
> 
There are 4 different face definitions.

1: f v1 v2 v3 - just coords
2: f v1/vn1 v2/vn2 v3/vn3 - coords + normals
3: f v1/vn1/vt1 v2/vn2/vt2 ... - coords + normals + tex coords
4: f v1//vt1 v2//vt2 ... - coords + tex coords

2: f v1/vn1 -> coords + tex coords.
4: f v1//vt1 -> coords + normals.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-11T15:53:29+00:00
- Post Title: Wavefront Obj File and Texture Mapping

Ya, I probably should've checked the order before I wrote it  
I don't know anything about texturing so I can't help there.
