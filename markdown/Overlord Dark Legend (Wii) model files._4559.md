## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-06-04T22:41:44+00:00
- Post Title: Overlord Dark Legend (Wii) model files.

Could someone throw together something that would let me convert these files to something that can actually be USED? Preferably with textures as well. I've uploaded the entire model archive for the game but the ones that interest me most are 'Widget' and 'WidgetNoMech'.

I've searched everywhere for information on it's file type but with no luck whatsoever.
Please help!
[http://www.sendspace.com/file/l8uavl](http://www.sendspace.com/file/l8uavl)
## Post #2
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-06-15T18:45:28+00:00
- Post Title: Overlord Dark Legend (Wii) model files.

Actually, I was looking for an answer to these as well. However, upon looking at them with a hex editor, there seems to be some sort of file hierarchy within them, and they may need the rest of the game files to run properly. I personally would like to see the elf king's model (I forgot his name).
## Post #3
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-06-30T20:15:55+00:00
- Post Title: Overlord Dark Legend (Wii) model files.

I'm not too sure on the style of these files. I was hoping they'd be easy to figure out but seeing as we've gotten no replies they must not be, which is a shame as I had some good intentions for these models.
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-07-16T22:29:51+00:00
- Post Title: Overlord Dark Legend (Wii) model files.

At least one file (the wolfqueen) is paritally composed of a renderware dff file [http://www.gtamodding.com/index.php?tit ... tream_file](http://www.gtamodding.com/index.php?title=RenderWare_binary_stream_file) and dds main texture and bitmap alpha texture, and has the regular edian the most PC and PS2 has. However the Widget file is not a regular dff model, and has the other type of edianess that most Wii games have. This file is Vertexes, NormalMapping, Texture mapping. It is odd that the texture maps seems to stop short, of all the vertexes, and normal maps. I think the faces are formed from QuadStrips with some culling, in the order the vertexes are found, but I still have to test this, in the image below I used them as TriStrips, so only all faces are showing, but of the faces that are showing most of them are correct.


[http://ps23dformat.wikispaces.com/file/ ... head.blend](http://ps23dformat.wikispaces.com/file/view/wolfqueenhead.blend)
