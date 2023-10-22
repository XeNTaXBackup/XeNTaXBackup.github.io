## Post #1
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2021-04-27T23:18:37+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

Is Nickelodeon Kart Racers 2: Grand Prix for PC compatible with umodel? I want to rip out some other skins from this game.

Thanks,
## Post #2
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-10-24T19:33:45+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

no, it uses vector engine, the engine used for most vector unit games
## Post #3
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2021-10-26T20:51:00+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

Hi

What tool do I use to open the game file
## Post #4
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-10-27T16:20:24+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

you could use the quickbms script, but it will end up giving you .dat files
## Post #5
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2021-10-27T20:04:23+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

HI

What the best way to got right files ?

Thank
## Post #6
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-12-06T18:04:05+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

you can try ninjaripper
## Post #7
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-03-08T10:13:49+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

I found this
[](https://ibb.co/4MQNzKx)

Textures are .GNF just need cut out. 
[](https://imgbb.com/)

[](https://ibb.co/Lvr7gQG)

If anyone could make a script that would be appreciated.

SAMPLES
[https://drive.google.com/file/d/1QoQuCe ... sp=sharing](https://drive.google.com/file/d/1QoQuCeErR-EQpqHWzE1-Ja8Q_uoNzn5L/view?usp=sharing)
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-03-08T15:25:46+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

Bone don't look correct, but not the worst format ever:
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-08T17:24:32+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

> Reply from Sharppy ↑Tue Mar 08, 2022 6:13 pm at Tue Mar 08, 2022 6:13 pm
>
> 
If anyone could make a script that would be appreciated.
file contains 3 lods except (char_dannyOutline.dat)
all model have 49 unk bytes after matrix, only  (char_dannyOutline.dat) have 51 bytes.
to open it  replace line  34 (seek 51) inside "fmt_datNK_single.py"

in archive 2 plugins: 
 fmt_datNK_single.py - opens firts lod (one model)
 fmt_datNK_multi.py - opens three lods
[fmt_dat.zip](https://xentaxbackup.github.io/file/21908_fmt_dat.zip)
## Post #10
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-03-09T03:01:02+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

Thanks guys for finally unlocking this one. I would prefer the bones since maybe the animations are possible. Game seems rather simple of formats. Although it did break on stage/track data. Here is some samples to that if the script cant get that too that's another one down.   

[https://drive.google.com/file/d/1rQ8ZRv ... sp=sharing](https://drive.google.com/file/d/1rQ8ZRvNgyk4KzDYcDBWJSQkm_oTMfym4/view?usp=sharing)
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-09T13:43:04+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

> Reply from Sharppy ↑Wed Mar 09, 2022 11:01 am at Wed Mar 09, 2022 11:01 am
>
> 
Game seems rather simple of formats.
then I think it will not be difficult for you to change the script. 

> Reply from Sharppy ↑Wed Mar 09, 2022 11:01 am at Wed Mar 09, 2022 11:01 am
>
> 
I would prefer the bones since maybe the animations are possible.
bones are loaded you only need to transform the matrix. and read the weights.

> Reply from Sharppy ↑Wed Mar 09, 2022 11:01 am at Wed Mar 09, 2022 11:01 am
>
> 
Although it did break on stage/track data.
they don't have bones (you need to remove reading bones from the script)
(all the files don't have a header. did you unpack them?)
(they seem to be cut wrong)
[props_catdog_board.001.dat..png](https://xentaxbackup.github.io/file/21911_props_catdog_board.001.dat..png)
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-09T23:47:27+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

> Reply from Sharppy ↑Wed Mar 09, 2022 11:01 am at Wed Mar 09, 2022 11:01 am
>
> 
Game seems rather simple of formats.
looked again.
same problem with bones.
one plug-in for all models.
I think you need to solve the problem with unpacking, otherwise need to use "crutches".

(I won't do it anymore  )
[fmt_datNK.zip](https://xentaxbackup.github.io/file/21918_fmt_datNK.zip)
## Post #13
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-03-10T00:24:31+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

Thank you so much
## Post #14
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-03-10T21:25:33+00:00
- Post Title: Nickelodeon Kart Racers 2: Grand Prix for PC

Well im having an issue writing in "normals" could you please help in pulling them. 
[](https://ibb.co/SwGNCTM)



Edit***
I was able to write them them in using the 1st script  Thanks again for this.
[](https://ibb.co/QrPDzZh)
