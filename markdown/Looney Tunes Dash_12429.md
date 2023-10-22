## Post #1
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2014-12-26T10:13:10+00:00
- Post Title: Looney Tunes Dash

Hi! 
I've got the files in this fun game:
[https://zynga.com/games/looney-tunes-dash](https://zynga.com/games/looney-tunes-dash)
meshes are *.fmlb extension and textures *.pvr.
someone can help me get the models?
thanks!
[PorkyPigMaster!.zip](https://xentaxbackup.github.io/file/8376_PorkyPigMaster!.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-26T11:20:19+00:00
- Post Title: Looney Tunes Dash

using hex2obj (view link in my sig):



PorkyPig.JPG (40.4 KiB) Viewed 923 times
## Post #3
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2014-12-26T12:30:57+00:00
- Post Title: Looney Tunes Dash

thanks!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-27T08:36:27+00:00
- Post Title: Looney Tunes Dash

face index tables are often easy to find for simple models. Search for "scrambled alphabets".

=.?.@.A.B.@.?.C.
1.D./.1.C.E.F.G.
H.I.J.K.I.H.L.M

If you're unsure whether to start from 0x4502 or 0x4504 here just try it out.

The vertex count is displayed at the bottom of the left lower list box after pressing go1 in hex2obj.


You can calculate the face index count by dividing the face index table size by the size of the faceindices (sizeofWord=2)

If you don't know how to get the table size, start with a face index count of 500.

start of vertices = start of face index table + faceIndexCount * 2: 
0x4504 + 8970*2  // 8970: decimal
= 0x8B18    // start of vertices

(// means: comment is following)

attention: this formula is valid for this type of models only
For other game's models other formulaes are to be used.



PorkyPig_hex.JPG (76.45 KiB) Viewed 895 times
## Post #5
- Username: ismailyk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 29, 2016 4:22 am
- Post datetime: 2016-04-28T20:37:15+00:00
- Post Title: Looney Tunes Dash

> Reply from shakotay2
>
> using hex2obj (view link in my sig):
hi shakotay2,
I tried to run your program, but got libgcc_s_dw2-1.dll missing error. I'm in an urgent need of the Bugs Bunny model converted. what are my options?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-28T21:07:38+00:00
- Post Title: Looney Tunes Dash

download the last version, 0.24c, please
## Post #7
- Username: Sakuraba
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Mar 14, 2016 4:23 am
- Post datetime: 2016-05-12T22:34:22+00:00
- Post Title: Looney Tunes Dash

Where is the texture for me to try?
## Post #8
- Username: PhillipGamer3264
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Aug 14, 2016 11:32 am
- Post datetime: 2016-08-20T00:52:59+00:00
- Post Title: Looney Tunes Dash

How we get from Noesis Python Script.
## Post #9
- Username: PhillipGamer3264
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Aug 14, 2016 11:32 am
- Post datetime: 2016-08-21T16:01:46+00:00
- Post Title: Looney Tunes Dash

> Reply from PhillipGamer3264
>
> How we get from Noesis Python Script.
i need it
## Post #10
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-08-22T00:59:16+00:00
- Post Title: Looney Tunes Dash

> Reply from PhillipGamer3264
>
> PhillipGamer3264 wrote:How we get from Noesis Python Script.
i need itIf you need it so badly, take the time to learn scripting and do it yourself. That's my philosophy.
