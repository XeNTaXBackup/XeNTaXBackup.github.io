## Post #1
- Username: philgrf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 07, 2017 1:11 am
- Post datetime: 2017-09-07T20:17:19+00:00
- Post Title: translate some blender 2.49 scripts to blender 2.7x scripts

I intend to translate some blender 2.49 scripts to blender 2.78 scripts for my convenience.

My method will rely on an analysis of existing scripts to understand how are created in different blender script version :
- mesh 
- UV 
- bones
- skinning 
- animation

I have gathered some referece scripts with a wide coverage of versions :
Codemanx         : blender 2.49 -> blender 2.70 / call of duty (COD)
gomtuu           : blender 2.49 ->  blender 2.67 / Valkyria Chronicles
zac_at_home      : blender 2.57 / League Of Legends
lispascal        : blender 2.71 / League of legends
bitcpy           : blender 2.62 -> blender 2.71 / legends of Grimrock
Theli            : blender 2.49 -> blender 2.63 /Heroes of Newerth - savage 2 ([https://forums.heroesofnewerth.com/show ... rt-scripts](https://forums.heroesofnewerth.com/showthread.php?65940-Blender-Model-import-export-scripts))
symmetric        : blender 2.54 -> blender 2.71 / neverwinter
Luke Hares and al: blender 2.44 -> blender 2.69 / neverwinter ([https://neverwintervault.org/](https://neverwintervault.org/))
darknet          : blender 2.49 -> blender 2.66 / unreal tournament
Der Ton, Keless  : blender 2.49 -> blender 2.63 / MD5 ([https://www.katsbits.com/tools/#md5](https://www.katsbits.com/tools/#md5))
deliverator      : blender 2.49 -> 2.7x / CIV ([https://forums.civfanatics.com/threads/ ... ts.497821/](https://forums.civfanatics.com/threads/deliverators-blender-scripts.497821/))

as well as some scripts developped for a unique version of blender  :
darkrain         : blender 2.63 / ufo _ alien invasion 
szkaradek123     : blender 2.49 / dragon age 2 + catherine + numerous others
oddwarlock       : blender 2.66 / virtua fighter
TheDude          : blender 2.73 / farCry 3-4
finale00         : blender 2.5x / sanae3D + blender ? / dark soul ?
figuresculptor   :  blender 2.57 / dragon age 2 + blender 2.56A /TERA Online
howfie           : blender 2.49 / escha&logy + DeusExHumanRevolution + C++ / Gundam Extreme/
buny             : blender 2.67 / DOA
volfin           : blender 2.71 / alien isolation + Far cry Primal + hitman 2016 + Watch  Dog

Since I am not a programmer, it may take time before I manage anything in the field.

I publish this research so that people can benefit from my early steps and eventually perform first script conversion.

My next step should be a conversion table blender 2.49 -> blender 2.7x.
## Post #2
- Username: philgrf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 07, 2017 1:11 am
- Post datetime: 2017-09-09T13:00:58+00:00
- Post Title: translate some blender 2.49 scripts to blender 2.7x scripts

I think the most tedious part of the translation may be automated by this script I found on blender artists :
 BGE Python 2.4 to 2.5 converter (in progress)[https://blenderartists.org/forum/showth ... -progress)](https://blenderartists.org/forum/showthread.php?229419-BGE-Python-2-4-to-2-5-converter-%28in-progress%29)

It leave everything related to mesh, bones, UV and animation to change but basic synthax should be fixed.
