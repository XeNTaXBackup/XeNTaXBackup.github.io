## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-13T16:23:44+00:00
- Post Title: FREEDOM FIGHTER

Hello

I need unpack *.wav pack
wav package use in :
freedom fighter
hitman 1,2.3

thank you
## Post #2
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-13T16:55:54+00:00
- Post Title: FREEDOM FIGHTER

> Reply from sajad
>
> Hello

I need unpack *.wav pack
wav package use in :
freedom fighter
hitman 1,2.3

thank you
That? WAV files. this is audio files!
Hitman WAV audio protected! You must dowload tool for playing files.
Find in Google.com Hitman .wav files. Good Look.
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-13T17:10:45+00:00
- Post Title: FREEDOM FIGHTER

no this archive include ogg file
but dont full extract with extractor program
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-14T11:49:13+00:00
- Post Title: FREEDOM FIGHTER

I have hitman 2 at home - I will look into it tomorrow, and see what I can come up with. I know about half of it already, so it shouldn't be too difficult.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-15T04:46:44+00:00
- Post Title: FREEDOM FIGHTER

This is what I have determined so far. There are 2 different archives containing the audio - one called streams.wav, and a bunch of smaller *.wav files that have an accompanying *.whd file outlining the file details. For the second one, this is how to read them...

```
| Hitman 2: Silent Assassin *.wav + *.whd |
+-----------------------------------------+

// WHD contains the details, WAV contains the file data

4    Archive Size (without header)
4    Archive Size (with header)
4    Unknown
4    Unknown

// for each file
X    Filename (null)
4    Unknown (6)
4    Unknown
4    Unknown (17)
4    Sampling Rate, khz (22050)
4    Unknown (4)
4    Unknown
4    File Size
4    Number Of Channels?, mono (1)
4    File Offset
4    Unknown
4    Unknown
4    Unknown


+--------------------------------+
| Hitman Contracts *.wav + *.whd |
+--------------------------------+

// WHD contains the details, WAV contains the file data

4    Archive Size (without header)
4    Archive Size (with header)
4    Unknown
4    Unknown

// for each file
X    Filename (null)
0-3  Padding (to a multiple of 4 bytes)
4    Unknown (6)
4    Unknown
4    Unknown (17)
4    Sampling Rate, khz (22050)
4    Unknown (4)
4    Unknown
4    File Size
4    Number Of Channels?, mono (1)
4    File Offset
4    Unknown
4    Unknown
4    Unknown
```


Note the code differs between the 2 game versions, namely on the padding bits. The way I check between versions is to read the 22050 field and double-check to see that it is 22050 - if not then I use the alternate format.


Now, I should point out that I think the audio is somehow encrypted - I couldn't see any simple encryption at first glance, ie nothing like a basic xor or anything, but i'm not too good at this so I may have missed something. This probably also occurs in the streams.wav file because I cannot see how to read it. Alternatively, the files could be compressed - although I havn't tested this.


Hope this helps.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-12T17:50:52+00:00
- Post Title: FREEDOM FIGHTER

These wave files (in reality are a collection of headerless audio data) use the ADPCM format.
I'm still searching ways for reading/converting these type of audio data (read also the threads about Jack Orlando and Nomad Soul) from raw files.

In the meantime, for other and future problems about audio files, a quick test to know if data is in ADPCM format is using Audacity and select the Import raw data from the Project menu, you will hear the original audio with some small distortion... I must still understand how much types of ADPCM formats exist, this is an unknown world for me!
