## Post #1
- Username: Mirailiyeon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 23, 2020 7:20 am
- Post datetime: 2021-06-16T23:09:59+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

Hello! So i used the QuickBMS script to extract the dat files in Swords of Legends Online, and I looked in the "models" folder and there are two model file types: .hkc and .model

I am trying to open one or the other, but cant seem to find a way to do so. I will include a google drive link with some samples. Thanks for your time!  

[https://drive.google.com/file/d/1S4NZ1b ... sp=sharing](https://drive.google.com/file/d/1S4NZ1b55fgSze1kAF6iEe1UGpK5M1m1I/view?usp=sharing)
## Post #2
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-17T08:12:18+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

For the female hair 010 .model faces should start at 0x05EC46 and should be short type. Verts have 0x20 bytes inbetween them (I think) but I can't quite find their starting offset.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-17T08:33:36+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

female_hair_main_010-model.png (108.69 KiB) Viewed 257 times
## Post #4
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-17T08:51:20+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

> Reply from shakotay2 ↑Thu Jun 17, 2021 4:33 pm at Thu Jun 17, 2021 4:33 pm
>
> 
female_hair_main_010-model.png

The verts are float type? I tried offset 0x086 with short sign/float/half-float and I'm wondering what I did wrong.

EDIT: Okay nevermind, I'm dumb it was my padding. I kept trying earlier with short / half-float but never thought to try float. Good job and thanks a ton shako, I'm sure OP would thank you too.

For hair 13: 

With AXE: 

Only thing I wasn't able to figure out was the UVs with AXE because I am not very certain on how to do that sort of thing yet.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-17T13:17:31+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

not sure, looks a little bit strange:
.



female_hair_main_010-maybe_uvs.png (43.72 KiB) Viewed 232 times
## Post #6
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-18T09:22:53+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

> Reply from shakotay2 ↑Thu Jun 17, 2021 9:17 pm at Thu Jun 17, 2021 9:17 pm
>
> 
not sure, looks a little bit strange:
.
female_hair_main_010-maybe_uvs.png

What offset is the uv position exactly? Like in mesh extractor how does the uv pos relate to the vertices? Like the 20 number you put.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-18T11:44:51+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

Dunno what you mean exactly, uvs start 20 bytes after vertices for this .model format:
.



SwordsOfLegends_model.format-FVF_block.png (25.84 KiB) Viewed 208 times


(FVF means "flexible vertex format")
## Post #8
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-18T17:05:19+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

> Reply from shakotay2 ↑Fri Jun 18, 2021 7:44 pm at Fri Jun 18, 2021 7:44 pm
>
> 
Dunno what you mean exactly, uvs start 20 bytes after vertices for this .model format:
.
SwordsOfLegends_model.format-FVF_block.png
(FVF means "flexible vertex format")

Thank you, that makes a lot more sense now. And UVs look correct I think since it's supposed to be hair anyway.
## Post #9
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2021-08-05T00:27:33+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

hey @Mirailiyeon how did you get the file names from the bms script. Used 
new_sword_legends.bms 0.2.5
## Post #10
- Username: reydria
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 06, 2020 9:06 am
- Post datetime: 2021-08-05T12:52:00+00:00
- Post Title: Swords of Legends Online .hkc and .model Files

Hi there I hope I can ask this here, I am trying to import my exported models from the bms script for swords of legends. I tried using the 3d object converter and when I import a .model, it says bad polygons and nothing shows up. Should I be using a different program? any help would be awesome
