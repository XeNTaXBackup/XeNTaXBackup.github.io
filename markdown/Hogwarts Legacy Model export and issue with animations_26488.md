## Post #1
- Username: LegnaX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2022 6:12 pm
- Post datetime: 2023-02-19T02:53:40+00:00
- Post Title: Hogwarts Legacy: Model export and issue with animations

Hello. So, as the title suggests, it is possible to extract models from Hogwarts Legacy. Using UE Viewer, you can select the game folder containing the paks (\Hogwarts Legacy\Phoenix\Content\Paks), which will display all assets inside the game. The interesting ones are mostly located inside Game/RiggedObjects.

Now, there's a problem I encountered: while it's perfectly fine to open, view and extract objects, the main issue for me is opening, browsing, appending, or extracting animations, as doing any of these actions with the animations will cause the following error to appear:


I tried different things, such as exporting the animations into a different folder (UmodelSaved) and including the model that uses them, but sadly, browsing the contents of that folder (which shows the assets properly) and then extracting any asset from the .pak into the folder will not even allow the UE Viewer to browse them afterward, outputting the following error: 


This is weird because the exported file has the same size as the one inside the .pak, and opening it with Notepad++ shows that the file is not encrypted. Not sure why this is not working.

Any idea for the animations to work? I am providing the folder where I extracted the model and animations that give the "encrypted" error, as I believe that solving that would allow the model to be exported with the animations attached to the armature: [Download link](https://mega.nz/file/dJkGVCSA#ytKimj3kCenG9lHvVYLM1XBDiMokV2B2SKCgxZ5H9cE)
## Post #2
- Username: LegnaX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2022 6:12 pm
- Post datetime: 2023-02-19T03:05:52+00:00
- Post Title: Hogwarts Legacy: Model export and issue with animations

I really should learn how to use my eyes sometimes.

As soon as I pressed send and started thinking, I went to Gildor's forum and found the solution. 

If anyone wants to know, it's [here](https://www.gildor.org/smf/index.php/topic,8496.0.html).

Basically:
1) Download the special version from [here](https://drive.google.com/file/d/1gOr_NbJaPgnu21EeVGCTsDjP78r_nbzq/view). To open UE Viewer, you need to use umodel_acl_2.1.exe.
2) Open the game's pak folder with this version. You need to select Unreal Engine 4, version 4.27.
3) Open the model you want to load from the RiggedObjects folder.
4) Append the correspondent animations from the Game/Animations folder. Make sure you append the correct animations.
5) Export. Very easy.
## Post #3
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2023-02-21T23:43:06+00:00
- Post Title: Hogwarts Legacy: Model export and issue with animations

how did you find the textures for the students the files given to me from a prominent game extracter only gives red or white textures; are these textures have to be colored manually or is there a process or script that needs to be run
