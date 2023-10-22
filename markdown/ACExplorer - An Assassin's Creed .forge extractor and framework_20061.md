## Post #1
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-04-20T09:55:20+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

ACExplorer V1.0.2
ACExplorer is an exporter and framework for accessing data from the Assassin's Creed forge file format. Written in Python 3.7.

If you would like to support me and this project you can donate via this link
https://www.paypal.me/gentlegiantJGC

Features:

Export base meshes to OBJ and COLLADA formats (automatically finds and exports textures).
Export textures to DDS format.
Export the assembled meshes as they appear in the world (see the Notre Dame example below)
Export the assembled low resolution mesh files used far from the camera.
A powerful user extendable python plugin system for reading and exporting the data to any required format.

Source code: https://github.com/gentlegiantJGC/ACExplorer
Executable release builds: https://github.com/gentlegiantJGC/ACExplorer/releases

Currently only Assassin's Creed Unity is supported but adding other games is almost as easy as adding a reader for the other file formats.

The user interface: (custom themes can be added)


The Notre Dame. An example of what the program can do. It takes the individual models and pieces them together.


The plugin system. Right click an entry to access plugins for that entry (they vary by data type).

Plugins with a right click symbol next to them have further options hidden under a right click. Left clicking will run the plugin with the last/default options
## Post #2
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-04-21T01:09:44+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

Damn, this is really cool!   
Thanks for sharing with us!
## Post #3
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-04-22T09:11:31+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

ACExplorer V1.0.1 is now available

 Fixed numerical values in list boxes not rendering
 Added icons to represent what the tree view entry represents
 Fixed a mesh reading issue (if you find any malformed meshes please open an issue with the information)
https://github.com/gentlegiantJGC/ACExplorer/releases
## Post #4
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-04-22T09:31:29+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

Question: 
> How to find a model of Notre Dame from Assassin's Creed Unity?

Answer: The Notre Dame is stored as hundreds (perhaps thousands) of individual 3D models scattered throughout the forge file. The DataBlock files specify how these models are pieced together in the world. The world is sliced up into a grid pattern and each DataBlock holds the data for one of these blocks. You will need to find each DataBlock (see below) used in that area and export each chunk individually to OBJ format and then load them all at the same time (which is what I did for that photo).

I want to add another plugin to make finding these chunks of data easier but that is the easiest option for now. Also note that file reading is not perfect so some models are skipped but it will get you what you see in the photo.

Here is a list of the names of the DataBlocks that cover the Notre Dame:

Cell07763_DataBlock
Cell07764_DataBlock
Cell07888_DataBlock
Cell07889_DataBlock
Cell07890_DataBlock
Cell07891_DataBlock
Cell07892_DataBlock
Cell08016_DataBlock
Cell08017_DataBlock
Cell08018_DataBlock
Cell08019_DataBlock
Cell08020_DataBlock
Cell08144_DataBlock
Cell08145_DataBlock
Cell08146_DataBlock
Cell08147_DataBlock
Cell08272_DataBlock
Cell08273_DataBlock
Cell09005_DataBlock
Cell09018_DataBlock
## Post #5
- Username: Jaapyse
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 01, 2019 6:20 am
- Post datetime: 2019-04-30T22:28:00+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

Hi all,

Amazing project! Very impressive.
What is worth a mention is the following: When opening ACExplorer you can search for the mentioned DataBlocks. You will get two items for each Cell[number] search. TAKE THE FIRST ONE. It took me 5 hours to figure it out.
I had taken the second ones from the list, that's just my brain.  

By the way gentle, is there any chance you could share the file you used for the screenshots directly? Compiling it all into one file is quite the hassle, and you already have it, so I thought I'd just ask.   

Thanks again for sharing this awesome project!
- Jaapyse
## Post #6
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-05-01T08:52:08+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from Jaapyse ↑Wed May 01, 2019 6:28 am at Wed May 01, 2019 6:28 am
>
> 
Hi all,

Amazing project! Very impressive.
What is worth a mention is the following: When opening ACExplorer you can search for the mentioned DataBlocks. You will get two items for each Cell[number] search. TAKE THE FIRST ONE. It took me 5 hours to figure it out.
I had taken the second ones from the list, that's just my brain.  

By the way gentle, is there any chance you could share the file you used for the screenshots directly? Compiling it all into one file is quite the hassle, and you already have it, so I thought I'd just ask.   

