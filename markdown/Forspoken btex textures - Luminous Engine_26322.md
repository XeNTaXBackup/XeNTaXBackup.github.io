## Post #1
- Username: EratoTiaTuatha
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 18, 2018 7:33 am
- Post datetime: 2023-01-25T14:44:08+00:00
- Post Title: Forspoken btex textures - Luminous Engine

With the earc archive differences from FFXV to Forspoken solved, we're part way done with the textures as well. Forspoken uses btex just like FFXV and Flagrum can already extract single texture files (dev build, not in release versions as of writing). Texture array files are an issue as of yet.

Some samples of what's already working: 





Flagrum github: [https://github.com/Kizari/Flagrum](https://github.com/Kizari/Flagrum)
Links to the Exineris discord as well, which you should join if you have questions or contributions.
## Post #2
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2023-01-25T16:55:45+00:00
- Post Title: Forspoken btex textures - Luminous Engine

> Reply from EratoTiaTuatha ↑Wed Jan 25, 2023 10:44 pm at Wed Jan 25, 2023 10:44 pm
>
> 
With the earc archive differences from FFXV to Forspoken solved, we're part way done with the textures as well. Forspoken uses btex just like FFXV and Flagrum can already extract single texture files (dev build, not in release versions as of writing). Texture array files are an issue as of yet.

Does this support extracting animations?
## Post #3
- Username: EratoTiaTuatha
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 18, 2018 7:33 am
- Post datetime: 2023-01-25T22:14:22+00:00
- Post Title: Forspoken btex textures - Luminous Engine

extracting animations, yes, getting them out falls under earc extraction.
doing something with those animations? As of right now, not really. Since the current focus is supporting the one new type of BTEX textures which is the new arrays, models and rigs are going to have to wait a few days. 
Unless of course someone's willing to help with them and tackle reversing that stuff - the model format is somewhat changed, being spread over more files and introducing morphs, so it needs some work, but Flagrum is very well documented so it'll give anyone an easy start into Forspoken-specific stuff.
## Post #4
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2023-01-25T22:49:31+00:00
- Post Title: Forspoken btex textures - Luminous Engine

> Reply from EratoTiaTuatha ↑Thu Jan 26, 2023 6:14 am at Thu Jan 26, 2023 6:14 am
>
> 
extracting animations, yes, getting them out falls under earc extraction.
doing something with those animations? As of right now, not really. Since the current focus is supporting the one new type of BTEX textures which is the new arrays, models and rigs are going to have to wait a few days. 
Unless of course someone's willing to help with them and tackle reversing that stuff - the model format is somewhat changed, being spread over more files and introducing morphs, so it needs some work, but Flagrum is very well documented so it'll give anyone an easy start into Forspoken-specific stuff.

Alright thx. Can you let me know when they have model/rig with animation into blender working.
Basically i want to be able to extract the model with animations into blender and also into unreal engine.
The parkour animation is pretty nice.
