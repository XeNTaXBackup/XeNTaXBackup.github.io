## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-03-22T21:08:46+00:00
- Post Title: LittleBigPlanet Karting .BIN

[http://puu.sh/gLm7B.BIN](http://puu.sh/gLm7B.BIN)

All of the models in the game are stored in this archive uncompressed. I gained a lot of hex2obj knowledge from LBP3, but this game separates the vertex data and face indices. I don't know what to do. A script aluigi wrote extracts everything as individual parts, but again, it separates all the vertex and face count data.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-22T21:46:35+00:00
- Post Title: LittleBigPlanet Karting .BIN

there's no mystery. it's just half floats:



TheGardensMP.JPG (38.57 KiB) Viewed 140 times
## Post #3
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-03-23T01:36:00+00:00
- Post Title: LittleBigPlanet Karting .BIN

Are UV's possible?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-23T07:34:44+00:00
- Post Title: LittleBigPlanet Karting .BIN

maybe here (not sure):



TheGardenMP_uvs.JPG (77.6 KiB) Viewed 125 times


For some strange reason most vtx values are in the range from -5.23 to 5.41 (instead of 0 .. 1.0)

edit: well, wrong texture set? Use 0xCDF4 for uv's start address.
## Post #5
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-03-23T19:51:45+00:00
- Post Title: LittleBigPlanet Karting .BIN


