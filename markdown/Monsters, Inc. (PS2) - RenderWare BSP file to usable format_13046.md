## Post #1
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-07-08T20:02:05+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

I really want these BSP models to be converted into a usable format, such as OBJ or 3DS. I'll attach one (it's 1.74 MB):

[https://www.dropbox.com/s/b2ajtolnrro2k ... t.bsp?dl=1](https://www.dropbox.com/s/b2ajtolnrro2k7m/basement.bsp?dl=1)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-09T05:03:35+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

quickhacked using hex2obj (view link in my sig):



basement_bsp.JPG (43.78 KiB) Viewed 306 times


vertex count for the submesh was 1483, so you'll need to use more FIs (face indices)

The '2' is the face indices offset to skip the fourth dummy FI (01 00).
## Post #3
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-07-09T06:46:41+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

Thank you! However, is there a way to get the entire model?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-09T07:43:28+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

pretty sure - but it's not me who will walk it...

but here's a correction for the first submesh:



basement_fst_SM.JPG (42.88 KiB) Viewed 152 times
## Post #5
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-07-10T00:31:33+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

Thanks for the help, nonetheless.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-11T13:59:11+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

FIs' start for the first SM seems to be 0xD0F6 (but doesn't change too much)

As I said it's rather simple to gain the submeshes if you invest some time (that I don't have)



basement_2nd.JPG (43.29 KiB) Viewed 270 times



(again FIs count may need some adjustment - I didn't really care...)
## Post #7
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-07-12T02:28:01+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

The bsp are RenderWare bsp files. You can use RWAnalyze to visualize them.
## Post #8
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-07-12T06:12:37+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

Yes, but I need them as a 3D model. And I tried RWAnalyze and didn't find such an option.
## Post #9
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2015-08-29T13:02:34+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

the best I can offer you now is my THPS3 BSP tool that I modified to support some Sonic the hedgehog game.
[http://www.mediafire.com/download/ithu5 ... 21sonic.7z](http://www.mediafire.com/download/ithu55fubjx9vbb/bsp2objv021sonic.7z)

unfortunately, it stumbles upon the face reading and only exports vertices for the first object. you can import the resulting OBJ into meshlab, it will show you the vertices.

even worse, I lost my delphi source of this tool almost year ago so I can't fix that (but it was too hardcoded for the sonic and I don't think it would've been an easy task).

a bit better news is that I have newer bsp tool written in c# and I might check if I can add support for this BSP file, but I can't actually promise you anything.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-30T11:14:29+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

I would have made a Make_H2O project of it but I'm a little bit tired 'cause noone really cares for this multimesh project.

Anyway here's the basement level with 30 submeshes:



basement_30SMs.JPG (172.24 KiB) Viewed 151 times



(I could upload the H2O files to be used with hex2obj's MultiMesh feature.)
## Post #11
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2015-08-31T12:15:01+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

is it like you manually add offset mapping for each model?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-31T13:03:09+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

it's one level (=model?) built with submeshes - I didn't add offsets


 basement_part1.zip
(202.58 KiB) Downloaded 20 times
## Post #13
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2015-09-01T19:53:55+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

is there bsp support in this hex2obj then?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-01T21:39:42+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

there's no built-in support. But I've a Make_H2O project for the basement level which creates these obj files (without uvs):


 basement_part2.zip
(213.09 KiB) Downloaded 30 times

(first part see my previous post)
## Post #15
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2015-09-02T14:58:51+00:00
- Post Title: Monsters, Inc. (PS2) - RenderWare BSP file to usable format?

> Reply from shakotay2
>
> there's no built-in support. But I've a Make_H2O project for the basement level which creates these obj files (without uvs):
basement_part2.zip(first part see my previous post)
i have no idea what that tool is. it looks like you provide it the offset to the mesh data and it extracts single mesh, so you have to "map" the file with custom offsets to extract whole mesh. am I wrong here?
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-02T20:34:12+00:00
- Post Title: Re: Monsters, Inc. (PS2) - RenderWare BSP file to usable for

> Reply from DCxDemo
>
> it looks like you provide it the offset to the mesh data and it extracts single mesh, so you have to "map" the file with custom offsets to extract whole mesh.that's a pretty good description how it works. Plus the "mapping data" is stored in H2O parameter files (human readable).
