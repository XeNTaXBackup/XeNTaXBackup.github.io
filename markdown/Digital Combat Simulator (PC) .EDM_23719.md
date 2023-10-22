## Post #1
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-09T00:09:36+00:00
- Post Title: Digital Combat Simulator (PC) .EDM

I searched and all i found is an exporter. There was a import tool but its last update was 2016. I tried it anyway with no luck. Are these able to be parsed with a script?
[](https://ibb.co/rZX3Zmw)
Vertex and UV data
[](https://ibb.co/z26cKpr)
Faces start after uv data
[](https://ibb.co/xhZz3yh)
Final result 
[](https://ibb.co/8bCs1W9)
The data seems pretty clear.

Thanks in advance for any help.

Sample
[https://drive.google.com/file/d/1LmVefh ... sp=sharing](https://drive.google.com/file/d/1LmVefhoSO84xU7q_ZBEfDyBYGyWEvvwJ/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-09T21:45:40+00:00
- Post Title: Digital Combat Simulator (PC) .EDM

Interesting format, guess it's using child objects (I didn't care for).
Here's the 3 biggest meshes I could get:
.



fa-18c.edm.png (190.72 KiB) Viewed 53 times



> Reply from Sharppy ↑Fri Apr 09, 2021 8:09 am at Fri Apr 09, 2021 8:09 am
>
> The data seems pretty clear.Really? Tell us more.
How to get the different FVFsizes (84, 36, ?).

How to get the structure (hierarchy, if any)?
## Post #3
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-09T22:57:13+00:00
- Post Title: Digital Combat Simulator (PC) .EDM

Well it seemed so at first  I guess my method on seeing the model data is "blind". I really just go by the patterns of data from Model Researcher which mariokart64 said was a bad thing to do. With what your saying yeah I wouldn't know where to look for such data. Or even know what FVF is    but by how the data was falling into MR it seemed like a easy format compared to others I've examined is what I should of said. Thanks for looking at it. There are more files in the folder but I figured since there was a .EDM importer awhile back that was all that was needed. Maybe they updated the files since 2016 ?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-10T07:20:55+00:00
- Post Title: Digital Combat Simulator (PC) .EDM

> Reply from Sharppy ↑Sat Apr 10, 2021 6:57 am at Sat Apr 10, 2021 6:57 am
>
> I really just go by the patterns of data from Model Researcher which mariokart64 said was a bad thing to do.Depends on what you mean by "the patterns of data". Using search-patterns in a hex editor to get "an idea of the data structure" is not that bad, if you have experience with some dozens of 3D formats. 
It's the fastest way to get results I know of. Not everybody has the time/patience/knowledge to do a full format analysis.

btw: FVF= flexible vertex format

btw (2): the ejection seat in the previous picture is far from being complete, here's a H2O file for fa-18c.edm:

0x1784EF2 41331
Vb1
36 28
0x16E5B11 18118
020000
0x0 255
