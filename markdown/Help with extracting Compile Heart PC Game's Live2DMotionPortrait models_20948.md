## Post #1
- Username: Maren
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 18, 2017 11:36 pm
- Post datetime: 2019-08-12T08:37:16+00:00
- Post Title: Help with extracting Compile Heart PC Game's Live2D/MotionPortrait models

I am unsure whether the model is built with Live2D or Motion Portrait, because I've seen Neptunia games built with Live2D, but the folder name 'MP' is short for "Motion Portrait" (I checked the MP website but the technology there doesn't seem to be the same used in the game, so I think Live2D is more likely the right answer).

I want to recover the original model of a game.

With some helps from kind guys in this forum, I was able to extrac the file MP010101.pck from the new PC Port of Date A Live Rio Reincarnation, which gave me these files: 
001.amb | Config.txt | exprLoop.exl | face.bin | face.mpb |  face.uca.bin | layername.bin | screen.txt  | tex_all_s.tex

I was also able to extract tex_all_s.tex and I got a PNG image that looked like sprite sheet.

The extracted folder and image can be found here: [https://www.dropbox.com/sh/2is8cc2eggux ... yUZwa?dl=0](https://www.dropbox.com/sh/2is8cc2egguxyw6/AADaPtRYj35lP-lOyyVfyUZwa?dl=0)

Thank you in advance.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-13T08:59:58+00:00
- Post Title: Help with extracting Compile Heart PC Game's Live2D/MotionPortrait models

structures:
.



face-mpb-0x22d10_vertices.png (18.7 KiB) Viewed 131 times
## Post #3
- Username: Maren
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 18, 2017 11:36 pm
- Post datetime: 2019-08-13T14:11:40+00:00
- Post Title: Help with extracting Compile Heart PC Game's Live2D/MotionPortrait models

Does this mean the model is corrupted or something?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-13T15:24:32+00:00
- Post Title: Help with extracting Compile Heart PC Game's Live2D/MotionPortrait models

> Reply from LeonNeol ↑Tue Aug 13, 2019 10:11 pm at Tue Aug 13, 2019 10:11 pm
>
> 
Does this mean the model is corrupted or something?I wouldn't know why. That's what you get using "floats" and an FVFsize of 16 chosen. (View links in my sig to understand what FVFsize means.)
Signature "ITOM" at start of the mpb file might be the abbreviation for "MOTION" so it's not static meshes. (The pic in my previous post might show a triangle at different positions ("moving") but usually other games use animation files for such.)
