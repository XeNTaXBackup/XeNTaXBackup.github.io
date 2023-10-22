## Post #1
- Username: Roselle
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 18, 2014 4:51 pm
- Post datetime: 2016-03-09T19:07:54+00:00
- Post Title: UV algorithm for help

I got some data with H2O in this file, but UV gives me a headache, I found only at the beginning of the UV data, I cannot calculate the next position of the elements of the UV, can you help me?
H2O:
0x1f510  1482
UV:   0x235c0  99
   0x8133 330

[II]0x200b0 180
   0x?         99 
   0xc963  80

[III]0x20220 2640
     0x?    99
     0xdae3  936
[XentaX.zip](https://xentaxbackup.github.io/file/10570_XentaX.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-09T23:03:45+00:00
- Post Title: UV algorithm for help

> Reply from Roselle
>
> I found only at the beginning of the UV data, I cannot calculate the next position of the elements of the UV, can you help me?0x235c0 looks like a correct beginning; the other uv start addresses might require some fiddeling.

0x28858 looks like a block end - the delta is 0x5298 = 2643x8 dec.

sum of verts *2 = 2692 = (330+80+936)*2
That's not close enough to 2643 so another idea is needed.

(Factor 2 is "derived" from the fact that there's two normals blocks (0x106C3. 0x132A3))

Maybe try 0x2A230 as a starting address, or, or, or, dunno...
