## Post #1
- Username: Sorinkun
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 24, 2016 12:49 am
- Post datetime: 2016-03-23T17:10:52+00:00
- Post Title: [PC Doujin] .dat file contains graphic resources - HELP!

There's this game Nekketsu Kakutou Densetsu for NES which got a PC remake by a japanese guy and adds more everything like more players on same screen, ability to design your maps and program them and add object with help of .obj text files and more (cuz this is not the important thing now).
The character bodies look like this:
[https://postimg.org/image/ep425lq1d/](https://postimg.org/image/ep425lq1d/)
This is the body that is used for brawler class. There are 5: brawler class, martial arts class, kung fu class, judo class and tiggers. (body0x.bmp in 256 color format ).

Here is the game.
[http://www.filedropper.com/kd_1](http://www.filedropper.com/kd_1)
Controls are WASD to move J to punch K to kcik L to jump U to block.
Q for select and E for start.

C'mon you have to know this game from your childhood! It's a Kunio kun game, maybe you've heard of River City Ransom...?

Anyway, the graphics are stored in Graphic folder and the .dat files which determines the way the body0x.bmp is read is located in Data folder as CharGraphic0x (CharGraphic00 starts with body01.bmp just in case you got troubles ).

I'm looking for a way to edit those .dat files to make my own body0x.bmp. And it's possible, there are modded versions of the game which has those files modified somehow!!

A 15 year old did this and hes gone years ago and I cannot ask him.... :/

Please I need help!

If you want, I can can give you the version which has these .dat files edited.

PS: I found out the game was made in VC++ and DirectX 6. Don't know if it helps.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-26T10:30:40+00:00
- Post Title: [PC Doujin] .dat file contains graphic resources - HELP!

try to split up the bitmaps into smaller pieces to get a deeper understanding of the sizes:



KD-split.jpg (44.38 KiB) Viewed 51 times


(The horizontal white lines are inserted while the vertical ones are overwriting pixels so don't be confused.)

Once u know how this puzzle works you could do some changes.
That will be hard but it's the easiest approach I could think of.

If you told me that there's a "vertical scheme" (and which) I could create an app for it.
## Post #3
- Username: Sorinkun
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 24, 2016 12:49 am
- Post datetime: 2016-03-31T16:53:05+00:00
- Post Title: [PC Doujin] .dat file contains graphic resources - HELP!

I know that already.
It's also present in .nes file when you open it with Tile Layer Pro, the same form...

But how could I edit the .dat file so that the graphic is readed in another form...
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-31T20:29:51+00:00
- Post Title: [PC Doujin] .dat file contains graphic resources - HELP!

> Reply from Sorinkun
>
> I know that already.If you know that already, then what relations did you draw to the regular patterns in CharGraphics00.dat?

Which changes did you try, which were the results?

If you know 0x86 assembler you could start the exe (tested on XP, 32 bit with ollydbg).
Tracing/setting a breakpoint, here for example, requires to start the game in windowed mode:

```
0047ADF4  |.  68 70974B00   |PUSH OFFSET 004B9770                    ; |<%s> = "C:\KD"
0047ADF9  |.  68 485D4B00   |PUSH OFFSET 004B5D48                    ; |Format = "%s\Data\CharGraphic%02d.dat"
0047ADFE  |.  8D95 E8FEFFFF |LEA EDX,[EBP-118]                       ; |
0047AE04  |.  52            |PUSH EDX                                ; |Buf
```


Good luck.
