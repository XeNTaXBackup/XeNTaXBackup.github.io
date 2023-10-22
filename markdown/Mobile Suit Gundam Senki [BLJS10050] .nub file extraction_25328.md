## Post #1
- Username: ssenrober
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat May 07, 2022 9:51 pm
- Post datetime: 2022-05-07T13:58:47+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

Hi,

As the title suggests I am looking for a solution to decode or extract this .nub file of this game. I have the sample attached below.

So far I have tried the nubExtractor r8 and r12 but both didn't work.

The .nub file was obtatined using quickbms.

[https://drive.google.com/file/d/1T59V42 ... sp=sharing](https://drive.google.com/file/d/1T59V42YQ3fJ86IJeZkbmpekniR1q4SXZ/view?usp=sharing)

Many thanks!
## Post #2
- Username: ssenrober
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-07T20:58:16+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

Your google drive link is private. You need to share a public link.
## Post #3
- Username: ssenrober
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat May 07, 2022 9:51 pm
- Post datetime: 2022-05-08T12:13:35+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

Oh thanks for the notification  ikskoks ,

Please have a look at these 2 samples instead

[https://drive.google.com/file/d/1T59V42 ... sp=sharing](https://drive.google.com/file/d/1T59V42YQ3fJ86IJeZkbmpekniR1q4SXZ/view?usp=sharing)

[https://drive.google.com/file/d/1jFJYp- ... sp=sharing](https://drive.google.com/file/d/1jFJYp-nxRGU9_-ZjdxygJQ5mKNHolaPc/view?usp=sharing)
## Post #4
- Username: ssenrober
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-09T19:12:08+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

Your samples seems to be compressed. I've found only one valid "RIFF" header inside.

Btw, NUB extractors are shared here [http://hcs64.com/files/](http://hcs64.com/files/)
## Post #5
- Username: ssenrober
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat May 07, 2022 9:51 pm
- Post datetime: 2022-05-09T19:19:03+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

Thanks for the reply ikskoks,

I have tried both NubExtractors but got unknown headers as a result.

even for the r12beta with "ignore nub header if RIFF header is present" it still didn't work,

I assume it has something to do with this .riff header now?
## Post #6
- Username: ssenrober
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-09T20:26:37+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

> I assume it has something to do with this .riff header now?

RIFF header occurs in WAV containers which can contain AT3 audio data [http://wiki.xentax.com/index.php/AT3_Audio](http://wiki.xentax.com/index.php/AT3_Audio)
I thought that those NUB files may contain some AT3 audio, because it seems to be common audio codec for PS3/PSP games.
## Post #7
- Username: ssenrober
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat May 07, 2022 9:51 pm
- Post datetime: 2022-05-10T06:26:50+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

> Reply from ikskoks ↑Tue May 10, 2022 4:26 am at Tue May 10, 2022 4:26 am
>
> 
I assume it has something to do with this .riff header now?

RIFF header occurs in WAV containers which can contain AT3 audio data http://wiki.xentax.com/index.php/AT3_Audio
I thought that those NUB files may contain some AT3 audio, because it seems to be common audio codec for PS3/PSP games.

Exactly, this is a PS3 game to be dealt with and at3 is a possible output for this.

However, it's not recognized by the nubExt which supports at3,bnsf,dsp,idsp,lwav,vag,xma, with an outcome of "unidentified header" and 0 file dectection.

What could possibly be done at this stage? I would be appreciated if there's a sol for this
## Post #8
- Username: ssenrober
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-10T20:18:14+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

I'm afraid that only solution for now may be to reverse engineer file format and to write a new custom tool to handle this.
## Post #9
- Username: ssenrober
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat May 07, 2022 9:51 pm
- Post datetime: 2022-05-10T20:40:28+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

> Reply from ikskoks ↑Wed May 11, 2022 4:18 am at Wed May 11, 2022 4:18 am
>
> 
I'm afraid that only solution for now may be to reverse engineer file format and to write a new custom tool to handle this.
 Oh boy, I'll see what I can do with this. Thanks anyways ikskoks

I'll keep an eye on this post as well incase there's any new clue
## Post #10
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-12T15:43:58+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

Basically this is extraction issue, because existing script is valid only for main game archive. I've posted updated script [here](https://forum.xentax.com/viewtopic.php?f=21&t=5622&p=184443#p184443), it should handle all game archives properly. 
Extracted nub files will be compatible with NUBExt tool and converted with it files are compatible with latest vgmstream.
## Post #11
- Username: ssenrober
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat May 07, 2022 9:51 pm
- Post datetime: 2022-05-16T00:34:15+00:00
- Post Title: Mobile Suit Gundam Senki [BLJS10050] .nub file extraction

Thank you both very much!

So this has something to do with the old script I used in that post to extract the files, with the updated script I was able to extract the files sucessfully using nubextr12 now, the extracted files are indeed in .at3 format. 

Bravo!
