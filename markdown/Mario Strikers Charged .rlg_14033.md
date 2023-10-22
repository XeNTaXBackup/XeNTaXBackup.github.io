## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2016-02-28T16:15:52+00:00
- Post Title: Mario Strikers Charged .rlg

I'm trying to figure out this in hex2obj, but I need help. Where's the start of the vertices?

[http://puu.sh/noB2s.rlg](http://puu.sh/noB2s.rlg)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-28T20:12:39+00:00
- Post Title: Mario Strikers Charged .rlg

Use big endian. Vertex start for example at 0x8E4, count: 123 gives some kind of point cloud.
Find a suiting face index block - the one starting at 0xB8 with 1041 FIs doesn't seem to fit (results in a vertex count of 278).
