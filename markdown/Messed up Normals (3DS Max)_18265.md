## Post #1
- Username: ItchyDani3l
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 29, 2016 3:20 pm
- Post datetime: 2018-06-20T22:55:55+00:00
- Post Title: Messed up Normals (3DS Max)

I have a large collection of very stubborn models which I've successfully extracted from a game archive, only to run into an issue with the normals.
Unfortunately, the game I intend to use these models in has single-sided faces, meaning the normals must be correct.

Here's the sample OBJ model and PNG texture:
[https://pastebin.com/raw/iVaKF401](https://pastebin.com/raw/iVaKF401)
[https://orig00.deviantart.net/328f/f/20 ... ceyg6b.png](https://orig00.deviantart.net/328f/f/2018/171/7/0/uhulk_by_itchydani3l-dceyg6b.png)

Here's a list of things I've tried: (none of them worked)
-Importing normals from file and Unifying
-Using Auto-normals and Unifying
-Welding vertices first, and then Unifying
-Welding vertices, exporting, importing with auto-normals, and then unifying

Does anyone have any ideas to fix these?
## Post #2
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-06-21T13:08:14+00:00
- Post Title: Messed up Normals (3DS Max)

I had a quick look and I can say it probably isn't the normals. 
If you check your geometry (move points, for example), you will see it's really bad and some vertexes do not weld together when they should, creating this awful effect. 
You will need a lot of patience to fix this..
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-21T13:53:50+00:00
- Post Title: Messed up Normals (3DS Max)

> Reply from lolwatt
>
> I had a quick look and I can say it probably isn't the normals. 
If you check your geometry (move points, for example), you will see it's really bad and some vertexes do not weld together when they should, creating this awful effect.
You can't expect a 3D app to weld two vertices belonging to two triangles of opposite normal vectors.

> Reply from lolwatt
>
> You will need a lot of patience to fix this..
I wouldn't say so since it's rather simple to solve via several lines of code.

The only reason causing this issue is that the model is double sided.
A few lines of the face indices from the beginning:

```

f 9/9 18/18 1/1
f 18/18 9/9 1/1

f 1/1 18/18 10/10
f 18/18 1/1 10/10

f 1/1 10/10 11/11
f 10/10 1/1 11/11

f 11/11 10/10 10/10
f 10/10 11/11 10/10

f 11/11 10/10 2/2
f 10/10 11/11 2/2

f 2/2 10/10 19/19
f 10/10 2/2 19/19

f 2/2 19/19 3/3
f 19/19 2/2 3/3

f 3/3 19/19 20/20
f 19/19 3/3 20/20

f 3/3 20/20 3/3
f 20/20 3/3 3/3

```

As you can see, the first triangle is followed by the same one of opposite orientation, which defines the orientation of the face normal vector. And this pattern repeats till the end of the face buffer. Now you can imagine why the model looks like a mess when you try to load this into Max.

Edit:
Here is a simple QuickBMS example script that can get you a better result from the existing obj files:

```
set Side1 Name
set Side2 Name
string Side1 + "_side1.obj"
string Side2 + "_side2.obj"

findloc Offset binary "\x66\x20"
log Side1 0 Offset
log Side2 0 Offset
append
set Size long 0
goto Offset
do
	savepos Offset1
	findloc Offset2 binary "\x0D\x0A"
	goto Offset2
	get Linefeed short
	savepos Offset2
	xmath Size "Offset2 - Offset1"
	log Side1 Offset1 Size
	
	findloc Offset1 binary "\x0D\x0A"
	goto Offset1
	get Linefeed short
	savepos Offset1
	xmath Size "Offset1 - Offset2"
	log Side2 Offset2 Size
	
	findloc Offset binary "\x66\x20"
while Offset != ""
```
## Post #4
- Username: ItchyDani3l
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 29, 2016 3:20 pm
- Post datetime: 2018-06-21T17:35:11+00:00
- Post Title: Messed up Normals (3DS Max)

You're right, every face was duplicated in reverse.

Thanks so much for your help!
