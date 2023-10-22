## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-24T18:39:08+00:00
- Post Title: Hyperdimension Neptunia Re;birth1 .tid

There are different pixel formats for .tid, but these should be similar to DDS?
Would be nice to apply to this


[face_c.zip](https://xentaxbackup.github.io/file/9777_face_c.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-24T22:22:47+00:00
- Post Title: Hyperdimension Neptunia Re;birth1 .tid

I used nr1_tidtool.exe to convert the tid file:



Neptunia_002_face.JPG (152.12 KiB) Viewed 289 times
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-25T02:45:12+00:00
- Post Title: Hyperdimension Neptunia Re;birth1 .tid

That will work for now. Still would like to know how the format is stored and how it's different from a regular DDS file.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-25T06:53:03+00:00
- Post Title: Hyperdimension Neptunia Re;birth1 .tid

convert face_c.png to a DXT1 dds file then compare it to face_c.tid
That's the way I would do it.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-17T23:58:27+00:00
- Post Title: Hyperdimension Neptunia Re;birth1 .tid

> Reply from finale00
>
> ... would like to know how the format is stored and how it's different from a regular DDS file.
the difference is your sample is morton swizzled, you can use this to unscramble the data array in Noesis  

```
texFmt = noesis.NOESISTEX_DXT1
```


and heres a script that only works with your sample


 face_c_tid.zip
(607 Bytes) Downloaded 39 times
## Post #6
- Username: deadrat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 16, 2017 3:20 pm
- Post datetime: 2017-02-16T08:35:03+00:00
- Post Title: Hyperdimension Neptunia Re;birth1 .tid

Hi guys. Please, help me. I have a Playstaytion3 games Mugen souls and Mugen souls Z . I`m extract all folders with TID-files. (This pictures, isn`t it? ) Please tell me how to format them to pictures? 

P.S
Guys from steamcommunity did it for Neptunia (PC). 
[https://steamcommunity.com/sharedfiles/ ... =409454600](https://steamcommunity.com/sharedfiles/filedetails/?id=409454600)
But this is not work for Mugen souls Z (PS3)

P.S. 2
I`m  found some soft for converting TID to DDS!!!
[http://crunchepillar.x10host.com/data/p ... -mugen.php](http://crunchepillar.x10host.com/data/project-pages/log-mugen.php)
but it`s give me strange pics
[7009.tid.png](https://xentaxbackup.github.io/file/12454_7009.tid.png)
