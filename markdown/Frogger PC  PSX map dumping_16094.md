## Post #1
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2017-04-05T20:10:59+00:00
- Post Title: Frogger PC / PSX map dumping?

I've been trying to use hex2obj to view the maps from Frogger. Here's what I've managed to figure out.

I can construct a point cloud of the file attached below by using this info:

step2: Vertex Block
FVFSize = 8

Start Address = 2d2e0 (A few bytes after the word "VRTX")
Count = 4935 (The first two bytes after "VRTX" reversed then converted into decimal create this number.)
ShortAll

Could someone help me fill in the rest of the data to get a complete model?

Can't upload .MAP files, so here's a dropbox link. [https://www.dropbox.com/s/1edg4pw02qy7ayv/FOR2.MAP?dl=0](https://www.dropbox.com/s/1edg4pw02qy7ayv/FOR2.MAP?dl=0)
