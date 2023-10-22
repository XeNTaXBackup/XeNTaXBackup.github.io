## Post #1
- Username: jonny5
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 05, 2020 8:34 am
- Post datetime: 2020-01-05T00:54:00+00:00
- Post Title: Requesting help on Dark Omen .FNT font file format

Hi everyone, is anyone able to help me decode the format of the Dark Omen fonts?

The list of font files in the game are as follows. In the brackets I've added a description of what I think the fonts are used for. 

- F_BOOKBD.FNT (books font, bold?)
- F_BOOKS.FNT (books font, standard text?)
- F_BOOKSR.FNT (books font, red?)
- F_BOOKSW.FNT (books font, white?)
- F_HELP.FNT (?)
- F_MENBG.FNT (menu font, big)
- F_MENBGR.FNT (menu font, big, red)
- F_MENSM.FNT (menu font, small)
- F_MENSMR.FNT (menu font, small, red)
- F_MESS_E.FNT (message font, English? if English, why is there no German?)
- F_MESS_F.FNT (message font, French? if French, why is there no German?)
- F_TITLE.FNT (?)
- F_TOOL.FNT (tooltip font?)

"BOOKS" fonts probably means anything in the game that is text written on parchment or paper (e.g. troop roster, troop catalog, magic item catalog).

For the main menu fonts, when you hover over an item, it goes red, so that's why I believe the ones ending in R are for red fonts. If that's the case, theoretically there would be some sort of colour table or red RGBA colour in the font file. Same story with the books red font—this is probably used for when you're replenishing troops in the troop roster. Note: the game ships with English, French and German variations of some assets, so this is why I'm confused about whether the _E and _F fonts are for English and French, respectively. It may be possible though if either or both of the _E and _F fonts can be combined for German? Probably not really that useful in helping to decode anyway...

Old Windows fonts are apparently named as such but through a hex inspector the Dark Omen fonts start with the string "FONT" whereas that's not mentioned in the Windows .FNT spec so I don't think they are the same. I've also used a .FNT template in the 010 hex editor program and it fails to decode them, so I'm pretty sure the Dark Omen fonts are not in this Windows format.

I don't want to break the forum rules and post a link to uploaded Dark Omen font files, so if you do want to take a look and don't have a copy of Dark Omen, please DM me and I'll send the fonts to you. Failing that, I believe there are plenty of places around where you can find a copy of Dark Omen.

Thanks in advance for anyone that is able to help out, and thanks for reading this far 

P.S. I originally posted in the Dark Omen forum for help but wanted to reach out to another audience as well: [http://forum.dark-omen.org/tools/lookin ... 520.0.html](http://forum.dark-omen.org/tools/looking-for-info-on-do-fnt-font-file-format-t1520.0.html)
