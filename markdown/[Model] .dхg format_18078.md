## Post #1
- Username: cfstevefox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 09, 2018 3:48 pm
- Post datetime: 2018-05-09T07:59:38+00:00
- Post Title: [Model] .dхg format

hi guys. i encountered an unknown format of the models when unpacking (models format .dхg)
Unfortunately, I did not find any information on the structure of this model
who can help with these models?
I am also ready to pay for work
I need to know their structure and whether they are packed.

Disk: [https://drive.google.com/file/d/1GRcRgp ... j7fcx/view](https://drive.google.com/file/d/1GRcRgp4L9_dliyh5auYfvcUcZYzj7fcx/view)
i am hope for your help
In the archive there is another type of format in the folder CharaModel, its value is also unknown to me and these files are only present on models with characters.
I think that they are needed to preview the model and use on it various items from the game
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-09T18:25:25+00:00
- Post Title: [Model] .dхg format

found a point cloud but for some reason the face indices don't seem to fit:



CM_00_011_02_000-dxg.jpg (156.7 KiB) Viewed 144 times



Don't have the time to care for but you might check this thread whether the formats are similar:
[viewtopic.php?f=16&t=14391&p=118979&hilit=dxg#p118979](http://forum.xentax.com/viewtopic.php?f=16&t=14391&p=118979&hilit=dxg#p118979)

edit: well, that plugin seems to work for some models
## Post #3
- Username: cfstevefox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 09, 2018 3:48 pm
- Post datetime: 2018-05-09T20:49:06+00:00
- Post Title: [Model] .dхg format

> Reply from shakotay2
>
> found a point cloud but for some reason the face indices don't seem to fit:
CM_00_011_02_000-dxg.jpg

Don't have the time to care for but you might check this thread whether the formats are similar:
viewtopic.php?f=16&t=14391&p=118979&hilit=dxg#p118979

edit: well, that plugin seems to work for some models

The plugin you are talking about does not fit my game.
The .dхg plugin is made for the AiSpace game, and they have different structures
I tried to use the .dхg plugin, it can not open these sections and gives an error

What should I do, I'm stuck on these models...

shakotay2, can you send your script for Neosis to work with this format of models?
I would also like to know if you can take this order if I'm willing to pay.
I need to know the structure of these files

By the way, in the game there are other types in the root directory, format .mrb, they are only available in the folder with the models where the characters are located, in models with objects of such file types does not exist. I think this is a hint
I also downloaded the model objects, they do not have the .mrb format in the directory, I do not know why.

[https://drive.google.com/open?id=1jvh2y ... 6c6fcsl8U_](https://drive.google.com/open?id=1jvh2yU2wGwRmMGpIUuqgD-6c6fcsl8U_)

In this archive there is a model that has the smallest size of 232 bytes, I think this model will be easier to analyze to study the structure.
Model name: T01_grd.dxg  (size 232 byte)
Path: \T01\model\ 
[https://drive.google.com/open?id=1edW3Z ... IzsqlRPX6i](https://drive.google.com/open?id=1edW3Zb075_P41EWJxrEkZCIzsqlRPX6i)

I tried to find a difference using Hex editors, look at the result.


I tried to single out the same values in the same color
You can see that some values are 4 bytes, for example green color, and dark green has 2 bytes at 0x64
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-10T03:00:31+00:00
- Post Title: [Model] .dхg format

> Reply from cfstevefox
>
> The plugin you are talking about does not fit my game.
The .dхg plugin is made for the AiSpace game, and they have different structures
I tried to use the .dхg plugin, it can not open these sections and gives an errordunno, which models' sections you mean.

If you had applied the patch in my post as of Wed May 25, 2016 11:29 am to the script in the thread I've linked above you would have found that it displays about 80% of the dxg models in the Charmodel/model subfolder you've uploaded.

> I would also like to know if you can take this order if I'm willing to pay.I'm not working for money here, sry, because it's just a hobby of mine.

> By the way, in the game there are other types in the root directory, format .mrb, they are only available in the folder with the models where the characters are located, in models with objects of such file types does not exist.Looks like motion files, with translation and rotation (which is supposed to have zero degrees).
Framecount is not constant, so tedious to check.

# CA_00_011_00_000_2258, offset 0x6c4: 

16.912653 80.101166 -15.091455 
17.195129 79.940498 -14.165799 
-2.041290 74.436867 15.861082 
-18.472355 63.905140 9.564021 
-20.818705 62.087467 4.124712 
-19.998549 61.627384 5.519426 
-20.691425 60.351799 7.286013 
-26.553867 63.182003 16.021811 
-31.965759 67.292694 25.959063 
-31.123539 69.603699 28.870346 
-24.567484 72.419365 28.555908 
-18.778324 74.334442 26.897554 
-11.362826 78.006851 24.772429 
-8.627209 83.151581 23.667692 
-7.535973 88.738800 21.981329 
-0.000000 -0.000004 -0.000008 
0.000002 -0.000004 -0.000007 
0.000004 -0.000004 -0.000008 
0.000002 -0.000004 -0.000008 
0.000002 -0.000006 -0.000008 
0.000002 -0.000004 -0.000006 
0.000004 -0.000004 -0.000009 
0.000007 -0.000005 -0.000009 
0.000000 -0.000003 -0.000006 
-0.000003 -0.000003 -0.000007 
-0.000002 -0.000002 -0.000008 
3.072120 159.434494 -3.603708 
-6.378955 150.219635 8.151332 
26.872185 136.930237 4.733947 
9.909876 65.577911 69.434586 
3.627127 61.624702 70.139893 
8.237770 61.413929 70.411507 
6.213377 71.226158 77.142303 
-1.009228 86.261383 86.254257 
0.375296 98.737991 87.118256 
7.600327 111.710060 80.876663 
19.708017 129.878357 62.351299 
26.321672 144.855438 37.922531 
21.237566 155.745728 14.776153 
6.360987 162.105881 -3.503386 
-0.000001 -0.000003 0.000005 
-0.000003 -0.000001 0.000000 
-0.000004 0.000000 0.000006 
-0.000008 0.000003 0.000005 
-0.000001 -0.000001 0.000003 
-0.000006 0.000000 0.000003 
-0.000003 0.000002 0.000005 
-0.000008 0.000002 0.000005 
-0.000006 -0.000005 0.000002 
-0.000003 -0.000005 0.000001 
-0.000004 -0.000002 0.000006 
-0.000002 -0.000003 0.000001 
-0.000004 -0.000003 0.000006 
1.403743 93.412941 -29.292477 
...
## Post #5
- Username: cfstevefox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 09, 2018 3:48 pm
- Post datetime: 2018-05-10T04:12:47+00:00
- Post Title: [Model] .dхg format

Thank you for taking the time for my topic.
As for the models, they really open, but not all and not always correctly.

As for the format of the .mrb
I made a stupid mistake! This file is responsible for the animation! 
If open "anim" folder in archive you can see .mrb files, it's animation
Why are the some .mrb files located in an external directory? I think it's just a backup

What can you advise for .dхg models so that I can view them all? (about correct view all models)
(I also found that these models are cut in pieces. One model has several pieces .dхg)
(How to combine .dхg with .mrb animation and textures .dds)

How open animation .mrb?
Forgive, me asking so many questions...
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-10T11:35:34+00:00
- Post Title: [Model] .dхg format

> Reply from cfstevefox
>
> What can you advise for .dхg models so that I can view them all? (about correct view all models)
(I also found that these models are cut in pieces. One model has several pieces .dхg)yeah, that's the reason why some models aren't displayed correctly by the Noesis script (which is not mine, maxeuwe uploaded it;I just patched it).

You can try some workaround like such:

```
        startofverts = 0x29c4
```

for CM_00_011_02_000.dxg (upper body)



dxg-011_02.jpg (105.15 KiB) Viewed 110 times


Finding the start of vertices is not too hard with some 3D formats experience.

> (How to combine .dхg with .mrb animation and textures .dds)hah, yes, you need to expand the script for loading multiple sections before asking such questions.  

> How open animation .mrb?Animations are time consuming, always. I'd start getting the skeletons first (bone names and hierarchy).
## Post #7
- Username: cfstevefox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 09, 2018 3:48 pm
- Post datetime: 2018-05-10T12:35:54+00:00
- Post Title: [Model] .dхg format

> You can try some workaround like such:
It takes a long time to edit the script for each model.

By the way, thanks for your program Hex2obj
I spent about an hour to learn how to open some models, however, the points in mesh are hard to see

As for my task, it's useless if I can not get a full-fledged model to repackage it back into the game.   
How do I work with bones and animations? I need to export the full model to 3D Max and pack it back after editing.

Unfortunately, you are the only one who responded to my topic ...
I have no one to ask how.

By the way, I can be wrong, but it seems to me that CM_00_011_00_000 model does not have verticles, but stores information about bones and other pieces .dхg this model
As for textures, the model lacks personal textures.
The game uses a shader script to apply textures to the model, you can see it in the archive by opening the folder "attr"
The last problem remains - animation of models and bones.

And I noticed that many bytes are not used from models, why?
Example:

What is this data? The model is an object.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-10T14:07:14+00:00
- Post Title: [Model] .dхg format

> Reply from cfstevefox
>
> It takes a long time to edit the script for each model.creating a suiting script for all models takes even longer..

> to repackage it back into the game.you'll need a full format analysis for such

> How do I work with bones and animations?that can't be explained in short - you'll need many basics. Also there's no general receipe because there's too many different formats.

Maybe start with building the skeleton:
1. Getting the bone names, maximum bone number (=bone count-1) 

2. getting the matrices block: translation and rotation of the bones
(sometimes BoneID and BoneParentID contained in this block, too)

3. getting the bones hierarchy
Some prefer this as 2nd step; depends on the format

Here's an example from an hkx file (underlined words are parenting ids, see bonenames table, most right column ):



BrawlerA_parentingIDs.jpg (148.88 KiB) Viewed 100 times



> What is this data? The model is an object.strange table, the ones from the dxgs you've uploaded usually contain indices for pos, normals and uvs, plus dummies (FFFF, FFFF)
(You can get such info very easily by looking into the py script, def parse_indices(self, numVerts, mesh) )

Maybe in this table it's binormals index plus FFFF, or something like that.
