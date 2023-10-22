## Post #1
- Username: Irnkman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 30, 2021 5:09 am
- Post datetime: 2022-02-20T20:39:01+00:00
- Post Title: King of Fighters XV

Models are accessible through Umodel but each character's animations are in an OTRA.uasset file that can't be utilized currently. Starting thread for discussion in case anyone makes any headway on this.
## Post #2
- Username: Cityhunter12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 21, 2021 7:31 am
- Post datetime: 2022-03-05T21:59:21+00:00
- Post Title: King of Fighters XV

> Reply from Irnkman ↑Mon Feb 21, 2022 4:39 am at Mon Feb 21, 2022 4:39 am
>
> 
Models are accessible through Umodel but each character's animations are in an OTRA.uasset file that can't be utilized currently. Starting thread for discussion in case anyone makes any headway on this.

I'm also investigating how to open the OTRA file which is something different.
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-11T20:11:32+00:00
- Post Title: King of Fighters XV

Here is fix for killercracker's [max script](https://forum.xentax.com/viewtopic.php?f=16&t=16439&start=30#p145359) ([download](https://drive.google.com/file/d/1wMwLJ43DHJj8aRabqXDzClX0rEdREXgb/view?usp=sharing)). I suppose animation format is still the same since KOF XIV, but it doesn't take into account UE4 specifics and mesh with bones are inverted when animation is applied (fixed in the updated script). It's the same with Samurai Shodown reboot. 
Script is accepting _OTRA.uexp files with animations, which should be extracted from game package first.




Clipboard03.jpg (84.93 KiB) Viewed 191 times
