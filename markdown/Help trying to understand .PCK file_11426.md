## Post #1
- Username: jamie1978
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 20, 2011 11:08 pm
- Post datetime: 2014-04-16T10:36:11+00:00
- Post Title: Help trying to understand .PCK file

Hi all, 

I am currently trying to modify the music in the game WWE2K14, I have had 1 success in that the replaced audio plays for about 5 seconds and then crashs...I can only assume it's something ni the header file I am missing however my hex skills are limited lol.

Has anybody come across .pck archives before? and knows how the headers are broken down?

below is a small part of the file I am working on.

```

00000000  41 4B 50 4B 00 07 10 00 00 00 00 01 00 00 00 24  AKPK...........$
00000010  00 00 02 70 00 07 0D 54 00 00 00 04 00 00 00 02  ...p...T........
00000020  00 00 00 14 00 00 00 01 00 00 00 20 00 00 00 00  ........... ....
00000030  65 6E 67 6C 69 73 68 28 75 73 29 00 73 66 78 00  english(us).sfx.
00000040  00 00 00 1F 00 31 1E B9 00 00 08 00 00 00 00 20  .....1.¹....... 
00000050  00 00 0D C3 00 00 00 01 08 61 CF 33 00 00 08 00  ...Ã.....aÏ3....
00000060  00 00 45 B4 00 00 00 E4 00 00 00 01 0A 53 71 7D  ..E´...ä.....Sq}
00000070  00 00 08 00 00 00 27 D4 00 00 00 ED 00 00 00 00  ......'Ô...í....
00000080  0B 1F EE F6 00 00 08 00 00 00 00 20 00 00 0D 9B  ..îö....... ...›
00000090  00 00 00 01 1D 80 F0 CA 00 00 08 00 00 01 14 BD  .....€ðÊ.......½
000000A0  00 00 0D 75 00 00 00 01 34 8F E8 D7 00 00 08 00  ...u....4.è×....
000000B0  00 00 0B 4D 00 00 0D 6A 00 00 00 01 4A C0 65 38  ...M...j....JÀe8
000000C0  00 00 08 00 00 00 00 20 00 00 0D 9C 00 00 00 01  ....... ...œ....
000000D0  4B 9F 04 4B 00 00 08 00 00 02 F7 B6 00 00 0D 0B  KŸ.K......÷¶....
000000E0  00 00 00 00 4C 05 1B 14 00 00 08 00 00 00 00 20  ....L.......... 
000000F0  00 00 0D C4 00 00 00 01 5C 66 DD 75 00 00 08 00  ...Ä....\fÝu....
00000100  00 00 00 20 00 00 00 E3 00 00 00 00 65 61 6F AD  ... ...ã....eao.
00000110  00 00 08 00 00 01 24 22 00 00 0D 9D 00 00 00 01  ......$"........
00000120  66 BB E9 D7 00 00 08 00 00 00 00 20 00 00 15 10  f»é×....... ....
00000130  00 00 00 01 6A B5 5B 42 00 00 08 00 00 00 00 20  ....jµ[B....... 
00000140  00 00 0D 9A 00 00 00 01 7C 52 07 C6 00 00 08 00  ...š....|R.Æ....
00000150  00 5F 3A 67 00 00 00 F5 00 00 00 01 80 35 EF 09  ._:g...õ....€5ï.
00000160  00 00 08 00 00 00 00 20 00 00 0D C8 00 00 00 01  ....... ...È....
00000170  80 3E 3E 44 00 00 08 00 00 00 00 20 00 00 0D C9  €>>D....... ...É
00000180  00 00 00 01 80 40 7C AD 00 00 08 00 00 00 00 20  ....€@|........ 
00000190  00 00 0D CA 00 00 00 01 82 73 74 36 00 00 08 00  ...Ê....‚st6....
000001A0  00 00 25 B6 00 00 0D 6F 00 00 00 00 89 EE DD 0E  ..%¶...o....‰îÝ.
000001B0  00 00 08 00 00 00 00 20 00 00 0D 99 00 00 00 01  ....... ...™....
000001C0  90 1D E8 9E 00 00 08 00 00 01 62 F7 00 00 0C DE  ..èž......b÷...Þ
000001D0  00 00 00 01 98 89 D8 17 00 00 08 00 00 00 00 20  ....˜‰Ø........ 
000001E0  00 00 0D 98 00 00 00 01 9A 48 47 CB 00 00 08 00  ...˜....šHGË....
000001F0  00 3A 1B BA 00 00 0D CC 00 00 00 01 9D E0 C6 BF  .:.º...Ì.....àÆ¿
00000200  00 00 08 00 00 00 00 20 00 00 0D CB 00 00 00 01  ....... ...Ë....
00000210  9E E0 44 6C 00 00 08 00 00 00 00 20 00 00 0C DD  žàDl....... ...Ý
00000220  00 00 00 00 C0 38 92 D6 00 00 08 00 00 00 00 20  ....À8’Ö....... 
00000230  00 00 0D C5 00 00 00 01 C0 3A D1 3F 00 00 08 00  ...Å....À:Ñ?....
00000240  00 00 00 20 00 00 0D C6 00 00 00 01 E1 D0 A7 0C  ... ...Æ....áÐ§.
00000250  00 00 08 00 00 00 00 20 00 00 0D C2 00 00 00 01  ....... ...Â....
00000260  E8 8C D7 A5 00 00 08 00 00 00 00 20 00 00 0D 74  èŒ×¥....... ...t
00000270  00 00 00 01 F4 4F 89 70 00 00 08 00 00 00 12 84  ....ôO‰p.......„
00000280  00 00 00 F2 00 00 00 00 F6 58 4A 9D 00 00 08 00  ...ò....öXJ.....
00000290  00 00 11 AE 00 00 0D 6C 00 00 00 01 FE A7 75 BA  ...®...l....þ§uº
000002A0  00 00 08 00 00 00 00 20 00 00 0D C7 00 00 00 01  ....... ...Ç....
000002B0  00 00 5A 44 00 00 0E C1 00 00 08 00 00 00 2C 70  ..ZD...Á......,p
000002C0  00 00 15 11 00 00 00 01 00 00 0F 93 00 00 08 00  ...........“....
000002D0  00 00 26 C7 00 00 15 17 00 00 00 00 00 00 4C 33  ..&Ç..........L3
000002E0  00 00 08 00 00 0D 4F 35 00 00 15 1C 00 00 00 00  ......O5........
000002F0  00 00 BE 4A 00 00 08 00 00 00 22 FB 00 00 16 C6  ..¾J......"û...Æ
00000300  00 00 00 01 00 03 2C 6B 00 00 08 00 00 00 26 A4  ......,k......&¤
00000310  00 00 16 CB 00 00 00 01 00 03 EB 8B 00 00 08 00  ...Ë......ë‹....
00000320  00 00 5A 1B 00 00 16 D0 00 00 00 01 00 04 6D A1  ..Z....Ð......m¡
00000330  00 00 08 00 00 00 40 02 00 00 16 DC 00 00 00 01  ......@....Ü....
00000340  00 05 09 E4 00 00 08 00 00 00 6D 33 00 00 16 E5  ...ä......m3...å
00000350  00 00 00 01 00 05 9C 60 00 00 08 00 00 00 DD 19  ......œ`......Ý.
00000360  00 00 16 F3 00 00 00 01 00 08 B4 64 00 00 08 00  ...ó......´d....
00000370  00 00 2D 08 00 00 17 0F 00 00 00 01 00 09 4D D9  ..-...........MÙ
00000380  00 00 08 00 00 00 3C 12 00 00 17 15 00 00 00 01  ......<.........
00000390  00 09 C8 6C 00 00 08 00 00 00 1B 3C 00 00 17 1D  ..Èl.......<....
000003A0  00 00 00 01 00 0A FE 84 00 00 08 00 00 00 29 81  ......þ„......).
000003B0  00 00 17 21 00 00 00 01 00 0B 47 64 00 00 08 00  ...!......Gd....
000003C0  00 00 B0 60 00 00 17 27 00 00 00 01 00 0B EC BC  ..°`...'......ì¼
000003D0  00 00 08 00 00 00 2D 5D 00 00 17 3E 00 00 00 01  ......-]...>....
000003E0  00 0D 91 FB 00 00 08 00 00 00 1A 35 00 00 17 44  ..‘û.......5...D
000003F0  00 00 00 01 00 0F 19 5E 00 00 08 00 00 00 D5 7B  .......^......Õ{
00000400  00 00 17 48 00 00 00 01 00 0F 3F 62 00 00 08 00  ...H......?b....
00000410  00 00 59 E1 00 00 17 63 00 00 00 01 00 10 0D D1  ..Yá...c.......Ñ
00000420  00 00 08 00 00 00 6E 45 00 00 17 6F 00 00 00 01  ......nE...o....
00000430  00 11 7D BF 00 00 08 00 00 00 26 D9 00 00 17 7D  ..}¿......&Ù...}
00000440  00 00 00 01 00 12 FB 19 00 00 08 00 00 00 58 21  ......û.......X!
00000450  00 00 17 82 00 00 00 01 00 13 4E EE 00 00 08 00  ...‚......Nî....
00000460  00 00 1F 82 00 00 17 8E 00 00 00 01 00 13 D8 64  ...‚...Ž......Ød
00000470  00 00 08 00 00 00 B6 AC 00 00 17 92 00 00 00 01  ......¶¬...’....
00000480  00 14 29 F6 00 00 08 00 00 00 7D 2E 00 00 17 A9  ..)ö......}....©
00000490  00 00 00 01 00 17 B3 59 00 00 08 00 00 00 84 54  ......³Y......„T
000004A0  00 00 17 B9 00 00 00 01 00 18 22 96 00 00 08 00  ...¹......"–....
000004B0  00 00 95 C4 00 00 17 CA 00 00 00 01 00 19 72 8A  ..•Ä...Ê......rŠ
000004C0  00 00 08 00 00 00 22 02 00 00 17 DD 00 00 00 01  ......"....Ý....
000004D0  00 19 FE 52 00 00 08 00 00 01 AF 94 00 00 17 E2  ..þR......¯”...â
000004E0  00 00 00 00 00 1A BD BA 00 00 08 00 00 00 AF 89  ......½º......¯‰
000004F0  00 00 18 18 00 00 00 01 00 1A F6 21 00 00 08 00  ..........ö!....
00000500  00 00 2A 13 00 00 18 2E 00 00 00 01 00 1B 3E E4  ..*...........>ä

```
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-04-17T03:14:00+00:00
- Post Title: Help trying to understand .PCK file

