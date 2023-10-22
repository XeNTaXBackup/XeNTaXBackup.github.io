## Post #1
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2017-11-14T07:26:44+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

Hi everyone. Today I ran into a strange problem. While I was converting some audio tracks from .xvag to .wave format with VGMStream, I found myself with a 4-channel audio file. Also during playback (not really perfect, because there is a really annoying white background noise level, especially if it is trying to raise the volume in addition also some click and pop), once the track finishes, it rains again, and I noticed the track lasted twice as much as it should be (if it lasted 3 minutes, it now lasts 6, playing it twice a time). I hope someone else besides me has come across my own problem and has managed to find a solution so he can possible help me. I attach below the links of an original and converted sample:

Original (Expired): [https://mega.nz/#!drwQTLyY!hXyxTaCBteCy ... jbeybGsd5o](https://mega.nz/#!drwQTLyY!hXyxTaCBteCyPFTQ4wkaRo5dHqpa4nek5jbeybGsd5o)
Converted (Expired): [https://mega.nz/#!BipVSRRK!ib7AZoXxLQLX ... oMJgEzpQTE](https://mega.nz/#!BipVSRRK!ib7AZoXxLQLX1ZfzoOVT0KegZjWOCWQmToMJgEzpQTE)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-12-26T12:06:41+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

Use the latest [vgmstream](https://raw.githubusercontent.com/bnnm/vgmstream-builds/master/bin/vgmstream-latest-test-u.zip) and it should playback and convert just fine with no issues.
## Post #3
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2017-12-27T02:37:15+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

Hi Brendan19, I tried as you advised me to do, but the problem also persists with this version...
[Screenshot.png](https://xentaxbackup.github.io/file/13733_Screenshot.png)
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-12-27T11:52:13+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

What problem are you talking about?
## Post #5
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2017-12-27T18:28:20+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

"I found myself with a 4-channel audio file. Also during playback (not really perfect, because there is a really annoying white background noise level, especially if it is trying to raise the volume in addition also some click and pop), once the track finishes, it rains again, and I noticed the track lasted twice as much as it should be (if it lasted 3 minutes, it now lasts 6, playing it twice a time)"
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-12-28T10:21:01+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

The track is only 59 seconds long so by default vgmstream will make it loop two times before adding a 10 second fadeout making the track 2:09


The clicking/popping issue:
Deleting the first two samples and the last two samples either side of the loop point which will remove the click/pop usually.

e.g. 2835189 is the loop point in this track. Delete two samples to the left of the loop point (2835187 and 2835188) and delete two samples to the right of the loop point (2835190 and 2835191) to remove the click/pop.

The track is quite ambient so I am pretty sure the "white noise" and "rain" is actually part of the soundscape and is meant to be part of the track.
## Post #7
- Username: bnnm
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Nov 10, 2017 6:43 am
- Post datetime: 2017-12-28T23:54:18+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

You can use "test.exe -i file.xvag" and it'll disable looping.

vgmstream detects the file loops fully (I'll adjust so looping is smoother though). If you remove looping the song will end abruptly.

Playback is fine as far as I can see. Didn't hear any clicks and the waveform is correct. You sure you don't have a problem with your sound card or something else?
## Post #8
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-12-29T11:44:28+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

The clicking starts appearing when you change the amplitude of the file bnnm. It plays back just fine normally without any volume change.
## Post #9
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2017-12-30T00:23:15+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

Excuse me, but unfortunately I do not understand some things:

1- "2835189" is the loop point of this track, but how can I remove the values you quoted?
2- Why them? How were they identified? Why two back and front or this value?
3- How can I disable looping and the two useless channels in the track with "test.exe -i file.xvag"? it's a command, right?
## Post #10
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-12-31T07:36:49+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

1/2. The click/pop occurs because the track has not reached what is called a "zero crossing" in the waveform when it goes to loop. Deleting two samples either side of the loop point fixes this issue a lot of the time and smoothes it out.

Open up the converted file in an audio editor like Audacity. Change any of the three boxes at the bottom of the window in Audacity (Selection Start) to show "Samples" instead of "Seconds".

After that, delete two samples before and after the loop point and the pop should be gone.

3. Save the following in notepad and with the extension .bat file to convert the file with no looping or a fadeout.

```
FOR %%a IN (*.xvag) DO test -l 1 -f 0 -o "%%a.wav" "%%a"
```
## Post #11
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2018-01-03T15:49:49+00:00
- Post Title: Datura (PS3/Soundtrack/.XVAG)

Thank you Brendan, I followed your advice and I finally succeeded to remove the loop and the 2 extra channels from the track, now I can play it perfectly as a normal stereo file without any kind of problem
