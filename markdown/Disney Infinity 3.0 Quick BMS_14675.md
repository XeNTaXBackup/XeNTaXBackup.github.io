## Post #1
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2016-07-23T07:50:07+00:00
- Post Title: Disney Infinity 3.0 Quick BMS

I used quick bms to extract everything from Disney Infinity 3.0, but when I try to open one of the .wav files I have to raw import it in audacity and then its just static. Help would be appreciated.

I've attached a sample wav file
[wav sample.zip](https://xentaxbackup.github.io/file/11339_wav sample.zip)
## Post #2
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2016-07-29T22:32:25+00:00
- Post Title: Disney Infinity 3.0 Quick BMS

It's wwise vorbis, use ww2ogg.
## Post #3
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2016-07-31T01:49:15+00:00
- Post Title: Disney Infinity 3.0 Quick BMS

> Reply from spider91
>
> It's wwise vorbis, use ww2ogg.
Do I put the Wav files in directly?
## Post #4
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2016-07-31T23:42:17+00:00
- Post Title: Disney Infinity 3.0 Quick BMS

Ok I did it but now its a long screeching sound.
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-01T00:27:49+00:00
- Post Title: Disney Infinity 3.0 Quick BMS

You need to use the --pcb command line option to select the right codebooks in packed_codebooks_aoTuV_603.bin:

```
ww2ogg --pcb packed_codebooks_aoTuV_603.bin OBK0194.wav
```

This is mentioned in the README.
## Post #6
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2016-08-02T17:59:13+00:00
- Post Title: Disney Infinity 3.0 Quick BMS

> Reply from hcs
>
> You need to use the --pcb command line option to select the right codebooks in packed_codebooks_aoTuV_603.bin:
Code: Select allww2ogg --pcb packed_codebooks_aoTuV_603.bin OBK0194.wav
This is mentioned in the README.
That worked, but all the sounds are in a different language, unless I'm not finding the right ones.
## Post #7
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2016-08-02T22:47:42+00:00
- Post Title: Disney Infinity 3.0 Quick BMS

Ok somehow I had the wrong language version of the game. I went and got the english version and its extracting via quickbms right now, but it takes forever. Is there any way to only extract wav files with quickbms?
## Post #8
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2016-08-17T05:40:50+00:00
- Post Title: Disney Infinity 3.0 Quick BMS

Ok so I got everything but it didn't include any of the Force Awakens DLC content or sounds. Any idea whats wrong?
