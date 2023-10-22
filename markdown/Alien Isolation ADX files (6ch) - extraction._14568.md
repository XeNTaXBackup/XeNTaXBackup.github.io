## Post #1
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2016-06-25T18:27:25+00:00
- Post Title: Alien: Isolation ADX files (6ch) - extraction.

Video files *.usm in Alien: Isolation can be extracted to video files and ADX-audio files, using VGMToolbox r1027.
The problem is, tools i use (vgmsteam r1013-test) can't extract 6-channel ADX to wav, they only create emty 1 kbyte files.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-06-27T00:59:58+00:00
- Post Title: Alien: Isolation ADX files (6ch) - extraction.

I don't think I've ever seen a 6 channel ADX, are you sure it isn't AIX or AAX?
## Post #3
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2016-07-08T12:33:56+00:00
- Post Title: Alien: Isolation ADX files (6ch) - extraction.

> Reply from hcs
>
> I don't think I've ever seen a 6 channel ADX, are you sure it isn't AIX or AAX?
Yes, they are 6 channel ADX, for sure.
Currently i extracted some of them succcesfully. It seems that errors were given by VGMToolbox r1027 when option "Extract video and audio" was choosen.
It seems that "extract audio only" works perfect and doesn't corrupt ADX files. Also, streaming information in several files starting from negative value (-1.344... etc), so using vgmstream's test.exe with -i key is necessary.
