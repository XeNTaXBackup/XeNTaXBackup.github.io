## Post #1
- Username: Zetsu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 02, 2017 12:35 am
- Post datetime: 2019-02-22T10:04:54+00:00
- Post Title: School of Dragons: Light Fury

Hi, would anyone know how to rip this model?
I've managed to extract the files for the game, but they don't include its model.
I believe I might be doing something wrong, but I'm unsure.
## Post #2
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-04-25T06:45:04+00:00
- Post Title: School of Dragons: Light Fury

I would love to help, but may I ask how did you go about extracting the models? AssetBundleExtractor doesn’t quite seem to find them in the asset bundles, unless I’m using the wrong tool/looking in the wrong place.
## Post #3
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-05-19T07:48:34+00:00
- Post Title: School of Dragons: Light Fury

Actually, I found her.


For future reference for OP and others who may stumble across this post. In order to extract files from School of Dragons, you must have:
 uTinyRipper 
A version of unity (version 2017+)
The Free FBX exporter plugin from the Unity Asset Store.

1. To find the extractable files, go to the AppData folder on your computer (it may be set to hidden)
2. Then navigate AppData>LocalLow>Unity>JumpStartSoD
3. Once in there scroll until you find files with dragon names (or anything else you want to extract) 
4. Go into the folders until you find a file called “-data”
5. Copy and paste “-data” into a folder outside of the AppData folder
6. Run “-data” through uTinyRipper
7. Take the exported asset file and drop it into Unity (download the FBX exporter as well)
8. the models you want will be in the “prefabs” folder
9. Drop one into the right hand panel and right click it and select “export to FBX”
10. Import your FBX into your 3D program of choice. 

IMPORTANT NOTE! 
The dragons/files that end up in the AppData folder seem to be random/loosely based on what you encounter within the game. (I have yet to figure it out). Just keep opening the game and play around, checking back in the AppData folder frequently to see what new files have ended up in there. 

Hope this helped!
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-06-01T02:16:24+00:00
- Post Title: School of Dragons: Light Fury

> Reply from Snapdragons ↑Sun May 19, 2019 3:48 pm at Sun May 19, 2019 3:48 pm
>
> 
Actually, I found her.

...
3. Once in there scroll until you find files with dragon names (or anything else you want to extract)
...
Very odd, I cant seem to find her anywhere, care to share the actual folder name for LightFury, thanks?
EDIT: Ah, never mind
## Post #5
- Username: Z0155
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 04, 2019 3:57 am
- Post datetime: 2019-08-05T18:41:23+00:00
- Post Title: School of Dragons: Light Fury

> Reply from Snapdragons ↑Sun May 19, 2019 3:48 pm at Sun May 19, 2019 3:48 pm
>
> 
1. To find the extractable files, go to the AppData folder on your computer (it may be set to hidden)
2. Then navigate AppData>LocalLow>Unity>JumpStartSoD
3. Once in there scroll until you find files with dragon names (or anything else you want to extract) 
4. Go into the folders until you find a file called “-data”
5. Copy and paste “-data” into a folder outside of the AppData folder
6. Run “-data” through uTinyRipper
7. Take the exported asset file and drop it into Unity (download the FBX exporter as well)
8. the models you want will be in the “prefabs” folder
9. Drop one into the right hand panel and right click it and select “export to FBX”
10. Import your FBX into your 3D program of choice.

I got to point 8, but when I open the prefabs folder, the models are pink. How could I fix that?
Also, the pic you linked seems to be a scene in Blender. Now, if the prefab models have the textures and materials correctly applied to them, is it possible to save them without the animation and other control points? I mean these:  Thanks in advance!
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-05T20:30:48+00:00
- Post Title: School of Dragons: Light Fury

> Reply from Z0155 ↑Tue Aug 06, 2019 2:41 am at Tue Aug 06, 2019 2:41 am
>
> I got to point 8, but when I open the prefabs folder, the models are pink. How could I fix that?
Just use AssetStudio for unity files and you'll be good to go, hassle free.
## Post #7
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-08-06T05:38:43+00:00
- Post Title: School of Dragons: Light Fury

> Reply from Z0155 ↑Tue Aug 06, 2019 2:41 am at Tue Aug 06, 2019 2:41 am
>
> 
I got to point 8, but when I open the prefabs folder, the models are pink. How could I fix that?
Also, the pic you linked seems to be a scene in Blender. Now, if the prefab models have the textures and materials correctly applied to them, is it possible to save them without the animation and other control points? I mean these:  Thanks in advance!

To your first question, the models are pink because there are no shaders assigned to them. Simply find the material spheres for the dragon you’re trying to extract, shift select all of them and set the shader in the right hand panel to “standard”
As for your second question, there’s a prefab with an un-animated dragon model. You can export that one. I should probably note that you don’t want to export the ones with “PfD” in their names. Just export the ones with “DW” in their name
## Post #8
- Username: Z0155
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 04, 2019 3:57 am
- Post datetime: 2019-08-14T20:56:07+00:00
- Post Title: School of Dragons: Light Fury

Alright, thank you for the suggestions!
## Post #9
- Username: guywithafork1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 10, 2020 7:37 am
- Post datetime: 2020-02-10T00:17:36+00:00
- Post Title: School of Dragons: Light Fury

> Reply from Snapdragons ↑Tue Aug 06, 2019 1:38 pm at Tue Aug 06, 2019 1:38 pm
>
> 
Z0155 wrote: ↑Tue Aug 06, 2019 2:41 am
I got to point 8, but when I open the prefabs folder, the models are pink. How could I fix that?
Also, the pic you linked seems to be a scene in Blender. Now, if the prefab models have the textures and materials correctly applied to them, is it possible to save them without the animation and other control points? I mean these:  Thanks in advance!


To your first question, the models are pink because there are no shaders assigned to them. Simply find the material spheres for the dragon you’re trying to extract, shift select all of them and set the shader in the right hand panel to “standard”
As for your second question, there’s a prefab with an un-animated dragon model. You can export that one. I should probably note that you don’t want to export the ones with “PfD” in their names. Just export the ones with “DW” in their name

So I got the file, for let's say a Stormcutter, from uTinyRipper. I have the entire -data folder, and when I import both the prefab and mesh .ASSET file, they come up with no mesh visible, and in the prefab all the scripts are missing. Also, the FBX exporter refuses to work and I'm trying to fix that, but mainly I just want to be able to see or use the mesh/prefab in Unity.

The error code for importing the mesh .asset files are common for all types of dragon "-data" files, it saying: something like (this is for the Stormcutter) Unable to parse file Assets/DWStormcutterMesh.asset: [Parser Failure at line 984: Unknown escaped character]
