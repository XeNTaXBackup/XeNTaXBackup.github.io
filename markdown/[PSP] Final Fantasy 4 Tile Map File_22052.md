## Post #1
- Username: travistrue
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2020 6:14 am
- Post datetime: 2020-04-22T09:49:17+00:00
- Post Title: [PSP] Final Fantasy 4 Tile Map File

I've been trying to figure out the tile map config file format, and I think I'm getting there... These files are all the little .cn2 files within the map directories. It looks like the the first 2 bytes of the file is the width of the map (in tiles), and the next 2 bytes is the height of the map. If I take the entire size of the file, and subtract 4 from it (the bytes that describe the width and height), then divide the result by 6, the final result is always equal to the width*height in every file. This leads me to believe that each tile in the map is described by 6 bytes.

Another thing I've noticed is that the file seems pretty dense with varying values for all odd bytes in the top 1/3 of the file, a value of 0, 1, or 2 for even bytes. The bottom 1/3 of the file is pretty much 0s for the majority of bytes except for a few things. All of the zeroes make a visual pattern easier to see in that bottom 1/3 of the file.

At the risk of comparing apples to oranges, I've been using the GBA version as reference since Everything has a really nice tile editor for the GBA release of the game. It's helped me make rough comparisons of the game, visually. The GBA version of the game seems to suggest that all tile maps have 3 layers: Layer 1, Layer 2, and a Triggers layer.

Given the 3 layers, every evem byte being 0, 1, 2 in at least the top 1/3 of the file, there's a 6:1 ratio between tiles in the map and bytes in the file, and the file's values start off dense and varied at the top, then it gets more sparse towards the bottom, my theory is these files store Layer 1 of information as an array of 2 8-bit values per cell in the first 1/3 of the file, Layer 2 is the middle 1/3 of the file, and the last 1/3 of the file is for the Triggers layer. Again, each cell in the tile map is represented by 2 bytes: the first byte being an index to look up the tile from the tileset, and the second byte being something completely different.

I'm writing a clone to FF4, so loading these maps up with cut down on manual work substantially. I've attached a screenshot of what it looks like when I load that map up into memory. It's far from perfect, but it feels like I'm close on getting Layer 1 to render correctly. I'm stuck on where to go next though.

Does anyone have any insight on the tile map format?
