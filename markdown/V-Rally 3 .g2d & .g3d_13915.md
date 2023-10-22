## Post #1
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-02-03T14:20:27+00:00
- Post Title: V-Rally 3 ".g2d" & ".g3d"

Data is packed mostly in ".bnk" archives, which is extractable using TDU tools (TDU and VR3 were both made by Eden Games)
I've attached what pops out after the extraction, a ".g2d" file which I guess is texture related, and a ".g3d" which should be the 3D part of the package.
A guy said (here >>> [viewtopic.php?p=97370#p97370](http://forum.xentax.com/viewtopic.php?p=97370#p97370)) these can be already imported, but I don't know how, and which tools are needed.
I've attached both files, original ".bnk" package included, just in case.

[http://www12.zippyshare.com/v/qu1KJPX5/file.html](http://www12.zippyshare.com/v/qu1KJPX5/file.html)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-03T17:11:15+00:00
- Post Title: V-Rally 3 ".g2d" & ".g3d"

well, you'll have to collect the faces of the submeshes somehow:



VR3_Cordoba.JPG (82.86 KiB) Viewed 172 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-03T19:52:27+00:00
- Post Title: V-Rally 3 ".g2d" & ".g3d"

using triangle strips it looks kinda better: 



Cordoba_TriStrips.JPG (28.85 KiB) Viewed 164 times



I'd think about creating a Make_H2O project but it would take too much time, I guess.
(As you may know in most cases I go for the first submesh only.)

Here the chassis could be done easily provided all models share the same format, FVF= 12 bytes, tristripped face indices (do they?).

The mesh is marked by 'GEOM' so its start is easy to be found.
But I don't know where to find the vertex count(s). For the first 6 (or 7) submeshes it should be 2802 or 2844 (0xB1C) in sum.

Also didn't check for uvs so far.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-04T13:09:43+00:00
- Post Title: V-Rally 3 ".g2d" & ".g3d"

just another lifetime wasting project?  
There are about 77 VFX objects with 147 submeshes (in sum).

I won't bother finding out the hierarchy ('HIER' sections), position offset can be found here, maybe, or in 'OBJ' sections.

I'll upload a tiny exporter sooner or later which will not care for positions, I guess:



Cordoba_VXF.JPG (52.87 KiB) Viewed 149 times

(upps, forgot about uvs, should be in UVF sections, nice format, though  )

(Did you try out a 3D ripper? From what I saw with 'Ride' (PC) it does not make sense
to dig in the hex data if you can get the model with a ripper.)
## Post #5
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-02-04T18:05:16+00:00
- Post Title: V-Rally 3 ".g2d" & ".g3d"

Yes, I've tried and the rip was screwed, something between the first pic and the second pic you posted
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-08T10:57:04+00:00
- Post Title: V-Rally 3 ".g2d" & ".g3d"

> Reply from Automotive Gaming
>
> Yes, I've tried and the rip was screwed,well, no surprise.  
There's some problems with analysing,  too many missing objects, some missing faces though I've made some progress:



cordoba.JPG (114.96 KiB) Viewed 128 times

(I know there's people on Xentax who could handle this better but I remember only one of them who cared for cars.)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-13T11:41:47+00:00
- Post Title: V-Rally 3 ".g2d" & ".g3d"

I managed to include the missing objects:



Cordoba_Lods.JPG (127.29 KiB) Viewed 94 times


(The uvs are a little bit refractory though they're floats.
When entering the parameters into hex2obj and clicking the 'UVs' button
after having loaded Cordoba.g3d  you'll see what I mean.)

Well, I could tell you that the uvs for this submesh probably start at 0x65818 with an UVB size of 8.

But you won't believe me that I found it by trial&error, will you?  
It's an offset of vertexcount*16 to the supposed original start address 0x634A8, ok.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-15T15:01:46+00:00
- Post Title: V-Rally 3 ".g2d" & ".g3d"

finally I got the uvs working somehow:



Cordoba_uvs.JPG (147.74 KiB) Viewed 78 times


(No time to check the first texture set.)
