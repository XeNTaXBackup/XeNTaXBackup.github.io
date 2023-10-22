## Post #1
- Username: huckbeine
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 05, 2011 7:32 pm
- Post datetime: 2015-07-17T19:13:36+00:00
- Post Title: Help with Natsuiro High School (PS3)

Ok, very very nooby 3d model ripper here, so please don't laugh.

I need help with Natsuiro High School 3d model ripping.

So I have the Natsuiro High School files and it was pretty small (2GB)
and most of the data is in the install folder. 

So the file is a .cpk file and I extracted it.
Now, I located all the files containing 3d model data and textures.

Unfortunately, the files are .cat and .gtf files. I don't the next step to this

Can anyone help me extracting the files into a format that can be imported to Max or maya?
## Post #2
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2015-07-18T20:36:47+00:00
- Post Title: Help with Natsuiro High School (PS3)

[http://www.mediafire.com/download/h7l7s ... r00_00.cat](http://www.mediafire.com/download/h7l7sqmpsa1ryg1/player_hair00_00.cat)



But I can not find UV data
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-18T21:13:40+00:00
- Post Title: Help with Natsuiro High School (PS3)

there are two datablocks, 1769x4 bytes each:
from 0xB290 to 0xCE34 and
from 0xCE40 to 0xE9E4
which may or may not contain uv data.

In the first block every fourth byte is zero,
in the 2nd block it's between 0 and 3 (like some bone id).

Very strange...
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-07-18T22:01:47+00:00
- Post Title: Help with Natsuiro High School (PS3)

Noesis script to load the gtf textures.
[fmt_Natsuiro_High_School_gtf.zip](https://xentaxbackup.github.io/file/9433_fmt_Natsuiro_High_School_gtf.zip)
## Post #5
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2015-07-19T15:52:30+00:00
- Post Title: Help with Natsuiro High School (PS3)

> Reply from shakotay2
>
> there are two datablocks, 1769x4 bytes each:
from 0xB290 to 0xCE34 and
from 0xCE40 to 0xE9E4
which may or may not contain uv data.

In the first block every fourth byte is zero,
in the 2nd block it's between 0 and 3 (like some bone id).

Very strange...

The rest

[http://www.mediafire.com/download/mfhhe ... /chara.rar](http://www.mediafire.com/download/mfhheoqomnd5xfz/chara.rar)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-19T22:12:19+00:00
- Post Title: Help with Natsuiro High School (PS3)

with some imagination you could recognize the outline of a 90° clock wise rotated face
but it's not uvs:



girl_face_.JPG (200.66 KiB) Viewed 298 times
