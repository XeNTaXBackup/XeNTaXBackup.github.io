## Post #1
- Username: omera
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 10, 2006 11:20 pm
- Post datetime: 2006-06-10T15:31:04+00:00
- Post Title: Eye of the beholder 3

Hi to you, ho great XeNTax ! 

So glad this place exists...

So !

I would be really pleased I you could take a look at 
"Eye of the beholder 3 - Assault on myth Drannor"

Game sheet :
[http://www.abandonware-france.org/ltf-jeu.php3?id=223](http://www.abandonware-france.org/ltf-jeu.php3?id=223)
Direct download :
[http://www.abandonware-france.org/ltf-t ... php?id=223](http://www.abandonware-france.org/ltf-telecharger.php?id=223)

The resources are stored in the EYE.RES file.

XWE program (extended wad editor) does a first job of "exploding" the .RES file and displaying all the entries found in it, but sadly, can hardly display only a few of them.

I'm greatly interested in the images found in this archive. I know there is some palette entries, and that images are probably bitmap (bmp ?).

If you could help, that would be awewsome !

Thanks in advance,

Best regards,

SN.
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-10T22:41:19+00:00
- Post Title: Eye of the beholder 3

looking at it. currently dont have a single clue of what graphics format
they have stored the gfx in.

The references in the file states to ILBM and BMP pictures,
but there are no such things in the archives. they must have made
an custom format for those games.

(i did however successfully rip out all music from the game) :/

but that was sadly not what you wanted
## Post #3
- Username: omera
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 10, 2006 11:20 pm
- Post datetime: 2006-06-11T18:36:21+00:00
- Post Title: Eye of the beholder 3

Ha ! Thanks for you time Strobe...

Any more hint ? Any good soul that would like to help a poor desesperate gamer ?
## Post #4
- Username: mirekluza
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 27, 2006 2:57 am
- Post datetime: 2006-11-26T19:34:43+00:00
- Post Title: Eye of the beholder 3

See the following links for the information about the AESOP engine (which is the base of the "Eye of Beholder 3" and the "Dungeon Hack" games):

[http://vogons.zetafleet.com/viewtopic.php?t=13168](http://vogons.zetafleet.com/viewtopic.php?t=13168)
[http://rewiki.regengedanken.de/wiki/EYE.RES](http://rewiki.regengedanken.de/wiki/EYE.RES)
[http://rewiki.regengedanken.de/wiki/AESOP/16](http://rewiki.regengedanken.de/wiki/AESOP/16)

We now have sources/manual for AESOP/32 (protected mode version of the AESOP/16 engine used in the EOB3/DH). They were released by the original author (John Miles) as public domain. They can be downloaded from the thread on Vogons.

I am the author of the DAESOP utility (at the moment DAESOP 0.60). It enables to get the informations about a RES file, extract resources, disassemble scripts. Generally, it is a quite useful utilitity for working with AESOP based games. You can download it from the thread on VOGONS.

With the help of DAESOP you can extract graphic binaries.
a) Run DAESOP /k eye.res 2 2.txt
This will extract the special AESOP table 2 which contains the list of AESOP resources and their original names.

b) Open the file 2.txt and look for a graphic - for example the line:
 
```
Backdrop       art\misc\bkgnd.bmp 
```

(it is the bitmap for the main game screen, the resource number is 190)

c) Now use DAESOP to extract the binary:
DAESOP /e eye.res "Backdrop" bkgnd.bmp

It produces bkgnd.bmp with the length of 14943 bytes...
The trouble is at the moment I do not know the format of the file (it is not common BMP file...).
It uses a palette from the resource "Fixed palette" (resource number: 335).
I found out this by disassembling of the script bytecode from EOB 3 (by DAESOP). See the thread on VOGONS.

I would welcome any information on the structure of the used BMP format (I am trying to make the EOB 3 run with a new engine I got from John Miles).

Mirek
