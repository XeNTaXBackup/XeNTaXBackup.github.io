## Post #1
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2020-11-26T02:31:58+00:00
- Post Title: Mario & Sonic at the RIO 2016 Olympic Games (.dsp file Wii U)

is it possible to convert .dsp to wav? (I already extracted from the se_system.acb with vgmtoolbox, now I have to convert the .dsp to wav)
screenshot [https://i.imgur.com/A2rm7CP.png](https://i.imgur.com/A2rm7CP.png)
## Post #2
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2020-11-27T00:52:38+00:00
- Post Title: Mario & Sonic at the RIO 2016 Olympic Games (.dsp file Wii U)

someone? (NOTE: the .dsp is different on the Wii U file)
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-27T07:59:57+00:00
- Post Title: Mario & Sonic at the RIO 2016 Olympic Games (.dsp file Wii U)

It seems that there is decoder in vgmstream for this format
[https://github.com/vgmstream/vgmstream/ ... _decoder.c](https://github.com/vgmstream/vgmstream/blob/master/src/coding/ngc_dsp_decoder.c)

So maybe you should try foobar + vgmstream plugin combination.
[http://www.foobar2000.org/](http://www.foobar2000.org/)
## Post #4
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2020-11-27T19:14:10+00:00
- Post Title: Mario & Sonic at the RIO 2016 Olympic Games (.dsp file Wii U)

I can't open or play .dsp files (because it's very different on the Wii U) and I get Unable to open item for playback (Unsupported format or corrupted file) (i installed the vgmstream plugin on foobar). How do I solve?
example: [https://i.imgur.com/m1PBv0x.png](https://i.imgur.com/m1PBv0x.png)
here the .DSP file:[https://mega.nz/file/iQoigRjR#Mtrf5Ph_i ... W26dsB1fYo](https://mega.nz/file/iQoigRjR#Mtrf5Ph_iZsI8q1AMYF9DQGv8C1hpYJhtW26dsB1fYo)
## Post #5
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2020-12-05T19:40:24+00:00
- Post Title: Mario & Sonic at the RIO 2016 Olympic Games (.dsp file Wii U)

any ideas??
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-06T12:03:47+00:00
- Post Title: Mario & Sonic at the RIO 2016 Olympic Games (.dsp file Wii U)

Some of them are already standard .dsp files, such as "se_system_decision" and they should already play without any problems.

For the other files that have "CWAC" as the first 4 bytes, you can just delete the first 32 bytes and they will then be normal playable .dsp files in Foobar, and you can convert them.
## Post #7
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2020-12-06T14:36:45+00:00
- Post Title: Mario & Sonic at the RIO 2016 Olympic Games (.dsp file Wii U)

How do I convert from mono to stereo in .dsp files or are they like this (some are stereo)??
## Post #8
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2020-12-07T05:21:18+00:00
- Post Title: Mario & Sonic at the RIO 2016 Olympic Games (.dsp file Wii U)

Or can I also convert the .dsp to .cwac and convert to .wav ??
