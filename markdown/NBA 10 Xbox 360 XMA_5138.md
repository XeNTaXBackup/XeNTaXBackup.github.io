## Post #1
- Username: 1212fg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 03, 2010 9:07 pm
- Post datetime: 2010-10-04T09:54:34+00:00
- Post Title: NBA 10 Xbox 360 XMA

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-06T10:06:47+00:00
- Post Title: NBA 10 Xbox 360 XMA

Without downloading (I'm currently not at my PC), *.sns files are normally EALayer3 - look into the main topic for the decoder and play around with it a bit..
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-10-06T11:45:32+00:00
- Post Title: NBA 10 Xbox 360 XMA

I ran the posted SNS file through the ealayer3 parser with no luck.
Looks to be the same format as the other sns file I have (from Sims 3) but I dont know what codec its using or why its not parsing properly.
## Post #4
- Username: 1212fg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 03, 2010 9:07 pm
- Post datetime: 2010-10-06T12:10:37+00:00
- Post Title: NBA 10 Xbox 360 XMA

First i msg Zench, he answered "It's XMA; EA Layer 3 is for PC only. I'm unfortunately not very knowledgeable about XMA, but if you post this in a new topic someone might be able to help you."
## Post #5
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-10-06T22:57:12+00:00
- Post Title: NBA 10 Xbox 360 XMA

WRONG.
Quoting from the Red Alert 3 Mod SDK we have:
PCAudioCompressionSetting
NONE
XAS
EALAYER3

XenonAudioCompressionSetting
NONE
XMA
EALAYER3

PS3AudioCompressionSetting
XAS
EALAYER3

XAS is an EA invented ADPCM variant (which has been decoded and is fully understood)
## Post #6
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-10-07T21:46:46+00:00
- Post Title: NBA 10 Xbox 360 XMA

First of all, this is not an EALayer3 file. I've examined it very thoroughly, and I am confident. Try running it though hcs's [ea_multi_xma](http://hcs64.com/vgm_ripping.html).

jfwfreo, a modding SDK is not a very good source to cite. I could not find that text anywhere on the internet either; just because it's listed doesn't necessarily mean it's used. All you would have needed to do is find an instance where EALayer3 has been used in a console video game. But it isn't; EALayer3 is based off of MPEG audio layer 3, which, to decode in software requires quite a bit of complexity. Much more than simple ADPCM variants. It would be unwise for a console game developer to waste processing power decoding EALayer3 over, say, XMA which is decoded in hardware. For PCs this is not a problem.
## Post #7
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-10-07T23:54:10+00:00
- Post Title: NBA 10 Xbox 360 XMA

Regardless of what they may have done on 360, its clear they are using EALayer3 for the Playstation 3 version of Red Alert 3. EA themselves said that EA XAS ADPCM is not suitable for music so PS3 is clearly using EALayer3.

The way to answer it once and for all would be to find copies of data from the 360 and PS3 games so it can be analyzed.
## Post #8
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-10-08T00:16:20+00:00
- Post Title: NBA 10 Xbox 360 XMA

Well, then, I guess you're right in that respect.

> Reply from jfwfreo
>
> The way to answer it once and for all would be to find copies of data from the 360 and PS3 games so it can be analyzed.Well, you can do that if you want but it doesn't matter so much to me.  

Anyways, let's get back on topic.
## Post #9
- Username: 1212fg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 03, 2010 9:07 pm
- Post datetime: 2010-10-08T14:06:04+00:00
- Post Title: NBA 10 Xbox 360 XMA

finally i got WAVs, used hsc tools [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)

```
FOR %%a IN (*.sns_stream1) DO xma_test "%%a" -o 800 -b 10000 -r "%%a.bin"
FOR %%a IN (*.bin) DO copy /b riffheader.hed + "%%a" "%%a.xma2"
DEL *.bin
FOR %%a IN (*.xma2) DO towav "%%a"
DEL *.xma2

```

there is one problem song speed is too fast
## Post #10
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-10-09T14:09:36+00:00
- Post Title: NBA 10 Xbox 360 XMA

You would need to change the frequency in riffheader.hed to 24000.
## Post #11
- Username: 1212fg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 03, 2010 9:07 pm
- Post datetime: 2010-10-09T16:43:39+00:00
- Post Title: NBA 10 Xbox 360 XMA

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-10-10T14:56:56+00:00
- Post Title: NBA 10 Xbox 360 XMA

Heh...this is the header I made for my XMA convert kits...
[riffheader24khz.zip](https://xentaxbackup.github.io/file/3508_riffheader24khz.zip)
## Post #13
- Username: 1212fg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 03, 2010 9:07 pm
- Post datetime: 2010-10-10T16:31:19+00:00
- Post Title: NBA 10 Xbox 360 XMA

> Reply from bxaimc
>
> Heh...this is the header I made for my XMA convert kits...
not fit, i guess it must be 44,1 khz header, have You got this header?
## Post #14
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-10-11T14:30:14+00:00
- Post Title: NBA 10 Xbox 360 XMA

EA is generally using XMA for all in 360 games what i've seen, plus using ealayer3 in x360 would demand software decode making it slower.
