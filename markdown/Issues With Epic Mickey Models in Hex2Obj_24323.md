## Post #1
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2021-08-05T21:40:55+00:00
- Post Title: Issues With Epic Mickey Models in Hex2Obj

Me and others have been trying to open the models in Epic Mickey with Hex2Obj, but we usually run into issues. It looks like the models are formatted weird? When we try to open an unused early level (link below), it always gives normal(ish) vertex counts, but then some numbers (like the UV list size) are either absurdly large or small (goes into negative numbers). So far we've only been able to open verrrrrrry simple models, such as this gear.



I've also tried an unused enemy (also linked below) and the same thing happens. I believe it is [this](https://epicmickey.fandom.com/wiki/Dropwings) enemy that is in the second game but was planned for the first (due to the file name being kamikaze).

I've triple checked my math and filled like 5 notebook pages with math and charts, so any help would be appreciated.





[(Early Enemy)](https://drive.google.com/file/d/1UDVgYrz4UaHGxr6NQ9MmmMJul45_zR1t/view?usp=sharing)
[(Early Level)](https://drive.google.com/file/d/10b35x_Z1hs8swP_29RTyvfbMrKqbaBaE/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-05T23:49:59+00:00
- Post Title: Issues With Epic Mickey Models in Hex2Obj

Structure of "blotling"-nif is a little bit different:
.



blotlingKamikaze1-nif_wii.png (101.78 KiB) Viewed 63 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-06T09:03:57+00:00
- Post Title: Issues With Epic Mickey Models in Hex2Obj

simpler one (vertex and uv data in 24 bytes blocks):
.



Demo_GV_Island01_Inert-nif_wii.png (71.3 KiB) Viewed 49 times


(First sub mesh only and normals ignored as always by me  )
