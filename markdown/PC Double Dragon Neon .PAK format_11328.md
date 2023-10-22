## Post #1
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2014-03-17T04:06:12+00:00
- Post Title: PC Double Dragon Neon .PAK format?

So I tried using the QuickBMS script for the Double Dragon Neon .PAK format from here: [viewtopic.php?f=10&t=10523](http://forum.xentax.com/viewtopic.php?f=10&t=10523)
Unfortunately, it spits out an empty .GR2 file upon using the extractor. I'm assuming the PC version of the game uses a different compression format compared to the XBLA and PSN versions of the game, so if anyone can provide a proper QuickBMS script for the PC version of the .PAK files, it'd be greatly appreciated.

Here's a sample of what I'm talking about:  [http://filesmelt.com/dl/abobo.pak](http://filesmelt.com/dl/abobo.pak)

Thanks!
## Post #2
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-17T15:06:38+00:00
- Post Title: PC Double Dragon Neon .PAK format?

Check Duck Tales PAK-tools
## Post #3
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2014-03-18T01:05:52+00:00
- Post Title: PC Double Dragon Neon .PAK format?

While it seems to load the .pak files, the program freezes upon extracting the files and gives me some unreadable .gr2 files. Any possible fix for the DuckTales PAK Tools by any chance?
## Post #4
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-04-28T09:15:25+00:00
- Post Title: PC Double Dragon Neon .PAK format?

I found a solution!

In the script you found simply edit the first line, instead of "endian big" write "endian little".

The "new" script will be: 

```
get filetable long
get files long
get dummy longlong
math filetable + 0x40
for i = 0 < files
get offset long
math offset + filetable
get size long
getct name string 0x3a
getct filename string 0x00
savepos off
math b = 0x4
math a = off
math a % 0x4
if a == 0
get dummy longlong
else
math b - a
math off + b
goto off
get dummy longlong
endif
log filename offset size
next i  

```


(Script taken from here: [viewtopic.php?f=10&t=10523](http://forum.xentax.com/viewtopic.php?f=10&t=10523))
## Post #5
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2014-04-29T02:31:44+00:00
- Post Title: PC Double Dragon Neon .PAK format?

It worked! Thanks
## Post #6
- Username: lavrov
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 11:39 pm
- Post datetime: 2014-10-05T14:29:28+00:00
- Post Title: PC Double Dragon Neon .PAK format?

Linked theme: [viewtopic.php?f=32&t=10687](http://forum.xentax.com/viewtopic.php?f=32&t=10687)
I wrote a console tool for that ([https://github.com/artlavrov/paktools](https://github.com/artlavrov/paktools)).
