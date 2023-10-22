## Post #1
- Username: xyzzrp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 01, 2021 5:10 am
- Post datetime: 2023-02-10T02:06:25+00:00
- Post Title: Nocturne model/anim formats

Hi!

Can someone take a shot at Nocturne (1999, Terminal Reality) model formats? Extracted from POD, they are in DFM (model) and SKL (anims) format. They can also be exported from the official editor in S3D format (Simple 3D), but the plugins included are for an ancient version of Max which wont install nowadays. I was not able to find any importer for S3D too.

I cant attach up a 500kb zip file so I put them on GDrive. Included are DFM, SKL and exported S3D.

[https://drive.google.com/file/d/10hmZX9 ... p=drivesdk](https://drive.google.com/file/d/10hmZX9rF059HBQ_HYjvxAJkllGZd0Vwm/view?usp=drivesdk)

There is also the official editor which includes the old plugins and some format documentation.

[https://www.moddb.com/downloads/nocturne-editor](https://www.moddb.com/downloads/nocturne-editor)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-02-10T06:53:37+00:00
- Post Title: Nocturne model/anim formats

Hi!

Well, both formats, the .s3d and the "raw" .DFM are pure ASCII files. So simply add a .txt extension.

Excerpt from bride.s3d.txt:

// vertList: x,y,z
-0.628759,0.0208607,-0.0048598
-0.443589,0.0155997,-0.498724
-0.674191,0.0109659,-0.663217
-0.815357,0.000100909,-0.0595589
-1.00275,0.0208007,-0.51042
-0.444428,0.233365,-0.380122
-0.606753,0.234051,-0.085092
...

>>> Add a preceeding "v " to each line to get a point cloud.

Triangles are harder to track:

// triList: materialIndex,vertices(index, texX, texY)
0, 1,207,200.859, 0,216.711,199.566, 2,216.828,199.789
0, 2,216.828,199.789, 0,216.711,199.566, 3,222.586,201
0, 2,216.828,199.789, 3,222.586,201, 4,233.156,200.031
0, 5,207.855,189.547, 0,216.711,199.566, 1,207,200.859
0, 6,216.613,188.012, 0,216.711,199.566, 5,207.855,189.547
0, 0,216.711,199.566, 7,223.105,188.598, 3,222.586,201

From the format description it says:
textureIndex, vertexIndex1,u1,v1, vertexIndex2,u2,v2, vertexIndex2,u2,v2

Maximum vertexindex for bride appears to be 407 which matches the number of vertex lines of vertList.
All u1, v1 pairs seem to be identical for the same vertexIndex. 

>>> So I'd grab the first occurence of any vertexIndex and sort those lines together.
Adding of "vt " required.

>>> Triangles list can be composed by creating lines like 
f vertexIndex1 vertexIndex2 vertexIndex3

Sadly the Nocturne Editor doesn't work when trying to execute, error message is:
---------------------------
Please copy Nocturne to your hard drive

File: inivar.cpp
Line: 87
---------------------------

Seems you'll need Windows XP to start it:
“Nocturne” doesn’t run on Windows 7 and higher.

(It has .S3D import/export plug-ins for Max 2.x and Max 3.0 only, so that would not help either.)
## Post #3
- Username: xyzzrp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 01, 2021 5:10 am
- Post datetime: 2023-02-10T12:43:54+00:00
- Post Title: Nocturne model/anim formats

There's an installer on MyAbandonware that is already fully patched and works on Win10. The only things not working properly are the menus, they take a lot of time to execute the commands.

Well I know nothing about reversing models (why I asked here). 

I guess the only way would be to figure out a way to install Max 2/3. Maybe find a portable version, or use a virtual machine.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-02-10T16:05:08+00:00
- Post Title: Nocturne model/anim formats

> Reply from xyzzrp ↑Fri Feb 10, 2023 8:43 pm at Fri Feb 10, 2023 8:43 pm
>
> I guess the only way would be to figure out a way to install Max 2/3. Maybe find a portable version, or use a virtual machine.Whatever. Or learn how to code.
.



bride_point_cloud.png (17.49 KiB) Viewed 252 times
## Post #5
- Username: xyzzrp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 01, 2021 5:10 am
- Post datetime: 2023-02-10T23:25:44+00:00
- Post Title: Nocturne model/anim formats

I have gotten into C++ programming lately for specific purposes not even close related to models or formats.

Anyhow. Using VBox. Running WinXP and 3DS 2.5 I managed to load the s3d only to find out there are no animations inside. They appear to be in the skl file. I dont think thats even the TPose, nocturne editor might export to s3d the current frame.

The textures appear to be exportable via BloodRayne toolset.
[Clipboard02.jpg](https://xentaxbackup.github.io/file/23401_Clipboard02.jpg)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-02-11T11:14:52+00:00
- Post Title: Nocturne model/anim formats

With some efforts it should be possible to create a .smd file from a .skl file:

// boneList
"Bip01 Pelvis", -1
"Bip01 L Thigh", 0
"Bip01 R Thigh", 0
"Bip01 Spine", 0
...

// reference bone org list: x,y,z
-0.000496486,-2.71782,-0.593064
-0.554033,0,-1.01328e-006
0.554033,0,1.01328e-006
...

// angle list: w,x,y,z
0.994919,-0.100678,7.95486e-008,-2.58666e-007
0.974202,-0.225037,0.0154768,0.00697736
0.974413,-0.223907,-0.0194872,-0.00250365
...

// root offset list: x,y,z
0,0,0
-4.40003e-005,-0.00138998,0
-5.21997e-005,-0.00277996,0
...
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-02-11T19:09:45+00:00
- Post Title: Nocturne model/anim formats

> Reply from xyzzrp ↑Fri Feb 10, 2023 10:06 am at Fri Feb 10, 2023 10:06 am
>
> 
 S3D format (Simple 3D)
I made a plugin for Noesis.
texture files should be near the model (RAW-pixdata, ACT-paldata)

*(strange, but I did not see information about the textures (width,height, etc.), I think all the textures in the game are 256x256)
[fmt_s3d.zip](https://xentaxbackup.github.io/file/23403_fmt_s3d.zip)
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-02-11T21:37:26+00:00
- Post Title: Nocturne model/anim formats

> Reply from xyzzrp ↑Fri Feb 10, 2023 10:06 am at Fri Feb 10, 2023 10:06 am
>
> 
SKL (anims) format.
only skeleton

[fmt_skl.zip](https://xentaxbackup.github.io/file/23404_fmt_skl.zip)
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-02-12T10:02:37+00:00
- Post Title: Nocturne model/anim formats

I have finished my Nocturne Engine ASCII *.KFM load module.
It supports the version 5, 6, 7, 8 ASCII *. KFM files.

I am working on the Binary version of .KFM files.





Nocturne_Engine_KFM.jpg (65.11 KiB) Viewed 137 times
## Post #10
- Username: xyzzrp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 01, 2021 5:10 am
- Post datetime: 2023-02-12T20:00:46+00:00
- Post Title: Nocturne model/anim formats

> Reply from Karpati ↑Sun Feb 12, 2023 6:02 pm at Sun Feb 12, 2023 6:02 pm
>
> 
I have finished my Nocturne Engine ASCII *.KFM load module.
It supports the version 5, 6, 7, 8 ASCII *. KFM files.

I am working on the Binary version of .KFM files.

Awesome! But what game uses binarized KFM?

> Reply from Durik256 ↑Sun Feb 12, 2023 5:37 am at Sun Feb 12, 2023 5:37 am
>
> 
only skeleton

Sweet. Thanks for the plugins!  So the animations are not actually in the SKL, or the plugin just dont support it?
## Post #11
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-02-13T07:14:43+00:00
- Post Title: Nocturne model/anim formats

> Reply from xyzzrp ↑Mon Feb 13, 2023 4:00 am at Mon Feb 13, 2023 4:00 am
>
> 
Awesome! But what game uses binarized KFM?

It is funny, because I did find the binary .kfm files in the game you posted here (Nocturne).

See the following files for example:

AMMOBAG.KFM
BAT.KFM 
BATCREEP.KFM
CANDLE.KFM
## Post #12
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-02-22T18:02:11+00:00
- Post Title: Nocturne model/anim formats

I have finished my
Nocturne Engine ASCII	*.KFM,
Terminal Reality TRI Tools	*.S3D loader modules.

I have released the following program:
- 3D Object Converter v10.002 (Windows)

How to get the 3D Object Converter v10.002:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version (if you don’t have it yet).
(Or just use the Help/Check for updates... function to get the v10.002.)