That is an Audiokinetic Wwise .PCK archive.

They can be extracted using [Ravioli Game Tools](http://www.scampers.org/steve/sms/other/RavioliGameTools_v2.8.zip). You will also need to install this [plugin](http://www.scampers.org/steve/sms/other/RavioliGameTools_v2.8_Patch1.zip) for the application to read the archive correctly.

Make sure you have .NET Framework 4.0
## Post #3
- Username: jamie1978
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 20, 2011 11:08 pm
- Post datetime: 2014-04-17T12:48:47+00:00
- Post Title: Help trying to understand .PCK file

Thanks for the advice, I have already extracted the files however what I need to be able to do is replace the audio.

The previous game WWE13 used the same .pck archive so I thought maybe I can copy one of the files out of WWE13 and then overwrite one in the current game (2K14). This worked for about 5 seconds when the game ran and then crashed...

So really exporting is'nt an issue it's replacing audio that I seem to have issues with..

Looks like in the .pck file there are RIFX headers for each audio track with WAVE format however they are actually Vorbis files. Below this there is a CUE header which I assume is when the track starts and then 2 data headers

```
0AD11000  52 49 46 58 00 11 53 22 57 41 56 45 66 6D 74 20  RIFX..S"WAVEfmt 
0AD11010  00 00 00 42 FF FF 00 02 00 00 7D 00 00 00 29 FC  ...Bÿÿ....}...)ü
0AD11020  00 00 00 00 00 30 00 10 00 00 00 03 00 33 4A AA  .....0.......3Jª
0AD11030  00 01 56 BD 00 11 3A 78 00 59 00 56 00 00 17 D4  ..V½..:x.Y.V...Ô
0AD11040  00 00 18 8E 01 5D 00 56 00 00 33 F4 00 00 35 94  ...Ž.].V..3ô..5”
0AD11050  60 83 9B F7 08 0B 63 75 65 20 00 00 00 34 00 00  `ƒ›÷..cue ...4..
0AD11060  00 02 00 00 00 01 00 04 49 59 64 61 74 61 00 00  ........IYdata..
0AD11070  00 00 00 00 00 00 00 04 49 59 00 00 00 02 00 33  ........IY.....3
0AD11080  4A A9 64 61 74 61 00 00 00 00 00 00 00 00 00 33  J©data.........3
0AD11090  4A A9 73 6D 70 6C 00 00 00 3C 00 00 00 00 00 00  J©smpl...<......
0AD110A0  00 00 00 00 00 00 00 00 00 3C 00 00 00 00 00 00  .........<......
0AD110B0  00 00 00 00 00 00 00 00 00 01 00 00 00 00 00 00  ................
0AD110C0  00 00 00 00 00 00 00 04 49 59 00 33 4A A9 00 00  ........IY.3J©..
0AD110D0  00 00 00 00 00 00 64 61 74 61 00 11 52 4C 0A C0  ......data..RL.À
0AD110E0  04 F0 08 00 01 EE 08 00 01 EA 08 00 01 E3 0A 80  .ð...î...ê...ã.€
0AD110F0  04 12 08 00 01 F6 08 00 01 F8 08 00 01 E9 0A 00  .....ö...ø...é..
0AD11100  03 99 08 00 02 0E 08 00 01 F8 08 00 01 F2 0A 80  .™.......ø...ò.€
0AD11110  04 0F 08 00 01 E2 08 00 01 EC 08 00 01 FB 09 80  .....â...ì...û.€
0AD11120  03 C7 08 00 02 15 09 80 03 D4 08 00 02 4B 09 00  .Ç.....€.Ô...K..
0AD11130  03 59 08 00 01 E3 08 00 01 CB 08 00 01 DE 08 00  .Y...ã...Ë...Þ..
0AD11140  01 FD 08 00 02 02 08 40 03 44 09 80 03 92 0A 40  .ý.....@.D.€.’.@
0AD11150  04 1E 08 00 01 EF 09 80 03 2D 08 00 01 E5 09 00  .....ï.€.-...å..
0AD11160  03 24 08 00 01 CB 09 80 03 4C 08 40 03 2F 0B C0  .$...Ë.€.L.@./.À
0AD11170  03 7E 08 40 03 06 0A C0 03 05 08 00 03 DA 08 00  .~.@...À.....Ú..
0AD11180  02 2B 08 00 01 FF 09 00 03 55 09 00 03 30 08 00  .+...ÿ...U...0..
0AD11190  02 0E 08 00 03 D3 08 00 02 2D 0A 00 03 C3 08 00  .....Ó...-...Ã..
0AD111A0  02 12 08 00 01 EF 09 80 03 F1 09 00 04 A1 08 00  .....ï.€.ñ...¡..
0AD111B0  02 00 08 00 01 E9 08 00 01 E5 08 00 01 CA 08 00  .....é...å...Ê..
0AD111C0  01 EA 08 00 01 EC 08 00 01 EE 08 40 03 66 0B C0  .ê...ì...î.@.f.À
0AD111D0  03 C4 08 00 02 09 09 80 03 60 08 80 04 2C 08 00  .Ä.....€.`.€.,..

```
## Post #4
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-04T03:00:16+00:00
- Post Title: Help trying to understand .PCK file

Just wondering if someone can help me figure out what I'm doing wrong. That patch helped a bit, I can at least see inside the archive with Ravioli now, however they all show as 0 bytes. 



Trying to extract them gives the same results, they get created, but are 0 bytes.

I am trying this on XB360 pcks from Smackdown vs Raw 2011 and '12.
## Post #5
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-04T09:16:47+00:00
- Post Title: Help trying to understand .PCK file

I figured it out, if it helps someone out in the future, in Ravioli Extractor, I had to set the Archive Type to Wwise Sound Bank in the drop down.
