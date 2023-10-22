## Post #1
- Username: Juso87
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 29, 2017 6:05 pm
- Post datetime: 2019-04-19T13:51:45+00:00
- Post Title: World War Z (Not a UE4 Game)

World War Z just came out and I thought it was a UE4 Game, however seems to be using Saber Interactive own proprietary engine instead.

Paks can be open with any zip program.
## Post #2
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2019-04-21T16:47:39+00:00
- Post Title: World War Z (Not a UE4 Game)

It's the same engine that is also used for Quake Champions
## Post #3
- Username: PlanK69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 02, 2015 5:32 am
- Post datetime: 2019-04-30T11:00:06+00:00
- Post Title: World War Z (Not a UE4 Game)

Thanks Juso87. Just did a quick search and saw your post. I really was only after the .bik files for the in-game movies, and I found them very quickly after reading your post. cheers
## Post #4
- Username: Alcat101
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 02, 2018 10:51 pm
- Post datetime: 2019-05-05T13:42:13+00:00
- Post Title: World War Z (Not a UE4 Game)

Hi, does anyone know how to extract model from this game?

I've scoured other xentax thread that discussed extracting asset from Saber proprietary engine, but it looks there's no surefire way to extract model intact written yet here.
The model format is in .tpl, while the texture is .pct

Ninjaripper is able to get textures and model, but the model doesnt have intact UV, so its only good on extracting textures.
## Post #5
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-06T05:51:06+00:00
- Post Title: World War Z (Not a UE4 Game)

> Reply from Alcat101 ↑Sun May 05, 2019 9:42 pm at Sun May 05, 2019 9:42 pm
>
> 
Hi, does anyone know how to extract model from this game?

I've scoured other xentax thread that discussed extracting asset from Saber proprietary engine, but it looks there's no surefire way to extract model intact written yet here.
The model format is in .tpl, while the texture is .pct

Ninjaripper is able to get textures and model, but the model doesnt have intact UV, so its only good on extracting textures.
Ninja ripper imports perfectly UVs
[](https://ibb.co/pywdkVp)
## Post #6
- Username: Alcat101
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 02, 2018 10:51 pm
- Post datetime: 2019-05-07T09:30:47+00:00
- Post Title: World War Z (Not a UE4 Game)

> Reply from fil1969 ↑Mon May 06, 2019 1:51 pm at Mon May 06, 2019 1:51 pm
>
> 
Ninja ripper imports perfectly UVs

huh, so character model have perfect UV extract. I just tried extracting the same character model, and viewing it with noesis and it does have texture applied correctly

but whatever weapon model .rip extract I preview on noesis, its all screwed up. (I tried extracting PDW)

is there any specific settings you use on ninjaripper?
## Post #7
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-07T16:21:12+00:00
- Post Title: World War Z (Not a UE4 Game)

> Reply from Alcat101 ↑Tue May 07, 2019 5:30 pm at Tue May 07, 2019 5:30 pm
>
> 
fil1969 wrote: ↑Mon May 06, 2019 1:51 pm
Ninja ripper imports perfectly UVs



huh, so character model have perfect UV extract. I just tried extracting the same character model, and viewing it with noesis and it does have texture applied correctly

but whatever weapon model .rip extract I preview on noesis, its all screwed up. (I tried extracting PDW)

is there any specific settings you use on ninjaripper?
yes, for clothes head you have to set in ninja uv scale to 4, for other parts like hair , skin and other , leave the scale as default (1)
## Post #8
- Username: cevefas
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Aug 29, 2019 1:36 am
- Post datetime: 2020-03-27T13:49:38+00:00
- Post Title: World War Z (Not a UE4 Game)

does ninjaripper export skeletons?
## Post #9
- Username: gladias9
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 27, 2018 3:33 pm
- Post datetime: 2020-05-12T21:51:37+00:00
- Post Title: World War Z (Not a UE4 Game)

Anyone find a way to edit character values? Like say if I wanted to edit Weapon stats, item values, CPU player health or other things regarding their efficiency?
## Post #10
- Username: CyberWolf
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 29, 2020 4:24 am
- Post datetime: 2021-10-26T17:46:03+00:00
- Post Title: World War Z (Not a UE4 Game)

Hey, guys! im sorry to butt in, but does anyone know how can I view .tpl files and export them to obj files by any chance?
## Post #11
- Username: KrazyBee129
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 08, 2022 12:55 am
- Post datetime: 2022-05-07T16:57:52+00:00
- Post Title: World War Z (Not a UE4 Game)

hello any one tried ripping the guns from this game?
## Post #12
- Username: Alcat101
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 02, 2018 10:51 pm
- Post datetime: 2022-05-08T15:02:55+00:00
- Post Title: World War Z (Not a UE4 Game)

model ripping is possible with this game

through my fairly shallow research, I found out that you can unpack the game files and see the raw format of it.
the weapon file I believe resides on shared_XXX.pak, which will have kinda 2 files below:
the .tpl is the model file which I assume is saber proprietary model format
the. pct is the texture file which iirc theres a tool that can directly convert it to general texture format (DDS, TGA, etc)
I believe the texture-pct tool exist somewhere on this forum that discusses Quake Champion game made by Saber, since they also uses the same engine/asset format I believe.

last time I used ninja ripper to grab the model the weapon rip kinda came out a jumbled mess, but idk if its a quirk of WWZ specifically only or not, 
to the point that it needs significant time sink to rearrange it to usable asset to be used elsewhere.

soo.. still waiting for a tool to directly convert those .tpl format.. or waiting for someone else to sort through the manual rip and dump it online xd
## Post #13
- Username: villynx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 30, 2022 2:37 am
- Post datetime: 2023-01-14T17:54:59+00:00
- Post Title: World War Z (Not a UE4 Game)

> Reply from fil1969 ↑Wed May 08, 2019 12:21 am at Wed May 08, 2019 12:21 am
>
> 
Alcat101 wrote: ↑Tue May 07, 2019 5:30 pm
fil1969 wrote: ↑Mon May 06, 2019 1:51 pm
Ninja ripper imports perfectly UVs



huh, so character model have perfect UV extract. I just tried extracting the same character model, and viewing it with noesis and it does have texture applied correctly

but whatever weapon model .rip extract I preview on noesis, its all screwed up. (I tried extracting PDW)

is there any specific settings you use on ninjaripper?

yes, for clothes head you have to set in ninja uv scale to 4, for other parts like hair , skin and other , leave the scale as default (1)
Can you guys share the tutorial to see the model and the texture? And what software is that? Is it using blender? Cause Im trying right now to import the model with the texture to blender but with my current info just only can import the model, the texture i don't know how to import it...
