## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-12-03T09:08:41+00:00
- Post Title: Help with 3dcgarts webgl models

I am interested in models from 3dcg-arts.net

you can get the models by using
[http://www.3dcg-arts.net/api/model/get/ ... ormat/XXXX](http://www.3dcg-arts.net/api/model/get/three_format/XXXX)

were you replace XXXX with the number of the model
for example I used 
[http://www.3dcg-arts.net/art/3687](http://www.3dcg-arts.net/art/3687)

so the link to the model would be
[http://www.3dcg-arts.net/api/model/get/ ... ormat/3687](http://www.3dcg-arts.net/api/model/get/three_format/3687)

Anyway, looking in the file and sorting the numbers after "faces:" I get something like

```
42,  5,6,4			,2,		4,5,6,1,1,1,
42,  6,7,4			,2,		5,7,6,1,1,1,
42,  7,8,4			,2,		7,8,6,1,1,1,
42,  8,9,4			,2,		8,9,6,1,1,1,
42,  9,10,4		  ,2,		9,10,6,1,1,1,
42,  10,5,4		  ,2,		10,4,6,1,1,1,
43,  13,14,12,11	,2,		11,12,13,14,2,2,2,2,
43,  15,16,14,13	,2,		15,15,12,11,3,3,3,3,
43,  19,20,18,17	,2,		11,12,13,14,4,4,4,4,
43,  21,22,20,19	,2,		15,15,12,11,5,5,5,5,
43,  25,26,24,23	,2,		11,12,13,14,6,6,6,6,
43,  27,28,26,25	,2,		15,15,12,11,3,3,3,3,
43,  31,32,30,29	,2,		11,12,13,14,7,7,7,7,
43,  33,34,32,31	,2,		15,15,12,11,5,5,5,5,
43,  37,38,36,35	,2,		11,12,13,14,8,8,8,8,
43,  39,40,38,37	,2,		15,15,12,11,3,3,3,3,
43,  43,44,42,41	,2,		11,12,13,14,9,9,9,9,
43,  45,46,44,43	,2,		15,15,12,11,10,10,10,10

```


What I want is something that can look for the the first 4 numbers after a 43, for example "2,3,1,0", add one to the numbers, making it "3,4,2,1", and writing it out as
3/3/3 4/4/4 2/2/2 1/1/1

For every 42 I want it to do the same except only to the first 3 numbers after it.

So doing that to the text above I should get

```
6/6/6 7/7/7 5/5/5
7/7/7 8/8/8 5/5/5
8/8/8 9/9/9 5/5/5		
9/9/9 10/10/10 5/5/5		
10/10/10 11/11/11 5/5/5
11/11/11 6/6/6 5/5/5
14/14/14 15/15/15 13/13/13 12/12/12
16/16/16 17/17/17 15/15/15 14/14/14
20/20/20 21/21/21 19/19/19 18/18/18
22/22/22 23/23/23 21/21/21 20/20/20
26/26/26 27/27/27 25/25/25 24/24/24
28/28/28 29/29/29 27/27/27 26/26/26
32/32/32 33/33/33 31/31/31 30/30/30
34/34/34 35/35/35 33/33/33 32/32/32
38/38/38 39/39/39 37/37/37 36/36/36
40/40/40 41/41/41 39/39/39 38/38/38
44/44/44 45/45/45 43/43/43 42/42/42
46/46/46 47/47/47 45/45/45 44/44/44

```


Is there an easier way to do thing than by hand? Some kind of tool I can use?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-03T11:50:44+00:00
- Post Title: Help with 3dcgarts webgl models

hmm, I thouht the bold groups being the faces; m maybe the material value.

43,  2,3,1.....0..(m=1)..0,1,.....2,3,0.....0,0,0
42,  5,6,4.....(m=2).....4,5,6.....1,1,1,

so it's

```
f 1 1 2
f 3 4 1
f 6 7 5
f 5 6 7
```

looked like triangle strips. But the object I got still having some hollow faces.

So I used your strange mix of triangles and quads and bingo:
astonishingly it's ok: [](http://www.pic-upload.de/view-21515233/bingo.jpg.html)

btw: any "public tool" might violate the copyrights of the model owners.
([viewtopic.php?f=16&t=10668&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=10668&start=15)) Nov. 18th
## Post #3
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-12-03T12:08:28+00:00
- Post Title: Help with 3dcgarts webgl models

Lines starting with 43 are quads and lines starting with 42 are tris.
What I posted was correct.

Ignoring the UVs and normals I got this


[https://www.dropbox.com/s/yh7ce72cenc89m9/3687test.obj](https://www.dropbox.com/s/yh7ce72cenc89m9/3687test.obj)

All I really need is a way to automate the processes I explained in the first post rather than fixing each line one by one.


Edit:
Well I'm not looking to share the models or use them as my own. 
All I really want to to extract some of them to use as reference material, but I can see how it could violate copyrights.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-03T12:13:11+00:00
- Post Title: Help with 3dcgarts webgl models

> Reply from o0DemonBoy0o
>
> What I posted was correct.That is what I wrote:

> So I used your strange mix of triangles and quads [...] astonishingly it's ok.

> All I really need is a way to automate the processes I explained in the first post rather than fixing each line one by one.You'll need skills in a programming language.

edit: I could send you some "C" code which performs the "data sorting" but which does not extract the models.
Do you think you could compile it using CodeBlocks for example?
## Post #5
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-12-03T12:20:03+00:00
- Post Title: Help with 3dcgarts webgl models

> Reply from shakotay2
>
> That is what I wrote:
you edited you post as soon as I posted that

> You'll need skills in a programming language.

Yeah, that's what i'm lacking.
I'm not sure what to use or how to start.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-03T12:27:23+00:00
- Post Title: Help with 3dcgarts webgl models

> Reply from o0DemonBoy0o
>
> you edited you post as soon as I posted thathmm, I edited it before I read your post, I swear.  

> Yeah, that's what i'm lacking.
>
> I'm not sure what to use or how to start.Ok, let's start with an exe file. Will take some time to PM it. - edit: DONE
