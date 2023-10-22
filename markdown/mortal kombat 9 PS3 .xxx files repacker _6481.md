## Post #1
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-04-23T08:31:53+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

hey there everybody 

.xxx files files for mk9 ps3 can be easily extracted by a few programs,i used quickbms and later Unreal Package Extractor from gildor which gives the most files

what i want to do is swap texture files or maybe more files between CHAR files and repack them.

only thing is the .xxx files use compressed chunks.

so in order to repack them a repacker has to be written and its to be very boring job according to aluigi.

i know there are alot of mk fans out there,so if someone(that fan:P) whit coding knowledge can write one 

or atleast point me in the right direction so i can try it myself 

tia
## Post #2
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-23T11:26:24+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

Friend, Did you used programs there, I'm not getting here.
## Post #3
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-04-23T13:28:01+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

> Reply from timartinelli
>
> Friend, Did you used programs there, I'm not getting here.

i dont understand what you are trying to say or ask??
## Post #4
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-23T14:21:00+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

excuse my English, I'm from Brazil, beauty?

So I was wondering what tool you used to extract the files, the more I read more of what you said I could draw well, can anyone help Repak file?

Another thing as you're editing the textures?
## Post #5
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-04-23T14:38:41+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

> Reply from timartinelli
>
> excuse my English, I'm from Brazil, beauty?

So I was wondering what tool you used to extract the files, the more I read more of what you said I could draw well, can anyone help Repak file?

Another thing as you're editing the textures?

okay now i understand you  i think 

