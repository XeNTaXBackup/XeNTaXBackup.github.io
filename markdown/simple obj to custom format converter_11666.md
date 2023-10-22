## Post #1
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-06T00:04:42+00:00
- Post Title: simple obj to custom format converter

Now iv spent quite a bit of time trying to figure out the format of the model - and iv got it down to bare minimum that is actually needed (my other thread).
But i lack any c++ or similar language skills to actually build a basic converter.

It doesn't need bones or animations.


```


struct mesh08
{
	
cstr [len=6] modelType; //MESH08
i16 numMesh; // number of models in the file
child mshblock [count=numMesh];
}

struct mshblock
{
cstr [len=100] objectName;
cstr [len=100] meshLink;

repeat 4 {
	i32 x;
	i32 x;
	i32 x;
	i32 x;
}
//D3DMATRIX 
repeat 4 {
	float X;
	float Y;
	float Z;
	float W;
}
repeat 4 {
	i32 x;
	i32 x;
	i32 x;
	i32 x;
}

i32 x;
i16 x;
cstr [len=200] texture; // must have drive,folder,filename like C:\tex\image.DDS
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i16 x;
i8 x;

i16 numVerts;
repeat numVerts
{
	//D3DXVECTOR4 x y z w
	float Vertex_x;
	float Vertex_y;
	float Vertex_z;
	float Vertex_w;
	//normals
	float normal_x;
	float normal_y;
	float normal_z;
	float normal_w;
	
	//uv map
	float tu1;
	float tv1;
	
	float tu2;
	float tv2;
	
	float tu3;
	float tv3;
	
	float tu4;
	float tv4;
}

//faces
i16 numFaces;
repeat numFaces 
{
i16 faceBuff;
}

i16 x; // 0
}
```


Here is the basic structure it has - where all the x values are 00 - filler.
i32 = 4bytes, i16 = 2bytes, i8 1 byte

