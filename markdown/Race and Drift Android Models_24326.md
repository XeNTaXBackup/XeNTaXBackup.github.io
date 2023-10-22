## Post #1
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-06T19:00:11+00:00
- Post Title: Race and Drift Android Models

they are .s3d files, how do i convert them to .obj [https://www.mediafire.com/file/n3immsxe ... 8.s3d/file](https://www.mediafire.com/file/n3immsxecxf8z3z/road_28.s3d/file)
## Post #2
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-07T08:45:56+00:00
- Post Title: Race and Drift Android Models

i tried using gtarcade noesis plugin but instead it failed
## Post #3
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-07T08:47:28+00:00
- Post Title: Race and Drift Android Models

nvm the models are in .m3d but there's no noesis plugin for them [https://www.mediafire.com/file/c00jl98b ... 1.m3d/file](https://www.mediafire.com/file/c00jl98bl39r9o0/car1.m3d/file)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-08T07:37:21+00:00
- Post Title: Race and Drift Android Models

Using hex2obj (view link in my sig):
.



car1-m3d.png (67.76 KiB) Viewed 110 times
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-08-13T19:25:34+00:00
- Post Title: Race and Drift Android Models

shakotay2,

Could you test its texture file on the model?

I can't get it to work in my program.

[http://www.i3dconverter.com/media/CAR1.png ](http://www.i3dconverter.com/media/CAR1.png)



CAR1.png (41.79 KiB) Viewed 87 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-13T20:17:44+00:00
- Post Title: Race and Drift Android Models

yeah, my bad, uvs need to be scaled down (div 500 or so), y mirrored, then y scaled up by 3 (round about):
.



car1_tex.png (46.22 KiB) Viewed 81 times
## Post #7
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-13T21:00:08+00:00
- Post Title: Race and Drift Android Models

i wonder how did you get this part of the uv map correctly if you do the scaled down mapping and mirrored
[Zrzut ekranu 2021-08-13 225917.png](https://xentaxbackup.github.io/file/20612_Zrzut ekranu 2021-08-13 225917.png)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-13T21:17:09+00:00
- Post Title: Race and Drift Android Models

just start with "div 500" (= multiply with 0.002):
.



uvs_0.002.png (30.41 KiB) Viewed 71 times
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-08-14T18:59:18+00:00
- Post Title: Race and Drift Android Models

> Reply from shakotay2 ↑Sat Aug 14, 2021 4:17 am at Sat Aug 14, 2021 4:17 am
>
> 
yeah, my bad, uvs need to be scaled down (div 500 or so), y mirrored, then y scaled up by 3 (round about):

Thank you for your tip, I have never seen UV datas like this before.

I used the div 512. 
The texture file is 1024 x 288, so I have calculated the correct value: 1024/288=3.55



Race_and_Drift_m3d.jpg (138.61 KiB) Viewed 56 times
