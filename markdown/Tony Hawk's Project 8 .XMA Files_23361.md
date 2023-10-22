## Post #1
- Username: ENunn
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 11, 2020 1:24 am
- Post datetime: 2021-01-25T18:03:43+00:00
- Post Title: Tony Hawk's Project 8 .XMA Files

I've been trying to convert these audio files from the 360 version of Project 8 and for the life of me I can't get it working.

I initially extracted the file from an .fsb archive that the game uses with FSB Extractor. It extracted correctly and wrote a WAVE header.


FFMPEG detects the file as a "adpcm_ima_wav"

For the conversion to .wav, I tried QuickBMS with the XMA transform script and it threw me up this error:

```
No XMA code found at designated offset (20).  Aborting all operations.
```


I tried vgmstream, nothing happens. Then I use VGMGUI, a vgmstream GUI, and it threw me this:


Tried ToWav, nothing happens at all.


Anyone know how to convert this? Here's a sample.
[https://mega.nz/file/3oNwiT6I#aoCMH2f_r ... dyrms-z0qM](https://mega.nz/file/3oNwiT6I#aoCMH2f_rwCzp0bpTiUqLTcNmSADcopwDdyrms-z0qM)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-25T18:24:13+00:00
- Post Title: Tony Hawk's Project 8 .XMA Files

It looks to me that there's a couple of issues with the .wav file:

Firstly, the codec is listed as 0x69 - it should be 0x165 for XMA, which is why you get "XMA code not found" error.
Secondly, the header is shorter than it should be - for XMA the header should be 0x3c bytes, where the audio data starts.

I can play the audio with a .txth file, so it's definitely XMA.

Did you extract the files from an archive first?  If so, could you upload it, unless it's too big.

EDIT: Just noticed you mentioned an FSB archive - you should be able to drop that archive straight into Foobar and it should play with the vgmstream plugin.
## Post #3
- Username: ENunn
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 11, 2020 1:24 am
- Post datetime: 2021-05-20T01:56:44+00:00
- Post Title: Tony Hawk's Project 8 .XMA Files

Sorry for the 5 month late reply, never got notified of your reply  

> Reply from DKDave ↑Tue Jan 26, 2021 2:24 am at Tue Jan 26, 2021 2:24 am
>
> 
Did you extract the files from an archive first?  If so, could you upload it, unless it's too big.

If you really want to give it a go, here: [https://mega.nz/file/7oNHzAaa#5LVaqCXUl ... ZvKC7Oat80](https://mega.nz/file/7oNHzAaa#5LVaqCXUl6w7jljOd1V2uQrMlqEXQbg67ZvKC7Oat80)

> Reply from DKDave ↑Tue Jan 26, 2021 2:24 am at Tue Jan 26, 2021 2:24 am
>
> EDIT: Just noticed you mentioned an FSB archive - you should be able to drop that archive straight into Foobar and it should play with the vgmstream plugin.

You'd think that but to me only one file shows up in vgmstreamGUI. Plus I don't use foobar, so I'd rather convert it to WAV or FLAC.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-20T11:31:42+00:00
- Post Title: Tony Hawk's Project 8 .XMA Files

> Reply from ENunn ↑Thu May 20, 2021 9:56 am at Thu May 20, 2021 9:56 am
>
> 
Sorry for the 5 month late reply, never got notified of your reply  
DKDave wrote: ↑Tue Jan 26, 2021 2:24 am
Did you extract the files from an archive first?  If so, could you upload it, unless it's too big.

If you really want to give it a go, here: https://mega.nz/file/7oNHzAaa#5LVaqCXUl ... ZvKC7Oat80
DKDave wrote: ↑Tue Jan 26, 2021 2:24 amEDIT: Just noticed you mentioned an FSB archive - you should be able to drop that archive straight into Foobar and it should play with the vgmstream plugin.


You'd think that but to me only one file shows up in vgmstreamGUI. Plus I don't use foobar, so I'd rather convert it to WAV or FLAC.

It's an FSB3 sound archive, so just take the extra extension off the filename, so that it's streamall.fsb.  Then drop it into Foobar and you get 2000+ audio files which you can play/convert to .wav.
