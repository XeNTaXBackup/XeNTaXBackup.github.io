## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-24T23:59:21+00:00
- Post Title: [solved] Adding texture to a .obj

I am trying to apply textures to a .obj file I created manually by extracting data from a custom game format. 
The model data and texture are on different files.

This is the texture (256x256):



And this is how it looks inside the game:



As you can see, the texture seems to be mirrored/duplicated because the texture image only contains 1 side. 
But how do I attach my texture to the object. I was trying it with a .mtl file but it just won't work. 



What did I do wrong?

Here is the .mtl file (I tried):

```
  illum 2
  map_Ka test.png
  map_Kd test.png
```
## Post #2
- Username: Leeloobastet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 16, 2016 3:45 am
- Post datetime: 2016-08-25T02:31:46+00:00
- Post Title: [solved] Adding texture to a .obj

When I extract an .obj file from a game, it always shows up with the .mtl file + the texture file(s).
I use Misfit Model 3D to re-attach the texture file to the object.
I open the object, then in the Edit Material option, I reattribute the texture files to all meshes.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-25T04:29:19+00:00
- Post Title: [solved] Adding texture to a .obj

@majidemo
first of all the notation of your faces in the obj file is incomplete.
It writes
f 1 2 3
f 1 3 4
[...]

Should be
f 1/1/1 2/2/2 3/3/3
f 1/1/1 3/3/3 4/4/4
[...]

because the 3D apps I know can't create the uv map from f 1 2 3 etc.
## Post #4
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-25T05:24:28+00:00
- Post Title: [solved] Adding texture to a .obj

> Reply from shakotay2
>
> @majidemo
first of all the notation of your faces in the obj file is incomplete.
It writes
f 1 2 3
f 1 3 4
[...]

Should be
f 1/1/1 2/2/2 3/3/3
f 1/1/1 3/3/3 4/4/4
[...]

because the 3D apps I know can't create the uv map from f 1 2 3 etc.

Sir shakotay2, do I just duplicate the face value? or is "1/x/y" x and y a completely different value I need to get the from custom format? 

Or it is simply 1/1/1 (x/x/x)? Thank you.

> Reply from Leeloobastet
>
> When I extract an .obj file from a game, it always shows up with the .mtl file + the texture file(s).
I use Misfit Model 3D to re-attach the texture file to the object.
I open the object, then in the Edit Material option, I reattribute the texture files to all meshes.

I don't think this is the case on mine, because I didn't use any program to extract the object. I manually decoded the custom format and wrote a python script to generate the .obj file.
## Post #5
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-25T05:34:39+00:00
- Post Title: [solved] Adding texture to a .obj

Sir shakotay2, 

I currently cant test 
```
f x/y/z
```
 or a different value for each slash, because the values on the custom format are all mapped already and I don't know where to get the slash values BUT...

I tested doing 
```
f v1/v1/v1 v2/v2/v2 v3/v3/v3
```
 assuming every slash is just a duplicate... and this is what I got. (at least the texture is now showing)



But there seems to be a problem in the mapping? what did I do wrong?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-25T05:51:51+00:00
- Post Title: [solved] Adding texture to a .obj

The indices for vertices/normals/uv may be different (such as f 1/1/2 2/2/3 3/3/2 for example) as you noticed.

> Reply from majidemo
>
> But there seems to be a problem in the mapping? what did I do wrong?Please upload the model file which you decoded.

