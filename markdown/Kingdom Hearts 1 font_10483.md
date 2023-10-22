## Post #1
- Username: crazycatz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 13, 2012 4:27 am
- Post datetime: 2013-06-02T02:26:10+00:00
- Post Title: Kingdom Hearts 1 font

I'm trying to modify the font used in Kingdom Hearts 1, and hit a little snag. There's 2 fonts in the game: "menu/sysfont.bin" and "kanji.knj". I can modify the sysfont (it uses the same format as the "sys.bin" font in KH2, in fact), but I can't get at kanji.knj. I get trash reading it like sysfont, and reading it like a "evt.bin" font from KH2 crashes.

I'm not very good at figuring out image formats, so I'm hoping someone here might be able to help. I've attached the font file and a partial texture of it (pulled via TexMod) from the English version of the game.

Any help would be appreciated.  

Edit:
For anyone interested in this, I'm pretty sure that the first 256*1024 bytes are image data and I know, through memory editing, the data after that is "width" data. The width data seems to be a single signed byte for each character, and specifies each characters width (ex: setting to 0 makes the characters overlap).

Edit 2:
Anyone have any idea on this? Through more memory editing, I think the font is "swizzled" (or whatever it is). In addition, each byte is split. The 0xF0 portion affects 1 half, the 0x0F affects the other half (one is top half, one is bottom half; sorry, I forgot which is which). I'm also assuming the font is monochrome, since it has 1/2 a byte per pixel and the font for KH games usually are.
[KH1_Kanji_font.zip](https://xentaxbackup.github.io/file/6443_KH1_Kanji_font.zip)
## Post #2
- Username: crazycatz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 13, 2012 4:27 am
- Post datetime: 2013-06-24T06:39:31+00:00
- Post Title: Kingdom Hearts 1 font

Well, I cracked the format myself. Was able to convert to a BMP, edit, convert back, and it all work right in-game.
For anyone interested, I attached the tools, source (please excuse the odd choice of language ), and a sample font file.
[Kanji.7z](https://xentaxbackup.github.io/file/6479_Kanji.7z)
## Post #3
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2013-11-25T22:49:41+00:00
- Post Title: Kingdom Hearts 1 font

bump cause you deserve it. =P
