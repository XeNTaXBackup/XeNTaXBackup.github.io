## Post #1
- Username: sucklead
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 02, 2021 9:09 pm
- Post datetime: 2021-03-27T19:54:31+00:00
- Post Title: Help needed extracting Call of Cthulhu: Dark Corners of the Earth Models

I've been doing a lot of work trying to support modding for Call of Cthulhu: Dark Corners of the Earth.
I've managed to get texture export and re-import of upscaled textures working by analysing some of the files.
I'm now looking at getting the 3d models exported.
There are .xbd files that contain different chunks such as CHAR, DOBS, DYNL, LNGL, PHYS, RESL.
As far as I can tell the models are in the CHAR chunk.
The only clues I have is that the developers originally used NetImmerse before switching to their own engine.
Any help on where to begin with this would be greatfuly received.
Attached is an example of the extracted CHAR chunk.
[06_REFINERY_PT5.zip](https://xentaxbackup.github.io/file/19786_06_REFINERY_PT5.zip)
## Post #2
- Username: sucklead
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 02, 2021 9:09 pm
- Post datetime: 2021-03-29T14:49:41+00:00
- Post Title: Help needed extracting Call of Cthulhu: Dark Corners of the Earth Models

An extra clue seems to have been left behind on the xbox version of the game only.
There is an 06_REFINERY_PT5.nnf file that looks like this:
...
32760	CTHULHU_SHRINE_GEOM_01
32764	CTHULHU_SHRINE_GEOM_03
32766	CTHULHU_SHRINE_GEOM_04
32768	CTHULHU_SHRINE_GEOM_05
32770	CTHULHU_SHRINE_GEOM_06
32772	CTHULHU_SHRINE_GEOM_07
...
Full file attached.
[06_REFINERY_PT5_nnf.zip](https://xentaxbackup.github.io/file/19800_06_REFINERY_PT5_nnf.zip)
## Post #3
- Username: sucklead
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 02, 2021 9:09 pm
- Post datetime: 2021-03-29T15:41:45+00:00
- Post Title: Help needed extracting Call of Cthulhu: Dark Corners of the Earth Models

Looking in some of the other files that aren't actually used I can see a mention of XPR0 in the RESL chunk.
From a quick google that would be the magic for an Xbox Packed Resource.
Although that text isn't present in the files that are used I guess it points to the models being in there.

I've now uploaded all chunks here [https://drive.google.com/file/d/11e8hE0 ... 4NtsS/view](https://drive.google.com/file/d/11e8hE0ZZyyBq-UPzDj4FQHT6k4i4NtsS/view)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-29T18:49:09+00:00
- Post Title: Help needed extracting Call of Cthulhu: Dark Corners of the Earth Models

Using hex2obj (view link in my sig):
.



06_REFINERY_PT5-xbd_CHAR.png (90.91 KiB) Viewed 83 times
## Post #5
- Username: sucklead
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 02, 2021 9:09 pm
- Post datetime: 2021-03-29T21:32:29+00:00
- Post Title: Help needed extracting Call of Cthulhu: Dark Corners of the Earth Models

> Reply from shakotay2 ↑Tue Mar 30, 2021 2:49 am at Tue Mar 30, 2021 2:49 am
>
> 
Using hex2obj (view link in my sig):
.
Thanks for this shakotay2 now I have some idea what I'm looking for I should be able to make some progress.
