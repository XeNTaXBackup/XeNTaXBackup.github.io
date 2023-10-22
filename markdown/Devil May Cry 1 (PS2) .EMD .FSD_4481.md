## Post #1
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-05-21T09:10:33+00:00
- Post Title: Devil May Cry 1 (PS2) .EMD .FSD

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-21T20:20:47+00:00
- Post Title: Devil May Cry 1 (PS2) .EMD .FSD

> Reply from ashkanhsj
>
> Hey guys, I wanted to extract all of the models and textures of Devil May Cry 1 (PS2). I already made some similar topics on the other forums, but they didn't really help me. I need some extractor tools, model viewers and plugins for Blender or 3DSMAX. I would be very grateful if you help me.

.EMD: http://www.2shared.com/file/sWolnzwt/EM4B.html

.FSD: http://www.2shared.com/file/bkoGcPRq/R120.html

Regards
Hello, I would like to help you, but can you upload the files to "RapidShare" instead of "2shared" because I am unable to use "2shared" from where I am at. Thank you very much.
## Post #3
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-05-21T21:08:02+00:00
- Post Title: Devil May Cry 1 (PS2) .EMD .FSD

> Reply from FurryFan
>
> ashkanhsj wrote:Hey guys, I wanted to extract all of the models and textures of Devil May Cry 1 (PS2). I already made some similar topics on the other forums, but they didn't really help me. I need some extractor tools, model viewers and plugins for Blender or 3DSMAX. I would be very grateful if you help me.

.EMD: http://www.2shared.com/file/sWolnzwt/EM4B.html

.FSD: http://www.2shared.com/file/bkoGcPRq/R120.html

Regards
Hello, I would like to help you, but can you upload the files to "RapidShare" instead of "2shared" because I am unable to use "2shared" from where I am at. Thank you very much.

Thanks for the response. It's done. check the first post.
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-22T19:56:10+00:00
- Post Title: Devil May Cry 1 (PS2) .EMD .FSD

In this file there is one main model, of a building I think, with some surrounding land.
The model is stored in sections, which consist of 4 parts, The vertexes, the normals, some texture information, and more texture information. Every section begins at an offset that ends in zero, because there is padding using the byte "CD" (which is also used as padding in the first 2 Legend of Spyro Games.

....#Vertexes, UnknownVariables(1-4), Padding, 4ByteFloatVertexes(x,y,z), Padding, 4ByteFloatNormalMappings(x,y,z), Padding, 4ByteTextureInfo1, Padding, 4ByteTextureInfo2, Padding......

The vertexes are tristrips, which are culled in some method.
## Post #5
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-05-23T13:30:48+00:00
- Post Title: Devil May Cry 1 (PS2) .EMD .FSD

> Reply from FurryFan
>
> In this file there is one main model, of a building I think, with some surrounding land.
The model is stored in sections, which consist of 4 parts, The vertexes, the normals, some texture information, and more texture information. Every section begins at an offset that ends in zero, because there is padding using the byte "CD" (which is also used as padding in the first 2 Legend of Spyro Games.

....#Vertexes, UnknownVariables(1-4), Padding, 4ByteFloatVertexes(x,y,z), Padding, 4ByteFloatNormalMappings(x,y,z), Padding, 4ByteTextureInfo1, Padding, 4ByteTextureInfo2, Padding......

The vertexes are tristrips, which are culled in some method.

Good job.... can you attach a texture on it? are these files similar to Resident Evil games?
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-23T17:24:33+00:00
- Post Title: Devil May Cry 1 (PS2) .EMD .FSD

There is a texture in the file you gave me, along with some audio. The texture format is a 32bit Tim2 texture, which is a type of texture used in playstation2 game. This Tim2 texture is the type without the TIM2 header so Xn-View can not open it. I also need to find how the UV coordinates are stored.
As for Resident Evil, I do not have a game or disc with that game, you can send with a file though.
## Post #7
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-10-04T09:36:05+00:00
- Post Title: Devil May Cry 1 (PS2) .EMD .FSD

The contents of this post was deleted because of possible forum rules violation.
