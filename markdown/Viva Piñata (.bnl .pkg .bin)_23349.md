## Post #1
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2021-01-21T03:25:23+00:00
- Post Title: Viva Piñata (.bnl .pkg .bin)

I tried to follow this tutorial [viewtopic.php?f=16&t=12463#p103583](https://forum.xentax.com/viewtopic.php?f=16&t=12463#p103583) the script doesn't work, Example: [https://www.mediafire.com/file/57p0sh6c ... a.zip/file](https://www.mediafire.com/file/57p0sh6c7k6ws2q/Viva+Pi%C3%B1ata.zip/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-21T12:41:47+00:00
- Post Title: Viva Piñata (.bnl .pkg .bin)

(You should try it in the archives section. Because it's a matter of compression.)

read here: 
> Reply from Mattzocrazy ↑Fri Apr 21, 2017 3:20 am at Fri Apr 21, 2017 3:20 am
>
> 
[https://gist.github.com/x1nixmzeng/c55c248c384bf1c9df2a](https://gist.github.com/x1nixmzeng/c55c248c384bf1c9df2a)

Conker, different game, yes, I know, but the tool tells that english.bnl is a valid (CAFF) file.

conker_caff\bin\Debug>conker_caff english.bnl
Found block named .data (size 22964)
Found block named .gpu (size 105181)
Data offset = 384
Data length = 128145
Result   02C95D50
Expected 02C95D50
Valid file

Continuing here; tool sadly fails:
mojobojo
[https://github.com/mojobojo/PublicXboxS ... fextractor](https://github.com/mojobojo/PublicXboxStuff/tree/master/Applications/Windows/bkextractor/caffextractor)

System.Char[] 120 ChkSum: 85724B4
NumberOf Symb:2956 FileParts:2956
NumberOf Sect:1

then tries to read null terminated strings but there aren't any in the english.bnl file.

edit: in debug_pack.bin there's uncompressed strings:
rotateX rotateY rotateZ rotateW transX transY transZ scaleX scaleY scaleZ BASE LF_H NECK RT_H TAIL JAW JAW_TOP ...
