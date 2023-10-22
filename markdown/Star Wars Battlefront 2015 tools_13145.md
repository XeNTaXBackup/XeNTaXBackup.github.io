## Post #1
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2015-08-02T23:10:59+00:00
- Post Title: Star Wars Battlefront 2015 tools

Releasing early versions of a tools (yes there are bugs)to import models from upcoming EA/DICE game Star Wars Battlefront 2015. (V1.1)(01/08/15)
To use the mesh import tool you`ll need to :

1. Dump game archives using Battlefield 4 python script by mr FrankElstner. 
1.1 Where? = [https://dl.dropboxusercontent.com/u/881 ... cripts.rar](https://dl.dropboxusercontent.com/u/88155050/Dumper%20Scripts/BF4_Python_Scripts.rar)
1.2 How?    = [https://www.youtube.com/watch?v=fR4dSlGxN-4](https://www.youtube.com/watch?v=fR4dSlGxN-4)

2. Then you need to run my chunk&mesh file tool. Tut is made using bf4 and bfhl but it all works on swbf.
2.1 Where? = [https://dl.dropboxusercontent.com/u/881 ... h_Tool.rar](https://dl.dropboxusercontent.com/u/88155050/StarWars%20BF/Chunk_%26_Mesh_Tool.rar)
2.2 How?    = [https://www.youtube.com/watch?v=4EKxrBnRNBc](https://www.youtube.com/watch?v=4EKxrBnRNBc)

3. Then you can use my maxscripts. Tested only on 3ds max 2012x64
3.1 Where? = [https://dl.dropboxusercontent.com/u/881 ... cripts.rar](https://dl.dropboxusercontent.com/u/88155050/StarWars%20BF/StarWars%20BF_maxscripts.rar)
3.2 How?    = [https://www.youtube.com/watch?v=VdgwQpWCk84](https://www.youtube.com/watch?v=VdgwQpWCk84)

4. Then for textures use my texture tools to get the files.
4.1 Where? = [https://dl.dropboxusercontent.com/u/881 ... WBF%29.rar](https://dl.dropboxusercontent.com/u/88155050/StarWars%20BF/Batch_Itexture_Converter%28SWBF%29.rar)
4.2 How do I view DX10 format? = [http://pixelandpolygon.com/](http://pixelandpolygon.com/)
4.3 [https://dl.dropboxusercontent.com/u/881 ... verter.rar](https://dl.dropboxusercontent.com/u/88155050/StarWars%20BF/DDS_Converter.rar) Paste these three files to the texture folder ur working with and run  ctex_all.bat

Credits to Mr Frankelstner, Luxox_18, and very helpful guys on Xentax forum.

Good luck.
## Post #2
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-08-07T15:09:55+00:00
- Post Title: Star Wars Battlefront 2015 tools

Why not just convert the cape to .obj for people that can't do it themselves it'd be so much easier and nicer for everyone.

Also you need to fix your bone tool the one in the 3ds max scripts download as it only imports half the bones (44) on one side and the full bone count is 266 or 267.
## Post #3
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2015-08-07T23:50:04+00:00
- Post Title: Star Wars Battlefront 2015 tools

> Reply from JakeGreen
>
> Why not just convert the cape to .obj for people that can't do it themselves it'd be so much easier and nicer for everyone.

Also you need to fix your bone tool the one in the 3ds max scripts download as it only imports half the bones (44) on one side and the full bone count is 266 or 267.

1. You are missing my point here, this is a tool release(work in progress) not a model request thread.
2. Bone tool has a variable "bone_count =*" change * to whatever you need.
good luck
## Post #4
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-08-08T01:59:43+00:00
- Post Title: Star Wars Battlefront 2015 tools

> Reply from dainazinas
>
> JakeGreen wrote:Why not just convert the cape to .obj for people that can't do it themselves it'd be so much easier and nicer for everyone.

Also you need to fix your bone tool the one in the 3ds max scripts download as it only imports half the bones (44) on one side and the full bone count is 266 or 267.

1. You are missing my point here, this is a tool release(work in progress) not a model request thread.
2. Bone tool has a variable "bone_count =*" change * to whatever you need.
good luck

Your missing my point as well don't include the cape mesh in your max scripts download and not tell people it can't be opened with your script cause the mesh has no chunk file since the data is in the mesh file and the mesh can only be converted with hex2obj and finding the mesh data with a hex editor, your GIF you posted indicates you can get the cape out with ease.
## Post #5
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2015-08-08T08:56:26+00:00
- Post Title: Star Wars Battlefront 2015 tools

the cape is in the *.mesh file, not in the ebx file.

imperial_snowtrooper_male_01_cape_new_mesh 66a52387cd251531 c0110000e03e03007001000090003001.mesh

cape in obj format.

[http://download1324.mediafire.com/w52af ... 1.mesh.rar](http://download1324.mediafire.com/w52afa9ajgig/swx6wd1yn3p56ls/imperial_snowtrooper_male_01_cape_new_mesh+66a52387cd251531+c0110000e03e03007001000090003001.mesh.rar)

info:

the mesh data for the cape is in floats not half floats contrary to the other files. The vertex data start in 0x11c0 not in 0x0 , the  size is 56 bytes ( total = 1595 vtx), faces in 0x16EB0. UV are in Half floats with 52 bytes size.


NOTE: Relax guys.
## Post #6
- Username: kkhaial
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 28, 2015 4:20 pm
- Post datetime: 2015-08-16T21:43:43+00:00
- Post Title: Star Wars Battlefront 2015 tools

> Reply from luxox18
>
> the cape is in the *.mesh file, not in the ebx file.

imperial_snowtrooper_male_01_cape_new_mesh 66a52387cd251531 c0110000e03e03007001000090003001.mesh

cape in obj format.

http://download1324.mediafire.com/w52af ... 1.mesh.rar

info:

the mesh data for the cape is in floats not half floats contrary to the other files. The vertex data start in 0x11c0 not in 0x0 , the  size is 56 bytes ( total = 1595 vtx), faces in 0x16EB0. UV are in Half floats with 52 bytes size.


NOTE: Relax guys.

How do you get the animation loaded in 3ds max?
## Post #7
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2015-08-17T11:00:05+00:00
- Post Title: Star Wars Battlefront 2015 tools

> Reply from kkhaial
>
> 
How do you get the animation loaded in 3ds max?
[https://youtu.be/VdgwQpWCk84?t=814](https://youtu.be/VdgwQpWCk84?t=814)
## Post #8
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-07T14:08:38+00:00
- Post Title: Star Wars Battlefront 2015 tools

python's dumper script don't work with new beta:

```
Traceback (most recent call last):
  File "C:/BF4_Python_Scripts/BF4_Python_Scripts/Python_Scripts/dumper.py", line 282, in <module>
    cat=Cat(catName)
  File "C:/BF4_Python_Scripts/BF4_Python_Scripts/Python_Scripts/dumper.py", line 58, in __init__
    entry.offset, entry.size, entry.casnum = unpack("<III",cat.read(12))
