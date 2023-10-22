## Post #1
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-07-13T04:36:30+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

Hello, I have a question about the MGS3 music files. I have asked a couple people here but they have not yet had time to look at the files, therefore I thought I would just throw this out to the community to examine.

I have found a program that lets me extract the music files from Metal Gear Solid 3: Subsistance (PS2). It extracts the music perfectly, the problem is, it does not convert it. The extension is .raw, however it definitely isn't the .raw that's compatible with Winamp, it is not recognized by Goldwave either.

Here is the one of the music files that I extracted: 

```
http://www.megaupload.com/?d=HNW8NLHP
```


Here is the DAT extractor. 

```
http://www.mediafire.com/?epwmyxtjtzd
```


Looking into a hex editor, I see the header is comprised of an odd string, MTA. Then there are quite a few 0000's, some more odd strings, etc, until you get to the real audio data at around 00000FE4.

Deeper into the stream structure, there seems to be no 0000 strings. I am certain it is stereo music, so it cannot be ADPCM like other PS2 games.

I have Googled around, and suspect this may be a format called Konami Wave, or some sort, but I haven't found a converter.

It doesn't seem to be PCM, Goldwave just reads it as static.

It seems to be some sort of proprietary PCM file, it's a PCM file's size, and I am nearly sure it is stereo. The track above I suspect is a smaller, stinger track or some sort. There are larger ones too.

I have tried opening the BGM file with Solidus to no avail.

If you can help me, I will be endlessly grateful. I can supply more audio files as well.

Thank you endlessly in advance!
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-07-14T11:54:15+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

Ive looked at these before but i couldnt make much of it either, SOLIDUS is able to partially open the MGS3 stage.DAT header revealing some file names and whatnot but thats it.

Try using STUNS (Stupid uncompressor) on the files, if you dont have it then i could probably upload it for you as its tiny anyways.Its not MINE though I got it from Turfster and i think he got it from somewhere else too.
## Post #3
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-07-14T22:32:10+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

Thanks for replying, can you please send me this tool?
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-07-15T09:31:08+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

here you go, It took me a few hours of scounging through an unforseen number of problems to finally find it again (i dont remember ever deleting it to be honest though...).


