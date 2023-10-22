## Post #1
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-02T14:38:09+00:00
- Post Title: Cryengine weird vertex format

Hi everyone,

I have found an interesting data structure for newer Cryengine games that is a confusing me.  It's a 16 byte structure that's part of an unknown datastream, but I'm thinking it contains vertex, normal and UV information... or some subset of that.  Here is a few samples:

00 48 ea 2a 54 bc 00 3c ff ff ff ff 32 40 df b4  
a3 44 ea 2a c0 38 00 3c ff ff ff c3 95 bc ba b4  
a3 44 40 29 b1 38 00 3c ff ff ff fa 93 bc f0 b4  
00 48 4a 2c 5d bc 00 3c ff ff ff ff 33 40 aa b4 
00 48 40 29 5d bc 00 3c ff ff ff ff 33 40 14 b5 
a3 44 4a 2c b1 38 00 3c ff ff ff e5 93 bc 84 b4  
00 48 4a 2c 6e bc 00 3c ff ff ff ff 36 40 75 b4 
a2 44 40 29 92 38 00 3c ff ff ff ff 91 bc 27 b5  
00 48 40 29 6e bc 00 3c ff ff ff ff 36 40 49 b5  

Link to a the sample file:  [https://dl.dropboxusercontent.com/u/816 ... ail_01.cgf](https://dl.dropboxusercontent.com/u/81602544/uee_asteroid_ACTutorial_rail_01.cgf)
The data starts at 0x06a4.

In the old way Cryengine had a separate datastream for Vertices, Normals, UVs, Indices and Tangents.  The new way just has the unknown stream, Indices and Tangents.  The number of elements in Tangents matches the ones in the new datastream, which is good.  It means that the 16 byte elements contains (most likely) the vertex info, as well as maybe the UV and maybe the normals.

The problem with using just Half numbers is the FF FF is NaN.  Which probably isn't the answer then.  Thoughts?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-02T15:32:05+00:00
- Post Title: Cryengine weird vertex format

using hex2obj (view link in my sig):
[uee_asteroid.JPG](https://xentaxbackup.github.io/file/9479_uee_asteroid.JPG)
## Post #3
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-02T17:01:38+00:00
- Post Title: Cryengine weird vertex format

Ok, I think I'm getting it...  3 floats for the vertices, 2 half floats for the UVs?

Grr...nope
0.0000000 0.0078574 NaN 2.0976560 -0.3044434
0.0000000 0.0078260 -512.0000000 -1.1455080 -0.2954102
0.0000000 0.0078260 -664614000000000000000000000000000000.0000000 -1.1435550 -0.3085938

Got it I think....
3 half float vertices, 2 half float UVs at the 12th byte.  No idea what bytes 7-11 are though.

Thanks, Shakotay!

edit:  Bingo!
