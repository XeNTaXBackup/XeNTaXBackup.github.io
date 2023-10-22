## Post #1
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-08-10T15:01:03+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

Hey guys, 
I successfully extracted a number of models from COD MW 2019, including Iska, but I'm having difficulties attaching the head to the body. Has anyone figured out a solution to this issue? I'm using Noesis and 3ds Max to work with the files. I can provide the extracted files if you need them, although if I remember right the forum rules are against sharing game files directly, so you'll need to talk to me privately to get them. 

I successfully extracted and attached heads on models from Infinite Warfare and Black Ops 3 a long while ago, but its been so long since I worked on that project, I've forgotten the tricks I used to get it to work, and I sadly never created a tutorial on how to do it. It appears as though the issue is exactly the same with the new Modern Warfare models, where the head, when merged onto the skeleton in 3ds max, causes the rig to flip out and twist the head into the body and rescale it down to a smaller size. 

I have access to Maya as well, I don't remember if the solution involved Maya or not.
## Post #2
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-08-11T20:07:04+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

> Reply from kingfisher13 ↑Mon Aug 10, 2020 11:01 pm at Mon Aug 10, 2020 11:01 pm
>
> 
Hey guys, 
I successfully extracted a number of models from COD MW 2019, including Iska, but I'm having difficulties attaching the head to the body. Has anyone figured out a solution to this issue? I'm using Noesis and 3ds Max to work with the files. I can provide the extracted files if you need them, although if I remember right the forum rules are against sharing game files directly, so you'll need to talk to me privately to get them. 

I successfully extracted and attached heads on models from Infinite Warfare and Black Ops 3 a long while ago, but its been so long since I worked on that project, I've forgotten the tricks I used to get it to work, and I sadly never created a tutorial on how to do it. It appears as though the issue is exactly the same with the new Modern Warfare models, where the head, when merged onto the skeleton in 3ds max, causes the rig to flip out and twist the head into the body and rescale it down to a smaller size. 

I have access to Maya as well, I don't remember if the solution involved Maya or not.
If you're using Max, checkmark the snap to pivot option and then snap the rootbone of the head part to where it is supposed to attach in the main body, such as spine3/4/etc. If there are duplicate bones such as with the neck, save the weights of the models, delete skin modifier, remove the duplicate, add skin modifier back and attach bones and then load the saved weights.
## Post #3
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-08-12T17:14:25+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

Hey, thanks for the reply! I tried your idea, and it was working just fine, but I accidentally stumbled across the original solution I had made back in the day XD

So the quick and easy fix for this issue, is to simply convert the SMDs exported by the COD tool into Unreal models (.PSKs) using Noesis, then import them into 3ds Max using Gildor's Umodel Importer. When you import the head first, then the body as PSKs, it automatically merges the skeletons and snaps the head into the correct position XDDD

I have a new issue however, do you guys have a solution for how to fix the normal maps? They extract in an odd dark blue format with green bits. I'm sure its just how the developers merged texture files to save memory and space, but I'm not sure the correct way to extract a standard normal map from that.
## Post #4
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-08-15T20:23:09+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

Hey guys, the Greyhound Extraction Tool no longer works with COD MW2, could we get support from one of you skilled code ninjas in updating the tool to work with the updated version of MW 2019?
## Post #5
- Username: gasamsg12
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 02, 2019 5:57 pm
- Post datetime: 2020-08-16T19:16:30+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

> Reply from kingfisher13 ↑Sun Aug 16, 2020 4:23 am at Sun Aug 16, 2020 4:23 am
>
> 
Hey guys, the Greyhound Extraction Tool no longer works with COD MW2, could we get support from one of you skilled code ninjas in updating the tool to work with the updated version of MW 2019?