i used Unreal Package Extractor [http://www.gildor.org/downloads](http://www.gildor.org/downloads) to extract the .xxx and also umodel for textures ,in umodel i used the commands -ps3 -nomesh -noanim or else it will give an error atleast for the ps3 files, it will give you mostly .tga files and other stuff.

what i really want to is swap\replace texture files from one CHAR.....xxx to another CHAR......xxx and repack them.
im not trying to edit the textures(well basicly i am trying  )
## Post #6
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-05-01T11:55:27+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

okay tried to figure things out myself 

beware im totaly new to this so probably most of you can see this in a sec just looking at the file (but hey we all gotta learn right  )

every file starts with "9E 2A 83 C1" "00 2E 01 D8" then the 3rd 4 bytes are for all .xxx files are different (maybe file number or something?)then the next 16 bytes are also always the same for every file "20 20 4B 4D 00 00 00 3E 00 00 00 05 4E 6F 6E 65" 
(only 2 files that i found so far start only with "9E 2A 83 C1" followed by "00 01 00 00" are TWEAKVARS.xxx and CORE.xxx)

but "9E 2A 83 C1"(always followed by 00 01 00 00 the 2nd time and so on) is found 20 times more in example:CHAR_REPTILE_B.xxx (are those the compressed chunks aluigi was talking about?)
offset 1BD refers to total texts :15 (21)
offset 1C1 refers to the length of the text :CHAR_Reptile_B.
between them are always 16 bytes (cant figure out what they are for   if anyone knows please do tell)
then there are 4 more texts that are seperate  at offset 4A3
at the end of that begins the next "9E 2A 83 C1" at offset 524 followed by "00 01 00 00" "00 07 13 0F" "00 0E 0D 41" "00 00 37 85" well "00 0E 0D 41" is also found at offset 56 which is in the first section?
and what i also figured out is "00 00 37 85" must be a lenght of compressed data (zlib) because at offset 5AC begins with "78 9C" + "00 00 37 85" the next bytes will also begin with "78 9C" so i took that part out and made a seperate file of it and then tried to decompress\unpack it with offzip but that did not work 

snippet:

```

00000000  9E 2A 83 C1 00 2E 01 D8 00 05 31 D9 20 20 4B 4D  ž*ƒÁ...Ø..1Ù  KM
00000010  00 00 00 3E 00 00 00 05 4E 6F 6E 65 00 02 88 00  ...>....None..ˆ.
00000020  09 00 00 08 24 00 00 03 E4 00 00 0E 82 00 01 29  ....$...ä...‚..)
00000030  0D 00 00 01 52 00 01 04 15 00 04 F7 D1 00 00 00  ....R......÷Ñ...
00000040  00 C7 D8 B4 AC 4A E5 C8 E8 AD 09 0B BA 46 3C 72  .ÇØ´¬JåÈè...ºF<r
00000050  F0 00 00 0A 2D 00 00 00 8B 00 00 00 01 00 00 00  ð...-...‹.......
00000060  14 00 00 03 E4 00 0E 0D 41 00 00 05 24 00 07 13  ....ä...A...$...
00000070  97 00 0E 11 25 00 0F CF 1B 00 07 18 BB 00 0B A8  —...%..Ï....»..¨
00000080  CC 00 1D E0 40 00 0E 83 78 00 12 C1 87 00 0A C8  Ì..à@..ƒx..Á‡..È
00000090  22 00 2C 63 B8 00 0E C4 93 00 1D 89 A9 00 08 26  ".,c¸..Ä“..‰©..&
000000A0  3B 00 3B 28 4B 00 03 FC 70 00 25 AF E4 00 03 C5  ;.;(K..üp.%¯ä..Å
000000B0  BF 00 3F 24 BB 00 2B 66 BA 00 29 75 A3 00 28 59  ¿.?$».+fº.)u£.(Y
000000C0  2D 00 6A 8B 75 00 00 02 4C 00 51 CE D0 00 00 00  -.j‹u...L.QÎÐ...
000000D0  F3 00 6A 8D C1 00 11 B5 E3 00 51 CF C3 00 0F CE  ó.j.Á..µã.QÏÃ..Î
000000E0  8D 00 7C 43 A4 00 0F F7 1D 00 61 9E 50 00 02 5B  ..|C¤..÷..ažP..[
000000F0  60 00 8C 3A C1 00 09 84 7B 00 63 F9 B0 00 04 20  `.Œ:Á..„{.cù°.. 
00000100  57 00 95 BF 3C 00 0F 07 7A 00 68 1A 07 00 02 EB  W.•¿<...z.h....ë
00000110  EB 00 A4 C6 B6 00 0D 68 99 00 6B 05 F2 00 07 F8  ë.¤Æ¶..h™.k.ò..ø
00000120  92 00 B2 2F 4F 00 0F 3B BA 00 72 FE 84 00 09 A3  ’.²/O..;º.rþ„..£
00000130  C8 00 C1 6B 09 00 0B F9 9D 00 7C A2 4C 00 04 97  È.Ák...ù..|¢L..—
00000140  BF 00 CD 64 A6 00 0E B6 8B 00 81 3A 0B 00 05 EA  ¿.Íd¦..¶‹..:...ê
00000150  0F 00 DC 1B 31 00 15 57 46 00 87 24 1A 00 05 2C  ..Ü.1..WF.‡$...,
00000160  5D 00 F1 72 77 00 2A AD 2B 00 8C 50 77 00 1F 7B  ].ñrw.*.+.ŒPw..{
00000170  15 01 1C 1F A2 00 0E B4 0B 00 AB CB 8C 00 09 0F  ....¢..´..«ËŒ...
00000180  CC 01 2A D3 AD 00 0F 7A CA 00 B4 DB 58 00 0A 3D  Ì.*Ó...zÊ.´ÛX..=
00000190  89 01 3A 4E 77 00 0C 76 40 00 BF 18 E1 00 07 99  ‰.:Nw..v@.¿.á..™
000001A0  CA 00 00 00 00 8B 97 F2 AA CE 67 E5 9B 20 B9 9D  Ê....‹—òªÎgå› ¹.
000001B0  A3 90 39 50 82 00 00 02 E6 00 00 00 81 00 00 00  £.9P‚...æ.......
000001C0  15 00 00 00 0F 43 48 41 52 5F 52 65 70 74 69 6C  .....CHAR_Reptil
000001D0  65 5F 42 00 0B 12 A4 81 42 D6 8D 33 FD 53 B2 A7  e_B...¤.BÖ.3ýS²§
000001E0  27 F0 EE 79 00 00 00 13 4D 4B 39 5F 43 68 61 72  'ðîy....MK9_Char
000001F0  4D 61 74 4C 69 62 72 61 72 79 00 91 FB 1B EC 4B  MatLibrary.‘û.ìK
00000200  C1 C3 5C 89 B4 B9 B6 59 7A FF EC 00 00 00 09 46  ÁÃ\‰´¹¶Yzÿì....F
00000210  58 5F 42 6C 6F 6F 64 00 98 E8 65 B7 42 D4 15 1D  X_Blood.˜èe·BÔ..
00000220  D0 30 10 96 18 DA 7A EB 00 00 00 16 4D 4B 39 5F  Ð0.–.Úzë....MK9_
00000230  46 58 5F 43 68 61 72 4D 61 74 4C 69 62 72 61 72  FX_CharMatLibrar
00000240  79 00 E7 04 B5 38 4D 90 C2 60 8C 32 46 AF 66 6B  y.ç.µ8M.Â`Œ2F¯fk
00000250  A7 F1 00 00 00 10 45 6E 67 69 6E 65 4D 61 74 65  §ñ....EngineMate
00000260  72 69 61 6C 73 00 0F 3C AA 27 43 A5 54 C7 EA 3B  rials..<ª'C¥TÇê;
00000270  B1 A4 FE EE D0 A2 00 00 00 0A 46 58 5F 47 6C 6F  ±¤þîÐ¢....FX_Glo
00000280  62 61 6C 00 0B 35 AF 13 49 BA 60 46 85 DC 0D 9A  bal..5¯.Iº`F…Ü.š
00000290  40 E3 7F 67 00 00 00 12 4D 4B 39 5F 53 6F 63 6B  @ã.g....MK9_Sock
000002A0  65 74 4C 69 62 72 61 72 79 00 B4 89 01 2C 44 82  etLibrary.´‰.,D‚
000002B0  FF 90 F1 51 20 80 AD DB 29 E7 00 00 00 12 52 65  ÿ.ñQ €.Û)ç....Re
000002C0  70 74 69 6C 65 5F 49 4B 53 6F 63 6B 65 74 73 00  ptile_IKSockets.
000002D0  A2 4B FD 40 4D 1F 39 72 FD E8 B7 98 45 DA 35 34  ¢Ký@M.9rýè·˜EÚ54
000002E0  00 00 00 0F 53 4E 44 5F 56 4F 5F 52 65 70 74 69  ....SND_VO_Repti
000002F0  6C 65 00 9E 0D 1E 61 40 25 C3 BF AF DD 23 A1 D4  le.ž..a@%Ã¿¯Ý#¡Ô
00000300  1D D6 C8 00 00 00 15 4D 4B 39 5F 46 58 5F 45 6E  .ÖÈ....MK9_FX_En
00000310  76 4D 61 74 4C 69 62 72 61 72 79 00 46 52 FF 81  vMatLibrary.FRÿ.
00000320  42 D6 09 E4 C7 4D DF 93 96 87 FF D5 00 00 00 0B  BÖ.äÇMß“–‡ÿÕ....
00000330  46 58 5F 52 65 70 74 69 6C 65 00 AF 9B E4 CE 4D  FX_Reptile.¯›äÎM
00000340  5C 57 83 1D E2 01 8B 2F 59 D7 27 00 00 00 0D 46  \Wƒ.â.‹/Y×'....F
00000350  58 5F 43 68 61 72 61 63 74 65 72 00 8C 9F 8B 58  X_Character.ŒŸ‹X
00000360  47 FE F6 1A E0 B4 98 B5 78 7D 6A 83 00 00 00 08  Gþö.à´˜µx}jƒ....
00000370  46 58 5F 46 69 72 65 00 1B 04 98 E4 44 76 96 F4  FX_Fire...˜äDv–ô
00000380  53 EA F0 9E 3E 1E CE D2 00 00 00 11 4E 50 43 5F  Sêðž>.ÎÒ....NPC_
00000390  4D 65 61 74 5F 52 65 70 74 69 6C 65 00 2D 62 31  Meat_Reptile.-b1
000003A0  4B 47 A9 07 09 3C 37 90 B4 30 C1 72 C5 00 00 00  KG©..<7.´0ÁrÅ...
000003B0  0D 46 58 5F 52 65 70 74 69 6C 65 5F 42 00 3D 4A  .FX_Reptile_B.=J
000003C0  DF 5E 45 04 81 DD 38 23 F4 88 97 7D FB 4D 00 00  ß^E..Ý8#ôˆ—}ûM..
000003D0  00 0D 43 48 41 52 5F 52 65 70 74 69 6C 65 00 7D  ..CHAR_Reptile.}
000003E0  F4 EE 1F 4D 6F 65 9E AC B6 64 A6 5F 4F 14 7D 00  ôî.Moež¬¶d¦_O.}.
000003F0  00 00 11 4E 50 43 5F 58 52 61 79 5F 52 65 70 74  ...NPC_XRay_Rept
00000400  69 6C 65 00 BA 9A 8F A7 4F 4C 51 16 A6 58 FF BC  ile.ºš.§OLQ.¦Xÿ¼
00000410  A6 B8 34 4A 00 00 00 10 53 4E 44 5F 53 46 58 5F  ¦¸4J....SND_SFX_
00000420  52 65 70 74 69 6C 65 00 8F 66 4B CF 4A 92 31 1E  Reptile..fKÏJ’1.
00000430  20 C1 2E 82 7C CB DA E2 00 00 00 12 73 6E 64 5F   Á.‚|ËÚâ....snd_
00000440  66 6F 6C 65 79 5F 6C 65 61 74 68 65 72 00 6B EC  foley_leather.kì
00000450  91 B4 40 CE 31 40 41 19 69 97 1C 32 7B 86 00 00  ‘´@Î1@A.i—.2{†..
00000460  00 10 73 6E 64 5F 66 6F 6C 65 79 5F 63 6C 6F 74  ..snd_foley_clot
00000470  68 00 F7 43 D0 98 4D 69 8C C0 6B B6 5E 88 EE AF  h.÷CÐ˜MiŒÀk¶^ˆî¯
00000480  26 5A 00 00 00 0D 52 65 70 74 69 6C 65 5F 58 52  &Z....Reptile_XR
00000490  41 59 00 8D 96 AC C0 40 38 20 37 D4 B3 02 B0 8C  AY..–¬À@8 7Ô³.°Œ
000004A0  5D F2 5A 00 00 00 04 00 00 00 07 45 6E 67 69 6E  ]òZ........Engin
000004B0  65 00 85 BE 16 82 BF E2 59 4F A3 B4 A8 1A E3 87  e.…¾.‚¿âYO£´¨.ã‡
000004C0  45 16 00 00 00 05 43 6F 72 65 00 5D A8 B3 33 F6  E.....Core.]¨³3ö
000004D0  3A 0A 8C 51 35 06 A0 EA 65 27 FE 00 00 00 18 43  :.ŒQ5. êe'þ....C
000004E0  48 41 52 5F 52 65 70 74 69 6C 65 5F 42 2D 39 31  HAR_Reptile_B-91
000004F0  36 61 34 61 30 30 00 19 A5 E7 13 7A F9 39 F7 54  6a4a00..¥ç.zù9÷T
00000500  3C 4C 85 69 DB 60 31 00 00 00 09 4D 77 79 44 65  <L…iÛ`1....MwyDe
00000510  63 61 6C 00 CA 1B 0C 4B 1D 90 1B CB 6F 33 45 DF  cal.Ê..K...Ëo3Eß
00000520  F6 03 1F AC 9E 2A 83 C1 00 01 00 00 00 07 13 0F  ö..¬ž*ƒÁ........
00000530  00 0E 0D 41 00 00 37 85 00 01 00 00 00 00 24 C9  ...A..7…......$É
00000540  00 01 00 00 00 00 21 D3 00 01 00 00 00 00 27 8B  ......!Ó......'‹
00000550  00 01 00 00 00 00 28 2F 00 01 00 00 00 00 AF AA  ......(/......¯ª
00000560  00 01 00 00 00 00 B4 45 00 01 00 00 00 00 BC 09  ......´E......¼.
00000570  00 01 00 00 00 00 CA BC 00 01 00 00 00 00 D8 CC  ......Ê¼......ØÌ
00000580  00 01 00 00 00 00 C2 77 00 01 00 00 00 00 C4 28  ......Âw......Ä(
00000590  00 01 00 00 00 00 B9 EA 00 01 00 00 00 00 3B 8C  ......¹ê......;Œ
000005A0  00 01 00 00 00 00 05 9F 00 00 0D 41 78 9C B5 7D  .......Ÿ...Axœµ}
000005B0  0B 77 DB C8 B1 A6 4F 62 EB FD A0 5E B6 2C 7B 6C  .wÛÈ±¦Obëý ^¶,{l
000005C0  67 66 6E 92 4D 72 EF B5 28 CD 6B 37 7B 6F A8 07  gfn’Mrïµ(Ík7{o¨.

```

 what im trying to do here is figuring out how the files are put together 
