## Post #1
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-08-24T05:59:49+00:00
- Post Title: FarCry 3 .ffd

i want make a translate patch for that game.
but i cant find anything for this ffd file, to edit  coordinates of font

this is a example
[trade_gothic_neurotic_default.zip](https://xentaxbackup.github.io/file/13243_trade_gothic_neurotic_default.zip)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-09-04T13:23:47+00:00
- Post Title: FarCry 3 .ffd

0x30 - Byte - Font name character count
0x31 - Char[] - Font name (Ascii)
0x4D8 - start of character set (Unicode)
0xBB3 - Path to font texture
0xBEB - Coordinates till EOF-4

Example coordinate entry:
0xBEB - unk (rises every 27 bytes by 256)
0xBEF - float - Top left
0xBF3 - float - top right?
0xBF7 - float - bottom left?
0xBFB - float - bottom right?
0xBFF - float?- unknown?
0xC03 - 3 bytes? - unknown?

In your example:
7857/27 = 291 (number of coordinates entries)
291*2 = 582 (number of characters in font declared)

Smallest value encountered:
0.03125
## Post #3
- Username: ramyzahran
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 23, 2017 7:41 am
- Post datetime: 2021-09-26T21:11:45+00:00
- Post Title: FarCry 3 .ffd

hi, im translating farcry 3,4,5 to ARABIC ,and i want to re-create this font [xbt&ffd] ,but i don't know how to edit ffd font cordinates..
can ANYONE help me??!
i searched almost every website for this but i am nearly desperate...

this is font files:
[FARCRY-Primal.zip](https://xentaxbackup.github.io/file/20902_FARCRY-Primal.zip)
## Post #4
- Username: AMININE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 12, 2021 9:29 pm
- Post datetime: 2021-10-13T18:33:11+00:00
- Post Title: FarCry 3 .ffd

this example : [https://prnt.sc/1w0nlwx](https://prnt.sc/1w0nlwx)

because it's not support THAI language font

can somone pls guild me something


Thanks....
## Post #5
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2021-10-18T05:15:09+00:00
- Post Title: FarCry 3 .ffd

[viewtopic.php?f=33&t=24615](https://forum.xentax.com/viewtopic.php?f=33&t=24615)
