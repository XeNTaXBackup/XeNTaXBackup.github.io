## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2015-10-24T04:41:43+00:00
- Post Title: Someone can find face indices for Wolfenstein BSP maps?(PS2)

Hello 

I'm trying to export some supposed bsp maps from return to castle wolfenstein (ps2 or xbox) to obj. For this task I'm using memory dumps. 

I analized the data with HEX2OBJ and I can obtain point clouds.





I checked the supposed maps with a hexadecimal tool and I can see something similar to face indices in file, but not fit in hex2obj

the images above are from the ps2 versions. This version is more easy to export I suppose, because is composed by a single large chunk of vertex or three at least in comparison of the xbox version, where the file model is divided in multiple little chunks.

maybe someone know more about BSP structure and can help me

here are some examples

[http://www.mediafire.com/download/hdur8 ... CW-BSP.rar](http://www.mediafire.com/download/hdur892l6flca6l/RTCW-BSP.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-24T19:24:48+00:00
- Post Title: Someone can find face indices for Wolfenstein BSP maps?(PS2)

as you may know getting faceindices can become a boring task  
So from the following list (skipping each 3rd DWord) you can see that
it's not very likely to contain faceindices:

6C 00 00 00  4B 00 00 00  D8 4A 88 01  
6D 00 00 00  4B 00 00 00  E8 4C 88 01  
6E 00 00 00  4C 00 00 00  CC 4D 88 01  
6F 00 00 00  4C 00 00 00  00 00 00 00  
70 00 00 00  4C 00 00 00  6C 4D 88 01  
71 00 00 00  4C 00 00 00  9C 4D 88 01  
72 00 00 00  4D 00 00 00  08 4E 88 01  
73 00 00 00  4D 00 00 00  D8 4D 88 01  
74 00 00 00  4E 00 00 00  FC 4D 88 01  
75 00 00 00  4E 00 00 00  14 4E 88 01  
76 00 00 00  4E 00 00 00  38 4E 88 01  
77 00 00 00  4F 00 00 00  00 00 00 00  
78 00 00 00  4F 00 00 00  2C 4E 88 01  
79 00 00 00  4F 00 00 00  5C 4E 88 01  
7A 00 00 00  4F 00 00 00  20 4E 88 01  
7B 00 00 00  52 00 00 00  60 4D 88 01  
7C 00 00 00  52 00 00 00  00 00 00 00  
7D 00 00 00  52 00 00 00  B8 4C 88 01  
7E 00 00 00  52 00 00 00  18 4D 88 01  
7F 00 00 00  52 00 00 00  D0 4C 88 01  
80 00 00 00  54 00 00 00  00 00 00 00  
81 00 00 00  54 00 00 00  00 00 00 00  
82 00 00 00  54 00 00 00  00 00 00 00  
83 00 00 00  54 00 00 00  00 00 00 00  
84 00 00 00  54 00 00 00  00 00 00 00  
85 00 00 00  54 00 00 00  00 00 00 00  
[..]
10 01 00 00  B5 00 00 00  00 00 00 00  
11 01 00 00  B5 00 00 00  B0 54 88 01  
12 01 00 00  B5 00 00 00  58 55 88 01  
13 01 00 00  B5 00 00 00  28 55 88 01  
14 01 00 00  B5 00 00 00  04 55 88 01  
15 01 00 00  B6 00 00 00  94 55 88 01  
16 01 00 00  B6 00 00 00  64 55 88 01  
17 01 00 00  B6 00 00 00  B8 55 88 01  
18 01 00 00  CC 00 00 00  A8 53 88 01  
19 01 00 00  CC 00 00 00  20 54 88 01  
1A 01 00 00  CC 00 00 00  30 53 88 01  
1B 01 00 00  CC 00 00 00  C0 53 88 01  
1C 01 00 00  D3 00 00 00  00 00 00 00  
1D 01 00 00  D3 00 00 00  9C 53 88 01  
1E 01 00 00  D3 00 00 00  B4 53 88 01  
1F 01 00 00  D3 00 00 00  00 56 88 01  
20 01 00 00  D6 00 00 00  00 00 00 00  
21 01 00 00  D6 00 00 00  4C 55 88 01  
22 01 00 00  D7 00 00 00  00 00 00 00  
23 01 00 00  D7 00 00 00  2C 54 88 01  
24 01 00 00  D7 00 00 00  FC 53 88 01  
25 01 00 00  D8 00 00 00  68 4E 88 01  
26 01 00 00  D8 00 00 00  00 00 00 00  
27 01 00 00  D8 00 00 00  00 00 00 00  
28 01 00 00  D8 00 00 00  B4 4D 88 01  
29 01 00 00  D8 00 00 00  00 00 00 00  
2A 01 00 00  D8 00 00 00  00 00 00 00  
2B 01 00 00  D8 00 00 00  00 00 00 00  
2C 01 00 00  D8 00 00 00  8C 4E 88 01  
2D 01 00 00  D9 00 00 00  00 00 00 00  
2E 01 00 00  D9 00 00 00  90 53 88 01  
2F 01 00 00  D9 00 00 00  24 56 88 01  
30 01 00 00  D9 00 00 00  F4 55 88 01  
31 01 00 00  D9 00 00 00  48 56 88 01  
32 01 00 00  DB 00 00 00  00 00 00 00  
33 01 00 00  DB 00 00 00  00 00 00 00  
34 01 00 00  DB 00 00 00  F0 56 88 01  
35 01 00 00  DB 00 00 00  00 00 00 00  
36 01 00 00  DB 00 00 00  30 56 88 01  
37 01 00 00  DB 00 00 00  14 57 88 01  
38 01 00 00  DE 00 00 00  C0 56 88 01  
39 01 00 00  DE 00 00 00  D8 56 88 01  
3A 01 00 00  DE 00 00 00  F4 4C 88 01  
3B 01 00 00  DE 00 00 00  00 00 00 00  
3C 01 00 00  DE 00 00 00  FC 56 88 01  
3D 01 00 00  DE 00 00 00  E4 53 88 01  

Trying linear FIs (f 1 2 3; f 4 5 6) looks funny but it's not correct, I guess:



PS2_ee1.JPG (72.26 KiB) Viewed 113 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-21T01:54:06+00:00
- Post Title: Someone can find face indices for Wolfenstein BSP maps?(PS2)

using tristripped face indices looks better but far from being nice:



TriStrippedFIs.JPG (103.95 KiB) Viewed 93 times
## Post #4
- Username: Caesar007
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 25, 2016 12:51 am
- Post datetime: 2016-05-05T16:53:32+00:00
- Post Title: Someone can find face indices for Wolfenstein BSP maps?(PS2)

any possible help in better understanding structure of container is appreciate.

research for almost completely disassembling cachemap container [here](http://wolfmap.ru/forum/viewtopic.php?f=123&t=2520&p=39256)
## Post #5
- Username: Eugeny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 03, 2015 11:55 pm
- Post datetime: 2017-07-24T13:23:55+00:00
- Post Title: Someone can find face indices for Wolfenstein BSP maps?(PS2)

Please help with formats