struct.error: unpack requires a string argument of length 12

Process finished with exit code 1

```
## Post #9
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-07T23:15:45+00:00
- Post Title: Star Wars Battlefront 2015 tools

> Reply from erik945
>
> python's dumper script don't work with new beta:
Code: Select allC:\Python274\python.exe C:/BF4_Python_Scripts/BF4_Python_Scripts/Python_Scripts/dumper.py
Traceback (most recent call last):
  File "C:/BF4_Python_Scripts/BF4_Python_Scripts/Python_Scripts/dumper.py", line 282, in <module>
    cat=Cat(catName)
  File "C:/BF4_Python_Scripts/BF4_Python_Scripts/Python_Scripts/dumper.py", line 58, in __init__
    entry.offset, entry.size, entry.casnum = unpack("<III",cat.read(12))
struct.error: unpack requires a string argument of length 12

Process finished with exit code 1

Yep neither does my tool i have it just completely crashes it, i think it's cause the script and my tool are looking for a update folder and the beta doesn't have that.
## Post #10
- Username: theradgamerdan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 10, 2014 6:15 pm
- Post datetime: 2015-10-09T05:57:39+00:00
- Post Title: Star Wars Battlefront 2015 tools

latest dumper scripts lads
[https://facepunch.com/showthread.php?t= ... st48863555](https://facepunch.com/showthread.php?t=1488991&p=48863555#post48863555)
## Post #11
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-09T08:06:02+00:00
- Post Title: Star Wars Battlefront 2015 tools

> Reply from theradgamerdan
>
> latest dumper scripts lads
https://facepunch.com/showthread.php?t= ... st48863555

Um sadly his mesh and chunk tool doesn't work with the beta.....

EDIT: Nevermind i fixed it on my own here it is [http://www.mediafire.com/download/8bk91 ... Reader.rar](http://www.mediafire.com/download/8bk91mob7bgxovg/Bf3_MeshFile_Type_Reader.rar)

Um you will need to run it twice, once in the chunk folder that is put along side the bundles and then again on the chunk folder inside the bundles folder.

also the exe is in Bf3_MeshFile_Type_Reader\bin\Debug . 

If i can get the Itexture working i'll past it here.
## Post #12
- Username: theradgamerdan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 10, 2014 6:15 pm
- Post datetime: 2015-10-10T00:20:25+00:00
- Post Title: Star Wars Battlefront 2015 tools

> Reply from JakeGreen
>
> theradgamerdan wrote:latest dumper scripts lads
https://facepunch.com/showthread.php?t= ... st48863555

Um sadly his mesh and chunk tool doesn't work with the beta.....

EDIT: Nevermind i fixed it on my own here it is http://www.mediafire.com/download/8bk91 ... Reader.rar

Um you will need to run it twice, once in the chunk folder that is put along side the bundles and then again on the chunk folder inside the bundles folder.

also the exe is in Bf3_MeshFile_Type_Reader\bin\Debug . 

If i can get the Itexture working i'll past it here.

If you just wanna find the chunk for a single mesh, a faster way would be to download HexEdit
[http://www.hexedit.com/](http://www.hexedit.com/)

right click on the mesh file, open with HexEdit, then the chunk id will be somewhere in there

for Star Wars Battlefront, the chunk id starts at 00, 0F0
example; for a280_mesh1p, the chunk id is 703182a1ec3d43c1c70f781a679886e3

then search for that id in /chunks/ & /bundles/chunks

anyway, if you can get his 3ds max mesh importer working too, that would be cool
## Post #13
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-10T00:32:23+00:00
- Post Title: Star Wars Battlefront 2015 tools

> Reply from theradgamerdan
>
> JakeGreen wrote:theradgamerdan wrote:latest dumper scripts lads
https://facepunch.com/showthread.php?t= ... st48863555

Um sadly his mesh and chunk tool doesn't work with the beta.....

EDIT: Nevermind i fixed it on my own here it is http://www.mediafire.com/download/8bk91 ... Reader.rar

Um you will need to run it twice, once in the chunk folder that is put along side the bundles and then again on the chunk folder inside the bundles folder.

also the exe is in Bf3_MeshFile_Type_Reader\bin\Debug . 

If i can get the Itexture working i'll past it here.

If you just wanna find the chunk for a single mesh, a faster way would be to download HexEdit
http://www.hexedit.com/

right click on the mesh file, open with HexEdit, then the chunk id will be somewhere in there

for Star Wars Battlefront, the chunk id starts at 00, 0F0
example; for a280_mesh1p, the chunk id is 703182a1ec3d43c1c70f781a679886e3

then search for that id in /chunks/ & /bundles/chunks

anyway, if you can get his 3ds max mesh importer working too, that would be cool

Yeah that sadly is a very time consuming thing and i don't have a lot of time to waste these days, but i am atm trying to figure out the Max Script.
## Post #14
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-01T17:16:14+00:00
- Post Title: Star Wars Battlefront 2015 tools

Sorry to double post but it's been awhile.

Any chance you could update your Itexture and 3ds max script to work with the full game, i'd be willing to supply you any of the mesh and chunk files you need to get it working.
## Post #15
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-12-06T18:50:55+00:00
- Post Title: Star Wars Battlefront 2015 tools

Someone try extraact 3d models from final game?
I unpack cas file, use this script
[viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584)
but chunk&mesh file tool dont't work.
## Post #16
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2015-12-09T08:05:40+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

The Itexture Converter isn't working for me, select a weapon folder with .unknownres 6bde20ba inside and its not seeing them also tried to rename them to .itexture and nothing
## Post #17
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2015-12-09T08:38:40+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

okay scratch that I got it to get the DDS file but I had to rename it to t_a280_c 6c337f52bd102443 0b000000010000000000000000000000.unknownres6bde20ba without a space in the .unknownres 6bde20ba, but the "DDS" file really isnt a dds file as the header should look like this 
DDS |......................................................................DXT5....................
this header is blank
and I ran the ctex_all.bat and it gave me this 

converted_t_a280_nw 577cca91fe3da737 0b000000010000000000000000000000.PNG
A corrupt file lol, not sure what the prob is
## Post #18
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2015-12-09T09:16:02+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

Also the 3ds Max Script isnt working with the base game models now and needs updating
## Post #19
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-11T19:37:24+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

> Reply from Trophi Hunter
>
> Also the 3ds Max Script isnt working with the base game models now and needs updating

I only know a little bit about making/editing scripts in 3ds max but i'm trying to get it to work but if someone else gets it before me that'd be awesome.
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-13T02:15:35+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

[out]
## Post #21
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-21T02:15:24+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

Here is a updated mesh and chunk tool for SWBF if you are using the scripts from this thread [viewtopic.php?f=10&t=13702](http://forum.xentax.com/viewtopic.php?f=10&t=13702) otherwise use the one i posted awhile back for the beta.

[http://www.mediafire.com/download/6orou ... Reader.rar](http://www.mediafire.com/download/6orou8dqq4uncdb/Frostbite_MeshFile_Type_Reader.rar)
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-22T04:15:19+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

[out]
## Post #23
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-23T01:45:04+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

[out]
## Post #24
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2015-12-26T00:27:56+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

@ Jake Green and @ Dainius G, the game is now using the new texture compression formats for dx11 ex.. BC7 and BC5U for the normal maps, your tool Dainius G isn't converting them to the correct format causing that broken texture i posted above Photoshop can now import these formats and save them out too. Jake when were you guys planning on releasing that Star Wars Battlefront Extraction Tool?
## Post #25
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-26T22:07:02+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

> Reply from Trophi Hunter
>
> @ Jake Green and @ Dainius G, the game is now using the new texture compression formats for dx11 ex.. BC7 and BC5U for the normal maps, your tool Dainius G isn't converting them to the correct format causing that broken texture i posted above Photoshop can now import these formats and save them out too. Jake when were you guys planning on releasing that Star Wars Battlefront Extraction Tool?

i've already gotten the textures to work using a modified version of the texture tool here done by daemon1 in the game archive section of the forums, models are the only thing atm.
## Post #26
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2015-12-27T03:23:58+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

Does any one know what maps are in the .msr file, like what is the red green and blue channel, looks like red or green is spec and the alpha in the normal map is AO
## Post #27
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2016-01-04T05:39:26+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

If your having trouble importing some textures into PhotoShop try this might help
[Here](https://www.youtube.com/watch?v=1z-FzYqiG8w)
## Post #28
- Username: diksonhe
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jul 23, 2015 10:15 pm
- Post datetime: 2016-01-06T06:39:53+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

This‘s 3dsMAX script listener error, Able to solve it? 
OK
"Frostbite model importer by Dainius G 2014, tested on 3ds max 2012x64"
0
0
""
""
0
0
0
0
0
0
0
0
readHalfFloat()
39
""
90
0
1
8
0
0
0
0
#()
#()
"ObjectFullPathName levels/desert/desert_03/objects/rockwallexterior_01_a_Mesh"
"ObjectFullName rockwallexterior_01_a_Mesh"
"ObjectType 0"
"GUID_Count 4"
"First_Data_Block_Offset 784"
"Mesh_Object_Count 2"
"Mesh_FaceIndice_Format 33"
"FaceIndiceOffset 199792"
769
1793
2049
1289
2054
2055
1569
1570
3074
3332
3358
2056
1571
#("Vert_Positions_F", "Vert_Positions_HF", "Vert_Positions_HF_plus", "Vert_Unknown_Flag1", "Vert_BiNormals", "Vert_Tangents", "Vert_Diffuse_UV", "Vert_Normals_UV", "Vert_Bone_Indices", "Vert_Blend_Weights", "Vert_Unknown_Flag2", "Vert_Unknown_Flag3")
#(769, 1793, 1289, 2054, 2055, 1570, 1569, 3074, 3332, 3358, 2056, 1571)
#()
"------------------------------"
"loop1"
"Submesh_1_VB_Size 52412"
8
2055
"Submesh_1_Vert_Count 816"
"Submesh_1_Face_Indice_Count 1065353216"
"var2 1065353216"
"Submesh_1_Material_Name 瓽!B?峋!o[?
"Position before verts 0  0x0"
"Position after verts 42768192  0x28c9740"
"Position before f-indice`s 199792L  0x30c70L"
-- Error occurred in x loop; filename: D:\Program Files\Autodesk\3ds Max 2012\Scripts\SWBF\StarWarsMeshImporter(V1.1).ms; position: 14240; line: 411
--  Frame:
--   fc: undefined
--   fb: undefined
--   x: 12830
--   fa: 1
--   called in sub_m loop; filename: D:\Program Files\Autodesk\3ds Max 2012\Scripts\SWBF\StarWarsMeshImporter(V1.1).ms; position: 14329; line: 415
--  Frame:
--   var6: 1
--   texturefiles: undefined
--   face_array: #([1,2,3], [2,4,3], [1,5,2], [2,5,4], [6,7,4], [6,8,7], [9,8,10], [10,8,11], [12,11,8], [6,12,8], [6,4,13], [12,6,13], [5,14,4], [4,14,15], [4,15,13], [12,16,11], [16,12,13], [17,13,15], [16,13,17], [16,18,11], ...)
--   BoneIndexSameBool: true
--   vbi3: undefined
--   Vert_Positions_array: #([-24238.5,119.895,0.271214], [8.60742,34.4678,-1.80075], [10.7688,12.197,5.43677], [21.29,38.2192,2202.28], [0.00231063,0.00230482,0.00230598], [0.0033195,0.00337529,0.00145867])
--   TextureExt: undefined
--   bool_for_query_box: undefined
--   Submesh_Mat_Name_Offset: 0
--   jibi: undefined
--   VB_positions: #(1570, 40, 1578, 44, 0, 255, 0, 255, 0, 255, 0, 255, 0, 255, 0, 255, 0, 255, 0, 255, ...)
--   parts_array: undefined
--   sub_m: 1
--   skinMod: undefined
--   bi_arr: undefined
--   layer: undefined
--   BoneOrderOffset: 2055
--   mesh1: undefined
--   vertex_count: undefined
--   Vert_Tangents_array: #([1,-0.846191,0.902832], [0.491943,-0.754395,1], [1,0.874512,-0.291016], [3.07227,-5.80549e-005,2.4707], [6.60419e-005,6.6638e-005,6.46114e-005], [0.000154138,0.000159025,0.000159621])
--   vbi4: undefined
--   da: 0
--   vb_poos: 856L
--   bw_arr: undefined
--   vbi1: undefined
--   vbi2: undefined
--   f_inc: 0
--   readface: ReadShort()
--   BoneCount_From_Order: 8
--   ba: 0
--   Vert_BiNormals_array: #([1,-0.846191,0.902832], [0.491943,-0.754395,1], [1,0.874512,-0.291016], [3.07227,-5.80549e-005,2.4707], [6.60419e-005,6.6638e-005,6.46114e-005], [0.000154138,0.000159025,0.000159621])
--   a: 199792L
--   jaba: undefined
--   Submesh_Face_Indice_Count: 1065353216
--   Vert_Diffuse_Array: #([0.328857,0.368896,0], [-1.18164,1.25879,0], [-0.340088,1,0], [-0.630371,3.07858e-005,0], [5.9098e-005,5.9247e-005,0], [0.000147223,0.000147343,0])
--   db: 1
--   Vert_Normal_Array: #([1,-0.846191,0], [0.491943,-0.754395,0], [1,0.874512,0], [3.07227,-5.80549e-005,0], [6.60419e-005,6.6638e-005,0], [0.000154138,0.000159025,0])
--   jtex1: undefined
--   vertIndex_array: undefined
-- No ""+"" function for undefined
true
"Position 13L"
OK
4679864L
true
true
OK
-- Error occurred in anonymous codeblock; filename: D:\Program Files\Autodesk\3ds Max 2012\Scripts\SWBF\StarWarsMeshImporter(V1.1).ms; position: 14236; line: 411
-- Type error: Call needs function or class, got: undefined
## Post #29
- Username: kosinus123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 03, 2016 6:23 am
- Post datetime: 2016-05-01T16:19:32+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

