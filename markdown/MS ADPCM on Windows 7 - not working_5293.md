## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-25T20:42:11+00:00
- Post Title: MS ADPCM on Windows 7 - not working?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-10-25T22:17:25+00:00
- Post Title: MS ADPCM on Windows 7 - not working?

Hello alpha i got this file to play with the latest audacity beta and having ffmpeg external libraries for audacity installed. 

[http://audacity.sourceforge.net/download/beta_windows](http://audacity.sourceforge.net/download/beta_windows)

[http://manual.audacityteam.org/index.ph ... tallffmpeg](http://manual.audacityteam.org/index.php?title=FAQ:Installation_and_Plug-Ins#installffmpeg)
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-25T23:10:58+00:00
- Post Title: MS ADPCM on Windows 7 - not working?

> Reply from OrangeC
>
> Hello alpha i got this file to play with the latest audacity beta and having ffmpeg external libraries for audacity installed. 

http://audacity.sourceforge.net/download/beta_windows

http://manual.audacityteam.org/index.ph ... tallffmpeg
Hm, can you play it with Winamp? I think if the codec is installed correctly it should be...
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-10-25T23:59:10+00:00
- Post Title: MS ADPCM on Windows 7 - not working?

Nope can't play it through winamp.
## Post #5
- Username: Bumeaung50
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 08, 2019 9:21 pm
- Post datetime: 2019-02-08T13:34:58+00:00
- Post Title: MS ADPCM on Windows 7 - not working?

> Reply from AlphaTwentyThree
>
> OrangeC wrote:Hello alpha i got this file to play with the latest audacity beta and having ffmpeg external libraries for audacity installed. 

http://audacity.sourceforge.net/download/beta_windows

http://manual.audacityteam.org/index.ph ... tallffmpeg
Hm, can you play it with Winamp? I think if the codec is installed correctly it should be...
Really? So it is the reason why I can't use it for Winamp, I have a lot of thing that I do, I search it in audacity guides and trying to fix the problem but that doesn't work at all. Thanks for the tips, I will check it again and I hope that will fix this problem.
## Post #6
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-02-08T21:29:53+00:00
- Post Title: MS ADPCM on Windows 7 - not working?

You could also implement a TXTH header with vgmstream, using that codec:
[https://github.com/losnoco/vgmstream/bl ... oc/TXTH.md](https://github.com/losnoco/vgmstream/blob/master/doc/TXTH.md)

You may have to read the files header for some values (ie sample rate) but possibly not. Should work fine in vgmstream
