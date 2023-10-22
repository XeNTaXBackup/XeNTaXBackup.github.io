## Post #1
- Username: Schtolteheim
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 22, 2017 10:29 am
- Post datetime: 2017-04-22T02:40:58+00:00
- Post Title: [Wii] Need Help Recompressing .VOL Archives Into .CXD Files

I'm currently working on a re-localization and re-dub of Arc Rise Fantasia for the Wii. I'm attempting to edit the dialogue files within the iso, but I'm encountering multiple issues.

Most of the dialogue files are stored within .VOL archives, which are in turn stored into .CXD archives. I can decompress the files with LZ77Ex, and I can re-import the contents of the .VOL archive without issue. However, when I attempt to re-compress them (which I've tried both with Derric's LZ77 compressor and Ovaron's LZSS compressor,) the re-compressed .CXD is significantly different from the original .CXD. Because of this, the new .CXD will not load in Dolphin, giving me a slew of invalid read/write errors, even when nothing within the .VOL archive was changed at all.

I suspect that whatever compression method these files use isn't standard LZ77, unlike most other Wii games. With that said, I have no idea what sort of algorithm could have been used on these files. If anyone here has any information about these archive formats, I would highly appreciate some help.

Thank you for reading.
