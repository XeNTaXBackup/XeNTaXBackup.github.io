## Post #1
- Username: yukiisama
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 10, 2012 10:54 pm
- Post datetime: 2012-06-13T13:05:41+00:00
- Post Title: help me unpack pak sound file

i guys 

i really need help 

i want to unpack a pak sound file and re pack it after i edit it =)    plssssssss help me 

this is the files 

[http://www.mediafire.com/file/tqi0pt09e2ccgfo/BOSS.rar](http://www.mediafire.com/file/tqi0pt09e2ccgfo/BOSS.rar)


thanks alot guys ^_^

sorry for my bad english...
## Post #2
- Username: yukiisama
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 10, 2012 10:54 pm
- Post datetime: 2012-06-16T14:22:27+00:00
- Post Title: help me unpack pak sound file

anyone =_=???
## Post #3
- Username: snailium
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 16, 2011 11:34 am
- Post datetime: 2012-08-30T06:07:33+00:00
- Post Title: help me unpack pak sound file

Here is the file structure.

Data is devided by truncks. Two kinds of truncks are observed - descriptive and data.

Descriptive trunck
- always 0x100 long.
- aligned to 0x1000000 address boundary (16K)
- file name is from 0x0
- file length is at 0xFC, uint32, big endian

Data trunck
- located just after corresponding descriptive trunck
- zero padding to 16K boundary, for the next descriptive trunck


Take E1A0.PAK as an example. It has 3 files.
- e1A0.scx, descriptor from 0x0 to 0xFF, data from 0x100 to 0x68F
- e1A0_00.BED, descriptor from 0x6C0 to 0x7BF, data from 0x7C0 to 0x273F
- e1A0_99.BED, descriptor from 0x2740 to 0x283F, data from 0x2840 to 0xA1BF
