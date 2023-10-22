## Post #1
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-09-30T21:28:14+00:00
- Post Title: MegaRace Sprites

Hi everyone,

I'm trying figure out how to properly view the sprites in MegaRace.  I got the sprites via extracting various HSQ files from Game Extractor and then decompressing those HSQ files using Bigs' unHSQ decompressor.  Once the file has been decompressed, I load the file into GGD and was able to load this:



This sprite's filename is _OUZ.hsq (or _OUZ.___, when decompressed).  I used the palette data at the end of the file and I'm getting somewhere, but it's still very pale and different from what's in-game.  Any suggestions to fix this?



Also, it's seems that the file is incomplete as it's missing tire spinning animation as well as the animation where the car spins out of control and does a 360.  I'm wondering if there's a problem with the compressor and it's not extracting other files for the other animations.  Again, any help would be greatly appreciated. 

[http://dunerevival.svn.sourceforge.net/ ... tools/hsq/](http://dunerevival.svn.sourceforge.net/viewvc/dunerevival/tools/hsq/) Here's the HSQ decompressors and source code, if you wanna mess around with the HSQ files.

Bigs_fr has his decompressor already compiled, which is the program I used: [https://sites.google.com/site/duneedito ... edirects=0](https://sites.google.com/site/duneeditor/bigs_fr-mirror/unhsq.zip?attredirects=0)
## Post #2
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-10-07T02:24:18+00:00
- Post Title: MegaRace Sprites

Could anyone offer some advice, please?
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-07T18:06:03+00:00
- Post Title: MegaRace Sprites

can you send a HSQ sample?
## Post #4
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-10-07T19:19:24+00:00
- Post Title: MegaRace Sprites

> Reply from WRS
>
> can you send a HSQ sample?

Sure thing! Here's an HSQ file:

[http://www.mediafire.com/?wo4yzg6ojxhhlh6](http://www.mediafire.com/?wo4yzg6ojxhhlh6)

And here's the uncompressed file that was inside of the HSQ file; the sprite data:

[http://www.mediafire.com/?ffed35b452bsty2](http://www.mediafire.com/?ffed35b452bsty2)

Thanks in advance!
## Post #5
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-10-11T03:33:10+00:00
- Post Title: MegaRace Sprites

Just wanted to let you know that HSQ compression is, I believe, based off of the LZ77 algorithm.  There maybe some RLE compression in the sprite file, but I'm not entirely sure.

I also read somewhere that the palette color data maybe in 6-bits...If so, is there a sprite viewer that can let me view the palette data in 6bpp?

Thanks in advance!
## Post #6
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-11-02T00:30:12+00:00
- Post Title: MegaRace Sprites

Any advice guys?  Are there any other programs I can open this file up in and do stuff like GGD?
## Post #7
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2012-11-04T23:18:48+00:00
- Post Title: MegaRace Sprites

> Reply from MrSinistar
>
> Any advice guys?  Are there any other programs I can open this file up in and do stuff like GGD?
IIRC, the GGD project was discontinued quite some time ago. From those ashes rose 'tiledggd'; being what one might address as GGD's successor.
It's still in continued development, all source-code is open and freely available, but most notably it's features exceed those of the aforementioned predecessor, as well as mirroring the features of the original GGD.
It's available from here: [http://code.google.com/p/tiledggd/](http://code.google.com/p/tiledggd/)
There's also a decent-enough tutorial (given the overall ambiguity and variability of sprites/textures etc. from a universe of different games): [http://code.google.com/p/tiledggd/wiki/Tutorial](http://code.google.com/p/tiledggd/wiki/Tutorial)

Having said all that, I don't really have the time to look into your sample files at the present time, as I'm overwhelmingly bogged-down with work & what-not else.
I remember following that Dune-Revival project thread with enthusiasm a while back, though. As I'm sure you must have, too   

Cryo formats (of all sorts) are notoriously complex and difficult to discern/reverse-engineer, but you look like you're doing well so far at least   
I hope I've at least helped you out even a little, despite this post being mostly banter.
Good luck with everything, mate.
## Post #8
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2012-11-04T23:20:39+00:00
- Post Title: MegaRace Sprites

Haha, oh and I just happened to notice your avatar: Lance Boyle

Dude, that brings back a ton of memories
## Post #9
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-11-05T03:34:39+00:00
- Post Title: MegaRace Sprites

> Reply from RENIKRILL
>
> Having said all that, I don't really have the time to look into your sample files at the present time, as I'm overwhelmingly bogged-down with work & what-not else.
I remember following that Dune-Revival project thread with enthusiasm a while back, though. As I'm sure you must have, too   

Cryo formats (of all sorts) are notoriously complex and difficult to discern/reverse-engineer, but you look like you're doing well so far at least   
I hope I've at least helped you out even a little, despite this post being mostly banter.
Good luck with everything, mate.

Yes, that Dune-Revival project really helped out understanding old Cryo formats and I figured reverse engineering MegaRace's files will help work with other Cryo games like Dune, etc.  Likewise, I would work more on it but I'm doing college and other projects that are more important so this is on the backburners for me.

Thanks for the good luck! I hope someday these files will be viewable outside of the game.

Thanks for noticing the avatar too!  He's insane, lol.  Lovin' the spice worm avatar too! lol
## Post #10
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-11-05T18:10:53+00:00
- Post Title: MegaRace Sprites

Just curious, is there a generic LZ77 or RLE decompressor that I can load these sprite files into?  It seems that a lot of this data is compressed and if I can find a way to decompress it, that will help out a lot.
## Post #11
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-11-13T08:38:55+00:00
- Post Title: MegaRace Sprites

I don't know if this is the complete sprite but it's the closest I could get to seeing the full explosion in-game.  I'm assuming that the actual explosion sprite is cropped off intentionally since the explosion is being animated by the game to move out of view during a race.

Anyways, enjoy!
