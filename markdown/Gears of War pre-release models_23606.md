## Post #1
- Username: AngelBryan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 18, 2021 8:18 am
- Post datetime: 2021-03-18T04:31:52+00:00
- Post Title: Gears of War pre-release models

Hello. I am trying to extract the models from the leaked Unreal Warfare (Gears of War) pre-release build from 2004, however the files are too old and is almost impossible to get them out, that's why I came here asking for your help. I already tried extracting them with UE Viewer but It crashes everytime I try to open the packages. What I managed to do is exporting each individual asset from some packages into .T3D files, but trying to open them with UDK Editor fails as well. So what could be done? As fas as I know, those models have never been ripped and would be nice to get them out just for the sake of preservation, maybe we could also give them use and a new life.

Pre-release COG Gear





 







Pre-release Geist (Locust) Wretch





COG Assault Rifle





Unreal Warfare Build: [https://mega.nz/file/jodUkRIA#gKhBYLwVu ... j1K4HLXXDw](https://mega.nz/file/jodUkRIA#gKhBYLwVuvS32uHECI0x1QNb5_EHQLHdZj1K4HLXXDw)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-03-18T13:36:43+00:00
- Post Title: Gears of War pre-release models

From what I can see, there's no actual model data in those Grunt or Wretch files - just textures and text files.
## Post #3
- Username: AngelBryan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 18, 2021 8:18 am
- Post datetime: 2021-03-18T13:46:23+00:00
- Post Title: Gears of War pre-release models

Yeah i just realized that, it seems that only the textures were exported. Any idea on how could we extract them? I don't know what else to do.
## Post #4
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2021-03-18T18:45:10+00:00
- Post Title: Gears of War pre-release models

I believe the source code to compile the engine was also included, so what you could do is write a new batch commandlet that goes into the USkeletalMesh Class and dumps it to your desired format, this is quite advanced and will probably require some experience with the Unreal API but its the only clean and fast solution i can think of unless you edit UModel ( Unreal Model Viewer) and then support the differences in the Format/Classes. ( The exact information is also in the native source code ).
## Post #5
- Username: AngelBryan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 18, 2021 8:18 am
- Post datetime: 2021-03-19T01:27:21+00:00
- Post Title: Gears of War pre-release models

> Reply from Highflex ↑Fri Mar 19, 2021 2:45 am at Fri Mar 19, 2021 2:45 am
>
> 
I believe the source code to compile the engine was also included, so what you could do is write a new batch commandlet that goes into the USkeletalMesh Class and dumps it to your desired format, this is quite advanced and will probably require some experience with the Unreal API but its the only clean and fast solution i can think of unless you edit UModel ( Unreal Model Viewer) and then support the differences in the Format/Classes. ( The exact information is also in the native source code ).
Unfortunately that is beyond my abilities. Do you think you could do it? I will appreciate it very much.
