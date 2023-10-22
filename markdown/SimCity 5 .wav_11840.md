## Post #1
- Username: CzlowiekDrzewo
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 17, 2014 5:46 pm
- Post datetime: 2014-08-25T10:26:16+00:00
- Post Title: SimCity 5 .wav

Hello
I have a problem with .wav files extracted from SimCity 5. They are unplayable and when trying to import it as raw data, it's only noise. If it might help, here's dump with header:



And sample: [https://www.dropbox.com/s/71vuirwayuelz ... 0.wav?dl=0](https://www.dropbox.com/s/71vuirwayuelzr0/SCP_0x0d9e5710-0x40490000-0x0b67f070.wav?dl=0)
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2014-08-28T12:51:11+00:00
- Post Title: SimCity 5 .wav

RIFF Vorbis.
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-08-28T16:58:54+00:00
- Post Title: SimCity 5 .wav

You can use hcs64's tool [ww2ogg](http://hcs64.com/vgm_ripping.html) to convert it to standard OGG.

In command line:

```
ww2ogg.exe SCP_0x0d9e5710-0x40490000-0x0b67f070.wav --pcb packed_codebooks_aoTuV_603.bin
```


Then you can additionally use revorb tool (mentioned on hcs64's page), to fix seeking in that sound file.

Ex.

```
revorb.exe SCP_0x0d9e5710-0x40490000-0x0b67f070.ogg new_SCP_0x0d9e5710-0x40490000-0x0b67f070.ogg
```
