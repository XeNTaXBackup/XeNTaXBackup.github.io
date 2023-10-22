## Post #1
- Username: OverLord115
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 26, 2017 12:52 am
- Post datetime: 2017-11-08T21:04:53+00:00
- Post Title: Resistance 2 .dat files ¿how do i decrypt them?

Hello, I'm new to these forums and I would like to know how decrypt the .dat files (mainly mobys, textures and shaders because I understood that they are the most important) of Resistance 2, I have seen several times that this topic was treated but I still do not understand it. I understood that the program noesis serves to decrypt this type of files but it always gives me the error "File could not be previewed" with all the .dat files and others so if they have the solution to this I would be very grateful. All this to get the models (obviously), textures (also obviously) and sounds to export them to Garry's Mod.

Here is the mobys, textures and shaders.dat link: [https://www.mediafire.com/folder/zn4nn1fpi3qb5/things](https://www.mediafire.com/folder/zn4nn1fpi3qb5/things)

From already thank you very much

(Sorry if i have a bad english, i am from Argentina)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-11-10T11:25:24+00:00
- Post Title: Resistance 2 .dat files ¿how do i decrypt them?

All those dat files are headerless archives without TOC, they are cooked that way.
All of them are hash-based. File "assetlookups.dat" is TOC file that contains offset infos for most other .dat files.
About naming them, some files have names built-in, some don't. Textures are tricky to get, since infos are stored in shader files.
## Post #3
- Username: OverLord115
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 26, 2017 12:52 am
- Post datetime: 2017-11-11T11:40:33+00:00
- Post Title: Resistance 2 .dat files ¿how do i decrypt them?

> Reply from PredatorCZ
>
> All those dat files are headerless archives without TOC, they are cooked that way.
All of them are hash-based. File "assetlookups.dat" is TOC file that contains offset infos for most other .dat files.
About naming them, some files have names built-in, some don't. Textures are tricky to get, since infos are stored in shader files.

So, i need to search how to decrypt .toc files?
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-11-11T16:45:44+00:00
- Post Title: Resistance 2 .dat files ¿how do i decrypt them?

They are not encrypted, they're just cooked.
Here, let me explain.
All those files: animsets, assetlookup,cinematics,cubemaps,effect, etc.
Most of them are linked together via hashes. 
And file called assetlookups.dat like I said is TOC (== Table of contents). 
That means it have hashed names and offsets for most of other files, so game could read them correctly.
Anyway I'm testing my old extraction app for this game, I'll try to release it next week. It should extract/convert most files.
## Post #5
- Username: OverLord115
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 26, 2017 12:52 am
- Post datetime: 2017-11-11T18:17:31+00:00
- Post Title: Resistance 2 .dat files ¿how do i decrypt them?

> Reply from PredatorCZ
>
> They are not encrypted, they're just cooked.
Here, let me explain.
All those files: animsets, assetlookup,cinematics,cubemaps,effect, etc.
Most of them are linked together via hashes. 
And file called assetlookups.dat like I said is TOC (== Table of contents). 
That means it have hashed names and offsets for most of other files, so game could read them correctly.
Anyway I'm testing my old extraction app for this game, I'll try to release it next week. It should extract/convert most files.

Oh! Now I understand, well, thank you very much for the explanations and everything, I hope you are successful with your extraction app and if you can let me know when it is achievable
