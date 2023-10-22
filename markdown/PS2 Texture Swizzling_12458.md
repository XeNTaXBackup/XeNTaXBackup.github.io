## Post #1
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-01-01T23:48:48+00:00
- Post Title: PS2 Texture Swizzling?

I've been trying to unswizzle some PS2 textures. Using Noesis' implemented "rapi.imageUntwiddlePS2" is somewhat useful. It seems to unswizzle the data fine but there are some problems with the image.

Before Swizzle:



After Swizzle



What could be wrong with this? The images are 8-bit with a palette so perhaps the palette needs swizzling/reordering?

Sample: [Download](https://mega.co.nz/#!w8A3lDYT!HR9uqQVJSTt2BckSfK0-1HJGWihQhF2QnJFGuAxj-yc)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-03T13:25:58+00:00
- Post Title: PS2 Texture Swizzling?

You don't have the original pic, do you?
If so you could try this trick from Mr.Mouse:

> I then made a screenshot and used the original testpicture as overlay in Photoshop and set the blending option to "Difference". here [viewtopic.php?f=18&t=3894&hilit=eagt&start=15](http://forum.xentax.com/viewtopic.php?f=18&t=3894&hilit=eagt&start=15)

(Didn't read the whole thread, Mr.Mouse wrote something about primary colors,
so I made a simple rgb entry reducing test which didn't reveal anything:)



b5.tr8sgl-newPaletteout-7F_3F.jpg (21.18 KiB) Viewed 424 times
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-01-03T18:12:31+00:00
- Post Title: PS2 Texture Swizzling?

Well I have the original of a smaller sample which I've uploaded here:

[BGR Ver.](https://mega.co.nz/#!5swElBhQ!qJVHDFdeTeOEbOW6Dj7R_AuDwAomtZNV7Rbgw8wFfrE)
[TGA Ver.](https://mega.co.nz/#!E0xwHIwC!TygcrZM8mdloWWNeCod2-vO2u6H2OImJ6So96ggzWaY)

This was dumped from PCSX2. Some of the image data is just not how it should be.

B2.SGL
E1 4D 99 18
2A 0E 06 80 72 52 3C 80 42 1E 11 80 5A 2E 1C 80

B2.TGA
2A 0E 06 80 29 0E 07 80 2E 0E 08 80 2E 12 09 80

So yeah it looks like and issue with the palette or the swizzle algorithm must have been slightly altered.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-03T19:36:15+00:00
- Post Title: PS2 Texture Swizzling?

Use Mr.Mouse's EAGT tool to exchange the palette ("Convert PS2 EA palette"):



b2_comp.JPG (87.68 KiB) Viewed 410 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-03T20:00:30+00:00
- Post Title: PS2 Texture Swizzling?

working with your first sample, too:



b5.tr8sgl-EAGTout.JPG (3.58 KiB) Viewed 407 times
## Post #6
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-01-03T21:07:05+00:00
- Post Title: PS2 Texture Swizzling?

> Reply from shakotay2
>
> working with your first sample, too:
b5.tr8sgl-EAGTout.JPG

Thank you, I need to get this working in Noesis so I can get the textures auto loaded onto some PS2 meshes. Since there's no source provided I'll just drop Mr.Mouse a PM asking how it's done.
