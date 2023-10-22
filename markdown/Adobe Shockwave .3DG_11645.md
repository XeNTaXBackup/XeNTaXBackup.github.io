## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-06-30T16:54:39+00:00
- Post Title: Adobe Shockwave .3DG

Most Adobe Shockwave games with 3D graphics seem to use .3DG as their model format. Here's some samples from Hey Arnold! Runaway Bus:
[http://puu.sh/9QSbg.zip](http://puu.sh/9QSbg.zip)
## Post #2
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-07-31T14:05:57+00:00
- Post Title: Adobe Shockwave .3DG

no one?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-31T19:41:30+00:00
- Post Title: Adobe Shockwave .3DG

You can display some structures using the point cloud feature of hex2obj (button PtCld)
vertices start address was 0x14 for the 3 samples I checked.
(00faddee.3dg)



00faddee.JPG (38.23 KiB) Viewed 162 times



For 00fce212.3dg I tried to build the faces but it's not "straight forward"
so it costs me too much time to complete this.

copy the following lines into an empty text file, rename it to test.obj
then do a wavefront import into your preferred 3d program.

# 0x14: verts= 50
v 0.282372 -0.235681 163.948578 
v -16.177330 -12.194359 151.141495 
v 6.569422 -19.585224 151.141495 
v 20.627687 -0.235681 151.141495 
v 12.844198 38.425655 0.000000 
v 40.933304 -0.235681 0.000000 
v 12.844206 -38.897011 0.000000 
v -32.604919 -24.129704 0.000000 
v 0.282372 -0.235681 0.000000 
v -16.177336 11.722995 151.141495 
v 40.933304 -0.235681 30.915201 
v 12.844198 38.425655 30.915201 
v 10.096304 -30.439846 129.132767 
v 32.040913 -0.235681 129.132767 
v 6.569418 19.113865 151.141495 
v -32.604927 23.658337 0.000000 
v 10.096304 -30.439846 36.139000 
v 32.040913 -0.235681 36.139000 
v 12.844206 -38.897011 30.915201 
v -32.604919 -24.129704 30.915201 
v -32.604927 23.658337 30.915201 
v 10.096299 29.968487 36.139000 
v 10.096299 29.968487 129.132767 
v -25.410824 -18.902885 36.139000 
v -25.410824 -18.902885 129.132767 
v -25.410830 18.431519 36.139000 
v -25.410830 18.431519 129.132767 
v -3.476418 -5.451734 168.995224 
v -3.476418 -5.451734 151.302704 
v 7.131316 0.672645 151.302704 
v 7.131316 0.672645 168.995224 
v -3.476419 6.797024 151.302704 
v -3.476419 6.797024 168.995224 
v 47.740120 0.191021 108.469688 
v 47.740120 15.818590 92.842117 
v -45.349716 15.818593 92.842117 
v -45.349716 0.191023 108.469688 
v -45.349709 -15.436549 92.842117 
v -45.349716 0.191021 77.214546 
v 47.740120 0.191019 77.214546 
v 47.740120 -15.436550 92.842117 
v -51.896393 0.191023 92.842117 
v 53.567806 0.191020 92.842117 
v -75.219528 -75.725426 0.000000 
v -75.219528 74.274574 0.000000 
v 74.780472 74.274574 0.000000 
v 74.780472 -75.725426 0.000000 
v -75.219528 -75.725426 300.000000 
v 74.780472 -75.725426 300.000000 
v 74.780472 74.274574 300.000000 
f 3 10 2 
f 11 6 5 
f 19 3 13 
f 18 13 14 
f 46 1 4 
f 24 16 5 
f 17 18 14 
f 8 7 19 
f 21 16 8 
f 5 16 21 
f 19 7 6 
f 18 22 23 
f 24 17 13 
f 26 24 25 
f 23 22 26 
#next faces unsure
## Post #4
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-07-31T22:51:10+00:00
- Post Title: Adobe Shockwave .3DG

I get this.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-01T22:43:16+00:00
- Post Title: Adobe Shockwave .3DG

you won't get more except someone will dig deeper into the face indices.

this is 00faddee with too many wrong faces:



00faddee_.JPG (71.38 KiB) Viewed 137 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-02T08:04:44+00:00
- Post Title: Adobe Shockwave .3DG

sometimes trying the unlogical is giving better results:



00ffaddee_ok.JPG (68.38 KiB) Viewed 129 times
## Post #7
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-08-02T15:20:25+00:00
- Post Title: Adobe Shockwave .3DG

so how do I do this? you aren't telling how it works
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-02T16:43:28+00:00
- Post Title: Adobe Shockwave .3DG

use hex2obj (view link in my sig) to get the vertices.

For the face indices search for the FFFFFFFF blocks. They have a size of 72 bytes normally
and the face indices are the last three DWords.

Since the block size varies (maybe 72 or 68 or 76 bytes) you'll need to be a coder to get the faces properly.

If you're not I would extract your preferred model if you told me its 3dg name.
## Post #9
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-08-02T18:59:07+00:00
- Post Title: Adobe Shockwave .3DG

[http://puu.sh/aBMtC.zip](http://puu.sh/aBMtC.zip)
Here's the ones I'd like. I've named them. I'm not a coder so I know nothing about this stuff. Would a quickbms script be possible?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-02T21:37:23+00:00
- Post Title: Adobe Shockwave .3DG

quickbms is more suitable for unpacker scripts so I'd prefer plain "C" for exporters.

This is Arnold: [http://www.uploadmb.com/dw.php?id=1407015005](http://www.uploadmb.com/dw.php?id=1407015005)

He's looking a little bit strange



Arnold.jpg (51.45 KiB) Viewed 94 times


So you may be required to erase some faces manually in the obj file.
If you find out which faces (f x y z lines) to be erased I could give the other chars a try.
Without that I wouldn't.

Maybe the face index selection (as explained in my previous post) is not suitable for characters. Don't have the time to check this.
## Post #11
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-08-02T23:19:23+00:00
- Post Title: Adobe Shockwave .3DG

[http://puu.sh/aC6vI.zip](http://puu.sh/aC6vI.zip)
here's some different models from SpongeBob SquarePants Saves The Krusty Krab. I think these are models of the level itself.
## Post #12
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-08-08T01:19:35+00:00
- Post Title: Adobe Shockwave .3DG

nobody? hex2obj is way beyond my level and I want to convert something for a Source map.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-08T09:57:42+00:00
- Post Title: Adobe Shockwave .3DG

what about "Arnold"? Did you check it?
## Post #14
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-08-08T15:41:00+00:00
- Post Title: Adobe Shockwave .3DG

yes I did. I've lost interest in the Hey Arnold models at the moment and are more interested in the SpongeBob Saves The Krusty Krab models.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-08T17:27:30+00:00
- Post Title: Adobe Shockwave .3DG

> Reply from lemurboy12
>
> yes I did. I've lost interest in the Hey Arnold models at the momenttoo bad that I took your request for serious...
