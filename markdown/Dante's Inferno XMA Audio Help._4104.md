## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-01T22:19:38+00:00
- Post Title: Dante's Inferno XMA Audio Help.

Hello this is from the demo of the game, this looks like pure xma audio however the file header doesn't mention anything useful and i appear to be what i see the sample rate but it still doesn't work with it corrected in the xma header. Little help in figuring this one out, i don't think its multichannel either.

[http://www.megaupload.com/?d=BX94R4DT](http://www.megaupload.com/?d=BX94R4DT)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-02T03:01:24+00:00
- Post Title: Dante's Inferno XMA Audio Help.

Cut off the first 0x20 bytes and run it through unpack1943.  I guess it's EA's own special brand of XMA.  Wonder if their layer 3 stuff is similar in principle...
## Post #3
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2010-02-02T03:21:12+00:00
- Post Title: Dante's Inferno XMA Audio Help.

Aha, thanks HCS!
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-02T11:48:28+00:00
- Post Title: Dante's Inferno XMA Audio Help.

Your a Life saver man thanks.

EDIT: Audio seems to have some glitches though when i converted with 48hz assuming its the correct rate.

heres one.
[http://www.mediafire.com/?imlt5mxtt51](http://www.mediafire.com/?imlt5mxtt51)
## Post #5
- Username: cryogen
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Aug 25, 2009 6:07 pm
- Post datetime: 2010-02-06T16:27:17+00:00
- Post Title: Dante's Inferno XMA Audio Help.


## Post #6
- Username: cryogen
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Aug 25, 2009 6:07 pm
- Post datetime: 2010-02-07T23:45:31+00:00
- Post Title: Dante's Inferno XMA Audio Help.

I converted most of them to wav, a real pain in the ass anyway.
I noticed that all the english vocals of the game work good,they convert without glitches, the other regions work bad, there are lot of glitches after the conversion(it happen here only with france and spain vocals, but who cares when I can have them in english?  ).
For who is interested u have to use ToWav for the final conversion.
All the music and atmos sounds seems to work good   
One last thing, u don't have to cut the first 0x20 but another value and they work...
Again thx to Luigi for his script...

Ops, another last thing, some extracted files(after Luigi's script) seems to be containers of other files....

yo
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-08T08:01:38+00:00
- Post Title: Dante's Inferno XMA Audio Help.

If you still have the files around could you upload one of the other language files?  I'd like to see why they're glitchy.
## Post #8
- Username: cryogen
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Aug 25, 2009 6:07 pm
- Post datetime: 2010-02-08T20:43:48+00:00
- Post Title: Dante's Inferno XMA Audio Help.

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-10T10:57:46+00:00
- Post Title: Dante's Inferno XMA Audio Help.

Woke up with the solution to this...
I think the situation here, and what also may have been the case in Battlefield: Bad Company (which I never quite understood), is that EA's XMA packing encodes sets of samples independently, but they don't always fit in a single packet.  In XMA in general:
A packet will contain some number of frames, and because they don't pack exactly into the packet one frame will overflow into the next packet, so the first real frame of the packet will start at some offset in the packet, this is stored in the packet header as the "skip bits" because it's how many bits from the previous packet you need to skip to actually start decoding.  In the last packet in a stream in XMA1 the skip bits value may be 16384, which is invalid (a packet has 16380 bytes of payload [2k-4 byte header], so this would skip the entire packet and more which makes no sense).  XMA2 has a similar mechanism, though it uses 32767 (all bits of "skip bits" set), but the message is the same: rather than skipping bits in this packet to get to the first frame, there is *no* frame starting in this packet, so the decoder can skip it.  This happens when the last packet only has the overflow of a frame rather than any frames of its own.

So why is this a problem?

EA seems to encode fixed groups of samples entirely independently.  In the France file this seems to be 4608 samples at a time (9 frames at 512 samples each).  Ordinarily they choose this value such that the encoded frames will always fit in a single packet.  However in this France file (and in Battlefield:Bad Company, I went back and checked) it doesn't always fit, so the frames overflow into an additional packet.  The trouble is that toWav apparently doesn't support the "skip whole packet" mechanism I described above, either in XMA1 or XMA2.  In XMA2 we encountered this issue a lot more often because even normally encoded XMA2 had this stream end a lot, at the end of blocks.  XMA1 has no concept of blocks, though, so usually you'd only see this at the end of a stream so toWav messing up on it wouldn't matter.  With these files, though, it occurs all throughout the stream, so you get little skips.

The generally available xmaencode seems to properly support this for XMA1.  So the workaround is to use the method I describe here (once you've cut off the 0x20 byte header):
[http://aluigi.freeforums.org/post9118.html#p9118](http://aluigi.freeforums.org/post9118.html#p9118)

I'm glad to finally understand why this worked in xmaencode but not in toWav.  Unfortunately this involves some crap to create a more valid .xma file, more work than simply sticking a header on it.  The real solution would be for xma_test to support rebuilding XMA1 streams the same way I support rebuilding XMA2 streams as XMA1, so that everything is packed contiguously and this issue doesn't come up (as well as correcting the sequence numbers).  I also guess I need to remove the "Unknown = 0, expected 2" warning on 16384-skip packets; I take it this is yet another way of signaling end-of-stream.
## Post #10
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-10T21:13:16+00:00
- Post Title: Dante's Inferno XMA Audio Help.

Figure this is worth another post:
I've updated xma_test (0.7) to be able to rebuild XMA1 streams as well, like:

```
xma_test infile -1 -r outfile
```
I also updated ea_multi_xma (0.1), it should now work on all of these EA-packed XMAs.  It's also a lot simpler to use, and it works out the number of streams, so it should work on the 1, 2 and 3 stream files in Dante's Inferno, as well as all the old stuff that unpack1943 worked with (which is now deprecated).  It makes up file names by putting _streamN on the end of the input file name.  It also comes with a -o option, so you can specify a header to skip, this saves the trouble of cutting off 0x20 bytes all the time.

So now for these infernal files you do:

ea_multi_xma to unpack the streams
xma_test to rebuild each stream as usable XMA
add header, decode w/ towav
## Post #11
- Username: cryogen
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Aug 25, 2009 6:07 pm
- Post datetime: 2010-02-12T20:43:04+00:00
- Post Title: Dante's Inferno XMA Audio Help.

WOW!!!THX this will be a long night for me .....  
Well done I'm going to try your tools...later
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-14T18:52:30+00:00
- Post Title: Dante's Inferno XMA Audio Help.

This might interest most of you.

I have created batches mostly for some of hcs tools needed to decode dante's inferno.

ea_multi_xma.bat > use this to automatically extract all streams from the packed files. NOTE: you have to specify the offset for some files in the bat, but the default is 20, like most of the files, only like 60 of those have different offsets, it shouldn't be too hard to filter those out.

xma_parse.bat> this is intended to rebuild the unpacked xma2 streams to xma, it outputs the fixed streams to blah.out. 

I also included an addXMAheader bms script along with quickbms latest version and a batch file to automatically add a stereo xma header to the fixed streams, ready for decoding with towav. Thanks for alphatwentythree on the script and batch help.

[http://www.mediafire.com/?dobmmymtmzj](http://www.mediafire.com/?dobmmymtmzj)

This should greatly reduce the time by half so it can relieve the stress of manual labor for these thousands of files.  

thanks to hcs for the additional batch help.
## Post #13
- Username: norm
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 12, 2010 3:54 am
- Post datetime: 2010-02-27T07:48:19+00:00
- Post Title: Dante's Inferno XMA Audio Help.

> Reply from OrangeC
>
> 
I also included an addXMAheader bms script along with quickbms latest version and a batch file to automatically add a stereo xma header to the fixed streams, ready for decoding with towav. Thanks for alphatwentythree on the script and batch help.

Could you say how you go about changing the header file with this script? I need to add mono headers for files from Bad Company 2. ([http://hcs64.com/files/xma_header_mono.zip](http://hcs64.com/files/xma_header_mono.zip))

I looked in the addXMARIFFHeader.bms but don't see where you specify anything.

Thanks to hcs on his great work.

EDIT: Nevermind. I compared the XMA mono file and saw it was practically identical to the bms script except for one byte. I changed it from 02 to 01.

set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"
## Post #14
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-26T13:11:41+00:00
- Post Title: Dante's Inferno XMA Audio Help.

The contents of this post was deleted because of possible forum rules violation.
[BFBC_res_decode_pack.7z](https://xentaxbackup.github.io/file/2886_BFBC_res_decode_pack.7z)
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-26T13:34:21+00:00
- Post Title: Dante's Inferno XMA Audio Help.

Wow thanks alpha for the tool pack.
## Post #16
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-03-26T14:37:56+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

its not working properly with most of the smaller files, its cut almost completely off near the start.
## Post #17
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-26T16:34:01+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

> Reply from Pepper
>
> its not working properly with most of the smaller files, its cut almost completely off near the start.
Could you upload a sample file (source)?
## Post #18
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-03-27T00:10:42+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

i can upload plenty, it seems every small file is cut off, and the large files are cut off later in (size relation perhaps)
[BU_lmg_M60_reload_3p_WaveDataSns_1.zip](https://xentaxbackup.github.io/file/2888_BU_lmg_M60_reload_3p_WaveDataSns_1.zip)
## Post #19
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-28T13:24:53+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

Indeed - looks like one of the stepsonly processes the first block of 800 bytes... That's a case for HCS - HELP US PLEASE!
## Post #20
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-03-31T02:05:12+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

That file isn't XMA1, it's XMA2.  Just extract with ea_multi_xma and use a mono 48khz header.

The radio file Alpha had posted way back, you're using a header that's too small, it only supports up to 10 MB or so.
Here's a nice big one: [http://hcs64.com/files/header3](http://hcs64.com/files/header3)
## Post #21
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-31T07:18:40+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

Thanks a lot HCS! 
Totally forgot to implement the data size into the script - will do that later! Damn, I wish there was a tool that detects the different XMA versions and lets me decode the file right-away without having to adjust the decoding process each time... HCS? 
And yeah, I wish I could code C or C++...
## Post #22
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-03-31T08:08:26+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

afaict there isn't a way to look at an raw XMA stream and tell what sample rate or channel count it should be.
However, these .res files do have a little header (which ea_xma_multi strips out) that has the sample rate, so you can at least get that from there.
## Post #23
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-31T11:48:57+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

Yes of course it's not possible. But to distinguishing between XMA and XMA2 should be possible, right? So that the program could just try to decode the file with adjustable options I mean. 
So it would be great to have a GUI withfile input
sample rate and channel settings (maybe drop-down menu for both)
file output ([input name].wav = standard)
decode buttonIn the background it just detects XMA or XMA2 and runs the appropriate programs with adjusted options (like mine above for XMA and yours for XMA2). I don't know anything about GUI but I'm thinking of something like Zench's DecUbiGUI.
## Post #24
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-31T12:48:45+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

That would be great
## Post #25
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-31T20:54:25+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

I've just updated the bms script to support the maximum file size possible.  Now works for all the radio files too.
## Post #26
- Username: Sfinks69
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 19, 2010 2:18 pm
- Post datetime: 2010-05-19T19:11:26+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

What makes the files from the PC version and Xbox. I have obtained excellent to convert files with the Xbox but the PC does not 
result? They are encrypted? 
Sorry for my language skills.
## Post #27
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-05-20T06:00:09+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

the pc version isn't xma audio it's some type of EA ADPCM audio.  we dont know how to do the pc yet.
## Post #28
- Username: Sfinks69
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 19, 2010 2:18 pm
- Post datetime: 2010-05-20T19:12:32+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

And how to be for example with it? At me they broken or still that. It XMA2? 

 VOMP_RUSupport_Commrose_Order_GoGoGo_R_01_waveDataSns_1.zip
(2.58 KiB) Downloaded 39 times
## Post #29
- Username: Xevin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 11, 2010 1:41 am
- Post datetime: 2010-06-10T20:08:11+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

I needed to extract the audio files from BattleField: Bad Company 2 (BFBC2) and the information on this page really helped me do it. Along the way I wanted to extract ALL the files faster, so working off AlphaTwentyThree's .bat file I modified it to convert all the files under the folder tree of the .bat file and leave the files inside their original folders.

```
for /r %%i in (*.res_stream1) do ren "%%i" *.str
for /r %%i in (*.str) do "%CD%\xma_test.exe" "%%i" -1 -r "%%i.xm"
del /s *.str
for /r %%i in (*.xm) DO "%CD%\quickbms.exe" -o "%CD%\addXMARIFFHeader.bms" "%%i" "%%~dpi\"
del /s *.xm
for /r %%i in (*.xma) do (
"%CD%\towav.exe" "%%i" 
move *.wav "%%~dpi/"
)
del /s *.xma
del /s *.res
```


I also created a tutorial based on the information I found on this site, but modified to work with BFBC2. It's posted here: [http://www.bfeditor.org/forums/index.ph ... opic=14539](http://www.bfeditor.org/forums/index.php?showtopic=14539)

Thank's for helping me you guys!

[edit]Oops! I left xma_test.exe in XMA2 mode (for BFBC2). It's fixed now.[/edit]
## Post #30
- Username: Sfinks69
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 19, 2010 2:18 pm
- Post datetime: 2010-06-12T08:42:42+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

> Reply from Xevin
>
> I needed to extract the audio files from BattleField: Bad Company 2 (BFBC2) and the information on this page really helped me do it. Along the way I wanted to extract ALL the files faster, so working off AlphaTwentyThree's .bat file I modified it to convert all the files under the folder tree of the .bat file and leave the files inside their original folders.
to Xevin
What do I do not so? I have made archive under your scheme and I try to recode remarks from game. But at me a problem. Sounds turn out accelerated why I do not know. I think that in all my system is guilty, but is not assured.

[ExtractOmatic.exe](http://rapidshare.com/files/398103323/ExtractOmatic.exe)
[Sounds](http://rapidshare.com/files/398104050/Sound.rar)
## Post #31
- Username: oldguy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 11:26 am
- Post datetime: 2014-08-11T04:32:41+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

Hell guys, I need help with Dante's Inferno audio. I used [this](http://www.bfeditor.org/forums/index.php?showtopic=14539) instruction, aluigi's bms script for di. It works well, but some converted files are insanely accelerated. I tried to change the sample rate in header with no success.
Any ideas, what's wrong with them?
[000001b5.zip](https://xentaxbackup.github.io/file/7655_000001b5.zip)
## Post #32
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-08-12T00:55:32+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

Can you provide an XMA file instead?
## Post #33
- Username: oldguy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 11:26 am
- Post datetime: 2014-08-12T03:38:15+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

Maybe other files will be useful too. Dat, str, xm, xma.
[DImono.zip](https://xentaxbackup.github.io/file/7656_DImono.zip)
## Post #34
- Username: oldguy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 11:26 am
- Post datetime: 2014-08-19T12:25:12+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

I still can't find any solution.
## Post #35
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-08-19T22:41:40+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

> Reply from oldguy
>
> I still can't find any solution.
I think those files were either ripped incorrectly, or hold something else entirely. they seem like XMA, they have the XMA2 8000 block bit in them, without a proper XMA2 style header. (all xma2 starts with something like xx000100xx, replace x's with any number. 2400010004 is an example.

Ah, the problem is you were doing it in a method for bc2, dante's inferno is different, check the first page of this topic for some of the differences, particularly in needing to rebuild as XMA1 to decode properly.
[YourSampleFixed.zip](https://xentaxbackup.github.io/file/7685_YourSampleFixed.zip)
## Post #36
- Username: oldguy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 11:26 am
- Post datetime: 2014-08-25T23:56:14+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

Thanks, changing xma_test -2 to -1 works fine. Now I need to figure out correct offsets for many .dat files, because a lot of game sounds are missing in already unpacked. Can somebody advise me how to do it properly and quickly? Seems that other offsets were not mentioned anywhere before, only 0x20.
## Post #37
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-08-26T01:03:25+00:00
- Post Title: Re: Dante's Inferno XMA Audio Help.

> Reply from oldguy
>
> Thanks, changing xma_test -2 to -1 works fine. Now I need to figure out correct offsets for many .dat files, because a lot of game sounds are missing in already unpacked. Can somebody advise me how to do it properly and quickly? Seems that other offsets were not mentioned anywhere before, only 0x20.
Can't help you there unfortunately... I've never tried ripping that particular game myself and from what I'm reading, it varies for those.
