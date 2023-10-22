## Post #1
- Username: Inuyasha22
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 01, 2020 7:06 am
- Post datetime: 2022-12-11T10:05:23+00:00
- Post Title: ACT File

Hello,

so I got this file containing textures from a game named "WOLF". The game folder contains several of these .ACT files.
I did some replacing and swapping around and found the one file containing something I direly need.

What's in the file:

Plus several variations of the wolves and the background.

The file itself:
[http://www.raven-woods.de/FE00.ACT](http://www.raven-woods.de/FE00.ACT)

Tried feeding the bytes to an array and draw it directly.
Fed it to photoshop as raw.
No success so far.

Any idea what to do with the file in order to get the graphics out?
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-01-08T08:37:25+00:00
- Post Title: ACT File

(I have no answers, only questions)
What architecture? (that helps figure out things like graphics and palette format)
What OS? (there are many results searching for "wolf game", but I'm assuming DOS?)
Do you have a pure screenshot without the extra filtering or zooming (to extract the actual color indices)?
Are you sure there are wolves in this file, and not just background mountains and trees?
Have you tried drawing FE00.ACT starting from 0x5463B with a size of 320x96, 8-bit palette indices, and standard imaging left-to-right top-to-bottom flow? (see below)
Have you looked for hex bytes corresponding to the palette colors in the game files? e.g. The background sky color above the mountain is palette index 95 (0x5F) with RGB (211, 227, 251) or stored as VGA 6-bit per channel hex (0x34, 0x38, 0x3E). The palettes are sometimes stored in the corresponding graphics file, and sometimes stored separately (e.g. .pal files).
How about trying DOSBox-X's debugger commands like "VGA DACPAL" to dump the palette, which would help find it in the original data?
[FE00.ACT-5463B.png](https://xentaxbackup.github.io/file/23271_FE00.ACT-5463B.png)
## Post #3
- Username: Inuyasha22
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 01, 2020 7:06 am
- Post datetime: 2023-01-15T10:40:40+00:00
- Post Title: ACT File

> Reply from piken ↑Sun Jan 08, 2023 4:37 pm at Sun Jan 08, 2023 4:37 pm
>
> 
What architecture? (that helps figure out things like graphics and palette format)
- I guess x86? 

> Reply from piken ↑Sun Jan 08, 2023 4:37 pm at Sun Jan 08, 2023 4:37 pm
>
> 
What OS? (there are many results searching for "wolf game", but I'm assuming DOS?)
- Definitely DOS

> Reply from piken ↑Sun Jan 08, 2023 4:37 pm at Sun Jan 08, 2023 4:37 pm
>
> 
Do you have a pure screenshot without the extra filtering or zooming (to extract the actual color indices)?
- 

> Reply from piken ↑Sun Jan 08, 2023 4:37 pm at Sun Jan 08, 2023 4:37 pm
>
> 
Are you sure there are wolves in this file, and not just background mountains and trees?
- Yes, because the whole screen goes blank when the file is emptied, not only the background. Except for the UI.
But looking at your result I start to doubt that logic of mine   

> Reply from piken ↑Sun Jan 08, 2023 4:37 pm at Sun Jan 08, 2023 4:37 pm
>
> 
Have you tried drawing FE00.ACT starting from 0x5463B with a size of 320x96, 8-bit palette indices, and standard imaging left-to-right top-to-bottom flow? (see below)

> Reply from piken ↑Sun Jan 08, 2023 4:37 pm at Sun Jan 08, 2023 4:37 pm
>
> 
Have you looked for hex bytes corresponding to the palette colors in the game files? e.g. The background sky color above the mountain is palette index 95 (0x5F) with RGB (211, 227, 251) or stored as VGA 6-bit per channel hex (0x34, 0x38, 0x3E). The palettes are sometimes stored in the corresponding graphics file, and sometimes stored separately (e.g. .pal files).
- Looks like there are like 6 palette files in the folder. Other than that I didn't check the rest yet. 

> Reply from piken ↑Sun Jan 08, 2023 4:37 pm at Sun Jan 08, 2023 4:37 pm
>
> 
How about trying DOSBox-X's debugger commands like "VGA DACPAL" to dump the palette, which would help find it in the original data?
- Worth a shot, thanks!
