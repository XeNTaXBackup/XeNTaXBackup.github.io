## Post #1
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-07-30T17:48:29+00:00
- Post Title: Ridge Racer (PS Vita) GIDX

Currently working on Ridge Racer Vita models, and unfortunately have come to a halt with the textures. I believe I have come across them as they're right next to the model data, but I can't seem to figure out what format this is. I should note these were acquired through a RAM dump.

A few things I have been able to determine however...

At 0x14, there's what seems to be texture width and height, and at 0x00 is the file size.

Can anyone help me with this format please? Much appreciated.
[GIDX_Samples.zip](https://xentaxbackup.github.io/file/16548_GIDX_Samples.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-07-31T06:17:39+00:00
- Post Title: Ridge Racer (PS Vita) GIDX

this Noesis python script will open your 2 samples.  


 tex_RidgeRacer_PSVita_tex.zip
(677 Bytes) Downloaded 37 times


supports morton swizzled dxt5.
you must give the samples the tex extension.
## Post #3
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-07-31T18:51:49+00:00
- Post Title: Ridge Racer (PS Vita) GIDX

Thank you so much Acewell! This is working great, much appreciated!
