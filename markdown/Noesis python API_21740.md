## Post #1
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-02-11T21:48:59+00:00
- Post Title: Noesis python API

I am looking for documentation on noesis python api
In particular, how to add a third UV channel to NoeMesh?
first - .uvs
the second is .lmUVs
third- ???
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-02-17T07:40:13+00:00
- Post Title: Noesis python API

Sadly, Noesis supports only 2 UV sets (viz `rpgBindUV1BufferSafe`, `rpgBindUV2BufferSafe`).
You could try to store third UV (and possibly 4th set) as a vertex color (RG channels). For example, 3ds max loads vertex color as an uv set with index 0 (vertex alpha as -2, but only Alpha channel). Noesis stores vertex colors as a float, so I don't see any problem here, fbx should export them as float too.
However I do not recommend this, since it's not standardized, but it's a way to achieve what you want.
From my experience, I haven't seen much things with a 3rd UV set, surely I've seen ones with 4th set, but it was only for some cases (for certain materials, where you could switch uv sets for different textures, etc.) I could only imagine 3 UV sets for models, where first 2UV sets are texture coords, and 3rd is used for Lightmap, but never seen such.
