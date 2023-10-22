## Post #1
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-01T14:49:33+00:00
- Post Title: Luigi's mansion 3 noesis script

You can grab the script on my github repository (link down below) but make sure to read the instructions here first as the file structure of this game is a bit tricky.

Features: 
-Extract assets from .data archives using the associated .dict file
-Extract textures
-Extract rigged models with material support (diffuse and normal maps)

Extraction instructions : 
That game uses .dict/.data pairs to store pretty much everything. These pairs are not completely independent between themselves, as some textures/animations needed by some assets in some .data files are present in global.data, which is the most important one. 
I took that into account when writing the script, so just follow the steps below 

1) Open global.dict in Noesis and let the script extract everything, it'll take some time as the archive is quite big. You'll get a "global" folder next to it, with some subfolders. 
2) Close Noesis, open the script in a text editor and replace 

```
globalPath = None
```

by the path where the folder was extracted, for example

```
globalPath = "D:\\LM3\\romfs\\global"
```

3) Save the script and reopen Noesis. Now when you'll extract the other .data archives by clicking on the associated .dict files, it'll take into account the global archive and grab textures/animations there if they're missing.

Usage instructions : 
Simply open the extracted lm3m model files or lm3t texture files, located in the "Models" and "Textures" folders. Keep in mind these formats are not the real ones, they're pickle dumps I use to actually reconstruct the assets since the game has a chunk system which is tricky to deal with.


If you put the bLoadMaterials option to True (it is by default), materials will be auto applied to the model. It won't work perfectly on 100% of the models as I rely on patterns since the material sections of this game use some kind of presets and I don't want to RE them all. It'll work on most models though and the mistakes are easy to fix in a 3D soft. I only apply diffuse and normal textures for now but I could add more if people tell me what some textures are used for. Don't forget to toggle face cull and cycle through the different blend options if if some elements are invisible.


In any case all textures related to the model will be extracted, even if not used by the materials. They can be viewed using "Tools->Data Viewer->Textures" and will be exported with the models.

Animations are WIP and will be added later


Credits : 
Big thanks to KillzXGaming and TheFearsomeDzeraora for their research on the file structure and the geometry chunks. That script is a direct upgrade of their hard work on the formats.

Link : 
[https://github.com/Joschuka/fmt_lm3](https://github.com/Joschuka/fmt_lm3)
## Post #2
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-01T14:50:03+00:00
- Post Title: Luigi's mansion 3 noesis script

Version 1.1 : Basic animation support



If you previously extracted some dict/data pairs you'll need to re-extract these again (double clik on the dict file, previous files will be overwritten).

To import animations make sure that the bLoadAnimations option is set to True (it is by default). If so when opening a model you'll be asked to choose an animation pack, which will be located in the "Animation Packs" folder after extraction. Usually the animPacks have the same number or one that is close to the number of the model.

So for example King Boo, which is model_0 has the animPack_0, but model_28 could have animPack_29 or animPack_27, some trial and error will be needed. Also keep in mind that some packs have animations which will not be adapted to the model but some will, for example all basic ghosts anims seem to be located in the same pack despite being for different models so make sure to quickly go through all of them to make sure you're not missing anything.
## Post #3
- Username: Über Winfrey
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Nov 16, 2018 7:38 am
- Post datetime: 2020-06-04T07:12:43+00:00
- Post Title: Luigi's mansion 3 noesis script

Thanks for doing this, I was manually rigging these, I had all the Luigis and Peach completely rigged, this saves me a ton of time with the other models, especially since I'm mostly after the Dance animations from the Night Club Ghosts and Luigi's dance, so I'll definitely be checking in for when that part is completed
## Post #4
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-13T17:03:57+00:00
- Post Title: Luigi's mansion 3 noesis script

I didn't have and won't have the time (at least for the next weeks/months) to make further progress so I've updated the script with what I had so far. The second post has been edited with all the necessary information.
## Post #5
- Username: befithalo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 13, 2021 5:42 pm
- Post datetime: 2021-08-30T05:18:20+00:00
- Post Title: Luigi's mansion 3 noesis script

An invalid syntax error is given when importing this into noesis
## Post #6
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-10-01T03:53:33+00:00
- Post Title: Luigi's mansion 3 noesis script

is there any plans to update this script? some models still don't open or open with textures. also when I put my global path in the script I get a syntax error
## Post #7
- Username: CaninosVermelhos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 28, 2022 6:36 am
- Post datetime: 2022-10-27T22:37:57+00:00
- Post Title: Luigi's mansion 3 noesis script

Hey how to import the texture back. I want to edit some textures and repack it.
## Post #8
- Username: alerion921
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 21, 2023 2:55 am
- Post datetime: 2023-06-20T18:56:42+00:00
- Post Title: Luigi's mansion 3 noesis script

Hello, i have been trying to get this script working quite some time now. Anyone know where exactly i can place the .py file inside the python folder? Anywhere i try it just closes with no dialog
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-20T19:45:04+00:00
- Post Title: Luigi's mansion 3 noesis script

> Reply from alerion921 ↑Wed Jun 21, 2023 2:56 am at Wed Jun 21, 2023 2:56 am
>
> 
Hello, i have been trying to get this script working quite some time now. Anyone know where exactly i can place the .py file inside the python folder? Anywhere i try it just closes with no dialog

you don't need python. download [Noesis](https://richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4466.zip) and put the script in "..\Noesis\plugins\python", then run Noesis and open the required files
## Post #10
- Username: alerion921
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 21, 2023 2:55 am
- Post datetime: 2023-06-21T06:43:22+00:00
- Post Title: Luigi's mansion 3 noesis script

> Reply from Durik256 ↑Wed Jun 21, 2023 3:45 am at Wed Jun 21, 2023 3:45 am
>
> 
alerion921 wrote: ↑Wed Jun 21, 2023 2:56 am
Hello, i have been trying to get this script working quite some time now. Anyone know where exactly i can place the .py file inside the python folder? Anywhere i try it just closes with no dialog 


you don't need python. download Noesis and put the script in "..\Noesis\plugins\python", then run Noesis and open the required files

Thank you for your reply! 
I was having a hard time doing this and now i finally got it working thanks to you, i was having troubles with the information i found and was using python to try and achieve it (this was obviously wrong) installing a ton of things i did not need. 

The answer is to download this file (if anyone is having this issue): https://richwhitehouse.com/index.php?co ... sv4466.zip

And placing the fmt_lm3.py inside the plugins/python folder there ! 

Another question, the reason i am trying this is i want to extract all the prompts from the game to be able to change them. Is this process actually extracting those files and will i be able to recreate/save the global.dict back to original after doing so?

Thanks in advance for any answers !
