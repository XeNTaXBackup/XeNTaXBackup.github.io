## Post #1
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-06T04:55:50+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

Hey guys, I'm trying to get my head around the texture files for Ghostbusters on the PS3 and the Ghostbusters Tex to DDS converter doesn't seem to work -- I suspect because it's for the PC version. It converts without issue but I can't seem to open the DDS files themselves. Anyone able to take a look and tell me what I should be doing?

Here's a sample of the .tex files I'm looking at: [https://www.sendspace.com/file/yts34i](https://www.sendspace.com/file/yts34i)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-06T05:49:32+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

here is a Noesis python script that can open your sample  
*updated April 13, 2017*


 tex_Ghostbusters_PS3_X360_tex.zip
(817 Bytes) Downloaded 87 times


no support for bump textures, i don't know what format they are
## Post #3
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-06T06:08:52+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

Thanks Ace! I was hoping you might be able to help! I'm a little unfamiliar with the different formats, but I assume it has something to do with the others not showing up? Would these help? 

Body2_aocc
[https://www.sendspace.com/file/org3gg](https://www.sendspace.com/file/org3gg)

Body2_bump
[https://www.sendspace.com/file/zucqxr](https://www.sendspace.com/file/zucqxr)

Body2_diff
[https://www.sendspace.com/file/snde4a](https://www.sendspace.com/file/snde4a)

EDIT: I've dug in a little deeper and found these TGA files -- they seem to be the same as the TEX files, but I can't seem to find a way of opening them... anyone got any ideas?

Azetlor_diff.tga
[https://www.sendspace.com/file/fvjzbb](https://www.sendspace.com/file/fvjzbb)

Azetlor_bump.tga
[https://www.sendspace.com/file/jcvklv](https://www.sendspace.com/file/jcvklv)

Azetlor_spec.tga
[https://www.sendspace.com/file/sjmgk1](https://www.sendspace.com/file/sjmgk1)
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-01-06T10:20:23+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

new examples looks compressed and swizzled (PVR?) :/ 

are from ps3, right?  (the tex files and tga are the same formats after all, maybe with different headers but same data composition)
## Post #5
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-06T10:23:01+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

> Reply from luxox18
>
> new examples looks compressed and swizzled (PVR?) :/ 

are from ps3, right?  (the tex files and tga are the same formats after all, maybe with different headers but same data composition)

Thanks for looking man! They're from the Xbox 360 version
## Post #6
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-01-06T10:35:57+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

> Reply from trexjones
>
> Thanks for looking man! They're from the Xbox 360 version

I suspected that haha, I'm not very familiarized with xbox 360 texture formats but looks like a variant of the xpr format ( very common in that console)
## Post #7
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-06T11:37:39+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

Any idea what I could use to convert them to something usable?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-06T12:52:39+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

i updated the previous Noesis script to support both your new X360 samples
and the PS3 samples, except for the bump textures, no idea what they are
## Post #9
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-01-06T20:55:06+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

I can't define the bump texture too, I think (and only think) that is based in tga format rgba
## Post #10
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-07T08:05:17+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

Really appreciate you guys taking a look at these -- if you guys are stumped then I had NO hope!
## Post #11
- Username: loko
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 29, 2017 11:34 pm
- Post datetime: 2017-06-29T15:48:25+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

Hello AceWell;

Can you help me with this same format (.TEX) but for other game (Metal Slug)?

Here are two example files: [https://www.dropbox.com/sh/x0lzqu2ly9b3 ... 7REla?dl=0](https://www.dropbox.com/sh/x0lzqu2ly9b33tq/AABAlJi7y0HNlQkr2ZXV7REla?dl=0)


Thanks in advance!!
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-01T06:51:09+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

this game for PC right?
[http://store.steampowered.com/app/366250/METAL_SLUG/](http://store.steampowered.com/app/366250/METAL_SLUG/)

i have no idea what they are, could be palletized textures which i'm no good at, maybe herbert3000 knows more.
## Post #13
- Username: loko
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 29, 2017 11:34 pm
- Post datetime: 2017-07-01T11:57:35+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

I extracted those files from the .POD (Using Dragon Unpacker).  They are from the Wii version (Metal Slug Anthology).

Someone posted a script for the .TEX files for this game a few years ago...
[viewtopic.php?f=18&t=12568](http://forum.xentax.com/viewtopic.php?f=18&t=12568)

Sadly, that script only worked for the PSP version (Even when they are the same file format ".TEX").  Could you check the link with the script? Maybe can help...

Thanks in any case AceWell!
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-02T03:17:10+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

no luck man, i just can't work with palletized texture data, and adding to the problem they are from a console
that i rarely have luck with anyway.   
i usually deal with PC, Xbox, X360, PS3 and sometimes PSVita, PSP and rarely ever Wii samples and thats all. 
"tex" is not a format, just a useless extension used by whatever this format is, i could show you a hundred samples
with the "tex" extension that have different headers or structure be it compressed, swizzled, raw, headerless etc.
i still say have herbert3000 or barti take a look since they know how to deal with this data successfully.
## Post #15
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2023-07-06T09:56:52+00:00
- Post Title: Ghostbusters PS3 .tex files not converting to .DDS?

With the help of Stargayzer we fixed the .tex files that can be found in the .pkg file now they can be exported correctly (note: we only fixed the textures that can be opened but they have horizontal lines)
[GB_PS3_XB360.rar](https://xentaxbackup.github.io/file/24027_GB_PS3_XB360.rar)
## Post #16
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-07-11T08:32:46+00:00
- Post Title: Re: Ghostbusters PS3 .tex files not converting to .DDS?

@loko Regarding your Metal Slug textures, they are 8-bits per pixel 8x4 tiles (like one of the GameCube formats). I don't know any scripts/tools to import/export them, nor where the palette is stored, but that might give you more info to find something that does.
[MetalSlugTiled8bpp8x4.png](https://xentaxbackup.github.io/file/24062_MetalSlugTiled8bpp8x4.png)
