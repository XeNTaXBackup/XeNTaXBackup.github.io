## Post #1
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2019-03-14T21:28:00+00:00
- Post Title: Xenoblade Map Meshes

Is anyone still interested in xenoblade 2 maps? I'm poking around the files but could use some help. I haven't fully figured out the UVs and the chunk ordering. There is a chunk data for the vert info and chunks for the face info. How the two match together i'm not sure and have been manually pairing them so far. The face chunk data changes in size depending on the type of data it is. Some larger chunks i suspect of having vertex colors and probably custom normal data.



At the time of the screenshot i got through about 51 of the 132 chunks in the file even though i skiped the UVs


The header is always 0x1000 bytes. first four dwords are mesh table offset, mesh count, face table offset, face count. 32 byte seems to be the most common chunk size for the vert info. Attached is the raw file

File i used for picture above:
[https://drive.google.com/open?id=1hWYzG ... p8wLwzoLS6](https://drive.google.com/open?id=1hWYzGnXSHROj5B71CVnjAJp8wLwzoLS6)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-15T09:44:31+00:00
- Post Title: Xenoblade Map Meshes

> Reply from pox911 ↑Fri Mar 15, 2019 5:28 am at Fri Mar 15, 2019 5:28 am
>
> I'm poking around the files but could use some help. I haven't fully figured out the UVs and the chunk ordering. There is a chunk data for the vert info and chunks for the face info. How the two match together i'm not sure and have been manually pairing them so far.[...]

The header is always 0x1000 bytes. first four dwords are mesh table offset, mesh count, face table offset, face count. 32 byte seems to be the most common chunk size for the vert info.You need to go to details, noone will start from scratch again.
Starting with 0xAF75 (44917 dec.) at file offset 0x54
you can calculate these adresses at 0x70, 0x90, 0xB0:

44917x32= 0x15EEA0
50335x32= 0x1893E0 -> 0x2E8280 (= 0x15EEA0+ 0x1893E0)
2439x20= 0xBE8C    -> 0x2F410C

but guess you know this already.

UVs look a little bit stretched:



m04_6_.png (27.07 KiB) Viewed 74 times


(44575 is just a quickhack, might be 44917)
## Post #3
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2019-03-15T18:52:37+00:00
- Post Title: Xenoblade Map Meshes

i kinda posted it in a bit of a hurry before work so that is partly  my bad. The first 4 DWords are mesh table offset, mesh table length, face table offset, face table entries. Mesh table seems to be 0x20 bytes long with the first dword being the offset of the mesh table if it started at 0, so just add 0x1000 to it. Second dword is the number of entires. Third dword is the size of the chunks. This number varies with the 4th entry being only 24 bytes in size instead of the usual 32. The other two values in the mesh table i haven't figured out yet.

The face table is pretty similar with the first dword being the offset and the second being the count.

Its how the face table relates to what mesh chunk that i haven't figured out.

When i poked the uvs, i got something similar, i just wasnt sure if it was correct.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-16T08:30:34+00:00
- Post Title: Xenoblade Map Meshes

> Reply from pox911 ↑Sat Mar 16, 2019 2:52 am at Sat Mar 16, 2019 2:52 am
>
> Its how the face table relates to what mesh chunk that i haven't figured out.Yep, the hard part.
vertices are simple, 14 blocks (need to add 0x1000 to each start address):
# 0 44917, FVFsize: 32
# 15eea0 50335, 32
# 2e8280 2439, 20
# 2f410c 3399, 32
# 30e9ec 7768, 32
# 34b4ec 8707, 32
# 38f54c 48, 28
# 38fa8c 165, 32
# 390f2c 17, 20
# 391080 14749, 44
# 42f77c 190, 52
# 431e14 24, 60
# 4323b4 44, 36
# 4329e4 36, 24
vertex sum: 132838

131 FI blocks which have different lastFIs: 43871, 44575, 44584, 44827, 44864, 44867, 44878 
from submesh 15 to 131: lastFI= 50335 (maybe combine them with vertex block 0x15fea0 50335)

So you can't use lastFI as offset for the next FIs' block as you would normally do.

For me it looks ok up to submesh 14 (# 14. 0x45e244, FI count: 3249).
So the question would be: why is submesh 15 spoiled (# 15. 0x45fba8, 27360)?



m04_6_more.png (156.35 KiB) Viewed 53 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-16T08:48:08+00:00
- Post Title: Xenoblade Map Meshes

submesh_15 is ok now:



submesh_15.png (71.6 KiB) Viewed 47 times



H2O file for submesh 16:

0x477B0C 39987
Vb1
32 12
0x15FEA0 48528
020000
0x0 255

submesh 51 is using vertex block 6:

0x4AFA38 11151
Vb1
32 12
0x34C4EC 8523
020000
0x0 255
## Post #6
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2019-03-17T07:02:32+00:00
- Post Title: Xenoblade Map Meshes

I'm just wondering if another file has extra info pertaining to this one when it comes to how to tell which submesh goes to which block. There should be one about what materials go where. I just look forward to this being automated once enough info can be figured out.
