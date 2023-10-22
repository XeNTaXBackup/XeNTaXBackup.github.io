## Post #1
- Username: Hayal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 12, 2021 11:28 pm
- Post datetime: 2021-05-16T23:44:58+00:00
- Post Title: Overlord *.pvp/.prp/.vpk files reimport

Hi there,

First of all, my goal is to repack these files with modified content.

Overlord uses quite a few proprietary fileformats, some of which the devs later re-used for their later games, such as Age of Wonders.

I had no luck peeking into these files using the modding tools included with Age of Wonders, they either crashed or identified the file as outdated. (Given the 10+ year difference between the games.)

Luckily, there are some Python Scripts available, for extraction purposes:
[https://github.com/mortalis13/PythonScr ... verlord.py](https://github.com/mortalis13/PythonScripts/blob/master/wav_extractor_overlord.py) (for .pvp, Credit: Mortalis13)
[https://github.com/REDxEYE/PRP_IO](https://github.com/REDxEYE/PRP_IO) (.prp, Credit: REDxEYE)

However, has anyone here had luck reimporting modified content into these package files?

For example, MinionVoiceData_ENGLISH also consists of multiple extra components such as .vpk and .debug-vpk, however they only seem to carry a few strings, when investigated further in a Hexeditor.

More info on the .pvp format: [https://www.reddit.com/r/overlordgame/c ... ame_files/](https://www.reddit.com/r/overlordgame/comments/jvs8sd/sounds_extraction_from_game_files/)

Examples: [https://www.mediafire.com/file/ff9v7pnx ... a.zip/file](https://www.mediafire.com/file/ff9v7pnxlw7cnho/Overlord_Data.zip/file)

Thanks!
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-17T15:18:09+00:00
- Post Title: Overlord *.pvp/.prp/.vpk files reimport

If you want to just replace WAV file data, the easiest solution is to use File Stripper
[http://wiki.xentax.com/index.php/Extrac ... e_Stripper](http://wiki.xentax.com/index.php/Extraction_tools#File_Stripper)
It has re-import option.

But if you plan to do more advanced stuff, then you should consider reverse engineering those file formats
and write some custom repacker or quickbms script.
Here are some tutorials for that [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #3
- Username: Hayal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 12, 2021 11:28 pm
- Post datetime: 2021-05-17T20:55:20+00:00
- Post Title: Overlord *.pvp/.prp/.vpk files reimport

Thanks for the heads up, it does exactly what I need it for! It properly caught all raw data just like the aforementioned Python Scripts, however, if it's not the exact same data inside the Wave file, it can't re-inject it into the given archive. Otherwise, the re-injection works.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-18T07:42:57+00:00
- Post Title: Overlord *.pvp/.prp/.vpk files reimport

I didn't really used this re-inject feature of this tool, but maybe you have to adjust the size of the new file to match the original one.
So you have to produce WAV file that is smaller than original and then fill it with zeroes using hex editor to match the size.
