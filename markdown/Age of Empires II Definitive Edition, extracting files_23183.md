## Post #1
- Username: Red Khan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 18, 2020 9:20 am
- Post datetime: 2020-12-18T02:30:42+00:00
- Post Title: Age of Empires II: Definitive Edition, extracting files

Greetings!

I run into some problems while extracting files of AoE2:DE.

There is SFX.bnk. This file contains a lot of *.wwise_v files and some *.wav files. While I'm having no trouble extracting, converting and playing the  *.wwise_v files, I can't play *.wav for some reason.

Music.bnk contains some *.wav files, which are yet again not playable.

Also game has some files are located directly in game's folder, without being placed inside bnk, for example 667441127.wem Moreover Music.bnk contains a file name 667441127.wem
I tried some tools to convert it to some other format, but none of them worked and returned errors.
wwise_ima_adpcm -  "Invalid input file format. Expected Wwise IMA ADPCM. Found Format: 12352"
ww2ogg024 - "Parse error: expected 0x42 fmt if vorb missing"
The tool I found [here on this forum](https://forum.xentax.com/viewtopic.php?t=16474#p131776) - "Unhandled Exception: System.IO.EndOfStreamException: Unable to read beyond the end of the stream"

Are these files valid? And if yes - how can I convert these files to ogg?

All mentioned files can be found here - [https://dropmefiles.com/ZceoO](https://dropmefiles.com/ZceoO)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-18T19:37:07+00:00
- Post Title: Age of Empires II: Definitive Edition, extracting files

Foobar with the vgmstream plugin opens both of those .bnk files with no problems - and it will convert them to .ogg, or other formats.
## Post #3
- Username: Red Khan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 18, 2020 9:20 am
- Post datetime: 2020-12-18T19:50:31+00:00
- Post Title: Age of Empires II: Definitive Edition, extracting files

Thanks a lot, this worked!

I tried foobar, but didn't know about the plugin.
## Post #4
- Username: Mevrynth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 08, 2023 12:36 pm
- Post datetime: 2023-10-08T04:45:53+00:00
- Post Title: Age of Empires II: Definitive Edition, extracting files

I am sorry for reactivating an old topic.
I am trying to extract sound files from the current version of AoE2 DE but they have since been placed in pck files and bnk files extractor cannot be used on them.
