## Post #1
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-06-26T15:24:46+00:00
- Post Title: How to add Textures to Noesis?

How can i add dds Textures to a Model via Noesis? Can anyone tell me?
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-06-28T03:17:06+00:00
- Post Title: How to add Textures to Noesis?

> Reply from Ahri
>
> How can i add dds Textures to a Model via Noesis? Can anyone tell me?Hello what mean add textures to noesis? if you mean to load automatic when you load model this depend if script have it, if not sure you don't got it, annd in any case remember always put in same folder textures and models, this sometimes work, but as told you before this is always when script support it.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-06-28T03:17:43+00:00
- Post Title: How to add Textures to Noesis?

> Reply from Ahri
>
> How can i add dds Textures to a Model via Noesis? Can anyone tell me?Hello what mean add textures to noesis? if you mean to load automatic when you load model this depend if script have it, if not sure you don't got it, annd in any case remember always put in same folder textures and models, this sometimes work, but as told you before this is always when script support it.
## Post #4
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2014-06-28T19:38:04+00:00
- Post Title: How to add Textures to Noesis?

Create material
Add texture to material
put material in global material list (, texture in texturelist)
Assign material to CommitTriangle call

```
material.setTexture(texName)
matList.append(material)
texList.append(texName) # or loaded texture // path to texfile etc whichever works
rapi.rpgSetMaterial(material)
rapi.rpgCommitTriangles(*args)
mdl = rapi.rpgConstructModel()
mdl.setModelMaterials(NoeModelMaterials(texList, matList))

```

Something like that

You need to set a material for each rpgCommitTriangles call
