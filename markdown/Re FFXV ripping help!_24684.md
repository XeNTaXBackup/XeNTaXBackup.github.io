## Post #1
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-11-06T19:05:13+00:00
- Post Title: Re: FFXV ripping help!

duuude this is what i was trying to figure out as well im in the same boat
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-11-07T00:46:42+00:00
- Post Title: Re: FFXV ripping help!

I can't speak for characters, but you can't load environment maps, you can only load individual environment assets, you'd have to lay them out and place them yourselves, along with remake the terrain data entirely.

ie: toward the end of the game when noctis fights the guardian-like characters that transport you to another world for the battle, thats a single mesh, so you can load that, but for 99% of the game it's multiple asset collections placed around that're referenced by the map files.
As it stands currently there isn't a tool for it.
## Post #3
- Username: elderserpent
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 14, 2022 7:39 am
- Post datetime: 2022-02-14T00:05:37+00:00
- Post Title: Re: FFXV ripping help!

> Reply from lionheartuk ↑Sun Nov 07, 2021 8:46 am at Sun Nov 07, 2021 8:46 am
>
> 
I can't speak for characters, but you can't load environment maps, you can only load individual environment assets, you'd have to lay them out and place them yourselves, along with remake the terrain data entirely.

ie: toward the end of the game when noctis fights the guardian-like characters that transport you to another world for the battle, thats a single mesh, so you can load that, but for 99% of the game it's multiple asset collections placed around that're referenced by the map files.
As it stands currently there isn't a tool for it.

You have any clue where the terrain data could be located in the files? I pieced together Galdin Quay but can't seem to find the ground terrain like the beach shore surrounding it or the actual ground itself around Galdin, like mountains and etc.
## Post #4
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2022-02-16T02:20:30+00:00
- Post Title: Re: FFXV ripping help!

bro he just answered your question I too have tried to piece together environments ; i tried to piece together Luna Freya Room nonetheless impossible as there are certain assets missing that cannot be extracted to complete the whole room; this game is already hitting 10 years old already so I doubt there will be any updates to the tools to allow this ;you will have to recreate assets from the game from a powerful program like blender or 3dmax desk and get fammilar with sculpting and creating terrain in those programs if you want to be as closest as possible to the environmental asset
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2022-02-21T00:38:16+00:00
- Post Title: Re: FFXV ripping help!

> Reply from elderserpent ↑Mon Feb 14, 2022 8:05 am at Mon Feb 14, 2022 8:05 am
>
> 
lionheartuk wrote: ↑Sun Nov 07, 2021 8:46 am
I can't speak for characters, but you can't load environment maps, you can only load individual environment assets, you'd have to lay them out and place them yourselves, along with remake the terrain data entirely.

ie: toward the end of the game when noctis fights the guardian-like characters that transport you to another world for the battle, thats a single mesh, so you can load that, but for 99% of the game it's multiple asset collections placed around that're referenced by the map files.
As it stands currently there isn't a tool for it.


You have any clue where the terrain data could be located in the files? I pieced together Galdin Quay but can't seem to find the ground terrain like the beach shore surrounding it or the actual ground itself around Galdin, like mountains and etc.

The terrain is most likely heightmap data like terrains/landscapes usually are.
So if you're able to find weird greyscale textures in the project then those are possibly the heightmaps, you'll just have to plug them into your own geometry it's all heightmap data not actual meshes.
For things like the assets placed around, that'll be somewhere but so far as I'm aware nobody has looked into it, they just instance things everywhere, the same way the grass is done.
