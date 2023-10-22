## Post #1
- Username: Zero Diamond
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 27, 2009 7:10 am
- Post datetime: 2009-12-27T10:09:05+00:00
- Post Title: [DOS] Terminator Rampage / Terminator 2029 Files

I've been struggling with a couple of file types in the early Bethesda Terminator games over the last couple of days, trying to figure out what exactly they are.  I'm fairly certain that they contain graphics, probably in the same .IMG format as is found in their .BSA files, but I have no idea as to how to get them out.  I figured since it looks like .BSA is a fairly universal storage method for Bethesda games that there might be some answers out there as to what these files are and how to extract them, but no dice as far as I've seen.  The extensions being dealt with here are .CFA and .DFA for Rampage and .DFA, .CIF, .DFF, and .CAF for 2029.  Rampage's .IMG files can be viewed properly with [Game File Explorer](http://www.google.com/url?sa=t&source=web&ct=res&cd=2&ved=0CAsQFjAB&url=http%3A%2F%2Fmirrored.xentax.com%2Fgfe%2Findex.html&ei=_C03S6iXL82ztge43vyQCQ&usg=AFQjCNFy5waEx1ZW1nFxbkuYoss90iTkcw&sig2=nHlvVFcWw94lG0_d8HuJHg).  It seems like 2029's may be able to as well, but the ones I've tried so far have come up a garbled mess.

Linked below (my hosting) is a ZIP containing two ZIP files, each containing a sample of the filetypes in question and a sample of that game's .IMG files (in the event that the two types of .IMG are different in some way).  Any help would be greatly appreciated!

[Terminator Rampage + 2029 Files](http://www.zxdware.net/terminator_files.zip)
## Post #2
- Username: Zero Diamond
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 27, 2009 7:10 am
- Post datetime: 2009-12-30T20:21:58+00:00
- Post Title: [DOS] Terminator Rampage / Terminator 2029 Files

Terminator Rampage's CFA, DFA, and SET files are all exactly the same format as those of The Elder Scrolls: Arena, whose resources can be dumped using [WinArena](http://www.tesnexus.com/downloads/file.php?id=8516); the program can't directly load Terminator Rampage's files, but it you rename TR's files to match the ones in TES:A's BSA file and inject them using [BSA_F-EX](http://www.projet-french-arena.org/files/bsa_f-ex_1.3.2.7z) you can dump the files since both games utilize the same in-game palette.

According to the included source of WinArena, CFA files are a series of RLE compressed images that make up the frames of an animation.  DFA is practically the same except it is utilized for animations where the whole image doesn't change, instead storing small parts of the image that change as the other frames most of the time.  I didn't find the information regarding the SET files, but those contain sets of textures so I assume it's probably something similar.  It's all documented fairly well in the source; it'd have to be for a rube like me to take anything away from it at all!

Still no information regarding Terminator 2029 however.
