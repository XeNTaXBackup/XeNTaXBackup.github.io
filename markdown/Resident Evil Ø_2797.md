## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-09-27T06:52:19+00:00
- Post Title: Resident Evil Ø

I couldn't find anything on google about Resident Evil Zero's compression, so I'm posting what little I know here.

Almost All the files are in an *.ARC container, holding a compressed File (*ALZ) and I'm pretty darn sure ALZ is also where the model data is locked.
BTW
St. Vamprye had already made a ARC tool for Re0. get it here;
[http://markgrass.the-horror.com/Vampyre ... tor1.1.rar](http://markgrass.the-horror.com/Vampyre/RE0_ArcExtractor1.1.rar)

Anyway these.*ARC files hold various other files, yet it uses one compressed format, or even an XOR encryption. The ext is called ALZ, but has nothing to do with ALZipCompression.

I've been trying to dismantle the header of these ALZ files, in hopes of finding the XOR key; well if it is XOR'd like Re2 that is....

[quote="ALZ Header"]Offset      0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
00000000   02 20 F3 00 00 01 02 58  F5 03 FC 41 B8 1E CD 23   . ó....Xõ.üA¸.Í#
00000010   9A 81 B4 E5 83 BF 5B 16  A6 4C B1 2E DB BE 0D 2B   š
[re0_alz.zip](https://xentaxbackup.github.io/file/1346_re0_alz.zip)
## Post #2
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2014-12-07T10:07:51+00:00
- Post Title: Resident Evil Ø

Has anyone managed to figure this out yet? I finally found a way to properly disassemble the main executable in IDA Pro, but these Gekko ops are really complex and I'm not even sure if I understand how it handles function arguments. What type of operations should I be looking for?
## Post #3
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2014-12-07T19:08:38+00:00
- Post Title: Resident Evil Ø

I think it's a form of LZ compression. Here is my guess on the structure:

u8: version/type/level
u32: decompressed length

You can definitely see a pattern when comparing files.



Anyone got any ideas?
## Post #4
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2014-12-26T17:17:03+00:00
- Post Title: Resident Evil Ø

I took it upon me to reverse engineer the decompression routine in the game since I guess no one else was going to do it. Anyone interested can get a decompressor and a text converter here:

[http://hcs64.com/mboard/forum.php?showt ... showpage=2](http://hcs64.com/mboard/forum.php?showthread=36979&showpage=2)
## Post #5
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2014-12-27T17:30:40+00:00
- Post Title: Resident Evil Ø

Thank you very much men , but iam a bit confused here in the comand line said :

Usage: alzdec <input> <output>  

So i use "alzdec <em10.mod.alz> <em10.alz> , <input em10.mod.alz> <output em10.mod> but just return with the same message from above.
## Post #6
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2014-12-27T18:16:10+00:00
- Post Title: Resident Evil Ø

Leave out the tags (< and >). Also please note that the tool is not intended for modding, which is what I assume you are trying to do.

Valid example:
alzdec.exe option_e.lz option_e_decompressed.bin

<input> must be an original (unmodified) file from the game
<output> is a file that the program will write the decompressed data to (the file will be automatically created if it does not exist).



I have not written a program to compress data back to ALZ, sorry.

If the program does not work with valid parameters, please let me know.
## Post #7
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2014-12-27T18:53:06+00:00
- Post Title: Resident Evil Ø

> Reply from Nisto
>
> Leave out the tags (< and >). Also please note that the tool is not intended for modding, which is what I assume you are trying to do.

Valid example:
alzdec.exe option_e.lz option_e_decompressed.bin

<input> must be an original (unmodified) file from the game
<output> is a file that the program will write the decompressed data to (the file will be automatically created if it does not exist).



I have not written a program to compress data back to ALZ, sorry.

If the program does not work with valid parameters, please let me know.

Thanks men now works but no i was not interested on mod this game i was just a bit confused wih the line command 

So those ALZ files have inside more arc files but you can open them and we have texture (tpp) and  think model (mdt) so my cuestion
is how i can open those mdt files?
## Post #8
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2014-12-27T19:00:18+00:00
- Post Title: Resident Evil Ø

I see. Glad it worked for you.

I don't know if there are any tools for the models yet. Maybe look at "biofat" by MarkGrass. I know that for the textures (tpl anyway) you can use "tplx".
## Post #9
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2014-12-27T19:10:15+00:00
- Post Title: Resident Evil Ø

Yea Mark Grass tool can extract the tpp files and convert them in normal tpl textures so any one can convert them in tga, dds or whatever format well. 

I myselft rip everting 5 years ago with 3Dviaprintscreen and dolphin but i know that there still a lot of beta stuff that cant be ripped due of the alz compression so thanks to you we can finally check and see what´s there.
## Post #10
- Username: jiqigou
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 14, 2012 1:18 am
- Post datetime: 2015-01-01T13:53:52+00:00
- Post Title: Resident Evil Ø

> Reply from Nisto
>
> Leave out the tags (< and >). Also please note that the tool is not intended for modding, which is what I assume you are trying to do.

Valid example:
alzdec.exe option_e.lz option_e_decompressed.bin

<input> must be an original (unmodified) file from the game
<output> is a file that the program will write the decompressed data to (the file will be automatically created if it does not exist).



I have not written a program to compress data back to ALZ, sorry.

If the program does not work with valid parameters, please let me know.

HI, Nisto, thank you very much and finally ALZ format Resident Evil 0 solved, I am waiting for more than four years time, but I want to change the enemy's data, there is a problem is that even though you can unlock tool ALZ file it can not be compressed back, very much hope that you can come up with a compression tool, once again thank you for your hard work.
## Post #11
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2015-01-20T08:37:13+00:00
- Post Title: Resident Evil Ø

Small update for the people who aren't up to date with the hcs thread: for those who wants to mod the game, you can set the first byte to 0 and the size (offset 0x1) to the uncompressed size and mod the file using uncompressed data.
## Post #12
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2016-06-25T23:50:33+00:00
- Post Title: Resident Evil Ø

The last few days, I've been working on the original ALZ decompression tool I wrote, to also support compressing, since it's been requested once or twice. Now I truly understand the algorithm (and compression concepts in general. and have finally finished writing a successor with compression support. It can (de)compress any known ALZ type (0-2), and the word compression algorithm even seems to be more efficient.

[https://github.com/Nisto/bio-tools/tree ... 0/alz-tool](https://github.com/Nisto/bio-tools/tree/master/bio0/alz-tool)
