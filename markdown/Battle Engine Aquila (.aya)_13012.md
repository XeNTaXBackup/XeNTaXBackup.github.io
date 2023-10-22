## Post #1
- Username: Notfounded
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 30, 2014 8:12 pm
- Post datetime: 2015-07-02T15:49:21+00:00
- Post Title: Battle Engine Aquila (.aya)

The only attempt to decompress these files was made in 2005 (I believe that this is the compression method, because both textures and models are in this format)

Here some samples of the file:
[https://drive.google.com/file/d/0B4uKIP ... sp=sharing](https://drive.google.com/file/d/0B4uKIPLNbQV6Rnh5Y2E3djBEVUU/view?usp=sharing) (model)

[https://drive.google.com/file/d/0B4uKIP ... sp=sharing](https://drive.google.com/file/d/0B4uKIPLNbQV6bXMyeHNJSTd0MGM/view?usp=sharing) (texture)

and some kind of resources (I really don't know what kind of resources it is)
[https://drive.google.com/file/d/0B4uKIP ... sp=sharing](https://drive.google.com/file/d/0B4uKIPLNbQV6YUVyY0NlWHFZcGc/view?usp=sharing)

Any ideas how to decompress these files?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-02T17:42:47+00:00
- Post Title: Battle Engine Aquila (.aya)

use offzip:



meshtex---aya.JPG (74.96 KiB) Viewed 50 times



Finds 4 valid zip blocks in 110_res_PC.aya) 

Use forum search on how to use offzip.
## Post #3
- Username: Notfounded
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 30, 2014 8:12 pm
- Post datetime: 2015-07-03T17:01:22+00:00
- Post Title: Battle Engine Aquila (.aya)

> Reply from shakotay2
>
> use offzip:
meshtex---aya.JPG

Finds 4 valid zip blocks in 110_res_PC.aya) 

Use forum search on how to use offzip.

Thank you!

After editing of textures i want to use them in game

Is it possible to compress them in this format using packzip? (I try to compress with original offset but it don't work. Did i do something wrong?)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-03T21:18:58+00:00
- Post Title: Battle Engine Aquila (.aya)

> Reply from Notfounded
>
> Did i do something wrong?)dunno.
Talking about the "meshtex...aya"?
Guess you'll need to know the meaning of its first four bytes: E7 C3 02 00
Thought it were the uncompressed size but seems it's not.

(78 9C marks the start of zip-compressed data)

I would suggest to compress the unchanged dds and compare it to the original .aya in a hexeditor.
This might give you an idea what's going wrong with your proceeding.
## Post #5
- Username: Notfounded
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 30, 2014 8:12 pm
- Post datetime: 2015-07-04T01:08:57+00:00
- Post Title: Battle Engine Aquila (.aya)

> Reply from shakotay2
>
> Notfounded wrote:Did i do something wrong?)dunno.
Talking about the "meshtex...aya"?
Guess you'll need to know the meaning of its first four bytes: E7 C3 02 00
Thought it were the uncompressed size but seems it's not.

(78 9C marks the start of zip-compressed data)

I would suggest to compress the unchanged dds and compare it to the original .aya in a hexeditor.
This might give you an idea what's going wrong with your proceeding.

The new file has a different size and when I compared it and the old file through the hex editor and found that they're different, I tried to edit the beginning of a new file, so it was like at the beginning of the old file (or even copy it)
But new file still don't works.

I think it is because game uses different zlib version (11 Marth 2002) (I do not quite understand the theme about file compression. Because of this, I can not find any other reason.)
