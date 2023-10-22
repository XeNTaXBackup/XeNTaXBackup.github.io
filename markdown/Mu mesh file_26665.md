## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-17T02:59:09+00:00
- Post Title: Mu mesh file

Hello I was trying to get the model inside this file, I have used the start vertices (1280) and start face indices (7A64) in hex2obj, but still not getting any viable mesh, and still cannot identify nothing about uv  , any help gonna be awesome! thank you for read and your time!
[https://www.mediafire.com/file/fh3hxe0a ... 00.37/file](https://www.mediafire.com/file/fh3hxe0ay39dvf6/00000000.37/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-17T13:19:07+00:00
- Post Title: Mu mesh file

I wouldn't say it's a simple format but after years
I'd say you'll need something that is called a "plan".  

I.e. starting with a point cloud, for example.

I'll leave you alone with this H2O file which reveals some shape:

0x7A68 2467
Vb1
32 99
0x127F 625
021000
0x0 255

Start address of face indices maybe wrong, uvs not set, and so on. Good luck.  
(resulting mesh will look better than the shown one because of some last parameter changes)
.



mu mesh.png (82.37 KiB) Viewed 135 times
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-17T18:53:40+00:00
- Post Title: Mu mesh file

> Reply from shakotay2 ↑Mon Apr 17, 2023 9:19 pm at Mon Apr 17, 2023 9:19 pm
>
> 
0x7A68 2467
Vb1
32 99
0x127F 625
021000
0x0 255

OH it was! (0x127F) I missed that "6" lol, and about the start address of face indices is  (7A64), surprisely I was correct   

0x7A64 2469
UV 32 --- ?
0x127F 2467

Well uv is always a pain for me   , any advice shakotay2?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-17T19:16:11+00:00
- Post Title: Mu mesh file

> Reply from moonpaladin ↑Tue Apr 18, 2023 2:53 am at Tue Apr 18, 2023 2:53 am
>
> ..., and about the start address of face indices is  (7A64), surprisely I was correctSeriously, you were not!   I don't say that 07A68 is correct but 0x7A64 is simply wrong. Look at the resulting test.obj then:
...
v 1.420595 0.056065 2.946092 
v -9223374235878031400.000000 0.000000 -0.000000 
...

> Well uv is always a pain for me   , any advice shakotay2?I have no idea here. After 0x60A0 a "number/weight" table seems to follow, something like this.
 (Well, some number is 343, so no bone numbers.   )

Obviously there's enough floats in that table for uvs. Be creative to arrange them - I don't have the time for it.
## Post #5
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-17T20:20:47+00:00
- Post Title: Mu mesh file

Hi, I think I found UVs, so it is something like this:
0x127B Vertices count(71 02 00 00)=271 Hex=625 Dec
0x127F Vertices address

For UVs just add 12 to vertAdd

Faces:
0x7A66 Faces count(A2 09 00 00)=92A Hex=2466 Dec
0x7A6A Faces address

The mesh looks weird because there are a lot of extra polygons, so you need to delete those maually(I don't know other way, lol.):



test_1.jpg (126.23 KiB) Viewed 104 times
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-17T21:18:19+00:00
- Post Title: Mu mesh file

> Reply from shakotay2 ↑Tue Apr 18, 2023 3:16 am at Tue Apr 18, 2023 3:16 am
>
> 
 Look at the resulting test.obj then:
Oh :'( , I though I was correct, because it looked like this 


Thanks Shakotay, I will check the model again and again
## Post #7
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-17T21:21:28+00:00
- Post Title: Mu mesh file

> Reply from roocker666 ↑Tue Apr 18, 2023 4:20 am at Tue Apr 18, 2023 4:20 am
>
> 
Hi, I think I found UVs, so it is something like this:
0x127B Vertices count(71 02 00 00)=271 Hex=625 Dec
0x127F Vertices address

For UVs just add 12 to vertAdd
Thanks rocker666! gonna take a look at the valuees!! 

> Reply from roocker666 ↑Tue Apr 18, 2023 4:20 am at Tue Apr 18, 2023 4:20 am
>
> 
The mesh looks weird because there are a lot of extra polygons, so you need to delete those maually(I don't know other way, lol.):
hahaha there should be some value that is causing it, but is taking the form!!   , Thank you
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-17T22:38:33+00:00
- Post Title: Mu mesh file

> Reply from roocker666 ↑Tue Apr 18, 2023 4:20 am at Tue Apr 18, 2023 4:20 am
>
> 
Hi, I think I found UVs, so it is something like this:
...
For UVs just add 12 to vertAddyeah, cool. (That's FVFsize/UVpos 32 12 in hex2obj, btw)

> 0x7A6A Faces addressThat did the trick with the uvs. I can't believe that 0x7A68 could have such an impact on uvs (making them "unvisible" in hex2obj) edit: hmm, strange, recheckt with 0x7A68 and I should have seem them ->growing older, but not wiser...
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-18T00:04:34+00:00
- Post Title: Mu mesh file

> Reply from shakotay2 ↑Tue Apr 18, 2023 6:38 am at Tue Apr 18, 2023 6:38 am
>
> 
(That's FVFsize/UVpos 32 12 in hex2obj, btw)
Thanks it worked!

> Reply from shakotay2 ↑Tue Apr 18, 2023 6:38 am at Tue Apr 18, 2023 6:38 am
>
> 
That did the trick with the uvs. I can't believe that 0x7A68 could have such an impact on uvs (making them "unvisible" in hex2obj) edit: hmm, strange, recheckt with 0x7A68 and I should have seem them ->growing older, but not wiser...
I tried with this one, and got the mesh with the uv , Thank yoou!
0x7A64 2469
UV 32 12
0x127F 2467
