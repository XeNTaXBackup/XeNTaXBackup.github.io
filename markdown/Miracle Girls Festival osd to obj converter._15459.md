## Post #1
- Username: delphist2008
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 02, 2015 6:43 pm
- Post datetime: 2016-11-06T19:26:14+00:00
- Post Title: Miracle Girls Festival osd to obj converter.

Since chrrox's "Project Diva X (Vita)" script crashes on MGF osd's, here is a small tool to convert them to wavefront obj. It's buggy as hell  and produces a complete garbage for some of the stage file, but hopefully works for all the chara models ("<some anime name>itm<number>.osd" ones).

[More images](http://imgur.com/a/pPaLX)
It reads only mesh info and diffuse materials, but not the skeleton and bone weights.
You will also need to extract all the textures using chrrox's Noesis plugin to png, starting from 0_0.png, then open the tool and select an .osd file. The resulting obj + mdl with the corresponding name will appear after a few seconds in the osd's folder.
When converting fig*.osd, the eyes will sometimes have the same material as the body, so try to assign eye material to "___group____" bodypart.

Source is also included, but it's shitty 
P.S.: Can someone share DLC costumes for this game?
[MGF2OBJ.zip](https://xentaxbackup.github.io/file/11886_MGF2OBJ.zip)
## Post #2
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2016-11-11T12:39:02+00:00
- Post Title: Miracle Girls Festival osd to obj converter.

Opening the file, the program was closed at moment 
It tested on Windows 10 64bit
## Post #3
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-11-12T06:59:27+00:00
- Post Title: Miracle Girls Festival osd to obj converter.

Currently testing them all. So far I've found out that all the Arpeggio girls 2nd costumes have problems. Haruna and Takao's costumes don't even convert, and Iona's has vertex problems. They are arhitm002, ariitm002, and artitm002.

Hopefully at some point, there will be animation support for these models. I'm too lazy to do facials by hand ; - ;..... I'm guessing you separated the pieces for Karen by hand.
## Post #4
- Username: Cyberpixie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 23, 2017 8:22 pm
- Post datetime: 2017-04-23T15:03:35+00:00
- Post Title: Miracle Girls Festival osd to obj converter.

I tried to use this but all I got was an MTL file without an OBJ and some nameless files that crash the windows explorer when I try opening them on notepad. What should I do?
