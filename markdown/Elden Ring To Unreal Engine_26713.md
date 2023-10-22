## Post #1
- Username: Dhieen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 29, 2023 10:48 pm
- Post datetime: 2023-04-29T18:16:55+00:00
- Post Title: Elden Ring To Unreal Engine

Hello, so I followed a udemy tutorial on how to make a soulslike combat system ( [https://www.udemy.com/course/unreal-eng ... ke-combat/](https://www.udemy.com/course/unreal-engine-5-soulslike-combat/) )
And I wanted to add some elden ring animations to this, by replacing the base player character, I succeeded by importing a custom skeleton, with ds anim studio, havok max, f4ak, noesis, blender, to unreal. But I can't retarget those animations to any unreal character, i tried alot of different things for that, my main issue is the skeleton, first its inverted, its left handed instead of right handed and i didnt find any solution to fix that. Then there is the parenting of the bones that is weird





So to fix that I parented my armature to an empty in blender that i scaled X -1 and its working, but I have some problems, because of that i cant retarget to an unreal character, and I have trouble doing root motion animation with an empty

Any idea how i can scale x -1 my skeleton and applying the transforms without any problem ? I have alot of animations on the skeleton already

And is there someone here doing the same thing as me and found a solution? I saw some videos on youtube of people putting elden ring/ dark souls in unreal engine and made it working!
