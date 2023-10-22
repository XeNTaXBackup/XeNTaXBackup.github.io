## Post #1
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2023-03-07T15:21:46+00:00
- Post Title: Clock Tower 3 files

Hi, it's been some time now, but someone made a bms script to extract the main archive of the PS2 game 
Clock Tower 3

and i've been wondering if anyone had tried to look into the files in it ?



AL.png (12.64 KiB) Viewed 116 times



here's some samples, if it helps
[https://www.mediafire.com/file/jneiulv3 ... s.zip/file](https://www.mediafire.com/file/jneiulv30qlj5t7/samples.zip/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-07T19:37:54+00:00
- Post Title: Clock Tower 3 files

Aly2, not that thrilling:
.



point_cloud_Aly2.png (13.65 KiB) Viewed 107 times
## Post #3
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2023-03-07T19:58:21+00:00
- Post Title: Clock Tower 3 files

> Reply from shakotay2 ↑Wed Mar 08, 2023 3:37 am at Wed Mar 08, 2023 3:37 am
>
> 
Aly2, not that thrilling:
.
point_cloud_Aly2.png

hm, maybe i forgot to provide additional files with it ?

well if it helps, heres the BMS
[http://aluigi.org/bms/clocktower3.bms](http://aluigi.org/bms/clocktower3.bms)
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-08T22:07:07+00:00
- Post Title: Clock Tower 3 files

quickly looked at the files, made a plugin that opens a cloud of points and uv points
*(all meshes in a heap)

auto triangular stripe does not give good results, you need to look for something related to faces (maybe this is a data block after the vertices)

also some textures


**(this is not a simple format, I think you should use rippers)
***(oh yes, if there is a conflict of plugins, I advise you to change the file extension for example to "BIN2")
[fmt_BIN2.zip](https://xentaxbackup.github.io/file/23528_fmt_BIN2.zip)
## Post #5
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2023-03-12T01:48:39+00:00
- Post Title: Clock Tower 3 files

> Reply from Durik256 ↑Thu Mar 09, 2023 6:07 am at Thu Mar 09, 2023 6:07 am
>
> 
quickly looked at the files, made a plugin that opens a cloud of points and uv points
*(all meshes in a heap)

auto triangular stripe does not give good results, you need to look for something related to faces (maybe this is a data block after the vertices)

also some textures


**(this is not a simple format, I think you should use rippers)
***(oh yes, if there is a conflict of plugins, I advise you to change the file extension for example to "BIN2")

Wow nice, thanks a lot for looking into it ! 
this is still a step forward and i'm glad it didn't just fade away because of a potential lack of interest in the game

as for rippers, sadly since its a ps2 game, it doesn't work, i even tried the old PCSX2 snap mode, and it didn't give good results
same for Ninja ripper...
