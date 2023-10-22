## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-07T19:14:56+00:00
- Post Title: UVB for the body part :(

Hello, to everyone, maybe someone could help me with this problem, I'm trying to get the start of the UVB corresponding of the body part, the head is in 709B and the body should start in any part past that UVB of the head. There is another texture block but that correspond to the lod model, and I'm not interesting in it because is really low poly model.  I will post the model/texture and my current values on the hex2obj, I really want this working because I have been trying for a while. Thanks 

[https://www.mediafire.com/file/8m1sh288 ... dy.bm/file](https://www.mediafire.com/file/8m1sh2880n6h1qu/body.bm/file)

[https://www.mediafire.com/view/5yikpsv3 ... y.png/file](https://www.mediafire.com/view/5yikpsv39plo2ku/body.png/file)



values.png (24.72 KiB) Viewed 71 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-07T22:25:59+00:00
- Post Title: UVB for the body part :(

well, pointing you to 0x13A4C which I thought being the start of the bodies uv data was wrong, my bad.

> Reply from moonpaladin ↑Mon Mar 08, 2021 3:14 am at Mon Mar 08, 2021 3:14 am
>
> the head is in 709B and the body should start in any part past that UVB of the head. There is another texture block but that correspond to the lod model,
You have the solution, more or less, it's totally simple, maybe you'll find out for yourself how to calculate the suiting one.
Just use the end address of the head's uv block +1.
.



body-uvs.png (60.86 KiB) Viewed 63 times
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-07T22:47:57+00:00
- Post Title: UVB for the body part :(

> Reply from shakotay2 ↑Mon Mar 08, 2021 6:25 am at Mon Mar 08, 2021 6:25 am
>
> 
well, pointing you to 0x13A4C which I thought being the start of the bodies uv data was wrong, my bad.
moonpaladin wrote: ↑Mon Mar 08, 2021 3:14 amthe head is in 709B and the body should start in any part past that UVB of the head. There is another texture block but that correspond to the lod model,
You have the solution, more or less, it's totally simple, maybe you'll find out for yourself how to calculate the suiting one.
Just use the end address of the head's uv block +1.
.
body-uvs.png

Shakotay, Best as always, thanks
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-03-07T23:54:09+00:00
- Post Title: UVB for the body part :(

I've done a quick Noesis script to display the whole model.  No guarantee it'll work for other files (it might!), and I haven't got textures to test.


[fmt_bm.zip](https://xentaxbackup.github.io/file/19671_fmt_bm.zip)
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-08T01:39:50+00:00
- Post Title: UVB for the body part :(

> Reply from DKDave ↑Mon Mar 08, 2021 7:54 am at Mon Mar 08, 2021 7:54 am
>
> 
I've done a quick Noesis script to display the whole model.  No guarantee it'll work for other files (it might!), and I haven't got textures to test.

Thanks! Gonna check it !
