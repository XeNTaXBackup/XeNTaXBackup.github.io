## Post #1
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2019-10-26T22:50:40+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

I am making this thread so i can try getting at the models from the demo, this runs on an updated version of the hedgehog engine and specifically the formats of the models was updated as well as the inclusion of the new .pxd format in which it will contain the skeleton and animations.

samples: [https://drive.google.com/file/d/1i4-2nT ... sp=sharing](https://drive.google.com/file/d/1i4-2nTELbegGDbxD6q3-8eeeomh-w4wq/view?usp=sharing)

these models work in modelfbx but it needs modifications to support this game, but here is an example of the mesh.
[peach_surf.png](https://xentaxbackup.github.io/file/16945_peach_surf.png)
## Post #2
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2019-10-27T14:29:28+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

Anyone.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-27T15:56:18+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

> Reply from ChaoticFusion40 ↑Sun Oct 27, 2019 6:50 am at Sun Oct 27, 2019 6:50 am
>
> these models work in modelfbx but it needs modifications to support this gamedunno what you mean exactly?

(Here's a .model file extracted:



peach_M_surfing-model.png (110.27 KiB) Viewed 603 times

)
## Post #4
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2019-10-27T20:34:28+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

can't wait till someone can make a tool to extract them to .smd or fbx
## Post #5
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2019-11-23T14:55:51+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

Tried sky's modelfbx on this as well, getting similar results. Vertices, weights, bones are all fine, so it seems to be a matter of face indices only.
Had a look at model.cpp but couldn't make it work.

> Reply from shakotay2 ↑Sun Oct 27, 2019 11:56 pm at Sun Oct 27, 2019 11:56 pm
>
> 
ChaoticFusion40 wrote: ↑Sun Oct 27, 2019 6:50 amthese models work in modelfbx but it needs modifications to support this gamedunno what you mean exactly?

(Here's a .model file extracted:

Shakotay, What was your process of finding the offset/count here? I figure there will be a ever so slight difference to LibGen's [model::getFaceList()](https://github.com/blueskythlikesclouds/libgens-sonicglvl/blob/experimental/src/LibGens/Model.cpp), but what?

There's a "FF FF FF FF FF FF FF FF FF FF FF FF" part a few bytes before the faces start, could that be used as an achor?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-23T16:19:40+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

> Reply from Jaw ↑Sat Nov 23, 2019 10:55 pm at Sat Nov 23, 2019 10:55 pm
>
> Shakotay, What was your process of finding the offset/count here?Nothing special - had a look at the file, some trial 'n error, ready (for one submesh only).

> There's a "FF FF FF FF FF FF FF FF FF FF FF FF" part a few bytes before the faces start, could that be used as an achor?skip 6 zero bytes after it, then search for the first "00 st 00 uv 00 wx 00 yz" sequence as a face indices start.

Might work, didn't test it (st, uv,.. = any byte values, "wildcard").

Another (better?) approach:
(as an example, bytes before face indices start:)
00 00 00 01 00007540 00 00 00 03 00007544, i.e. 
search for 00 00 00 ab 00 00 cd ef 00 00 00 gh 00 00 ij kl

Then the face indices to follow.
## Post #7
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2019-11-23T18:11:40+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

> Reply from shakotay2 ↑Sun Nov 24, 2019 12:19 am at Sun Nov 24, 2019 12:19 am
>
> 
skip 6 zero bytes after it, then search for the first "00 st 00 uv 00 wx 00 yz" sequence as a face indices start.

Might work, didn't test it (st, uv,.. = any byte values, "wildcard").

Thanks! This actually worked on the _L file as well. The second aproach looks good too, but seems much harder to spot manually right now.

One question though, if I may: the Surfing_L.model file is nearly twice as big as the _M file, yet there's apparently merely 73 verts difference between them. Any clue what could be causing blow-ups like that? Hope I'm not missing some important content.

PS: just realized her crown is literally skewering her head! yikes
[MarioSonicMurderCrown.png](https://xentaxbackup.github.io/file/17105_MarioSonicMurderCrown.png)
## Post #8
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2019-11-23T18:33:00+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

Ok, found the problem: looks like there's more than one blocks of faces/verts contained in each of these .model files. 
Even just getting out one complete model is gonna suck without automation.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-23T19:34:55+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

> Reply from Jaw ↑Sun Nov 24, 2019 2:33 am at Sun Nov 24, 2019 2:33 am
>
> Even just getting out one complete model is gonna suck without automation.Shouldn't be a big deal using the Make_obj project (basic knowledge of 'C' required).

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 

Once you've got the start address of face indices (FIstart) 
start_of_vertices = FIstart + FIcount x 2

(works for peach_M_surfing.model at least and your "MarioSonicMurderCrown")
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-11-24T00:11:12+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

Here is a small tool that extracts the meshes as obj. Drag and drop the ".model" file on the exe and it will export the objs in a new folder. I made it really quickly, so not much error handling. Seems to work fine with the uploaded samples.



The format doesn't look too hard. I might make a proper tool with skeleton/skinning if I find the time.
[MSOModExp.rar](https://xentaxbackup.github.io/file/17106_MSOModExp.rar)
## Post #11
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2020-08-01T23:59:15+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

> Reply from akderebur ↑Sun Nov 24, 2019 8:11 am at Sun Nov 24, 2019 8:11 am
>
> 
Here is a small tool that extracts the meshes as obj. Drag and drop the ".model" file on the exe and it will export the objs in a new folder. I made it really quickly, so not much error handling. Seems to work fine with the uploaded samples.



The format doesn't look too hard. I might make a proper tool with skeleton/skinning if I find the time.

since the game is released, can you make a tool to convert them to either ascii or fbx.
## Post #12
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2021-08-09T21:21:22+00:00
- Post Title: Mario And Sonic at the Olympic Games Tokyo 2020 Demo (.model)

Hi,

Can you make the tool so it extracts out the bones with the skin please?

Thanks,
