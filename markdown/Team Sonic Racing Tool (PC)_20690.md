## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-19T14:59:50+00:00
- Post Title: Team Sonic Racing Tool (PC)

A tool for extracting models and textures from Team Sonic Racing. Geometry/Skeleton/Skinning supported. My main focus was character models as always. Car parts seem to load fine too. Other stuff may or may not work.

Tool overview and example exported model






How to use

Load

Browse : For selecting the .cpu.sp2 file. Corresponding .gpu.sp2 file must be in the same folder.
List : Found models will be added to the list. Select one to load it.
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
SEModel : Exports the model in SEModel (*.semodel) format by dtzxporter. There are import scripts for Maya and Blender 2.79/ 2.80
DDS : Loads all the textures inside the selected file and exports them as DDS.
Note  : Models and textures will be exported into the folder Export.
Download : [https://www.mediafire.com/file/guk4vldy ... r.rar/file](https://www.mediafire.com/file/guk4vldyn3palv9/TSRViewer.rar/file)
## Post #2
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2019-06-20T21:24:00+00:00
- Post Title: Team Sonic Racing Tool (PC)

Good stuff, but would it be possible to make the tool able to work with stage Background characters?

Ones like King Boom Boo end up with their skeleton pre-posed and out of alignment:


Would be nice if this was addressed, but overall, really good tool!
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-20T21:44:05+00:00
- Post Title: Team Sonic Racing Tool (PC)

> Reply from MisterPrawn ↑Fri Jun 21, 2019 5:24 am at Fri Jun 21, 2019 5:24 am
>
> 
Ones like King Boom Boo end up with their skeleton pre-posed and out of alignment:
Can you tell me the name of the  .sp2 file, and also the name of the model if possible? I will take a look.
## Post #4
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2019-06-20T21:58:40+00:00
- Post Title: Team Sonic Racing Tool (PC)

The file is: booshouse.cpu.sp2

King Boom Boo is found within it as: root_tsr_sp_room_4_sand2
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-20T22:24:23+00:00
- Post Title: Team Sonic Racing Tool (PC)

Sometimes the vertices need to be transformed with "SE_LOCATOR". The tool already does it for stuff like car tires, because they had ids corresponding to the locators. The character models don't seem to have them. So the problem with that model is that it is not getting transformed to where it should be, and doesn't align with its skeleton.

I can try a quick hack like finding the first locator based on the name. It would work with the model you posted, but would not work for more complex stuff with multiple locators. Still it might be better than nothing. I will try to see if I can find a better way without needing to do too much work. I will update the tool when I am finished.
## Post #6
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2019-06-20T22:32:27+00:00
- Post Title: Team Sonic Racing Tool (PC)

That works for me. I'm more interested in ripping characters found on the tracks, anyway. Namely the Boos and King Boom Boo, as stated.
## Post #7
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2019-06-29T02:07:17+00:00
- Post Title: Team Sonic Racing Tool (PC)

I hate to bump this, but has there been an update to the tool to properly work with the background characters, yet? It has been a bit of a while, so I just thought I'd check in.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-29T08:11:43+00:00
- Post Title: Team Sonic Racing Tool (PC)

> Reply from MisterPrawn ↑Sat Jun 29, 2019 10:07 am at Sat Jun 29, 2019 10:07 am
>
> 
It has been a bit of a while
Yep, there are other irl and freelance stuff I have to do. I am doing this as hobby, so other stuff that actually fund me takes priority always  I will do an update when i have the time.
## Post #9
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2019-06-29T16:09:29+00:00
- Post Title: Team Sonic Racing Tool (PC)

> Reply from akderebur ↑Sat Jun 29, 2019 4:11 pm at Sat Jun 29, 2019 4:11 pm
>
> 
MisterPrawn wrote: ↑Sat Jun 29, 2019 10:07 am
It has been a bit of a while

Yep, there are other irl and freelance stuff I have to do. I am doing this as hobby, so other stuff that actually fund me takes priority always  I will do an update when i have the time.

Okay, that makes sense.   

Take your time.
## Post #10
- Username: KillzXGamig
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 18, 2018 10:08 pm
- Post datetime: 2019-07-21T14:59:35+00:00
- Post Title: Team Sonic Racing Tool (PC)

Any chance you can give out documentation or code on how the models,materials, and skeleton chunks are structured? Would help alot.
## Post #11
- Username: Harbinger
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 02, 2020 7:03 pm
- Post datetime: 2020-02-02T11:05:06+00:00
- Post Title: Team Sonic Racing Tool (PC)

Does anyone have the model files for TSR?
