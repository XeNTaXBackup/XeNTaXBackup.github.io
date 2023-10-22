## Post #1
- Username: Sseast
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 25, 2020 11:19 pm
- Post datetime: 2020-05-01T14:58:56+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

Hello everyone, 

Anyone knows how to animate the "t-Pose" obj files from mgs1 ?



Untitled.png (48.75 KiB) Viewed 177 times



I am going to keep looking for files that may contains animations, otherwise I guess I'll rigg them from scratch   

Thank you 

Edit : I have the feeling that .oar file may be the key as there are as many .oar files as character models in every levels.

But I don't really know how to handle these files...
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-10-24T20:13:46+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

+bump

I want to know as well, I have attached a file with both the .KMD file with the mesh data for Snake as well as the .OAR archive featuring the animations... I'm dying to port these...


The only information I can find regarding any of this is a neat model viewer made by the same person who worked on the awesome RE1MV, RE2MV, RE3MV (Model viewers capable of previewing and exporting mesh data and animations from OG Resident Evil Titles), however the last I saw about MGSMV was back in 2015, he has been working on other projects.



Here is the thread.
[Snake Model and animations.rar](https://xentaxbackup.github.io/file/18890_Snake Model and animations.rar)
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-10-25T23:19:16+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

You can't animate OBJ files, OBJ isn't a format that can contain bones or animation data, it's a purely model data format.
You'd need to get them out of the game in a whole different format.
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-10-25T23:46:45+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

> Reply from lionheartuk ↑Mon Oct 26, 2020 7:19 am at Mon Oct 26, 2020 7:19 am
>
> 
You can't animate OBJ files, OBJ isn't a format that can contain bones or animation data, it's a purely model data format.
You'd need to get them out of the game in a whole different format.

Yes and no. If you check out RE1MV and RE2MV, meshes are exported to OBJ's, segmented. Upon using the 3ds max script they are automatically rigged, each section is attributed it's characteristic bone.

Here: [https://youtu.be/Fx3NULUpf0k](https://youtu.be/Fx3NULUpf0k)
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-10-26T00:09:07+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

> Reply from Pepsee ↑Mon Oct 26, 2020 7:46 am at Mon Oct 26, 2020 7:46 am
>
> 
lionheartuk wrote: ↑Mon Oct 26, 2020 7:19 am
You can't animate OBJ files, OBJ isn't a format that can contain bones or animation data, it's a purely model data format.
You'd need to get them out of the game in a whole different format.


Yes and no. If you check out RE1MV and RE2MV, meshes are exported to OBJ's, segmented. Upon using the 3ds max script they are automatically rigged, each section is attributed it's characteristic bone.

Here: https://youtu.be/Fx3NULUpf0k

It's not yes/no, it's entirely no unfortunately.
That max script is doing 1 of these 2 things.
It's either doing the rigging and skinning process entirely in Max based on the original games rigging data or B: It's converting all the vertex offset data from the original game and applying that to the imported obj file (which once it's imported isn't an OBJ anymore).
IF you exported it all again as an OBJ it'd lose all the animation and any rigging because obj files don't support anything other than geometry and possibly vertex colors.

The only difference between this script and manually going in and rigging everything yourself is that the script does it all for the user.
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-10-26T08:10:17+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

> Reply from lionheartuk ↑Mon Oct 26, 2020 8:09 am at Mon Oct 26, 2020 8:09 am
>
> 
Pepsee wrote: ↑Mon Oct 26, 2020 7:46 am
lionheartuk wrote: ↑Mon Oct 26, 2020 7:19 am
You can't animate OBJ files, OBJ isn't a format that can contain bones or animation data, it's a purely model data format.
You'd need to get them out of the game in a whole different format.


Yes and no. If you check out RE1MV and RE2MV, meshes are exported to OBJ's, segmented. Upon using the 3ds max script they are automatically rigged, each section is attributed it's characteristic bone.

Here: https://youtu.be/Fx3NULUpf0k


It's not yes/no, it's entirely no unfortunately.
That max script is doing 1 of these 2 things.
It's either doing the rigging and skinning process entirely in Max based on the original games rigging data or B: It's converting all the vertex offset data from the original game and applying that to the imported obj file (which once it's imported isn't an OBJ anymore).
IF you exported it all again as an OBJ it'd lose all the animation and any rigging because obj files don't support anything other than geometry and possibly vertex colors.

The only difference between this script and manually going in and rigging everything yourself is that the script does it all for the user.

If you're using the RAW OBJ, definitely, there's no rigging data at all. But in this case, OBJ is a viable option and this method doesn't require another format to be exported such as FBX, SMD, etc.
## Post #7
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-10-26T10:39:52+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

> Reply from Pepsee ↑Mon Oct 26, 2020 4:10 pm at Mon Oct 26, 2020 4:10 pm
>
> 
lionheartuk wrote: ↑Mon Oct 26, 2020 8:09 am
Pepsee wrote: ↑Mon Oct 26, 2020 7:46 am


Yes and no. If you check out RE1MV and RE2MV, meshes are exported to OBJ's, segmented. Upon using the 3ds max script they are automatically rigged, each section is attributed it's characteristic bone.

Here: https://youtu.be/Fx3NULUpf0k


It's not yes/no, it's entirely no unfortunately.
That max script is doing 1 of these 2 things.
It's either doing the rigging and skinning process entirely in Max based on the original games rigging data or B: It's converting all the vertex offset data from the original game and applying that to the imported obj file (which once it's imported isn't an OBJ anymore).
IF you exported it all again as an OBJ it'd lose all the animation and any rigging because obj files don't support anything other than geometry and possibly vertex colors.

The only difference between this script and manually going in and rigging everything yourself is that the script does it all for the user.


If you're using the RAW OBJ, definitely, there's no rigging data at all. But in this case, OBJ is a viable option and this method doesn't require another format to be exported such as FBX, SMD, etc.

Again though, obj isn't a viable option because of the format, this is just how this specific script writer wanted it to work.
OBJ is the easiest 3D format to write so thats why it was likely used.
If it wasn't for the Max script everyone would just be stuck with a useless static OBJ file.
As i said, its just static mesh data, the rest of the data is doing through the script, you don't need OBJ to do that, could've used any format, this is a bit of a weird way to do it if anything. This script doing things in an unusual way isn't better than a single fbx being exported with animations for example.

> this method doesn't require another format to be exported such as FBX, SMD, etc.
It does if you ever intend to use it outside of 3DS Max.
## Post #8
- Username: firblind
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Oct 31, 2019 10:06 am
- Post datetime: 2020-10-26T13:09:26+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

I doubt you actually read what Pepsee is saying. He's not saying OBJ is the format that contains animation data, instead it's the Max script for the RE1 models that turn the segmented parts of the mesh into a rigged and animated form, which is then turned into a format which DOES contain animations data, I.e. FBX, etc.

Next time read what people are saying instead of just jumping to conclusions.
## Post #9
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-10-26T13:35:35+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

> Reply from firblind ↑Mon Oct 26, 2020 9:09 pm at Mon Oct 26, 2020 9:09 pm
>
> 
I doubt you actually read what Pepsee is saying. He's not saying OBJ is the format that contains animation data, instead it's the Max script for the RE1 models that turn the segmented parts of the mesh into a rigged and animated form, which is then turned into a format which DOES contain animations data, I.e. FBX, etc.

Next time read what people are saying instead of just jumping to conclusions.
The script isn't applying the animation to the obj, this is my entire point, it's applying it to the mesh thats added to the max scene, if it was an fbx, an ascii or any other format it'd most likely still work, because the format doesn't matter. Once you import an obj into maya/max/houdini etc it's no longer an obj so far as the software is concerned, all the format limitations are removed as it's now just scene data.
Creating a tool that requires outputting to a format that doesn't support animation, importing that into a specific 3D software, applying the animation inside that software so that you can then export it with animation to a format like fbx/dae etc, is so many more steps than just extracting the files straight into max from the original game, or straight into fbx/dae from the original game.
## Post #10
- Username: firblind
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Oct 31, 2019 10:06 am
- Post datetime: 2020-10-26T14:09:51+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

> Reply from lionheartuk ↑Mon Oct 26, 2020 9:35 pm at Mon Oct 26, 2020 9:35 pm
>
> 
firblind wrote: ↑Mon Oct 26, 2020 9:09 pm
I doubt you actually read what Pepsee is saying. He's not saying OBJ is the format that contains animation data, instead it's the Max script for the RE1 models that turn the segmented parts of the mesh into a rigged and animated form, which is then turned into a format which DOES contain animations data, I.e. FBX, etc.

Next time read what people are saying instead of just jumping to conclusions.

The script isn't applying the animation to the obj, this is my entire point, it's applying it to the mesh thats added to the max scene, if it was an fbx, an ascii or any other format it'd most likely still work, because the format doesn't matter. Once you import an obj into maya/max/houdini etc it's no longer an obj so far as the software is concerned, all the format limitations are removed as it's now just scene data.
Creating a tool that requires outputting to a format that doesn't support animation, importing that into a specific 3D software, applying the animation inside that software so that you can then export it with animation to a format like fbx/dae etc, is so many more steps than just extracting the files straight into max from the original game, or straight into fbx/dae from the original game.

If your entire argument isn't relevant to the topic at hand, then you are senselessly arguing, and clearly have nothing better to do with your time. Good day sir, and please find something actually relevant to the topic or you're just wasting your own, and more importantly, other people's time.
## Post #11
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-10-30T23:25:29+00:00
- Post Title: Metal Gear Solid 1 - Animate obj files

bump      ..Please, can anyone help out?
