## Post #1
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-06-08T17:24:14+00:00
- Post Title: Mortal Kombat: Armageddon (.ssf)

Hello guys! I would like to know, is it possible to convert .ssf files to use them in 3ds max? If yes, can someone explain me how?
Thanks in advance!

Here's the file: [https://mega.co.nz/#!MQhSEbDC!Nq3X-_rTK ... gx0728gl_Y](https://mega.co.nz/#!MQhSEbDC!Nq3X-_rTKDvq0-v4TbbIMqcbquFzqMnu8gx0728gl_Y)

Thanks in advance.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-08T19:22:48+00:00
- Post Title: Mortal Kombat: Armageddon (.ssf)

you may read here: [http://wiki.xentax.com/index.php/Mortal ... ptions_SSF](http://wiki.xentax.com/index.php/Mortal_Kombat_Deceptions_SSF)

endian order is: big

13 files, archive size: 0x425000: 4345856 B.

```

00 00 00 01  00 00 08 00  00 0F 43 00  7C 80 1A 4F 
00 00 00 01  00 0F 50 00  00 0F 43 00  7C 80 1A 4F 
00 00 00 01  00 1E 98 00  00 06 26 00  7C 80 1A 4F 

00 00 00 02  00 24 C0 00  00 00 D8 40  7C 80 1A 4F 
00 00 00 02  00 25 A0 00  00 00 64 80  7C 80 1A 4F 
00 00 00 02  00 26 08 00  00 00 52 20  7C 80 1A 4F 
00 00 00 02  00 26 60 00  00 00 44 20  7C 80 1A 4F 
00 00 00 02  00 26 A8 00  00 00 8D C0  7C 80 1A 4F 
00 00 00 02  00 27 38 00  00 00 77 00  7C 80 1A 4F 

00 00 00 03  00 27 B0 00  00 01 91 00  7C 80 1A 4F 
00 00 00 03  00 29 48 00  00 0F 10 00  7C 80 1A 4F 
00 00 00 03  00 38 58 00  00 05 7D 00  7C 80 1A 4F 
00 00 00 03  00 3D D8 00  00 04 72 80  7C 80 1A 4F
```


dunno about conversion - well, maybe this one:



sektor_ssf.JPG (41.22 KiB) Viewed 201 times
## Post #3
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-06-08T19:51:00+00:00
- Post Title: Mortal Kombat: Armageddon (.ssf)

> Reply from shakotay2
>
> you may read here: http://wiki.xentax.com/index.php/Mortal ... ptions_SSF

endian order is: big

13 files, archive size: 0x425000: 4345856 B.
Code: Select allfile type     offset      lenght

00 00 00 01  00 00 08 00  00 0F 43 00  7C 80 1A 4F 
00 00 00 01  00 0F 50 00  00 0F 43 00  7C 80 1A 4F 
00 00 00 01  00 1E 98 00  00 06 26 00  7C 80 1A 4F 

00 00 00 02  00 24 C0 00  00 00 D8 40  7C 80 1A 4F 
00 00 00 02  00 25 A0 00  00 00 64 80  7C 80 1A 4F 
00 00 00 02  00 26 08 00  00 00 52 20  7C 80 1A 4F 
00 00 00 02  00 26 60 00  00 00 44 20  7C 80 1A 4F 
00 00 00 02  00 26 A8 00  00 00 8D C0  7C 80 1A 4F 
00 00 00 02  00 27 38 00  00 00 77 00  7C 80 1A 4F 

00 00 00 03  00 27 B0 00  00 01 91 00  7C 80 1A 4F 
00 00 00 03  00 29 48 00  00 0F 10 00  7C 80 1A 4F 
00 00 00 03  00 38 58 00  00 05 7D 00  7C 80 1A 4F 
00 00 00 03  00 3D D8 00  00 04 72 80  7C 80 1A 4F

dunno about conversion - well, maybe this one:
sektor_ssf.JPG

can i at least load models from archives in binding pose using MeshExtractor?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-08T20:10:53+00:00
- Post Title: Mortal Kombat: Armageddon (.ssf)

> Reply from pechenko121
>
> can i at least load models from archives in binding pose using MeshExtractor?From the pic in the above post I don't see a reason why not. (But I didn't check for uvs, weights, bones and so on.)
## Post #5
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2015-06-08T20:41:30+00:00
- Post Title: Mortal Kombat: Armageddon (.ssf)

> Reply from shakotay2
>
> pechenko121 wrote:can i at least load models from archives in binding pose using MeshExtractor?From the pic in the above post I don't see a reason why not. (But I didn't check for uvs, weights, bones and so on.)

Can you please explain me how to do that if it won't be hard for you  
I tried to use it before but was unlucky.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-08T20:45:17+00:00
- Post Title: Mortal Kombat: Armageddon (.ssf)

I suggest to press the 'tut' button of hex2obj, read the tutorial, understand the example.
