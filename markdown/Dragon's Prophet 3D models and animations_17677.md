## Post #1
- Username: Cippman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 18, 2017 1:25 am
- Post datetime: 2018-02-07T22:56:38+00:00
- Post Title: Dragon's Prophet 3D models and animations

Hi guys I'm Cippman, I'm a newbie here,
I'm searching for a tool like the bone importer of models [viewtopic.php?f=16&t=11217](http://forum.xentax.com/viewtopic.php?f=16&t=11217) that do the same thing to .ras animation files of Dragon's Prophet. These .ras files contains the bones name and some other binary data (after each bonename) that probably contains bone's position/rotation/scale/(don't know) during animation.
Anyone can help me? I searched almost everywhere about .ras files but I didn't found the right infos.

Notes: sometimes the script for importing "_skeleton.ros"   and "model_name".ros makes 3dStudioMax to EAT all ram (yes, even if you have 16gb or more) or it goes in exception (I'm not practical of max scripts but if needed link is here, I don't remember what is the original but I re-share both:
v1: [https://drive.google.com/open?id=1CHbek ... 048i2JWiUy](https://drive.google.com/open?id=1CHbekuVtcILN1_I6SZerhA048i2JWiUy) 
v2: [https://drive.google.com/open?id=1L-Ejr ... g2Ad7qI1JX](https://drive.google.com/open?id=1L-EjryIugAiCEUbhUCu-yPg2Ad7qI1JX)
Probably if a .ros model contains even some ''animations'' or "other details" that script isn't able to import it (as for the Skitter model, for example).
Even the act_"any-name".ros or mal-"any-name".ros or few others .ros can not be opened or imported in 3dStudioMax.
Someone can fix this, please?

(I tried even Intel GPA to rip any geometry of any application at runtime, so even dragon's prophet, but... the exported result sucks with this game.)

I've already exctracted... all files with the IDXUnpacker (as procedure found on web somewhere), even on european forum of the game [http://www.dragonspropheteurope.com/for ... -3dcg-art/](http://www.dragonspropheteurope.com/forum/topic/28060-tut-using-dragon-models-for-3dcg-art/) and in someother to get that. Here's a copy of IDXUnpacker: [https://drive.google.com/open?id=16oXbQ ... qtgbNmVLWU](https://drive.google.com/open?id=16oXbQl2Sg-Wu1nXYjmKIXoqtgbNmVLWU)
Importing even the 3d models is nice, but I'd like to get even the .ras animations! 

I came some years later after Dragon's Prophet gold-times but I hope to find some help  

ATTACHMENTS for who want to try to do something with some ''.ros" and ".ras" files without download the 13gb of dp client and IDXUnpacking it: 
vargs: [https://drive.google.com/open?id=1SBZU4 ... WoWawoLff1](https://drive.google.com/open?id=1SBZU4Zci78rSc-1ZkygXA4WoWawoLff1)
celers: [https://drive.google.com/open?id=1ys_nT ... H6zFFs8-lj](https://drive.google.com/open?id=1ys_nTHSGZEPk1DazzOeEBAH6zFFs8-lj)
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2018-03-01T18:38:57+00:00
- Post Title: Dragon's Prophet 3D models and animations

Here is a blend file to import ros and ras files.
Need to install Blender version 249 and Python version 26x (32bits).
Doubleclick "Blender249.blend" and in Blender Text Window press alt+p

First import all meshes - *.ros files
Than file with "skeleton" in name
And at the end select armature in 3d window and import animation from *.ras

Not all works, but most. 
Script is free so you can modify, copy...
[Blender249[DragonsProphet][PC][ros][ras][2018-03-01].zip](https://xentaxbackup.github.io/file/13979_Blender249[DragonsProphet][PC][ros][ras][2018-03-01].zip)
## Post #3
- Username: Cippman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 18, 2017 1:25 am
- Post datetime: 2018-03-08T20:43:12+00:00
- Post Title: Dragon's Prophet 3D models and animations

> Reply from Szkaradek123
>
> Here is a blend file to import ros and ras files.
Need to install Blender version 249 and Python version 26x (32bits).
Doubleclick "Blender249.blend" and in Blender Text Window press alt+p

First import all meshes - *.ros files
Than file with "skeleton" in name
And at the end select armature in 3d window and import animation from *.ras

Not all works, but most. 
Script is free so you can modify, copy...

Thanks, I love you!
## Post #4
- Username: grawiorum
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 05, 2017 1:09 am
- Post datetime: 2020-07-09T19:39:26+00:00
- Post Title: Dragon's Prophet 3D models and animations

> Reply from Szkaradek123 ↑Fri Mar 02, 2018 2:38 am at Fri Mar 02, 2018 2:38 am
>
> 
First import all meshes - *.ros files
Than file with "skeleton" in name
And at the end select armature in 3d window and import animation from *.ras

is it possible to import a modified mash back into the game
## Post #5
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-07-10T13:18:06+00:00
- Post Title: Dragon's Prophet 3D models and animations

> Reply from Cippman ↑Thu Feb 08, 2018 6:56 am at Thu Feb 08, 2018 6:56 am
>
> 
Hi guys I'm Cippman, I'm a newbie here,
I'm searching for a tool like the bone importer of models http://forum.xentax.com/viewtopic.php?f=16&t=11217 that do the same thing to .ras animation files of Dragon's Prophet. These .ras files contains the bones name and some other binary data (after each bonename) that probably contains bone's position/rotation/scale/(don't know) during animation.
Anyone can help me? I searched almost everywhere about .ras files but I didn't found the right infos.

Notes: sometimes the script for importing "_skeleton.ros"   and "model_name".ros makes 3dStudioMax to EAT all ram (yes, even if you have 16gb or more) or it goes in exception (I'm not practical of max scripts but if needed link is here, I don't remember what is the original but I re-share both:
v1: https://drive.google.com/open?id=1CHbek ... 048i2JWiUy 
v2: https://drive.google.com/open?id=1L-Ejr ... g2Ad7qI1JX
Probably if a .ros model contains even some ''animations'' or "other details" that script isn't able to import it (as for the Skitter model, for example).
Even the act_"any-name".ros or mal-"any-name".ros or few others .ros can not be opened or imported in 3dStudioMax.
Someone can fix this, please?

(I tried even Intel GPA to rip any geometry of any application at runtime, so even dragon's prophet, but... the exported result sucks with this game.)

I've already exctracted... all files with the IDXUnpacker (as procedure found on web somewhere), even on european forum of the game http://www.dragonspropheteurope.com/for ... -3dcg-art/ and in someother to get that. Here's a copy of IDXUnpacker: https://drive.google.com/open?id=16oXbQ ... qtgbNmVLWU
Importing even the 3d models is nice, but I'd like to get even the .ras animations! 

I came some years later after Dragon's Prophet gold-times but I hope to find some help  

ATTACHMENTS for who want to try to do something with some ''.ros" and ".ras" files without download the 13gb of dp client and IDXUnpacking it: 
vargs: https://drive.google.com/open?id=1SBZU4 ... WoWawoLff1
celers: https://drive.google.com/open?id=1ys_nT ... H6zFFs8-lj

Can anyone help me?
I get a DLL Error when i want to open the Unpacker Exe
## Post #6
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-07-13T13:00:26+00:00
- Post Title: Dragon's Prophet 3D models and animations

Need Help oO
