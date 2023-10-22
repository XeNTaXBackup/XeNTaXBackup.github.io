## Post #1
- Username: dolan1995
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 18, 2020 3:22 pm
- Post datetime: 2022-06-05T19:20:08+00:00
- Post Title: Diablo Immortal models extracting

Hi, just wanna ask if anybody managed to extract models data from the game yet?
I used this QuickBMS script:
[https://aluigi.org/bms/netease_mpk.bms](https://aluigi.org/bms/netease_mpk.bms)

but only get very small results before the script return end error, with 1 title screen cg video (it's something i guess). Is this because they updated the encryption or something?
## Post #2
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-06-05T21:25:40+00:00
- Post Title: Diablo Immortal models extracting

An example model would be nice.
## Post #3
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-06-08T01:24:44+00:00
- Post Title: Diablo Immortal models extracting

As far as I can tell, there is no way currently to extract files from the PC version of Diablo Immortal MPK archives.

DIDT is the tool that can be used for the IOS/Android version:
[https://github.com/CucFlavius/DIDT](https://github.com/CucFlavius/DIDT)

Hopefully they will update their tool to include the PC version, as the PC Archives are around 23.2 GB in size, compared to the 6 GB size for the mobile versions.  I assume this is because the PC version has higher resolution textures.
## Post #4
- Username: dolan1995
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 18, 2020 3:22 pm
- Post datetime: 2022-06-08T06:18:22+00:00
- Post Title: Diablo Immortal models extracting

I managed to get these model files of Diablo from the Wowhead website's model viewer.
Unfortunately, I couldn't export them even with the same tools that successfully exported D2R's models.
Is there any updates to them or new tools that can work with the new models?

[https://mega.nz/folder/SU0HUALK#TTg11n-zWDZKlLNrCr7Vsg](https://mega.nz/folder/SU0HUALK#TTg11n-zWDZKlLNrCr7Vsg)
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-08T12:00:13+00:00
- Post Title: Diablo Immortal models extracting

@zardalu: Actually you can extract them with fixed [mpk script](https://zenhax.com/viewtopic.php?f=9&t=16089#p71884), but without original names - that's what DIDT is able to do (convert hashed names into actual ones by using resource.repository). Though currently renaming doesn't work properly due to minor differences in PC version.
## Post #6
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2022-06-08T21:06:38+00:00
- Post Title: Diablo Immortal models extracting

> Reply from dolan1995 ↑Wed Jun 08, 2022 2:18 pm at Wed Jun 08, 2022 2:18 pm
>
> 
I managed to get these model files of Diablo from the Wowhead website's model viewer.

Do you have a link?  That site is always confusing to me.

btw, those ".model" files are actually 4 files in one.  Model + Mesh + Material + SkinSkeleton.  Each subfile begins with a "MESSIAH" id.

do you know where does wowhead get it DI sources?  From PC or mobile?
## Post #7
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-06-08T21:11:59+00:00
- Post Title: Diablo Immortal models extracting

> Reply from Spiritovod ↑Wed Jun 08, 2022 8:00 pm at Wed Jun 08, 2022 8:00 pm
>
> 
@zardalu: Actually you can extract them with fixed mpk script, but without original names - that's what DIDT is able to do (convert hashed names into actual ones by using resource.repository). Though currently renaming doesn't work properly due to minor differences in PC version.

Thanks Spiritovod, trying this now!
## Post #8
- Username: dolan1995
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 18, 2020 3:22 pm
- Post datetime: 2022-06-09T07:49:17+00:00
- Post Title: Diablo Immortal models extracting

> Reply from roswell ↑Thu Jun 09, 2022 5:06 am at Thu Jun 09, 2022 5:06 am
>
> 
dolan1995 wrote: ↑Wed Jun 08, 2022 2:18 pm
I managed to get these model files of Diablo from the Wowhead website's model viewer.


Do you have a link?  That site is always confusing to me.

btw, those ".model" files are actually 4 files in one.  Model + Mesh + Material + SkinSkeleton.  Each subfile begins with a "MESSIAH" id.

do you know where does wowhead get it DI sources?  From PC or mobile?
[https://www.wowhead.com/diablo-immortal ... ablo-71815](https://www.wowhead.com/diablo-immortal/npc/diablo-71815)
Here's the link, just click the red "View in 3D" button near top of the page to load the viewer.
There's 2 more pages but i assume that's for his "ghost" versions, hence the "phantom-ish" leg effects.

You can search for more by going back to 
[https://www.wowhead.com/diablo-immortal/npcs](https://www.wowhead.com/diablo-immortal/npcs)

There's actually no download button, so before loading the viewer you can open the web developer tool, the network tab will cache all the files loaded, that's how i got them.

Also, i don't know which version of the game they used, they don't actually gave a source. Some models look low-res to fit a mobile game, some looks more detailed like Diablo here, but it's probably just the normal texture. I guess it's more likely it's the mobile version, cuz i mean the game was only planned for mobile only so i would assume the PC version is more of an HD port.
## Post #9
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2022-06-09T09:05:34+00:00
- Post Title: Diablo Immortal models extracting

> Reply from dolan1995 ↑Thu Jun 09, 2022 3:49 pm at Thu Jun 09, 2022 3:49 pm
>
> 
Also, i don't know which version of the game they used, they don't actually gave a source. Some models look low-res to fit a mobile game, some looks more detailed like Diablo here, but it's probably just the normal texture. I guess it's more likely it's the mobile version, cuz i mean the game was only planned for mobile only so i would assume the PC version is more of an HD port.

Just a guess, but if you squeeze your eyes in game, even on PC, you'll notice that outside the Main chars, Bosses, and some npcs, enemies have kinda a low-res/nothing special texture. That's kinda normal with games which use this "not so close camera" and various flashy effect, it makes you think the graphic is better than what actualy is.

I do find curious that the models are animated in the 3D viewer, albeit you can't change the animation.
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-09T09:21:33+00:00
- Post Title: Diablo Immortal models extracting

> Reply from dolan1995 ↑Wed Jun 08, 2022 2:18 pm at Wed Jun 08, 2022 2:18 pm
>
> 
Unfortunately, I couldn't export them
I still do not understand whether it was possible to open the models.  
took a quick look at the models and made a plugin.
(only mesh, maybe i'll finish it later)



 fmt_model.zip
(852 Bytes) Downloaded 94 times



UPDATE (click up arrow)

> Reply from Durik256 ↑Fri Jun 10, 2022 4:53 am at Fri Jun 10, 2022 4:53 am
>
> 
MeshToOBJ.exe
## Post #11
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-06-09T18:12:01+00:00
- Post Title: Diablo Immortal models extracting

> Reply from Durik256 ↑Thu Jun 09, 2022 5:21 pm at Thu Jun 09, 2022 5:21 pm
>
> 
dolan1995 wrote: ↑Wed Jun 08, 2022 2:18 pm
Unfortunately, I couldn't export them

I still do not understand whether it was possible to open the models.  
took a quick look at the models and made a plugin.
(only mesh, maybe i'll finish it later)

Thanks for this!

Which version of the .model files does your plugin work with?  

I followed Spiritovod's advice and was able to use the fixed mpk script to extract the files from the PC version, and then used DIDT to rename them.

I now have a PC version of extracted files (29.2GB), as well as an IOS and Android version (around 6GB each).

But I am unable to see the models of either version with your script:  Just says: "File could not be previewed".
## Post #12
- Username: dolan1995
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 18, 2020 3:22 pm
- Post datetime: 2022-06-09T19:10:29+00:00
- Post Title: Diablo Immortal models extracting

> Reply from zardalu ↑Fri Jun 10, 2022 2:12 am at Fri Jun 10, 2022 2:12 am
>
> 
Durik256 wrote: ↑Thu Jun 09, 2022 5:21 pm
dolan1995 wrote: ↑Wed Jun 08, 2022 2:18 pm
Unfortunately, I couldn't export them

I still do not understand whether it was possible to open the models.  
took a quick look at the models and made a plugin.
(only mesh, maybe i'll finish it later)



Thanks for this!

Which version of the .model files does your plugin work with?  

I followed Spiritovod's advice and was able to use the fixed mpk script to extract the files from the PC version, and then used DIDT to rename them.

I now have a PC version of extracted files (29.2GB), as well as an IOS and Android version (around 6GB each).

But I am unable to see the models of either version with your script:  Just says: "File could not be previewed".

I encountered the same problem at first, and I think Noesis defaulted to using the GR2 plugin so it couldn't view the files. You have to remove the GR2 plugin because it's conflicting with each other's targeted ".model" format.
## Post #13
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-06-09T20:40:03+00:00
- Post Title: Diablo Immortal models extracting

> Reply from dolan1995 ↑Fri Jun 10, 2022 3:10 am at Fri Jun 10, 2022 3:10 am
>
> 
I encountered the same problem at first, and I think Noesis defaulted to using the GR2 plugin so it couldn't view the files. You have to remove the GR2 plugin because it's conflicting with each other's targeted ".model" format.

Thanks Dolan, yes this was part of the problem.  I also figured out that Durik256 seems to have written his plugin for the .model files which come from the the Wowhead website's model viewer, not the files extracted via the DIDT method.  I was able to get it working when viewing Wowhead .model files.

As roswell mentioned, the .model files from Wowhead are actually 4 files in one. Model + Mesh + Material + SkinSkeleton. Unfortunately Wowhead does not include all models.

The .model files when extracted via " netease_mpk_v2.bms" and renamed via DIDT are actually split into 4 seperate files: .Model +. Mesh + .Material + .Skeleton.

Here is a skeletal mesh example:

[https://www.mediafire.com/file/t5iccshc ... o.rar/file](https://www.mediafire.com/file/t5iccshcbyzbvfb/npc_devil_diablo.rar/file)

Here are some static mesh examples:

[https://www.mediafire.com/file/zixtym0f ... l.rar/file](https://www.mediafire.com/file/zixtym0fuhfxd27/bw_hell.rar/file)
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-09T20:53:51+00:00
- Post Title: Diablo Immortal models extracting

\\\\\\\\\\\MeshToOBJ.exe
added preview. bugs fixed.
*(my personal 3D library created in pure c# without third-party libraries, etc.)
Link on github: [MeshToOBJ.exe](https://github.com/Durik256/Noesis-Plugins/blob/master/MeshToOBJ.exe)


\\\\\\\\\\\Noesis
for Noesis for *.mesh/*.model
link on github: [fmt_mesh_diablo.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_mesh_diablo.py)

OLD_PLUGIN:


 fmt_mesh_diablo.zip
(771 Bytes) Downloaded 111 times
## Post #15
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-06-09T22:30:32+00:00
- Post Title: Diablo Immortal models extracting

> Reply from Durik256 ↑Fri Jun 10, 2022 4:53 am at Fri Jun 10, 2022 4:53 am
>
> 
zardalu wrote: ↑Fri Jun 10, 2022 4:40 am
I also figured out that Durik256 seems to have written his plugin for the .model

I just don't have the game or the files. what was for that and wrote.  

I don't understand why to split file. 
zardalu wrote: ↑Fri Jun 10, 2022 4:40 am
Here are some static mesh examples:

for *.mesh (only mesh, uvs does not have yet.)

edit

Amazing!  Mesh load works perfectly for both skeletal and static mesh.

I see you got UVs working for the diablo model
## Post #16
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-09T22:40:25+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from zardalu ↑Fri Jun 10, 2022 6:30 am at Fri Jun 10, 2022 6:30 am
>
> 
I see you got UVs working for the diablo model
forgot to upload a new archive, update in the previous post.

```
Q4H_T2H(_T2H) - q? 4 half _ texture 2 half _ (texture 2 half, not always ,second uv chanel)
W4B_I4B - weight 4 byte _ index 4 byte (None if static)
None - none

```
## Post #17
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-06-09T23:33:01+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from Durik256 ↑Fri Jun 10, 2022 6:40 am at Fri Jun 10, 2022 6:40 am
>
> 
zardalu wrote: ↑Fri Jun 10, 2022 6:30 am
I see you got UVs working for the diablo model 

forgot to upload a new archive, update in the previous post.
Code: Select allP3F - point 3 float
Q4H_T2H(_T2H) - q? 4 half _ texture 2 half _ (texture 2 half, not always ,second uv chanel)
W4B_I4B - weight 4 byte _ index 4 byte (None if static)
None - none

PERFECT!!!!!!!!         Works great, amazing job, thank you Durik256
## Post #18
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2022-06-18T14:32:45+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from dolan1995 ↑Fri Jun 10, 2022 3:10 am at Fri Jun 10, 2022 3:10 am
>
> 
zardalu wrote: ↑Fri Jun 10, 2022 2:12 am
Durik256 wrote: ↑Thu Jun 09, 2022 5:21 pm

I still do not understand whether it was possible to open the models.  
took a quick look at the models and made a plugin.
(only mesh, maybe i'll finish it later)



Thanks for this!

Which version of the .model files does your plugin work with?  

I followed Spiritovod's advice and was able to use the fixed mpk script to extract the files from the PC version, and then used DIDT to rename them.

I now have a PC version of extracted files (29.2GB), as well as an IOS and Android version (around 6GB each).

But I am unable to see the models of either version with your script:  Just says: "File could not be previewed".


I encountered the same problem at first, and I think Noesis defaulted to using the GR2 plugin so it couldn't view the files. You have to remove the GR2 plugin because it's conflicting with each other's targeted ".model" format.
I also have the issue "File could not be previewed", but I don't have GR2 plugin in Noesis.
Also I am using the .mesh plugin for Diablo Immortal.
The mesh come from DIDT android beta version (it doesn't have an option to download the retail current version).
## Post #19
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-18T20:51:20+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from okami29 ↑Sat Jun 18, 2022 10:32 pm at Sat Jun 18, 2022 10:32 pm
>
> 
The mesh come from DIDT android beta version

post a sample
(dont quote all post)
## Post #20
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2022-06-19T03:02:50+00:00
- Post Title: Re: Diablo Immortal models extracting

Here it is :
[https://mega.nz/file/Btk3kZzA#fiS1uQISy ... Vr-Zy1Riok](https://mega.nz/file/Btk3kZzA#fiS1uQISynafqFRztmU0r4JMY4wHBHQSQVr-Zy1Riok)

EDIT : ok it works with the data from the PC game, I was using the mesh from the beta android version, I think it's the reason.
## Post #21
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2022-06-20T01:59:18+00:00
- Post Title: Re: Diablo Immortal models extracting

These files are still compressed with LZ4.  You can tell by the 'ZZZ4' id in the header.  If they come from DIDT, you need to do one more step and decompress them.
## Post #22
- Username: FantasticalPanda
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 27, 2019 6:27 am
- Post datetime: 2022-08-08T10:50:24+00:00
- Post Title: Re: Diablo Immortal models extracting

I don't suppose there's a Blender-friendly way of importing these models?

I don't have access to 3Ds Max ^^'

Edit 1:
Would use the Noesis plugin, but as of today my Neosis just crashes on startup, even did a fresh install of it
## Post #23
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-08-08T13:12:48+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from FantasticalPanda ↑Mon Aug 08, 2022 6:50 pm at Mon Aug 08, 2022 6:50 pm
>
> 
Would use the Noesis plugin, but as of today my Neosis just crashes on startup, even did a fresh install of it
strange
i made python script *.mesh to *.obj (with out Noesis) >> (with out 2UVs chanel)
just drop file on script.
(just don't say you don't have a python)


 MeshToOBJ.zip
(959 Bytes) Downloaded 60 times



UPDATE (click up arrow)

> Reply from Durik256 ↑Fri Jun 10, 2022 4:53 am at Fri Jun 10, 2022 4:53 am
>
> 
MeshToOBJ.exe
## Post #24
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-08-08T19:56:41+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from FantasticalPanda ↑Mon Aug 08, 2022 6:50 pm at Mon Aug 08, 2022 6:50 pm
>
> 
I don't suppose there's a Blender-friendly way of importing these models?
i made windows form for convert *.mesh to *.obj.
Here I have done attribute parsing. now opens all models correctly.
python plugin opened some models incorrectly because the first buffer did not always contain only vertices (P3F) for example (P3F_N4B_T2F)

DragAndDrop file on first textBox for convert one file (or select file "..." -button)
click checkBox "all in Folder" and DragAndDrop file or folder for convert many files (or select folder "..." -button)
click checkBox "subdirectories" for convert all file in folder and subFolder.
click checkBox "show message" what would on or off show all message(info, error)


 MeshToOBJ.zip
(7.78 KiB) Downloaded 84 times



UPDATE (click up arrow)

> Reply from Durik256 ↑Fri Jun 10, 2022 4:53 am at Fri Jun 10, 2022 4:53 am
>
> 
MeshToOBJ.exe
## Post #25
- Username: FantasticalPanda
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 27, 2019 6:27 am
- Post datetime: 2022-08-09T12:00:44+00:00
- Post Title: Re: Diablo Immortal models extracting

Thank you so much! ^^

It's a shame it won't keep the original weight painting/skeleton but it just means I'll have to rig it myself
## Post #26
- Username: isrtc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 01, 2022 6:35 am
- Post datetime: 2022-12-02T16:46:43+00:00
- Post Title: Re: Diablo Immortal models extracting

Hello zandalù, how can I contact you by other means?
## Post #27
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2023-02-23T20:58:39+00:00
- Post Title: Re: Diablo Immortal models extracting

I m sorry but I m lost. If someone can help me go to be nice.

I download the game from mobile android not from DIDT. I exported mpk with the script. But how I use DIDT to rename them. Or that work only if I download  directly from DIDT?
## Post #28
- Username: werwerwerwewww
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 28, 2023 1:43 pm
- Post datetime: 2023-05-29T20:27:37+00:00
- Post Title: Re: Diablo Immortal models extracting

Hi guys, I really don’t understand what version of the game and how to get models for import into 3dmax, plugins for max didn’t work, mesh to obj doesn’t work. I downloaded the beta for android via DIDT, and at most I was able to convert all the textures, but there is no model.
Maybe I need to dig in a PC game? What tools?
## Post #29
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2023-06-02T14:36:52+00:00
- Post Title: Re: Diablo Immortal models extracting

I have been getting a lot of questions about Diablo Immortal models. I am not really the person to ask but I will do my best because it keeps coming up.

First, I used the PC version. I have no idea if/how the other works. 

I extracted the files and textures using DIDT, following spiritovod's instructions and scripts [HERE](https://zenhax.com/viewtopic.php?f=9&t=16089&p=71884#p71884).
I will copy the relevant part of those instructions here because it seems that zenhax might be on its way out:
"....create a "Data_BetaROW_Android" folder in the DIDT tool's folder, moving extracted files there, then select respective options in the tool (beta + android) and start renaming at extra tab. Though due to minor differences in PC version, tool can crash at some point."  It didn't crash for me.

I then used Durik256's tool from [HERE](https://forum.xentax.com/viewtopic.php?p=186382#p186382) and a batch file to convert the meshes. 
I also used TaylorMouse's [tool](https://github.com/TaylorMouse/MaxScripts/tree/master/GriffonStudios/Diablo) for some larger models because it supports multiple model parts. (Use GriffonStudios_DiabloImmortal_ImportModel.ms. I use 3DS max 2013)

I then attached textures to models using batch scripts and [THESE](https://zenhax.com/viewtopic.php?f=5&t=16452&start=20#p72267) instructions.

Using the above I was able to get most or all of the models out of the game. It was not a straightforward process, and I don't think I'll be able to create an easy step-by-step guide because I kept running into walls and had to create many fixes with sloppy custom batch files, which is my only limited skill. None of the skeletal meshes are rigged. I was able to match the textures to most of the models, but many had to be done manually.
[Image2.jpg](https://xentaxbackup.github.io/file/23872_Image2.jpg)
## Post #30
- Username: NotSoMLGAlli
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 06, 2015 12:14 pm
- Post datetime: 2023-06-06T15:15:57+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from zardalu ↑Fri Jun 02, 2023 10:36 pm at Fri Jun 02, 2023 10:36 pm
>
> 
I have been getting a lot of questions about Diablo Immortal models. I am not really the person to ask but I will do my best because it keeps coming up.

First, I used the PC version. I have no idea if/how the other works. 

I extracted the files and textures using DIDT, following spiritovod's instructions and scripts HERE.
I will copy the relevant part of those instructions here because it seems that zenhax might be on its way out:
"....create a "Data_BetaROW_Android" folder in the DIDT tool's folder, moving extracted files there, then select respective options in the tool (beta + android) and start renaming at extra tab. Though due to minor differences in PC version, tool can crash at some point."  It didn't crash for me.

I then used Durik256's tool from HERE and a batch file to convert the meshes. 
I also used TaylorMouse's tool for some larger models because it supports multiple model parts. (Use GriffonStudios_DiabloImmortal_ImportModel.ms. I use 3DS max 2013)

I then attached textures to models using batch scripts and THESE instructions.

Using the above I was able to get most or all of the models out of the game. It was not a straightforward process, and I don't think I'll be able to create an easy step-by-step guide because I kept running into walls and had to create many fixes with sloppy custom batch files, which is my only limited skill. None of the skeletal meshes are rigged. I was able to match the textures to most of the models, but many had to be done manually.

Thank you so much for explaining your process with links! I've been wanting to to take models from but the best way I was able to get them was through wow.head but not having skeletons on the meshes was kind of too much for me ;c. Hopefully there's a way to extract with skels soon. Maybe with Diablo 4's release this'll get more attention and people will help ease the process.
## Post #31
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2023-06-09T00:11:55+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from NotSoMLGAlli ↑Tue Jun 06, 2023 11:15 pm at Tue Jun 06, 2023 11:15 pm
>
> 

Thank you so much for explaining your process with links! I've been wanting to to take models from but the best way I was able to get them was through wow.head but not having skeletons on the meshes was kind of too much for me ;c. Hopefully there's a way to extract with skels soon. Maybe with Diablo 4's release this'll get more attention and people will help ease the process.

Check out TaylorMouse's [Github](https://github.com/TaylorMouse/MaxScripts/tree/master/GriffonStudios/Diablo).  

In there the following scripts are listed:

GriffonStudios_DiabloIII_Dialog.ms Diablo immortal support added
GriffonStudios_DiabloIII_ImportAnimation.ms Diablo immortal support added
GriffonStudios_DiabloIII_ImportModel.ms Diablo immortal support added
GriffonStudios_DiabloImmortal_ImportModel.ms

I did not test the animation script because my interest lies in static meshes, but animations may be working.  Let us know if you try it,

Cheers
## Post #32
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2023-06-09T17:34:09+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from zardalu ↑Fri Jun 09, 2023 8:11 am at Fri Jun 09, 2023 8:11 am
>
> 
Check out TaylorMouse's Github.  

In there the following scripts are listed:

GriffonStudios_DiabloIII_Dialog.ms Diablo immortal support added
GriffonStudios_DiabloIII_ImportAnimation.ms Diablo immortal support added
GriffonStudios_DiabloIII_ImportModel.ms Diablo immortal support added
GriffonStudios_DiabloImmortal_ImportModel.ms

I did not test the animation script because my interest lies in static meshes, but animations may be working.  Let us know if you try it,

Cheers

Got curious and gave it a try but i'm getting lots of errors on startup... also the D3 scripts refuse to load or give errors despite everything being in there (?) ... anyway, looking at the script at github makes me doubt it'd work with Diablo Immortal, since it reads

> /*
>
> 	Import Diablo III Animation
>
> 	Written by Taylor Mouse (c) 08.2014
>
> 	Added config possibilities
>
> 	Added Reaper Of Souls Animations
>
> */

while DI one is 2022 (also, it works as standalone), i guess if he had updated it he'd have written so?
OFC if someone manage to make it works and manage to test it it'd be more than welcome to let us know as there're no option for DI animations outside wowhead
## Post #33
- Username: NotSoMLGAlli
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 06, 2015 12:14 pm
- Post datetime: 2023-06-09T20:20:56+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from zardalu ↑Fri Jun 09, 2023 8:11 am at Fri Jun 09, 2023 8:11 am
>
> 
NotSoMLGAlli wrote: ↑Tue Jun 06, 2023 11:15 pm

Thank you so much for explaining your process with links! I've been wanting to to take models from but the best way I was able to get them was through wow.head but not having skeletons on the meshes was kind of too much for me ;c. Hopefully there's a way to extract with skels soon. Maybe with Diablo 4's release this'll get more attention and people will help ease the process.


Check out TaylorMouse's Github.  

In there the following scripts are listed:

GriffonStudios_DiabloIII_Dialog.ms Diablo immortal support added
GriffonStudios_DiabloIII_ImportAnimation.ms Diablo immortal support added
GriffonStudios_DiabloIII_ImportModel.ms Diablo immortal support added
GriffonStudios_DiabloImmortal_ImportModel.ms

I did not test the animation script because my interest lies in static meshes, but animations may be working.  Let us know if you try it,

Cheers

Was excited to try this, didn't read that I could just download it from the tool lmao downloaded nox/bluestacks and restarted my pc like 30 times then gave up just to find out DIDT does it all. 

Sadly for some reason the second I get to step 2 the extracting part it doesn't work, step 1 is stuck on "done". I've retried 3 times now, any ideas? It looks like most of it's extracted anyways but when I drag any of the .mesh's I have (specifically looking for armor) into the .meshtoobj converter I get an error.
## Post #34
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-16T08:12:12+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from Durik256 ↑Tue Aug 09, 2022 3:56 am at Tue Aug 09, 2022 3:56 am
>
> 
i made windows form for convert *.mesh to *.obj.
Here I have done attribute parsing. now opens all models correctly.
python plugin opened some models incorrectly because the first buffer did not always contain only vertices (P3F) for example (P3F_N4B_T2F)
Hi Durik! I was checking some files and have some erros (uv's, deformed meshes and others cannot be converted) would be awesome if you can give support for this meshes too, please!!  
[https://www.mediafire.com/file/e3ks0ybv ... 23.7z/file](https://www.mediafire.com/file/e3ks0ybvdi5m5co/mesh_samples_06-16-2023.7z/file)
## Post #35
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-17T12:29:41+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from moonpaladin ↑Fri Jun 16, 2023 4:12 pm at Fri Jun 16, 2023 4:12 pm
>
> 
Hi Durik

I don't have free time right now, I'll take a look at it later  

UPDATE (click up arrow)

> Reply from Durik256 ↑Fri Jun 10, 2022 4:53 am at Fri Jun 10, 2022 4:53 am
>
> 
MeshToOBJ.exe
## Post #36
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-10-20T12:41:22+00:00
- Post Title: Re: Diablo Immortal models extracting

> Reply from okami29 ↑Sun Jun 19, 2022 11:02 am at Sun Jun 19, 2022 11:02 am
>
> 
Here it is :

uncompress ZZZ4 files from Diablo Immortal 

```
f - uncompress one file/ or drop on exe.
d - uncompress all files in folder.
r - uncompress recursive all files in folder/subfolders.

```


link on gitHub:: [DI_ZZZ4.exe](https://github.com/Durik256/Noesis-Plugins/blob/master/DI_ZZZ4.exe)