The bone name can be filled manually in hex ( or a input in the converter?) same with the texture part.
Mainly need the matrix, vertex list ( vert, norm, uv) and face lis tafter that ( which is basically just a list of 2 byte values  with a max of vertexnum/3)
samplefile:
[https://mega.co.nz/#!7Y4HGKYI!y-6cdQJU- ... 4BKQoCGplE](https://mega.co.nz/#!7Y4HGKYI!y-6cdQJU-HTGR-WQ4BhrSHTli0w2HRx2L4BKQoCGplE)
## Post #2
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-07-06T14:06:22+00:00
- Post Title: simple obj to custom format converter

When I understood you right, you want a software that auto-imports obj-files, saves it's data and writes it in a custom format?

I think that's a nice idea. As I'm developing software for several years in C++, I would be ready to develop a small plugin-based software. It would be the easiest, when using simple DLL's as plugins, that can be written with poor C/C++-knowledge. But I don't know if beginners are going to do that.

Another option would be, to let the modders write their own plugins in python, but then the whole story is going to be more complex. Since then the software would need a python-interpreter like Boost::Python and and and...

So as you can see, this simple idea can easily grow to a bigger task. When several people here are going to like your idea, im ready to start developing.
## Post #3
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-06T15:44:22+00:00
- Post Title: simple obj to custom format converter

yeah -  i know php mainly btu thats not  a good option to deal with data intensive  job like that.

It would have to read all the data into into arrays - and then write it out based off the custom format structure.

The first part  would be common yea -  and not even too complicated. Then you could theoretically use plugins or some scripting language to allow the program write the data back into the custom file.
PHP would most likely crash trying to  parse several mb of 3d data.

In my case - actually all  it needs is 2 things - the 3d/texture data and matrix. The face list can be just generated ( divide vertex count by 3 and create a list of 2 byte numbers) - rest is just filler data and simple stuff.

Also - obj may not be the best option perhaps  ( since it has two files - mtl separately, so a bit more messy).
## Post #4
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-07-06T17:31:04+00:00
- Post Title: simple obj to custom format converter

If I'm following you, you want to take an OBJ file and convert it to another universal format...  Now this is where I get lost.

Just not sure I understand what the goal of this new file is.

-- MDA
## Post #5
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-06T17:45:53+00:00
- Post Title: simple obj to custom format converter

no this is far from universal format - its a custom format the game uses.
## Post #6
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-07-06T18:52:06+00:00
- Post Title: simple obj to custom format converter

Ok, understanding a little more.

Are you creating a game?  Are you attempting to import new models into an existing game?  Are you attempting to import models from one game to another?

Assuming the last, why not skip OBJ altogether?  If you know the formats of both it shouldn't be too much of a stretch to write something to go from one format to the other.  You cut out any middle-ware and are less likely to lose any information.

Learning a new programming language isn't that difficult if you have some programming background.  Visual Studio Express is free and powerful enough to help you learn while using.  I started out with BASIC on a C64 many years ago and have self-taught myself numerous languages over the years.  While I may not be the most efficient at programming, what I can do gets the job done.  Put your mind to it, and you can do anything.

-- MDA
## Post #7
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-06T19:31:18+00:00
- Post Title: simple obj to custom format converter

its new models into the game.

And cutting out  the conversion adds a lot of extra work - u would have to create a platform specific plugin for what ever 3d tool you are using ( for ex autodesk).

Also, are there easier formats to use besides obj ( that has similar structure already - instead of having separate  .obj and .mtl files).

Unless u know of something that would already take care of majority of it - so u would only have to deal with exporting the data to ur own format.
## Post #8
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-07-06T20:30:45+00:00
- Post Title: simple obj to custom format converter

> Reply from djmauro
>
> 
It would have to read all the data into into arrays - and then write it out based off the custom format structure.
With a plugin-system, there is a way more efficient way dealing with that.

> Reply from djmauro
>
> 
PHP would most likely crash trying to  parse several mb of 3d data.
Why should PHP crash? PHP is just fine as well as every language else. When configuring your server right, you can simply work with Gigabyte of data in PHP. There are just a few problems with multithreading, as that goes too far for PHP. (When I remember it correctly, that was a main-problem of PHP version <5?)

> Reply from djmauro
>
> 
The first part  would be common yea -  and not even too complicated. Then you could theoretically use plugins or some scripting language to allow the program write the data back into the custom file.
Don't understand me wrong, but as it seems, you really dont have any idea about softwareprogramming. So you shouldn't try to manage anything around that. Just try to support.

> Reply from djmauro
>
> 
Also - obj may not be the best option perhaps  ( since it has two files - mtl separately, so a bit more messy)
...
OBJ is just fine. Why should the seperate mtl-files be more messy? You just have to know if you want to support bone-animation or not, because OBJ only stores static meshes.
## Post #9
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-06T21:04:39+00:00
- Post Title: simple obj to custom format converter

> djmauro wrote:
>
> The first part  would be common yea -  and not even too complicated. Then you could theoretically use plugins or some scripting language to allow the program write the data back into the custom file.
>
> 
>
> Don't understand me wrong, but as it seems, you really dont have any idea about softwareprogramming. So you shouldn't try to manage anything around that. Just try to support.
Why is that?
There is nothing wrong with that way of doing things.
You would use your x language for the main part of the tool. 
You parse/read the data from  .. for ex. obj/mtl into arrays.
Now you have all the data.
You ether support user made  same language plugins to reformat and arrange the data for their file - or a simple scripting language that guides the tool to format it instead.

You often deal with ether binary or text based formats and mainly just loads of floats. Just in a different order with different indexing.

So im not sure where you took the " i have no idea about programming" - i do php, i can read  any language - even those i haven't seen before ( reverse engineering  purposes) - and do minor fixes.

I do not however simply have the experience to just write one from scratch and with  plenty of php work, reverse engineering  game file formats, hosting a server - and updating/maintaining it - i simply don't have the luxury to  learn  a language enough to write it from scratch.
## Post #10
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-07-06T22:15:43+00:00
- Post Title: simple obj to custom format converter

As I said, please don't understand me wrong. I'm sorry if you misunderstood me, there was no offense meant. Maybe there are some language-complications, english is not my mother-tongue   

What you wrote just sounded like: "you just have to do that and that... and then it is finished". Maybe that's what made my angry. Over the years I've got some bad expierence with people saying "lets do x, y, z" and in the end, you did everything, and they did nothing.

Just try to do the things, you are good at. And everyone else will too. Then things, like those little projects here, will be finished.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-07-07T15:51:02+00:00
- Post Title: simple obj to custom format converter

I would just use Noesis to write the converter. Then you can convert everything into your format.
## Post #12
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-07-07T18:59:50+00:00
- Post Title: simple obj to custom format converter

> Reply from finale00
>
> I would just use Noesis to write the converter. Then you can convert everything into your format.

Pretty much, i would just use Noesis for your needs, it can load and save in the formats you desire.

I'm not sure if saving as a format is supported tho, but it can open them.

If it doesn't it would be a nice idea to start considering doing it.
## Post #13
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-08T01:30:47+00:00
- Post Title: simple obj to custom format converter

noesis can read - that's what i used to reverse the format - but besides the c+ written dll or built in export supports... i don't see anything.. Not even documentation.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-08T01:33:58+00:00
- Post Title: simple obj to custom format converter

the included readme shows full export support i also did an xml export tutorial.
## Post #15
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-10T00:22:39+00:00
- Post Title: simple obj to custom format converter

i  may skip the obj and look at maxscript. anyone knows some decent tutorials  that covers binary format exporting on maxscripts (  so i can skip all the  100-s of basic tutorials - im overall quite familiar with scripting and programming by itself).
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-10T01:57:19+00:00
- Post Title: Re: simple obj to custom format converter

You just want to make an exporter to your custom game format right?
Use any language you want there are tons of example scripts for any 3d program you want.
blender, 3dsmax, noesis.
I am not sure what your looking for if you already know how to program why not just make your own converter?
