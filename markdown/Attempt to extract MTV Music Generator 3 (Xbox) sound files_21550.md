## Post #1
- Username: LeoneFamily
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 30, 2019 3:54 am
- Post datetime: 2019-12-29T20:42:27+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

Hello, this is my very first post here! 

I've been trying to extract sound samples from MTV Music Generator 3 on the OG Xbox to sample some riffs in Audacity and MIDI programs, as I am an hobbyist musician and would really love to edit some of those samples and make some nice stuff out of them 

So, today I extracted the audio folders of the game disc. Already there are a couple of ready-to-play .wav files but they are all just full songs, they are not the individual samples. The only other file in the audio folder is a file by the name of dbbody.dbd, so I bought the full version of WATTO's Game Extractor 3.09 and attempted to open this file. The only thing that the program found in that file are 56 unnamed .pcx image files, 128 Bytes each, yet the actual file size of dbbody.dbd is over 900 MB. I tried searching for the in-game names of some of those samples using HxD (HEX viewer) but it found none of those sample titles. So I am powerless from this point on. If someone has the ability of extracting those samples I would be forever grateful! I will also ask any questions you may have  

For now, here is that mysterious dbbody.dbd file that I suspect is the one containing the audio samples:
[https://www.dropbox.com/s/2syh2b8gi6ioq ... y.dbd?dl=0](https://www.dropbox.com/s/2syh2b8gi6ioq4g/dbbody.dbd?dl=0)

Thanks again from an overly polite french-canadian!
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-12-30T13:36:05+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

That file is just a stream of raw 16-bit PCM, 44,000 Hz, mono audio data, almost 3 hours long, as far as I can tell.

I can't see a file table that references the individual files, so that must be stored elsewhere.
## Post #3
- Username: LeoneFamily
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 30, 2019 3:54 am
- Post datetime: 2019-12-30T14:32:23+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

> Reply from DKDave ↑Mon Dec 30, 2019 9:36 pm at Mon Dec 30, 2019 9:36 pm
>
> 
That file is just a stream of raw 16-bit PCM, 44,000 Hz, mono audio data, almost 3 hours long, as far as I can tell.

I can't see a file table that references the individual files, so that must be stored elsewhere.

Thanks a lot! That's already a good start, I'm going to extract the whole game then, see if you can find the table that references the files. 
Here is the full game files: [https://www.dropbox.com/s/7b4elpbjlmoms ... s.zip?dl=0](https://www.dropbox.com/s/7b4elpbjlmomsum/MTV%20Music%20Generator%203%20Files.zip?dl=0)

P.S. I was able to upload the data in Audacity and from pure luck I found one of the audio samples that I was looking for in the sea of 3-hour long audio   , but a nice reference would be necessary to find where are the other samples
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-12-30T15:47:58+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

The first file in outputx.wbd is a database of the wave sounds and where they're located in the dbd file
## Post #5
- Username: LeoneFamily
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 30, 2019 3:54 am
- Post datetime: 2019-12-30T16:15:49+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

> Reply from DKDave ↑Mon Dec 30, 2019 11:47 pm at Mon Dec 30, 2019 11:47 pm
>
> 
The first file in outputx.wbd is a database of the wave sounds and where they're located in the dbd file

Wow! Thanks again! But how do I read the file? With HxD I'm able to find the in-game names of these samples but the rest is gibberish, where is the sample time position written in the file?
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-12-30T16:48:11+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

The file table stores the actual offsets and sizes of the data.

Try this QuickBMS script - it will extract the data as playable .wav files ...
[mtvmg3.zip](https://xentaxbackup.github.io/file/17259_mtvmg3.zip)
## Post #7
- Username: LeoneFamily
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 30, 2019 3:54 am
- Post datetime: 2019-12-30T17:01:29+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

Wow it works like a charm! Thanks you sooo much, I'm going to have a lot of fun with these samples!  I couldn't thank you enough!
## Post #8
- Username: skripto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 17, 2020 6:10 pm
- Post datetime: 2020-12-17T10:11:39+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

Please provide download link for the samples bro!  I would really appreciate it!
## Post #9
- Username: noode
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 25, 2022 8:13 pm
- Post datetime: 2022-07-25T13:00:11+00:00
- Post Title: Attempt to extract MTV Music Generator 3 (Xbox) sound files

[https://www.mediafire.com/file/pvjkch0j ... s.zip/file](https://www.mediafire.com/file/pvjkch0jtfriw1p/MTVMG3_Samples.zip/file)

It's a 1 Time link Unfortunately, So download it as quick as you can before anyone else does!