Hi, Everything works for me, [https://github.com/Scobalula/Greyhound/ ... ag/1.5.7.0](https://github.com/Scobalula/Greyhound/releases/tag/1.5.7.0) is it last release, but he closed his project(((((((, but it is extracting the model 
Can you give the link on Gildor's Umodel Importer.? Please
## Post #6
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-08-17T19:58:05+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

> Reply from kingfisher13 ↑Thu Aug 13, 2020 1:14 am at Thu Aug 13, 2020 1:14 am
>
> 
Hey, thanks for the reply! I tried your idea, and it was working just fine, but I accidentally stumbled across the original solution I had made back in the day XD

So the quick and easy fix for this issue, is to simply convert the SMDs exported by the COD tool into Unreal models (.PSKs) using Noesis, then import them into 3ds Max using Gildor's Umodel Importer. When you import the head first, then the body as PSKs, it automatically merges the skeletons and snaps the head into the correct position XDDD

I have a new issue however, do you guys have a solution for how to fix the normal maps? They extract in an odd dark blue format with green bits. I'm sure its just how the developers merged texture files to save memory and space, but I'm not sure the correct way to extract a standard normal map from that.

Another way of connecting the body and head is to use the SE Model Merger. Drag and drop the head and body files to the exe and it does the rest automatically. The downside is that it removes the connected textures at least in Blender. Way to fix that is to import the individual pieces first to Blender, then the merged mesh.
## Post #7
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-08-18T01:45:40+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

> Reply from MaZTeR ↑Tue Aug 18, 2020 3:58 am at Tue Aug 18, 2020 3:58 am
>
> 
Another way of connecting the body and head is to use the SE Model Merger. Drag and drop the head and body files to the exe and it does the rest automatically. The downside is that it removes the connected textures at least in Blender. Way to fix that is to import the individual pieces first to Blender, then the merged mesh.

Thats an interesting idea, thanks Maz. I prefer my technique tho, to be honest, its very simple and loses no texture info. 

> Reply from gasamsg12 ↑Mon Aug 17, 2020 3:16 am at Mon Aug 17, 2020 3:16 am
>
> 
Hi, Everything works for me, https://github.com/Scobalula/Greyhound/ ... ag/1.5.7.0 is it last release, but he closed his project(((((((, but it is extracting the model 
Can you give the link on Gildor's Umodel Importer.? Please

Thats odd, Gasams, you have the latest version of COD MW 2019, I assume? I don't think you can even play the game without updating, so I would assume you have the latest version. I have no idea why my copy of Greyhound stopped working, then. I had the latest version of Greyhound, so it makes no sense.

The issue I'm having is that when I load up the game, and load Greyhound, and press the "export selected" button, Greyhound freezes, and I have to force close it to shut it down. 

Also, the importer is called the "Actor X Importer", found here: [https://www.gildor.org/projects/unactorx](https://www.gildor.org/projects/unactorx)

Could you confirm for me that the tool works, by extracting the Iskra Skin found in tier 90 of the Battle Pass?
## Post #8
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-08-18T13:23:03+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

Alright, I re-downloaded MW 2019, and re-downloaded Greyhound, and it works fine now ;D

Not sure what happened, tbh.
## Post #9
- Username: gasamsg12
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 02, 2019 5:57 pm
- Post datetime: 2020-08-26T11:47:36+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

> Reply from MaZTeR ↑Tue Aug 18, 2020 3:58 am at Tue Aug 18, 2020 3:58 am
>
> 
kingfisher13 wrote: ↑Thu Aug 13, 2020 1:14 am
Hey, thanks for the reply! I tried your idea, and it was working just fine, but I accidentally stumbled across the original solution I had made back in the day XD

So the quick and easy fix for this issue, is to simply convert the SMDs exported by the COD tool into Unreal models (.PSKs) using Noesis, then import them into 3ds Max using Gildor's Umodel Importer. When you import the head first, then the body as PSKs, it automatically merges the skeletons and snaps the head into the correct position XDDD

I have a new issue however, do you guys have a solution for how to fix the normal maps? They extract in an odd dark blue format with green bits. I'm sure its just how the developers merged texture files to save memory and space, but I'm not sure the correct way to extract a standard normal map from that.


Another way of connecting the body and head is to use the SE Model Merger. Drag and drop the head and body files to the exe and it does the rest automatically. The downside is that it removes the connected textures at least in Blender. Way to fix that is to import the individual pieces first to Blender, then the merged mesh.

Please give the link on SE Model Merger
## Post #10
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-08-26T16:00:00+00:00
- Post Title: Call of Duty Modern Warfare 2019 Models

Hey guys, I extracted the Iskra model, as well as her 3 new skins from the season 5 pass, if anyone wants them, PM me, I can give them to you fully textured, rigged, and attached in FBX format.