Its a pretty simple program but if you get stuck give me a shout.
[None](https://xentaxbackup.github.io/file/2195_None)
## Post #5
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-07-15T14:32:00+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

Alrighty, thanks I'll try it out.
## Post #6
- Username: Waninkoko
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 22, 2009 10:24 pm
- Post datetime: 2009-12-22T21:39:30+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

I'm investigating too about these files but at the moment there's no luck 


Also, I unpacked VOX.DAT file using the "Konami DAT Tool" (phew, I didn't have to code my own unpacker ) and I noticed there are two different audio formats: VAG1 and VAG2.

VAG1 plays fine with MFAudio (most files are mono and 22050Hz) but VAG2 doesn't play correctly (it plays but with some kind of weird effect). Any ideas about VAG2? :/
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-12-22T23:12:41+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

> Reply from Waninkoko
>
> VAG1 plays fine with MFAudio (most files are mono and 22050Hz) but VAG2 doesn't play correctly (it plays but with some kind of weird effect). Any ideas about VAG2? :/

Have you tried stereo with an interleave of 16 (or 10, I think MFAudio uses hex). The "weird effect" might be that tight interleave.

I'm fairly sure that whatever the raw is is 4-bit oriented, but haven't pinned it down yet.
## Post #8
- Username: Waninkoko
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 22, 2009 10:24 pm
- Post datetime: 2009-12-23T00:06:46+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

> Reply from hcs
>
> Waninkoko wrote:VAG1 plays fine with MFAudio (most files are mono and 22050Hz) but VAG2 doesn't play correctly (it plays but with some kind of weird effect). Any ideas about VAG2? :/

Have you tried stereo with an interleave of 16 (or 10, I think MFAudio uses hex). The "weird effect" might be that tight interleave.

I'm fairly sure that whatever the raw is is 4-bit oriented, but haven't pinned it down yet.

Yeah but it doesn't fix the problem.

I opened the VAG2 file with an hex editor and I checked its frequency is 44100Hz (0xAC44). I did the following tests with MFaudio;

Frequency: 44100Hz
Channels: 2
Interleave: 10 (or 20)

Result: Doesn't sound properly


Frequency: 44100Hz
Channels: 2
Interleave: 1000

Result: Sounds OK but with that effect


Frequency: 44100Hz
Channels: 1

Result: Sounds OK, similar to the previous test, but with the weird effect too.
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-27T08:09:58+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

Could you upload two or three of these VAG2 files? I'd like to take a look.  Maybe it's a format that I've encountered lately.
## Post #10
- Username: tytansvx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 12, 2010 7:54 am
- Post datetime: 2010-06-12T14:55:10+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

Has any one found out how to decode/convert the PCM files from the BGM.DAT file?
## Post #11
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2010-06-15T18:33:12+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

The Audio.dat I get due to the SFX etc, But the game has a soundtrack, all the BGM is on there.
Did you try using STUNS on it to see what it throws out?
## Post #12
- Username: tytansvx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 12, 2010 7:54 am
- Post datetime: 2010-06-15T20:26:30+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

MFaudio, eufony for BGM and other PCM decoders but none work.
## Post #13
- Username: jhonsadins
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 02, 2010 9:09 pm
- Post datetime: 2010-07-03T08:01:30+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

Metal Gear Solid 3: Snake Eater manages to set a fantastic pace early on and keeps everything going right up to the closing credits and then some. Overall, this is the best Metal Gear Solid game that we've seen and, yes, it rules.
## Post #14
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-03T22:57:34+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

> Reply from tytansvx
>
> Has any one found out how to decode/convert the PCM files from the BGM.DAT file?
I've taken a look at these files and I haven't seen anything similar before. I can surely say that because that MGS3 format is really noticeable with the 0x330-byte-sized blocks and the 0x80-fillers. I've scoured the net a bit but couldn't find any information about the format. Maybe it's interpretable when it's parsed (i.e. the fillers deleted).
## Post #15
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-05-08T00:02:39+00:00
- Post Title: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not DAT)

I've finally had a little luck with this, I think. I just added MTAF support to vgmstream r942, but note that it needs to rip the audio out of DATs with this: [http://hcs64.com/files/demux_dat_01.zip](http://hcs64.com/files/demux_dat_01.zip)

Run like this:
demux_dat BGM.DAT DAT

Second argument is a prefix for the extracted files.
It also works on VOX, MOVIE, and DEMO.  I think the demux_dat_be version will work on MGS4, though I don't know what to do with the MTA2 files there yet.

The old DAT extractors took off a few too many bytes per block (particularly the frame count), I think mine may err a bit in the other direction, but at least it provides enough for decoding.  VOX uses VAG1, which I believe other stuff handles, vgmstream doesn't work for those yet.

As for the audio, I still haven't been able to locate the exact code, but I've made an approximation that sounds pretty good.  It's an IMA-flavor ADPCM with step idx saturated from 0 to 31, and it does hit those limits frequently, but it uses the Yamaha nibble to delta.  I've estimated the step size table by minimizing the least-squares difference across each frame, the tool for this is here is anyone wants to mess with it: [http://hcs64.com/files/mtaf_00.zip](http://hcs64.com/files/mtaf_00.zip) .  Needs lapack and blas for the computation.

I'm using .8 fixed point for the computations.  After minimizing across BGM.DAT, the average error is 4.6 and range is -27 to 39 per frame (out of 32k).
## Post #16
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-05-08T00:56:23+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Great work hcs!!

Hopeful for mgs4 now.
## Post #17
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-05-08T03:55:28+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Bit of a fix: [http://hcs64.com/files/demux_dat_02.zip](http://hcs64.com/files/demux_dat_02.zip)

New demuxer that cleans up files properly.  This requires the new version of vgmstream (r946) which doesn't try to do blocking itself.  Much cleaner now code-wise, the files are only slightly smaller and there is no impact on the audio.

Also now supports the VAG1 from VOX.DAT, just for kicks.

and r947 supports VAG2, apparently there is music in VOX.DAT...
## Post #18
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-05-14T08:10:14+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Alright, final nail in the coffin.  A helpful fellow shared his reversed decoder with me, and so I was able to locate the original decode table in the exe.  I've modified vgmstream to use this in r948, should be completely accurate now (and the errors across frames are all 0).
## Post #19
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2011-05-15T23:29:44+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Wow, great work, hcs!

I'll have to admit, however, I've been out of the ripping scene for about two years now and I'm afraid I can't completely figure out how to get the files extracted from the DAT to play in vgmstream (I'm using the sample that I posted on the first post as I don't have BGM.DAT anymore). If I'm reading correctly, the old DAT extractor didn't completely extract the music files, leaving off vital information, and that's why the files won't play in r948?

As for MGS4, IIRC the audio format was identical to MGS3, but I haven't verified this. This thread offers a sample file (DBM files from Metal Gear Online that have embedded MTAF's): [viewtopic.php?f=17&t=5996](http://forum.xentax.com/viewtopic.php?f=17&t=5996)

If you pursue MGS4, good luck! 

Edit: Scratch my statement that the formats are the same - I've been informed that MGS4 uses MTA2, not MTAF. Would you happen to know if the audio structures are similar? Hopefully, it won't be much work to add support for the MTA2's.
## Post #20
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-05-16T09:51:38+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

The big issue with the extractors I tried to use was that they left in big padding chunks.  demux_dat removes those.
demux_dat_be can be used on MGS4 .dat files, and the .dbm files have the same layout but it doesn't start until 0x800 bytes in.
The MTA2 codec seems to be quite different from MTAF, research is ongoing.
## Post #21
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2011-05-17T01:15:26+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Cool, thanks for the info!

Good luck on the MTA2 codec, and your work is really appreciated! I've been dying for a complete rip of MGS4 for ages...
## Post #22
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2011-05-29T18:30:24+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Hey hcs, if you don't mind me asking, how is the progress on the MGS4 codec?  No rush, in any case.
## Post #23
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2011-06-30T22:48:15+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Hey hcs, just letting you know I'm still interested in any progress if you have any time.
## Post #24
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-30T23:17:26+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Same.
## Post #25
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-07-01T04:01:13+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

No news, haven't looked at it for some time.
## Post #26
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2011-07-01T05:16:02+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

No worries, but if you have any time/desire to look into it further, I'd be very grateful. 

If I may ask, what do you know so far about the MGS4 codec?
## Post #27
- Username: MoriyaMug
- Rank: Banned
- Number of posts: 7
- Joined date: Sat Sep 11, 2010 12:03 am
- Post datetime: 2011-07-03T09:48:06+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

This is incredible news. I recently downloaded OrangeC's rip of MGS3, and it's a delight to have the entire thing. I'm attempting to replicate the process for the "Existence" disc (with the movie version of the game). The video is straight M4V format, which I can get with no trouble. The audio isn't working so well, though. I can get the .mtaf files extracted, but vgmstream won't play them in Winamp, and the text.exe reports, "failed opening demo_3.dat_00001_0011.mtaf". It's not a syntax error, that I can determine... it happens with each file, no matter what I do. vgmstream has the external DLLs needed, so that's not the issue. Any other ideas what might be going on or what steps I might have missed?

Also, is there any way of extracting the subtitles to something along the lines of a .srt subtitle file?

If I can get this working, I really want to get cracking on Zone of the Enders: The 2nd Runner.  Thanks in advance for any help.
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-07-17T17:01:48+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Did you update to the latest vgmstream.
## Post #29
- Username: Griffo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 15, 2011 6:18 am
- Post datetime: 2011-11-15T03:39:00+00:00
- Post Title: Re: Metal Gear Solid 3 Audio Format (Yes, Audio Format, not 

Sorry to bump this old topic. But I'm having trouble using the demux_dat.exe file to extract data from the DAT files. I've used the Konami dat utility before. Could you guys explain exactly how the file is meant to be used? Does it have to be in the same directory as the dat files, does it only open certain dat files etc? 

I've tried dragging the demux_dat.exe file into the command window and entering the text you wrote. Also, when I open it, a command window opens and closes very quickly. I'm not able to do anything with it. Am I making some stupid mistake? Would really appreciate your help with this. 

Thanks
