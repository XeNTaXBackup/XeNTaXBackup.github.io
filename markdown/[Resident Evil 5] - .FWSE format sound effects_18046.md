## Post #1
- Username: Amy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 30, 2018 10:11 pm
- Post datetime: 2018-04-30T14:15:49+00:00
- Post Title: [Resident Evil 5] - .FWSE format sound effects

Hello everyone!

I have a question, is there any tool capable of CONVERTING .FWSE format audio files to .WAV?

I have looked everywhere into it but I can't seem to find any. I am also 0% skilled with coding so writing a tool myself would be nearly impossible (trust me, I tried coding a calculator in C++ once and I got a headache after 4 hours of trying).

Thank you very much for your answer,

Amy.

EDIT:

File sample: [http://www.mediafire.com/file/z6yw34qbspe3e56/25.FWSE](http://www.mediafire.com/file/z6yw34qbspe3e56/25.FWSE)
## Post #2
- Username: zac43
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 13, 2018 2:40 pm
- Post datetime: 2018-05-13T06:49:58+00:00
- Post Title: [Resident Evil 5] - .FWSE format sound effects

I would like to see this aswell, i tried to make some understanding over the fwse format with no sucess, i have no idea about coding neither but i have the hope that someone with the right skills can figure this out, thanks for read my message
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-05-20T13:11:38+00:00
- Post Title: [Resident Evil 5] - .FWSE format sound effects

MTF v1 games were always used ADPCM, Vorbis and SE codecs, my knowlege of audio codecs is very limited, so I don't know what SE codec really means.

```
	uint Version;
	uint fileSize;
	uint bufferOffset;
	uint numChannels;
	uint numSamples;
	uint sampleRate;
	uint sampleDepth;
	char palette[992]; //4bit?
```
## Post #4
- Username: zac43
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 13, 2018 2:40 pm
- Post datetime: 2018-05-29T09:02:30+00:00
- Post Title: [Resident Evil 5] - .FWSE format sound effects

> Reply from PredatorCZ
>
> MTF v1 games were always used ADPCM, Vorbis and SE codecs, my knowlege of audio codecs is very limited, so I don't know what SE codec really means.
Code: Select all	uint ID;
	uint Version;
	uint fileSize;
	uint bufferOffset;
	uint numChannels;
	uint numSamples;
	uint sampleRate;
	uint sampleDepth;
	char palette[992]; //4bit?
thanks so much, do you think that it'll be possible to write a tool to handle in specific this formar? I tried to talk to Gh0stBlade (he have experience writing tools for this format) about this and he said that he have a tool but he have no intentions on sharing it, so if anyone could help me i could even pay for it.
## Post #5
- Username: NightFuri0us
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 13, 2016 3:30 am
- Post datetime: 2018-05-30T08:31:25+00:00
- Post Title: [Resident Evil 5] - .FWSE format sound effects

> Reply from zac43
>
> i could even pay for it.
+1
## Post #6
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-12-29T21:33:07+00:00
- Post Title: [Resident Evil 5] - .FWSE format sound effects

As of recent time, I had made SPAC extractor with built in FWSE converter.
[https://github.com/PredatorCZ/RevilToolset](https://github.com/PredatorCZ/RevilToolset)
I will also try to post a converter into the vmgstream project, since it's already part of it, but only on my fork so far.
After that, a raw FWSE files can be opened/converted by any app using vgmstream or it's plugins.
## Post #7
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2020-01-04T11:50:26+00:00
- Post Title: [Resident Evil 5] - .FWSE format sound effects

> Reply from PredatorCZ ↑Mon Dec 30, 2019 5:33 am at Mon Dec 30, 2019 5:33 am
>
> 
As of recent time, I had made SPAC extractor with built in FWSE converter.
https://github.com/PredatorCZ/RevilToolset
I will also try to post a converter into the vmgstream project, since it's already part of it, but only on my fork so far.
After that, a raw FWSE files can be opened/converted by any app using vgmstream or it's plugins.
Is there any tutorial? I tried on pc and it just says:invalid format.Thread{0x4E4}
## Post #8
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-01-09T13:53:30+00:00
- Post Title: [Resident Evil 5] - .FWSE format sound effects

It doesn't work on fwse files, only on SPC archives, that contains them.
