## Post #1
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2009-11-13T14:55:55+00:00
- Post Title: Level- R *.pack Archiv

Hallo Leute, leider kann ich kein gutes englisch und ich hoffe das es vieleicht einer übersetzen könnte.

Ich spiele zurzeit ein online Rennspiel names Level- R.

Leider kann ich die *.pack- Dateien nicht richtig entschlüsseln, ich denke aber das die Dateien die sich im Archiv befinden nicht komprimiert sind, sondern mit irgend einen verfahren die Bytes ausgetauscht werden.

Ich habe mal eine große und ne kleine Datei zur verfügung gestellt.

Hier die beiden Archive:

[ 103_2.pack](http://freenet-homepage.de/xennex//103_2.pack) (827 Bytes)
[ 96_41.pack](http://freenet-homepage.de/xennex//96_41.pack) (1.1 MB)

Vielecht kann mir jemand mehr erzählen wie genau dieses Archiv aufgebaut ist.

Grüße xennex
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-13T15:48:41+00:00
- Post Title: Level- R *.pack Archiv

it looks like a charset/substitution algorithm, for example in 96_41.pack seems to be located a DDS image at offset 0x40f where 0xd7 is the byte 0x00 and so on.

in the other file instead there are various 0xa4 bytes so if in reality it's a 0x00 means that it's not a fixed charset but a dynamic one.
## Post #3
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2009-11-14T19:38:48+00:00
- Post Title: Level- R *.pack Archiv

Now I once made a small file which are a couple of dds files, strictly speaking, 3 pce

but somehow I can form it does not rhyme, as each of the 3 different dds-header begins.

I guess the weights of information stuck in between the header and the first IPack001 dds file.

this applies all the time to decipher.

I have as I do not even have the slightest idea is to do it.

the smaller archive I once uploaded.

I once took a translator, so you can read me better ^. ^

[ 96_39.pack](http://freenet-homepage.de/xennex//96_36.pack) (129 KB)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-15T10:40:22+00:00
- Post Title: Level- R *.pack Archiv

also this file confirm my theory, the dds starts at offset 0x165 but I can't help more because I don't have the game
## Post #5
- Username: Jackster22
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 08, 2019 8:47 pm
- Post datetime: 2019-05-08T12:48:12+00:00
- Post Title: Level- R *.pack Archiv

We have just cracked the encrypted game files open. 

All the maps, textures, sounds and cars.

40,000 files in total, nearly 9GB. 

Uploaded a few of the files in the sample folder but over 40,000 files and nearly 9GB in total so we have ZIPed everything.
All available to view and download here [http://heatonline.tk/archive/extractedfiles/](http://heatonline.tk/archive/extractedfiles/)

We are reverse engineering the game, come join us [https://discord.gg/742wKsx](https://discord.gg/742wKsx) [http://heatonline.tk](http://heatonline.tk)
