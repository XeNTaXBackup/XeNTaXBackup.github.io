## Post #1
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-09-08T03:59:05+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

it would be possible to make a plugin capable of converting from fbx to .wmb, which is the format in which the game saves the meshes, or something similar not necessarily fbx something like blender to .wmb, I know that modding for the Paltinum engine is kind of complicated I know is there a plugin for nier autoamta that can import wmb to blender is it possible to do something like this for metal gear rising?


Samples
[https://drive.google.com/file/d/1fiFoF7 ... sp=sharing](https://drive.google.com/file/d/1fiFoF7k1poVkCKca4q1EE2i5VqfR_1aW/view?usp=sharing)

I know it can be complicated, but I would appreciate the help.


Probably useful


[https://zenhax.com/viewtopic.php?f=5&t= ... ear+rising](https://zenhax.com/viewtopic.php?f=5&t=4840&hilit=metal+gear+rising)
[https://github.com/WoefulWolf/NieR2Blender2NieR](https://github.com/WoefulWolf/NieR2Blender2NieR)
[https://github.com/Kerilk/bayonetta_tools](https://github.com/Kerilk/bayonetta_tools)
[viewtopic.php?f=16&t=10147&hilit=MGR](https://forum.xentax.com/viewtopic.php?f=16&t=10147&hilit=MGR)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-08T05:25:27+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

> Reply from LeoFeroz ↑Thu Sep 08, 2022 11:59 am at Thu Sep 08, 2022 11:59 am
>
> 
it would be possible to make a plugin capable of converting from fbx to .wmbHard to achieve, I guess.

> that can import wmb to the blender is it possible to make something like that for metal gear rising?Looks doable (using hex2obj, view link in my sig. One sub mesh only, as always, mostly):
.



em002a-wmb.jpg (210.81 KiB) Viewed 196 times
## Post #3
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-09-08T10:17:54+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

> Reply from shakotay2 ↑Thu Sep 08, 2022 1:25 pm at Thu Sep 08, 2022 1:25 pm
>
> 
LeoFeroz wrote: ↑Thu Sep 08, 2022 11:59 am
it would be possible to make a plugin capable of converting from fbx to .wmbHard to achieve, I guess.
that can import wmb to the blender is it possible to make something like that for metal gear rising?Looks doable (using hex2obj, view link in my sig. One sub mesh only, as always, mostly):
.
em002a-wmb.jpg

maybe but like every format, with a lot of effort you can get Nier automata has custom models so it may be possible but the plugin creator is not very interested in other games from Platinum Games, well thanks for your comment is already something
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-08T10:43:29+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

The Bayonetta plugin from Kerilk on Zenhax is said to support MGRR but I didn't get above wmb loaded using his dll.

Maybe the source needs to be compiled with setting "false" to "true" here:
SPGamesPair(Model_Bayo_Check<false, MGRR>, Model_Bayo_Load<false, MGRR>),

(Maybe I'll give it a shoot later...)
## Post #5
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-09-08T17:50:12+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

> Reply from shakotay2 ↑Thu Sep 08, 2022 6:43 pm at Thu Sep 08, 2022 6:43 pm
>
> 
The Bayonetta plugin from Kerilk on Zenhax is said to support MGRR but I didn't get above wmb loaded using his dll.

Maybe the source needs to be compiled with setting "false" to "true" here:
SPGamesPair(Model_Bayo_Check<false, MGRR>, Model_Bayo_Load<false, MGRR>),

(Maybe I'll give it a shoot later...)

the Kerilk plugin supports loading the models before being extracted from the .dat it reads the dat file without being extracted if I'm not mistaken
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-08T21:18:51+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

> Reply from LeoFeroz ↑Fri Sep 09, 2022 1:50 am at Fri Sep 09, 2022 1:50 am
>
> the Kerilk plugin supports loading the models before being extracted from the .dat it reads the dat file without being extracted if I'm not mistakenHaha, yes - catched me.   (Kerilk, he's unbelievable, isn't he?  )
.



em002a-dat.jpg (31.47 KiB) Viewed 163 times



> [like] a plugin for Nier Autoamta that can import wmb to the blender is it possible to make something like that for metal gear rising?So then I misunderstood your motivation. Perhaps.

What were the advantage of such a wmb importer for blender?
Once you have a model (from a .dat file) in Noesis you're free to export it to some other format.

(This doesn't help solving your fbx2wmb request, I see. But I thought wmb-import was another point of your interest.)
## Post #7
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-09-09T00:05:20+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

> Reply from shakotay2 ↑Fri Sep 09, 2022 5:18 am at Fri Sep 09, 2022 5:18 am
>
> 
LeoFeroz wrote: ↑Fri Sep 09, 2022 1:50 amthe Kerilk plugin supports loading the models before being extracted from the .dat it reads the dat file without being extracted if I'm not mistaken
Haha, yes - catched me.   (Kerilk, he's unbelievable, isn't he?  )
.
em002a-dat.jpg
[like] a plugin for Nier Autoamta that can import wmb to the blender is it possible to make something like that for metal gear rising?So then I misunderstood your motivation. Perhaps.

What were the advantage of such a wmb importer for blender?
Once you have a model (from a .dat file) in Noesis you're free to export it to some other format.

(This doesn't help solving your fbx2wmb request, I see. But I thought wmb-import was another point of your interest.)

what I'm really interested in and customized models like the blender part would be like NieR2Blender2NieRr capable of importing wmb, modifying it and exporting it to wmb something similar not necessarily fbx   

Well thanks anyway you are a very nice guy 

my english is pretty bad maybe i confused you a little
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-09T07:05:19+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

> Reply from LeoFeroz ↑Fri Sep 09, 2022 8:05 am at Fri Sep 09, 2022 8:05 am
>
> what I'm really interested in and customized models like the blender part would be like NieR2Blender2NieRr capable of importing wmb, modifying it and exporting it to wmb something similar not necessarily fbxOk. As I wrote earlier: exporting to wmb will be the hard part. Because you need to understand the meaning of every byte of the wmb format.

Question: is the Nier automata wmb format the same as the one of MGRR? (WMB4)
Guess, there's differences? Which?

> Well thanks anyway you are a very nice guyHaha, look at my avatar to see who I am.  

> my english is pretty bad maybe i confused you a littleNope, your english is fine.

It's just that I didn't want to check into Nier automata tools because of lack of time. I usually focus on working solutions, if any.
## Post #9
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-09-09T20:02:56+00:00
- Post Title: Metal Gear Rising Custom Meshes ?

> Question: is the Nier automata wmb format the same as the one of MGRR? (WMB4)
>
> Guess, there's differences? Which?

Yes if I'm not mistaken Nier automata is wmb3
Sample:

this is from a mod maybe not exactly the same

> It's just that I didn't want to check into Nier automata tools because of lack of time. I usually focus on working solutions, if any. I understand this takes time, you don't have to look right away, if you just take a look when you have some time available I would appreciate it.  


wmb
[https://drive.google.com/file/d/1KWK1p7 ... sp=sharing](https://drive.google.com/file/d/1KWK1p72Pt22oJYhJD_90Yv4m2mJHN-yQ/view?usp=sharing)
Complete
[https://drive.google.com/file/d/1BblTFd ... sp=sharing](https://drive.google.com/file/d/1BblTFd3GpqqJsKbNhPHIVHfyGn59wnvS/view?usp=sharing)

the format is more up-to-date it keeps all the meshes of the model without separate parts
