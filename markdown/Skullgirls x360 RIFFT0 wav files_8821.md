## Post #1
- Username: pioneer
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jan 25, 2010 10:28 pm
- Post datetime: 2012-04-23T17:17:52+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Pulled numerous .wav files from the character .xma2 sound containers, but i have been unable to convert into a playable format



Forum rules prohibit me from posting samples so please pm me anyone interested

Demo sound

[http://www.fileden.com/files/2007/9/30/ ... emosnd.wav](http://www.fileden.com/files/2007/9/30/1472128/Demosnd.wav)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-04-29T14:17:55+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

You must first parse the .XMA2 files with [HCS' XMA Parse tool](http://hcs64.com/files/xma_parse011.zip)

After you have run the files through this, then use ToWAV to convert them from XMA to PCM WAV.

ToWAV can be downloaded from here

[http://www.ctpax-x.ru/index.php?goto=files&show=24](http://www.ctpax-x.ru/index.php?goto=files&show=24)
## Post #3
- Username: pioneer
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jan 25, 2010 10:28 pm
- Post datetime: 2012-04-29T19:06:51+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Tested a few with xma parse and it returns an "error reading bitstream" when converting

[http://www.fileden.com/files/2007/9/30/ ... emosnd.wav](http://www.fileden.com/files/2007/9/30/1472128/Demosnd.wav)
## Post #4
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-07T03:36:01+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

you need to specify the data offset as well as a block size. Use VGMToolbox along with these tools for the frontend.
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-05-07T12:41:11+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Sorry I meant [XMAsh](http://hcs64.com/files/xmash08.zip), not XMA Parse. It should be able to do it
## Post #6
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-08T15:17:02+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

xmash works fine but it isn't so necessary if you have the VGMToolbox+ToWav+XMA Parse set up. Just set everything to read the data from the RIFF header and have it rebuild to XMA1 with a block size of 0x10000.
## Post #7
- Username: pioneer
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jan 25, 2010 10:28 pm
- Post datetime: 2012-05-08T16:41:49+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Thanks for taking the time to look 

Would it be possible for a vgmtoolbox presets file as they still wont convert for me with VGMToolbox+ToWav+XMA Parse set up
## Post #8
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-08T17:07:24+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Do you have both towav and xma_test in "\vgmtoolbox_bin_rXXX\external\xma" ?

I've attached a preset plugin. Extract it and place it in "\vgmtoolbox_bin_rXXX\plugins\XmaConverter" and load it up.
[xbla_skullgirls_xma2.zip](https://xentaxbackup.github.io/file/5413_xbla_skullgirls_xma2.zip)
## Post #9
- Username: pioneer
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jan 25, 2010 10:28 pm
- Post datetime: 2012-05-08T17:21:36+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Thanks

I have both xma_test and towav in the correct folder and your preset file loaded but the converted files are still inaudible

Did the demosound.wav file i posted convert for you ok?
## Post #10
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-08T20:08:56+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Yea, it worked fine. Weird that nothing is working for you.
## Post #11
- Username: pioneer
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jan 25, 2010 10:28 pm
- Post datetime: 2012-05-09T17:02:40+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Turns out winamp was at fault   

Your help was much appreciated bxaimc

Thanks
## Post #12
- Username: ttys000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 11, 2012 12:04 am
- Post datetime: 2012-05-10T16:15:24+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Valuable clues, thank you. I add these for further reference.

= Regarding .snd-xma2 blobs =

VGMtoolbox when configured for XMA extraction only seems to extract the first sound file from .snd-xma2 containers as found in Skullgirls.

Foremost - [http://foremost.sourceforge.net/](http://foremost.sourceforge.net/)

Combined with: 
```
xma2     y       8000000  \x52\x49\x46\x46\x54    \xff\xff\xff\xff
```

(See man page, will explain syntax.)

This header / footer combo will rip every item out into a seperate "xma2" file. In this case about 200 to 300+ sounds per character.
These will then hapily convert when processed through VGM toolbox.

= Regarding WAV playback =

Default windows codec set doesn't seem to like these wavs. VLC / Mplayer2 / Audacity play the output fine.

= Result =

Ms. Fortune "omnomnomnomnom" SMS notification get.
## Post #13
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-10T17:33:20+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

VGMT's XMA tool doesn't extract. It converts. It will only read the first file which is supposed to be the only file. If you have many files in one (unless it's an XWB bank or FSB bank -towav will play with those as-is-), just split the file with the simple cutter, advanced cutter, or VFS extractor and then convert with the XMA converter.
## Post #14
- Username: Meower
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 21, 2012 5:24 am
- Post datetime: 2012-10-21T20:17:17+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

I seem to have incurred in some sort of problem by following the same steps of op and the other posters:

While I do get no error whatsoever when I drag'n'drop (I hope it was what I was supposed to do, if you cannot tell I am the polar opposite of a computer wiz) to the xmash.exe program, nor when using the XMA Converter, I can't seem to be able to extract any file whatsoever.

Is there something wrong that I am doing or that I forgot to set (it most probably is)? Or could someone, real pretty please, give me a bit more details on the prerequisites for doing this?

While we're on the same page, I think I read in the .conf file of Foremost that it can also convert and retrieve .art files, and being there quite a few where the music files came from, I wanted to give a go at it and extract them... Only to find out that I'm missing like a single library that redirects to another gazillion ones (should be types.h but don't really take my word for it). Is there a way to compile it on a W7 OS without having to break anything?

I know I sounded uberly vague, I hope this doesn't sound like a horrible way to be a first timer newbie ;m;
## Post #15
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-12T20:52:55+00:00
- Post Title: Skullgirls x360 RIFFT0 wav files

Why don't you just use my XMA transform: [viewtopic.php?f=17&t=9023](http://forum.xentax.com/viewtopic.php?f=17&t=9023), it supports 98% of the xma variants.
## Post #16
- Username: Meower
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 21, 2012 5:24 am
- Post datetime: 2012-11-27T08:35:27+00:00
- Post Title: Re: Skullgirls x360 RIFFT0 wav files

> Reply from AlphaTwentyThree
>
> Why don't you just use my XMA transform: viewtopic.php?f=17&t=9023, it supports 98% of the xma variants.
I am not sure if it worked but I tried to pm you some specific details, do they show? :<
