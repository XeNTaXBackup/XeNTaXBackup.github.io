## Post #1
- Username: DYXiCZ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 28, 2014 1:38 pm
- Post datetime: 2015-01-30T19:34:20+00:00
- Post Title: Flatpyramid.com .json files

Hi everyone.
I would like to ask you for help.
I found way to get models from flatpyramid.com but is in .json format.
I tried several json importers/convertes but without result, noone works.

Here are several files: [Direct download](http://www.img.tpx.cz/uploads/FLATPYRAMID.rar)
Files isn't crypted (you can read the vertex positions via noteblock etc..)
Way for get the models from the site is so easy because they uses webgl 3d live preview.
(Same as stuner etc.. but in .json)

Would be useful for lots of us.
Thanks for help.
Regards,
DYXiCZ

PS: Sorry about my english, but i tried my best
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-31T11:26:51+00:00
- Post Title: Flatpyramid.com .json files

the jsons contain plain ASCII. Not too hard to code an ASCII-json to obj converter on your own.

"faces": [[	 0	,1	,2],[	 1	,34	,50],[	 34	,35	,36],

"vertices": [ -623.377,7.41711,252.529,

"normals": [ -0.898899,0.00128903,0.438153,

"tangents": [ -0.0722054,-0.98676,-0.145231,

"bitangents": [ 0.438153,-0.000278509,0.8989,


but both, using normal face indices or tristrips give a strange result (one submesh only):



ARKVIZ-json.jpg (104.93 KiB) Viewed 176 times

 (while the point cloud looks interesting)
## Post #3
- Username: DYXiCZ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 28, 2014 1:38 pm
- Post datetime: 2015-05-11T18:02:26+00:00
- Post Title: Flatpyramid.com .json files

Oh, iam so sorry i forgot to this topic.

I really don't know how to script Json-ASCII to OBJ converter.
I am not scripter, that's why i honestly ask there.
Please, it would be useful for a lot of peoples, on flatpyramid is a lot of cars.
For modders and semi-modellers (i modelling a lot of things on cars but full car is still hard for me)
it would be great news.

 Thanks for any help.
Regards,
DYXiCZ
