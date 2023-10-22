## Post #1
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-10-03T23:30:39+00:00
- Post Title: Noesis help: Exporting model with texture

Hi everyone,

I would like to know how to export a model with textures in Noesis, because when I click to export the model to .obj and put additional texture output as .dds (or any other) any texture are exported, just the model. I also use the command -objmtl to generate the mtl file.
My script is opening a model and appending materials and textures. The textures are in .dat format, but Noesis is automatically opening them using my other script for headerless textures.

Thanks in advance.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-04T00:45:18+00:00
- Post Title: Noesis help: Exporting model with texture

i think obj support was an experiment or something, i'd avoid using it and just go for fbx or another common exchange format just to get the data out.  
i'm not too familiar with exporting the textures with the model though, i usually batch convert the textures and sort that stuff out later.
