## Post #1
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-08-08T14:33:00+00:00
- Post Title: Just Dance 2014 (Wii) .tga.ckd/png.ckd

Hello, recently i've been extracting Just Dance games for Wii and i found out some (probably dds?) textures and i couldn't open them. They seem to have their header reversed so i don't know how to open them. Could anyone help me?
[cube_g.tga.rar](https://xentaxbackup.github.io/file/13177_cube_g.tga.rar)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-08-29T12:52:23+00:00
- Post Title: Just Dance 2014 (Wii) .tga.ckd/png.ckd

Yes, DXT1 marked as TEX. Width:256
That's quite bad you choosed cube side for sample texture. This texture is normally used for reflections and special effects, so probably the closest image I could get is:

Despite it looks like rubbish it may be 100% correct in-fact
as it's cube_g, so g stands for global illumination probably and it's cube so it may look weird
