## Post #1
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-18T17:29:59+00:00
- Post Title: Hex to 3D challenge

*old subject : PS2 Mahou Sensei Negima 3-Jikanme

Recently I'm studying to get a 3D model from Hex. I mainly focus only on the games I enjoyed. Now I'm verifying the PS2 Negima game.
The data was clearly more organized than the format I worked on before, and I thought it would be easier to get, but it didn't work. The vertices are probably getting close to the correct answer.
Regarding face, I think it is around 0x2B50, but I could only get corrupted data. I would appreciate it if someone could give me some advice.
[test.zip](https://xentaxbackup.github.io/file/21642_test.zip)
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-18T17:30:38+00:00
- Post Title: Hex to 3D challenge

Here are the results of the Point Cloud I got.
[negima.png](https://xentaxbackup.github.io/file/21643_negima.png)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-18T19:22:37+00:00
- Post Title: Hex to 3D challenge

hex2obj doesn't support DWORD stripped face indices, only word ones (16 bit).
Apart from this the DWORD ones don't seem to fit.

edit: well, just saw some other suspects - testing...

yay, ugly, but you may get the idea?
.



test.png (46.54 KiB) Viewed 135 times
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-18T20:44:29+00:00
- Post Title: Hex to 3D challenge

> Reply from shakotay2 ↑Wed Jan 19, 2022 3:22 am at Wed Jan 19, 2022 3:22 am
>
> 
yay, ugly, but you may get the idea?
mine is scarier 
[efwdvdsv.png](https://xentaxbackup.github.io/file/21648_efwdvdsv.png)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-18T20:49:30+00:00
- Post Title: Hex to 3D challenge

using triangle strips:
.



test.png (135.27 KiB) Viewed 132 times


Well, those extra faces, something must be wrong here:

f 1 22 2
f 22 1 2 < same face as before, other winding
f 2 1 16
f 1 6 16
f 16 6 15
f 6 7 15
f 15 7 18
f 7 5 18
f 18 5 20
f 5 267 20
f 20 267 21
f 267 24 21
f 21 24 22
f 24 1 22

f 22 1 2 < see above
f 1 16 2 < see above
f 2 16 19
f 16 29 19
f 19 29 14
f 29 9 14
f 14 9 34
f 9 37 34
f 34 37 5
f 37 27 5
f 5 27 3
f 27 23 3
f 3 23 2
f 23 22 2
f 2 22 1 < see above
...
## Post #6
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-22T06:32:12+00:00
- Post Title: Hex to 3D challenge

Thank you Durik256, shakotay2, for the research.
Give up on files that even advanced users do not get accurate results. In particular, Negima has another title that can be replaced with Wii, so you don't have to be particular about it.

I decided to try various things until I found a format that was as simple as possible, so I changed the title of the thread. I will learn little by little.

This time is PS2 Street Fighter EX3. The vertices are likely to be found relatively easily. As usual, it seems that lacks the ability to find faces and counts. Little by little, I've been able to discover face-like data from binaries, but I'm still lacking in ability. I would appreciate any advice.
[pl00.zip](https://xentaxbackup.github.io/file/21659_pl00.zip)
## Post #7
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-22T06:34:32+00:00
- Post Title: Hex to 3D challenge

This is the result I have obtained so far. The data starts with the face and then has the vertices. It seems that it is repeated for each part. The shape of the first part was difficult to understand, so I chose a relatively large length of data.
[sfex3.png](https://xentaxbackup.github.io/file/21660_sfex3.png)
