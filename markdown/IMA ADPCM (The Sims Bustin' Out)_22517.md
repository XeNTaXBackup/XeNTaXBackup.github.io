## Post #1
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2020-08-09T19:08:57+00:00
- Post Title: IMA ADPCM (The Sims Bustin' Out)

I've poked around a bit and it seems that the music from this game is some kind of headerless IMA ADPCM. Converting with sox results in a distorted/slow mess, and it refuses to output anything but mono anyway. You can find a sample below.

[https://drive.google.com/file/d/1Mgw_yp ... sp=sharing](https://drive.google.com/file/d/1Mgw_yp2a9I2vdanTKmOkXSzpKT32mqpr/view?usp=sharing)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-08-09T21:04:24+00:00
- Post Title: IMA ADPCM (The Sims Bustin' Out)

If you use Interleaved DVI as the codec, stereo, sample rate 44100 and the interleave is 0x80, then it will play
## Post #3
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2020-08-09T22:28:09+00:00
- Post Title: IMA ADPCM (The Sims Bustin' Out)

> Reply from DKDave ↑Mon Aug 10, 2020 5:04 am at Mon Aug 10, 2020 5:04 am
>
> 
If you use Interleaved DVI as the codec, stereo, sample rate 44100 and the interleave is 0x80, then it will play
Thank you so much (again)!
