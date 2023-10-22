## Post #1
- Username: ZolaKluke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 01, 2021 4:49 pm
- Post datetime: 2021-06-01T09:10:04+00:00
- Post Title: Blue Dragon dds files won't open

Hi, today I came across a Blue Dragon bms script to extract the game files and it has done so successfully and have been able to open audio files, text files, etc. The main problem I've been having is that the .dds files in the game won't open and I've tried both photoshop and dds viewer. I'll attach 4 files in the hopes that someone here can workout how out to open them.

Zip with dds files: [https://drive.google.com/file/d/1zxrQ-L ... sp=sharing](https://drive.google.com/file/d/1zxrQ-L7hRjPh1gwgS9TXzP99XCCjH7kE/view?usp=sharing)
## Post #2
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-06-02T06:32:04+00:00
- Post Title: Blue Dragon dds files won't open

There is not DDS header. Texture data starts in 0x800.
## Post #3
- Username: ZolaKluke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 01, 2021 4:49 pm
- Post datetime: 2021-06-02T11:55:03+00:00
- Post Title: Blue Dragon dds files won't open

> Reply from LinkOFF ↑Wed Jun 02, 2021 2:32 pm at Wed Jun 02, 2021 2:32 pm
>
> 
There is not DDS header. Texture data starts in 0x800.

That's very strange then since every texture in this game is labled as a dds file but isn't, wonder what the real format is then
## Post #4
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-06-03T04:11:26+00:00
- Post Title: Blue Dragon dds files won't open

> Reply from ZolaKluke ↑Wed Jun 02, 2021 7:55 pm at Wed Jun 02, 2021 7:55 pm
>
> 
That's very strange then since every texture in this game is labled as a dds file but isn't, wonder what the real format is then
You can use [Raw Texture Cooker](https://forum.xentax.com/viewtopic.php?t=16461). Rename DDS extension before using this tool.
