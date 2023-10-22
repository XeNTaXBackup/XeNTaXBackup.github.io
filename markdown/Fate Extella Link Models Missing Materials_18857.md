## Post #1
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-09-24T23:59:59+00:00
- Post Title: Fate Extella Link Models Missing Materials

Hello, I am trying to apply materials to the MDL files of fate extella link, when I go into noesis my model has 7 materials, all of which have textures, but aren't linked for some odd reason. I can easily just fix this in blender, but when I go to convert the mesh into FBX, then to FBX 7100, it appears that all of those materials has gone away. 

This is what noesis says I should have for materials

This is what I end up with for materials

I know that I have all the files properly decrypted and converted, but I believe there is either a problem with this model, with noesis, or with me (as always) 
I'd appreciate any help, and I've added a url to the model in the pictures
[drive.google.com/file/d/1vKPSZVblpqTiVe ... sp=sharing](drive.google.com/file/d/1vKPSZVblpqTiVePdc3RaRJ4tZpUd8DS7/view?usp=sharing)
## Post #2
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2018-09-26T21:23:33+00:00
- Post Title: Fate Extella Link Models Missing Materials

In Blender this model will be composed of several objects (body, hair, etc.) and each object has one material and one texture. Just select different object in Blender and you will see it has different material. Noesis shows them in one combined list.
If you want textures automatically loaded in Noesis you just need to open .mdl file from original extract directory without renaming or moving anything.
## Post #3
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-09-27T01:43:26+00:00
- Post Title: Fate Extella Link Models Missing Materials

> Reply from Kotcrab
>
> In Blender this model will be composed of several objects (body, hair, etc.) and each object has one material and one texture. Just select different object in Blender and you will see it has different material. Noesis shows them in one combined list.
If you want textures automatically loaded in Noesis you just need to open .mdl file from original extract directory without renaming or moving anything.
Whoops! This one was my fault, the tool I use accidentally combined all materials together, and it took an obvious answer like this for me to realize! Learning is all about making mistakes I suppose.
