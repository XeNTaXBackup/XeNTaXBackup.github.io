## Post #1
- Username: BuC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 18, 2010 4:35 am
- Post datetime: 2010-12-26T21:05:09+00:00
- Post Title: quickbms zlib help

Hello everybody this is my first post.
I would like to say the forum is great and full of very smart people.
I have a file that has multiple zlib files within.
Can someone show me an example of a quickbms script that will search for all .Csc then decompress all of the compressed files naming them the file name?
And maybe a script to compress and inject the files back in.
Is this possible with quickbms?

Offsets BF070-BF079 file name
Offsets BF07D-BF07E decompressed size
Offsets BF081-BF082 compressed size
Offset BF083 is zlib start

```

000BF050                                   FF FF FF FF 63             ÿÿÿÿc
000BF060  6C 69 65 6E 74 73 63 72 69 70 74 73 2F 6D 70 2F  lientscripts/mp/
000BF070  5F 61 75 64 69 6F 2E 63 73 63 00 00 00 29 8C 00  _audio.csc...)Œ.
000BF080  00 0A 93 78 9C C5 5A 6D 8F DB B8 11 EE D7 F3 AF  ..“xœÅZm.Û¸.î×ó¯
000BF090  60 54 F4 62 AF B5 3E DB BD A0 45 1C 07 08 EE 92  `Tôb¯µ>Û½ E...î’
000BF0A0  36 C0 35 0D 6E EF 43 81 5C 20 70 2D DA AB AE 2C  6À5.nïC.\ p-Ú«®,
000BF0B0  39 12 BD 6B 6F 2F FF BD 33 43 52 24 F5 66 E7 B2  9.½ko/ÿ½3CR$õfç²
000BF0C0  68 6F 0F B1 44 0E 1F 0E 1F 0E 67 86 A4 06 7F 4C  ho.±D.....g†¤..L
000BF0D0  B2 55 BA 8F 05 5B A5 89 C8 64 B9 2A 92 9D 2C 7F  ²Uº..[¥‰Èd¹*’.,.
000BF0E0  DD EE 7E 8D F6 32 49 13 79 5C 0C 7A 64 F8 F6 1A  Ýî~.ö2I.y\.zdøö.
000BF0F0  8B 76 7C 75 CB 37 62 31 E0 FB 38 C9 A3 24 4B E4  ‹v|uË7b1àû8É£$Kä
000BF100  90 A5 F9 8A A7 3F 50 93 77 FB 2D 1B 0D FE 33 48  .¥ùŠ§?P“wû-..þ3H
000BF110  C5 9D 48 27 69 0E 60 99 D8 26 A2 64 4B B6 E6 69  Å.H'i.`™Ø&¢dK¶æi
000BF120  09 2D EF 79 22 D7 79 A1 BA 18 B2 29 1B 2D 06 C9  .-ïy"×y¡º.²).-.É
000BF130  BA 81 B2 5C 62 15 40 95 59 1C 95 19 DF 95 37 B9  º.²\b.@•Y.•.ß•7¹
000BF140  54 1D 42 83 52 F2 42 5E E5 FB 2C FE 99 67 71 BE  T.BƒRòB^åû,þ™gq¾
000BF150  2D 9B 5A B8 42 3F E5 F9 AE AC DA FD 94 64 E2 F5  -›Z¸B?åù®¬Úý”dâõ
000BF160  36 91 52 14 54 28 6F 0A C1 63 86 1D 65 49 F6 6F  6‘R.T(o.Ác†.eIöo
000BF170  1E ED 8A 3C 5A DD 88 D5 AD 28 9C FA EB FD 76 17  .íŠ<ZÝˆÕ.(œúëýv.
000BF180  C9 22 D9 6C 44 11 11 90 53 89 8A 45 8A 94 52 8A  É"ÙlD...S‰ŠEŠ”RŠ
000BF190  4A AE 8E 0F 08 02 7E 0A 54 AA 56 B5 4E 32 9E 46  J®Ž...~.TªVµN2žF
000BF1A0  B7 49 9A AE F8 16 EB 3E C3 5F CB E0 2B 76 A1 22  ·Iš®ø.ë>Ã_Ëà+v¡"
000BF1B0  7E B5 92 C9 9D B8 D2 12 40 72 10 8B 35 DF A7 32  ~µ’É.¸Ò.@r.‹5ß§2
000BF1C0  58 38 52 EF C4 41 B6 CB 94 42 6E 40 99 9D E9 03  X8RïÄA¶Ë”Bn@™.é.
000BF1D0  68 EC C2 F6 B5 AD 94 92 37 49 76 AB D4 A5 72 21  hìÂöµ.”’7Iv«Ô¥r!
000BF1E0  AB BA 21 90 24 85 AF 70 4D 15 92 58 0C 76 45 92  «º!.$…¯pM.’X.vE’
000BF1F0  C9 34 1B B2 00 44 98 69 CF 62 71 BD DF 3C 67 80  É4.².D˜iÏbq½ß<g€
000BF200  A9 04 D9 D3 60 4C 0F E3 E0 69 80 0A 11 2E CB 72  ©.ÙÓ`L.ãài€...Ër
000BF210  99 AC 8F D0 38 13 F7 D1 F5 BE A4 AA 1A 77 5A 4D  ™¬.Ð8.÷Ñõ¾¤ª.wZM
000BF220  D0 05 6C 6F B8 58 E0 13 59 5D 27 95 4B D6 A1 75  Ð.lo¸Xà.Y]'•KÖ¡u
000BF230  35 20 86 A6 0C 6B 27 6D 74 FD 15 C8 AB 3C 93 49  5 †¦.k'mtý.È«<“I
000BF240  B6 17 08 C3 CB 52 80 95 B1 B7 E5 8F 02 CC 43 C4  ¶..ÃËR€•±·å..ÌCÄ
000BF250  C3 CE 96 D8 6F AF 78 7D 36 69 81 F4 CC BE 0F BF  ÃÎ–Øo¯x}6i.ôÌ¾.¿
000BF260  E8 B3 B9 F6 46 D6 80 7D A3 6F 63 0F A5 48 24 8B  è³¹öFÖ€}£oc.¥H$‹
000BF270  89 41 C7 1E 04 C8 64 1B 46 8D 99 70 AC 83 04 1B  ‰AÇ..Èd.F.™p¬ƒ..
000BF280  26 17 40 67 24 8B 78 8E 21 40 71 65 0B 85 80 26  &.@g$‹xŽ!@qe.…€&
000BF290  A4 08 D4 59 1F 12 FD 42 E6 5D F7 24 21 2B A0 9A  ¤.ÔY..ýBæ]÷$!+ š
000BF2A0  DC 08 33 56 F3 C4 A1 B8 AA 9D 28 7F 19 E1 B8 A2  Ü.3VóÄ¡¸ª.(..á¸¢
000BF2B0  6D 92 21 C7 20 DF 5D BF 64 33 63 2C 67 00 F2 43  m’!Ç ß]¿d3c,g.òC
000BF2C0  3F 20 D4 2F D9 9F 11 F0 FE 26 49 C5 90 CD 48 1A  ? Ô/ÙŸ.ðþ&IÅ.ÍH.
000BF2D0  2B 87 4C 8D F0 4D 9A 73 09 8F 1B D1 A3 76 D8 AF  +‡L.ðMšs...Ñ£vØ¯
000BF2E0  C0 E2 B4 BE A5 E2 8A BA B7 33 A9 23 08 53 B5 5C  Àâ´¾¥âŠº·3©#.Sµ\
000BF2F0  B2 60 6C 5B E6 E0 2E 93 6C 1C B0 1B 5E 32 28 50  ²`l[æà.“l.°.^2(P
000BF300  D8 CC 05 D4 93 29 20 88 20 6E CA 8F 54 DC 33 5D  ØÌ.Ô“) ˆ nÊ.TÜ3]
000BF310  9E 3E 6E B9 EA 8D 69 1F FB F9 9C 68 A2 79 87 3A  ž>n¹ê.i.ûùœh¢y‡:
000BF320  60 F9 6F 42 5E C9 62 BF 92 AF 8A 82 A3 E3 51 55  `ùoB^Éb¿’¯Š‚£ãQU
000BF330  41 08 F6 AA BA 4C F9 B5 48 03 C3 56 8D 2C 04 19  A.öªºLùµH.ÃV.,..
000BF340  B1 6F BF 35 2F 93 32 79 10 EC A5 8E 77 96 B1 8B  ±o¿5/“2y.ì¥Žw–±‹
000BF350  8B 0B A6 54 60 CF D9 5B 70 FE 09 4F 93 92 56 03  ‹.¦T`ÏÙ[pþ.O“’V.
000BF360  35 54 54 96 EC 92 05 6C EC 83 8D A1 48 E8 10 37  5TT–ì’.lìƒ.¡Hè.7
000BF370  21 3D D0 ED B1 04 94 9F 2E E0 E7 85 27 0E 25 E3  !=Ðí±.”Ÿ.àç…'.%ã
000BF380  31 75 6E 3C FC 99 AB 02 00 3E 24 1F 0D 91 66 6A  1un<ü™«..>$..‘fj
000BF390  DA 07 F0 2E F7 D5 9E 04 A6 5D 69 42 F4 2F 95 93  Ú.ð.÷Õž.¦]iBô/•“
000BF3A0  AE DB 58 29 D2 75 9B 79 15 42 EE 8B AC 6D 15 51  ®ÛX)Òu›y.Bî‹¬m.Q
000BF3B0  0B 33 D1 35 59 15 30 DE F1 AD C0 68 18 B4 7A 4E  .3Ñ5Y.0Þñ.Àh.´zN
000BF3C0  47 66 D4 32 8F 9E 42 10 EC 61 52 54 2F 1E 76 53  GfÔ2.žB.ìaRT/.vS
000BF3D0  AA C3 AD D7 7B 23 8B 84 05 B0 64 60 67 A2 B7 77  ªÃ.×{#‹„.°d`g¢·w
000BF3E0  20 5B 77 6D 1B D5 EB 9F E0 B4 6B 92 8C 14 B5 40   [wm.ÕëŸà´k’Œ.µ@
000BF3F0  2A 53 60 5E DB 4A 0B D1 A1 CF A4 41 71 14 7E 82  *S`^ÛJ.Ñ¡Ï¤Aq.~‚
000BF400  1C D6 4C 97 3A 41 52 10 5C 0B 57 66 A8 A2 6F 3D  .ÖL—:AR.\.Wf¨¢o=
000BF410  08 B8 14 2C DA 35 2D 65 BE FB 62 6D B5 55 FE BE  .¸.,Ú5-e¾ûbmµUþ¾
000BF420  A1 5A 4A 9F E8 47 CF D4 AD F5 C2 BC 78 D6 DB 30  ¡ZJŸèGÏÔ.õÂ¼xÖÛ0
000BF430  45 68 BD 11 B2 6E 89 AA 14 E0 E1 DF 92 5C 8A 27  Eh½.²n‰ª.àáß’\Š'
000BF440  0E 0E 45 3D 64 40 4B D0 E6 7C DB 61 1B 06 FE 88  ..E=d@KÐæ|Ûa..þˆ
000BF450  D6 FB BF 34 4D 27 53 3F 35 5F A1 A6 E2 CB 2C 35  Öû¿4M'S?5_¡¦âË,5
000BF460  60 D6 52 A1 AF 47 B3 D4 2B B0 D4 AF 55 DE 35 DC  `ÖR¡¯G³Ô+°Ô¯UÞ5Ü
000BF470  AF C5 3A 61 C7 76 E1 12 0B 71 2E CA EC A9 04 A0  ¯Å:aÇvá..q.Êì©. 
000BF480  5B 4D 09 EC E0 AC BB AE 6F AB 90 22 5C 58 45 6B  [M.ìà¬»®o«."\XEk
000BF490  6C 54 55 E7 C4 46 03 42 B1 51 BF F8 B1 31 16 10  lTUçÄF.B±Q¿ø±1..
000BF4A0  F6 29 86 35 E2 99 2B 6F E3 99 2E C5 20 E5 86 36  ö)†5â™+oã™.Å å†6
000BF4B0  27 D8 2C 34 E8 98 B2 31 D4 48 BD FF 89 CD A7 76  'Ø,4è˜²1ÔH½ÿ‰Í§v
000BF4C0  13 AA B2 A8 E9 64 3A B3 59 83 EB 03 9A DB 4A EC  .ª²¨éd:³Yƒë.šÛJì
000BF4D0  DC 29 68 65 06 EA 23 ED 8E CE E2 C7 C5 53 24 39  Ü)he.ê#íŽÎâÇÅS$9
000BF4E0  25 E7 33 55 6F E4 D0 E5 54 35 38 B3 2E EE 51 38  %ç3UoäÐåT58³.îQ8
000BF4F0  EB DE 31 EB B6 F5 43 02 14 D0 3C BE CE 0C 89 53  ëÞ1ë¶õC..Ð<¾Î.‰S
000BF500  E0 AD 09 12 84 75 BF C9 51 3C 92 3A 97 21 A8 90  à...„u¿ÉQ<’:—!¨.
000BF510  3D 7F DE 6C AA 74 6D 96 AB 46 CC DF 41 E2 B2 73  =.Þlªtm–«FÌßAâ²s
000BF520  F7 31 55 F7 24 FC 1E 38 51 80 24 A7 C9 34 27 08  ÷1U÷$ü.8Q€$§É4'.
000BF530  AE 2E 4A 12 15 C2 37 D8 BA C0 04 B4 70 53 09 A4  ®.J..Â7ØºÀ.´pS.¤
000BF540  82 DF 89 16 01 43 74 2F CA D0 53 4E 27 5B 4E D1  ‚ß‰..Ct/ÊÐSN'[NÑ
000BF550  DF 79 F9 5E 14 B7 18 C5 77 62 05 39 A7 3C 46 9F  ßyù^.·.Åwb.9§<FŸ
000BF560  F6 89 40 2B 65 A3 FE AC CB C2 4C B6 F9 9D D8 82  ö‰@+e£þ¬ËÂL¶ù.Ø‚
000BF570  0E F2 B8 13 3A 0A 74 D5 82 5B CE F6 69 1A 18 C4  .ò¸.:.tÕ‚[Îöi..Ä
000BF580  B7 65 DC 16 4E 68 61 34 90 68 68 2A 27 5C 36 C5  ·eÜ.Nha4.hh*'\6Å
000BF590  4F 40 9A 5C 12 D6 52 B7 F2 60 D1 40 05 BA 48 3D  O@š\.ÖR·ò`Ñ@.ºH=
000BF5A0  FE BB 3C DD 53 84 04 0B 8B E0 25 5A 17 90 28 03  þ»<ÝS„..‹à%Z..(.
000BF5B0  5B E0 61 87 16 45 DB AC A6 D5 D9 B1 4C C3 93 3E  [àa‡.EÛ¬¦ÕÙ±LÃ“>
000BF5C0  5C 77 E1 CE 67 D7 A4 BB 3D D2 6C B2 AF 9A CE 0E  \wáÎg×¤»=Òl²¯šÎ.
000BF5D0  A6 20 0C 88 FB BC 90 37 C7 FF 37 5D 56 93 1E CE  ¦ .ˆû¼.7Çÿ7]V“.Î
000BF5E0  BA 0C C4 1A 5A DB 71 1E 28 5B 15 F7 B8 1A B7 69  º.Ä.ZÛq.([.÷¸.·i
000BF5F0  D0 CC D1 EA 0E D7 42 5A 77 EB 77 E5 F8 5A F5 E3  ÐÌÑê.×BZwëwåøZõã
000BF600  75 61 0E 03 5B AB 8C 17 6A 3B A4 84 DD A2 14 99  ua..[«Œ.j;¤„Ý¢.™
000BF610  02 E8 DB 51 71 3C D1 E1 94 C0 30 03 D8 AC D3 C7  .èÛQq<Ñá”À0.Ø¬ÓÇ
000BF620  15 1D DE 8F 3D B6 FB C3 91 D4 1C 1E 16 B5 B8 38  ..Þ.=¶ûÃ‘Ô...µ¸8
000BF630  2C 1E 32 DC 65 56 F6 8F 2F 5F 62 F8 3D 26 AA 91  ,.2ÜeVö./_bø=&ª‘
000BF640  FB 73 68 C7 8D B4 92 37 32 7E B6 03 A0 B9 BA DC  ûshÇ.´’72~¶. ¹ºÜ
000BF650  5A E4 18 22 BB B1 6F E5 01 45 09 09 34 CE 0A AA  Zä."»±oå.E..4Î.ª
000BF660  77 D6 6A E9 5C 2C 7D B6 41 7D 8F D8 6F BF B5 E9  wÖjé\,}¶A}.Øo¿µé
000BF670  F4 62 F9 FB 94 3A ED F1 3C 9F E7 4F 70 6D E9 5A  ôbùû”:íñ<ŸçOpméZ
000BF680  23 EF A7 98 C2 81 D6 B3 9E D1 B7 C8 2D 3A 57 C1  #ï§˜Â.Ö³žÑ·È-:WÁ
000BF690  54 A7 C1 2B 9E 0A 63 22 87 59 C8 0E F3 90 1D E1  T§Á+ž.c"‡YÈ.ó..á
000BF6A0  F7 08 BF 0F D6 14 1F C0 03 1C 66 A3 C1 03 34 3D  ÷.¿.Ö..À..f£Á.4=
000BF6B0  50 BA 44 85 2F 41 5E 17 CE 21 9F 3A D0 03 BB 24  PºD…/A^.Î!Ÿ:Ð.»$
000BF6C0  11 3C 1A 44 19 7C 1B B1 EF 58 7C 00 09 CC E6 8E  .<.D.|.±ïX|..ÌæŽ
000BF6D0  28 71 04 89 7B 94 C8 2E A0 70 0C EF A0 AC 32 65  (q.‰{”È. p.ï ¬2e
000BF6E0  76 8F BA B5 D9 F0 CE 86 FB 6D 92 69 E7 BB 64 73  v.ºµÙðÎ†ûm’iç»ds
000BF6F0  C0 DA F2 83 7D FF EB 33 55 00 ED D5 82 47 69 F5  ÀÚòƒ}ÿë3U.íÕ‚Giõ
000BF700  32 81 37 23 A7 E1 70 D7 4A F8 66 1F A4 AA AB AB  2.7#§áp×Jøf.¤ª««
000BF710  1B 2D 3D FB CB 33 4A AA AE CB AA 23 78 86 F9 96  .-=ûË3Jª®Ëª#x†ù–
000BF720  22 BA E3 E9 5E 80 BB C4 34 4F 55 D2 01 48 B5 20  "ºãé^€»Ä4OUÒ.Hµ 
000BF730  3D 9A 2B D5 43 56 69 1D 32 AD A2 2A A3 07 DB 93  =š+ÕCVi.2.¢*£.Û“
000BF740  A5 46 21 6A 3D BC BE D7 F9 BD 3D DA A5 97 17 34  ¥F!j=¼¾×ù½=Ú¥—.4
000BF750  00 DD 70 88 45 17 97 C8 32 A5 AF BA 18 4B 11 6D  .ÝpˆE.—È2¥¯º.K.m
000BF760  95 E6 25 9A FD 2E 87 31 44 79 16 51 5A 2F 73 55  •æ%šý.‡1Dy.QZ/sU
000BF770  30 64 EF F1 27 64 98 3E 5F 61 94 51 8F AF F5 69  0dïñ'd˜>_a”Q.¯õi
000BF780  32 B9 46 91 C5 39 F4 13 E0 F1 36 6D C0 D4 81 27  2¹F‘Å9ô.àñ6mÀÔ.'
000BF790  74 88 A2 FF E0 9B AB 4F 45 4C 07 ED D9 46 DE 94  tˆ¢ÿà›«OEL.íÙFÞ”
000BF7A0  9F F6 BC 00 36 0C CC A5 C5 C6 10 CA 96 DF 0C 19  Ÿö¼.6.Ì¥ÅÆ.Ê–ß..
000BF7B0  FE 51 C7 1F A6 1F 5D 01 7C 1D B1 0B A8 D5 AD 5B  þQÇ.¦.].|.±.¨Õ.[
000BF7C0  EB 47 6C 3C B0 08 33 5F 62 56 47 68 AB F7 11 E6  ëGl<°.3_bVGh«÷.æ
000BF7D0  BE C4 BC 8E D0 56 8F 7F DF 0D 94 8C 61 40 5B 99  ¾Ä¼ŽÐV..ß.”Œa@[™
000BF7E0  C4 F9 99 4C 6D A8 D2 3B DD A5 C5 30 FB 67 A6 E4  Äù™Lm¨Ò;Ý¥Å0ûg¦ä
000BF7F0  5F B2 59 A7 3C 28 E0 EE B6 B1 75 74 70 B1 90 93  _²Y§<(àî¶±utp±.“
000BF800  31 80 9C 60 4D 1F DA 45 47 AF ED AC D9 B6 85 2F  1€œ`M.ÚEG¯í¬Ù¶…/
000BF810  D3 F6 C1 6B 3B 6F B6 6D 61 6A 51 1B 93 3E 8D 88  ÓöÁk;o¶majQ.“>.ˆ
000BF820  0E A1 7E 38 9A 87 87 6A 07 9F C5 11 AE 60 48 26  .¡~8š‡‡j.ŸÅ.®`H&
000BF830  C1 4E D7 07 B0 FA 43 02 0B 89 A7 09 87 6D 51 BE  ÁN×.°úC..‰§.‡mQ¾
000BF840  5E 97 42 1E CC C3 D1 3C 3C C0 43 B6 29 94 EF 06  ^—B.ÌÃÑ<<ÀC¶)”ï.
000BF850  13 E4 D5 6E C8 DB 5E D2 6D D0 0A AA A5 78 F3 2F  .äÕnÈÛ^ÒmÐ.ª¥xó/
000BF860  70 DA B5 3D A6 BD 1B 73 64 20 01 9A DC 7D 08 50  pÚµ=¦½.sd .šÜ}.P
000BF870  8D E0 23 3A 10 7C 72 6E 92 6B A2 B4 3E 20 33 43  .à#:.|rn’k¢´> 3C
000BF880  FF B0 E3 F7 D9 1B 7E 0B F4 D8 DB 64 36 4C 4C 16  ÿ°ã÷Ù.~.ôØÛd6LL.
000BF890  CB 86 A8 E9 E8 24 D4 2B 1C CF 92 86 85 24 55 74  Ë†¨éè$Ô+.Ï’†…$Ut
000BF8A0  76 A9 AA 04 82 8F 8D EE 34 7B 14 C6 F5 73 B5 2B  v©ª.‚..î4{.Æõsµ+
000BF8B0  AF 50 F5 C3 B8 12 0F A7 E1 54 C7 E2 16 B4 E3 B9  ¯PõÃ¸..§áTÇâ.´ã¹
000BF8C0  68 D3 D0 CC 59 0F DA C3 F9 68 06 EF A1 15 4D 1B  hÓÐÌY.ÚÃùh.ï¡.M.
000BF8D0  83 82 D3 2F 7A 7B C6 57 E8 BC AB 9B 1C 88 5F FE  ƒ‚Ó/z{ÆWè¼«›.ˆ_þ
000BF8E0  EB 9B C3 3F FD FE 16 55 A3 6B C8 D0 85 A4 B7 21  ë›Ã?ýþ.U£kÈÐ…¤·!
000BF8F0  33 72 61 F5 C4 2E 29 9D 80 FF 67 53 FC 8F 8D 42  3raõÄ.).€ÿgSü..B
000BF900  F5 69 41 E8 5C 1C 8D 54 87 31 E4 06 3C F3 71 08  õiAè\..T‡1ä.<óq.
000BF910  F8 43 B0 CB CB 44 26 39 CC 20 0A 57 83 6F D4 D2  øC°ËËD&9Ì .WƒoÔÒ
000BF920  E9 99 90 6B B0 30 98 FC BC D8 50 EF BD A6 14 32  é™.k°0˜ü¼ØPï½¦.2
000BF930  7B F4 86 CB 0C 0F A1 6C 1E 74 A2 A9 5E 83 93 67  {ô†Ë..¡l.t¢©^ƒ“g
000BF940  CE F5 54 6D B9 46 68 A4 91 D8 6E 93 EA A8 E9 D1  ÎõTm¹Fh¤‘Øn“ê¨éÑ
000BF950  16 A1 B7 1C 5E EA 3B 44 47 0D DC D6 A1 0A 49 6C  .¡·.^ê;DG.ÜÖ¡.Il
000BF960  9C 06 EE F9 42 27 39 A3 4B FB C8 3D DB 52 27 3A  œ.îùB'9£KûÈ=ÛR':
000BF970  EE A5 24 C2 E1 9E 51 25 82 11 4F C1 7A A8 09 89  î¥$ÂážQ%‚.OÁz¨.‰
000BF980  9A 88 8A B3 E7 5B 8D 07 42 A1 F3 54 F4 85 0C 85  šˆŠ³ç[..B¡óTô….…
000BF990  2E AE D4 49 12 4C 2B F9 08 93 8D AA 78 4C CF 18  .®ÔI.L+ù.“.ªxLÏ.
000BF9A0  7B 3B 92 7C 9C FB 48 D8 B3 6C DF 1A 48 A4 7E 39  {;’|œûHØ³lß.H¤~9
000BF9B0  E6 B5 6B B9 57 A8 0D F1 47 6D A7 57 3A B4 F7 AB  æµk¹W¨.ñGm§W:´÷«
000BF9C0  6D 81 50 5B 0F 0A 66 6C 3A FF 1E 42 06 FD D8 53  m.P[..fl:ÿ.B.ýØS
000BF9D0  B8 B9 3D 52 66 2D 8D 9E CD E6 D0 06 FF 75 0F EE  ¸¹=Rf-.žÍæÐ.ÿu.î
000BF9E0  9C 46 EE 71 9E 63 99 44 B6 9A 43 95 11 9E 4C C2  œFîqžc™D¶šC•.žLÂ
000BF9F0  61 29 D8 DB 06 9F 5D ED CB 35 B7 AD C4 EA 8F 16  a)ØÛ.Ÿ]íË5·.Äê..
000BFA00  BE 92 FE DA 9A 3C 1B C1 DF EC B5 5F 46 77 83 9D  ¾’þÚš<.Áßìµ_Fwƒ.
000BFA10  B8 69 FA 5C A9 C5 1B 9F 54 69 AF 80 07 0C C6 B7  ¸iú\©Å.ŸTi¯€..Æ·
000BFA20  A0 CF 8B 45 EB 07 09 AA 02 AA E8 41 1D 01 77 71   Ï‹Eë..ª.ªèA..wq
000BFA30  7C 92 DE BA 22 96 92 4E 3E BB 9B 38 A3 50 4A 56  |’Þº"–’N>»›8£PJV
000BFA40  C9 B9 91 59 68 1E 60 5F 47 AE C6 38 0F B2 BD EF  É¹‘Yh.`_G®Æ8.²½ï
000BFA50  A7 FE BD 8C 12 2C D5 AE 9D 7A D5 25 43 F7 13 12  §þ½Œ.,Õ®.zÕ%C÷..
000BFA60  5D 86 39 9A DD AE 20 90 31 E8 EA 78 9A F4 57 A5  ]†9šÝ® .1èêxšôW¥
000BFA70  3A F9 D0 FE 86 2A 10 07 4C 57 D5 79 EB 64 E6 E6  :ùÐþ†*..LWÕyëdææ
000BFA80  55 B5 CF B8 2A 10 BC 2C 6B D9 7A 06 EB DB D5 75  UµÏ¸*.¼,kÙz.ëÛÕu
000BFA90  A0 49 54 04 E2 39 D3 76 97 3A 48 11 40 45 25 DE   IT.â9Óv—:H.@E%Þ
000BFAA0  52 A1 A4 D9 8B BE 52 1F 54 FC 9C E7 5B 6A E3 CB  R¡¤Ù‹¾R.Tüœç[jãË
000BFAB0  07 18 1F ED 37 52 5E 87 22 30 C3 9F 4C 67 74 9A  ...í7R^‡"0ÃŸLgtš
000BFAC0  FF 85 98 66 B0 F6 73 B9 7B 2E 57 37 AE AB 67 C3  ÿ…˜f°ös¹{.W7®«gÃ
000BFAD0  59 73 B8 B0 C7 71 BE 09 04 77 1D 34 14 AC 8B AC  Ys¸°Çq¾..w.4.¬‹¬
000BFAE0  D7 41 6B 87 D5 F7 79 B5 0E 7B 8D 82 F6 DE 8E 41  ×Ak‡Õ÷yµ.{.‚öÞŽA
000BFAF0  D8 23 A2 AB EA 88 C8 E9 3D 70 8F 0B 6A 5F 33 AA  Ø#¢«êˆÈé=p..j_3ª
000BFB00  CB CF CA 05 F4 7C F0 F8 99 A8 46 F5 68 1C DF FC  ËÏÊ.ô|ðø™¨Fõh.ßü
000BFB10  E1 BF 6B 75 F8 54 74 FF FF FF FF 00 00 02 28     á¿kuøTtÿÿÿÿ...(

```

Thanks to anyone who can help.
and I love this site. Keep up the good work.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-26T23:20:07+00:00
- Post Title: quickbms zlib help

upload the file, or a cut of the file (check the stickied thread for help on this)

translating what you said into a quick example:

```
get fname string
endian big
get size long
get zsize long
comtype zlib
savepos pos
clog fname pos zsize size

```


finding the right filenames would take only a tiny bit more code

edit: fixed endian
## Post #3
- Username: BuC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 18, 2010 4:35 am
- Post datetime: 2010-12-26T23:42:49+00:00
- Post Title: quickbms zlib help

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-27T04:41:38+00:00
- Post Title: quickbms zlib help

```
endian big # change endian
comtype zlib # default type for clog function

# infinite loop
for

  get NEGONE long # -1
  get FNAME string # filename

  # backtrace to find the extention
  savepos FNPOS
  math FNPOS -= 4
  goto FNPOS
  getdstring EXT 4

  get ZSIZE long # real size
  get SIZE long # packed size
  savepos DATASTART # current position (data starts here)

  math SIZE += 1 # missing bytes from that value o.o

  if EXT == "csc"
    clog FNAME DATASTART SIZE ZSIZE
  endif

  math DATASTART += SIZE
  goto DATASTART

  get NEGONE long # -1
  get UNKNOWN long # ?

  # check not eof

  savepos POS
  if POS == REALSIZE
    cleanexit # exit safely
  endif

next

```


you show thanks with creative use of these smilies    or something like that
## Post #5
- Username: BuC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 18, 2010 4:35 am
- Post datetime: 2010-12-28T00:53:39+00:00
- Post Title: quickbms zlib help


