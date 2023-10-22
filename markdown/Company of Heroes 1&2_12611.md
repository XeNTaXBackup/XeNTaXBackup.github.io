## Post #1
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-02-16T18:57:35+00:00
- Post Title: Company of Heroes 1&2

"Company of Heroes"

in this game ".sga" files are packaged files, can be unpack this tool : [http://www.corsix.org/misc/CDMS_055.zip](http://www.corsix.org/misc/CDMS_055.zip)
then get some files like these:
 .rgt  -  textrue files,Use Corsix's tool can be save ".dds" or ".tga"
 .rpb -  I think those'r model files,but have no any tools can look them

these files I have no idea
  .abp  .mua  .muax  .sua

I upload some example files , anyone can  research them?  thanks

[http://www.mediafire.com/download/4a392 ... hicles.rar](http://www.mediafire.com/download/4a392w97rb984ta/vehicles.rar)

=======================================
"Company of Heroes 2" 

Corsix's tool  can't unpack this game's ".sga" file, so I tried ninjia ripper catch this game's model, but just get some texture files. 
I upload a example file

[http://www.mediafire.com/download/t61l6 ... ighXP1.sga](http://www.mediafire.com/download/t61l6wuwch6hhya/ArtHighXP1.sga)
## Post #2
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-02-18T03:28:59+00:00
- Post Title: Company of Heroes 1&2

anyone have interesting on these game ??
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-02-18T05:45:27+00:00
- Post Title: Company of Heroes 1&2

Company of Heroes 2
sga extractor: [http://forums.relicnews.com/showthread. ... 2-26-09-13](http://forums.relicnews.com/showthread.php?270246-TOOL-CoH2-SGA-Extractor-v-1-2-26-09-13)
rgm importer for max : [http://hq-coh.com/forum/index.php?topic=23026.0](http://hq-coh.com/forum/index.php?topic=23026.0)

Edit:2015-02-19

For curiosity i played with rgm and rga format. 
Generally i make importers from zero, don't using others sources. It is for better understanding, how it works and for self teaching.
I prefer Blender version 249. I don't use 3ds max. I  can never  to teach how navigate in this program. Too hard for me.

I had problem with uv mapping. Solution found in rgm importer for max. Really strange format for uv. I think still is something wrong in it.  
Another problem was type 5 for animation. 
type 4 - animation keys : rotation+position
type 3 - animation keys : rotation
type 5 - animation keys : rotatation+position for first frame, but next frames are in special case multiply with values like at offset 19749	
Maybe this type keys is used only for rotated wheels. I don't know.

```

offset 19456	vehicle\hull_stop_fwd  # - animation
offset 19645	(1,) - #used bone count
offset 19649	(96,) - #size of stream data
offset 19653	(24,)
offset 19657	bone:bone_chassis_shaker - #bone name used for animation
offset 19681	(5, 6, 0, 72) - #type animation , frame count, stream off start, stream off end
offset 19697	(1.0,) - #long animation in sec 
offset 19701	(0.0, -2.6865682801243546e-16, -0.0, 1.0, 0.021946858614683151, 0.0027103796601295471, 0.0013075463939458132, 0.0, 0.0, 0.0, 0.0, -1.794927534916057e+38) - initial key ?
offset 19749	(0.0, -2.1273346576163537e+19, -4.6566125955216364e-10, -1.6862942859182034e-34, -444019758858240.0, -2.0372400283813477) - strange values = float32*frame count
offset 19773	(0.0, 0.13333334028720856, 0.26666668057441711, 0.40000000596046448, 0.66666668653488159, 1.0) - frames




```


Well. Here is what i have done.
How use:
1.Unpack all sga archives and joint all art folders.
2.run Blender249.blend - not open in blender.exe only click on blend file
3.in Blender Text Window press alt+p and select:
- rgm files - textured and rigged models
- delete unnecessary objects and make parent  all meshes to "pose" armature
- rga files - unpack all animations to new folder 
- anim files - for animation

Updated: 2015-02-21:
- rgt - convert to dds format
[Blender249[CompanyOfHeroes2][PC][rgm][sga][anim][2015-02-21].zip](https://xentaxbackup.github.io/file/8726_Blender249[CompanyOfHeroes2][PC][rgm][sga][anim][2015-02-21].zip)
## Post #4
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-21T15:19:35+00:00
- Post Title: Company of Heroes 1&2

Hi Szkaradek123，My friend, thank you very much for the update script, the script runs very well, thanks again
## Post #5
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-02-22T06:26:55+00:00
- Post Title: Company of Heroes 1&2

wow!!  Szkaradek123 ,you'r an Master !!  
a big thank for your script
## Post #6
- Username: PONGINGPOOR
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 24, 2020 11:14 am
- Post datetime: 2020-10-24T06:19:33+00:00
- Post Title: Company of Heroes 1&2

Noob question,

How can I import .rgm to the blender and see the textures and rigged models?
alt+p then import .rgm does do anything.
