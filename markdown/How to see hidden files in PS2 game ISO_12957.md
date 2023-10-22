## Post #1
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-06-18T03:10:19+00:00
- Post Title: How to see hidden files in PS2 game ISO?

Sly Cooper and the Thievius Raccoonus has the game data hidden in the ISO file; Square Enix did this same thing with some Final Fantasy game. Is there any method of finding these hidden files so they show up and can be extracted? All 3 Sly games have this. It is probably impossible to get them to show up, but it's worth a shot. It appears as though the file will hide itself the moment the ISO gets opened. Any suggestions?
## Post #2
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2015-06-21T22:28:20+00:00
- Post Title: How to see hidden files in PS2 game ISO?

> Reply from frogz2007
>
> Is there any method of finding these hidden files so they show up and can be extracted?Yes, try this tools:

Sky`s Console File Scanner

 SkysConsoleFileScanner.zip
(154.9 KiB) Downloaded 151 times

this will give you PSS videos, their total size is 2,19 GB
```
0008a3f800|0003084004|1.PSS
000bac4000|000d754004|2.PSS
0019218800|000180c004|3.PSS
001aa3d000|0002850004|4.PSS
001e9d4800|0005644004|5.PSS
00244cf000|00024b8004|6.PSS
0026e81800|000180c004|7.PSS
00289fb000|000595c004|8.PSS
002e546000|00024b8004|9.PSS
0030bf8000|0002608004|10.PSS
0033df8800|0003084004|11.PSS
00376d8000|0005530004|12.PSS
003ccef800|0004724004|13.PSS
00417d1000|0004724004|14.PSS
004615f000|00023f8004|15.PSS
00486aa800|0015150004|16.PSS
0064781800|0000ab4004|17.PSS
006adbe800|0001c7c004|18.PSS
006cf76000|00023f8004|19.PSS
006f36e800|0005644004|20.PSS
0074c79800|0003b3c004|21.PSS
00787b6000|0002c8c004|22.PSS
007b50a000|0000ab4004|23.PSS
007c4fe000|0002c8c004|24.PSS
0080649000|0002850004|25.PSS
00833c7000|0015150004|26.PSS
0099728800|0003b3c004|27.PSS
009ea14800|00054d0004|28.PSS
00a42b4000|0001c7c004|29.PSS

```


also: Cube Media Player 2
my playlist file is only for SCUS-97198
[https://www.mediafire.com/?u8e5rat7caz56ve](https://www.mediafire.com/?u8e5rat7caz56ve)
open this file in HxD and replace all bytes from "E:\Архивы\DVD.iso" to your hdd ID and ISO path (yes, this is Cyrillic characters)

CMP will find PSS/SS2 files too, but most important is ADPCM files, that CMP can find and extract.

[](http://imgur.com/1mYvM5Q)

If you need textures, then follow this tutorial:
[http://www.swordofmoonlight.com/bbs/ind ... opic=712.0](http://www.swordofmoonlight.com/bbs/index.php?topic=712.0)

examples:
[](http://imgur.com/SNl1vhl)



if you need files, that not text data or media files, try to find them manually with HEX from the ISO file. Most of them not encrypted.
## Post #3
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-06-22T01:20:35+00:00
- Post Title: How to see hidden files in PS2 game ISO?

Awesome! Thanks so much.
