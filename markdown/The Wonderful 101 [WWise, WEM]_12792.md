## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-23T03:06:55+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

Before wwise 0.22 - "unknown chunk type"
wwise 0.22 - "expected 0x42 fmt if vorb missing"
With audio from .bnk - "RIFF truncated"

Few samples - [http://dropmefiles.com/oLFRk](http://dropmefiles.com/oLFRk)
## Post #2
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-26T09:43:33+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

Additional Info:
- Probably not standart OGG|ADPCM Wwise. (ww2ogg and ima_rejigger3 cant make playable or decodable data)
- Header: RIFX..рHWAVEfmt ..........}...Ґа.Ш.........?cue ................data............LIST....adtllabl..."....Adjust_Wwise_Latency(4frames).JUNK..............data..п°
## Post #3
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-28T05:22:56+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

It's simple to make playable ima_adpcm from that fles. I don't have much time now, so i will try to write a script later

[http://dropmefiles.com/PON1l](http://dropmefiles.com/PON1l)
## Post #4
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-28T11:14:33+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

[http://dropmefiles.com/PON1l](http://dropmefiles.com/PON1l) - doesn't work (Error 500)
## Post #5
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-28T11:36:55+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

Thats something with [http://dropmefiles.com](http://dropmefiles.com) . I can't download your original files too to make anorher sample
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-28T14:21:46+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

Now "Error 500" dont shown.

Try to find ima_adpcm(if its a tool), but find nothing. Or means something different to make playable audio?
## Post #7
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-28T15:11:58+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

it's audio codec. file i uploaded is playable. mpc plays it without any problems.
## Post #8
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-28T20:34:34+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

I know.

But I dont know a solution for decoding to standart ADPCM, I try to find it sometime ago, but without success.

So I dont have any clue how you make playable ADPCM audio.
## Post #9
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-29T01:40:08+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

for example you can use ffmpeg.
## Post #10
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-29T12:48:16+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

I try to use Zeranoe FFmpeg, because my OS is Win 7 x64.

But he dont supports RIFX:

> [NULL @ 02b883a0] WAVEFORMATEX support for RIFX files
>
> [NULL @ 02b883a0]  is not implemented. Update your FFmpeg version to the newest one from Git. If the problem still occurs, it means that your file has a feature which has not been implemented.
>
> 156452.wem: Not yet implemented in FFmpeg, patches welcome

I dont have source compilation experience myself, so I cant use ffmpeg, if only share version of ffmpeg with RIFX support.
## Post #11
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-29T14:09:16+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

> Reply from Researchman
>
> 
[NULL @ 02b883a0] WAVEFORMATEX support for RIFX files

RIFX is header from original file, ffmpeg can't convert it. You can convert my modified file, not the original wwise.
## Post #12
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-29T17:38:17+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

I'm starting to get confused is that you try to say.

In the first and second post I write about audio specials and tries to decode it with ww2ogg, because its only known wwise decoder for me, but without any result.

How to make these original, not modificated wwise audio, to decodable ADPCM wav as one of methods to get playable audio I dont know and dont understand how.

P.S.: Sorry for possible emotions.
## Post #13
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-29T20:58:20+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

ww2ogg is only for wwise vorbis (ogg), while this files are wwise ima adpcm.There is no decoder to that files. To get playable ima adpcm you need to change file header like i did in file i uploaded before. If you don't know how to do that just wait for a script, i'll make it as soon as i can.
## Post #14
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-05-01T02:01:44+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

[http://dropmefiles.com/3AnUr](http://dropmefiles.com/3AnUr) - files were deleted. Please, reupload them.
## Post #15
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-05-01T04:45:31+00:00
- Post Title: The Wonderful 101 [WWise, WEM]

Done - [http://dropmefiles.com/oLFRk](http://dropmefiles.com/oLFRk)
## Post #16
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-05-02T12:48:17+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

Well, i've made a script. First of all you need to interleave files with ima_rejigger, then run this script to get playable .wav. Didn't work with music from your archieve, only with voices, don't know why (maybe because of 6 channels?).

```
goto 0x16
get CHANNELS short
reverseshort CHANNELS
get FREQ long
reverselong FREQ
get BPS long
reverselong BPS
get UNK1 short
reverseshort UNK1
get UNK2 short
reverseshort UNK2
goto 0xC
do
	getDstring CHUNK_NAME 4
	get DATA_SIZE long
	savepos DATA_OFFSET
	getDstring DUMMY DATA_SIZE

while CHUNK_NAME != "data"
set FULLSIZE long 0x30
math FULLSIZE += DATA_SIZE
reverselong DATA_SIZE
set RIFF_SIZE long FULLSIZE
math RIFF_SIZE -= 0x8
reverselong RIFF_SIZE
log MEMORY_FILE 0 0
set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x14\x00\x00\x00\x11\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x00\x41\x00\x64\x61\x74\x61\x00\x00\x00\x00"
putVarChr MEMORY_FILE 4 RIFF_SIZE long
putVarChr MEMORY_FILE 22 CHANNELS short
putVarChr MEMORY_FILE 24 FREQ long
putVarChr MEMORY_FILE 28 BPS long
putVarChr MEMORY_FILE 32 UNK1 short
putVarChr MEMORY_FILE 34 UNK2 short
putVarChr MEMORY_FILE 44 DATA_SIZE long
append
reverselong DATA_SIZE
log MEMORY_FILE DATA_OFFSET DATA_SIZE
get NAME basename
string NAME += ".wav"
log NAME 0 FULLSIZE MEMORY_FILE

```
## Post #17
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-05-02T13:31:16+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

I think so - ffmpeg, xmplay with vgmstream, WMP, Audition CS6 reports about unknown codec or loads without sound(silence in 6ch files).

Funny, but Windows Explorer detects audio time even for 6ch files.

Probably need inform hcs about it.
## Post #18
- Username: Chaofanatic
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 11, 2015 1:51 am
- Post datetime: 2015-07-10T18:21:10+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

I hate to bump such an old post but I've been trying this and I'm able to get wav files I can play but they all have grinding static sound over them while I can still hear the original sound underneath.
It sounds like this was figured out but I think I missed a step or I may be using a wrong version of ima_rejigger or something. Were you actually able to get completely working files out of this or is it still being figured out?
## Post #19
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-07-10T23:37:33+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

mono and stereo files plays well if you use [ima_rejigger](http://hcs64.com/files/ima_rejigger3.zip) first and my script after that. If you don't you will get that grinding sound
## Post #20
- Username: Chaofanatic
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 11, 2015 1:51 am
- Post datetime: 2015-07-11T06:53:40+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

Oh! It worked! Thank you! I was using the wrong version of ima_rejigger and there were some problems with my batch file. Thanks a ton!
I'd also like to ask about the 6 channel files as well. Is there any way of dealing with those and getting something usable out of them? I checked around with some people and they may be used for event dialogue or something similar.

I've got some files here if you'd like to take a look.
[https://www.dropbox.com/s/qmb48ahnuboqd ... s.rar?dl=0](https://www.dropbox.com/s/qmb48ahnuboqdkw/6_channel_and_error_sounds.rar?dl=0)
## Post #21
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-03-31T09:59:36+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

spider91's wwise_ima_adpcm gave me the final clue, that Wwise uses one less sample per block than standard MS IMA:

MS IMA has the weird feature that every block, which is fairly small, has in its header the first sample in full 16-bit PCM form, which allows for very accurate seeking. The rest of the block is 4 byte chunks with 8 4-bit samples each, so the sample count of a block is always 8x+1.

In Wwise IMA, the final decoded sample is thrown away, and in fact that last nibble is always 0. Thus, sample count is 8x. I assume they did this because it lets them keep some buffer aligned to nice round numbers.

The upshot of which is that it is impossible to convert Wwise IMA ADPCM to standard Microsoft IMA ADPCM; there are these extra samples hanging out which throw the whole file off. There is actually a space in the extra format data for "samples per block", but I don't think many decoders care about that (sox [rejects anything without that extra +1 sample-per-block](https://sourceforge.net/p/sox/code/ci/sox-14.4.1/tree/src/wav.c#l720), libavformat seemingly ignores it).

Anyway, I'm glad to finally be able to put this behind me and retire the old ima_rejiggers, which never worked properly.

Here's [ima_rejigger5](https://hcs64.com/files/ima_rejigger5.zip), which does the decoding to PCM and supports both RIFF and RIFX wems, so it should be usable with The Wonderful 101. It isn't super-necessary but I wanted to get some closure here.

edit;
I'm realizing belatedly that my whole digression into reinterleaving stuff with the rejiggering tools was a huge wrong turn, this IMA turns out to be more common to the stuff we see on consoles all the time than the weird +1 thing standardized in RIFF. Sorry for causing and prolonging the confusion. I hope things are correct now, they certainly sound good.

edit2:
One final thought: I may have been a little too harsh on myself, this is definitely an unusual format, somewhere between MS IMA and normal IMA. Normally when you see IMA/DVI with block headers with a sample in it, that sample is just history, used only for seeking; you have to take that history and compute a new sample from the first nibble of ADPCM data. It is a good idea that MS came up with to not waste that and actually use it as part of the stream, so it is less redundant, but in so doing they wound up with really oddly sized blocks. I think AK came along and realized the best of both worlds, as they've managed to do in such creative ways with Vorbis.
## Post #22
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-03-31T15:16:31+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

Finally a solution is found!
## Post #23
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-04-03T13:01:45+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

Credit where it is due: wwise_ima_adpcm is by Zwagoth Klaar (zabb65), whose repository of Payday 2 modding tools is found [here](https://bitbucket.org/zabb65/payday-2-modding-information).

I'm not sure why spider91 was distributing the .exe without the readme, but it's my fault for not looking hard enough. Oops.
## Post #24
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-04-19T20:37:15+00:00
- Post Title: Re: The Wonderful 101 [WWise, WEM]

Was just looking over this again due to clipping in some very loud files from EVE Online, here's the heart of the decoder in the x64 debug lib from Wwise_v2015.1.6_Build5553_SDK.Linux

```
  10:   83 e0 07                and    $0x7,%eax        ; sample
  13:   01 c0                   add    %eax,%eax        ; sample*2
  15:   83 c0 01                add    $0x1,%eax        ; sample*2+1
  18:   0f af 45 e4             imul   -0x1c(%rbp),%eax ; (sample*2+1)*scale
  1c:   8d 50 07                lea    0x7(%rax),%edx   ; result+7
  1f:   85 c0                   test   %eax,%eax        ; result negative?
  21:   0f 48 c2                cmovs  %edx,%eax        ; adjust if negative to fix rounding for below division
  24:   c1 f8 03                sar    $0x3,%eax        ; (sample*2+1)*scale/8

```

What's notable is that this is a different rounding model from what ima_rejigger5 and wwise_ima_adpcm use, which is the shift-and-add from the IMA specification. There are very small differences, though with the block headers resetting state every few samples it doesn't accumulate. It looks like the noise introduced by this is down in the -50 dB range.

In any case this didn't fix my clipping problem, which is probably unavoidable. Maybe I will release a new revision of ima_rejigger to reflect this but I don't know if I'll bother.

(As an aside I'm pretty sure the adjustment done before division is unnecessary (and unwanted anyway), but the compiler probably didn't look at the constant table to figure this out and had to play it safe with signed division.)
