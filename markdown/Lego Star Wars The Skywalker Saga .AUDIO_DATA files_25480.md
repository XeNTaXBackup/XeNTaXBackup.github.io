## Post #1
- Username: iteachvader
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 21, 2014 2:47 am
- Post datetime: 2022-06-02T03:04:06+00:00
- Post Title: Lego Star Wars: The Skywalker Saga .AUDIO_DATA files

I've been trying to convert the .AUDIO_DATA files from the new Lego Star Wars to no success, but a friend of mine on my Discord server managed to convert one using a Mac-only audio editor called Cog. I'm on Windows, so I can't tinker with the program myself. Apparently, Cog lists the file as being a Microsoft 4-bit ADPCM (mono/interleave) at a sample rate of 44,100, bitrate 178. I've tried using programs that supposedly convert this format to PCM, but nothing has worked.

Can someone help me out with this? Here's a link to one of the .AUDIO_DATA files.
[https://mega.nz/file/dI8knTZQ#tFCiL9hc0 ... uar1Dkgk4A](https://mega.nz/file/dI8knTZQ#tFCiL9hc0pJfDGCNJvEr1VhGT-7nqIECPuar1Dkgk4A)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-02T21:03:14+00:00
- Post Title: Lego Star Wars: The Skywalker Saga .AUDIO_DATA files

Can you upload more samples? Engine sound is not a good sample for finding audio format.

Best samples would be:
- some character dialogues/voices,
- music
etc.
## Post #3
- Username: iteachvader
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 21, 2014 2:47 am
- Post datetime: 2022-06-02T23:15:36+00:00
- Post Title: Lego Star Wars: The Skywalker Saga .AUDIO_DATA files

That file is the only one that doesn't work using the Cog program, I was hoping someone could figure out how to convert it if possible.
Try this file instead, the X-wing blaster cannon sound.
[https://mega.nz/file/sU1mHLxA#vboDxeDfm ... 7Xjdtmb5d8](https://mega.nz/file/sU1mHLxA#vboDxeDfmQDFXAZLJRZGVlvx0aG-VqhlR7Xjdtmb5d8)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-03T21:45:06+00:00
- Post Title: Lego Star Wars: The Skywalker Saga .AUDIO_DATA files

Not the best samples in the world, but I'll just post what I came up with and you can test it yourself on other samples.


So this is my script:

```
start_offset = 0x5B
channels = 2
interleave = 0x100
sample_rate = @0x0C
num_samples = data_size
```


You can save it with name ".audio_data.txth" and put it with other files.
Final effect should look like this [https://imgur.com/a/77dSsAV](https://imgur.com/a/77dSsAV)

Now you can install foobar2000 with vgmstream plugin
and you should be able to play your audio - just drag and drop your file to foobar's window.
## Post #5
- Username: iteachvader
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 21, 2014 2:47 am
- Post datetime: 2022-06-03T22:19:54+00:00
- Post Title: Lego Star Wars: The Skywalker Saga .AUDIO_DATA files

> Reply from ikskoks ↑Sat Jun 04, 2022 5:45 am at Sat Jun 04, 2022 5:45 am
>
> 
Not the best samples in the world, but I'll just post what I came up with and you can test it yourself on other samples.


So this is my script:
Code: Select allcodec = IMA
start_offset = 0x5B
channels = 2
interleave = 0x100
sample_rate = @0x0C
num_samples = data_size

You can save it with name ".audio_data.txth" and put it with other files.
Final effect should look like this https://imgur.com/a/77dSsAV

Now you can install foobar2000 with vgmstream plugin
and you should be able to play your audio - just drag and drop your file to foobar's window.

This almost works. It starts off fine for a moment, but then after a few samples it just goes crazy. I changed the channels from 2 to 1 which works better. Other samples just play poorly all throughout. Here's an example conversion:
[https://mega.nz/file/EJtTSASa#FyTAT-MPa ... 4GCLYodzJw](https://mega.nz/file/EJtTSASa#FyTAT-MPaQacL24zl-qvgiJYIQ2aO1VIZ4GCLYodzJw)
## Post #6
- Username: iteachvader
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 21, 2014 2:47 am
- Post datetime: 2022-06-04T04:00:35+00:00
- Post Title: Lego Star Wars: The Skywalker Saga .AUDIO_DATA files

Actually I tried it again just using VGMStream by itself without Foobar as a frontend, and it works flawlessly... except on one or two files. I'll compare the data in their headers with ones that work and see if I can tweak the script to fix the broken ones.

EDIT: Update! My friend cu2 on Discord suggested a fix for the looping sounds! On one file, I used a hex editor to remove the 44-byte loop portion of the header, and now it plays perfectly. I think that solves it!
