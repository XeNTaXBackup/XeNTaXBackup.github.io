## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-28T13:03:14+00:00
- Post Title: correct GC ADPCM extension

Hi there!

The game "Sniper Elite" for Wii has GC ADPCM for audio but the file extension is *.sfx. I'm pretty sure that the header variant is supported by vgmstream but the extension needs to be changed. Does anybody have an idea what the correct extension would be?
Here's the header:
Any help is appreciated! 

Regards, Timo
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-01-28T14:46:21+00:00
- Post Title: correct GC ADPCM extension

Here's a list of the GameCube extensions supported by vgmstream. Try these and see if any work 

```
- .aaap
- .agsc
- .amts
- .asr
- .bns
- .bo2
- .capdsp
- .cfn
- .ddsp
- .dsp
  - standard, optional dual file stereo
  - RS03
  - Cstr
  - _lr.dsp
  - MPDS
- .gca
- .gcm
- .gsp+.gsp
- .hps
- .idsp
- .ish+.isd
- .lps
- .mpdsp
- .mss
- .mus (not quite right)
- .ndp
- .pdt
- .sdt
- .smp
- .sns
- .spt+.spd
- .ssm
- .stm/.dsp
- .str
- .str+.sth
- .sts
- .swd
- .thp, .dsp
- .tydsp
- .vjdsp
- .waa, .wac, .wad, .wam
- .was
- .wsd
- .wsi
- .ydsp
- .ymf
- .zwdsp
```
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-28T15:29:18+00:00
- Post Title: correct GC ADPCM extension

Thanks.  However, none of these work. Is this a new variant? For your information, the interleave is 8.
