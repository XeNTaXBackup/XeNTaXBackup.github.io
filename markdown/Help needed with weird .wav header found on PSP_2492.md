## Post #1
- Username: Killy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 27, 2006 2:11 am
- Post datetime: 2007-03-02T19:43:44+00:00
- Post Title: Help needed with weird .wav header found on PSP

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-02T21:51:37+00:00
- Post Title: Help needed with weird .wav header found on PSP

Can attach a sample?
## Post #3
- Username: Killy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 27, 2006 2:11 am
- Post datetime: 2007-03-02T23:14:05+00:00
- Post Title: Help needed with weird .wav header found on PSP

I added a sendspace link at the bottom... -_- attachments don't work.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-03T00:22:11+00:00
- Post Title: Help needed with weird .wav header found on PSP

Likely because it exceeds 256kbs. There's a 256kb limit.
## Post #5
- Username: Killy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 27, 2006 2:11 am
- Post datetime: 2007-03-03T00:47:18+00:00
- Post Title: Help needed with weird .wav header found on PSP

... I knew that already. The file is 250kb. Attachements do not work, I don't know why, I get an internal server error mesage. However... none of that is relevant. Would anyone actually care to help me and answer my question..? :/
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-03T01:42:26+00:00
- Post Title: Help needed with weird .wav header found on PSP

Though Strobe might do this I will find a utility. I thought it was for the PS2 format but was really PSP audio conversion I was looking at. So I'm trying to find that.

Alright! I got somthing you might like. 

[ATRAC3 Audio Codec](http://www.free-codecs.com/download/Sony_ATRAC3_Audio_Codec.htm)

This is a codec that would allow the conversion from and to the PSP standard.

Now for some bad news. The example you gave seems corrupted. >_< My Windows Media Player recognises the codec but gives an error so somthing is amiss.
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-03T01:58:59+00:00
- Post Title: Help needed with weird .wav header found on PSP

Normally PSP waved audio are Atrac3 or Atrac3 plus i only have the atrac3 acm, so maybe it's atrac3plus

I think Sonic Stage can open this file
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-03T02:52:53+00:00
- Post Title: Help needed with weird .wav header found on PSP

Hard to say really. But I suppose best bet is Sonic Stage. Though I am testing somthing I found. Tell you what the results are.
## Post #9
- Username: Killy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 27, 2006 2:11 am
- Post datetime: 2007-03-03T11:14:50+00:00
- Post Title: Help needed with weird .wav header found on PSP

I don't mean to be rude or anything, but the Atrac codec is old news... I would usually use GoldWave or Sound Forge to open the files, but it doesn't work I'm afraid, which is why I feel that I have no other choice but to hex my way through.

Is there really nothing that can be done? I haven't tried Sonic Stage, would you guys let me know if there's any success with it?
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-03-05T08:48:28+00:00
- Post Title: Help needed with weird .wav header found on PSP

just a fast reply here, yes, this is Atrac3 Plus.
the codec ID for this is 0xFEFF and is utilized by new firmware 
by the PSP. there is yet NO Atrac3 Plus codecs out there for
windows, only standard Atrac3. =(

so.....currently you cant do shit about it =X
## Post #11
- Username: Killy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 27, 2006 2:11 am
- Post datetime: 2007-03-05T11:37:48+00:00
- Post Title: Help needed with weird .wav header found on PSP

Aw crap, but oh well, thanks for clearing that up Strobe, much appreciated.  In regard, thanks for your previous help as well!
## Post #12
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2007-03-12T19:50:53+00:00
- Post Title: Help needed with weird .wav header found on PSP

just for letting you guys know.
im on the case reversing the atrac3Plus format

/funtex
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-13T01:11:35+00:00
- Post Title: Help needed with weird .wav header found on PSP

Good luck, FunteX. Do tell if you find out anything.
## Post #14
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2007-03-15T09:36:45+00:00
- Post Title: Help needed with weird .wav header found on PSP

UPDATE:

i've made a little research and have found that in sony's audio products (Cinescore, ACiD Pro, and so on) is there an Atract plug-in capable of Decoding and Encoding to Atrac, Atrac3Plus and Atract Advanced Lossless (.aa3 and .oma included) files.

so if we can help each other reversing the calling routines and making a gui for that dll, then we have a working encoder/decoder for the atrac format series.

cheers 
FunteX
## Post #15
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-07-04T18:13:39+00:00
- Post Title: Help needed with weird .wav header found on PSP

Any update on this?

Im tryign to convert the king kong music file from PSP.
## Post #16
- Username: samwh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 25, 2007 8:13 am
- Post datetime: 2007-07-31T22:00:41+00:00
- Post Title: 

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: fastelbja
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 09, 2007 3:05 am
- Post datetime: 2007-12-20T19:28:55+00:00
- Post Title: 

if someone is still interested in,

here is the converted file bgm11.at3 to wav :

[http://rapidshare.de/files/38094790/0_oma.wav.html](http://rapidshare.de/files/38094790/0_oma.wav.html)

tell me if u want info on how to do that
## Post #18
- Username: bias
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 24, 2008 4:22 am
- Post datetime: 2008-04-14T18:06:09+00:00
- Post Title: 

> Reply from fastelbja
>
> if someone is still interested in,
(...)
tell me if u want info on how to do that

i would very much be interested in it.
i send you PM.

thanks.
## Post #19
- Username: triton
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Mar 05, 2007 10:41 am
- Post datetime: 2008-04-18T18:51:02+00:00
- Post Title: 

Why not just post at the thread?
## Post #20
- Username: bias
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 24, 2008 4:22 am
- Post datetime: 2008-05-08T19:27:28+00:00
- Post Title: 

> Reply from triton
>
> Why not just post at the thread?

equal to me.
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-09T00:03:57+00:00
- Post Title: 

Doesn't the program Hi-MD renderer convert Atrac3?
## Post #22
- Username: bias
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 24, 2008 4:22 am
- Post datetime: 2008-05-11T15:06:01+00:00
- Post Title: 

> Reply from OrangeC
>
> Doesn't the program Hi-MD renderer convert Atrac3?

i tried it and it works!
