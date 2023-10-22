## Post #1
- Username: ZenkaiBoost312
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 16, 2022 2:55 pm
- Post datetime: 2022-06-16T06:59:06+00:00
- Post Title: NBA 2K6 Interleave [PS2 ADPCM]

Greetings,
I've extracted music from NBA 2K6 (PS2 version). I've found the audio I want but I can't find the right interleave to play the files without the left/right channel being unsynced. the sample rate from these songs are 22050. Some help would be greatly appreciated, please.

The files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1_MGKTvQKUvSzfIoNCQjq5rJqXuaU3qlo?usp=sharing)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-06-16T11:26:52+00:00
- Post Title: NBA 2K6 Interleave [PS2 ADPCM]

Did you try the interleave of 0x2000 I suggested on your previous post on Zenhax?
## Post #3
- Username: ZenkaiBoost312
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 16, 2022 2:55 pm
- Post datetime: 2022-06-18T15:50:17+00:00
- Post Title: NBA 2K6 Interleave [PS2 ADPCM]

Yeah but it working wrongly in some files. I must be doing something wrong. Do you can create a ".txth" for me?
## Post #4
- Username: Vnov93
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 08, 2022 6:16 am
- Post datetime: 2022-07-07T22:31:15+00:00
- Post Title: NBA 2K6 Interleave [PS2 ADPCM]

I was actually trying to do the same thing with. For all the regular audio files, like sound effects, player names, crowd noises, commentary, etc., pretty much any large value works. For the actual songs, some of them work with an interleave of 2000, but a lot of them do not. I can't figure it out either. Another problem is that some of the audio files are longer mixes of the beats they play in the Arena. So if you get the interleave down for one of them, the others will be off. If the songs you want are on "2K6: The Tracks", obviously you can just go buy the CD. That's what I have. But I'm assuming that's not your case. 

The only thing of help that I found a few months ago was some posts from the past saying that you can find the interleave of a file if you open it up in a Hex editor program and do a search for the first 0 x 10 bytes of data, but that has never worked for me any time I have tried it.

If you ever find a solution to this, let me know. Thanks a lot.
