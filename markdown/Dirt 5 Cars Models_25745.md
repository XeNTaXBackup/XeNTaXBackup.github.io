## Post #1
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2022-08-28T12:02:50+00:00
- Post Title: Dirt 5 Cars Models

Hi all!
Interested in car models from Dirt 5.
Unpacked the game, got models in gso format.
So far, I've been able to extract models using 3D Model Researcher. Further work with such models is impossible.
Is it possible to write a script for Noesis to open models normally?
  Waiting for your suggestions.


Model example:

[https://www.mediafire.com/file/npndxnw7 ... l.rar/file](https://www.mediafire.com/file/npndxnw72qj5211/audi_ai_trail.rar/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-28T20:16:20+00:00
- Post Title: Dirt 5 Cars Models

"ITAM" and "HSEM" were signatures in Forza Motorsport's .carbin files. (Dunno whether this could help.)
.



Audi_ai_rail.jpg (217.32 KiB) Viewed 199 times


Sooner or later someone will release a script, I guess.
(Just a matter of finding the start addresses of submeshes.)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-28T21:41:35+00:00
- Post Title: Dirt 5 Cars Models

FVFsize of previous meshes= 48,here 40:
.



audi_ai_trail_sm_x.jpg (179.03 KiB) Viewed 194 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-31T10:07:17+00:00
- Post Title: Dirt 5 Cars Models

Made a tool which provides H2O files for use with hex2obj (view link in my sig):


 Make_H2O_Dirt5_gso.zip
(85.77 KiB) Downloaded 38 times


Tested with ONE .gso file only (audi_ai_trail.gso). So don't blame me if the tools fails badly with other model files.
Use it on your own risk!

Example H2O file (compare previous post):

0x14dcf27 94035
Vb1
40 28
0x18e7bab 20947
040100
0x0 255
