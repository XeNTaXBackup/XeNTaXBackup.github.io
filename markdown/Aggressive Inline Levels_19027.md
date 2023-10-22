## Post #1
- Username: g00dman
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 03, 2018 9:28 pm
- Post datetime: 2018-11-05T21:22:32+00:00
- Post Title: Aggressive Inline Levels

Hey! I'd like to be able to export the levels from Aggressive Inline into Blender to port them into the Tony Hawk's Underground 2 mod THUG PRO.

Here's a link to the level folders of all 3 versions of the game (Ps2, xbox, gamecube): [https://mega.nz/#F!ZcsVVCxS!SERX_B9eMnq2U3nL6tPuwQ](https://mega.nz/#F!ZcsVVCxS!SERX_B9eMnq2U3nL6tPuwQ)

The PS2 version has some unused stuff on the disc so it would preferable to be able to view those, but anything is appreciated.

There's a tool that can export the Gamecube/xbox levels to an .obj - however it misses some textures and a lot of objects, and won't export textures from the Xbox version since it uses a different texture format. I've attached it to this post if anyone wants to take a look and see if they can fix it or something... Let me know if you can help 
[ZAxisLevelTool.zip](https://xentaxbackup.github.io/file/15134_ZAxisLevelTool.zip)
## Post #2
- Username: g00dman
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 03, 2018 9:28 pm
- Post datetime: 2019-06-08T01:10:05+00:00
- Post Title: Aggressive Inline Levels

Hey, sorry to necro an old thread, but I have come across a little bit of documentation written by one of the THUGPro developers on the level format:

[https://github.com/Morten1337/io_thps_s ... _notes.txt](https://github.com/Morten1337/io_thps_scene/blob/zaxis-importer/_zaxis_notes.txt)
[https://github.com/Morten1337/io_thps_s ... t_zaxis.py](https://github.com/Morten1337/io_thps_scene/blob/zaxis-importer/import_zaxis.py)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-08T16:23:32+00:00
- Post Title: Aggressive Inline Levels

> Reply from g00dman ↑Sat Jun 08, 2019 9:10 am at Sat Jun 08, 2019 9:10 am
>
> 
Hey, sorry to necro an old thread, but I have come across a little bit of documentation written by one of the THUGPro developers on the level format:

https://github.com/Morten1337/io_thps_s ... _notes.txt
https://github.com/Morten1337/io_thps_s ... t_zaxis.pyyeah, there's lots of scripts on [https://github.com/Morten1337/io_thps_s ... s-importer](https://github.com/Morten1337/io_thps_scene/tree/zaxis-importer) but who has the time to deal with? Guess noone.

Why not simply use the ZAxisLevelTool.exe? Gives good results incase you replace the following lines in the created .obj which confuse blender's wavefront obj importer:
v n. def. n. def. n. def. -> v 0.0 0.0 0.0

vt n. def. n. def. -> vt 0.0 0.0

result for INDUST.GEO:
.



INDUST-geo.png (105.81 KiB) Viewed 79 times
## Post #4
- Username: g00dman
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 03, 2018 9:28 pm
- Post datetime: 2019-06-09T00:58:06+00:00
- Post Title: Aggressive Inline Levels

You'll have to forgive my inexperience with coding languages and the like   

I have tried to use the level tool, but the problem is that it misses a lot of objects on import. I did a little bit of digging through the original .GEO and .INS files and found that a lot of objects are defined with a 'Def', like GlassDef or CarDef, in the .GEO file, but in the .INS file those same objects drop the 'Def' - these objects are missing from the exported .obj. Stuff like vertex shading is missing too but I guess you can bake lighting onto the map.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-09T06:14:43+00:00
- Post Title: Aggressive Inline Levels

> Reply from g00dman ↑Sun Jun 09, 2019 8:58 am at Sun Jun 09, 2019 8:58 am
>
> I have tried to use the level tool, but the problem is that it misses a lot of objects on import. I did a little bit of digging through the original .GEO and .INS files and found that a lot of objects are defined with a 'Def', like GlassDef or CarDef, in the .GEO file, but in the .INS file those same objects drop the 'Def' - these objects are missing from the exported .obj.How can you be sure that it's missing mesh objects? Those names might be "properties" only ore something like that.

Can you give an example of a missing object (ingame screenshot versa exported obj file)?

> Stuff like vertex shading is missing too but I guess you can bake lighting onto the map.Maybe just don't be too greedy.
## Post #6
- Username: g00dman
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 03, 2018 9:28 pm
- Post datetime: 2019-06-09T13:03:12+00:00
- Post Title: Aggressive Inline Levels

I'm sure because I'm very familiar with the game. But anyway, here's a comparison from the first level:

Blender export:


Ingame:


As you can see several things are missing. Lots of trees, some trickable objects like planters, bike racks, etc. There are some missing textures too but I can get those myself.

Also you may be right about being too greedy.....
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-09T15:09:26+00:00
- Post Title: Aggressive Inline Levels

> Reply from g00dman ↑Sun Jun 09, 2019 9:03 pm at Sun Jun 09, 2019 9:03 pm
>
> 
I'm sure because I'm very familiar with the game. But anyway, here's a comparison from the first level:Thank you!

> As you can see several things are missing. Lots of trees, some trickable objects like planters, bike racks, etc.
Trees, planters and bike racks are used in different levels, aren't they?
So they might be handled as references only which could explain that the ZAxisLevelTool doesn't handle them.

(That's a wild guess only, which could be proven if there were separate tree meshes apart from the level files.)

> Also you may be right about being too greedy.....That was a joke only!  
It makes sense to get the complete levels. But to get it "perfect" would be a tedious task.
## Post #8
- Username: g00dman
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 03, 2018 9:28 pm
- Post datetime: 2019-06-09T15:54:15+00:00
- Post Title: Aggressive Inline Levels

I'm not sure. I was actually able to get several models out of the .GEO file by using a QuickBMS script, including some of the missing ones. Here's a link: [https://cdn.discordapp.com/attachments/ ... Tto3ds.bms](https://cdn.discordapp.com/attachments/500066729024815117/587308192929939476/AggressiveInlineZITto3ds.bms)

Now while in theory I suppose I could piece together all the missing things and add them to the ZAxisLevelTool export, the scale of the objects is not the same, there are no textures or UV data, etc... As you said about getting things perfect, it's tedious work....
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-09T21:13:17+00:00
- Post Title: Aggressive Inline Levels

> Reply from g00dman ↑Sun Jun 09, 2019 11:54 pm at Sun Jun 09, 2019 11:54 pm
>
> 
I'm not sure. I was actually able to get several models out of the .GEO file by using a QuickBMS script, including some of the missing ones. Here's a link: https://cdn.discordapp.com/attachments/ ... Tto3ds.bmsyeah, those "famous" bms scripts for PS2 made by FurryFan are known for missing uvs...
## Post #10
- Username: g00dman
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 03, 2018 9:28 pm
- Post datetime: 2019-06-09T22:35:12+00:00
- Post Title: Aggressive Inline Levels

Bummer....   Sadly that was the only other thing I found that could get stuff out of it
## Post #11
- Username: g00dman
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 03, 2018 9:28 pm
- Post datetime: 2019-06-27T23:48:04+00:00
- Post Title: Aggressive Inline Levels

Found a way to make the level tool export load the missing objects!!

In the .INS file, all objects that appear multiple times in a level (everything that has a Def_ in its name in the .GEO file "propdef_treesmall", for example) are instead listed as prop_treesmall06, or 07, and so on. Changing those names in the .INS file to the same name as it has in the .GEO file will export them, with UVs, textures, and usually in the right place (except AnimProps which are animated objects in the level - those just appear as big boxes. Other stuff like Cars, dynamic objects, AnimObjs, etc. won't import either cuz they aren't listed in the INS file). While I'm so so happy that this works, it does take a long ass time. Thought I'd update you on this anyway.
## Post #12
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-06-28T00:48:54+00:00
- Post Title: Aggressive Inline Levels

Crap. I was working on this game in 2016. I wish i saw the thread earlier on
## Post #13
- Username: g00dman
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 03, 2018 9:28 pm
- Post datetime: 2019-06-28T13:42:42+00:00
- Post Title: Aggressive Inline Levels

Oh neat, what were you working on exactly?
