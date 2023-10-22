## Post #1
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2023-05-21T14:11:42+00:00
- Post Title: Cannot open .mesh in blender from ZombieDriver

Please, help. Can't import file .mesh in Blender.
About 10 years ago I could do it, but now I can't. This is an old game ZombieDriver, I installed it for my child, and now I want to make changes in the streets and buildings and export it back.

But it fails to import first.

I have Blender 2.79b.
Please help me solve the problem.

Original file MESH from ZombieDriver:
[https://www.mediafire.com/file/pkpv0hu0 ... H.zip/file](https://www.mediafire.com/file/pkpv0hu0qo8vw0b/OriginalFilesMESH.zip/file)

When importing I get this error:


error import in blender MESH Без имени-2.jpg (43.8 KiB) Viewed 147 times
## Post #2
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2023-05-21T15:04:40+00:00
- Post Title: Cannot open .mesh in blender from ZombieDriver

I also tried converting the file through the plugin OgreXMLConverter. The error is different, and does not open.
[Мщзкщы2.jpg](https://xentaxbackup.github.io/file/23821_Мщзкщы2.jpg)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-05-21T16:38:07+00:00
- Post Title: Cannot open .mesh in blender from ZombieDriver

For me it says "FileNotfoundError: train_station.mesh.xml"

You'll need the OgreXMLconverter from here:

> Reply from Kva3imoda ↑Wed May 30, 2018 7:52 pm at Wed May 30, 2018 7:52 pm
>
> 

The uv map looks a little bit strange to me, though:
.



train_station.jpg (142.92 KiB) Viewed 119 times
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-05-21T16:52:19+00:00
- Post Title: Cannot open .mesh in blender from ZombieDriver

> Reply from shakotay2 ↑Mon May 22, 2023 12:38 am at Mon May 22, 2023 12:38 am
>
> 
For me it says "FileNotfoundError: train_station.mesh.xml"
I quickly looked inside the plugin, it reads only .xml, and converts .mesh using OgreXMLConverter.exe,
or, try manually converting the *.mesh to *.xml
[Ogre.zip](https://drive.google.com/file/d/1s6o9ZgDVsEDcost4ZnukmnY1h6N_g2tt/view?usp=sharing)
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-05-21T17:59:01+00:00
- Post Title: Cannot open .mesh in blender from ZombieDriver

> Reply from shakotay2 ↑Mon May 22, 2023 12:38 am at Mon May 22, 2023 12:38 am
>
> 
The uv map looks a little bit strange to me, though:
probably because each submesh has its own texture. it is visible in xml 

```
<submesh material="Concrete/concrete_wall_cracks"...
<submesh material="Tiles/roof_tiles_ceramic_red"...
<submesh material="Concrete/train_station_sidewalk"...

```

[fmt_ogre_xml.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_ogre_xml.py)
strange xml module from the built-in python Noesis, for some reason I don’t want to parse the this xml file. I wrote a quick parse for the test.



train_station.mesh.png (222.29 KiB) Viewed 110 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-05-21T20:04:15+00:00
- Post Title: Cannot open .mesh in blender from ZombieDriver

Yeah, for some strange reason blender refuses to apply the texture. Even when I deleted 3 of 4 sub meshes
(checked it with a cube to be sure not to miss something):
.



cube.jpg (241.82 KiB) Viewed 99 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-05-21T20:18:05+00:00
- Post Title: Cannot open .mesh in blender from ZombieDriver

Well, near to perfect in newest blender:
.



train_station_new.jpg (161.98 KiB) Viewed 94 times
## Post #8
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2023-05-22T22:31:23+00:00
- Post Title: Cannot open .mesh in blender from ZombieDriver

Guys thanks a lot for your help!! )) 
seems to work. Not all cards line up. But I remembered that in 2012 I did it on an old laptop and then I still had Blender 2.49, Windows Vista ... )) The old import plugin works. I just tried it on a new computer Windows 10 and the blender 2.49 with the plugin does not start. Apparently very old programs, and will work on the old operating system. But somehow it works!!! Thank you very much for your help.
