## Post #1
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-08-22T17:10:30+00:00
- Post Title: Disney Infinity .DCT (DICT) files

Hey guys, I'm playing around inside Disney Infinity and would love to have the dictionary files in some kind of easier-to-read-and-understand format. All the descriptions and other text is in here in plain text, but it's clearly some sort of database file (perhaps an SQL derivative?)

If anyone can help make sense out of this, I'd really appreciate it.

Thanks!

[http://www.mediafire.com/download/0y8aw ... sc_ps3.dct](http://www.mediafire.com/download/0y8awaenabaebn0/english_ntsc_ps3.dct)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-08-22T18:38:41+00:00
- Post Title: Disney Infinity .DCT (DICT) files

You can use Jenner's DCT tool for PURE. It's the same format.

Just drag .dct file on pure.exe and wait for generated .txt. Compilation of translated texts works the same.
[pure_dct_tool.7z](https://xentaxbackup.github.io/file/6568_pure_dct_tool.7z)
## Post #3
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-08-22T18:47:35+00:00
- Post Title: Disney Infinity .DCT (DICT) files

You're a god among men, you know that, right? I searched for anything DCT related and didn't come up with squat, so thank you!

It's too bad that it's an unorganized mess though, nothing is logically organized at all. Oh well, still helpful!
## Post #4
- Username: thisrock84
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 02, 2019 8:20 pm
- Post datetime: 2019-03-02T15:01:29+00:00
- Post Title: Disney Infinity .DCT (DICT) files

Hi,
I want to translate Disney Epic Mickey 2: The Power of Two. This tool can Extract 2 files but I think dat file is different than Pure game. So after Compile the file, the game not running and its not work for me. Have you got any idea?
## Post #5
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2022-04-10T20:03:36+00:00
- Post Title: Disney Infinity .DCT (DICT) files

> Reply from thisrock84 ↑Sat Mar 02, 2019 11:01 pm at Sat Mar 02, 2019 11:01 pm
>
> 
Hi,
I want to translate Disney Epic Mickey 2: The Power of Two. This tool can Extract 2 files but I think dat file is different than Pure game. So after Compile the file, the game not running and its not work for me. Have you got any idea?

Open the .dat file generated by the PURE tool and add this to the end:

```
#0|6500#0|6501#0|6502#0|6503
```


The game should now launch correctly. It seems this happens because Disney Interactive added extra data to the end of the DCT files. For some reason the PURE tool doesn't pick this up when decompiling, but it does pick it up when compiling (if you add it back).
