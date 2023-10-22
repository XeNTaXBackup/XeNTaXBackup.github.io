## Post #1
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2012-09-07T04:33:21+00:00
- Post Title: Aquapazza Textures

So I've extracted a texture from the game using a slightly modified version of the algorithm used for Arcana Heart and I'm not sure what to do with it.  The table with the texture information on it claims that it is DXT1 but I cannot get it to display properly.  In fact, this texture actually comes as a two-part file which I have just joined together for convenience.  (Equal size parts, just go halfway to see the second file)

I'm totally stumped, I have very limited experience dealing with DDS compression types.  As far as I know this is supposed to expand to 1024x1024.
[AquapazzaUnknown.zip](https://xentaxbackup.github.io/file/5774_AquapazzaUnknown.zip)
## Post #2
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2012-09-11T13:57:36+00:00
- Post Title: Aquapazza Textures

Figured it out, the two parts needed to be striped together.  The first half is all the palette chunks and the second half is all the pixel data.
## Post #3
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-01-05T22:52:54+00:00
- Post Title: Aquapazza Textures

Sorry for bumping this thread,but im trying to also extract textures,for ps3,all i can find within the files are .SAP files within the files
can you explain how you used the algo rhytum of AC and extracted it
## Post #4
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-01-12T16:03:05+00:00
- Post Title: Aquapazza Textures

here are the first 304 bytes of the file "stage0C_c.bgt" from the folder "BG" from aquapazza

i will write down what i found out so far


```

00000000  00 0A 00 05 00 32 01 00 01 00 00 01 31 54 58 44  .....2......1TXD
00000010  BE A3 D7 0A 3E 38 51 EC 00 00 00 00 01 00 00 00  ¾£×.>8Qì........
00000020  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000030  01 01 01 01 01 01 01 01 01 01 01 01 01 01 01 01  ................
00000040  01 01 01 01 01 01 00 00 00 00 00 00 00 00 00 00  ................
00000050  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000060  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000070  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000080  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000090  00 00 00 00 14 0A 00 00 2A BB 00 00 14 FC 00 00  ........*»...ü..
000000A0  2C 5F 00 00 0A 36 00 00 13 FE 00 00 1E 06 00 00  ,_...6...þ......
000000B0  04 78 00 00 0C 78 00 00 29 E6 00 00 3E E1 00 00  .x...x..)æ..>á..
000000C0  2D 98 00 00 1F 5B 00 00 22 26 00 00 09 50 00 00  -˜...[.."&...P..
000000D0  0A 26 00 00 19 F2 00 00 2F 69 00 00 3F 73 00 00  .&...ò../i..?s..
000000E0  36 98 00 00 28 AA 00 00 19 B8 00 00 00 00 00 00  6˜..(ª...¸......
000000F0  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000100  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000110  00 00 00 00 00 00 00 00 00 00 89 53 41 50 00 00  ..........‰SAP..
00000120  00 00 00 00 40 00 00 00 40 00 00 00 00 18 00 00  ....@...@.......
00000130  07 9E 3F FF 00 00 FF FF F8 01 F8 01 F8 01 F8 01  .ž?ÿ..ÿÿø.ø.ø.ø.

```


1st 2 bytes is a short dont know what it is for
2nd 2 bytes is a short dont know what it is for
3rd 2 bytes is a short which is the amount of "SAP" files (0x32 or 50 bytes)
4th 2 bytes is a short and is the width or height of the image "256"
5th 2 bytes is a short and is the width or height of the image "256"
6th 2 bytes is a short and is always 00 01 as i have seen in all the other files i looked at in the "BG" folder
7th 4 bytes is dxt1 signature
8th 4 bytes is a float value "-0,32"
9th 4 bytes is a float value "0,18"
10th 4 bytes is a null long is also for all the files the same in "BG" folder
11th 4bytes is always 10 00 00 00
then you get the amount of "SAP" in single bytes in this case 0x32 bytes these are flags for the next table when its 00 it contains nothing and when its 01 it contains the size of the "SAP" file
then you get the size table of the "SAP" files these are 4 bytes which in this case the size is 0xC8 or 200 bytes (50x4)
from here the "SAP" files begin
1st 4 bytes is "SAP" signature
2nd 4 bytes are zero's but what i have seen in the other files they sometimes are "00 01 00 00" or "00 01 00 01"so i dont know if this is in read in 4 bytes or in single bytes
3rd and 4th 4 bytes always have the same values in this case "00 00 40 00"=16384???? in other files its sometimes "00 03 20 00" or "00 00 80 00"
5th and 6th 4 bytes are offsets starting beginning of the "SAP" file the first 1 is always "00 00 00 18" the 2nd differs per "SAP" file

after this the data begins until the 2nd offset,i dont know if its compressed or not,i used offzip with no result
so what am i missing/or not seeing here... some help is apreciated
## Post #5
- Username: powoct
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 12, 2011 5:59 pm
- Post datetime: 2013-02-10T10:42:18+00:00
- Post Title: Aquapazza Textures

```
string NAME += ".dds"
get SIZE asize
set HALFSIZE SIZE
math HALFSIZE / 2
set COUNT SIZE
math COUNT / 8
set OFF1 0
set OFF2 HALFSIZE
set OFF 0x80
set MEMORY_FILE binary "\x44\x44\x53\x20\x7c\x0\x0\x0\x7\x10\x8\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x20\x0\x0\x0\x4\x0\x0\x0\x44\x58\x54\x31\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x10\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0"
putVarChr MEMORY_FILE 0x10 0x400 long
putVarChr MEMORY_FILE 0xc 0x400 long
putVarChr MEMORY_FILE 0x14 SIZE long
for i = 0 < COUNT
goto OFF1
get TMP long
putVarChr MEMORY_FILE OFF TMP long
math OFF + 4
math OFF1 + 4
goto OFF2
get TMP long
putVarChr MEMORY_FILE OFF TMP long
math OFF + 4
math OFF2 + 4
next i
get ASIZE asize MEMORY_FILE
log NAME 0 ASIZE MEMORY_FILE
```

I can convert the .raw to .dds.
But how can I get .raw from .pil files of Aquapazza?Can you tell me,Insanius?
Thanks bro.
