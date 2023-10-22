## Post #1
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-19T07:12:02+00:00
- Post Title: Unity format meshe 43. Need help struct.

I load unity mesh .43 my self.
Simple mesh load ok, but animation mesh vertices show not correct.
I need help on the structure file format unity mesh 43 . And who interesting join.
[https://www.youtube.com/watch?v=CAD-bsu ... e=youtu.be](https://www.youtube.com/watch?v=CAD-bsuwskg&feature=youtu.be)
## Post #2
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-20T06:23:10+00:00
- Post Title: Unity format meshe 43. Need help struct.

This animated mesh.
I read only vertices data and indices. But mesh look like boom.
[Orc Molten.rar](https://xentaxbackup.github.io/file/9578_Orc Molten.rar)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-20T10:32:06+00:00
- Post Title: Unity format meshe 43. Need help struct.

> Reply from Roman
>
> But mesh look like boom.It's the way orcs look like 



OrcMolten.JPG (43.77 KiB) Viewed 186 times
## Post #4
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-20T11:04:42+00:00
- Post Title: Unity format meshe 43. Need help struct.

shakotay2
How do you load my model Orc Molten ?
Do you know unity mesh 43 format ?
Please tell me how you do ?

You vertex offset is 64 bytes ? I'm right?
I download you programm Hex2o__v0.2x and i get right mesh Orc Molten.
## Post #5
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-20T11:47:44+00:00
- Post Title: Unity format meshe 43. Need help struct.

In hex editor i found number vertices and vertices data size of bytes.
I 0x03F7E0/0x152A = 0x30 bytes vertices offset 

shakotay2
Why you do 64 bytes offset on vertices data ?
[Molten.jpg](https://xentaxbackup.github.io/file/9586_Molten.jpg)
## Post #6
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-20T12:03:15+00:00
- Post Title: Unity format meshe 43. Need help struct.

shakotay2
And how do you read Vertices data ?
I mean first 12 bytes this is vertices then next 12 bytes normals and 8 bytes TextureUV.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-20T12:06:32+00:00
- Post Title: Unity format meshe 43. Need help struct.

> Reply from Roman
>
> Why you do 64 bytes offset on vertices data ?dunno what you mean by offset - mean vertex stride?
It's 40 bytes (all params for hex2obj are decimal values except the startaddresses 0x...)

From one 00 00 80 3F pattern to the next one it's 40 bytes - as simple as that.

You'll learn it by experience and patience.

btw: as far as I can see an UVpos of 24 (12+12) will not give valid UV data.



OrcMolten_tex.JPG (85.33 KiB) Viewed 177 times
## Post #8
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-20T12:28:21+00:00
- Post Title: Unity format meshe 43. Need help struct.

Ha !   
I do vertex stride = 40 bytes and i got model   
Strangely ! From the hex editor data i think vertex stride = 48 bytes.
From hex editor 0x03F7E0/0x152A = 0x30 bytes vertices stride
[orc.jpg](https://xentaxbackup.github.io/file/9589_orc.jpg)
## Post #9
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-20T12:48:46+00:00
- Post Title: Unity format meshe 43. Need help struct.

Other unity mesh Bandit 
Thanks for you help shakotay2
[bandit.jpg](https://xentaxbackup.github.io/file/9592_bandit.jpg)
## Post #10
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-20T13:52:52+00:00
- Post Title: Unity format meshe 43. Need help struct.

[https://www.youtube.com/watch?v=9-BkZkz ... e=youtu.be](https://www.youtube.com/watch?v=9-BkZkz4WDM&feature=youtu.be)
