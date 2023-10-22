## Post #1
- Username: theismarius
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 14, 2017 8:11 am
- Post datetime: 2017-01-21T11:53:42+00:00
- Post Title: split .dat

does anyone know how to split data files but keepeng it in .dat files?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-21T17:02:20+00:00
- Post Title: split .dat

Talking about the mobys.dat I guess?

It's simple but you'll need to learn how to use a hexeditor:
selecting bytes  and writing the selection to a file. Any valuable hexeditor should be capable of that.
HexEdit (from Andrew Phillips) is free and can do it (Edit/Mark/Mark Position, Extend To Mark, Edit/Write Selection).

All you have to do is to search for IHGW (49484857) somewhere in the midst of the file, place the cursor onto 49, press ctrl-shift-end, then Edit/Write Selection.

(See, you even don't have to place a Mark.)
## Post #3
- Username: theismarius
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 14, 2017 8:11 am
- Post datetime: 2017-01-21T21:23:39+00:00
- Post Title: split .dat

ims trying to split a file called highmips.dat, which weight 315 mb, but need it to divided until each part weights 120 mb or less so I can use the dat2irb converter.
