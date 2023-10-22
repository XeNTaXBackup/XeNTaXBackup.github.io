## Post #1
- Username: Bokudan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 28, 2020 7:33 pm
- Post datetime: 2020-04-10T22:36:55+00:00
- Post Title: Help to view graphics PS2

Hi guys, I've seen  a python file to the Noesis tool that reads the pallete data and the texture information for a ps2 game road trip.

This opens nicely the 06.GSL file however the other files with the same structure can't open/are not completely correct. What do I need to change besides the initial sign of 0x1012,0x1040 or 0x1087? Thank you

This is the link with 3 texture sample of the game and the .py to place under noesis plugins
[https://we.tl/t-SQDJ0NXYiG](https://we.tl/t-SQDJ0NXYiG)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-11T21:36:56+00:00
- Post Title: Help to view graphics PS2

> Reply from Bokudan ↑Sat Apr 11, 2020 6:36 am at Sat Apr 11, 2020 6:36 am
>
> Hi guys, I've seen  a python file to the Noesis tool that reads the pallete data and the texture information for a ps2 game road trip.Hi, and who's the creator of that script?

> What do I need to change besides the initial sign of 0x1012,0x1040 or 0x1087? Thank youEverything. Looks like SCOREA05.GSL isn't compressed as SCOREA06.GSL is (try data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "g8 r8")).

Loading ...05.GSL as raw data into IrfanView (at the left) or try Noesis (at the right side), data offset used: 112 bytes:
.



SCOREA05-GSL.jpg (189.04 KiB) Viewed 77 times


(You need to care for the palette, of course.)
