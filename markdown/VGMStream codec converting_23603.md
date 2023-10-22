## Post #1
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-03-17T17:32:12+00:00
- Post Title: VGMStream codec converting

I'm trying to convert a file to use a specific codec using [VGMStream](https://github.com/vgmstream/vgmstream) and can't seem to figure out how to change what codec I'm encoding with,
Specifically from either mp3 or wav to MSF, however it will always use PCM Signed 16-bit, while I need it to use Atrac 3 which it supports, I'm unsure if I can do this using foobar or have to specifically use the command line but it doesn't say how to swap what codec I'm converting to.
Any help on this would be much appreciated, and if any more details are needed I can provide them, I'll attach 2 MSF files (One with the PCM and one with Atrac3 header) for if needed, (sorry that the PCM one is mega bitcrunched but should still work to test conversions)

[https://drive.google.com/file/d/1ohCxWN ... sp=sharing](https://drive.google.com/file/d/1ohCxWNrBXRh9VSawFRHkSbo1Wbai02cC/view?usp=sharing)
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2021-03-18T07:21:38+00:00
- Post Title: VGMStream codec converting

VGMStream is made to 'support decoding' the game audio formats, not 'support encoding' in to them generally (thus you only get PCM output) so you need some other tool for the job. Besides those that know the format closely may determine if it needs to be Atrac3 or Atrac3+, if new game it is 3+ more likely which has no public encoder(?) unlike basic atrac3.
## Post #3
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-03-18T16:21:35+00:00
- Post Title: VGMStream codec converting

> Reply from Apollo ↑Thu Mar 18, 2021 3:21 pm at Thu Mar 18, 2021 3:21 pm
>
> 
VGMStream is made to 'support decoding' the game audio formats, not 'support encoding' in to them generally (thus you only get PCM output) so you need some other tool for the job. Besides those that know the format closely may determine if it needs to be Atrac3 or Atrac3+, if new game it is 3+ more likely which has no public encoder(?) unlike basic atrac3.

Ah I see, I can most likely state that it's probably Atrac3 and not Atrac3+ as that's what foobar says unless they both get stated as just Atrac3, I see thanks for the help!
[MSF Encoding.PNG](https://xentaxbackup.github.io/file/19744_MSF Encoding.PNG)
