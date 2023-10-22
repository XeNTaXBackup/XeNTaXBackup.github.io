## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-04-26T08:03:47+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

I dunno but since I'm browsing and viewing these files just for the lulz, I'm curious as to what's in the files used for the models and most other models. A friend of mine already cracked the audio formats, which are merely scrambled ADPCM (Sony PS2 .VAG) files, but what about the meshes and stuff?

Of course I uploaded a bunch of files from the game; they consist of .COL, .GEL, .INS, .LIT, .MAT, .MB2, .PSI, .RCK, .STR and .VIS. I assume that the .MAT file contains the materials/textures, as evidenced by the "TEX" acronym in the header.

Here's a RAR file of the assets:
[assets.rar - 3.70MB](http://www.zshare.net/download/753940049ef8085a/)

Any help will be greatly appreciated... ^_^
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-04-28T09:46:29+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

I know this sounds silly, but anyone?
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-27T21:28:51+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

> Reply from huckleberrypie
>
> I know this sounds silly, but anyone?
I have to do some more searching for the names of the models but here is the format for objects which are in the "INS" extension files:
Vertex Section
#NumVertexes--4Bytes
Vertexes--4Bytefloats(X,Y,Z)
NormalMap--4Bytefloats(X,Y,Z)
VertexWeight?--4Bytefloats(X,Y,Z)  I have not seen this really used it is almost always "00 00 80 42" = 64
4ByteInterger 
4ByteInterger
(optional  Bone to Vertex map?--4ByteMasterVertex, 4byteVertexs(#1,#2,#3) FF FF FF FF 00 00 00 00 4byteBoneID)
Face Index Section(s)
4ByteInterger
4ByteInterger
4ByteNull--(Either 00 00 00 00 or FF FF FF FF)
Size of Section to begin after this integer --4Bytes
Vertexes in faces--4ByteVertex(#1,#2,#3)
FaceTextureMapping--Vertex#1(U,V) Vertex#2(U,V) Vertex#3(U,V)

I do not yet know how to implement and import Face Texture Mappings in Blender, as this is different than Vertex Texture Mappings that by definition have to be continuous and "match up".


[http://ps23dformat.wikispaces.com/file/ ... SHIP.blend](http://ps23dformat.wikispaces.com/file/view/CAKESHIP.blend)
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-08-05T06:24:55+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

Thanks for breaking it down for me. Sorry for the bump, but how will I convert it on my own? I dunno what to look for in the hex codes first.
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-08-07T06:42:59+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

huckleberrypie,

Did you delete your sample file ?
## Post #6
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-08-09T23:30:53+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-08-15T08:41:36+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

huckleberrypie,

Thank you for your sample files, I added the .ins loader module to my program (developer version yet) at the last day.
I note FurryFun extracted the first object from the .ins file.

Here I uploaded the .obj/mtl files (vertex mapped) I converted from the .ins ones.
[http://web.t-online.hu/karpo/ins_to_obj.zip](http://web.t-online.hu/karpo/ins_to_obj.zip)
## Post #8
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-08-16T04:41:11+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

> Reply from Karpati
>
> huckleberrypie,

Thank you for your sample files, I added the .ins loader module to my program (developer version yet) at the last day.
I note FurryFun extracted the first object from the .ins file.

Here I uploaded the .obj/mtl files (vertex mapped) I converted from the .ins ones.
http://web.t-online.hu/karpo/ins_to_obj.zip

Thanks. BTW, when will you release the next version of your 3D converter tool?
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-08-17T15:58:17+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

I released the v4.421 now.

You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates…).
## Post #10
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-08-18T08:56:10+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

For one thing, the reason why I asked for format documentation was because I would like to get the character models from it and port them to another game. I saw what appears to be character models in the OBJ file you converted, but the bodies seemed messed up.
## Post #11
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-08-23T13:08:31+00:00
- Post Title: Strawberry Shortcake: The Sweet Dreams Game models

I did not find human models in your uploaded .ins files.
Unfortunately, I don't have other .ins files, so I don't know which other .ins files contain human models.
