## Post #1
- Username: nodots
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 16, 2017 4:26 am
- Post datetime: 2017-01-15T20:49:33+00:00
- Post Title: Making an Xbox trainer manager, need XBTF file help

I noticed a severe lack of trainer managers, so I am writing one in Python/Tkinter. I need help with .xbtf support.

Features: (Working)
List of all (.etm) files in the directory (sorted).
Select a file on the left and click "Load file info" to display internal info.
Renaming of selected file.

To-do:
Add support for .xbtf files.
Check for duplicates using CRC32 on certain parts of the file only.
Display game art.

ETM support took like 5 minutes, all the pointers are at the start of the file and nothing is mangled.
XBTF support is the one thing I can't do alone. I can't read ASM inline in C. The source code to read this stuff is in the XBMC4Xbox project, and the file the read code is in has the most important bits in ASM inline in the C code. I can't make heads or tails of what data is fed to the code as I don't know C well enough.

If anyone could help me out, I would love it!
## Post #2
- Username: nodots
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 16, 2017 4:26 am
- Post datetime: 2017-01-16T20:32:20+00:00
- Post Title: Making an Xbox trainer manager, need XBTF file help

I just figured out what I couldn't figure out! XBTF support will come within the month (when depends on my amount of lazy).
