## Post #1
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-03T07:18:04+00:00
- Post Title: Child of Light font files(.cdk)

I think it is something like a .fnt files that contain information of font file.
But it is different from Rayman Origin series and I can not read it. How can I deal with
this file to modify the font size, width and position for making a translation patch?
[font02.tfn.zip](https://xentaxbackup.github.io/file/7290_font02.tfn.zip)
## Post #2
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-05-03T16:25:40+00:00
- Post Title: Child of Light font files(.cdk)

Can you add texture of this font?
## Post #3
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-03T17:51:54+00:00
- Post Title: Child of Light font files(.cdk)

> Reply from Thief1987
>
> Can you add texture of this font?

Here is it. [https://www.mediafire.com/?1c1m2lzqr8mu7in](https://www.mediafire.com/?1c1m2lzqr8mu7in)
Anyway, I understand it but it doesn't represent on game. Don't know why.   

goto 0xCC there are a number of glyphs. And read each 11 long bytes.(=44 bytes)

00 00 00 28 00 00 00 20 00 00 00 45 00 00 00 60 00 00 00 05 00 00 00 05 FF FF FF FE 00 00 00 5A 00 00 00 19 00 00 00 00 00 00 00 0F 

=>
char id=00 00 00 20, x=00 00 00 45, y=00 00 00 60, width=00 00 00 05, height=00 00 00 05, xoffset= FF FF FF FE, yoffset=00 00 00 5A, xadvance=00 00 00 19, page=00 00 00 00, chnl=00 00 00 0F

00 00 00 28 00 00 00 21 00 00 00 E2 00 00 01 14 00 00 00 14 00 00 00 4C 00 00 00 06 00 00 00 12 00 00 00 21 00 00 00 00 00 00 00 0F 

=>
char id=00 00 00 21, x=00 00 00 E2, y=00 00 01 14, width=00 00 00 14, height=00 00 00 4C, xoffset= 00 00 00 06, yoffset=00 00 00 12, xadvance=00 00 00 21, page=00 00 00 00, chnl=00 00 00 0F

..and so on.

bundle_pc32.ipk and templateinstance_pc32.ipk both contain font02.tfn.ckd file. I changed hex value of font02.tfn.ckd and reimported it to bundle_pc32.ipk. Finally I copy and paste it to game folder but it doesn't change anything. And templateinstance_pc32.ipk can not unpacked by merlinsvk's quickbms script. [viewtopic.php?f=10&t=11475](http://forum.xentax.com/viewtopic.php?f=10&t=11475) So there's no way to test it. I think font02.tfn.ckd in bundle_pc32.ipk is dummy.
## Post #4
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2014-05-22T20:24:33+00:00
- Post Title: Child of Light font files(.cdk)

Here is missing "avant_garde_md_32_outline.tfn" file from templateinstance_pc32.ipk. Archive is zlibed. Zlib block starts 535159b.
[avant_garde_md_32_outline.tfn.zip](https://xentaxbackup.github.io/file/7365_avant_garde_md_32_outline.tfn.zip)
