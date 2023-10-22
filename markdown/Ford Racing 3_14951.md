## Post #1
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2016-08-27T22:28:19+00:00
- Post Title: Ford Racing 3

I'm exploring Ford Racing 3 formats and have some things, which I don't understand.

For all 3d models used certain group of files - XBX and DXT archives for meshes & textures. 
These files have Zlib compression, but in sample I provide already uncompressed.

Vertexes can be easy found in 3dobjsp.xbx  file. Starting from very beginning of file, it's seen very good.
 

Something looks like Vertex Indices contain other file with name 3dobjs.xbx . But there's no way I can combine it with vertexes, because indices repeats more times and even for "Strip" mode not give right result. 

bininfo.BIN contain names of meshes\submeshes, materials.

3dobjdb.bin file, within the meaning of, should contain some info like counts of vertexes and indexes, submeshes, textures, object types, offsets & etc, but I can't see something like that in file.

And 3dmodel.txt file, like Log file after model compile,  from which can discover names of submodels, textures, materials.

About textures from textures.DXT file i'm know nothing, because not get outside of graphics formats. So, maybe somebody can help me with it?

In attach cars models. Also In DEBUG folder some primitive objects like sphere and boxes.

[http://www.mediafire.com/download/q05n8 ... 90/CARS.7z](http://www.mediafire.com/download/q05n8y50r4s9f90/CARS.7z)
## Post #2
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2016-08-29T10:09:23+00:00
- Post Title: Ford Racing 3

So, no one haven't deal with similar? 

If not, then ok. Thanks for reading my post.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-29T19:26:58+00:00
- Post Title: Ford Racing 3

nasty format; small meshes, most of them with a vertex count of about 200 or less
(autocreation of FI's seems to be useless here)

If it's a PC game I'd suggest to try out a 3D ripper.
## Post #4
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-08-29T20:07:06+00:00
- Post Title: Ford Racing 3

3DSimED supports Ford Racing 3 format, did you take a look at it already?
