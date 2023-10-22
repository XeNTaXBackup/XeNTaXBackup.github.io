## Post #1
- Username: Gooch818
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 28, 2020 11:07 pm
- Post datetime: 2020-08-28T23:26:03+00:00
- Post Title: Blood Bowl - Chaos Edition

Hey all!

I am having some issues getting .nif files from Blood Bowl into .obj format. I can get the file, but its all in standard poses, t pose basically. I am able to export the entire model, or a single mesh at a time. My ultimate goal is to get a model into a pose using the .kf associated file, into an object file.

I'm using NifSkope right now, and man if it only had a .stl export function, lol. My initial attempt was to use blender, with the nif plug in. As I am coming to learn, that plug in only works with specific games. Blood Bowl not being one of them, it is supplying an error when I attempt to import the nif.

Any suggestions?
## Post #2
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-28T23:29:22+00:00
- Post Title: Blood Bowl - Chaos Edition

> Reply from Gooch818 ↑Sat Aug 29, 2020 7:26 am at Sat Aug 29, 2020 7:26 am
>
> 
Hey all!

I am having some issues getting .nif files from Blood Bowl into .obj format. I can get the file, but its all in standard poses, t pose basically. I am able to export the entire model, or a single mesh at a time. My ultimate goal is to get a model into a pose using the .kf associated file, into an object file.

I'm using NifSkope right now, and man if it only had a .stl export function, lol. My initial attempt was to use blender, with the nif plug in. As I am coming to learn, that plug in only works with specific games. Blood Bowl not being one of them, it is supplying an error when I attempt to import the nif.

Any suggestions?

Use the built in Noesis plugin.
## Post #3
- Username: Gooch818
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 28, 2020 11:07 pm
- Post datetime: 2020-08-29T01:20:34+00:00
- Post Title: Blood Bowl - Chaos Edition

> Reply from qs12 ↑Sat Aug 29, 2020 7:29 am at Sat Aug 29, 2020 7:29 am
>
> 

Use the built in Noesis plugin.

I haven't heard of that program, thanks!  I am getting ready to hit the sack, but plan on trying that first thing in the morning.

I did finally have luck using Blender today and got the output I was looking for in .stl format....but man is it a process.  Here's to hoping Noesis expedites some of it!
## Post #4
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-29T05:57:09+00:00
- Post Title: Blood Bowl - Chaos Edition

> Reply from Gooch818 ↑Sat Aug 29, 2020 9:20 am at Sat Aug 29, 2020 9:20 am
>
> 
qs12 wrote: ↑Sat Aug 29, 2020 7:29 am

Use the built in Noesis plugin.


I haven't heard of that program, thanks!  I am getting ready to hit the sack, but plan on trying that first thing in the morning.

I did finally have luck using Blender today and got the output I was looking for in .stl format....but man is it a process.  Here's to hoping Noesis expedites some of it!
[https://richwhitehouse.com/index.php?co ... ojects.php](https://richwhitehouse.com/index.php?content=inc_projects.php)
## Post #5
- Username: Gooch818
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 28, 2020 11:07 pm
- Post datetime: 2020-08-29T17:29:22+00:00
- Post Title: Blood Bowl - Chaos Edition

> Reply from qs12 ↑Sat Aug 29, 2020 1:57 pm at Sat Aug 29, 2020 1:57 pm
>
> 
Gooch818 wrote: ↑Sat Aug 29, 2020 9:20 am
qs12 wrote: ↑Sat Aug 29, 2020 7:29 am

Use the built in Noesis plugin.


I haven't heard of that program, thanks!  I am getting ready to hit the sack, but plan on trying that first thing in the morning.

I did finally have luck using Blender today and got the output I was looking for in .stl format....but man is it a process.  Here's to hoping Noesis expedites some of it!

https://richwhitehouse.com/index.php?co ... ojects.php

Ok, so I've taken a look and Noesis will not load the .nif file BUT it will export it if I want.  Same for the .kf file.  But I can tell I will be using this software with other titles going forward.  Thank you again for the tip!

It's interesting, when exporting the .nif to say a .obj or .stl it adds meshes that are invisible when viewed in nifskope.  For example, a model may have multiple pieces of armor that change depending on the upgrades that character gets in game.  With the export it just throws ALL of them on the model at once.  BUT I am able to get the models initial pose with the export, not just the static T pose.  So that is a start.  I know in nifskope I am able to delete meshes, so it sounds like a little bit of work to get only the meshes I want then export.
