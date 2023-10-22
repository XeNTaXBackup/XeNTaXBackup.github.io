## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-01-02T01:02:30+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

It came quick to my attention that MS:SV001 uses a different TIM format (two examples provided). I opened one as raw and saw garbled sprites with frames and pallette data but the format could not be read unfortunately >_<.

I'm not sure how difficult it would be but I'll let you public be able to check it out while I do a lil of my own.
[OMAKE.rar](https://xentaxbackup.github.io/file/1013_OMAKE.rar)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-15T02:02:24+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Is this the correct palette ? 
[rawtim_ 1_xxxx.jpg](https://xentaxbackup.github.io/file/1054_rawtim_ 1_xxxx.jpg)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-16T03:32:42+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Looks great but I can't seem to find that image in the game, dangit. I only found similar in the image gallery but it didn't have "Another Story 2" on it.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-16T03:55:41+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

The palette is stored in the beginning of the files, as 16 bit values.
the conversion i made was simply by using the palette entries and plotted them out as 16 bit TGA color values for each color entry.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-16T12:12:03+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Looks awsome.  I'm sure there are other games out there that use this type of TIM.
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-16T13:34:18+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

There is just one single problem :X

The identification is pure shit. as the only identifier that shows
that it is this kind of format is a very vague 16 bit value.

so the level of false detection is currently very high ;D

but my beta version of jaeder does detect.

but i cant release it just yet because of my testing with the new
scanner, too much stuff that needs to be fixed before i dare to
release this one :X

Edit:
Okay. prototype alpha, take care 
[http://jaedernaub.ath.cx/Jaeder%20Naub%20V1.9.3c.zip](http://jaedernaub.ath.cx/Jaeder%20Naub%20V1.9.3c.zip)
(edit again, new release)

the high-end scanner is enabled by default.
if it starts crashing and other stuff, just unclick it.

there are numerous bugs related to the high-end scanner,
but overall it should work just fine unless you start trying to crash it 
, this TIM format is name Raw TIM on the optionscreen.
so click that if you are planning on converting more of those strange formats to TGA.

only tested it on 2 images though........
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-16T23:28:11+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Yeah, there are bugs but I managed to convert one and it looked alright XD

I suppose one of the bugs is that it stops scanning?
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-17T02:02:43+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

One bug i know of is that the scanner looks like it stops.
(often near the end), this is however just a display bug,
the file should have been scanned anyways =X

but if it stops just randomly in the beginning or middle then
its probably a new bug.

and now a new alpha for public testing! =D

[http://jaedernaub.ath.cx/Jaeder%20Naub%20V1.9.3c.zip](http://jaedernaub.ath.cx/Jaeder%20Naub%20V1.9.3c.zip)
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-17T20:45:12+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

The bug that locked the file selection when a folder was entered is now gone. It runs smoothly now except it overwrites files when it scans another. And the images turn out flipped but can be fixed in an image editing program. So it looks good. The colors and such look right except for some background TIMs which don't all seem to be recognised.

I have noticed somthing though, the TIMs with sprites differ from the loading screens.

[http://www.megaupload.com/?d=5U6OEBHL](http://www.megaupload.com/?d=5U6OEBHL)

Here are some of the sprite TIMs
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-18T00:49:42+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Not that i saw some sprites on those images 

i could only see fullsize images! 
but anyways, they are now rippable/convertable aswell.

[http://jaedernaub.ath.cx/](http://jaedernaub.ath.cx/)

And, the Raw TIM files are no longer overwriting eachother.
now they will just add an .tga extension instead to the original name
of the file.
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-18T09:28:52+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Kudos Strobe, 

Alright! We've gotten somewhere! These are the art gallery pictures and a perfect oppertunity to get the right color map  it looked good but I realised somthing... the colors are inverted! Which means perhaps the palette is backwards. 

The ripped version from JN (flipped):


The ingame version:


This is the file: S15.TIM

Also, inside the TAR is a 7Z (it came out smaller than an RAR), I couldn't post the 7Z so I stored it in a TAR.

This pattern seems to be consistent with the other TIMs.
[S15.tar](https://xentaxbackup.github.io/file/1063_S15.tar)
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-18T12:22:05+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Yeah.......im noticing that now....

they have an own pixelformat.
they are not using regular 16 bit colors,
the R and B bits are switched, the G bits are though intact...



bah...working on a fix  ....
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-18T12:41:28+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Yeah, the images are perfect. Just the colors are slightly off. Shadeing remains intact. I was working to get an image to reference to that would show this best. But the quality of the rip is otherwise amazing.
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-20T03:48:51+00:00
- Post Title: (PSX) Metal Slug - Super Vehicle 001 [TIM format Unknown]

Ok, found the sprite TIMs and background TIMs I stupidly enough forgot all about >_<

I think this is the final TIM type used in the game (other than backgrounds).
[GAME31.rar](https://xentaxbackup.github.io/file/1065_GAME31.rar)
