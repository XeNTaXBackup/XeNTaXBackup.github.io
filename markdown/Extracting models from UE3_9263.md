## Post #1
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2012-07-13T16:32:34+00:00
- Post Title: Extracting models from UE3

Im trying to extract models from lollipop chainsaw and I have all these .xxx files



I have heard about UE Viewer but I dont know how to go about extracting the models with this and I cant find any tutorials either. All the tutorials I have seen are using a different file format. 
Can anyone please guide me where to go from here.
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-07-13T16:53:49+00:00
- Post Title: Extracting models from UE3

Here is a link to official UE tool FAQ - [http://gildor.org/projects/umodel/faq](http://gildor.org/projects/umodel/faq)
Also check out English forum section there you can find any help you need. If you still don't understand something, ask here maybe I can help. I have extracted models from that game.
## Post #3
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2012-07-14T16:46:43+00:00
- Post Title: Extracting models from UE3

Ok so I have managed to extract the models with umodelGUI but the textures are low res. I read on Gildors site that the high res textures are stored separate and how you can find them with umodel but I dont know how to use umodel and Im using umodelGUI. Any ideas how and where I can look for the high res textures?
## Post #4
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-14T17:14:03+00:00
- Post Title: Extracting models from UE3

> Reply from farakh
>
> Ok so I have managed to extract the models with umodelGUI but the textures are low res. I read on Gildors site that the high res textures are stored separate and how you can find them with umodel but I dont know how to use umodel and Im using umodelGUI. Any ideas how and where I can look for the high res textures?
the textures are stored in the .tfc files, just make sure they are all in the same folder as the model files.
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-07-14T17:35:47+00:00
- Post Title: Extracting models from UE3

A small advice - extract all files in one folder, put umodel files there and there create .bat file. Then umodel can handle all files automatically.
Example of .bat file is attached.
[extract.rar](https://xentaxbackup.github.io/file/5574_extract.rar)
## Post #6
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-07-14T17:36:39+00:00
- Post Title: Extracting models from UE3

> Reply from farakh
>
> Ok so I have managed to extract the models with umodelGUI but the textures are low res. I read on Gildors site that the high res textures are stored separate and how you can find them with umodel but I dont know how to use umodel and Im using umodelGUI. Any ideas how and where I can look for the high res textures?

That happens because you don't have umodel.exe inside your root game's folder and you're calling that program with a loader from another location, so It's using the small textures that come inside your .xxx files.

Open your windows menu, go to run (or search in win 7) and type cmd. After that, copy the folder adess where you extracted  your files and type in your cmd window:

```

```


Then type:

```

```


And that's all.

Tips: you must have umodel.exe inside the folder where you unpacked all your game data. The textures are inside of .tfc files that umodel can't extract by itself but I can by emulating the unreal engine.

See ya.
## Post #7
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2012-07-14T22:35:50+00:00
- Post Title: Extracting models from UE3

Thanks for your help guys. I extracted everything from the disc and umodel extracted everything, low res, high res textures, animations, static meshes, all the characters etc.
