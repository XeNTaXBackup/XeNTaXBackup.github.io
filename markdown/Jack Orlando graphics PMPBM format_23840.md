## Post #1
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-06T23:27:55+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

Hi Guys

Is anyone tried to extract images from this game?

They are porobably stored in .PM / .PBM files.

I added examples.
I think MONEY.BM can be an object which Jack can pick up, AUTOJAC.PBM his car.
[jackorlando img.7z](https://xentaxbackup.github.io/file/20077_jackorlando img.7z)
## Post #2
- Username: Pejti
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-07T19:38:35+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

MONEY.BM can be easily viewed in texture finder [https://i.imgur.com/Me8qdKw.png](https://i.imgur.com/Me8qdKw.png)
File format is simple:
2 bytes (uint16) - width
2 bytes (uint16) - height
x bytes - image data

But AUTOJAC.PBM seems to be compressed.
## Post #3
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-07T21:43:51+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

Thank you for fast reply. I hope PBM files will not require reverse engineering of game.
## Post #4
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-10T20:56:20+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

Okay, now I have two files:

HYDRN_A is like BM file, so it can be viewed in TextureFinder (RGB565, 20x33, shift 4)
HYDRN_B is the same image but compressed

Question: is it possible to find out what method was used?
[hydr.zip](https://xentaxbackup.github.io/file/20102_hydr.zip)
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-10T22:10:51+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

Yeah, you could try to cut those 4 bytes at the beginning with some hex editor
and then use compression scanner [https://zenhax.com/viewtopic.php?t=23](https://zenhax.com/viewtopic.php?t=23)
## Post #6
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-11T01:39:04+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

Unfortunately this way did not bring any results but..

I found on github scummvm and there is described JackOrlando game engine and according to "graphics":

.PBM are RLE-compressed:
int16: Width in pixels.
int16: Height in pixels.
int16[]: 128-color palette.
byte[]: Row-first indices of each pixel. The first 7 bits are the index and the last bit is a RLE flag (if 1, repeat index by the value of the next byte).

Can you help me to convert it to simple BMP?
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-11T21:29:30+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

I have tried to make a working tool, but it seems that standard RLE implementations in Python doesn't work for me in this case.
As far as I know there are several types of RLE algorithms and the "flag" type (RLEB) needs to be used here.
You will find more info on this site [https://moddingwiki.shikadi.net/wiki/RLE_Compression](https://moddingwiki.shikadi.net/wiki/RLE_Compression)

I have also created a wiki article for future reference
[http://wiki.xentax.com/index.php/Jack_Orlando_PM_PBM](http://wiki.xentax.com/index.php/Jack_Orlando_PM_PBM)
## Post #8
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-12T12:45:21+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

Thanky you for your time. I will read about RLEB.
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-12T20:50:14+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

I have made some progress on this file format. Now, pixel data can be viewed in IrfanView.
Here is how converted AUTOJAC.PBM looks like [https://i.imgur.com/tZHoRXU.png](https://i.imgur.com/tZHoRXU.png)

But as you can see, I am struggling with converting palette for BMP output.
Anyway, here is my code
[https://github.com/bartlomiejduda/Tools ... BM_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Jack%20Orlando/Jack_Orlando_PBM_Tool.py)
## Post #10
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-13T12:31:12+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

I see that you made progress. In game car looks like this (I cut it from game screen):
[https://imgur.com/a/mCrPNbD](https://imgur.com/a/mCrPNbD)
[AUTO.png](https://xentaxbackup.github.io/file/20113_AUTO.png)
## Post #11
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-13T13:08:40+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

Ok, so we're close. But I'm not sure how to convert 128-color palette for BMP output, I've never done something like that and I hope that someone more experienced could help with this.
## Post #12
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-13T20:22:24+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

So, do you think palette colors are compressed/ in RGB565 mode? What I know that in palette colors have 3Bytes per color.
## Post #13
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-13T21:06:09+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

I know, I can edit post, but I decided to reply. ;P

I found out how palette works. Code is in TXT file. This info is also from github, scummvm. Thanks to SupSuper.
[jackpalette.zip](https://xentaxbackup.github.io/file/20116_jackpalette.zip)
## Post #14
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-13T21:33:27+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

According to documentation from github, this palette has 128 colors and 1 entry takes 2 bytes of space which means this should be 16-bit palette.
But as far as I know BMP needs 32-bit RGBA palette with 256 colors for 8-bit images [http://wiki.xentax.com/index.php/BMP_Image](http://wiki.xentax.com/index.php/BMP_Image)
That was the conversion I failed to achieve in my script (see the code that was commented).

It may be something easy to do, but I'm not sure how to proceed on that, even with the code you have shared.
Maybe you should raise a ticket on github to ask about this case?
## Post #15
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-14T13:38:32+00:00
- Post Title: Jack Orlando graphics PM/PBM format?

I don't know what more I can write. I spoke yesterday with guy which made Code which I shared but he didn't say more than we just know.
## Post #16
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-16T21:04:01+00:00
- Post Title: Re: Jack Orlando graphics PM/PBM format?

Many thanks to SupSuper for his tool.

Tool uses the same code which I shared for PBM files (palette color).
Simple tutorial ;p:
-open game archive
-find image (BM/PBM)
-click export

Except tool I added AUTOJAC.png - from one of game archive.
[https://imgur.com/a/k4kh88x](https://imgur.com/a/k4kh88x)

Thank you ikskoks for your time. ; )
[PakManager.zip](https://xentaxbackup.github.io/file/20146_PakManager.zip)
