## Post #1
- Username: shaqqytc
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 14, 2023 6:45 pm
- Post datetime: 2023-02-14T10:57:52+00:00
- Post Title: Need help extracting/packing Unity 5.4.0f2 WebGL data file

Hello, I have been trying to unpack all the data from a data file from a webgl game, this unity bundle file contains files most unity games do not such as the global-metadata file. All the tools I've tried will not extract and I cannot repack the file properly because of it. You can find the file here.

[https://game.mages.co.jp/plastic-memori ... bgl.datagz](https://game.mages.co.jp/plastic-memories/system/webgl/Release/webgl.datagz)

Any help with figuring this out would be appreciated. Thanks!
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-02-15T21:56:02+00:00
- Post Title: Need help extracting/packing Unity 5.4.0f2 WebGL data file

You can use UABEA to export/import [https://github.com/nesrak1/UABEA](https://github.com/nesrak1/UABEA)

Other tools are listed here [http://wiki.xentax.com/index.php/List_of_Unity_Tools](http://wiki.xentax.com/index.php/List_of_Unity_Tools)
## Post #3
- Username: shaqqytc
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 14, 2023 6:45 pm
- Post datetime: 2023-02-20T00:30:51+00:00
- Post Title: Need help extracting/packing Unity 5.4.0f2 WebGL data file

Unfortunately all the tools don't support WebGL Unity games. That's why I'm asking for help. None of those tools can extract global metadata or any of the games' scripts.
## Post #4
- Username: kiraio
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 20, 2023 5:39 pm
- Post datetime: 2023-02-20T10:26:35+00:00
- Post Title: Need help extracting/packing Unity 5.4.0f2 WebGL data file

> Reply from shaqqytc ↑Mon Feb 20, 2023 8:30 am at Mon Feb 20, 2023 8:30 am
>
> 
Unfortunately all the tools don't support WebGL Unity games. That's why I'm asking for help. None of those tools can extract global metadata or any of the games' scripts.

You can use [AssetStudio](https://github.com/Perfare/AssetStudio/) to extract Unity WebGL.data file, but AssetStudio can't pack it back to original file. After extracting you will get a bunch of resources, go to Il2CppData/Metadata folder, there you will get global-metadata.dat file. The path may be different, cause the Unity version is too old. I try to open global-metadata file using [Il2CppInspector](https://github.com/djkaty/Il2CppInspector), but no luck. I stuck at second step, cause there's no executable file in WebGL build.
## Post #5
- Username: shaqqytc
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 14, 2023 6:45 pm
- Post datetime: 2023-02-20T15:37:41+00:00
- Post Title: Need help extracting/packing Unity 5.4.0f2 WebGL data file

So I tried extracting webgl.data with AssetStudio but the only Resource I get is unity_builtin_extras.
## Post #6
- Username: kiraio
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 20, 2023 5:39 pm
- Post datetime: 2023-04-15T19:52:53+00:00
- Post Title: Need help extracting/packing Unity 5.4.0f2 WebGL data file

> Reply from shaqqytc ↑Mon Feb 20, 2023 11:37 pm at Mon Feb 20, 2023 11:37 pm
>
> 
So I tried extracting webgl.data with AssetStudio but the only Resource I get is unity_builtin_extras.

AssetStudio didn't support Unity 5, maybe? IDK.
