## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-07-11T08:23:33+00:00
- Post Title: Heart of Darkness PAF decoder needing compiling.

[http://www.sendspace.com/file/tqjxrr](http://www.sendspace.com/file/tqjxrr)

Simple enough. I found this thing after an extensive search for information on HoD's "hod.paf" file. If someone can quickly compile this for Windows 7 64-bit I think I'll be able to get my next project off the ground.
## Post #2
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-14T15:55:51+00:00
- Post Title: Heart of Darkness PAF decoder needing compiling.

someone can compile this [http://cyxdown.free.fr/pafdec/](http://cyxdown.free.fr/pafdec/) plz i have no compiler installed thank's
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-01-22T23:58:42+00:00
- Post Title: Heart of Darkness PAF decoder needing compiling.

just compiled with mingw, hope it helps
[paf_decoder.zip](https://xentaxbackup.github.io/file/6140_paf_decoder.zip)
## Post #4
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-01-23T17:32:34+00:00
- Post Title: Heart of Darkness PAF decoder needing compiling.

Its write for PS version of the game?

Begin from PC version hod.paf:

```
И...И°9.Иpi.Иx..Иhx.И`u.ИШ..И ѓ.И(Ї.ИиД.И...И`И.И€щ.И...ИXk.И.’.Иhъ.Иё..И@f.И(Е.Иh/.ИР..И.Ы.И€й.ИШш.Иш..И8..Иp..И€..Иђ..Ии..И0".И.-.Иё0.И€<.Иш?.ИpC.И0I.ИИM.ИxP.ИИU.И.[.Иш_.ИЁe.И(i.ИШk.ИШp.ИРu.И@{.ИH†.Packed Animation File V1.0.(c) 1992-96 Amazing Studio...............................................................................л...d.......А...........Ђ...С¦...(..Ђ...@...:............и.Ђ.ё...А...И...Р...Ш...а...и...р...р.Ђ.ш.Ђ.ш................... ...(.....Ђ...Ђ...Ђ.0...8...@...H...P...X..
```


In sources(paf_decoder.cpp):

```
*headerSignature = "Packed Animation File V1.0\n(c) 1992-96 Amazing Studio\n";
```
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-01-25T17:38:56+00:00
- Post Title: Heart of Darkness PAF decoder needing compiling.

Found no info about the version it is for but maybe you can just scrap the data before the header signature.
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-01-28T05:51:58+00:00
- Post Title: Heart of Darkness PAF decoder needing compiling.

Scrap dont help - extracts 4095 empty png files and one wav file, which is also extract wrong, I think, because the beginning is normal, but when not.
## Post #7
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-03-14T10:22:14+00:00
- Post Title: Heart of Darkness PAF decoder needing compiling.

Is anyone still reading this? PAF Decoder doesn't work. Here's what I did. Found a libpng3.dll, put it in the same folder, dnd'd hod.paf on paf_decoder.exe. I actually tried with 3 different versions of the game: English 1.0, English 1.4, French 1.4. The result is always the same:

```
Unable to read .PAF file header
```


Can someone, please, come up with a QuickBMS script or something?
## Post #8
- Username: finster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 26, 2015 6:20 pm
- Post datetime: 2015-08-26T10:22:42+00:00
- Post Title: Heart of Darkness PAF decoder needing compiling.

I joined this site out of interest for this decoder. if anyone can help me with it It'd be greatly appreciated.
