## Post #1
- Username: harky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 05, 2018 5:58 am
- Post datetime: 2019-11-17T23:25:56+00:00
- Post Title: Elsword files

In elsword it is possible to find some animations in .x but there are also mostly files described as motions, which cannot be opened in programs normally but it is possible to find references to textures and bones, models by hxd, the information I have is that these files are encrypted, I wonder if anyone could extract these animations or decrypt these files

Motion_Lu.x = Encrypted? or just one compressed archive 
Motion_Lu_Emotion_Bonny.X = Normal motion file with animation


[https://www.mediafire.com/file/bm2r59z0 ... u.rar/file](https://www.mediafire.com/file/bm2r59z0q8ene7n/Motion_Lu.rar/file)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-18T00:09:15+00:00
- Post Title: Elsword files

The second file on the list is just one compressed file - you can use this QuickBMS script to decompress it:

Comtype MSZIP

GetDString FILENAME 0x10
Get SIZE Long
Set OFFSET Long 0x14
Get ZSIZE asize
Math ZSIZE - 0x14

CLog FILENAME OFFSET ZSIZE SIZE
## Post #3
- Username: harky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 05, 2018 5:58 am
- Post datetime: 2019-11-18T01:04:30+00:00
- Post Title: Elsword files

I was wrong when writing the topic I inverted what is encrypted and what is not the "Motion_Lu_Emotion_Bonny.X" 
works normally
## Post #4
- Username: kunmajuck
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 09, 2019 4:14 pm
- Post datetime: 2019-12-11T06:39:29+00:00
- Post Title: Elsword files

i have a probel like you, but i cant not fix this (
