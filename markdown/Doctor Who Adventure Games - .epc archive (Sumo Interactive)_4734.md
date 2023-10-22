## Post #1
- Username: dprogo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 07, 2010 12:03 pm
- Post datetime: 2010-07-10T17:55:03+00:00
- Post Title: Doctor Who Adventure Games - .epc archive (Sumo Interactive)

This is an amazing forum, and I really love the tutorials that I've found (chrrox's in particular), however, after 12 hours of poking around, I think I may just not be clever enough to grasp all of this on my own. In short, I'd love to get some help, if anyone is willing to help me understand.

Game: Doctor Who Adventure Games
Developer: Sumo Interactive
Engine: Emmersion
License: Free to Download (if you're in the UK or have a UK-based IP address)
Game Link: [http://www.bbc.co.uk/doctorwho/dw/theadventuregames](http://www.bbc.co.uk/doctorwho/dw/theadventuregames) ~250MB per chapter
Sample .epc Files: [http://www.sendspace.com/file/lx2hek](http://www.sendspace.com/file/lx2hek) ~33 MB

I'm trying to extract 3D models and their associated animations and textures from .epc files (I believe this extension stands for "Emmersion PaCkage", Emmersion being the name of Sumo Interactive's game engine). 

What I know from opening these files in a hex editor:
• @ byte 0 All .epc files start with 00000000 00000000 454D4446 (EMDF - Emmersion Data File?)
• @ byte 12 - 4-byte sequence that changes in each file (not sure yet what this represents) 
• @ byte 16 - 216 bytes of data that doesn't seem to change, except in one file I've looked at (amy.epc in the sample files)
• @ byte 232 - 20 bytes of a time and date (in that order) with values separated by a hex value of 20 
• @ byte 336 - 24 bytes. "Stever.ASUMOBUILd.ALIGNA" in ASCII 
• @ byte 360 - File listing starts. 
• Note: I believe "ALIGN" and "pad." are repeating values (ASCII) used before and after file names to pad them to an appropriate byte length.
• Padding notwithstanding, the filename lengths aren't always a consistent length of bytes.
• After each filename are a few tags followed by information. The first tag, EMTH (45 4D 54 48) seems to always be followed by the same data, different from .epc to .epc, but consistent for all files listed within each .epc
• The second tag, EMDT (45 4D 44 54), is followed by 4 bytes that I believe may indicate the offset at which each file begins (or ends?). This assumption is based on the fact that each successive listing has a higher EMDT value than the preceding file. (little endian)
• For the last file in the listing, there's no EMDT value, but there's an EMDH value that's higher than the preceding EMDT value.
• Beyond this, all the files are listed again, though in a different format, followed by what I believe may be the names of parts of the respective 3d files (many of these file names are .mb files, which I believe is a standard Maya 3d format) 
• SAMPLE: |EM_ANIMATOR_Chisholm|EM_LOCATOR_Ground|Pelvis|Waist|Spine|Chest|Collar_L|Shoulder_L|Elbow_L|Hand_L|Middle_01_L|Middle_02_L|

Not looking for a free lunch here, but I'd really appreciate any advice or input on how I might proceed further.

Please let me know if the information I've provided is insufficient. Thanks to anyone willing to help!
## Post #2
- Username: pashok6798
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 06, 2014 2:45 am
- Post datetime: 2017-10-29T08:47:30+00:00
- Post Title: Doctor Who Adventure Games - .epc archive (Sumo Interactive)

I tried to extract textures from game, but I don't know how to calculate count of mip-maps! If I don't mistake, almost all texture either DXT5 or DXT1. I was angry from some name of textures, because some textures didn't have own name. I suppose that names are tags for engine, because sometime I found in scripts some names and these names were in EPC archives. Very strange engine. If somebody want a tool, which can extract textures, I'll send here.
