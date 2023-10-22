## Post #1
- Username: darkchaosblast
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 22, 2015 7:39 am
- Post datetime: 2015-07-28T16:30:19+00:00
- Post Title: PSX .VFS

I´m trying to mod a PSX game called "digimon rumble arena", There´s one archive called A.VFS that contains the sounds and the graphics of the game (supposedly TIM/SEQ/VAQ files) and I can´t open it after trying with many tools, If someone could decompile it I could continue my project

FILE: [https://mega.co.nz/#!MxUD2RiK!w6dlhqjUa ... t-Ut0Bpp5w](https://mega.co.nz/#!MxUD2RiK!w6dlhqjUaOf1XMK2Y9XowqFJdtTrMcqkot-Ut0Bpp5w)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-07-29T23:08:08+00:00
- Post Title: PSX .VFS

It's possible to extract stuff from this.
## Post #3
- Username: darkchaosblast
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 22, 2015 7:39 am
- Post datetime: 2015-07-30T17:31:59+00:00
- Post Title: PSX .VFS

Well, after some tries I could extract some of the files
It´s similar to Crash Team Racing BIGFILE.BIG, there are files but they haven´t got names because they are not supposed to be extracted.

I will try to recompile it by editing the file in a hex editor. I hope it works

PD: sorry for my bad english
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-07-30T21:47:52+00:00
- Post Title: PSX .VFS

No, there are names. There is a header section that is zlib compressed that contains all information about the resources in the archive.
## Post #5
- Username: darkchaosblast
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 22, 2015 7:39 am
- Post datetime: 2015-07-31T22:14:57+00:00
- Post Title: PSX .VFS

At what offsets that part of the header starts and end?,also how i could extract that information?
