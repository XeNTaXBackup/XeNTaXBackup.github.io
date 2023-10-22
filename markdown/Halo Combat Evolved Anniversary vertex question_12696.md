## Post #1
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2015-03-18T22:16:17+00:00
- Post Title: Halo: Combat Evolved Anniversary vertex question

Iv'e been having a problem trying to figure out how to draw the vertices from this game. I've singled out the count and size of the vertices but the individual vertices aren't stored in the conventional way of three floats but rather what looks like three shorts and an unknown short at the end. Now my problem is that when I do draw them they come out warped and I have to manually edit them so they come out somewhat normal but that varies for each direction, like in this case z and x are too large. Also when I skip the 1st byte and read the shorts in big endian the model comes out the same. Not something that I expected since all of the file before the buffer was little endian and I'm sure should't be applicable.

I believe each vertex influences the next and the last short is also used in this buffer for positional information, but I'm sure that that's not the case since I'm still very fuzzy in the subject. If anyone is willing to help, the vertex buffer offset for the linked model starts at 0x57d1, size is 8 bytes, and the count, if I'm not mistaken, is 5738.

Help would very much be appreciated.


[cyborg.rar](https://xentaxbackup.github.io/file/8842_cyborg.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-19T00:44:32+00:00
- Post Title: Halo: Combat Evolved Anniversary vertex question

yep, strange. But dividing x by 2.0 gives this:



cyborg_x_div_2.JPG (25.04 KiB) Viewed 158 times



So you'll just need to find the scaling factors, or do I miss something?
edit: x /= 2.5; z /= 1.5
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-03-19T01:11:01+00:00
- Post Title: Halo: Combat Evolved Anniversary vertex question

it most likely needs to be scaled by its bounding box.
## Post #4
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2015-03-19T18:11:04+00:00
- Post Title: Halo: Combat Evolved Anniversary vertex question

I went ahead and touched up the script in an attempt to find any scaling and bounding box information but was not able to find any. How is such data usually stored? I have here linked the script and more example models if needed.

[http://a.pomf.se/mfaxxh.rar](http://a.pomf.se/mfaxxh.rar)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-19T19:31:23+00:00
- Post Title: Halo: Combat Evolved Anniversary vertex question

From what I know the bounding box values are stored as 2 diametrical points of a box where the model fits into.
(Using floats it would be 24 bytes.)

Did you care for the skeleton? I could image it will help to get the correct dimensions.
