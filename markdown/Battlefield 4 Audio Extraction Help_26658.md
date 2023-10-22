## Post #1
- Username: Leighter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 14, 2023 8:50 am
- Post datetime: 2023-04-14T01:04:57+00:00
- Post Title: Battlefield 4 Audio Extraction Help

I have been attempting to extract audio from the Japanese version of Battlefield 4 mainly for voicelines. I have tried using these scripts to extract: [https://zenhax.com/viewtopic.php?f=9&t= ... tor#p42944](https://zenhax.com/viewtopic.php?f=9&t=9384&p=42944&hilit=bfeditor#p42944). 

I don't think I had any trouble with extracting the chunks as the total file size is 26gb, but I am unable to decode all of the audio. For some reason the shell output listed the filenames, but didn't convert some of them at all. It only converted about 1.3gb of sound files compared to a more complete extraction of about 20gb I found online. Am I not following the directions or is there a problem with this script? 

Also, I'm wondering if there is a different way of extraction BF4 audio, or is this the only option left?
[shelloutput.zip](https://xentaxbackup.github.io/file/23661_shelloutput.zip)
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-04-14T23:18:54+00:00
- Post Title: Battlefield 4 Audio Extraction Help

> Reply from Leighter ↑Fri Apr 14, 2023 9:04 am at Fri Apr 14, 2023 9:04 am
>
> ...Also, I'm wondering if there is a different way of extraction BF4 audio, or is this the only option left?
Oh my, those have been deprecated long ago, there is a better, complete way of doing what you are looking for at the following link:
[https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)

Before beginning, please delete any progress you have done so far, as those old methods where inaccurate.
You need the frostbite 3 folder of the scripts, first you use dumper.py to dump/extract entire game, then you must use the ebxtoasset.py script in order to get every single audio/sound the game has, DLCs included, assuming you have them too.

Have fun.
