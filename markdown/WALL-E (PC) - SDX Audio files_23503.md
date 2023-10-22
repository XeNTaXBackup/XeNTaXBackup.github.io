## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-24T08:18:29+00:00
- Post Title: WALL-E (PC) - SDX Audio files

I was trying to reverse SDX samples from WALL-E.
Here are results of my work
[http://wiki.xentax.com/index.php/Asobo_Studio_SDX](http://wiki.xentax.com/index.php/Asobo_Studio_SDX)

They are similar to the ones used in CT Special Forces, but I think they contain some custom ADPCM data.
I have written a simple extractor for WALL-E 
[https://github.com/bartlomiejduda/Tools ... DX_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Asobo%20Studio%20DPC%20DPS%20Research/Asobo_SDX_Tool.py)

So after extracting I have some kind of header (2048 bytes) and ADPCM audio data for each file.
Do anyone know how to convert them without "noises"?
The best I could do here is to use IMA ADPCM and 32kHz rate and the result file1.wav is in attachment below.

Samples + converted wav file: 
[https://drive.google.com/file/d/1pIDOP8 ... sp=sharing](https://drive.google.com/file/d/1pIDOP8Z-C28AvPX5wPGwNOhKsIEgACPq/view?usp=sharing)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-02-24T13:03:13+00:00
- Post Title: WALL-E (PC) - SDX Audio files

It looks like the codec is MS_IMA with an interleave of 0x24, and the audio data starts at 0x800 as you mentioned.  The number of channels is unclear, but seems to be mono in all the samples I listened to.  No idea what that header data is for.  The sample rate is contained in the file table - offset 4 in each entry.  I'm guessing that the 0x800 value following it is the offset of the actual audio data from the start of each file.
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-24T16:25:46+00:00
- Post Title: WALL-E (PC) - SDX Audio files

Ok, thank you. So case closed. I have updated wiki and my tool to be compatible with foobar.

A have also added TXTH header to github for others
[https://github.com/bartlomiejduda/Tools ... tream.txth](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Asobo%20Studio%20DPC%20DPS%20Research/.vgmstream.txth)

Now sounds are playing fine.
