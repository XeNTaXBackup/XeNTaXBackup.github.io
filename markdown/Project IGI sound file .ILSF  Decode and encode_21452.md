## Post #1
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2019-12-01T09:24:37+00:00
- Post Title: Project IGI sound file .ILSF  Decode and encode

Hello Everyone!
I know this topic may look funny but for me its very important.
Here is Some .Wav sound files from #Project_IGI/
I think that they are PCM wav or maybe MP3 but they encrypted them with a header and the header first 16 looks like this _ ILSF........"V..  _   can anyone make a small program to encrypt and decrypt these files? 
a am attaching the samples here. 

please help me its very important for me.
[IGI 1 sound file.zip](https://xentaxbackup.github.io/file/17132_IGI 1 sound file.zip)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-12-01T11:43:17+00:00
- Post Title: Project IGI sound file .ILSF  Decode and encode

I'm not sure how to re-encode them (maybe FFMPEG?), but the audio is Interleaved DVI 4-Bit IMA ADPCM.  The actual audio data starts at offset 0x14, so you can use GENH in VGMToolbox to create playable files.  The header seems to be as follows:

0x00  "ILSF"
0x04  Version?
0x06  Interleave value?
0x08  Channels
0x0A  ??
0x0C  Sample rate
0x10  Number of samples
0x14  Audio data
## Post #3
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-12-01T20:41:34+00:00
- Post Title: Project IGI sound file .ILSF  Decode and encode

> Reply from DKDave ↑Sun Dec 01, 2019 7:43 pm at Sun Dec 01, 2019 7:43 pm
>
> 
I'm not sure how to re-encode them (maybe FFMPEG?), but the audio is Interleaved DVI 4-Bit IMA ADPCM.  The actual audio data starts at offset 0x14, so you can use GENH in VGMToolbox to create playable files.  The header seems to be as follows:

0x00  "ILSF"
0x04  Version?
0x06  Interleave value?
0x08  Channels
0x0A  ??
0x0C  Sample rate
0x10  Number of samples
0x14  Audio data

The uint16 value at 0x6 is not an interleave value with the samples provided. Channels are stored at 0x8 uint32, not uint16, removing the unknown value at 0xA. Maybe if there was stereo file would there be interleave, but it is mono.

Attached is an even easier method than using GENH, using the TXTH function of vgmstream:


 ilsf_txth.7z
vgmstream txth (254 Bytes) Downloaded 64 times



For this you will need foobar2000 with the vgmstream component:
[http://foobar2000.org](http://foobar2000.org) 

For some reason, txth sometimes fails with me and foobar, so just get the actual vgmstream with test.exe in case:

[https://github.com/losnoco/vgmstream/releases](https://github.com/losnoco/vgmstream/releases)


Rename those wavs to *.ilsf , and drag and drop them in the same folder as "test.exe". Also drag the TXTH in the same folder as "test.exe". Make sure it is named 
```
.ilsf.txth
```
 and not just 
```
ilsf.txth
```
 You need the "." in front, or else the function will not work. Happy decoding. As for encoding, I'd check FFMPEG out, not sure if it supports DVI4 though
