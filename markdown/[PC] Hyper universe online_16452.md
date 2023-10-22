## Post #1
- Username: LDTD016
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 05, 2017 9:45 pm
- Post datetime: 2017-06-26T00:56:10+00:00
- Post Title: [PC] Hyper universe online

Homepage : [http://hu.nexon.com/Main/Index](http://hu.nexon.com/Main/Index)

download : [http://www.mediafire.com/file/yr84mo41h ... -+Copy.rar](http://www.mediafire.com/file/yr84mo41ha50hi9/HyperUniverse+-+Copy.rar)

I think these files are encrypted unity files.

Is there any way to decompile this?
## Post #2
- Username: calypsoup
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Sep 12, 2016 3:51 am
- Post datetime: 2017-06-30T21:50:51+00:00
- Post Title: [PC] Hyper universe online

definitely +1'ing this ! please someone
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-01T16:29:35+00:00
- Post Title: [PC] Hyper universe online

> Reply from LDTD016
>
> I think these files are encrypted unity files.which encryption are you speaking of exactly?

At least the files are compressed, yes.



Unity-HyperUniv-Qlow.jpg (195.23 KiB) Viewed 530 times


Since the mesh type is listed as 43 you might try other tools (read here for example: [viewtopic.php?f=16&t=16292&p=130753&hil ... 43#p130753](http://forum.xentax.com/viewtopic.php?f=16&t=16292&p=130753&hilit=unity+.43#p130753))
and link at the bottom
## Post #4
- Username: calypsoup
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Sep 12, 2016 3:51 am
- Post datetime: 2017-07-02T22:02:44+00:00
- Post Title: [PC] Hyper universe online

wow thank you for this info !
## Post #5
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2020-04-15T09:23:57+00:00
- Post Title: [PC] Hyper universe online

Copy pasted from my post at zenhax => [https://zenhax.com/viewtopic.php?f=9&p=55948#p55948](https://zenhax.com/viewtopic.php?f=9&p=55948#p55948)

Tutorial for the noobs like me:

Requirements:
-Python 3.x installed, I'm doing this with python 3.4 =>  [https://www.python.org/downloads/](https://www.python.org/downloads/)
-AssetStudio.x64.v0.14.38 => [https://ci.appveyor.com/project/Perfare ... /artifacts](https://ci.appveyor.com/project/Perfare/assetstudio/branch/master/artifacts)
-Blender 2.79 or 2.8x, I'm using Blender 2.82 for this => [https://www.blender.org/download/](https://www.blender.org/download/)
-Disk Space of at least 6.32 gb (the game of 3GB plus decrypted copies of encrypted files).
-Full game (3GB), thanks to kurupeko100 for providing this on post 9 of this thread => [https://drive.google.com/file/d/1UfnU6F ... 4oHm0/view](https://drive.google.com/file/d/1UfnU6F0h1VCT0wu8zcEAczfyzSG4oHm0/view)
-A small python script and text file provided in "hyperuniverse.zip" file in the attachment of this post.

1. Unpack full game "HyperUniverse.rar" in folder with not so long folder path just in case, I'm doing this f.e. in "D:\projects\games\HyperUniverse".
2. Go into folder "D:\projects\games\HyperUniverse\HyperUniverse\HyperUniverse_Data\0000" and extract files "hyperuniverse.py" and "hyperuniverse.txt" from ""hyperuniverse.zip" attached in this post.
3. Open "hyperuniverse.py" and run (shortcut F5) with python 3's own IDLE or other IDE of preference.
It reads the tab seperated csv file "hyperuniverse.txt" and copies and converts the files in "0000" folder where I did find the xor string and puts them in handy separate sub folders in "D:\projects\games\HyperUniverse\HyperUniverse\HyperUniverse_Data\0000", where models and corresponding animations are put together.
It also moves the encrypted files I could find the xor string to folder "0000\succes_original", leaving all the files I couldn't succesfully find in folder "0000" (at the moment 83 unfound xor strings).
The decrypted files are named after the xor string and it also renamed the cab-xxxxxxx inside the files for easier navigation in AssetStudio, don't know if that screws up the files, I haven't had any trouble with it.
This script takes in my case 15 seconds.

4. Run "AssetStudioGUI.exe" in AssetStudio, File > Load folder and browse to sub folders of folder "0000" to choose a desired hero, I'll take "Tatyana" c0 (main costume) as an example.



5. Go to Asset List Tab and press type column to make sure you get all the "Animation Clips", then shift select them. Make sure you don't accidentally also select an Animator file, cause that sometimes caused an error for me.



6. Go to Scene Hierarchy Tab and select bazooka + sign (or bazooka_c1 or bazooka_c2), then "Bazooka", if sub node has "Bip001" then you're good to go.



7. Select "Model" > "Export Selected Objects + Selected AnimationClips", press Select Folder. If everything goes right AssetStudio opens a a window to the exported files.



8. Open Blender, as of this writing I'm using blender 2.8, but I tested 2.79 and that's also fine.
File > Import > FBX (.fbx). Copy paste window address that AssetStudio so conveniently opened for you, press enter.



doubleclick Bazooka.fbx and viola, imported into blender.

The Armature object's scale is 0.011 so in 3D View Editor, go to transform tab and press backspace shortcut on one of the scale value to set all scale to 1.





End of tutorial

Thanks to kurupeko100, chrrox, gorodork, google and stackoverflow!
[hyperunivers.zip](https://xentaxbackup.github.io/file/17929_hyperunivers.zip)
## Post #6
- Username: wuxian
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 28, 2020 11:15 pm
- Post datetime: 2020-10-03T11:07:13+00:00
- Post Title: [PC] Hyper universe online

Good job！！
## Post #7
- Username: gorodork
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 06, 2015 2:13 am
- Post datetime: 2023-08-19T14:43:08+00:00
- Post Title: [PC] Hyper universe online

If anyone needs the game files I uploaded a new link with them, here you go: [https://drive.google.com/file/d/1oTd1pW ... 2wwcw/view](https://drive.google.com/file/d/1oTd1pWdCAgD-AXSAobU-LgD6G7h2wwcw/view)

The password its my username
## Post #8
- Username: iceS
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 04, 2022 8:23 pm
- Post datetime: 2023-08-22T23:13:22+00:00
- Post Title: [PC] Hyper universe online

> Reply from gorodork ↑Sat Aug 19, 2023 10:43 pm at Sat Aug 19, 2023 10:43 pm
>
> 
If anyone needs the game files I uploaded a new link with them, here you go: https://drive.google.com/file/d/1oTd1pW ... 2wwcw/view

The password its my username

Hello, how to get the xor key, or what is the algorithm
