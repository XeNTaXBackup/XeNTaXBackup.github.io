## Post #1
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-08-03T20:02:50+00:00
- Post Title: Digimon World 1 [PSX]

Could I ask you to look into the 3D Model Data of Digimon World 1 for PSX?
I would really appreciate that.

Here is a sample of Phoenixmon
[https://rapidshare.com/files/37321962/HOUO.MMD](https://rapidshare.com/files/37321962/HOUO.MMD)
## Post #2
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-08-07T20:12:08+00:00
- Post Title: Digimon World 1 [PSX]

Bumping this up. 

Please someone look into this?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-07T21:01:14+00:00
- Post Title: Digimon World 1 [PSX]

Can't make out anything from that file. Must be one of those PSX type of models with their own special way of storing data.
## Post #4
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-08-07T21:56:01+00:00
- Post Title: Digimon World 1 [PSX]

MMD is a simple archive format for Playstation TMD's

4 Byte = Offset
4 Byte = Size
X Byte = TMD Data

Milkshape 3D can import PSX TMD's, but no bones

[](http://www.imagebanana.com/view/lxw7or0s/HOUO.jpg)
## Post #5
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-08-08T09:38:35+00:00
- Post Title: Digimon World 1 [PSX]

Yeah I know that Milkshape can do this. 
The problem is the Model imported is not rigged. 
Like everything is just getting  centered so the Model is not imported right.
Every object seems to get the coordinate (0,0,0) or sth like that

But the game displays them right so somehow there also must be information in the file how the game
puts the objects together right?
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-08T17:48:27+00:00
- Post Title: Digimon World 1 [PSX]

Well ya there must be something that tells the files where to go but the plugin author didn't figure it out...
## Post #7
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-08-10T09:37:59+00:00
- Post Title: Digimon World 1 [PSX]

I think it is just that the MMD Files also contain the Animation data and that in the animation data there is how the objects are getting merged together. 
But I'm not sure about this.

One hacker I know, Lowlines made some assumptions about MMD I don't know if they are helpful:

> header {
>
> u8 numframes,
>
> u8 flags, /* 0x80 means scale included */
>
> }
>
> 
>
> init_header {
>
> /* if scale included */
>
> s16 sx,
>
> s16 sy,
>
> s16 sz,
>
> /* endif */
>
> s16 tx?,
>
> s16 ty?,
>
> s16 tz?,
>
> s16 rx,
>
> s16 ry,
>
> s16 rz
>
> /* above could be six s16 values, or three s32 values, I'm not sure however most of the data seems to be in s16/u16 */
>
> }
>
> /* repeats until 0xFF10 is found, call the init-header your base values for objects, numobjects can also be calculated from this */
>
> 
>
> FF10_section {
>
> /* still needs some figuring out, has varying lengths, normally 16 bytes */
>
> }
>
> 
>
> frame * numobjects {
>
> u8 frameid,
>
> u8 flag, /* 0x20 means last frame, 0x00 otherwise */
>
> framedata /* repeats until next frame */
>
> }
>
> 
>
> framedata {
>
> u16 flagid, /* b0-5, objectid, b6-15 flags
>
> u16 time/length (in frames),
>
> data /* depends on flags */
>
> }
## Post #8
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-08-12T12:35:53+00:00
- Post Title: Digimon World 1 [PSX]

bumping this, since still not solved.
## Post #9
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-09-06T20:58:32+00:00
- Post Title: Digimon World 1 [PSX]

bumping this, since still not solved.
