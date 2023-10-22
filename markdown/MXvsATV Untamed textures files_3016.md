## Post #1
- Username: WinDev
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 04, 2006 4:27 pm
- Post datetime: 2008-04-18T20:14:14+00:00
- Post Title: MXvsATV Untamed textures files

Hi guys,
Could anyone help me to figure out the texture format of MXvsATV Untamed PS2 version.

Like this : 
[MX_S_450f_Honda_Plastics_4_4.pst](http://www.mgp07.com/files/MX_S_450f_Honda_Plastics_4_4.pst)

Thx in advance
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-18T20:32:28+00:00
- Post Title: MXvsATV Untamed textures files

8 bit palettized image, X width specified in header. Cannot find Y though.
first block is 32bit indexes of palette, the rest of the body is image data.

import as RAW into photoshop with 512x and 340y for grayscale image.

this should be fairly simple to make a Conversion/Reconversion tool for.
## Post #3
- Username: WinDev
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 04, 2006 4:27 pm
- Post datetime: 2008-04-20T15:14:39+00:00
- Post Title: MXvsATV Untamed textures files

Thx Strobe.

Too bad for colors, but perhaps...
