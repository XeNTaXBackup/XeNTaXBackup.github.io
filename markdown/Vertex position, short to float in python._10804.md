## Post #1
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-26T00:54:25+00:00
- Post Title: Vertex position, short to float in python.

I've been looking some Noesis scripts for importing models and to my surprise vertex position in many type of meshes are stored in short bytes.
Of course I can't use that data to an importer, I wonder how to translate that into python?

I found this explanation below in the opengl website (although the game I checked used directx) but honestly I don't understand it much. Noesis seems to do it automatically when RPGEODATA_SHORT is used? 
like: rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_SHORT,vertStride, 0)

> Positions
>
> These are fairly hard to pack more efficiently than GL_FLOAT​, but this depends on your data and how much work you're willing to do. You can employ GL_HALF_FLOAT​, but remember the range and precision limits relative to 32-bit floats.
>
> A time-tested alternative is to use normalized GLshorts. To do this, you rearrange your model space data so that all positions are packed in a [-1, 1] box around the origin. You do that by finding the min/max values in XYZ among all positions. Then you subtract the center point of the min/max box from all vertex positions. Followed by scaling all of the positions by half the width/height/depth of the min/max box. You need to keep the center point and scaling factors around.
>
> When you build your model-to-view matrix (or model-to-whatever matrix), you need to apply the center point offset and scale at the top of the transform stack (so at the end, right before you draw). Note that this offset and scale should not be applied to normals, as they have a separate model space.

Any help on how to treat those shorts and convert them to a usable float form will be appreciated.
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-09-26T07:34:30+00:00
- Post Title: Vertex position, short to float in python.

[viewtopic.php?f=33&t=4582&start=1419](http://forum.xentax.com/viewtopic.php?f=33&t=4582&start=1419)
## Post #3
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-26T10:59:03+00:00
- Post Title: Vertex position, short to float in python.

Awesome, thanks a lot.
