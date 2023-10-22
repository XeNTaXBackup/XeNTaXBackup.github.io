## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-17T12:26:44+00:00
- Post Title: help ntp3 to dds

Hi all
I have some textures in .nut file from Naruto Shippuden:Ultimate Ninja Storm 2
File headers are in "NTP3", the similar format Idolm@ster uses for texture files.
I don't know how to convert nut file to dds file.
Just open the nut file to TextureFinder.


Can someone help me convert nut to dds!!!

Here is some nut file
[http://www.mediafire.com/?x4bybrqy0e427hi](http://www.mediafire.com/?x4bybrqy0e427hi)
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-18T02:50:34+00:00
- Post Title: help ntp3 to dds

Here is another nut file.




Is no one interested in this post.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-18T04:02:02+00:00
- Post Title: help ntp3 to dds

try this it may work its probably the same format.
[viewtopic.php?f=16&t=4814](http://forum.xentax.com/viewtopic.php?f=16&t=4814)
## Post #4
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-18T04:18:23+00:00
- Post Title: help ntp3 to dds

> Reply from chrrox
>
> try this it may work its probably the same format.
viewtopic.php?f=16&t=4814
Thanks for your interest.
But, an error has occurred
## Post #5
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-01-18T21:13:35+00:00
- Post Title: help ntp3 to dds

I saw NT*3 somewhere before... *thinks* Right!
Eternal Sonata features NTX3 files in the XBOX 360 demo (Probably the 'X' is for XBOX and the 'P' for Playstation),
they also have the same structure.

But there was something else... *thinks* ah...., .nut files! I remember them from Tales of Symphonia (PS2 version)! They had TIM2 instead of NT*3
(funny thing I was currently working on them anyways )

All of them (ES,ToS and those files) have the same structure (eXt and GIDX readable in the first few bytes)



I will start tomorrow to write a generic .nut converter (will take 2-3 weeks I'm slow  ) with a GUI
because this seems useful for multiple games and the format seems pretty straightforward.



Alternatively if you just want a few files converted I can do it by hand (slapping a custom DDS header on them)



Edit after reading linked topic above:
Maybe just changing the endianess in the script to little could do the trick, PS3 is little endian if I remember correct (didn't test it)
## Post #6
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-19T04:49:03+00:00
- Post Title: help ntp3 to dds

> Reply from 0xFAIL
>
> I saw NT*3 somewhere before... *thinks* Right!
Eternal Sonata features NTX3 files in the XBOX 360 demo (Probably the 'X' is for XBOX and the 'P' for Playstation),
they also have the same structure.
But there was something else... *thinks* ah...., .nut files! I remember them from Tales of Symphonia (PS2 version)! They had TIM2 instead of NT*3
(funny thing I was currently working on them anyways )
All of them (ES,ToS and those files) have the same structure (eXt and GIDX readable in the first few bytes)
I will start tomorrow to write a generic .nut converter (will take 2-3 weeks I'm slow  ) with a GUI
because this seems useful for multiple games and the format seems pretty straightforward.
Alternatively if you just want a few files converted I can do it by hand (slapping a custom DDS header on them)
Edit after reading linked topic above:
Maybe just changing the endianess in the script to little could do the trick, PS3 is little endian if I remember correct (didn't test it)
Thanks for your interest.
I'm looking forward to it.
## Post #7
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-01-19T07:45:27+00:00
- Post Title: help ntp3 to dds

I will update here, but if you want to see the progress live:
Repository Link

Currently researching all the files.

Eternal Sonata looks like the header is slightly different.
## Post #8
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-19T18:34:35+00:00
- Post Title: help ntp3 to dds

> Reply from 0xFAIL
>
> I will update here, but if you want to see the progress live:
Repository Link

Currently researching all the files.

Eternal Sonata looks like the header is slightly different.
At least four ntp3 that i know of.
Naruto Narutimate Storm(=Naruto Ultimate Ninja Storm)
Naruto Shippuden: Narutimate Storm 2(=Naruto Shippuden: Ultimate Ninja Storm 2)
Dragon Ball Z: Burst Limit
## Post #9
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-01-21T18:14:00+00:00
- Post Title: help ntp3 to dds

Progress!

Figured out most of the Tales of Symphonia .nut file structure and it matches with the NTP3 files.
(see [LINK](https://github.com/0xFAIL/0xFAIL_Toolbox/blob/master/Tools/Graphics/generic_file_formats/DOC/generic_file_formats.txt) for results)

What I would like to have:
3 (or more) example files per game (please make a new folder for each game) in a zip file uploaded to mediafire.
Could you upload them please?

Why are the files needed?
I have to look if there are any more image data formats.
So far I only have found DXTn and 8BPP+256 Color CLUT.

What comes next?
1)Completing file spec.
2)completing DDS header creator in the toolbox.
3)Writing converter.
## Post #10
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-21T18:54:57+00:00
- Post Title: help ntp3 to dds

> Reply from 0xFAIL
>
> Progress!

Figured out most of the Tales of Symphonia .nut file structure and it matches with the NTP3 files.
(see LINK for results)

What I would like to have:
3 (or more) example files per game (please make a new folder for each game) in a zip file uploaded to mediafire.
Could you upload them please?

Why are the files needed?
I have to look if there are any more image data formats.
So far I only have found DXTn and 8BPP+256 Color CLUT.

What comes next?
1)Completing file spec.
2)completing DDS header creator in the toolbox.
3)Writing converter.
The related file had been sent as an attachment to PM.
## Post #11
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-01-28T08:02:31+00:00
- Post Title: help ntp3 to dds

Any news about the ntp3 format?
## Post #12
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-01-30T00:45:26+00:00
- Post Title: help ntp3 to dds

Short update

I'm currently having a problem with the Mip Maps, I have to find a way to reliablely detect them (and the irregular header that
comes with them).

Also working on the DDS header generator is slow cause I have to understand DXT/STC3 a bit more.
## Post #13
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2012-02-09T23:37:40+00:00
- Post Title: help ntp3 to dds

star fox assault has a .nut and it is also a namco game see if it helps
[nud_pack_12.rar](https://xentaxbackup.github.io/file/5049_nud_pack_12.rar)
## Post #14
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-05T01:33:18+00:00
- Post Title: help ntp3 to dds

Here's a NTP3 unpack quickbms script

```
endian big
get version short
get files short
goto 0x10
for i = 0 < files
savepos offset
get size long
get name basename
string name + i
string name + .dds
log name offset size
math offset + size
goto offset
next i
```


I have altered chrrox's NTXR quickbms script.
[viewtopic.php?p=40987#p40987](http://forum.xentax.com/viewtopic.php?p=40987#p40987)
## Post #15
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2012-09-01T01:00:51+00:00
- Post Title: help ntp3 to dds

Ugh, so close and yet so far away lol. Trying to find Pain's Cloak Texture T_________T maybe im not looking in right place... /sigh
## Post #16
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-03-31T06:18:38+00:00
- Post Title: Re: help ntp3 to dds

> Reply from 0xFAIL
>
> I saw NT*3 somewhere before... *thinks* Right!
Eternal Sonata features NTX3 files in the XBOX 360 demo (Probably the 'X' is for XBOX and the 'P' for Playstation),
they also have the same structure.

But there was something else... *thinks* ah...., .nut files! I remember them from Tales of Symphonia (PS2 version)! They had TIM2 instead of NT*3
(funny thing I was currently working on them anyways )

All of them (ES,ToS and those files) have the same structure (eXt and GIDX readable in the first few bytes)



I will start tomorrow to write a generic .nut converter (will take 2-3 weeks I'm slow  ) with a GUI
because this seems useful for multiple games and the format seems pretty straightforward.



Alternatively if you just want a few files converted I can do it by hand (slapping a custom DDS header on them)



Edit after reading linked topic above:
Maybe just changing the endianess in the script to little could do the trick, PS3 is little endian if I remember correct (didn't test it)
How to readable GIDX file? Thanks for help!
[xfgame_cmn.fnt.rar](https://xentaxbackup.github.io/file/7153_xfgame_cmn.fnt.rar)
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-31T12:32:20+00:00
- Post Title: Re: help ntp3 to dds

Hm, NTP3 header just like Tekken Revolution (PS3) has, along with GIDX. Also Tekken Tag 2 uses GIDX. I'm sure if you swap header you can open them in Noesis.
