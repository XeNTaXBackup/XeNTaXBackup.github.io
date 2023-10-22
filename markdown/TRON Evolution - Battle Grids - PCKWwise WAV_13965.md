## Post #1
- Username: jasonpatrick72
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 16, 2015 9:58 am
- Post datetime: 2016-02-14T07:24:10+00:00
- Post Title: TRON: Evolution - Battle Grids - PCK/Wwise WAV?

So Im trying to rip the music from TRON: Evolution - Battle Grids. I successfully extracted the WAVs from the PCK file using the wavscanner BMS script, but then when I try using any of the previous methods to convert a Wwise file to OGG, I get an error...

Heres a sample. 

[https://mega.nz/#!O0FQEaqT!FXiIj5VWAA7e ... CkTfe-wA_o](https://mega.nz/#!O0FQEaqT!FXiIj5VWAA7e5T_2DqqzyFS3TtdQW8pUVCkTfe-wA_o)

Hope someone can help
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-14T16:15:14+00:00
- Post Title: TRON: Evolution - Battle Grids - PCK/Wwise WAV?

Because it's not an OGG file at all.

I think it was extracted wrong. You see, from 10 MB it compresses to just 600k. Can you imagine what type of music can it be? A couple of notes in total silence?
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-02-15T06:23:41+00:00
- Post Title: TRON: Evolution - Battle Grids - PCK/Wwise WAV?

Definitely not OGG. It's most likely GC ADPCM which is what the Wii uses natively with a wwise header. Not sure if anyone has done any work regarding Wwise GC ADPCM.

The best solution I can give is to make GENH headers with VGM Toolbox using the Nintendo DSP 4-bit ADPCM setting and putting in the co-efficients.
