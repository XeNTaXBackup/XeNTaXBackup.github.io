## Post #1
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-04-26T19:22:31+00:00
- Post Title: DJ Hero (Wii) - msb Models and Related Files

Moving along from the archive research forum, after extracting the contents of DJ Hero's FAR archives I am left with 3 model-related files.

.msb files are models. They contain texture, part and bone names, but are currently unreadable.
.img files are textures. After a brief search, I couldn't find a program with IMG support that could read them.
.gr2 files are animations. They are "Granny 3D" files, and are readable in the GR2 Viewer released by RAD Game Tools.

Included is a 7-Zip archive of files that should relate to each other, extracted from FAR archives from the game's "*\Wii\FAR" directory. The files were all found in seperate FAR archives, but their directories fit together:

*\Wii\FAR\DJ_DaftPunk_x2: art\djs\dj_daftpunk_x2\daftpunk_x2.msb
*\Wii\FAR\DJ_DaftPunk_x2Costume1Skin1: art\djs\dj_daftpunk_x2\textures_daftpunk01/textures_daftpunk02\*.img
*\Wii\FAR\DJ_DaftPunk_x2_AnimSet_Game: art\djs\dj_daftpunk_x2\anim\*.gr2
I own a copy of this game. My E-mail address is accessible from my profile on this forum.

I know I'm sounding repetitive, but could someone please consider making a convertor for the Wii version of DJ Hero's models? Thanks for reading this post.
## Post #2
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-04-27T18:24:24+00:00
- Post Title: DJ Hero (Wii) - msb Models and Related Files

This probably doesn't count for much, but...
Here's the result of running one of the .img files though TextureFinder 2.1, in DXT5 quad format at a width of 1024 and shift of 3:
[Image Removed]
In comparison to the same texture dumped with the Dolphin emulator:
[Image Removed]

Does anyone know a program that can read these textures? There probably is and I'm just not thinking of it.
