## Post #1
- Username: xmotoracer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 01, 2022 10:18 pm
- Post datetime: 2023-07-09T08:04:10+00:00
- Post Title: extract models

Hi
can anyone take a look at these files and see if they can get 3d models & textures from them ?

thanks


[https://mega.nz/file/tclmTLyT#kAZ-g0NHB ... fAsqYFJX_Q](https://mega.nz/file/tclmTLyT#kAZ-g0NHB0hwcgCxxDGGBlUtt4hIi31YEfAsqYFJX_Q)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-09T10:50:33+00:00
- Post Title: extract models

btd seems to contain a track:
.



Daytona0-bdt.png (18.53 KiB) Viewed 261 times
## Post #3
- Username: xmotoracer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 01, 2022 10:18 pm
- Post datetime: 2023-07-09T11:06:53+00:00
- Post Title: extract models

thanks.....

can you see what the .TX2 file is ? looks promising size wise
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-09T11:23:11+00:00
- Post Title: extract models

Usually I don't care for textures. Load it into irfanView for example, as a raw file 2048x1024, 8 BPB to see what it looks like.
## Post #5
- Username: xmotoracer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 01, 2022 10:18 pm
- Post datetime: 2023-07-09T11:33:29+00:00
- Post Title: extract models

doesn't open for me

not sure what that TX2 file is tbh. i just thought it might hold the rest of the track due to it's size or the files in the m1 folder ?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-09T11:50:15+00:00
- Post Title: extract models

> Reply from xmotoracer ↑Sun Jul 09, 2023 7:33 pm at Sun Jul 09, 2023 7:33 pm
>
> 
doesn't open for meEvery file opens as raw in IrfanView; except it's bigger than 4 GB.   (well, maybe it's 1 GB, didn't check it.)
.



IrfanView.jpg (168.85 KiB) Viewed 246 times



> Reply from xmotoracer ↑Sun Jul 09, 2023 7:33 pm at Sun Jul 09, 2023 7:33 pm
>
> 
i just thought it might hold the rest of the track due to it's size or the files in the m1 folder ?"Tx" means "texture" here.
## Post #7
- Username: xmotoracer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 01, 2022 10:18 pm
- Post datetime: 2023-07-09T12:51:14+00:00
- Post Title: extract models

"Tx" means "texture" here.

sorry......that does make sense. know nothing about this tbh, i just thought that a larger file meant it may hold in this case a racing track
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-10T22:16:36+00:00
- Post Title: extract models

Checked an mtm file. Looks like parts of a track:
.



1_CF-mtm.png (13.29 KiB) Viewed 203 times



You might check another H2O file with 1_CF.mtm, but I don't know what the result could mean:

0x12AB0 3366
Vb1
12 99
0xC190 2244
020000
0x0 255

----------------------------

O_N.mtm is switching between vertices and normals parts, too tired for fiddling. You may check these H2O files as point clouds:

0x0 3
Vb1
16 99
0x510 76
020000
0x0 255

0x0 3
Vb1
16 99
0x9D0 277
020000
0x0 255

0x0 3
Vb1
16 99
0xF00 102
020000
0x0 255

Overall face index count is 246950 which results in a vertex? count of 12586. (FIs' start address: 0x2D1DE0)
Have fun.
## Post #9
- Username: xmotoracer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 01, 2022 10:18 pm
- Post datetime: 2023-07-11T16:04:24+00:00
- Post Title: extract models

good stuff....I'm hoping it should be a track
## Post #10
- Username: xmotoracer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 01, 2022 10:18 pm
- Post datetime: 2023-07-14T17:42:16+00:00
- Post Title: extract models

can anyone with the skill & knowledge make an extractor for this to get the 3ds & textures out please
## Post #11
- Username: xmotoracer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 01, 2022 10:18 pm
- Post datetime: 2023-07-29T16:08:44+00:00
- Post Title: extract models

wibble
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-29T16:56:50+00:00
- Post Title: extract models

All we have so far is tracks, or am I mistaken? And textures for tracks? I can't remember anyone to have shown a separate texture for a track.

So you'll need to wait (very long, I guess) 'till someone cares for this game, whose name we don't even know.
## Post #13
- Username: xmotoracer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 01, 2022 10:18 pm
- Post datetime: 2023-08-05T15:30:50+00:00
- Post Title: extract models

nascar 2011 for wii. this version would work well for me to convert to an older game as the vertices count is lower etc that it's other platform versions
