## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-22T12:29:26+00:00
- Post Title: Neverwinter Online .mset files

Hi guys! 
I'm looking for help with extracting files from Neverwinter .mset archives. I like the game much and I want to explore model format. If someone could take a look on those samples it would be great! Thanks in advance
[mset_samples.7z](https://xentaxbackup.github.io/file/7243_mset_samples.7z)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-04-23T06:01:26+00:00
- Post Title: Neverwinter Online .mset files

Zlib blocks with best compression

first one starts at 0x1C0 for Icespire_Dwarf_Statue_Head.mset

after that I can't make sense of the extracted data though
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-23T18:24:03+00:00
- Post Title: Neverwinter Online .mset files

Hi Cra0! Thanks a lot for info and help. I tried offzip on some files, and from one of them I've got a chunk which I think is a mesh itself. It has "NXSMESH" header and I see counts for verts/faces also something like vertex/index buffers? But I can't make any use of this files, it looks like encrypted?

Link to original file
[https://www.mediafire.com/?t25j5ibw6dsre2d](https://www.mediafire.com/?t25j5ibw6dsre2d)
[mesh_nxs.7z](https://xentaxbackup.github.io/file/7250_mesh_nxs.7z)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-23T20:30:27+00:00
- Post Title: Neverwinter Online .mset files

> Reply from zaramot
>
> It has "NXSMESH" header and I see counts for verts/faces also something like vertex/index buffers? But I can't make any use of this files, it looks like encrypted?NXS is the collisionmesh of PhysX. It contains a simplified copy of the original mesh for collision purposes. So not of that interest. (You can use PhysX SDK for creating an NXS file with the simplified mesh as an input.)
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-06-20T06:45:12+00:00
- Post Title: Neverwinter Online .mset files

Since, there's not much hope to get those models extracted, if anyone interested to do the job for money just contact me via PM to discuss details.Thanks
