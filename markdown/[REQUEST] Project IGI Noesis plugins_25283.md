## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-04-22T14:27:22+00:00
- Post Title: [REQUEST] Project IGI Noesis plugins

[https://mega.nz/folder/kDghTZSJ#DncmjWqkSMTMpzwobP8M2w](https://mega.nz/folder/kDghTZSJ#DncmjWqkSMTMpzwobP8M2w)
[https://mega.nz/folder/4LIV1BZB#W1PW-pszyIsa3yoa7ni3MQ](https://mega.nz/folder/4LIV1BZB#W1PW-pszyIsa3yoa7ni3MQ)

I tried this simple Noesis plugin, but it fails to load:

I also tried this character model (000_01_01.mef), but it seems distorted due to animations:


Now, I'm requesting proper Project IGI 1/2 Noesis plugins import all models.
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-22T16:01:03+00:00
- Post Title: [REQUEST] Project IGI Noesis plugins

> Reply from mrmaller1905 ↑Fri Apr 22, 2022 10:27 pm at Fri Apr 22, 2022 10:27 pm
>
> 
I tried this simple Noesis plugin
if you're talking about this ["plugin"](https://forum.xentax.com/viewtopic.php?f=16&t=7165&hilit=Project+IGI#p58244). This is not a python script. this is just a draft, "pseudocode".
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-22T20:07:55+00:00
- Post Title: [REQUEST] Project IGI Noesis plugins

> Reply from mrmaller1905 ↑Fri Apr 22, 2022 10:27 pm at Fri Apr 22, 2022 10:27 pm
>
> 
Project IGI 1/2 Noesis plugins import all models.
took a quick look at the models. made a plugin for noesis. the model contains 2 meshes 2nd is a collision. Some do not, such as weapons.

(maybe I'll finish it later) 
[fmt_mef.zip](https://xentaxbackup.github.io/file/22125_fmt_mef.zip)
## Post #4
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-05-13T20:47:01+00:00
- Post Title: [REQUEST] Project IGI Noesis plugins

Can someone update the Noesis plugin so it can fix twisted character models please?
## Post #5
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-08-15T17:54:38+00:00
- Post Title: [REQUEST] Project IGI Noesis plugins

I'm still trying to find a way to fix character models from IGI-2: Covert Strike

*.IFF (animations): [https://mega.nz/file/5bpl1L6Q#kZecraTtV ... XdbRnGCRFc](https://mega.nz/file/5bpl1L6Q#kZecraTtV5YLWWIZaHw7gXTZshZIy4sMnXdbRnGCRFc)
[https://mega.nz/file/hSpTxYKC#eXk-p9UET ... zLcfrAMM4c](https://mega.nz/file/hSpTxYKC#eXk-p9UETM0aj-IdDB_3LaARIvKuH6zvMzLcfrAMM4c)
[bandicam 2022-08-15 10-51-26-619.jpg](https://xentaxbackup.github.io/file/22650_bandicam 2022-08-15 10-51-26-619.jpg)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-15T18:31:53+00:00
- Post Title: [REQUEST] Project IGI Noesis plugins

Dunno which model you used so I took a different one:
.



431_02_1-mef.jpg (169.95 KiB) Viewed 110 times



btw: you should have mentioned that there is a thread already which handles IG2 .mef files:
(... upps, seems those threads were merged instantly...  )
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-15T20:16:21+00:00
- Post Title: [REQUEST] Project IGI Noesis plugins

As another quick hack (tested with 3 models only, so don't blame me):
.


 Make_H2O_IGI2_mef.zip
(82.88 KiB) Downloaded 11 times


Covers one submesh only!

Expects the face indices block to start with 000001000200. If that condition isn't met -> break, no H2O file being created.

> Reply from mrmaller1905 ↑Tue Aug 16, 2022 1:54 am at Tue Aug 16, 2022 1:54 am
>
> 
I'm still trying to find a way to fix character models from IGI-2: Covert StrikeCharacters are clumped. Will need a special treatment. Maybe some offset position to be searched for?

btw: uvpos=32 (for FVFsize 40) is wrong; correct it to 24
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-16T21:40:39+00:00
- Post Title: [REQUEST] Project IGI Noesis plugins

Could be helpful to separate the parts:
.



bad_sc_1_separate.jpg (48.79 KiB) Viewed 65 times