Thanks again for sharing this awesome project!
- Jaapyse

Thank you. Yeh there are sometimes two datafiles with the same block name but contain different data (and have a different numerical id which isn't currently show to the user).
The order of them can vary but like you say it is generally consistent if it is before or after. The easy way to tell is to expaand the entry and see which entry has more data. I would like to at some point add a tool to make extracting the data easier and in one file rather than lots.

For the screenshot I opened up all the files at the same time so that they loaded over each other so it isn't actually one file. Added to this the files are over 3GB and it isn't my property so I can't legally distribute it.
## Post #7
- Username: Jaapyse
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 01, 2019 6:20 am
- Post datetime: 2019-05-01T18:25:38+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

Thanks for your reply, I understand that you can't share it.
I'll keep at it myself!

- Jaapyse
## Post #8
- Username: chavochavo79
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 28, 2019 5:25 am
- Post datetime: 2019-05-01T23:35:25+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

Very nice. Any chance of getting an AC:Black Flag version?
## Post #9
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-05-25T23:54:18+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

Thank you for this amazing work for Unity game, and world coordinates for map geometry, much appreciated.

I simply cannot export to COLLADA, since OBJ has major issues while importing in 3dsMax 2018/2020, complains about vertex coordinate too big adjust object-scale on almost all of them, and NOTHING gets imported.
And a good majority of geometry is in the middle of the scene as vertices in 3dsMax 2012, very odd.
Every time I right click like in image below and select Export DataBlock nothing else appears on the screen to select COLLADA, I just see the OBJ/MTL pair exported with the relevant textures, noting else.

I really want to give this a try and test it out, but I am obviously missing something to test COLLADA.

> Reply from gentlegiantJGC ↑Sat Apr 20, 2019 5:55 pm at Sat Apr 20, 2019 5:55 pm
>
> 

Export base meshes to OBJ and COLLADA formats (automatically finds and exports textures).
So basically I see this option.

BUT, I do NOT get this option, what so ever, what am i doing wrong?

Also, to do multiple CellBlocks selection/extraction would be very nice, one by one is super tedious
## Post #10
- Username: Decovulous
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 26, 2019 1:38 pm
- Post datetime: 2019-05-26T05:40:38+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

Hey this is awesome work you're doing! Does this also detect the Dead Kings DLC?? I'm trying to find the model for the Guillotine Gun but I'm having trouble.
## Post #11
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-05-26T08:40:55+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from mono24 ↑Sun May 26, 2019 7:54 am at Sun May 26, 2019 7:54 am
>
> 
and select Export DataBlock nothing else appears

You are right clicking on the item in the tree view to get the plugin select dialogue. It sounds like you are then left clicking the "Export DataBlock" plugin which runs it using the last used/default inputs. To open the further dialogue boxes you need to right click on the "Export DataBlock" function. This is signified by right click mouse icon to the left.

This being said it might not fix your issue. It sounds like 3dsMax does not like large vertices. This program exports the models to the same coordinates they are in the world which are rather large. If there is an option in the 3dsMax obj import window to scale the model then try that. The model works fine when imported into Blender.

Edit: I would like to do a multi data block export at some point but I still need to reverse engineer the file that points to them
## Post #12
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-05-26T08:48:59+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from Decovulous ↑Sun May 26, 2019 1:40 pm at Sun May 26, 2019 1:40 pm
>
> 
Hey this is awesome work you're doing! Does this also detect the Dead Kings DLC?? I'm trying to find the model for the Guillotine Gun but I'm having trouble.

It should load all forge files that are in the same directory as long as they are the same format. If you are trying to find a specific object using the search feature then it is worth pointing out that it is currently case sensitive (I need to improve it but haven't gotten around to it). Try searching for "uillotine" without the g and it will capture entries containing "guillotine" and "Guillotine".

To export things property (including textures) from things outside of the base game you will need to either manually find the texture files or right click on the forge file and select the decompress forge file plugin.
## Post #13
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-05-26T17:47:07+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from gentlegiantJGC ↑Sun May 26, 2019 4:40 pm at Sun May 26, 2019 4:40 pm
>
> It sounds like you are then left clicking the "Export DataBlock" plugin which runs it using the last used/default inputs. To open the further dialogue boxes you need to right click on the "Export DataBlock" function. This is signified by right click mouse icon to the left.
Yeah, that was one main step I was missing, thanks for that.

> Reply from gentlegiantJGC ↑Sun May 26, 2019 4:40 pm at Sun May 26, 2019 4:40 pm
>
> This being said it might not fix your issue. It sounds like 3dsMax does not like large vertices. This program exports the models to the same coordinates they are in the world which are rather large. If there is an option in the 3dsMax obj import window to scale the model then try that.
Unfortunately there is nothing that I will try to make it import to 3dsMax 2018/2020 if I change the scale even up to 0.01, it will still throw same error.

Also will look forward to use the COLLADA option to be implemented for export, or maybe even FBX? since it only does OBJ/MTL at the moment, unless that is easy enough to pick and I don't see it? 



obj.jpg (21.64 KiB) Viewed 1179 times


And looking forward as well for more improvements to the tool if your still working on it, its really amazing so far.
## Post #14
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-05-26T19:08:48+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

Carefully loading the mentioned blocks in your post still doesn't show what you have in your screenshot, no matter what, even if I follow the pattern blocks, still same result every time, literally.



001.JPG (136.9 KiB) Viewed 1177 times


Something must NOT get exported/imported/missing, that is Blender 2.79 in screenshot btw.
## Post #15
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-05-26T20:12:03+00:00
- Post Title: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from mono24 ↑Mon May 27, 2019 1:47 am at Mon May 27, 2019 1:47 am
>
> 
Also will look forward to use the COLLADA option to be implemented for export, or maybe even FBX? since it only does OBJ/MTL at the moment
I don't know what the issue is with 3ds Max as I don't have it to play around with.

I may not have implemented COLLADA for that plugin. I think it is only set up for individual models currently. If you know anything about python you could add it. The COLLADA handler has been written so it should just be a case of hooking it up to the plugin.

> Reply from mono24 ↑Mon May 27, 2019 3:08 am at Mon May 27, 2019 3:08 am
>
> 
Something must NOT get exported/imported/missing

You will note that a number of the data blocks with data in them appear twice in the list. Generally one contains all the data and another one contains some of the data (I still need to work out why this is the case). You will need to play around and find the ones with all the data. You have probably exported some of the ones with only part
## Post #16
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-05-26T22:55:28+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from gentlegiantJGC ↑Mon May 27, 2019 4:12 am at Mon May 27, 2019 4:12 am
>
> If you know anything about python you could add it. The COLLADA handler has been written so it should just be a case of hooking it up to the plugin.
Nope, not a clue about reversing/python and stuff alike at that level 

> Reply from gentlegiantJGC ↑Mon May 27, 2019 4:12 am at Mon May 27, 2019 4:12 am
>
> You will note that a number of the data blocks with data in them appear twice in the list. Generally one contains all the data and another one contains some of the data (I still need to work out why this is the case). You will need to play around and find the ones with all the data. You have probably exported some of the ones with only part.
Ah, alright, because in beginning I was confused as to why they seem different in size, the files simply get overwritten, so all I have to try next and test, first row in one location and second row in another location to then compare and see what is going on.

PS: thank you for your responses, much appreciated.
## Post #17
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-05-27T04:31:29+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Ok, more tests, they all give same result in every software I have tried so far.
Such as, 3dsMax versions between 2009-2020, Blender, UU3D, Daz3D, Poser even Noesis.
Something must go wrong with initial export from ACExplorer, because if we take as example Cell08018_DataBlock 2nd row obj size 317MB.
In the center of the scene there are 40909verts/107601edges/35867polys with the following messed up elements:

```
FRV_LM_NotreDame_BackGroundBottom_01_LOD0_0
FRV_LM_NotreDame_BackGroundBottom_01_LOD0_4
FRV_LM_NotreDame_BackGroundBottom_01_LOD0_4
FRV_LM_NotreDame_BackGroundBottom_01_LOD0_2
FRV_LM_NotreDame_BackGroundBottom_01_LOD0_6
FRV_LM_SEW_WL_6x_14_LOD0_1
FRV_LM_SEW_WL_6x_06_LOD0_2
FRV_LM_SEW_WL_6x_03_LOD0_2
FRV_LM_SEW_WL_6x_03_LOD0_6
FRV_LM_SEW_WL_6x_03_LOD0_12
FRV_LM_SEW_WL_6x_03_LOD0_16
FRV_LM_SEW_WL_6x_03_LOD0_22
FRV_LM_SEW_WL_6x_03_LOD0_26
FRV_LM_SEW_WL_6x_03_LOD0_32
FRV_LM_SEW_WL_6x_15_LOD0_2
FRV_LM_NotreDame_BackGroundBottom_01_LOD0_0
FRV_LM_SEW_WL_1x_01_LOD0_0
FRV_LM_SEW_WL_1x_01_LOD0_2
FRV_LM_SEW_WL_90_LOD0_4
FRV_LM_SEW_WL_1x_01_LOD0_5
LargeMesh_IC_NotreDameCemetary_01_LOD1_Chunk_0018_0
FRV_LM_SEW_WL_6x_06_LOD0_0
FRV_LM_SEW_WL_6x_03_LOD0_0
FRV_LM_SEW_WL_6x_03_LOD0_4
FRV_LM_SEW_WL_6x_03_LOD0_10
FRV_LM_SEW_WL_6x_03_LOD0_14
FRV_LM_SEW_WL_6x_03_LOD0_20
FRV_LM_SEW_WL_6x_03_LOD0_24
FRV_LM_SEW_WL_6x_03_LOD0_30
FRV_LM_SEW_WL_6x_15_LOD0_0
FRV_LM_SEW_WL_1x_01_LOD0_0
FRV_LM_SEW_WL_1x_01_LOD0_2
FRV_LM_SEW_WL_1x_01_LOD0_5
FRV_LM_SEW_WL_1x_01_LOD0_7
FRV_LM_SEW_WL_6x_14_LOD0_1
FRV_LM_SEW_WL_6x_06_LOD0_0
FRV_LM_SEW_WL_6x_03_LOD0_0
FRV_LM_SEW_WL_6x_03_LOD0_6
FRV_LM_SEW_WL_6x_03_LOD0_10
FRV_LM_SEW_WL_6x_03_LOD0_16
FRV_LM_SEW_WL_6x_03_LOD0_20
FRV_LM_SEW_WL_6x_03_LOD0_26
FRV_LM_SEW_WL_6x_03_LOD0_30
FRV_LM_SEW_WL_6x_15_LOD0_0
FRV_LM_SEW_WL_6x_14_LOD0_3
FRV_LM_SEW_WL_6x_06_LOD0_2
FRV_LM_SEW_WL_6x_03_LOD0_2
FRV_LM_SEW_WL_6x_03_LOD0_8
FRV_LM_SEW_WL_6x_03_LOD0_12
FRV_LM_SEW_WL_6x_03_LOD0_18
FRV_LM_SEW_WL_6x_03_LOD0_22
FRV_LM_SEW_WL_6x_03_LOD0_28
FRV_LM_SEW_WL_6x_03_LOD0_32
FRV_LM_SEW_WL_6x_15_LOD0_2
FRV_LM_SEW_WL_6x_14_LOD0_3
FRV_LM_SEW_WL_6x_06_LOD0_4
FRV_LM_SEW_WL_6x_03_LOD0_4
FRV_LM_SEW_WL_6x_03_LOD0_8
FRV_LM_SEW_WL_6x_03_LOD0_14
FRV_LM_SEW_WL_6x_03_LOD0_18
FRV_LM_SEW_WL_6x_03_LOD0_24
FRV_LM_SEW_WL_6x_03_LOD0_28
FRV_LM_SEW_WL_6x_03_LOD0_34
FRV_LM_SEW_WL_6x_15_LOD0_4
FRV_LM_SEW_WL_6x_06_LOD0_4
FRV_LM_Crypte_AR_01_LOD0_0
FRV_LM_Crypte_AR_01_LOD0_2
FRV_LM_Crypte_AR_01_LOD0_4
FRV_LM_Crypte_AR_01_LOD0_6
FRV_LM_Crypte_AR_01_LOD0_8
FRV_LM_Crypte_AR_01_LOD0_10
FRV_LM_Crypte_AR_01_LOD0_12
FRV_LM_Crypte_AR_01_LOD0_14
FRV_LM_Crypte_AR_01_LOD0_16
FRV_LM_Crypte_WL_01_LOD0_1
FRV_LM_Crypte_WL_01_LOD0_3
FRV_LM_Crypte_WL_01_LOD0_5
FRV_LM_Crypte_WL_01_LOD0_7
FRV_LM_Crypte_WL_01_LOD0_9
FRV_LM_Crypte_AR_01_LOD0_0
FRV_LM_Crypte_AR_01_LOD0_2
FRV_LM_Crypte_AR_01_LOD0_4
FRV_LM_Crypte_AR_01_LOD0_6
FRV_LM_Crypte_AR_01_LOD0_8
FRV_LM_Crypte_AR_01_LOD0_10
FRV_LM_Crypte_AR_01_LOD0_12
FRV_LM_Crypte_AR_01_LOD0_14
FRV_LM_Crypte_AR_01_LOD0_16
```

while the rest of the geometry 3298881verts/8525625edges/2841875polys is nicely placed where belongs in the 3d map with its coordinates.
Please do check again and maybe it can somehow be fixed, if possible 

Also are normals supported? some meshes seem highly broken/unwelded.

PS: Was thinking maybe support for individual elements to be exported instead of the whole CellBlock might be better? I know that means thousands up on thousands of exported geometry elements, but its easy to import in a batch only desired ones, what do you think?
## Post #18
- Username: potatosenpai
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 27, 2019 10:05 am
- Post datetime: 2019-06-27T04:00:29+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Hi, I cant get it to work in blender although I import all obj
## Post #19
- Username: PlatZ
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 07, 2017 12:46 am
- Post datetime: 2019-06-29T18:10:32+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Hi ! When running ACExplorer.exe, programm don't open and close immediatly. I tried multiple time and it don't work.
## Post #20
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-07-02T12:15:18+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from PlatZ ↑Sun Jun 30, 2019 2:10 am at Sun Jun 30, 2019 2:10 am
>
> 
Hi ! When running ACExplorer.exe, programm don't open and close immediatly. I tried multiple time and it don't work.

When extracting the zip file you need to extract every file together not just the exe file. Most likely you have just taken out the exe file. If you have done that there may be more information in the acexplorer.log file
## Post #21
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2019-07-02T12:21:30+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

ACExplorer V1.0.2 is now available
More work on the connection files - ACExplorer can now export most of the models pieced together for ACU
Project restructuring to makes plugins more powerful and clean up the project a little
Made pyUbiForge a true library that is imported and used correctly (this also means it can be used as a library outside the program)
https://github.com/gentlegiantJGC/ACExplorer/releases
## Post #22
- Username: Mathew1
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 6:30 pm
- Post datetime: 2019-07-26T23:53:38+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Thank you for this great exporter. I looked at almost all the Data Blocks and this is what I noticed:
Invalides, Villa Arno, Bastilia, Temple, Notre Dame - blocks are exported entirely with external walls and internal walls
Pantheon, Luxembourg palace, Sante-Chapelle, Hotel de Ville, Grand Chatelet, Halle aux Bles, Palais Royale, Louve (Tuileries), Versailles palace - blocks are exported only with external walls. The internal walls are lost.
As for Saint Denis, Abbey has the opposite situation - internal walls are exported, external walls are lost.  Basilica not exported at all, only empty land.
I hope this information will be useful.
## Post #23
- Username: LordMustang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 09, 2019 2:43 am
- Post datetime: 2019-09-19T11:03:13+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Is there a way to identify which datablock to export for specific buildings? Or does this have to be done by trial and error?
## Post #24
- Username: derinhalil2015
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 11, 2019 4:23 am
- Post datetime: 2019-10-07T18:59:05+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

It says in the first post that it's very easy to add support for new games. How could I, an end user, help with that? I own all the AC games except Origins, Odyssey or the Chronicles games, and I really do want to help.

EDIT: I know some Python, if that helps.
## Post #25
- Username: noire90
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 13, 2020 7:49 am
- Post datetime: 2020-01-12T23:55:29+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

I really would like to use your program for Odyssey or Origin. There are some possibilities for you to made this real before long?
## Post #26
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2020-01-20T13:47:44+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from noire90 ↑Mon Jan 13, 2020 7:55 am at Mon Jan 13, 2020 7:55 am
>
> 
I really would like to use your program for Odyssey or Origin. There are some possibilities for you to made this real before long?

Blacksmith tool for Odyssey
## Post #27
- Username: noire90
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 13, 2020 7:49 am
- Post datetime: 2020-01-21T16:23:01+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from Damoclès ↑Mon Jan 20, 2020 9:47 pm at Mon Jan 20, 2020 9:47 pm
>
> 
noire90 wrote: ↑Mon Jan 13, 2020 7:55 am
I really would like to use your program for Odyssey or Origin. There are some possibilities for you to made this real before long?


Blacksmith tool for Odyssey

Thanks for your answear. I know Blacksmith, it is a nice tool but it can't extract datablocks like ACexplorer.   ... or not ?
## Post #28
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-02-09T12:29:17+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Thank you for the tool.
AC: Unity was my first AC game (and still remains the only one I started). With your tool I definitely start play it one day again and disassemble some blocks ^^
## Post #29
- Username: TheDarkslayer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 26, 2020 9:44 pm
- Post datetime: 2020-03-26T13:54:02+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Any ideas where I can find all Arno models?
Although I found some under the name of Arno, it was not everything, I do not know where to look for them, I did not find the hidden leaf either, if someone found something more than head and hands to advise please

Edit: this exporter is super cool
## Post #30
- Username: BananaeJoe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 05, 2020 6:15 pm
- Post datetime: 2020-05-05T10:18:31+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

This is great work by @gentlegiantJGC.

Can anyone give me a hint where to find the Paris Cathedral in all those forge files? I would like to browse it in blender, if possible. But those count of forge files is overwhelming   I got lost   

Cheers!
## Post #31
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-05-05T17:01:35+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from BananaeJoe ↑Tue May 05, 2020 6:18 pm at Tue May 05, 2020 6:18 pm
>
> Can anyone give me a hint where to find the Paris Cathedral in all those forge files?
Just type the Cell# blocks as instructed in the search bar, and it will find them for you, then export both blocks making sure to rename them after so they do not get overwritten, and then after your done, import each and one of them in your desired software, but be prepared for large files, and also, they will be incomplete, as the tool is not finished an doesn't support all types, unfortunately.
## Post #32
- Username: BananaeJoe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 05, 2020 6:15 pm
- Post datetime: 2020-05-05T18:44:00+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Thanks a lot! Seeing some progress here...
## Post #33
- Username: AESRYL
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 05, 2019 7:37 pm
- Post datetime: 2020-05-21T16:42:45+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Just wondering if anyone has found the files for the Assassins Hideout & can someone teach me how to work this tool
## Post #34
- Username: DragonRuines4
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 24, 2019 3:28 pm
- Post datetime: 2020-07-26T08:56:41+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

{}
## Post #35
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-07-26T22:46:12+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from DragonRuines4 ↑Sun Jul 26, 2020 4:56 pm at Sun Jul 26, 2020 4:56 pm
>
> 
Hello Everybody. I just checked to Cell04411_Datablcok in Paris.forge and just found 4 or 5 of them working... all of them were not containing anything.is this alright? I wanted to extract the whole map
Unfortunately this tool like many others about this engine, is unfinished, so what ever you extract, it will be incomplete, broken, missing parts etc etc etc etc etc, you will waste your time, so before continue, stop, cause I tried and wasted a looooooooot of time on it, its sad, because these maps are great.
## Post #36
- Username: Therapy77782
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 11, 2022 6:43 am
- Post datetime: 2022-04-10T22:48:49+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

I know this extractor is old but I was wondering if this ACexplorer can get scene from Assassins Creed Syndicate? My goal is to get Westminster palace and Westminster Bridge.


[https://youtu.be/-57bKMZQh18](https://youtu.be/-57bKMZQh18)



Thanks 
Kory
## Post #37
- Username: AsrielDewitt53
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 21, 2020 10:22 am
- Post datetime: 2022-04-14T10:48:02+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from gentlegiantJGC ↑Sat Apr 20, 2019 5:55 pm at Sat Apr 20, 2019 5:55 pm
>
> 

[*]Export the assembled meshes as they appear in the world (see the Notre Dame example below)

I know this project is discontinued a long time ago, but for god sake, SHOW US how to assmebled the meshes! Like... YOu just told us about the plugin system and that's it!

Do I like, Select multiple DataBlocks by selecting them and then right click, and right click again, and select export?

I... I freaking don't freaking get it. There's no multiple select, there's no check boxes, there's no FUCKING nothing, to tell you how to export assembled mesh.
## Post #38
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-04-14T14:37:26+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from AsrielDewitt53 ↑Thu Apr 14, 2022 6:48 pm at Thu Apr 14, 2022 6:48 pm
>
> …I know this project is discontinued a long time ago, but for god sake…
I can relate to your raging frustration more than I could explain here, but, there’s no need for foul language to get proper help/answers, what I recommend is this, even if it’s outdated here in the forum, join its discord to get it's more newer version.
[viewtopic.php?f=16&t=22864](https://forum.xentax.com/viewtopic.php?f=16&t=22864)
## Post #39
- Username: Yanting Yet
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 12, 2022 10:53 pm
- Post datetime: 2022-07-12T14:59:17+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

thank you,but I have some suggestion.
It will be more convenient if we can choose more data to export, because it is cumbersome to choose one by one.

All the normal maps we exported seem to be damaged, showing the appearance of mosaic. I hope they can be repaired.
## Post #40
- Username: Yanting Yet
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 12, 2022 10:53 pm
- Post datetime: 2022-07-13T05:25:31+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from Yanting Yet ↑Tue Jul 12, 2022 10:59 pm at Tue Jul 12, 2022 10:59 pm
>
> 
thank you,but I have some suggestion.
It will be more convenient if we can choose more data to export, because it is cumbersome to choose one by one.

All the normal maps we exported seem to be damaged, showing the appearance of mosaic. I hope they can be repaired.

I try to use the old version ACExplorer V1.0.1,it better than ACExplorer V1.0.2.
Its normal map is quite normal, but it is a little translucent due to the addition of an alpha channel. You have to use the XnView tool to convert it to BPM format, and then turn the B channel into white in PS, and then delete the alpha channel to return to normal. I hope to update the tool to fix these problems later. Although the steps are a little troublesome, it is indeed possible to successfully export the models and maps in the game and restore them in other 3D software. Finally, thank you for your efforts.
## Post #41
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-07-13T19:29:56+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from Yanting Yet ↑Wed Jul 13, 2022 1:25 pm at Wed Jul 13, 2022 1:25 pm
>
> ...it is indeed possible to successfully export the models and maps in the game and restore them in other 3D software. Finally...
umm: [viewtopic.php?f=16&t=22864](https://forum.xentax.com/viewtopic.php?f=16&t=22864)
On tool's discord you'll find a more recent version, more support and updates.
## Post #42
- Username: Hotcoco99999
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 06, 2022 7:49 am
- Post datetime: 2022-12-05T23:51:54+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

So I have been trying to extract models from AC games for a long time and I found this amazing tool, however, I have a few questions, firstly, does this work for any AC game or only AC Unity, and secondly, after trying to export a model my antivirus (norton) would shut down AC explorer, any idea on how to avoid this.
## Post #43
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-12-05T23:56:15+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

> Reply from Hotcoco99999 ↑Tue Dec 06, 2022 7:51 am at Tue Dec 06, 2022 7:51 am
>
> 
So I have been trying to extract models from AC games for a long time and I found this amazing tool, however, I have a few questions, firstly, does this work for any AC game or only AC Unity, and secondly, after trying to export a model my antivirus (norton) would shut down AC explorer, any idea on how to avoid this.
Avoid this tool it is entirely obsolete, you need this: [viewtopic.php?p=167856#p167856](https://forum.xentax.com/viewtopic.php?p=167856#p167856)
Join Discord to get latest version.
## Post #44
- Username: Hotcoco99999
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 06, 2022 7:49 am
- Post datetime: 2022-12-06T14:50:59+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

Hey, I have two problems, firstly, I was trying to export meshes from ac syndicate and when I tried that my anti-virus (norton) shut down the program, any way to solve this, and my other problem is that when I try to export files from other games, the script reads "exception: unsupported forge file format : "25""
Is there a way to solve this.
## Post #45
- Username: pepapoha
- Rank: n00b
- Number of posts: 16
- Joined date: Wed May 20, 2020 9:49 pm
- Post datetime: 2023-05-30T12:29:24+00:00
- Post Title: Re: ACExplorer - An Assassin's Creed .forge extractor and framework

when I select folder assasin creed origin error console why I dont open?
[https://gifyu.com/image/Suhgk](https://gifyu.com/image/Suhgk)
