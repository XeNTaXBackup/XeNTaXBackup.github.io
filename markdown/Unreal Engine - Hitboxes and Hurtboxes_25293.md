## Post #1
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2022-04-25T20:43:36+00:00
- Post Title: Unreal Engine - Hitboxes and Hurtboxes

hi,   

So i've been trying to mod unreal engine games for a while now and i know how to do some basic stuff. 
Something i don't know yet but i really want to know about and figure out how it works are the hitboxes and hurtboxes (or collisions whatever you prefer naming it). I don't know where to find it. Could i find it in the blueprint file of an object or model? Or is it somewhere at a completely different location? I have been trying for a while, but i see no result and i'm still here with the same knowledge as at the moment i started trying. 

Hopefully someone can help me out here.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2022-04-26T02:12:49+00:00
- Post Title: Unreal Engine - Hitboxes and Hurtboxes

> Reply from StijnDark ↑Tue Apr 26, 2022 4:43 am at Tue Apr 26, 2022 4:43 am
>
> 
hi,   

So i've been trying to mod unreal engine games for a while now and i know how to do some basic stuff. 
Something i don't know yet but i really want to know about and figure out how it works are the hitboxes and hurtboxes (or collisions whatever you prefer naming it). I don't know where to find it. Could i find it in the blueprint file of an object or model? Or is it somewhere at a completely different location? I have been trying for a while, but i see no result and i'm still here with the same knowledge as at the moment i started trying. 

Hopefully someone can help me out here.

Collisions are held within the static mesh or skeletal mesh.
If its an animation then a hitbox may be custom to specific frames of the animation.
