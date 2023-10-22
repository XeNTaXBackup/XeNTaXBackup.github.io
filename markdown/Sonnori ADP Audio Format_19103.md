## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2018-11-23T15:57:30+00:00
- Post Title: Sonnori ADP Audio Format

Found in two games - [Steel Empire](http://www.hardcoregaming101.net/korea/part2/company-sonnori.htm#steelempire) and [Arcturus](http://www.hardcoregaming101.net/korea/part2/company-sonnori.htm#arcturus).

Header - 24 or 26 bytes
Header 1 - 10 00 00 00 22 56 00 00 02 00 00 00 [Arcturus]
Header 2 - 10 00 00 00 22 56 00 00 02 00 00 00 FE (last could be different) [Steel Empire]
Format (not sure) - 8 bit, Sign Bit, Mono, 22050

Looks like ADPCM variant.

Few samples - [https://dropmefiles.com/Fqw9k](https://dropmefiles.com/Fqw9k)
## Post #2
- Username: Corak
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 13, 2014 9:34 am
- Post datetime: 2020-11-19T00:20:17+00:00
- Post Title: Sonnori ADP Audio Format

Searched for solution too.
1. Need to rip ADP files with "pakext" utility from ArcData.
pakext.exe music.pak
[http://coraksoft1.narod.ru/games/RPG/Arcturus/pakext.7z](http://coraksoft1.narod.ru/games/RPG/Arcturus/pakext.7z)

2. ADP are ADPCM_IMA method packed. Closest are .APC method, so you can unpack them to PCM wavs with ffMpeg:
ffmpeg -c adpcm_ima_apc -i "%1" -af "asetrate=22050" %~n1.wav
[http://coraksoft1.narod.ru/games/RPG/Ar ... _to_wav.7z](http://coraksoft1.narod.ru/games/RPG/Arcturus/ffmpeg_adp_to_wav.7z)
