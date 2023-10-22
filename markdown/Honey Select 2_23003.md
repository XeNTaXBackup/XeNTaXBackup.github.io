## Post #1
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-14T12:13:10+00:00
- Post Title: Honey Select 2

I am in the process of compiling Honey Select 2 models within C4D, I wanted the models to have full working facial morphs.

Attached link is a test file containing the head and added morphs files using pose morph and xpresso tags, I wondered if anyone could check and let me know if there might be a better way to achieve this. Moving the various morphs is achieved by selecting the pose morph tag on the head mesh with which I made the driver for some of the basic movements.

Thanks Graeme

[https://drive.google.com/file/d/1TDAFHV ... sp=sharing](https://drive.google.com/file/d/1TDAFHV7q_1mzIeUeCZ6qXEsId-3wOXiy/view?usp=sharing)
## Post #2
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-16T10:16:59+00:00
- Post Title: Honey Select 2

I have compiled the head+morphs, hair and body files making a fully rigged figure.
The neck+body join needs point snapping? but all seems to be working, now need to add clothing sets etc.

[https://drive.google.com/file/d/1YbtQih ... sp=sharing](https://drive.google.com/file/d/1YbtQihAETh75gAcZReLL1Wx7kD_y98xf/view?usp=sharing)

What would be the best way to re-colour the eye files?
[c_t_eye_01-DXT1.png](https://xentaxbackup.github.io/file/19036_c_t_eye_01-DXT1.png)
## Post #3
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-17T09:06:51+00:00
- Post Title: Honey Select 2

Included an FBX file for anyone who wants to check how the face morphs and rig functions within other software.

Added clothing and some alpha maps, need to work on how best to get workable textures.

[https://drive.google.com/file/d/1cB0Icm ... sp=sharing](https://drive.google.com/file/d/1cB0IcmkKBb_i26Yx9V2Tk72mvMySyxOv/view?usp=sharing)
[Clipboard01.jpg](https://xentaxbackup.github.io/file/19041_Clipboard01.jpg)
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-11-20T20:39:51+00:00
- Post Title: Honey Select 2

Are you trying to build a tool, or do you wanna keep it in c4d?
Great job man!
## Post #5
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-21T08:34:24+00:00
- Post Title: Honey Select 2

Hi Henchman800, using C4D just to compile the models the end result being working fbx files that can be used in most 3D software.

The eye textures have been solved using Gimp by extracting RGB:
1. Open 3 copies of the eye texture
2. Colors\Components\Extract Component\ Choose RGB Red for one copy RGB Green for another, then RGB Blue for the last
3. Colors\Color to Alpha - Select the black and the alpha is created
4. RGB Blue use Colors\Invert giving a black base
5. Copy Paste in place RGB Red + Green onto RGB Blue layer
6. Colour the RGB Red layer using Colors\Map\Color Exchange 
7. Layer Mode Screen 50% on both RGB Red+ Green layers
[c_t_eye_01_blue_00.png](https://xentaxbackup.github.io/file/19058_c_t_eye_01_blue_00.png)
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-11-21T13:15:19+00:00
- Post Title: Honey Select 2

Nice progres man!
Cant wait for more
## Post #7
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-22T10:15:57+00:00
- Post Title: Honey Select 2

I am still unsure the best method to connect morphs so when exported the link works between: eyelashes to eyelids - mouth to teeth and tongue
Below link of T-Pose model + textures

[https://drive.google.com/file/d/1AqWNbm ... sp=sharing](https://drive.google.com/file/d/1AqWNbmDSyC2Cf-vILrKQFazI-Y-MD_en/view?usp=sharing)

Render and quick pose+face morphs
[HS2_BARG_TESTRender.jpg](https://xentaxbackup.github.io/file/19061_HS2_BARG_TESTRender.jpg)
## Post #8
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-24T10:23:17+00:00
- Post Title: Honey Select 2

I think I've solved the challenges of extracting and compiling these models, the interchangable assets are endless, so maybe a guide on how to extract & compile would be helpful so you can build your own characters?

Here is another sample file, FBX attached with the C4D file.

[https://drive.google.com/file/d/1ZM2n1k ... sp=sharing](https://drive.google.com/file/d/1ZM2n1klYP1qbazcyzsJETdKzzEzN0wV6/view?usp=sharing)
[Clipboard02.jpg](https://xentaxbackup.github.io/file/19076_Clipboard02.jpg)
## Post #9
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-11-24T17:51:14+00:00
- Post Title: Honey Select 2

Great job man!
And yeah, that Guide would be awesome!!!
## Post #10
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-25T09:53:08+00:00
- Post Title: Honey Select 2

Honey Select 2: Part 1 - Extraction - Base Files

Tools - SB3Utility [https://github.com/enimaroah/SB3Utility/releases](https://github.com/enimaroah/SB3Utility/releases)

Run SB3UtilityGUI.exe [Do not run as admin]

1.Body: Honey Select 2\abdata\chara\oo_base.unity3d
  Drag+Drop oo_base.unity3d into SB3UtilityGUI
  Double Click p_cf_body_00
  Select Mesh Tab - Select o_body_cf - Preview will display all selected - Export FBX2020.0.1
  [The other mesh is not required]
  p_cf_body_00 = Female
  p_cm_body_00 = Male
  Texture Tab: Shift+Select ALL - Export

  You will have created a folder: oo_base\p_cf_body_00\meshes0.fbx + .dds files

2.Head: Honey Select 2\abdata\chara\00
  ao_ = Accessories
  fo_ = Female Models
  ft_ = Female Textures
  mo_ = Male Models
  mt_ = Male Textures
  so_ = Hair Models
  st_ = Texture Details

  Drag+Drop fo_head_00.unity3d into SB3UtilityGUI
  Double Click p_cf_head_00
  Select Mesh Tab - Shift+Select All Mesh - Preview will display all selected - Export FBX2020.0.1
  Morphs:
  Select Mesh Head ONLY - Select Morph Tab - head [o_head] - Export FBX 2020.0.1
  Select Mesh Eyelashes - Select Morph Tab - lash [o_eyelashes] - Export FBX 2020.0.1
  Same method with: namida, tang & teeth
  Do The same with p_cf_head_01
  Texture Tab: Shift+Select ALL - Export

  You should have a folder named fo_head_00\p_cf_head_00\ and \p_cf_head_01
  meshes0.fbx, o_eyelashes-lash-0.fbx, o_head-head-0.fbx, o_namida-namida-0.fbx, o_tang-tang-0.fbx, o_tooth-tooth-0.fbx + .dds files

3.Textures: FemaleFace - ft_skin_f_00.unity3d
                  FemaleBody - ft_skin_b_00.unity3d
  Extract all the st_ files

4.Hair: so_hair_f_00.unity3d = Front
           so_hair_b_00.unity3d = Back
           so_hair_s_00.unity3d = Side
	   so_hair_o_00.unity3d = Accessories
		Extract all as above.

Move all folders\files created to a working folder for clear\easy access.
## Post #11
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-25T11:03:58+00:00
- Post Title: Honey Select 2

Honey Select 2: Part 2 - Eye+Face Textures

Tools - Gimp [https://www.gimp.org](https://www.gimp.org)

Run Gimp: Attached templates for eye & face

[https://drive.google.com/file/d/1nJXPYj ... sp=sharing](https://drive.google.com/file/d/1nJXPYj7-W06v-xTY750ijL4S3sSerqDa/view?usp=sharing)

Above file will make it much easier to swap eye designs\colours makeup, brows & lips for the face

IMPORTANT: Adding colour to the layers e.g eyeshadow - Colors\Map\Color Exchange - Use Pick Color then choose color to replace
This feature within Gimp is also excellent for changing the colours of any texture by adjusting the RGB Threshold to get the look you require.

When swapping eye textures: As mentioned in a previous post omitting the RGB Blue layer
1. Open 2 copies of the eye texture
2. Colors\Components\Extract Component\ Choose RGB Red for one copy RGB Green for another
3. Colors\Color to Alpha - Select the black and the alpha is created
4. Copy & Paste in place RGB Red + Green into the eye template
5. Colour the RGB Red layer using Colors\Map\Color Exchange
## Post #12
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-28T10:01:05+00:00
- Post Title: Honey Select 2

Honey Select 2: Part 3 - Head Fix

NOTE: This process will no doubt be available in Blender and 3DSMax.

C4D\File\Merge from folder created with SB3Utility extraction:
fo_head_00\p_cf_head_00\meshes0.fbx

C4D: Import Settings
Geometry
Convert Normals to Phong Tag Edge Breaks [Untick This Feature]

Tools - [C4D] Selection To Object [https://matniedoba.de/selection-to-object-split/](https://matniedoba.de/selection-to-object-split/)

[1] Apply a face texture to the head and this occurs, there are 3 head meshes grouped causing this problem



HeadFix_1.jpg (22.24 KiB) Viewed 425 times
## Post #13
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-28T10:01:48+00:00
- Post Title: Honey Select 2

[2] Main Menu\Extensions\Selection to Object - This will split the mesh and fix the texture



HeadFix_2.jpg (44.11 KiB) Viewed 425 times
## Post #14
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-28T10:02:34+00:00
- Post Title: Honey Select 2

[3] Rename one of the meshes to o_head_0 and drag it outside the node as shown, then delete the node + the 2 other meshes, I then delete 2 of the UV tags also delete the skin tag because after splitting the mesh the bones do not function.



HeadFix_3.jpg (39 KiB) Viewed 425 times
## Post #15
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-28T10:03:21+00:00
- Post Title: Honey Select 2

[4] Fix the head by adding: Character\skin then drag & drop the skin tag beneath the head mesh as shown



HeadFix_4.jpg (37.53 KiB) Viewed 425 times
## Post #16
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-29T09:33:42+00:00
- Post Title: Re: Honey Select 2

Honey Select 3: Part 4 - Compiling

Required Component:
oo_base\p_cf_body_00\meshes0.fbx

You will need to find the clothing\accessories you require to build your character:
  ao_ = Accessories
  fo_ = Female Models
  ft_ = Female Textures
  mo_ = Male Models
  mt_ = Male Textures
  so_ = Hair Models
  st_ = Texture Details
Honey Select 2\abdata\chara\30 [This folder contains a good selection]
Extract using SB3Utility as described in Part 1
Example: h2mcon = Concierge - Which has 9 components bra,top,socks,shoes,garter,shorts,bot,neck & head

Compiling the FBX files:

NOTE: This is where a script would be very useful, I am searching for other methods but at the moment this does a great job and will have to suffice.

Tools: Motion Builder [Download FREE 30 Day Trial] 
[https://www.autodesk.com/products/motio ... antity=1#0](https://www.autodesk.com/products/motionbuilder/overview?plc=MOBPRO&term=1-YEAR&support=ADVANCED&quantity=1#0)


Motion Builder:
File Open - oo_base\p_cf_body_00\meshes0.fbx
Open Options - Select Open
View - Drop Down Menu - Above Left - Frame Selected
File Merge - Example: fo_top_30\p_cf_top_h2mcon\meshes0.fbx
Merge all files required to build your character
Save as xxx.fbx

NOTE: Accessories will not conform\postion to the body, they will be added at the origin\root\feet.
Add them to the build as they can be positioned and fixed to a bone later.
## Post #17
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2021-06-08T06:47:53+00:00
- Post Title: Re: Honey Select 2

Finally a plugin that exports character models [FBX + PNG Textures]

Grey's mesh exporter 1.0.2.7

Link: [https://github.com/FlailingFog/KK-Blend ... master/GME](https://github.com/FlailingFog/KK-Blender-Shader-Pack/tree/master/GME)

Install:
1. Copy\Paste both UnityFbxExporter dll's to Root folder
2. Copy\Paste HS2MeshExporter.dll to BepInEx\Plugins folder
3. Open Game\Studio Press 'Numpad Minus' [This will create an Export folder within Root with FBX + Textures]

Enjoy.
## Post #18
- Username: NovaShard
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 24, 2017 11:16 pm
- Post datetime: 2021-09-12T00:39:12+00:00
- Post Title: Re: Honey Select 2

Thank you! I hope this works. <__> with exporting to Unreal? if it's not too stressful can you link me to a place where it's possible?
?
## Post #19
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2021-09-12T06:55:32+00:00
- Post Title: Re: Honey Select 2

Hi NovaShard, I just noticed Grey's Mesh Exporter has been updated to 1.5.5, will test later.
I am not sure what link you require?
The fbx format is universal within 3d software so you should have no problem importing\merging\opening within Unreal.

Just tested Grey's Mesh Exporter 1.5.5 - Honey Select 2 DX

Working fine, although make sure you place 'HS2MeshExporter.dll' into: BepInEx\Plugins\
Will not work if just copied into BepinEx folder.

Grey's Menu will appear when loading Studio.
## Post #20
- Username: NovaShard
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 24, 2017 11:16 pm
- Post datetime: 2021-09-13T02:03:31+00:00
- Post Title: Re: Honey Select 2

I have them both and yes I see the grey tab to export ^__^.
Thanks, I was thinking would I have to redo everything like add her clothes and all of that. Like the bone rigging and all that good stuff. I will find out soon enough!
Again, thanks for replying back.

edit: I can't seem to get the model from honey select to appear with anything.
Only use for hs studio's? I have the plugs right from the folder to where it says to put them in. 



HS plug HSP.png (8.45 KiB) Viewed 241 times



damn, got it working at least after downloading a modpack
## Post #21
- Username: AmazingFun
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 08, 2021 5:32 pm
- Post datetime: 2021-12-09T05:33:25+00:00
- Post Title: Re: Honey Select 2

that tool is helpful, but the armature totally are messed up .
Can you share some kwnoledge about processing the fbx?
textures are confusing part , mostly the eyeshadow and eyebase.
## Post #22
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2021-12-09T08:50:12+00:00
- Post Title: Re: Honey Select 2

@AmazingFun
Which 3d software are you using when importing the fbx file? 
All functions and face morphs should be available.
The eyeshadow requires an alpha material, I covered the eyebase earlier in this thread.
## Post #23
- Username: AmazingFun
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 08, 2021 5:32 pm
- Post datetime: 2021-12-09T14:21:08+00:00
- Post Title: Re: Honey Select 2

> Reply from X3D ↑Thu Dec 09, 2021 4:50 pm at Thu Dec 09, 2021 4:50 pm
>
> 
@AmazingFun
Which 3d software are you using when importing the fbx file? 
All functions and face morphs should be available.
The eyeshadow requires an alpha material, I covered the eyebase earlier in this thread.

Just realized blender is not a fbx-friendly software, need to do a little fix.
i will try your eyebase method, thank you.
btw, do you have any hint for extracting pose & animation?
## Post #24
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2021-12-09T15:55:39+00:00
- Post Title: Re: Honey Select 2

The process I use is to import the fbx into Blender which cleans all the useless nodes from the rig\armature, then export for use in C4D.

Animation isn't an option using Greys Exporter at the moment, but poses are fine.

I exported animations using SB3Utlity [https://github.com/enimaroah/SB3Utility/releases](https://github.com/enimaroah/SB3Utility/releases) but then you need to go down the extremely long process as explained in the beginning of the thread to use them, retarget etc.
## Post #25
- Username: AmazingFun
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 08, 2021 5:32 pm
- Post datetime: 2021-12-10T15:17:54+00:00
- Post Title: Re: Honey Select 2

ok, the tool is cool and it is time to learn some new skill ,since have heard it long ago.
About the facial morph, it is controlled by real-time invoke ? is there any code or something that can help people to understand the procedure ? curious about the design pattern.
## Post #26
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2021-12-10T16:16:44+00:00
- Post Title: Re: Honey Select 2

The facial morphs appear as a tag on the mesh which has sliders to adjust the various expressions, understanding your chosen 3D software is 90% of the battle.
As I mentioned earlier in this topic, I could not find a way to link morph sliders easily within C4D, I'm sure there will be a method detailed somewhere.
Example:
If you used the head morph tag to close the eyes by 50%, you would also need to adjust the morph tags on other mesh objects connected to that area by 50% too, like eyelashes, eyebrows etc., so if you opened the mouth you would also have to move the teeth and tongue separately.
Again, it depends which 3D software you learn, maybe other programs have a basic option to link morph tags with a click of a button?
## Post #27
- Username: AmazingFun
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 08, 2021 5:32 pm
- Post datetime: 2021-12-11T05:43:17+00:00
- Post Title: Re: Honey Select 2

blender has the function for morph , called shape key.
users can record the variation into keyframe to achive the effect ,ie, a closed eye gradually opens in your frame rate.
have you tried other game，   all of the illusion game share the same animation ?
## Post #28
- Username: AmazingFun
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 08, 2021 5:32 pm
- Post datetime: 2021-12-11T05:58:12+00:00
- Post Title: Re: Honey Select 2

> Reply from AmazingFun ↑Fri Dec 10, 2021 11:17 pm at Fri Dec 10, 2021 11:17 pm
>
> 
ok, the tool is cool and it is time to learn some new skill ,since have heard it long ago.
About the facial morph, it is controlled by real-time invoke ? is there any code or something that can help people to understand the procedure ? curious about the design pattern.

about this question,i know how to do a equivalent effect, just interested in their design pattern  in variation control .
## Post #29
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2021-12-11T07:58:11+00:00
- Post Title: Re: Honey Select 2

Koikatsu has a different naming convention for the skeleton but like most 3D models within games they all follow the same guidelines\patterns utilizing physics, morphs, weights, rigs, mesh, and textures encoded into different formats to protect them.
Yes, blender shows the morph tag with its own brand called shape keys, but I only use blender as a stepping stone, maybe it has a function to link shape keys? if so I may be more interested in using it.
I am not sure what you mean by 'design patterns' and their 'variation control' or do you mean how the morphs themselves are created and used? again that will depend on the 3D software used.
## Post #30
- Username: AmazingFun
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 08, 2021 5:32 pm
- Post datetime: 2021-12-12T10:43:37+00:00
- Post Title: Re: Honey Select 2

simply,every morph is a single variation , combine them to result a expectation . 
in the former post , i wanted to know how the popular game company to collect factors to get a decent result or just use specified value ,not software, just algorithm. let it go.
if you want correlate morph, simply  add a new combine morph or a master 'button' using api ,many methods there . it is a common request in blender and maya.
## Post #31
- Username: Onetimeposter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 13, 2021 8:25 am
- Post datetime: 2021-12-13T01:15:49+00:00
- Post Title: Re: Honey Select 2

Just an fyi since I came across this: I am going to be removing the Grey's Mesh Exporter rehost from the KK-Blender-Shader repository probably within the next month or two, so you might want to use the permalink or grab it directly off of the illusion soft discord from Grey:
[https://github.com/FlailingFog/KK-Blend ... 201.5.5.7z](https://github.com/FlailingFog/KK-Blender-Porter-Pack/blob/9fcef4127ba56b4e8e8718fb546945fc00eaaad9/GME/Grey%27s%20mesh%20exporter%201.5.5.7z)

> Reply from X3D ↑Sat Dec 11, 2021 12:16 am at Sat Dec 11, 2021 12:16 am
>
> 
Example:
If you used the head morph tag to close the eyes by 50%, you would also need to adjust the morph tags on other mesh objects connected to that area by 50% too, like eyelashes, eyebrows etc., so if you opened the mouth you would also have to move the teeth and tongue separately.
Again, it depends which 3D software you learn, maybe other programs have a basic option to link morph tags with a click of a button?

In blender this can be done with drivers that link the morph values. There's also scripting functions that can merge the morphs together automatically. C4D probably has something similar for automation.
Here's an example of a short script that automatically merges the morphs for Koikatsu models (these are similar to honey select morphs): [https://github.com/FlailingFog/KK-Blend ... #L277-L398](https://github.com/FlailingFog/KK-Blender-Porter-Pack/blob/V5-merger/importing/shapekeys.py#L277-L398)
## Post #32
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2021-12-13T07:49:10+00:00
- Post Title: Re: Honey Select 2

Thankyou Onetimeposter for the information.
## Post #33
- Username: kskui008
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 04, 2018 11:56 am
- Post datetime: 2022-10-13T12:13:24+00:00
- Post Title: Re: Honey Select 2

> Reply from X3D ↑Wed Nov 25, 2020 7:03 pm at Wed Nov 25, 2020 7:03 pm
>
> 
Honey Select 2: Part 2 - Eye+Face Textures

Tools - Gimp https://www.gimp.org

Run Gimp: Attached templates for eye & face

https://drive.google.com/file/d/1nJXPYj ... sp=sharing

Above file will make it much easier to swap eye designs\colours makeup, brows & lips for the face

IMPORTANT: Adding colour to the layers e.g eyeshadow - Colors\Map\Color Exchange - Use Pick Color then choose color to replace
This feature within Gimp is also excellent for changing the colours of any texture by adjusting the RGB Threshold to get the look you require.

When swapping eye textures: As mentioned in a previous post omitting the RGB Blue layer
1. Open 2 copies of the eye texture
2. Colors\Components\Extract Component\ Choose RGB Red for one copy RGB Green for another
3. Colors\Color to Alpha - Select the black and the alpha is created
4. Copy & Paste in place RGB Red + Green into the eye template
5. Colour the RGB Red layer using Colors\Map\Color Exchange

Great, but I would like to ask, can the texture of the eyes be repaired by PS? I don't understand how Gimp works, sorry for my bad English。。。
Also, I didn't get the correct diffuse textures with SB3Utility, body and face textures I'll get with Ninjaripper. But anyway trying to get the texture for it is an amazing job, thanks for your work here。
