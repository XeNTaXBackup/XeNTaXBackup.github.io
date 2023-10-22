## Post #1
- Username: josejl1987
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 28, 2011 3:52 am
- Post datetime: 2016-03-21T23:11:04+00:00
- Post Title: PS Vita VAG files

Hello there.

I have the voice files from Ys Memories of Celceta for PS Vita. 

They are compressed using a new version of the VAG format (HE-VAG). I don't know much about sound formats,but it seems that they use another kind of ADPCM compression.

Is there any way to decode these? The tools for regular VAG files only return static noise.

[https://dl.dropboxusercontent.com/u/230 ... v_0000.vag](https://dl.dropboxusercontent.com/u/23091275/ycv_0000.vag)

Thanks
## Post #2
- Username: Coleiosis
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 16, 2016 6:51 am
- Post datetime: 2016-03-21T23:39:07+00:00
- Post Title: PS Vita VAG files

I use MFAudio to play VAG files (mainly from my PS2 games). It's downloadable for free!

[http://www.zophar.net/utilities/ps2util ... o-1-1.html](http://www.zophar.net/utilities/ps2util/mfaudio-1-1.html)
## Post #3
- Username: josejl1987
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 28, 2011 3:52 am
- Post datetime: 2016-03-21T23:50:17+00:00
- Post Title: PS Vita VAG files

That was one of the tools I tried,no luck,I only get noise with this new format.
## Post #4
- Username: Coleiosis
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 16, 2016 6:51 am
- Post datetime: 2016-03-22T01:11:46+00:00
- Post Title: PS Vita VAG files

Another one I used was called foobar2000, which also plays VPK files perfectly. I suggest you try this; but if it doesn't work out well, tell me.

[http://www.foobar2000.org/download](http://www.foobar2000.org/download)
## Post #5
- Username: josejl1987
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 28, 2011 3:52 am
- Post datetime: 2016-03-22T11:29:56+00:00
- Post Title: PS Vita VAG files

I assume you need to install the vgmstream plugin for foobar? 

Sadly ,all it plays is noise,like with the other tools.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-22T17:52:01+00:00
- Post Title: PS Vita VAG files

> Reply from josejl1987
>
> They are compressed using a new version of the VAG format (HE-VAG). I don't know much about sound formats

Then how do you know its HE-VAG ?
## Post #7
- Username: josejl1987
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 28, 2011 3:52 am
- Post datetime: 2016-03-22T18:21:23+00:00
- Post Title: PS Vita VAG files

Well,there are several sources talking about Vita using a new version of VAG.


[http://www.fmod.org/files/fmod.cs](http://www.fmod.org/files/fmod.cs)
[http://docs.unity3d.com/Manual/class-AudioClip.html](http://docs.unity3d.com/Manual/class-AudioClip.html)

There are also some Sony docs,but I'd rather not know how many rules linking to that would break.

Anyway,the version number in the VAG header is different from the old files.

About not knowing about sound formats,well,I really meant about not knowing the actual implementation of sound compression.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-23T16:01:35+00:00
- Post Title: PS Vita VAG files

ok, it seems they really changed format a little. It must be very possible to decode that, considering the fact that FMOD supports it. I may look into this later, but I think nobody done this before just because not many people need sounds from that little toy.
## Post #9
- Username: josejl1987
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 28, 2011 3:52 am
- Post datetime: 2016-03-25T10:52:04+00:00
- Post Title: PS Vita VAG files

Oh,thanks for your time.

About Vita formats not being popular,well,I think it is because dumping the game data isn't too easy right now,needing the FW 3.52 and all that.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-26T12:04:37+00:00
- Post Title: PS Vita VAG files

It seems FMOD supported this format even in 2010. But they don't allow decoding, only encoding. Let's see if I can get the algorithm there. I see no other tools support this format.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-28T15:06:57+00:00
- Post Title: PS Vita VAG files

Good news. I was able to find tables and algorithm in their code.

p.s. Meanwhile, can you send me more files? Are there any stereo, longer files?
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-29T17:09:44+00:00
- Post Title: PS Vita VAG files

First version.

Not perfect decoding, needs more work, may have errors, only supports mono 44100.

Anyway, you can already hear what is in there.
[hevag_decoder.rar](https://xentaxbackup.github.io/file/10653_hevag_decoder.rar)
## Post #13
- Username: josejl1987
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 28, 2011 3:52 am
- Post datetime: 2016-03-29T17:45:33+00:00
- Post Title: PS Vita VAG files

Thank you very much. 
If I set the playback rate to 24000 it seems to play correctly.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-29T18:34:30+00:00
- Post Title: PS Vita VAG files

I can make it getting rate from the header. Are there stereo files? Other games have stereo files too.
## Post #15
- Username: eduardogalvan24
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 16, 2016 3:54 pm
- Post datetime: 2016-07-19T18:50:36+00:00
- Post Title: PS Vita VAG files

SEGA uses these files inside their Project DIVA game. I've been trying to get at them and some files do actually work using a regular non HE-VAG decoder (PS1). However, some other files just don't work at all, even with your decoder. Could I get some help with this? Also, these files are all mono files.
I will attach a file that is supported using the decoder and another that isn't.
[https://goo.gl/1vOghV](https://goo.gl/1vOghV)
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-20T08:01:26+00:00
- Post Title: Re: PS Vita VAG files

> Reply from eduardogalvan24
>
> However, some other files just don't work at all, even with your decoder.
Also, these files are all mono files.
I will attach a file that is supported using the decoder and another that isn't.

I found 2 files in this archive, and both were decoded with my decoder.

One of them mono, another one stereo.

Where are files that don't work?
## Post #17
- Username: eduardogalvan24
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 16, 2016 3:54 pm
- Post datetime: 2016-07-31T08:46:34+00:00
- Post Title: Re: PS Vita VAG files

> Reply from daemon1
>
> eduardogalvan24 wrote:However, some other files just don't work at all, even with your decoder.
Also, these files are all mono files.
I will attach a file that is supported using the decoder and another that isn't.

I found 2 files in this archive, and both were decoded with my decoder.

One of them mono, another one stereo.

Where are files that don't work?
The file that doesn't work is se_pv_button_l1_off. It converts but gives a garbled sound. (It's supposed to be the end of a looping button hold. [https://youtu.be/50CnEwZ3gBo?t=37s](https://youtu.be/50CnEwZ3gBo?t=37s)) The other one correctly works, and loops as it should.
Also, impressive that you've written a VAG decoder for these newer files! I didn't think anyone would actually care because it's Vita.
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-31T08:51:53+00:00
- Post Title: Re: PS Vita VAG files

> Reply from eduardogalvan24
>
> The file that doesn't work is se_pv_button_l1_off. It converts but gives a garbled sound.

That's not the same. Ok, this is stereo file, and my tool currently only supports mono. I converted both channels individually, they work ok. The problem that is all games have different headers, and I don't know where to look for channel number. Also not many people even interested in that.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-09T06:19:28+00:00
- Post Title: Re: PS Vita VAG files

The version that takes sample rate from 0x10 offset of header. Must work in many cases.
[hevag_decoder.rar](https://xentaxbackup.github.io/file/11770_hevag_decoder.rar)
## Post #20
- Username: Firestorm7893
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 10, 2017 1:05 am
- Post datetime: 2017-11-09T17:14:41+00:00
- Post Title: Re: PS Vita VAG files

> Reply from daemon1
>
> eduardogalvan24 wrote:The file that doesn't work is se_pv_button_l1_off. It converts but gives a garbled sound.

That's not the same. Ok, this is stereo file, and my tool currently only supports mono. I converted both channels individually, they work ok. The problem that is all games have different headers, and I don't know where to look for channel number. Also not many people even interested in that.

Hey i know this thread is old, but can i take a look at the source files of your decoder? I'd like to try making it work even with stero files
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-09T18:47:19+00:00
- Post Title: Re: PS Vita VAG files

i think somebody already implemented my code into ffmpeg or vgmstream,  i remember i gave the code to someone to do  that
## Post #22
- Username: bnnm
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Nov 10, 2017 6:43 am
- Post datetime: 2017-11-12T14:03:10+00:00
- Post Title: Re: PS Vita VAG files

I implemented HEVAG support into vgmstream ([https://hcs64.com/vgmstream.html](https://hcs64.com/vgmstream.html)) based on the code daemon1 gave me (thanks again), should handle all known HEVAG but source is on github.
## Post #23
- Username: Firestorm7893
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 10, 2017 1:05 am
- Post datetime: 2017-11-13T19:29:50+00:00
- Post Title: Re: PS Vita VAG files

thank you a lot! it's what i needed!
