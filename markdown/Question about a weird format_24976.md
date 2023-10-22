## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-22T17:14:57+00:00
- Post Title: Question about a weird format

Hello, I was  looking some files that had in my drive, and found this one, I'm checking if it contain a 3d model or not, hope someone can take a look at it too , because Im not seeying the correct values    . Thanks for your time!

[https://www.mediafire.com/file/hazq41n4 ... u.out/file](https://www.mediafire.com/file/hazq41n408zdwms/mx_jiu.out/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-22T19:14:53+00:00
- Post Title: Question about a weird format

you don't even see a point cloud with 68 vertices?  
.



mx_jiu.png (4.21 KiB) Viewed 34 times
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-22T19:27:30+00:00
- Post Title: Question about a weird format

> Reply from shakotay2 ↑Sun Jan 23, 2022 3:14 am at Sun Jan 23, 2022 3:14 am
>
> 
you don't even see a point cloud with 68 vertices?

Honestly not xd
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-22T20:03:03+00:00
- Post Title: Question about a weird format

Try as a point cloud:
0x0 0
Vb1
16 99
0x4 68
020000
0x0 255

And there is a block of 392 x 2 floats at 0xEE8, maybe uvs but I don't think it's worth bothering, sorry.
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-22T20:20:20+00:00
- Post Title: Question about a weird format

> Reply from shakotay2 ↑Sun Jan 23, 2022 4:03 am at Sun Jan 23, 2022 4:03 am
>
> 
Try as a point cloud:
Thank you shakotay2, gonna review your values.