(I'm off to office now...)
## Post #7
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-25T06:13:40+00:00
- Post Title: [solved] Adding texture to a .obj

I did notice. Thanks for your time in looking into this.

here's the file: [download](http://www.mediafire.com/download/i3yi7ol4cii5mtr/obj_file.zip). It contains a few related files like textures and the obj archive, but the actual file is "def_22.obj". (not a wavefront .obj, but a custom format .obj) 

A few more details on the format:

The faces starts at offset 76 (decimal) and ends at offset 1954 (decimal). I also added 1 (+1) to all values of the face.

Starting from offset 1954 (decimal) this structure follows until the end:

```
float y
float z

```


I hope the info helps.
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-08-25T08:32:45+00:00
- Post Title: [solved] Adding texture to a .obj

majidemo,

I recommend to read this page:
[https://en.wikipedia.org/wiki/Wavefront_.obj_file](https://en.wikipedia.org/wiki/Wavefront_.obj_file)
## Post #9
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-25T08:37:48+00:00
- Post Title: [solved] Adding texture to a .obj

> Reply from Karpati
>
> majidemo,

I recommend to read this page:
https://en.wikipedia.org/wiki/Wavefront_.obj_file

Thanks but I did use that as reference while writing my script to create the obj file.
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-08-25T08:52:55+00:00
- Post Title: [solved] Adding texture to a .obj

OK, Can you tell me which game from comes the (binary) .obj and .t16 files?
## Post #11
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-25T08:54:47+00:00
- Post Title: [solved] Adding texture to a .obj

> Reply from Karpati
>
> OK, Can you tell me which game from comes the (binary) .obj and .t16 files?

It's an old korean mmorpg back from 2001. It's no longer around as the company is long gone. I'm just studying the files. Its called Khan.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-25T18:55:50+00:00
- Post Title: [solved] Adding texture to a .obj

I've used your params in hex2obj:



def_022.jpg (138.41 KiB) Viewed 123 times


It's just a matter of building 1-y for the uvs (similar to mirroring at y axis)


These are the faces (similar to yours but normals indices ignored)

g submesh_0
f 1/1 2/2 3/3 
f 1/1 3/3 4/4 
f 5/5 6/6 7/7 
f 5/5 7/7 8/8 
f 9/9 10/10 11/11 
f 12/12 10/10 9/9 
f 13/13 9/9 11/11 
[...]
## Post #13
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-25T19:16:01+00:00
- Post Title: [solved] Adding texture to a .obj

> Reply from shakotay2
>
> I've used your params in hex2obj:
def_022.jpg
It's just a matter of building 1-y for the uvs (similar to mirroring at y axis)


These are the faces (normals indices ignored)

g submesh_0
f 1/1 2/2 3/3 
f 1/1 3/3 4/4 
f 5/5 6/6 7/7 
f 5/5 7/7 8/8 
f 9/9 10/10 11/11 
f 12/12 10/10 9/9 
f 13/13 9/9 11/11 
[...]

Oh, wow. Although I didn't completely understand when you said: "It's just a matter of building 1-y for the uvs". So does that mean that the faces are actually just duplicates?

Thank you so much for your help. I'll try to update my python script to also generate the texture.

---edit---

I can't figure out how to fix the texture. Can you show me your `.obj` and `.mtl` file? Thank you


```
usemtl test
g submesh_0
f 1/1 2/2 3/3
f 1/1 3/3 4/4
f 5/5 6/6 7/7
f 5/5 7/7 8/8
f 9/9 10/10 11/11

```
[/size]
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-25T19:21:14+00:00
- Post Title: [solved] Adding texture to a .obj

> Reply from majidemo
>
> Although I didn't completely understand when you said: "It's just a matter of building 1-y for the uvs".uv Coords 0.0 0.0 -> 0.0 1.0, 1.0 1.0 ->1.0 0.0
Some people say it's mirroring at the y axis, but it's an additional adding of 1.0 to y,
so in the end y -> 1-y

> but I can't figure out how to add the textures there.it's not implemented.
I use blender for the texture thingie ("mirroring" included).

edit: I don't have a mtl file.
you can get the obj by performing a File/SaveAs mesh in hex2obj.
## Post #15
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-25T19:26:27+00:00
- Post Title: [solved] Adding texture to a .obj

> Reply from shakotay2
>
> majidemo wrote:Although I didn't completely understand when you said: "It's just a matter of building 1-y for the uvs".uv Coords 0.0 0.0 -> 0.0 1.0, 1.0 1.0 ->1.0 0.0
Some people say it's mirroring at the y axis, but it's an additional adding of 1.0 to y,
so in the end y -> 1-y
but I can't figure out how to add the textures there.it's not implemented.
I use blender for the texture thingie.

Oh, if I understand correctly. My current python script:

```
"vt %f %f\n" % (x[0], x[1])
```


Should be changed to:

```
"vt %f %f\n" % (x[0], 1-x[1])
```


??
## Post #16
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-25T19:28:45+00:00
- Post Title: Re: Adding texture to a .obj

Oh great! Thanks it works... Love your work on hex2obj btw. Now, I'm on to bones. Might be back here if it gets tough. See you around...
