## Post #1
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-09T22:21:38+00:00
- Post Title: [Request] Project Sylpheed - Arc of Deception Models

This was an Xbox 360 game released by Square Enix a year or so after the 360 came out. Really awesome game, great visuals, typical anime storyline, really really cool mechanical designs for starships and warships.

The player's spacecraft, the Delta Saber: 

Anyway, here's all the information I can provide:

The root contains 2 folders, "dat" and "hidden" as well as a config.ini file which appears to be just for setting the in-game language option and the typical default.xex file.

the dat folder contains the folder "movie" with .wmv's of all the game's cutscenes and several uniquely named .p00 (some have files from .p00 through .p04) files of varying sizes between 426kb and 255mb. each is followed by a .pak file of the same name as the .p00 file before it with file sizes between 1kb and 19kb.

the hidden folder contains 2 more sets of .p00 and .pak files as well as another folder "resource3d" (pretty obvious where the models and textures are stored.) this folder contains .xpr files, which to my understanding are a standard xbox 360 container of some sort. using unbundler.exe from the XSDK extractes all the .tga textures, but of course, no models.

I know the .xpr files contain mesh data for some dead or alive and soul calibur games so i'd assume it's the same here. This file may have already been covered but my research didn't turn up anything. I tried greed xplorer and several other xpr exporters meants for DoA and SC and they errored out.


Since Unbundler.exe did export the textures properly, All we need here is the mesh data.


Sample XPR Data: DeltaSaber_A.xpr

[https://skydrive.live.com/#cid=E74D852E ... DF762F!108](https://skydrive.live.com/#cid=E74D852ED8DF762F&id=E74D852ED8DF762F!108)
