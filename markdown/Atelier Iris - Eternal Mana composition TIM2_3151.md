## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-10T23:09:31+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

I used PCSX2 to dump data from the running game and came up with some interesting results, primarily uncompressed graphics of different items. Among these I got this which seems to be a TIM2 composed of several character sprite sheets each with their individual palettes and other data. When I use TIM2TGA it comes up weird so help is appreciated.

[The seemingly compound TIM2](https://www.yousendit.com/download/bVlDQmtYT2JqY3FGa1E9PQ)

This file seems to contain all the uncompressed sprites used in the current screen. Including the pig which is the EXACT sprite used for the save screen. It was not easy retrieving these. Even in the dump many graphics are still LZR compressed... -_-

Edit: Yep! It is confirmed that dumping the last couple files of  Atelier games will give the uncompressed graphics!  Next is of course converting them properly...
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-12T02:15:14+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Here's another, it contains a couple pictures, a conversion of the top stuff and an example of a monster (Wolf).

[Another example](http://www.yousendit.com/download/bVlDb3BDOC84NVdGa1E9PQ)

And I'll also attach an example image of the pig.
[Pig.png](https://xentaxbackup.github.io/file/1640_Pig.png)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-12T06:33:27+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Here's a whole bunch of compound TIM2s: [Here](http://www.yousendit.com/download/bVlDb3BBMm1tNElLSkE9PQ)

In there it shows what TIM2TGA spits out. TIM2TGA does not support this form of TIM2. Any way a program that could split the compound TIM2 up into several TGAs could be made? The graphics are all uncompressed, the palettes are intact, and so on but the TIM2 is a chimera composed of several graphic segments totally different from each other.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-12T22:48:05+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

No current TIM2 handling software can convert these images, I have already tried them all. Seems this is an Atelier specific format.

I've tried hexing it so that the next image is first but I don't know what the heck I'm doing...
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-17T03:28:39+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Sorry to bump this again but it seems to me that all data is contained and would require only some way to split them up as separate images. They are uncompressed, unswizled or however it is called and seem straight forward. Only problem is, no TIM2 programs convert/view them properly. The only thing that may show up is the TIM2 that starts it off.

Perhaps they are a separate image format that SEEMS to attach itself to the TIM2 that has no header or so it seems to me anyways... no available tools work for this.
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-19T00:21:54+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Any ideas yet? I'll assume that many are busy but I figured such a format would be straight forward. Must be pretty busy times, I'd do it but I have little experience with images. Just a bit with sounds.

I noticed bars of data I assume are palettes and height/width data.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-30T19:07:04+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Anymore of these necessary? I haven't given up on this just yet. Please someone crack this, maybe even get a converter/splitter working for it. It'd be most appreciated. 

Thanks for your time.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-26T07:47:16+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Has anyone found anything with these images? It's been a while since I last looked at them but I'm still interested in converting/viewing them.
## Post #9
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-11-26T23:23:47+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

I wouldnt mind looking but all the links are expired.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-27T05:54:30+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Dump 1: [http://www.sendspace.com/file/4ui7g2](http://www.sendspace.com/file/4ui7g2)

Dump 2: [http://www.sendspace.com/file/swindc](http://www.sendspace.com/file/swindc)

And thanks!
## Post #11
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-11-30T02:52:21+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Probally not much help, but I can tell you this is some sort of compressed image format like DXT. All I was able to locate was the height and width.
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-30T04:29:16+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Well the thing is, the graphics are not compressed. They are fully uncompressed and similar to TIM2 graphics.

How I know they are not compressed is because I can view the graphics perfectly with any texture viewer... albeit without palettes. Also, each TIM2 does have a palette. The composition TIM2s might have a palette index.
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-02-07T04:53:43+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Using the VRAM dump method leaves the graphics decompressed and includes the palette data intact. I don't see the compression you are speaking of.
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-03-15T18:53:55+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

Will I need to upload a new sample? Because I'm really starting to want to convert these.
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-03-27T10:37:23+00:00
- Post Title: Atelier Iris - Eternal Mana composition TIM2?

[http://www.sendspace.com/file/usmrej](http://www.sendspace.com/file/usmrej)

NOT compressed, NOT encrypted. As I see it using a viewer, it's a pretty clear picture (the TGA shows the first image converted), there are obvious palettes but I am having difficulty using them in the viewers I have. I will provide screenshots of the graphics presented...

Edit: Here is what the one graphic looks like colorized (the cat).
[Werecat.png](https://xentaxbackup.github.io/file/1943_Werecat.png)
## Post #16
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-06-09T09:08:21+00:00
- Post Title: Re: Atelier Iris - Eternal Mana composition TIM2?

Here's the TIM2 that contains the were cat sheet. I cut it down to be able to get it in there and show the specific test image.
[dump13Cut.rar](https://xentaxbackup.github.io/file/2090_dump13Cut.rar)
## Post #17
- Username: wizzardx
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jun 14, 2009 8:34 pm
- Post datetime: 2009-06-21T11:31:12+00:00
- Post Title: Re: Atelier Iris - Eternal Mana composition TIM2?

This topic is relevant to my interests.

>_>.

I've worked a lot with GUST graphics (usually after extracting with Lilie). In a forum I frequent, we've worked with them a bit, to make animated gifs, for instance:

[http://artonelico.isisview.org/wiki/ind ... a%27s_GIFs](http://artonelico.isisview.org/wiki/index.php/Eleinia%27s_GIFs)

What kind of tools do you normally work with, to view/extract/etc/tm2 files? It sounds like you are using some kind of advanced options in e2psxe to dump video data. Mind giving me links where I can read more on these tools/techniques?

I've used the tim2tga converter, but it fails >.<. I asked the author about it, and he recommended taking a look at the source code for Photoshop's TIM plugin. I'd like to do that sometime, to make a command-line converter. But, I'm lazy, and I don't use Windows, Visual Studio, or Photoshop >_>.

Actually, this very forum has a few links, including the above plugin ^^.

[viewtopic.php?f=18&t=2164](http://forum.xentax.com/viewtopic.php?f=18&t=2164)

Edit: Also, I tried taking a look at your attachments, but those links were offline. I probably can't do anything with them, but I'm interested in how they look. If it's just simple image editing I can code that (for instance, I wrote a program that extracts individual sprite images from GUST sprite sheets, and adds transparency).
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-06-21T23:22:04+00:00
- Post Title: Re: Atelier Iris - Eternal Mana composition TIM2?

What format are the sprite sheets normally in? TIM2 or just regular TIM? I've noticed so far that the item images are normal PSX TIM images.
## Post #19
- Username: wizzardx
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jun 14, 2009 8:34 pm
- Post datetime: 2009-08-21T13:49:17+00:00
- Post Title: Re: Atelier Iris - Eternal Mana composition TIM2?

The game actually has images in both formats.
