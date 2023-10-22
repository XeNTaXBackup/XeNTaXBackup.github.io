## Post #1
- Username: iseeeva
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 19, 2021 10:04 am
- Post datetime: 2022-10-06T20:20:41+00:00
- Post Title: Cars 2 PS3 vbuf/ibuf files

im trying reverse endianness for cars 2,
i handle a pc version but ps3 version is soo awkward for me.
can anyone help for info? (ibuf/index, vbuf/vertex)

%1.vbuf is big endian and vertexs start with this pattern;

[cars2_ps3_bufs.rar](https://xentaxbackup.github.io/file/22881_cars2_ps3_bufs.rar)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-06T23:02:10+00:00
- Post Title: Cars 2 PS3 vbuf/ibuf files

> Reply from iseeeva ↑Fri Oct 07, 2022 4:20 am at Fri Oct 07, 2022 4:20 am
>
> 
can anyone help for info?
holly_0.ibuf - indices (short)
holly_0.vbuf - uvs buffer (halfFloat)
holly_1.vbuf - vert buffer (stride 32)



exsample.png (142.12 KiB) Viewed 101 times
