## Post #1
- Username: genwitt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 29, 2011 10:35 am
- Post datetime: 2011-11-29T03:12:23+00:00
- Post Title: RAGE (idtech5) .pages .pageLines information

I've been trying to decode the Rage megatextures, but I've gotten stuck, hopefully this will help someone.

The .pageLines file is a complete quadtree for the texture, one 2 byte little endian number per tile, there is no header.  The levels are stored in raster order.  -1 means 'no tile', it propagates from coarse to fine.  (if a level has a -1 tile, the corresponding tiles to all finer levels will all be -1.)  Negative numbers are unique, there is one in the entire stack, they occur in order starting with -32768.  Positive numbers occur multiple times.

The .pages file starts with a 32 byte header, numbers are all little endian.

```
----------------------------
0x00   int[4]    0x77339904
0x04   int[4]    size in tiles
0x08   int[4]    ?
0x0c   int[4]    log2(size in tiles)
0x10   char[2]   'UU'
0x12   char[6]   ?
0x18   int[4]    size of the file in bytes
0x1c   int[4]    0x0
```


Inside pages there is one tile for each unique image in the pageLines file.  They start with the magic cookie "04 ed bf ca", this cookie will be 2 byte aligned.  This is followed by a 4 byte integer, which is 0 for the first tile, and 5 for every other tile, I assume this is the number of images in the tile.

The mapping from pageLines value to offset into pages appears to be in a separate file.

The first image of every tile has "0000 7100 a3c7 8a3c 78a3 c780 ff00 0001" in it.  This appears to be the start of a JPEG XR, IMAGE_PLANE_HEADER starting at the 71, this header looks sane.  There are 4 000001 markers in each tile, it's my guess that these are TILE_STARTCODE markers from JPEG XR.

Tacking on a regular JPEG XR header and running the images through the JPEG XR reference decoder doesn't work.
## Post #2
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2011-11-30T03:13:43+00:00
- Post Title: RAGE (idtech5) .pages .pageLines information

I'm sorry to say that all of that is over my head. Nevertheless, I hope for the best from this. As I've posted elsewhere, I would love to apply those texture files to the models.
## Post #3
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-10T14:48:07+00:00
- Post Title: RAGE (idtech5) .pages .pageLines information

Any progress towards extract the textures from RAGE .pages files ?
