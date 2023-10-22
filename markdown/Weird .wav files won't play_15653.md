## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-12-27T20:40:54+00:00
- Post Title: Weird .wav files won't play

I've recently been extracting sounds from the underrated, infamous prequel: Perfect Dark Zero using unxwb.exe to extract the sounds from .xwb and .xsb files. However, after extracting these files, the output of them is in .wav, yet none of them are playable in WavePad or Audacity. I tried using ToWav.exe, but it's not working for me. Any ideas? I've included some samples [here](https://www.dropbox.com/s/sh0zbwkjciri2z2/PDZ.rar?dl=0). Thank you, and have a nice day
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-12-28T12:43:01+00:00
- Post Title: Weird .wav files won't play

It would probably be more helpful if you could provide a sample of the original .xsb/.xwb files.
## Post #3
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2016-12-28T18:12:59+00:00
- Post Title: Weird .wav files won't play

The sample files are still compressed or encrypted.  Seems like whatever converter didn't really make them into wave data.  After forcing them to play by modifying their headers, its just static/noise/compressed/encrypted ...
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-12-28T19:00:56+00:00
- Post Title: Weird .wav files won't play

> Reply from Liandril
>
> It would probably be more helpful if you could provide a sample of the original .xsb/.xwb files.
[Here](http://www.mediafire.com/file/w6xgq2anfwggu35/PDZ_XWB_Files.rar), I uploaded some .xwb's and .xsb's that are for music and I assume SFX.
## Post #5
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-12-28T23:25:59+00:00
- Post Title: Weird .wav files won't play

Hi Pepsee

and thanks for the samples. The .xwbs are in big endian order and contain wma files. The problem is: [xactxtract](http://forum.xentax.com/viewtopic.php?f=17&t=4391&p=43840) can extract wma, but only little endian order files. unxwb can extract big endian, but no wma. unxwb doesn't show a message that it cannot extract wma. Instead, it obviously just writes a wav header and appends the wma data, that's why you hear only static noise.
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-12-29T02:29:36+00:00
- Post Title: Weird .wav files won't play

> Reply from Liandril
>
> Hi Pepsee

and thanks for the samples. The .xwbs are in big endian order and contain wma files. The problem is: xactxtract can extract wma, but only little endian order files. unxwb can extract big endian, but no wma. unxwb doesn't show a message that it cannot extract wma. Instead, it obviously just writes a wav header and appends the wma data, that's why you hear only static noise.

Thanks for looking into them, Liandril! Well, what script/program should be used in order to get the appropriate files?
## Post #7
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-12-29T12:09:28+00:00
- Post Title: Weird .wav files won't play

> Reply from Pepsee
>
> 
Thanks for looking into them, Liandril! Well, what script/program should be used in order to get the appropriate files?
Sorry, if I knew an answer to this, I would have posted it
## Post #8
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-12-29T12:22:51+00:00
- Post Title: Weird .wav files won't play

> Reply from Liandril
>
> Pepsee wrote:
Thanks for looking into them, Liandril! Well, what script/program should be used in order to get the appropriate files?
Sorry, if I knew an answer to this, I would have posted it

Damn   Well, there's got to be some way to extract and convert those files
## Post #9
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-12-30T17:35:43+00:00
- Post Title: Weird .wav files won't play

Any ideas, anyone?
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-30T21:44:22+00:00
- Post Title: Weird .wav files won't play

use unxwb to extract the files and xmaencode to convert them to playable wavs
like the description under unxwb says, seems to work okay  

[http://aluigi.altervista.org/papers.htm#xbox](http://aluigi.altervista.org/papers.htm#xbox)
## Post #11
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-12-30T23:10:46+00:00
- Post Title: Weird .wav files won't play

> Reply from AceWell
>
> use unxwb to extract the files and xmaencode to convert them to playable wavs
like the description under unxwb says, seems to work okay  

http://aluigi.altervista.org/papers.htm#xbox

It doesn't work, I'm trying to convert a strange .wav to a regular, playable .wav file.
I tried using Xwmaencode.exe and it gives me an error, saying "Requested PCM format is invalid"
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-31T07:41:13+00:00
- Post Title: Weird .wav files won't play

> Reply from Pepsee
>
> It doesn't work, I'm trying to convert a strange .wav to a regular, playable .wav file.
I tried using Xwmaencode.exe and it gives me an error, saying "Requested PCM format is invalid"
i don't know what "Xwmaencode.exe" is, i used "xmaencode.exe" to convert your samples
to normal wavs and played some in VLC player and worked or else i wouldn't have posted
## Post #13
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-12-31T12:46:04+00:00
- Post Title: Weird .wav files won't play

> i don't know what "Xwmaencode.exe" is, i used "xmaencode.exe" to convert your samples
>
> to normal wavs and played some in VLC player and worked or else i wouldn't have posted

Could you please upload it or link me to it? I can only find xWmaencode.exe, no wonder it wasn't working for me
EDIT: Also, how did you use xmaencode to convert to .wav? I thought that was to convert .wav to .xma
Am I supposed to convert it to .xma then use towav to reconvert it? I don't understand
## Post #14
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-12-31T15:03:10+00:00
- Post Title: Weird .wav files won't play

> Reply from Pepsee
>
> Also, how did you use xmaencode to convert to .wav? I thought that was to convert .wav to .xma
Am I supposed to convert it to .xma then use towav to reconvert it? I don't understand
You can also use xmaencode like this

```
XMAENCODE <xmafile> /X <pcmfile>
```

in order to convert xma to .wav.

After a closer look: 

 stock_s.xwb contains 91 files marked as WMA and 2 files marked as XMA (0000005c, 0000005b)
 stock.xwb: 870 marked as WMA, 1 marked as XMA (0000035b)

When I use xmaencode on the WMA(!) files (as AceWell did), then I get playable output, but not when I use it on the files marked as XMA. To me it seems as if the format tags are set incorrectly (wma instead of xma and vice versa).

BTW: xmaencode (and xWMAencode) are available for download in [this thread](http://forum.xentax.com/viewtopic.php?f=17&t=4367).

Happy new year to you all
## Post #15
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2017-01-01T15:32:07+00:00
- Post Title: Weird .wav files won't play

> Reply from Liandril
>
> Pepsee wrote:Also, how did you use xmaencode to convert to .wav? I thought that was to convert .wav to .xma
Am I supposed to convert it to .xma then use towav to reconvert it? I don't understand
You can also use xmaencode like this
Code: Select allXMAENCODE <xmafile> /X <pcmfile>
in order to convert xma to .wav.

After a closer look: 

 stock_s.xwb contains 91 files marked as WMA and 2 files marked as XMA (0000005c, 0000005b)
 stock.xwb: 870 marked as WMA, 1 marked as XMA (0000035b)

When I use xmaencode on the WMA(!) files (as AceWell did), then I get playable output, but not when I use it on the files marked as XMA. To me it seems as if the format tags are set incorrectly (wma instead of xma and vice versa).

BTW: xmaencode (and xWMAencode) are available for download in this thread.

Happy new year to you all

Yes, but I have a major problem. I only get .wav files out of the .xwb with unxwb, I don't get .xma or .wma's 
P.S: Happy 2017, everyone!
## Post #16
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2017-01-01T17:29:20+00:00
- Post Title: Re: Weird .wav files won't play

> Reply from Pepsee
>
> Yes, but I have a major problem. I only get .wav files out of the .xwb with unxwb, I don't get .xma or .wma's Don't worry about the extension. Extract for example stock.xwb, then decode the xma to wav by

```
xmaencode.exe 00000000.wav /X out000.wav
```
(just an example, you'll rather use a script to decode all). This should work for the XMAs (that are wrongly marked as WMAs) in your xwb files, but not for the 3 WMAs that are marked as XMAs... Phew! Really weird
