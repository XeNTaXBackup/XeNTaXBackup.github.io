## Post #1
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-10T19:11:53+00:00
- Post Title: Gamebryo File Format Version 20.6.0.0

game:Ragnarok Online 2
[http://store.steampowered.com/app/231060/](http://store.steampowered.com/app/231060/)
Hello everyone, this is the format of the Gamebryo engine, Gamebryo File Format Version 20.6.0.0 did not import tools, hope someone can write a good import tool, below is the games unzip tool (Forum download tools) with the sample file link：[https://onedrive.live.com/redir?resid=6 ... 1236%21142](https://onedrive.live.com/redir?resid=6A28B826BE5F1236%21142)
[BaiduShurufa_2014-11-11_2-57-57.png](https://xentaxbackup.github.io/file/8062_BaiduShurufa_2014-11-11_2-57-57.png)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-10T19:34:33+00:00
- Post Title: Gamebryo File Format Version 20.6.0.0

Did you try noesis
## Post #3
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-11T09:56:26+00:00
- Post Title: Gamebryo File Format Version 20.6.0.0

> Reply from chrrox
>
> Did you try noesis
Hello, my friend, you are right, I really too stupid to actually ignore the Noesis of this great tool
[BaiduShurufa_2014-11-11_17-55-24.png](https://xentaxbackup.github.io/file/8063_BaiduShurufa_2014-11-11_17-55-24.png)
## Post #4
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-11-13T17:05:24+00:00
- Post Title: Gamebryo File Format Version 20.6.0.0

Any way to get animation in 3d editor ?
Noesis plugin not support NiBSplineCompTransformEvaluator / NiBSplineData / NiBSplineBasisData in .kf files
## Post #5
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-13T18:42:07+00:00
- Post Title: Gamebryo File Format Version 20.6.0.0

> Reply from deltaone
>
> Any way to get animation in 3d editor ?
Noesis plugin not support NiBSplineCompTransformEvaluator / NiBSplineData / NiBSplineBasisData in .kf files
Hello, my friend, Noesis is supports animations, you can first select KF file, it will let you choose the correct NIF file so you can import animation
## Post #6
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-11-13T19:21:35+00:00
- Post Title: Gamebryo File Format Version 20.6.0.0

> Reply from raykingnihong
>
> deltaone wrote:Any way to get animation in 3d editor ?
Noesis plugin not support NiBSplineCompTransformEvaluator / NiBSplineData / NiBSplineBasisData in .kf files 
Hello, my friend, Noesis is supports animations, you can first select KF file, it will let you choose the correct NIF file so you can import animation

```
NiSequenceData NiTransformEvaluator  NiTransformData  NiConstTransformEvaluator   NiTextKeyExtraData  

```

ACTOR\Monster\Abrahim\Abrahim_NORMAL_DOWN_01.kf
Loading ok ...


```
NiSequenceData NiTransformEvaluator NiBSplineCompTransformEvaluator NiBSplineData NiBSplineBasisData NiTextKeyExtraData 

```

ACTOR\Monster\Abrahim\Abrahim_BATTLE_CRITICALHIT_01.kf 
Result - bad animation ...
## Post #7
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-14T05:44:16+00:00
- Post Title: Gamebryo File Format Version 20.6.0.0

> Reply from deltaone
>
> raykingnihong wrote:deltaone wrote:Any way to get animation in 3d editor ?
Noesis plugin not support NiBSplineCompTransformEvaluator / NiBSplineData / NiBSplineBasisData in .kf files 
Hello, my friend, Noesis is supports animations, you can first select KF file, it will let you choose the correct NIF file so you can import animation
Code: Select allGamebryo File Format, Version 20.6.0.0
NiSequenceData NiTransformEvaluator  NiTransformData  NiConstTransformEvaluator   NiTextKeyExtraData  

ACTOR\Monster\Abrahim\Abrahim_NORMAL_DOWN_01.kf
Loading ok ...

Code: Select allGamebryo File Format, Version 20.6.0.0
NiSequenceData NiTransformEvaluator NiBSplineCompTransformEvaluator NiBSplineData NiBSplineBasisData NiTextKeyExtraData 

ACTOR\Monster\Abrahim\Abrahim_BATTLE_CRITICALHIT_01.kf 
Result - bad animation ...
I'm sorry, this method is not suitable for all models, I was just a test, so I didn't test all KF files
