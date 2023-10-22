## Post #1
- Username: SimpleSymphony
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 14, 2022 4:35 am
- Post datetime: 2022-12-13T20:57:39+00:00
- Post Title: How do I play and convert City Builder's .mus files?

Hello! I've been trying to find a way to play the .mus sound files of City Builder (Wii) and/or convert them to a common format like .mp3, but with no success. I've tried using foobar with vgmstream, but it always fails with "unsupported format or corrupted file," and Finale Notepad gives me "enigma error -12." I think I was able to convert them with Audacity to a common format a long time ago when I first started this project, but the audio was scratchy, garbled, and just a mess all-around, not the wacky jazz I was looking for at all. I'm a total newbie to music ripping, and there aren't many recent and extensive guides on ripping Wii .mus files, so I'd like to get some help with this one! Here's the download link to the game's entire Sounds folder: [https://www.mediafire.com/folder/rbu62wf7dfu5i/Sounds](https://www.mediafire.com/folder/rbu62wf7dfu5i/Sounds), and the game uses the Vicious Engine, if that helps anyone. If you have any questions, please let me know! Thanks!
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2022-12-14T07:14:25+00:00
- Post Title: How do I play and convert City Builder's .mus files?

Here's the TXTH script needed for your samples:

```
channels = 1
sample_rate = 32000
start_offset = 0x2C
data_size = @0x28:BE

coef_offset = 0
coef_endianness = BE

num_samples = data_size

```


Save the scripts above as ".MUS.TXTH" and put it on the same directory as the MUS files. Then just drag one of the MUS files to foobar (If the length still shows "?", go to foobar preferences then check "Enable unknown exts").
Info about TXTH: [https://github.com/vgmstream/vgmstream/ ... oc/TXTH.md](https://github.com/vgmstream/vgmstream/blob/master/doc/TXTH.md)
## Post #3
- Username: SimpleSymphony
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 14, 2022 4:35 am
- Post datetime: 2022-12-15T02:42:37+00:00
- Post Title: How do I play and convert City Builder's .mus files?

> Reply from BloodRaynare ↑Wed Dec 14, 2022 3:14 pm at Wed Dec 14, 2022 3:14 pm
>
> 
Here's the TXTH script needed for your samples:
Code: Select allcodec = DSP
channels = 1
sample_rate = 32000
start_offset = 0x2C
data_size = @0x28:BE

coef_offset = 0
coef_endianness = BE

num_samples = data_size


Save the scripts above as ".MUS.TXTH" and put it on the same directory as the MUS files. Then just drag one of the MUS files to foobar (If the length still shows "?", go to foobar preferences then check "Enable unknown exts").
Info about TXTH: https://github.com/vgmstream/vgmstream/ ... oc/TXTH.md
It worked like a charm! Thank you so much!
