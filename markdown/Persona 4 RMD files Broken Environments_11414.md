## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-04-13T23:21:49+00:00
- Post Title: Persona 4 RMD files Broken Environments

Hey Guys.

I know theres this topic here: [viewtopic.php?f=16&t=10760](http://forum.xentax.com/viewtopic.php?f=16&t=10760) that discusses the persona 4 RMD format, and even ends in the creation of an RMD viewer, which works great for character files, but for environments and buildings it just produces a huge confusing mess of planes and stretched textures

I've linked to a dropbox folder that contains 1 character model, the RMD viewer and an environment model for anyone who's interested in taking a look.

[https://www.dropbox.com/sh/azf19y7homu8qnj/u-JOQibN1q](https://www.dropbox.com/sh/azf19y7homu8qnj/u-JOQibN1q)

The interesting thing is, since the Persona 4 RMD format is the same as the Persona 3 RMD format, if we can open 4's environments perfectly, then 3's should work perfectly too, in theory.

If anyone wants the tools to extract from the CVM and Original iso too, I can add it into the dropbox too.

I can't seem to find the source code for the original RMD viewer unfortunately, but I think having support for the files in something like noesis would be better than having a seperate viewer, due to being able to export, and having good viewport controls.

Appreciate any help anyone can provide here.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-15T20:10:18+00:00
- Post Title: Persona 4 RMD files Broken Environments

M006_103.RMD
 0x41372: 384 vertices 3x float 
 0x40BDA 240 faces, face indices 4x UINT16, 3rd WORD (00 00) to skip



M006_103_RMD.JPG (20.76 KiB) Viewed 264 times
## Post #3
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2014-04-16T05:22:57+00:00
- Post Title: Persona 4 RMD files Broken Environments

I think the main issue with P3 and P4 is that they use some tileset for the model files for environments as well, to build the rooms as to where the files for them are I have no clue. That and some of the files from the game just don't load in there would be nice to get them all sorted out to work nicely and in noesis would be real nice.
## Post #4
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2014-04-17T04:45:19+00:00
- Post Title: Persona 4 RMD files Broken Environments

Here is an updated version of the viewer.
[PersonaViewer.rar](https://xentaxbackup.github.io/file/7223_PersonaViewer.rar)
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-04-18T00:03:30+00:00
- Post Title: Persona 4 RMD files Broken Environments

> Reply from prototypesky
>
> Here is an updated version of the viewer.

Wow thankyou, that works a LOT better than before, a lot of scenes are still broken up for some reason, but generall it works really well.

Is the viewer still actively being worked on?
## Post #6
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2014-04-18T06:50:19+00:00
- Post Title: Persona 4 RMD files Broken Environments

> Reply from prototypesky
>
> Here is an updated version of the viewer.

Possible to release a version that isn't in debug but in release?
## Post #7
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2014-04-26T16:36:52+00:00
- Post Title: Persona 4 RMD files Broken Environments

> Reply from lionheartuk
>
> prototypesky wrote:Here is an updated version of the viewer.

Wow thankyou, that works a LOT better than before, a lot of scenes are still broken up for some reason, but generall it works really well.

Is the viewer still actively being worked on?

I work on it form time to time I am still trying to figure out the animation part of the data.
I'll probably do a neosis plugin instead as suggested.
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-04-27T13:43:19+00:00
- Post Title: Persona 4 RMD files Broken Environments

> Reply from prototypesky
>
> lionheartuk wrote:prototypesky wrote:Here is an updated version of the viewer.

Wow thankyou, that works a LOT better than before, a lot of scenes are still broken up for some reason, but generall it works really well.

Is the viewer still actively being worked on?

I work on it form time to time I am still trying to figure out the animation part of the data.
I'll probably do a neosis plugin instead as suggested.

Ah thats great, a lot of the environments are still screwed up even on the new viewer, but they're much much better than before, still a lot of weird intersecting models and whatnot, but dramatically less so.

Great work, hugely appreciated.
## Post #9
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-09-12T23:13:40+00:00
- Post Title: Persona 4 RMD files Broken Environments

> Reply from prototypesky
>
> lionheartuk wrote:prototypesky wrote:Here is an updated version of the viewer.

Wow thankyou, that works a LOT better than before, a lot of scenes are still broken up for some reason, but generall it works really well.

Is the viewer still actively being worked on?

I work on it form time to time I am still trying to figure out the animation part of the data.
I'll probably do a neosis plugin instead as suggested.
Could you please post the source/RMD format spec?
