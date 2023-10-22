## Post #1
- Username: Jibun
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 16, 2020 11:07 pm
- Post datetime: 2020-05-16T16:07:00+00:00
- Post Title: Discworld 2 new localization

Hello all,

I am a programmer and I really love classic games, so I have decided I want to create a localization for Discworld II: Missing Presumed...!? (which was one of my first point-and-click adventures) to my native language.

I tried the naive approach of replacing the text in the already existent localization file ENGLISH1.txt to the translated one, however when I run the game in ScummVR it crashes.

I have been researching and I know the game was developed with the Tinsel Engine and it looks like the localization .txt files are somehow linked to the DW2.scn file, probably memory positions or something. DW2.scn is in a format I cannot see properly.

Here is all the information I have found about it:
[http://automagically.de/tinsel.html](http://automagically.de/tinsel.html)
[https://wiki.scummvm.org/index.php?title=Tinsel](https://wiki.scummvm.org/index.php?title=Tinsel)
It looks like the format documentation stored in REWiki is no longer available

I am quite new with this old and no-longer-existing file formats and almost-no-documentation stuff and I do not quite know how to tackle it.
Should I try to build the engine? And then what?
Could someone with a little experience give me a hand, even if its just some tips or some places to research.

Thanks!
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-05-25T22:32:39+00:00
- Post Title: Discworld 2 new localization

Hello. I'm not sure if I can help you, but I'll try.

> It looks like the format documentation stored in REWiki is no longer available

Why not use web archive?
[https://web.archive.org/web/20160805225 ... sel_engine](https://web.archive.org/web/20160805225750/http://rewiki.regengedanken.de/wiki/Tinsel_engine)
[https://web.archive.org/web/20130904192 ... Discworld)](https://web.archive.org/web/20130904192356/http://rewiki.regengedanken.de/wiki/.TXT_%28Discworld%29)
[https://web.archive.org/web/20130903115 ... /wiki/.SCN](https://web.archive.org/web/20130903115000/http://rewiki.regengedanken.de/wiki/.SCN)


> I am quite new with this old and no-longer-existing file formats and almost-no-documentation stuff and I do not quite know how to tackle it.
>
> Should I try to build the engine? And then what?
>
> Could someone with a little experience give me a hand, even if its just some tips or some places to research.

Ok, so I don't really know this Tinsel engine, but first thing I would do is to check 
text file in hex editor and change some strings without changing length of those strings
just to see if game crash or not. If this work fine and game won't crash, I would write
some simple text extractor, edit some strings and then tried to rebuild text file.
You can see some examples here --> [https://github.com/bartlomiejduda/Tools ... EW%20Tools](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools)
