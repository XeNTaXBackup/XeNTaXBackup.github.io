## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-21T21:08:29+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

If I'm not mistaken, these .DAT files hold the game's texts. If somebody could take a look at it, I would be grateful 
Link: [http://rghost.net/47332524](http://rghost.net/47332524)
## Post #2
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-10T14:41:26+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

Bumping the thread, updated the links.
## Post #3
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-07-10T19:21:45+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

strings files is simple

```
string fname - ".dat"
string fname + ".txt" 
get strings long
log MEMORY_FILE 0 0

for i = 0 < strings
get dummy long
get stringoffset long
savepos tableoffset
goto stringoffset
getct str string 0x00
strlen str_size str
putdstring str str_size MEMORY_FILE
put 0x0a0d short MEMORY_FILE
goto tableoffset
next i

get size asize MEMORY_FILE
log fname 0x00 size MEMORY_FILE
```


But d6Item have strange structure for text. That's for sure text files?
## Post #4
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-10T19:54:33+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

Well, I wasn't sure, but uploaded it anyway, thought it had a different structure.
The code you posted, is that a BMS script? Because Quickbms crashes, when I import it.
[crash.jpg](https://xentaxbackup.github.io/file/6514_crash.jpg)
## Post #5
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-07-10T20:11:42+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

Yes for quickbms.
This is what i get after applying script
[http://rghost.ru/private/47339674/6a8f1 ... 602604e56a](http://rghost.ru/private/47339674/6a8f1578bde124a0b9c4b2602604e56a)
## Post #6
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-10T20:33:02+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

> Reply from Thief1987
>
> Yes for quickbms.
This is what i get after applying script
http://rghost.ru/private/47339674/6a8f1 ... 602604e56a
Thank you, got it to work, but it can't be used to reimport the file back into the archive with QuickBMS, right? It says "Script invalid for reimporting, it uses MEMORY_FILEs".
## Post #7
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-07-10T21:20:30+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

For repack need new script. Format not hard, i will write script tomorrow
## Post #8
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-11T05:39:22+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

> Reply from Thief1987
>
> For repack need new script. Format not hard, i will write script tomorrow
Thank you very much
## Post #9
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-07-14T00:43:31+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

Sorry for delaying.

```
open FDDE "txt" 1
get fname FILENAME
string fname + "repack"
log MEMORY_FILE 0 0
get strings long
put strings long MEMORY_FILE
savepos ftoffset MEMORY_FILE
math ftoffset + 0x8
math TMP = strings
math TMP * 0x8
getdstring stringtable TMP
putdstring stringtable TMP MEMORY_FILE
math strings - 1
for i = 0 < strings
savepos tmpoff 1
get prov short
if prov != 2573
goto tmpoff 1
getct str string 0x0d 1
strlen str_size str 
putdstring str str_size MEMORY_FILE
getdstring dummy 0x1 1
put 0x00 byte MEMORY_FILE
savepos stroffset MEMORY_FILE
goto ftoffset MEMORY_FILE 
get dummy long MEMORY_FILE
put stroffset long MEMORY_FILE
savepos ftoffset MEMORY_FILE 
goto stroffset MEMORY_FILE
else
put 0x00 byte MEMORY_FILE
savepos stroffset MEMORY_FILE
goto ftoffset MEMORY_FILE 
get dummy long MEMORY_FILE
put stroffset long MEMORY_FILE
savepos ftoffset MEMORY_FILE 
goto stroffset MEMORY_FILE

endif


next i

getct str string 0x0d 1
strlen str_size str 
putdstring str str_size MEMORY_FILE
put 0x00 byte MEMORY_FILE

get size asize MEMORY_FILE
log fname 0x00 size MEMORY_FILE
```


This is repack script, i unpack and repack without change ds6strings.dat file for testing. Repack and original dat same. If you don't break structure of unpacking txt files(don't delete dummy strings for example) script must work correctly. Although write if you have problem
## Post #10
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-14T07:59:24+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

Thank you. Could you write the whole commandline command you used? I think I'm doing something wrong.

I use: quickbms.exe -r -w repack.bms D6STRING.DAT D6STRING

It says "Incomplete input file number 1, can't read 1 bytes." 
D6STRING is the directory, where I extracted D6STRINGS.txt.
## Post #11
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-07-14T16:54:26+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

Unpack and repack doing with the same command. Just choose script and .DAT file, and unpacking .TXT must be in the same folder. Not need use repack function of quickbms.
## Post #12
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-22T16:33:50+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

One small thing tho. Does anyone know how to edit these .FNT files (font files)?
[dlfonts.zip](https://xentaxbackup.github.io/file/6529_dlfonts.zip)
## Post #13
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-07-22T19:00:09+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

I'm not good at this kind of thing, but here's my try:

```
4 bytes = texture width
4 bytes = texture height
4 bytes = number of glyphs
8 bytes = zeros

Offset 0x14 - description start
4 bytes = ascii code of glyph
4 bytes = x coordinate
4 bytes = y coordinate
4 bytes = glyph's width
4 bytes = glyph's height
4 bytes = have no clue

... and so on

```


Whole "description" is 0x8B4 bytes long. After it goes the texture until end of file.
It seems like RGBA format, so 4 bytes per pixel.

If I rename it to .raw extension, I can open it in Photoshop with these params.

Example for DLII_Font01.FNT.raw



And it looks like




But I'm not really sure if am I right
## Post #14
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-22T19:05:15+00:00
- Post Title: Dungeon Lords MMXII [.DAT]

Thanks, I'll try this
