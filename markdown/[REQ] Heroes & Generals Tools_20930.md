## Post #1
- Username: ALIEN31ITA
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 15, 2017 11:59 pm
- Post datetime: 2019-08-08T19:55:37+00:00
- Post Title: [REQ] Heroes & Generals Tools?

Hello, i know this may sound requested already long time ago... but... is there an actual tool that simplifies the work of ripping those Meshes?

About the textures someone said to use Crunch and works... but about meshes?

Convert Multiple .crn Batch
Create a bat file with those strings, and drag a .crn on it (You need to download crunch from github, in bin folder)

```
title Command Repeating Batch File
for %%a in (*.crn) do "crunch.exe" "%%a"
pause

```

Or Use Noesis

This seems a little bit hard for meshes... there should be an easy workaround
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-09T08:24:07+00:00
- Post Title: [REQ] Heroes & Generals Tools?

> Reply from ALIEN31ITA ↑Fri Aug 09, 2019 3:55 am at Fri Aug 09, 2019 3:55 am
>
> This seems a little bit hard for meshes... there should be an easy workaroundGuess, there is. Looking at the start of a .dat reveals the block sizes:



HeroesAndGenerals-block_sizes.png (7.73 KiB) Viewed 167 times


0x16: 61f80 size vertex block: 16720 x 24, dec. 
0x1A: 149BE size FI block: 42207 x 2, dec.
An FVF size of 24 and a vertex start address of 0x1E assumed you could easily create some script/batch.
(But I'm not sure whether 24 and 0x1E apply to all .dat files!)

(I'm not very interested in military games - otherwise I'd included H&G .dat  into the Make_obj project.)
## Post #3
- Username: ALIEN31ITA
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 15, 2017 11:59 pm
- Post datetime: 2019-08-16T16:32:05+00:00
- Post Title: [REQ] Heroes & Generals Tools?

> Reply from shakotay2 ↑Fri Aug 09, 2019 4:24 pm at Fri Aug 09, 2019 4:24 pm
>
> 
ALIEN31ITA wrote: ↑Fri Aug 09, 2019 3:55 amThis seems a little bit hard for meshes... there should be an easy workaround
Guess, there is. Looking at the start of a .dat reveals the block sizes:
HeroesAndGenerals-block_sizes.png
0x16: 61f80 size vertex block: 16720 x 24, dec. 
0x1A: 149BE size FI block: 42207 x 2, dec.
An FVF size of 24 and a vertex start address of 0x1E assumed you could easily create some script/batch.
(But I'm not sure whether 24 and 0x1E apply to all .dat files!)

(I'm not very interested in military games - otherwise I'd included H&G .dat  into the Make_obj project.)

But wait for get the Dat files i have to use wich kind of script? and also about your project sounds a good idea, but honestly i gotta say this, i'm not really a scripter, i'm just a modeller/porter... so yeah never worked on those things... but one day i will
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-16T19:00:51+00:00
- Post Title: [REQ] Heroes & Generals Tools?

> Reply from ALIEN31ITA ↑Sat Aug 17, 2019 12:32 am at Sat Aug 17, 2019 12:32 am
>
> But wait for get the Dat files i have to use wich kind of script?
> Reply from ALIEN31ITA ↑Mon Aug 28, 2017 3:37 am at Mon Aug 28, 2017 3:37 am
>
> 
(2 years later...  )
## Post #5
- Username: ALIEN31ITA
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 15, 2017 11:59 pm
- Post datetime: 2019-08-16T19:34:54+00:00
- Post Title: [REQ] Heroes & Generals Tools?

> Reply from shakotay2 ↑Sat Aug 17, 2019 3:00 am at Sat Aug 17, 2019 3:00 am
>
> 
ALIEN31ITA wrote: ↑Sat Aug 17, 2019 12:32 amBut wait for get the Dat files i have to use wich kind of script?ALIEN31ITA wrote: ↑Mon Aug 28, 2017 3:37 am
(2 years later...  )
Eh i forgot about that... welp, Ehehe
## Post #6
- Username: ALIEN31ITA
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 15, 2017 11:59 pm
- Post datetime: 2019-08-22T14:10:16+00:00
- Post Title: [REQ] Heroes & Generals Tools?

Can someone, well guide me? it's kinda a confusing process... honestly i never worked with Hex editing... like sending an example... (Specialy with the Vehicle meshes)
