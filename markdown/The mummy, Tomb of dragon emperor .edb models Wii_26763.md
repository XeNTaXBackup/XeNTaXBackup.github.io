## Post #1
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-05-13T19:21:47+00:00
- Post Title: The mummy, Tomb of dragon emperor .edb models Wii

Hi, I tried to extract models from this game. Models have submeshes, I found vertices and UVs but I can't get faces, it seems like faces are grouped because bytes 00 98 xx xx appears several times(in same mesh) but I am nor really sure.. 

This is the first submesh in MR:


This is faces data(1st submesh):



Here is the sample if somebody wants to try:


 s_rck1.rar
(105 KiB) Downloaded 21 times



Thanks!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-05-14T14:09:32+00:00
- Post Title: The mummy, Tomb of dragon emperor .edb models Wii

yeah, the data is full of wrong faces:
...
f 313 568 568 
f 334 521 521 
f 321 562 562 
f 333 521 521 
f 321 535 535 
f 305 522 522 
f 322 535 535 
f 305 541 541 
f 324 536 536 
f 307 527 527 
f 325 537 537 
f 332 528 528 
f 326 533 533 
f 298 528 528 
f 326 566 566 
f 299 525 525 
f 327 566 566 
f 299 523 523 
f 328 547 547 
f 331 523 523 
...

I'd vote for a point cloud skinner:
.



s_rck1_Skinner.jpg (34.43 KiB) Viewed 123 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-30T19:28:00+00:00
- Post Title: The mummy, Tomb of dragon emperor .edb models Wii

Or you might try Eurochef tool from cohaereo, mentioned here:

> Reply from ColbyDash ↑Wed May 10, 2023 5:05 pm at Wed May 10, 2023 5:05 pm
>
> 
.



Eurochef, cohaereo.png (123.86 KiB) Viewed 78 times
## Post #4
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-09-01T06:36:44+00:00
- Post Title: The mummy, Tomb of dragon emperor .edb models Wii

> Reply from shakotay2 ↑Thu Aug 31, 2023 3:28 am at Thu Aug 31, 2023 3:28 am
>
> 
Or you might try Eurochef tool from cohaereo, mentioned here:
ColbyDash wrote: ↑Wed May 10, 2023 5:05 pm

Yeah, I remember that tool but at that time there where no releases :O

This game is not listed there but I am glad that it works, I will try to test the tool.

Thanks man!
