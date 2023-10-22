## Post #1
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-04-29T15:50:49+00:00
- Post Title: [LB DAT] A simple file but I can't find size & zsize values.

Hi, guys. I have some problems that I can't find a SIZE and ZSIZE values.



K-33.png (61.22 KiB) Viewed 70 times



```
get unknown1 short => I mean 1A 00
get unknown2 short => I mean 64 00 00 00
get null long
for i = 0 < files
get offset long
next i
```


This file contains 54 files and there are 55 offset values. The end of file offset is 2D AE 17 00. What's wrong with my bms script..?

*All of the files contain LB DAT and 1A 00. But unknown2 is different from files.
ex) 00 02 00 00 or 58 02 00 00 or 00 04 00 00
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-04-29T20:05:07+00:00
- Post Title: [LB DAT] A simple file but I can't find size & zsize values.

There's no file sample but I think unknown 2 is headerSize.
size and zsize could be first two ints of start of each file and I think the first int should be 'and' (&) with 0xFFFFFF.
## Post #3
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-04-29T22:23:59+00:00
- Post Title: [LB DAT] A simple file but I can't find size & zsize values.

> Reply from deepshit
>
> There's no file sample but I think unknown 2 is headerSize.
size and zsize could be first two ints of start of each file and I think the first int should be 'and' (&) with 0xFFFFFF.

Ok. Here are sample files.
[https://www.mediafire.com/?1xtlq0jen96t0gm](https://www.mediafire.com/?1xtlq0jen96t0gm)
## Post #4
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-01T09:42:54+00:00
- Post Title: [LB DAT] A simple file but I can't find size & zsize values.

> Reply from deepshit
>
> There's no file sample but I think unknown 2 is headerSize.
size and zsize could be first two ints of start of each file and I think the first int should be 'and' (&) with 0xFFFFFF.

You mean like this..? But as you know it doesn't work.

```
get ZSIZE long
get HEADERS long
get null long

for i = 0 < files
get offset long
log offset ZSIZE SIZE 0xFFFFFF
next i
```


*Additional information for example scenario.dat

                scenario.dat
1st Offset	14 08 00 00
2nd Offset	50 44 00 00	=> 4450-0814=3C3C	(packed size) => Actual size A130 (unpacked size) 001.dat
3rd Offset	A0 61 00 00	=> 61A0-4450=1D50	(packed size) => Actual size 429B (unpacked size) 002.dat
4rd Offset	11 A0 00 00	=> A011-61A0=3E71	(packed size) => Actual size 8BD7 (unpacked size) 003.dat
