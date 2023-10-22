## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-12-30T06:36:15+00:00
- Post Title: ipod .ani + .gtl files

Hello fellows. I've been trying to extract graphics from a game for the ipod touch. Specifically, Wackylands Boss. I was hoping they would be as simple as other chillingo games what with the convertable PNGs. Turns out they're another common method in ipod games. ".ANI" files, which are used commonly in various other cartoonish games.

Anyway, here's a few sample files.
[http://www.sendspace.com/file/5xug7c](http://www.sendspace.com/file/5xug7c)
This zip file holds a folder containing various ANI files. If you need any more, just ask.

As usual the goal here is to extract the graphics, as they ARE graphic files.
## Post #2
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-12-30T06:58:39+00:00
- Post Title: ipod .ani + .gtl files

Aha, sorry, I forgot to include the referenced .gtl files for the .ani files.

Here they are.
[http://www.sendspace.com/file/8rlky8](http://www.sendspace.com/file/8rlky8)
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-30T07:11:14+00:00
- Post Title: ipod .ani + .gtl files

pretty sure these are just the coordinates for the sprite animations

looked up a gameplay video. the sprite parts are just translated around the screen. plus those filenames are a dead giveaway    sorry
## Post #4
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-12-30T07:13:39+00:00
- Post Title: ipod .ani + .gtl files

I realized that quickly, but I found the archives that contain the sprite components I believe. The above .GTL files seem to be it.
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-30T07:16:45+00:00
- Post Title: ipod .ani + .gtl files

ah yes!

have you checked out existing converters?

[https://github.com/cocos2d/cocos2d-ipho ... ure.m#L121](https://github.com/cocos2d/cocos2d-iphone/blob/release-0.99.3/cocos2d/CCPVRTexture.m#L121)
## Post #6
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-12-30T07:27:13+00:00
- Post Title: ipod .ani + .gtl files

Ahaha...hoo boy...that would probably work if I knew what to do with it. I'm not very well educated on scripts...
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-30T07:35:47+00:00
- Post Title: ipod .ani + .gtl files

the pvr header isn't the same for this file

```
{
    uint32_t headerLength;
    uint32_t height;
    uint32_t width;
    uint32_t numMipmaps;
    uint32_t flags;
    uint32_t dataLength;
    uint32_t bpp;
    uint32_t bitmaskRed;
    uint32_t bitmaskGreen;
    uint32_t bitmaskBlue;
    uint32_t bitmaskAlpha;
    uint32_t pvrTag;   << expected to be ASCII "PVR!"
    uint32_t numSurfs;
} PVRTexHeader;

```


not sure what that means or if i found an outdated spec
## Post #8
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-12-30T07:38:03+00:00
- Post Title: ipod .ani + .gtl files

So I couldn't use this even if I knew how?

Ah man...this seems like it's gonna be another dead end for me...

Is there any hope for a simple method like xoring and running through filestripper, or maybe renaming it to a different, extractable archive?
## Post #9
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-12-30T08:21:11+00:00
- Post Title: ipod .ani + .gtl files

D'oh...I really need to look at these things more carefully. I just noticed the significance of the 'PVR!' thing. I found it in the hex of the file I'm trying to extract. How would this script work if I were to utilize it? Is there an engine that runs it?
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-30T08:29:11+00:00
- Post Title: ipod .ani + .gtl files

its an apple thing. i really have no clue   i used it as a reference for the file format

whats interesting about the enemiesc.gtl is the the magic (pvrTag) is at pos 43 and not 41
so oddly structured headers.

i've read up that the image size needs to be a power of 2, so instead of width and height, it could just store the "dimentions". maybe you should post in the graphic format section