so that a repacker can be written sinds noone else replied to this topic i might as well try it myself,only thing is i cant write code,so any help is much apriciated

edit : [http://www.gildor.org/smf/index.php/topic,882.0.html](http://www.gildor.org/smf/index.php/topic,882.0.html) found this on gildor
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-05-16T14:49:35+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

If you can figure out the format of the files, I can write an app to extract and repack it. You just need to be very specific how the files are structured. 

It would be really cool to mod this game though.
## Post #8
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-06-03T17:22:40+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

> Reply from plodtrew
>
> If you can figure out the format of the files, I can write an app to extract and repack it. You just need to be very specific how the files are structured. 

It would be really cool to mod this game though.

well i found out that you can play the char_.....XXX decompressed with decompress from gildor.credits to gildor   

so i did some texture swapping between files    manually with a hexeditor.

you also have to change the ps3toc for the size of the file.

anyways here something i already i did 

[http://www.megaupload.com/?d=7TCVW6YU](http://www.megaupload.com/?d=7TCVW6YU)

edit : maybe someone can write a script for the decompressed .XXX files for quickbms and we can implement the reimporter?
as the decompressed files no longer use compressed chunks
## Post #9
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-06-07T19:15:35+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

some vids of the the texture mods
[http://www.youtube.com/watch?v=ufrdeY_02Hg](http://www.youtube.com/watch?v=ufrdeY_02Hg)
[http://www.youtube.com/watch?v=FDPMUV3i7MI](http://www.youtube.com/watch?v=FDPMUV3i7MI)
[http://www.youtube.com/watch?v=9D-cnbIn7rA](http://www.youtube.com/watch?v=9D-cnbIn7rA)
## Post #10
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-07-02T10:00:45+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

What is the structure of these files, headers, graphics formats, etc. I can add support in my xpacker app if someone can illustrate this to me.
## Post #11
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-07-07T16:33:39+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

how did you manage to edit / replace the textures?

i only have the 360 version and there the tga files are headerless... any help? :/
## Post #12
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-07-14T07:43:21+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

@darksoul, how are you editing the texture2d files? Or are you editing and injecting tga files?
## Post #13
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-07-21T23:45:12+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

i have tested darksouls method (decompress, extract, replace, modify toc) successfully with the 360 version.

i have then tried to modify an original texture (converted to tga by umodel).

imported it into UDK (udk.com) and created a new package with a texture in it -> texture2d

saved said package and extracted it again for the new texture 2d file, which unfortunately was bigger than the original texture2d 

i tried to replaced it anyway, leaving out the bytes over size which resulted in a fatal crash xD

anyone else had any luck with modifying textures in an unreal based game and injecting them back into a package?
## Post #14
- Username: peoman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 23, 2011 10:18 am
- Post datetime: 2011-12-25T17:48:49+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

I'm a new guy here.

I'm trying to create a DLC for Goro, Kintaro and Shao Kahn on MK9 for Xbox 360 like lllsondowlll did with Goro.
I'm using "Le Fluffie App" to extract and create a DLC.
I'm using "decompress" and "extract" from gildor to extract an XXX file.
But i need a way to build / rebuild the XXX file with my files.
I've gathered all the files i need (some taken from the game itself and some from the mk9-boss_unlock for PS3)
ex for Goro:

> CHAR_Goro.xxx
>
> Goro__MK9Game.eng
>
> goro__Xe-MK9Game.ini
>
> Goro_CharIntro.xxx
>
> Goro_Fatality1.xxx
>
> Goro_Fatality2.xxx
>
> Goro_Victory.xxx
>
> NPC_Goro_Baby.xxx
>
> Goro_ui.xxx
>
> Goro_ui_n.xxx
I need to create the Goro_ui.xxx and Goro_ui_n.xxx with the files:

> BD_goro.TextureJPEG
>
> BD_goro_alpha.BinaryBlobJPEG
>
> BD_goro_color.BinaryBlobJPEG
>
> BD_Skarlet.ObjectRedirector
>
> CombinedReferencer.ObjectReferencer
>
> Head.Texture2D
>
> ladder_a.Texture2D
>
> ladder_b.Texture2D

I've tried replacing with hex editing, X-PacKer, even Skorpion2k7 rebuilder for PS3 with no success.
Is there a way to create a new XXX file?
Maybe add this function to X-PacKer...

Thanks in advance
## Post #15
- Username: vampire78
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 14, 2011 4:06 pm
- Post datetime: 2012-01-12T02:38:24+00:00
- Post Title: mortal kombat 9 PS3 .xxx files repacker ?

Hi peoman I was trying to do the same thing someone can help us?
the ui files gives error and shutdown the xbox...
