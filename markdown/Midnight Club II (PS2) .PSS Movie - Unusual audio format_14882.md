## Post #1
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2016-08-18T09:16:55+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

Hi.

Can somebody help me cracking the audio format of movies used in Midnight Club II (PS2)?

Usually, the PS2 PSS files consist of MPEG2 Streams + PS2 ADPCM (Uncompressed). But, this one is completely different.

With this game, playing them with MFAudio (or any video players supporting the format) only static noises yet barely audible sounds  could be heard (Weird thing is, in MFAudio the audio was detected as 12000Hz as opposed of 48000Hz audio found in most PS2 games.)

I'll included the sample of audio streams if needed (It's the Rockstar Games logo).

> https://mega.nz/#!Kht0zSAD!5SE2Phfeux_1 ... GDDBPQqohY

Update 12/20/22:
The codec was found and figured out long time ago, but I forgot to edit the thread. Turns out it was DVI IMA ADPCM interleaved by 64 bytes per channel and the sample rate is 48000Hz. vgmstream + foobar2000 should be enough to play them correctly.
## Post #2
- Username: Tungui
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 26, 2021 3:43 pm
- Post datetime: 2022-12-19T21:34:47+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

Hello! 

Were you able to figure out the audio static issue? 

Been at it for a while now along with extracting all the other audio files from this game in order to improve the PC port. 

Appreciate it!
## Post #3
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2022-12-20T08:12:42+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

> Reply from Tungui ↑Tue Dec 20, 2022 5:34 am at Tue Dec 20, 2022 5:34 am
>
> 
Hello! 

Were you able to figure out the audio static issue? 

Been at it for a while now along with extracting all the other audio files from this game in order to improve the PC port. 

Appreciate it!

Yes, sorry forgot to update the thread.
vgmstream is already able to play some exotic audio codec inside a PSS movie like this one for some time. Just use a supported media player (I recommend [foobar2000](https://www.foobar2000.org/download)) then install the [plugin](https://vgmstream.org/downloads/), lastly just play the PSS file on there. BTW the codec is DVI IMA ADPCM interleaved by 64 bytes per channel.
## Post #4
- Username: Tungui
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 26, 2021 3:43 pm
- Post datetime: 2022-12-22T00:42:56+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

Oh wow! I already have this component, never knew even bothered to try it this way! 

Many thanks!
## Post #5
- Username: Tungui
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 26, 2021 3:43 pm
- Post datetime: 2022-12-22T01:19:40+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

Can't seem to get foobar to play the file, but I'll give it a go with the commandline/winamp one. Just want to try and convert the audio into something I can use for compiling both the audio and video together.

Thanks again!
## Post #6
- Username: Tungui
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 26, 2021 3:43 pm
- Post datetime: 2022-12-26T08:51:12+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

Yeah, I can't seem to get the audio. 

Let me know if you can help out! I already did a run on PS2 and just recorded all the cutscenes to match the audio with the raw video. Appreciate your help again.
## Post #7
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2022-12-26T09:59:49+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

> Reply from Tungui ↑Mon Dec 26, 2022 4:51 pm at Mon Dec 26, 2022 4:51 pm
>
> 
Yeah, I can't seem to get the audio. 

Let me know if you can help out! I already did a run on PS2 and just recorded all the cutscenes to match the audio with the raw video. Appreciate your help again.

Hmm, I swore vgmstream can load the PSS file directly without need to demuxing it first, oh well. You can use [vgmtoolbox](https://sourceforge.net/projects/vgmtoolbox/) to demux/extract the audio. After you run the tool, go to "Streams -> Video demultiplexer". Then in the format dropdown field, choose "PSS (PlayStation Stream)". If you want to extract/demux the both of video and audio, left the radio buttons at the right to default, otherwise choose "Extract audio only" to extract just the audio tracks. Then just drop the PSS file into the tool, it will create two files with m2v and ss2 extensions (If you choose "Extract audio only", only the ss2 files are created). M2V are the video tracks and SS2 are the audio tracks. SS2 files is the one you're looking for. Lastly, just drag then convert the SS2 file to WAV on foobar.
## Post #8
- Username: Tungui
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 26, 2021 3:43 pm
- Post datetime: 2022-12-26T10:30:22+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

That worked! Thanks a bunch! 

I apologize for bugging, but you are awesome. 

All I gotta do is just get those .ipu files converted so I can get the "texture" for the end points for these cutscenes.
## Post #9
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2022-12-26T10:50:04+00:00
- Post Title: Midnight Club II (PS2) *.PSS Movie - Unusual audio format

> Reply from Tungui ↑Mon Dec 26, 2022 6:30 pm at Mon Dec 26, 2022 6:30 pm
>
> 
That worked! Thanks a bunch! 

I apologize for bugging, but you are awesome. 

All I gotta do is just get those .ipu files converted so I can get the "texture" for the end points for these cutscenes.

That's easy, you can use ffmpeg to convert it straight to image files. It's command line tools though.
