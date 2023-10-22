## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-07-09T16:16:13+00:00
- Post Title: How to extract 3D models from Juiced 1 and 2?

I found mariokart64n's maxscript, but 3DS Max is very expensive.

> Reply from mariokart64n ↑Fri Feb 26, 2021 6:09 pm at Fri Feb 26, 2021 6:09 pm
>
> 

.d8m / .d9m = car models
.d8g / .bdl = map models
.ddt = textures
.jsm = character models (only for Juiced 2)

I used hex2obj but car models look garbage:



bandicam 2023-07-09 17-08-30-973.jpg (65.9 KiB) Viewed 125 times



Can someone make a Blender/Noesis plugin?

Samples:
[https://mega.nz/folder/VSJ2gCAa#Ug-zB3eur1Zn_ebFm28T0w](https://mega.nz/folder/VSJ2gCAa#Ug-zB3eur1Zn_ebFm28T0w)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-09T16:49:45+00:00
- Post Title: How to extract 3D models from Juiced 1 and 2?

> Reply from mrmaller1905 ↑Mon Jul 10, 2023 12:16 am at Mon Jul 10, 2023 12:16 am
>
> 
I used hex2obj but car models look garbage:It's because you need to care for sub meshes.
.



wheel_oz_vs6.png (43.75 KiB) Viewed 114 times


"Juice 1" has many parts which are divided up in sub meshes. I guess no one will create a noesis script when a max script exists.

There's was a "ms to py" project if I remember correctly. That would make more sense, imho, than creating a py script from scratch.
Except you're a very proficient py scripter.

edit: found it (different format), mariokart64n already started to create blender py functions from maxscript functions:

> Reply from mariokart64n ↑Sat Mar 13, 2021 1:55 am at Sat Mar 13, 2021 1:55 am
>
>
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-09T17:26:26+00:00
- Post Title: How to extract 3D models from Juiced 1 and 2?

This eve_10 chassis looks very smooth if you don't enter the full FI count (16991):
.



evo_10_chassis.png (44.34 KiB) Viewed 105 times


As I wrote you simply need to find the EOSM (end of sub mesh).

(The vertex count of the first sub mesh is 3799, btw. To be found in that d9m file at 0x856C)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-10T09:20:52+00:00
- Post Title: How to extract 3D models from Juiced 1 and 2?

Another sub mesh out of assumed 10:
.



evo_10_bumpers.png (23.38 KiB) Viewed 79 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-10T12:04:25+00:00
- Post Title: How to extract 3D models from Juiced 1 and 2?

Here's the H2O files for evo_10, dm9. One mesh (out of 10) faulty, no time for checking.
.


 evo_10_chass.d9m_0.zip
(1.68 KiB) Downloaded 17 times

Use with hex2obj, copy H2Os into model file folder, load model, then choose SaveAs Mmesh.
(Yes, it reads mMesh, not mesh, btw.)
10 .obj files to be created then.
