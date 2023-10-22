## Post #1
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2020-11-08T21:10:08+00:00
- Post Title: Identify unknown wave format

Wave files from the game Tom Clancy's Rainbow Six Siege previously extracted as ".lwav" files (wwise adpcm) using "[pck_AKPK_extractor.bms](https://forum.xentax.com/viewtopic.php?p=80192#p80192)" and "[func_getTYPE.bms](https://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577)" are being extracted as ".wav_unknown" files after an update.

Any idea what wave type this could be and how to convert it?

Archive with samples of old and new files: [removed]
## Post #2
- Username: Silvris
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jul 16, 2019 5:44 am
- Post datetime: 2020-11-08T22:55:41+00:00
- Post Title: Identify unknown wave format

It's still WWise, just rename .wav_unknown to .wem and it will be read by vgmstream. To be a little more specific, vgmstream gives Platinum 4-bit ADPCM, but with the same WWise RIFF header.
## Post #3
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2020-11-09T18:30:42+00:00
- Post Title: Identify unknown wave format

Thanks a lot for the quick response, renaming and vgmstream was the way to go!
