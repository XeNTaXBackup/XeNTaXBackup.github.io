## Post #1
- Username: krzys837
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 10, 2014 5:21 pm
- Post datetime: 2023-05-27T19:31:41+00:00
- Post Title: tex files Gadget PS1 game

Hello. I want to edit a small game for PS1. Inspector Gadget.
Text file is normal txt file. Graphics files like a font 
and language selector are a .tex files.
In TileMolester It can be view very unclear at 4, 8 and 15 bpp.
I attach a header of files and screenshot from tilemolster.
Can someone give me a advice?
[spoiler]


[/spoiler]
[Gadget files.rar](https://xentaxbackup.github.io/file/23848_Gadget files.rar)
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-06-02T08:48:09+00:00
- Post Title: tex files Gadget PS1 game

Hmm, the font pages are clearly 256x256 4bpp logical endian, but it's a cluttered mix of foreground glyphs and background/shadow glyphs, with the glyph bounding rects stored elsewhere. The vertical stripes are suspicious in bit layer 3. Also I see weird horizontal black lines in the data files you attached that I don't see in your screenshots (whatever program I use). If you can find the equivalent glyphs at runtime in video RAM, that might give you something to compare against. Have you tried randomly modifying the pixels in these files to verify it updates the glyphs at runtime, just in case the fonts are actually stored in different files?
[InspectorGadget.png](https://xentaxbackup.github.io/file/23868_InspectorGadget.png)
## Post #3
- Username: krzys837
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 10, 2014 5:21 pm
- Post datetime: 2023-06-03T05:43:05+00:00
- Post Title: tex files Gadget PS1 game

Hi.
Fonts are stored in a few files but the correct one is called "menu01.tex". I tried to edit it in TileMolester.
Like in your and my screenshot font has a normal letter and the same letters in black for shadows. I edited It by drawing pixel by pixel, one by one and I was able to draw a "Ś" Polish letter and make a red/white Polish Flag on English template.

In that form It can't be edited properly. It's too painfull, complicate and uncomfortable. It will took a half year. I need convert it to some normal file like dds or png or whatever.
