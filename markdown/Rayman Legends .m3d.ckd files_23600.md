## Post #1
- Username: TheZoroark007
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 16, 2019 1:14 am
- Post datetime: 2021-03-17T10:57:15+00:00
- Post Title: Rayman Legends .m3d.ckd files

Hello everyone,

I tried to extract some models from Rayman Legends and while searching for a way, I came across a Blender script in this topic ([viewtopic.php?t=12526](https://forum.xentax.com/viewtopic.php?t=12526)) that works well with the Child of Light .m3d.ckd files but not with the Rayman Legends variation. 
Upon opening model files from both games in a Hex Editor, I found that the Rayman Legends file seems to have an inverted file structure compared to the Child of Light one: .

Would it be possible to adjust the Blender script to add compatibility for the Rayman Legends .m3d.ckd files ?
The two files used in the example are attached.
[Files.zip](https://xentaxbackup.github.io/file/19738_Files.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-17T12:18:08+00:00
- Post Title: Rayman Legends .m3d.ckd files

> Reply from TheZoroark007 ↑Wed Mar 17, 2021 6:57 pm at Wed Mar 17, 2021 6:57 pm
>
> 
Hello everyone,

...
Would it be possible to adjust the Blender script to add compatibility for the Rayman Legends .m3d.ckd files ?
Hello,
this would require you to identify the bone name hashes in the head.m3d.ckd to check whether the table has the same structure.

From the robe we get these bone name hashes:

('bone count', 21)
('bone name', -949761414)  at 0x9460
('bone name', 418993405)   at 0xA0D4
('bone name', 2022581127)
('bone name', 1780780598)
('bone name', -1252605364)
('bone name', -1346085783)
('bone name', 2045893134)
('bone name', 562865731)
('bone name', 1641867316)
('bone name', 1489805092)
('bone name', -2000141195)
('bone name', -546898160)
('bone name', 905046157)
('bone name', -735999227)
('bone name', 1271217864)
('bone name', 1582312523)
('bone name', 1270767479)
('bone name', 900358157)
('bone name', 1391125022)
('bone name', 941417325)
('bone name', 1501481675) at 0xD8A8
current offset is 55992

(If it's only about the mesh an analyzing of the head's data would make more sense, imho.)
## Post #3
- Username: TheZoroark007
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 16, 2019 1:14 am
- Post datetime: 2021-03-17T12:34:53+00:00
- Post Title: Rayman Legends .m3d.ckd files

Alright, thank you.

Since I really mostly just want to get the mesh of the head, what would be the best way to get that exported ?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-17T13:50:55+00:00
- Post Title: Rayman Legends .m3d.ckd files

Usually you would use one of the mesh-to-obj extractor tools here in the forum but for the Rayman L. ckd some scripting is required for getting correct faces:
.



head_ckd.png (154.5 KiB) Viewed 42 times
