## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-07T10:33:11+00:00
- Post Title: 007 Goldeneye PS3

007 Legends tools. To save time, I didn't make a full set of tools, so its done in steps:

1. Split big archives into individual "GEOM" files with vgmtoolbox.
vgmtoolbox "advanced cutter" can be found in "misc tools / extraction / generic"
Put 007_geom.xml into its folder, load it and drag files onto it. Game files have no names, so proper extraction will not be possible anyway.

2. Run goldeneye007_unpack.bms script on .geom files and it will extract resources from it: textures, models, skeletons, other types.

3. 007_image_ps3.exe will convert all textures into DDS.
Run it in the folder where you have .texture files.

4. Drag .skel file onto 007_model_ps3.exe to convert all meshes in the directory and connect them with that skeleton. Low quality models will have many LODs. Recognized by having no finger bones. Usually not needed. Good quality models are usually in separate .geom file, with only one highest LOD.


[007 goldeneye.rar](https://xentaxbackup.github.io/file/11589_007 goldeneye.rar)
## Post #2
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-06-05T19:12:05+00:00
- Post Title: 007 Goldeneye PS3

I just want to let it be known that for some reason it was neglected that the version of quickbms needed for this to work is here: 

[https://drive.google.com/file/d/1n5Wfgk ... sp=sharing](https://drive.google.com/file/d/1n5Wfgk8HvzyTOa9ZLn09AYYaiewmF5gT/view?usp=sharing)

Otherwise you will run into errors like I did lol.
