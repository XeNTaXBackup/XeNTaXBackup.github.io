## Post #1
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-06-19T23:29:23+00:00
- Post Title: LittleBigPlanet 3 Background Scenery .smh

The backgrounds in LBP3 use a format called .smh, which I think stands for "squished model" or something of that sort, the format is very different from the format the models use. They're compressed, but after decompressing them, you get a file like these:

[http://puu.sh/ivoKi.out](http://puu.sh/ivoKi.out)
[http://puu.sh/ivrB7.out](http://puu.sh/ivrB7.out)

I tried using hex2obj on it with no luck, could someone help me out?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-21T05:38:56+00:00
- Post Title: LittleBigPlanet 3 Background Scenery .smh

env_caverns_out.JPG (39.37 KiB) Viewed 119 times

(first submesh only)
Do a hex search for 000000010002 to find the start addresses of the face indices blocks.

Here it's 94 submeshes.
So it will be a little bit tedious to build the whole mesh if you don't have basic skills in "C"
(to build a Make_H2O project) or maxscript.
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-06-30T18:43:26+00:00
- Post Title: LittleBigPlanet 3 Background Scenery .smh

I wrote a smh to obj converter in C#. I wasn't able to figure out the normals or uvs right now but I'll add them in if I do.
Most submeshes convert correctly, however few are messed up for unknown reasons.

Just drag an smh file into it and it will output an obj.
Also, these levels are high poly holy shit.

EDIT: I figured out what was causing the submeshes to mess up. They were using a mix of triangle strips and triangle lists.
Easy to implement by checking whether or not the strip has flipped and (stripSize % 6 == 0)
Still no uvs or normals though, got anything on that shakotay?


 smh2obj.7z
(5.05 KiB) Downloaded 24 times
## Post #4
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-07-03T18:06:57+00:00
- Post Title: LittleBigPlanet 3 Background Scenery .smh

whoa, wasn't expecting a whole program to convert them, thanks!

uv's and normals would be awesome though too if you can figure those out, shakotay?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-03T19:22:21+00:00
- Post Title: LittleBigPlanet 3 Background Scenery .smh

looks like half floats at UVpos=20 wich need some up scaling:



env_caverns_UVs.JPG (55.7 KiB) Viewed 66 times


(You'll need some fiddeling to get that displayed using hex2obj's UVs preview.)

HF-normals at offset 22 of the FVF block (did not check it in blender).
## Post #6
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-07-04T02:39:07+00:00
- Post Title: LittleBigPlanet 3 Background Scenery .smh

Okay I added the uvs in. Tried poking around in the buffer but couldn't get any good looking normals out.
Might be using packed normals (10 bits for xyz, pretty common on ps3/360) or whatever they're using.


 smh2obj.7z
(8.26 KiB) Downloaded 33 times
