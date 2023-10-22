## Post #1
- Username: headgehof
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jun 27, 2010 10:11 pm
- Post datetime: 2012-08-17T20:48:23+00:00
- Post Title: help webgl 3d format identify

Hi, can someone help me identify this 3d format. Its ascii from a webgl.
Thanks
[2173.rar](https://xentaxbackup.github.io/file/5682_2173.rar)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-17T22:10:54+00:00
- Post Title: help webgl 3d format identify

I don't understand what you need to identify. It's ASCII. You just read it off.
Since you know it's webgl you just need to get a copy of webgl and pass in the data.
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-17T22:34:49+00:00
- Post Title: help webgl 3d format identify

Yeah this is actually the easiest one ever 

mqo based data

if you open it in notepad++ and put some carrage returns in it you get this:

```
	"colors":[],
	"edges":[],
	"faces":[[43,21,5,41,...,3051,2677,2677]],
	"materials":
	[
	{
		...
		"mapDiffuse":"\u5e8a.bmp.jpg",
		...
	}
	]
	"normals":[[0.6124,-0.2346,-0.7548,...,0.7993]],
	"scale":100.0,
	"uvs":[[[0.0,0.0,0.8333,0.4285,...,0.7751,0.4182,0.8073]]],
	"version":2,
	"vertices":[[1.5155,88.8848,...,-0.0377,85.8348]]};

```


I removed most of the data just to pin point the relevant data

T.
## Post #4
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-18T16:51:05+00:00
- Post Title: help webgl 3d format identify

I was wondering and interested in what kind of a model this was....

but then I took a look at the faces list...

and after a few entries I got a question

43,21,5,  41,57,2,  0,0,0,  0,0,1,  1,0

how can you have a face ( triangle)  that is indexed 0,0,0 ???   

also, the number of faces in the list is not a multiple if 3 ...

T.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-18T17:27:46+00:00
- Post Title: help webgl 3d format identify

The faces are not just vertex indices. If you were to say it is mqo-based, the face stores UV indexes and material index as well. And other info. It would be easiest to just download the parser FROM the website where he got the model from and then just copy the methods.

Here's what we got before without bothering to look at source code.

[viewtopic.php?p=70351#p70351](http://forum.xentax.com/viewtopic.php?p=70351#p70351)

Though, at this point, I think if people REALLY want the models, they might as well just grab the source code and send the output to an OBJ exporter or something.

However the script is minimized so figuring out what's going on might be a little tricky.

Oh, it also supports animation. webgl is quite amazing.

It's kind of interesting how fast javascript could load that thing. I tried parsing it in python and it just took forever. Or maybe cause I was converting everything to bytes...
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-18T19:13:03+00:00
- Post Title: help webgl 3d format identify

Damn finale00, you are quite amazing   

Thanks anyways

T.
## Post #7
- Username: headgehof
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jun 27, 2010 10:11 pm
- Post datetime: 2012-08-18T21:29:17+00:00
- Post Title: help webgl 3d format identify

Thank you for the help. This is the script that loads the model.
Anyone know how i can execute it and convert the model from js to mqo?
[loader.rar](https://xentaxbackup.github.io/file/5685_loader.rar)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-19T02:14:52+00:00
- Post Title: help webgl 3d format identify

> Anyone know how i can execute it and convert the model from js to mqo?

Programming?