any success fixing it ?
## Post #30
- Username: chromamods
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 16, 2016 5:24 am
- Post datetime: 2016-11-16T02:15:31+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

> Reply from erik945
>
> Someone try extraact 3d models from final game?
I unpack cas file, use this script
viewtopic.php?f=10&t=13584
but chunk&mesh file tool dont't work.

I am having the same issue.  Sorry for bumping this old thread, however the help would be greatly appreciated.
## Post #31
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2016-12-05T04:56:19+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

Exists a way the 3dsmax script works with NFS The Run?
## Post #32
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2016-12-23T00:13:52+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

are there good tutorials on how to use these tools cus this stuff is very confusing. base game and all dlc.
## Post #33
- Username: kodatarule
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 11, 2017 4:23 am
- Post datetime: 2017-01-12T16:48:23+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

Has anyone been able to get model files for the new heroes/villains ?
Thanks in advance!
## Post #34
- Username: Icetric
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 09, 2017 6:19 pm
- Post datetime: 2017-02-15T12:55:02+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

Hello, I now be badly in need of LZ77. DLL source code, but do you have? Can you give me a? Thank you very much! My email is [849392294@qq.com](mailto:849392294@qq.com)
## Post #35
- Username: currve
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 13, 2016 3:05 am
- Post datetime: 2017-06-29T12:17:40+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

