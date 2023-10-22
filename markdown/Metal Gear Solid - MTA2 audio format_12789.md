## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-22T11:44:15+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

One user asked me if I can look at the sounds from Metal Gear Solid 4. So I checked bgm_mgo_title01.bgm and it looks like 4-channel audio encoded as ADPCM of some kind. 64-sample blocks. If we take first (uncompressed) samples from each block, this is the picture:



and it sounds like some music (probably looped at the end). Let's try some research on this.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-22T11:50:37+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

Here is an EBOOT.BIN file from the PS3 Demo version incase you need it assuming you are good at looking into game exe's for decoding algorithims.

I will find a MTAF sample file as soon as i find a working MGS 2 or 3 link.

Link Removed
EDIT: Also NOTE that the decoding algorithm for MTAF is inside the vgmstream.dll but I cannot find source code or a decompiled version of it from hcs.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-22T12:01:33+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

> Reply from OrangeC
>
> EDIT: Also NOTE that the decoding algorithm for MTAF is inside the vgmstream.dll but I cannot find source code or a decompiled version of it from hcs.

Yes I found his source, but now we need to know how different is MTA2 from MTAF. It may be very different.
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-22T12:08:32+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

Link Removed.

Here is an MTAF file.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-22T12:54:23+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

> Reply from OrangeC
>
> Here is an MTAF file.

ok, it is really different. 128 samples instead of 64 in MTA2, and probably another algorithm. I will keep you informed. bgm_mgo_lobby01.bgm has 12-channel streams. Weird. Maybe that are 3 parts of one 4-channel music track.
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-22T13:05:49+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

Okay thank you. I knew the format was somehow different.
## Post #7
- Username: GHzGangster
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 15, 2014 1:00 pm
- Post datetime: 2015-04-22T17:35:52+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

Love you guys.  

bgm_title_mgo has 3 phases/version for sure, each is usually more/less dramatic.

It seems like each phase is denoted by the first byte of each block, then the next 3 bytes are the frame number.
00 00 00 01 ... 0x12c more bytes...
01 00 00 01 ... 0x12c more bytes...
02 00 00 01 ... 0x12c more bytes...
It's like this. For each frame, each version of that frame comes right after.

That EBOOT.BIN is probably useless though. I haven't looked at it, but I'm fairly certain you uploaded the "bootloader". The file you're looking for is MGS4.SELF. I did some debugging, but it seems the sound decoding is done on one of the SPUs (faster than the regular CPU), and it isn't as easy to debug there. Therefore, it's probably some SPU code inside of the ELF, but I really have no experience with SPU stuff right now.

And about the OP, you mentioned taking the first "uncompressed" sample from each block. Did you just take some normal ADPCM algorithm and decode the first sample with that?

Also, just something to note... I was able to take the sample data from one MTA2 and swap it in with another MTA2, and the sound seemed to be playing just fine, other than the loop obviously not working. I don't think there is a lot in the MTA2 that really determines how the actual sample decoding itself is done.

And if you're interested, me and tbg have a Skype chat going on. PM me if you feel like talking about anything. We also emailed the owner of multimedia.cx, he said he would take a look at it, a while ago.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-22T18:13:44+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

Interesting stuff. So how did you manage to get the MTA2 samples playing when you did the swap thing?
## Post #9
- Username: SecaProject
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Apr 11, 2012 1:48 am
- Post datetime: 2015-04-22T18:26:16+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

I have some info about this files, but i don't know how to do a conversor, if you want i can share to you.
daemon1, you have a PM.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-22T18:29:05+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

> Reply from GHzGangster
>
> I did some debugging...

We actually don't need debugging. We just need ADPCM tables for this codec.

I didn't decode the first sample. It is saved in the ADPCM block unchanged. This is what I wanted to check and it was successful.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-22T18:34:48+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

> Reply from OrangeC
>
> Interesting stuff. So how did you manage to get the MTA2 samples playing when you did the swap thing?

Easily. They are all just a stream of 64 sample-blocks. You can replace them all you want.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-22T20:04:01+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

This is a comparison between the decoded first samples of each frame and same sound recorded from youtube. We can now try and guess where the sample shifts go to decode the whole frames.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-23T15:55:16+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

Each adpcm block has some 5-bit value. We are trying to find out what can it be. An index for some table, or just a scale?



It seem to correspond the original waveform posted on the top
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-25T10:32:21+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

We've calculated an approximate values in the table. Here's the first output. The red points are where the wave gets wrong, because the values are not accurate.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-28T20:44:30+00:00
- Post Title: Metal Gear Solid - MTA2 audio format

Today is a good day for MGS fans. MTA2 codec algorithm was finally figured out with all tables and values. We can now decode any audio from the game.
## Post #16
- Username: GHzGangster
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 15, 2014 1:00 pm
- Post datetime: 2015-05-01T21:35:22+00:00
- Post Title: Re: Metal Gear Solid - MTA2 audio format

I'm creating a general sound file encoder/decoder from Daemon's work, coming soon.
## Post #17
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2015-06-24T18:37:50+00:00
- Post Title: Re: Metal Gear Solid - MTA2 audio format

Cool to hear you've worked it out, any news?
## Post #18
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2015-07-04T06:26:59+00:00
- Post Title: Re: Metal Gear Solid - MTA2 audio format

> Reply from hcs
>
> Cool to hear you've worked it out, any news?

Decoder
[https://app.box.com/s/9en2aqajomma0rthxzv79ge506u3gb31](https://app.box.com/s/9en2aqajomma0rthxzv79ge506u3gb31)

[https://github.com/GHzGangster/Solid4](https://github.com/GHzGangster/Solid4)
## Post #19
- Username: GHzGangster
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 15, 2014 1:00 pm
- Post datetime: 2015-07-10T23:13:15+00:00
- Post Title: Re: Metal Gear Solid - MTA2 audio format

The JAR works for most files, it has trouble with very large files though (there is at least 1), I haven't reworked the memory stuff quite yet.
I'll fix that stuff up soon and upload stuff to my GitHub as well.
