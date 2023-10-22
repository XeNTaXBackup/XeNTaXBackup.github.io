## Post #1
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2017-08-10T21:53:31+00:00
- Post Title: Converting a texture file

I got an .fmt file that is actually a texture and i'm trying to convert it to png, i've tried texturefinder but the colors don't display correctly
[face.zip](https://xentaxbackup.github.io/file/13189_face.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-08-10T23:32:38+00:00
- Post Title: Converting a texture file

what game is this from?

it fits perfectly as a 128x128 image but maybe has a color palette associated with it?

do you recognise the image btw? are there 2 frames per image? the face image has eyes which are closed (l) and open (r). spot the difference 2015?
## Post #3
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2017-08-11T00:47:35+00:00
- Post Title: Converting a texture file

This is an unused texture from Final Fantasy X (PS2 version), although that same one is found on the HD PC version, which is the one i uploaded, since i have no way to extract the PS2 version's.

The image consists of 7 portraits of summonable monsters 4 on the left 3 on the right

This is the only way i can display the image at the moment
## Post #4
- Username: EmptyMan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2016 2:22 am
- Post datetime: 2017-09-01T19:22:27+00:00
- Post Title: Converting a texture file

I don't recognise palette data
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-02T03:20:19+00:00
- Post Title: Converting a texture file

is that just 8-bit alpha?
## Post #6
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-09-15T08:38:24+00:00
- Post Title: Converting a texture file

Just look at data structure. It's different at 0x4000 (coincidence?)
Every 0xFFFFFFFFFF... thing is 256 byte long

16384/256 = 64

TextureFinder setting:
888=24; width=85; skew+1 offset 16384
