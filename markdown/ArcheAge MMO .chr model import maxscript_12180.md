## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-11-01T08:07:15+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

Hi guys! Here's maxscript to import ArcheAge MMO .chr models with bones+weights (3ds max 2009-2012). 
I know there's some tools for models, but as I understand theres no bone and weights (static models), right? So, if anyone will find it useful that's cool  

P.S. Report bugs
[ArcheAge_MMO.7z](https://xentaxbackup.github.io/file/8013_ArcheAge_MMO.7z)
## Post #2
- Username: dnnkeeper
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 09, 2014 8:26 am
- Post datetime: 2014-11-05T17:35:10+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

Thank you very much! Do you know how to apply animations from AA to this models? I managed to load .caf animations onto character in CryEngine SDK and it even worked properly but I didn't manage to export it properly for 3dsmax...

Add:

Also I'd like to say that many chr files doesn't contain heirarchy of bones (e.g. nu_m_nude.chr) but some other (so called, ***_base.chr e.g. nu_m_base.chr) does. It would be marvelous if script could combine them (mesh and bone weights from one apply to bones from another). 

I managed to export base .chr files to CE SDK and apply .caf animations easily. It required removing Bone_#_* prefix from bones name (line 184) in this script. But base chr files doen't contain skinned mesh itself so only bones were animated. Still couldn't export and import HTR back to 3dsmax properly...
## Post #3
- Username: neasov
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 21, 2015 9:49 pm
- Post datetime: 2017-04-13T15:36:56+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

Please tell me how to export animation from the *.caf to 3Dmax format
## Post #4
- Username: neasov
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 21, 2015 9:49 pm
- Post datetime: 2017-06-13T13:46:29+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

up up up caf animate
## Post #5
- Username: miyuko
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 23, 2017 8:59 pm
- Post datetime: 2017-06-17T15:13:17+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

> Reply from zaramot
>
> Hi guys! Here's maxscript to import ArcheAge MMO .chr models with bones+weights (3ds max 2009-2012). 
I know there's some tools for models, but as I understand theres no bone and weights (static models), right? So, if anyone will find it useful that's cool  

P.S. Report bugs
It seems don't work anymore.
## Post #6
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2017-06-28T00:22:39+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

-- Error occurred in anonymous codeblock; filename: C:\Program Files\Autodesk\3ds Max 2017\scripts\ArcheAge_MMO.ms; position: 33680; line: 1495
-- MAXScript FileIn Exception:
-- Unable to convert: undefined to type: Integer64
-- MAXScript callstack:
--	thread data: threadID:13400
--	------------------------------------------------------
--	[stack level: 0]
--	In i loop; filename: C:\Program Files\Autodesk\3ds Max 2017\scripts\ArcheAge_MMO.ms; position: 32613; line: 1451
--		Parameters:
--			i: 1
--		Locals:
--			size: 8
--			skinMod: undefined
--			FaceOff: 119164L
--			Facearray: #([1,2,3], [4,5,3], [5,4,6], [6,7,5], [7,6,8], [8,9,7], [10,7,9], [9,11,10], [12,10,11], [11,13,12], [12,13,14], [14,15,12], [15,14,16], [16,17,15], [17,16,18], [18,19,17], [3,17,19], [15,17,3], [3,20,15], [21,18,16], ...)
--			Weight_array: #((weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), (weight_data boneids:#(11) weights:#(1.0)), ...)
--			ModelName: undefined
--			msh: undefined
--			i: 1
--			count: 1525
--			vertArray: #([9.64044,-26.3505,46.2466], [11.4623,-26.2208,46.2116], [11.4501,-25.6127,46.6734], [11.811,-25.4286,45.2517], [11.824,-24.2969,45.5808], [11.9712,-24.3095,43.9859], [12.1603,-22.7434,43.8253], [11.6247,-23.5481,42.2294], [11.805,-21.9232,41.8996], [11.3576,-22.4466,44.1636], [10.5643,-21.5049,42.5394], [9.52887,-22.8692,45.2107], [8.18125,-21.8672,44.108], [6.92637,-23.9037,45.5174], [8.83906,-24.5483,46.2269], [6.93669,-25.7159,45.7218], [9.03098,-25.7224,46.4915], [7.54224,-26.282,45.4769], [9.64044,-26.3505,46.2466], [10.6888,-24.142,45.8967], ...)
--			ctype: 9
--			UV_array: #([0.989339,-0.581244,0], [0.989468,-0.549538,0], [0.985469,-0.560111,0], [0.97721,-0.546798,0], [0.970313,-0.554519,0], [0.96086,-0.543323,0], [0.949034,-0.550673,0], [0.942828,-0.535999,0], [0.930345,-0.546364,0], [0.94803,-0.556365,0], [0.928812,-0.556759,0], [0.95355,-0.571882,0], [0.93626,-0.579626,0], [0.957154,-0.596035,0], [0.970996,-0.581071,0], [0.973978,-0.601833,0], [0.982703,-0.581545,0], [0.981898,-0.60269,0], [0.989339,-0.581244,0], [0.969664,-0.56531,0], ...)
--			BoneMapId: #()
--			ModelInfo: undefined
--			VertOff: 154744L
--		Externals:
--			Stride: Global:Stride : undefined
--			BoneMapStart: Global:BoneMapStart : 69944L
--			vert_info_array: Global:vert_info_array : #(70204, 106412, 106884, 119124, 154088, 154704)
--			FacePosArray: Global:FacePosArray : #(0, 5418)
--			VertexEnd: Global:VertexEnd : #(0, 1489)
--			SecSize: Global:SecSize : #(1525, 1525, 1525, 5550, 1525, 1525)
--			DataCount: Global:DataCount : 2
--			FaceCountArray: Global:FaceCountArray : #(5418, 132)
--			f: Global:f : <BinStream:E:\tx\sg\unpack\game\objects\characters\animals\cat_baby_pet\cat_baby_pet_lod1.chr>
--			VertexCountArray: Global:VertexCountArray : #(1489, 36)
--			bone_info_array: Global:bone_info_array : #(166944)
--			owner: undefined
--			ChunkOneType: Global:ChunkOneType : #(0, 1, 2, 5, 6, 9)
--	------------------------------------------------------
--	[stack level: 1]
--	called from top-level
## Post #7
- Username: Alukardqwe
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 07, 2017 5:59 am
- Post datetime: 2017-08-05T14:20:20+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

> Reply from zaramot
>
> Hi guys! Here's maxscript to import ArcheAge MMO .chr models with bones+weights (3ds max 2009-2012). 
I know there's some tools for models, but as I understand theres no bone and weights (static models), right? So, if anyone will find it useful that's cool  

P.S. Report bugs

The script works great. But there are a couple of questions about importing animations into max or what are the ways to drive it there
## Post #8
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2017-12-15T07:53:30+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

HI,Thank you for your great works!
I found that this script was not good for all the .chr files.(3dsmax 2010 x86)



Ashampoo_Snap_2017.12.15_15h26m12s_001_.png (101.58 KiB) Viewed 464 times


I uesed the noesisv to open the .chr files.It's good,but there were not weight+bones.
This script didn't work for the hair\ clothe\ parts of character.
Here is the samples.can you update your script?Thank you.
[https://mega.nz/#!HpoWQZqb!Kv2kuBcm3aL1 ... gxTO1FXylk](https://mega.nz/#!HpoWQZqb!Kv2kuBcm3aL1A4TBEf5zQHzaSHnSrRfHtgxTO1FXylk)
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-15T09:59:03+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

There are a lot of tools for CryTek files, did you tried Noesis for example or script made by joqqy [viewtopic.php?f=16&t=12085&hilit=ryse&start=75](http://forum.xentax.com/viewtopic.php?f=16&t=12085&hilit=ryse&start=75) ? Otherwise, I will updated my script when I will have time.
## Post #10
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2017-12-16T00:17:54+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

> Reply from zaramot
>
> There are a lot of tools for CryTek files, did you tried Noesis for example or script made by joqqy viewtopic.php?f=16&t=12085&hilit=ryse&start=75 ? Otherwise, I will updated my script when I will have time.

Thank you for your answer, I think ，the game using the same game engine, the file type is not necessarily the same, so the imported tool are not the same. I'll try the tool you told me, and reply.
sorry about my bad english.
p.s.how to known which game engine does the game use? thank you.

update~[*]sorry about that, the script is for 3dmax 2017. I just have the 3dmax2010~
update~I have a constant error on load ui_.ms: but there is an error.     -- Error occurred in anonymous codeblock; filename: C:\Program Files\Autodesk\3ds Max 2017\scripts\ui_.ms; position: 10538; line: 271
-- Compile error: Can't find include file:  HEADER_.ms
## Post #11
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2017-12-27T09:25:03+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

> Reply from zaramot
>
> There are a lot of tools for CryTek files, did you tried Noesis for example or script made by joqqy viewtopic.php?f=16&t=12085&hilit=ryse&start=75 ? Otherwise, I will updated my script when I will have time.

today,I use noesis to import the .chr file, it's ok but there is not including the bones.the script made by joqqy is the same as noesis.



Ashampoo_Snap_2017.12.27_17h18m03s_001_.jpg (121.89 KiB) Viewed 408 times


can you update your script when you have time ? thank you !!!!
p.s your script is good for 3dmax 2017 !(I can not upload another picture^^)
## Post #12
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2018-10-15T19:27:12+00:00
- Post Title: ArcheAge MMO .chr model import maxscript

Any news for import animation files  ? Thx
