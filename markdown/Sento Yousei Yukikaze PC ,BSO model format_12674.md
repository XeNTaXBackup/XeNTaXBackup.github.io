## Post #1
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-11T05:14:07+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

Hi,I found a very good sci-fi aircraft design.
It's originally an Anime. 
It's an old pc/Xbox game. 
Official site link
[http://www.ss-alpha.co.jp/products/yukikaze.html](http://www.ss-alpha.co.jp/products/yukikaze.html)
Some chinese made an H.A.W.X mod of this aircraft,i extracted it and found it's topology is really messy.
So i decide to extract better models from this game.

I've figure out "part" of it's model pattern.

```
unsigned long = face index count
float3 = vertex coordinate
float3 = normal
float2 = UV coordinate
unsigned short x face index count = face index
faces are saved as tri-list

```


Some samples
[https://www.sendspace.com/file/ypozev](https://www.sendspace.com/file/ypozev)

There seems to have more than 1 model pattern stored,and i still don't figure out it's header pattern.
Please help if you have time.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-11T11:15:42+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

header pattern?
For example K1.BSO, from address 0x130 you'll find the vertex counts, face indices counts (DWords) with an offset
of 48 bytes to the next submeshes entry.

using hex2obj (view link in my sig):



A1_BSO_.JPG (218.33 KiB) Viewed 283 times
## Post #3
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-11T11:31:52+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

> Reply from shakotay2
>
> header pattern?
For example K1.BSO, from address 0x130 you'll find the vertex counts, face indices counts (DWords) with an offset
of 48 bytes to the next submeshes entry.

using hex2obj (view link in my sig):
A1_BSO_.JPG

Nice tool,it even support Big endian!
I started to figure out it's header pattern,,however some aircraft have dozens of tiny meshes,so import them one by one with your tool is not an efficient way.
I'll try to write maxscript once i understand it's header structure totally(each meshes' vert count and face count are stored in the header).
Thanks for telling me this handy tool,will try it on other games later:)
## Post #4
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-11T14:24:51+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

ok,,figure out it's primary header structure and model pattern now.


There are 3 types of data in the model.
1st. ***.ORO .  it's main container of models ,the red rectangle in the picture is ORO count.Each ORO container has a 4x4 matrix array in the header.The yellow rectangle in the picture,I'm guessing it's transform matrix,each ORO container may have multiple 2nd,3rd type of data as listed below

2nd. I name 2nd type of data as "Controller".Just guessing from it's string name,It's data consist of 8 floats,can be identified by identifier in the header,as 0xFF FF FF FF

3rd. Model data,as I mentioned at the 1st post,can be identified by 0x 00 00 00 00

Blue rectangle is the total count of controller + model data.
Purple rectangle is the count of type2 + type3 data inside the ORO container.

I don't know what the "controller" 8 floats meaning,,,will try to import 3d model first.
## Post #5
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-11T17:09:07+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

Alright,almost all airplanes are imported.
It's pretty low poly from point of view today,but it's a very good material to be polished in zbrush.
Some small parts still have problem because i still don't add transform matrix into it.(look at it's rudder)



Here is the script
## Post #6
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-13T07:37:30+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

Script update!
Fixed bug can't read part of the terrain/aircraft models.

I need help with the translation part,I can't find the proper way to transform it's small parts like rudder/pilots/wing flaps into correct location.
## Post #7
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-03-14T03:41:25+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

the matrices seem wrong when you load it as bones
## Post #8
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-14T04:11:28+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

> Reply from TGE
>
> the matrices seem wrong when you load it as bones
I'm not sure if it's really a "matrix" now.
I'm start to think it's just point3 values.
I found a way to get the correct displacement value.use following script.

```
m21 = readfloat f * -1.0 ; m22 = readfloat f ; m23 = readfloat f * -1.0
m31 = readfloat f * -1.0 ; m32 = readfloat f ; m33 = readfloat f * -1.0
m41 = readfloat f ; m42 = readfloat f ; m43 = readfloat f
ORO_scale = readfloat f ; ukn = readfloat f ; ukn = readfloat f ; ukn = readfloat f
ORO_tfm = matrix3 [m11,m13,m12] [m21,m22,m23] [m31,m33,m32] [m41,m42,m43]

displacement_value = ORO_tfm.row3 - ORO_tfm.row1

```


As for rotation,,I've tried all kinds of matrix,quaternion combination,still no luck.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-14T11:23:44+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

nice script!  

But seems you missed to post lines like these in your last addition:

displacement_value *= ORO_scale
if (magic_type>=0) then ORO_tfm += transMatrix displacement_value

I tried D0.BSO without using ORO_tfm and can confirm your script to work with the pilots.
But seems there's still a wrong position of the landing gear with what I tried:



D0_BSO_.JPG (48.67 KiB) Viewed 182 times


These are the displacements for the left landing gear and they are zero (except for 0.173):
SM 23: displ. 15. [0,0,0]
SM 25: displ. 17. [0,0,0]
SM 27: displ. 19. [0,0,0]
SM 29: displ. 21. [0,0,0.172963]
Not sure about the gear, I'm not a pilot  , but isn't it the gear lips the arrow points to (and they are closed; missing rotation?)

edit: ah, well, see. Nice construction plan!   So the position is correct.
Is this a real plane? So it's landing with it's nose pointing upwards in some angle
what would explain why the landing gear is displaced backwards.
## Post #10
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-14T11:56:00+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

> Reply from shakotay2
>
> nice script!  

But seems you missed to post lines like these in your last addition:

displacement_value *= ORO_scale
if (magic_type>=0) then ORO_tfm += transMatrix displacement_value

I tried D0.BSO without using ORO_tfm and can confirm your script to work with the pilots.
But seems there's still a wrong position of the landing gear with what I tried:
D0_BSO_.JPG
Not sure about the gear, I'm not a pilot  , but isn't it the gear lips the arrow points to (and they are closed; missing rotation?)

This should be able to answer your question.


The displacement script i posted only solved pilot location problem.There are still few parts doesn't fit that script.
So that script may not 100% correct i think.
As for rotation,,I'm thinking each ORO group may be transformed by the "controller" type data.
The "controller" data is actually meshes too,but sometimes they don't have face index data,only 1 vertex.
I think i'll try to render these single vertex stuff as dummy and skin other stuff onto it,then try to move the dummy and see what will happen.
## Post #11
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-15T08:45:34+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

> Reply from shakotay2
>
> nice script!  

Is this a real plane? So it's landing with it's nose pointing upwards in some angle
what would explain why the landing gear is displaced backwards.

Of course it's not a real one.It's 3d-airplane with 2d char anime.
I've tried to render those single vertex controllers as dummy,pretty sure they're not working as skeleton.
They're used as attaching point of missiles/wingtip contrails meshes.


update the script 
render all "controller" stuff as dummy.
Meshes have correct names.
added few debug message,that help you find the matrix3 (or point3 ,whatever they are) values of each mesh.
Rendering speed is slow because of lots debug messages.

I'm pretty sure the value m21,m22,m23,,and m41,m42,m43 are realated to rotation .
Still no luck with it:P
## Post #12
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-17T02:40:03+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

Find the answer of rotation,it's Radians value..really interesting.It's my first time see game uses this kind of stuff.

To get the correct rotation value

Where
1 radian =
57.2957795 degree

m21 * 57.2957795 = y rotation value
m22 * 57.2957795 = x rotation value
m23 * 57.2957795 = z rotation value
## Post #13
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-03-18T01:12:58+00:00
- Post Title: Sento Yousei Yukikaze PC ,BSO model format

Ok,this should be the last update for this project.
All parts are in their location,you can play with those pivot dummies.
fixed x,y,z direction problem.
values of m41,m42,m43,m51 are probablly quaternion,which is used to control the rotation limit of each pivot.I leave the debugging message so you can adjust those values manually by message.

My script may not be 100% correct,but the result of the models seems to be okay.
Please share your idea if you know the better way to construct this kind of model format.
And don't forget to share your rendering result:)


[Yukikaze_PC_model_extractor_ver1.4.7z](https://xentaxbackup.github.io/file/8838_Yukikaze_PC_model_extractor_ver1.4.7z)