hey guys,

thanks for developing such great tools like hex2obj and the py script to unpack the dice packs. I only run into an issue everytime I try to convert a chunk into obj using hex2obj. I've followed a couple of tutorials and doing things step by step exactly the same way, like:

- BF2015 final packs are extracted using the optimized py script
- .chunk and .mesh are together using the bf optimized management tool
- open the chunk in hex2obj first
- open the chunk in hexworkshop secondly
- find the hex value '0000010002' with all instances
- having now 2 or more instances
- using the second instance first to calculate it in hex mode and doing a thing like

# Try at model 1 with Error:
-> hex: instance2 - instance1 Enter = instanceNew -> Dec: /2 = indices count
-> hex: 11E568 - 120DB8 Enter = FFFFFFFFFFFFD7B0 -> Dec: -10320 / 2 = -5160 ?? wait what? why negative? I understand the mathematical reason why but that can't be the correct way to use it.
-> converting failed because of the negative indices count

# Try at model 2 with Error:
-> hex: instance2 - instance1 Enter = instanceNew -> Dec: /2 = indices count
-> hex: 8854 - 7F30 Enter =  -> Dec: 2340 / 2 = 1170 verts count
-> open up the mesh brings a totally mess and not the desired results. Any ideas here? 

Have I done something wrong? Thanks already for the answers
## Post #36
- Username: Icetric
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 09, 2017 6:19 pm
- Post datetime: 2017-07-15T01:42:48+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

Hi,Batch_Itexture_Converter(SWBF) tip me "Never to field "ITexture. DDSHeader. M_reserved" assignment, the field will keep its default value is null", And some other unassigned variables，And compiled tools can't Select Itexture, can you help me? thank you
## Post #37
- Username: Staedtler
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 11:45 pm
- Post datetime: 2018-07-28T14:59:18+00:00
- Post Title: Re: Star Wars Battlefront 2015 tools

Hey man,

the download link for Battlefield 4 python script by mr FrankElstner is currently down, can you make a new one, please?

Thanks.
