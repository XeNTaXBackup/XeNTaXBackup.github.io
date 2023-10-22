## Post #1
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2022-08-21T04:42:42+00:00
- Post Title: Crimson Tears (PS2)

Extracted this from the game's main resource archive with MungeExplorer. Would love to get the actual models for all the characters in the game. Found very little info regarding this games' formats such as DAR, ARB and LDP. 

[https://www.mediafire.com/file/75nhrmgm ... s.zip/file](https://www.mediafire.com/file/75nhrmgmomlsm2x/crimsontears.zip/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-21T09:24:10+00:00
- Post Title: Crimson Tears (PS2)

This is what I got from a point cloud using a blender skinner plugin (still too lazy to care for face indices):
.



enemy-a00_0-dar.jpg (112.85 KiB) Viewed 265 times
## Post #3
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2022-08-22T04:06:42+00:00
- Post Title: Crimson Tears (PS2)

Interesting! That isn't a particular enemy or boss I recognize off the top of my head and it's hard to tell if those "wings" are just broken bits of mesh or not though.  What plugin did you happen to use?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-22T06:49:52+00:00
- Post Title: Crimson Tears (PS2)

Point cloud skinner for blender 2.6x: [https://sourceforge.net/projects/pointcloudskin/](https://sourceforge.net/projects/pointcloudskin/)

You'll need to collect the vertices from a .dar before, of course. The skinner can't handle .dar (or other 3D formats). It needs a point cloud as input.
## Post #5
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2022-12-08T05:08:41+00:00
- Post Title: Crimson Tears (PS2)

I know it's been a while, but have you had any looks at the LDP files? Apparently someone on this forum said they were the actual raw model files, like I stated above. Can't be too sure, though.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-08T09:30:03+00:00
- Post Title: Crimson Tears (PS2)

ask0.ldp, using VIF tags, here's uvs probably (+ char).
.



CrimsonTears_uvs.jpg (106.57 KiB) Viewed 199 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-08T10:44:32+00:00
- Post Title: Crimson Tears (PS2)

ask0_autocreated_triStrips.jpg (129.12 KiB) Viewed 197 times
## Post #8
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2022-12-08T20:02:27+00:00
- Post Title: Crimson Tears (PS2)

Yep, That's DEFINENTLY Asuka (or Amber, as her localized name was)

Excellent work. I'm not gonna bug you anymore, but I hope someone can eventually find a way to rip these raw. DreamFactory games seem to be very obscure, sadly.
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-11T01:00:01+00:00
- Post Title: Crimson Tears (PS2)

> Reply from Mario123311 ↑Fri Dec 09, 2022 4:02 am at Fri Dec 09, 2022 4:02 am
>
> 
but I hope someone can eventually find a way to rip these raw

i just made a test plugin.(mesh and texture)

*bones at the end of the file
seems to have this structure:

```
	name 64bytes
	parent int32
	seek 12
	position 3(float)
	seek 4
	rotation EulerDeegre 3(float)
	seek 4
	scale 3(float)
	seek 4

```


edit: added UV
[fmt_ldp.zip](https://xentaxbackup.github.io/file/23121_fmt_ldp.zip)
## Post #10
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2023-01-10T02:50:37+00:00
- Post Title: Crimson Tears (PS2)

Holy hell. Amazing progress. I'm actually testing these scripts out, and I'm able to view the unpacked character models and even the weapon ones. Only issue I'm having is trying to figure out how to view the textures in Neosis. (which is probably just me being dumb)

That and I'm still the most curious about those DAR files. Wish I was notified of your response sooner because this is a huge breakthrough for such an obscure game and developer.
