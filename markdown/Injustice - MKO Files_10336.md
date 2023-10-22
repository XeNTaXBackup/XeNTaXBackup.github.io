## Post #1
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2013-04-14T22:18:13+00:00
- Post Title: Injustice - MKO Files

Injustice has released a patch on the 360, and inside it there are some MKO files that contain character data. It looks compressed/encrypted or something, or its just in a format I don't understand. 

Can someone point me in the right direction about how to approach this? I've attached some samples

FYI, in the uncompressed file, this may be the header(?) for the CHAR_Aquaman.mko if that helps (patch version is in the attachment):

```

008CE870  00 00 11 43 68 61 72 5F 41 71 75 61 6D 61 6E 2E  ...Char_Aquaman.
008CE880  6D 6B 6F 00 00 00 05 87 00 00 00 00 00 06 73 A0  mko....‡......s 
008CE890  00 00 00 01 81 3F 5F C1 00 00 01 49 00 00 07 F3  .....?_Á...I...ó
008CE8A0  00 00 00 A1 00 00 00 0B 00 00 00 D6 00 00 00 3A  ...¡.......Ö...:
008CE8B0  00 00 FC 88 00 00 00 09 00 03 1E 94 00 00 7D C4  ..üˆ.......”..}Ä
008CE8C0  00 01 14 C0 00 00 08 C4 00 00 DF 48 00 00 1D 40  ...À...Ä..ßH...@
008CE8D0  00 00 00 50 00 00 00 00 00 00 00 00 00 00 00 00  ...P............
008CE8E0  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
```

[IGAU-MKO-Samples.rar](https://xentaxbackup.github.io/file/6331_IGAU-MKO-Samples.rar)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-14T23:48:29+00:00
- Post Title: Injustice - MKO Files

it is indeed compressed (compressed poorly too lol winrar compresses it again to half the size).
if you look at the export table for aquaman prepatch:

```

```


the first 8 bytes in the mko file are

00009859 000673A0

which appear to be compressed and uncompressed sizes. did you try decompressing the mko data using LZO1X?
## Post #3
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2013-04-15T09:45:49+00:00
- Post Title: Injustice - MKO Files

Aquaman.mko patched header:

```
00009859 000673A0 00064F80 8F00F49201FD2086010B748201744C8201156483
```


The first 4 bytes are the size of the mko file in whole.
The next 4 bytes (0x05-0x08) seem to be the decompressed size, however this same value (000673A0) appears in the decompressed Aquaman xxx file just a few bytes after it says Char_Aquaman.mko lol - not sure why that value matches the value in this mko file (maybe its like a before/after check value or something).

In the Aquaman mko, bytes 9-12 also seem related to bytes 5-8, but less. I saw this int he tweakvars file for each character as well.  First value tells you how long the section/file is, next value is smaller and I'm not sure what exactly it signifies. The difference between the two values changes from character to character as well, so its not like a constant footer size or something.

I tried LZO1x starting at 9,13 etc, but they all did not work. Not sure if I'm using it correctly - but if I am, I think I'm telling it to start reading compressed data at offsets 9 or 13, then tell it the source size (first 4 bytes - however many bytes I read in). I've tried using the 3rd value (bytes 0x09-0x0C) as the destsize as well, but none have worked.

----------------------

EDIT: So I extracted the MKO from the decompressed PAK - going by the offsets/size from the export table. RAR'd it using best compression and it only comes down to 59kb. Tried a bunch of zip parameters and only got it down to about 52k. The patch file is only 39k

So one way or another, I think that means that the patch file is partial - in relation to the whole MKO.

----------------------

EDITx2: Is it possible to insert compressed code into another compressed package and still unzip correctly? Like, the XXX files are compressed, maybe this compressed segment needs to be inserted into there before the XXX file is decompressed?
## Post #4
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2013-04-15T13:39:54+00:00
- Post Title: Injustice - MKO Files

I extracted the original Aquaman.mko from the decompressed xxx file. Its attached. Cant read it still, but I know certain parts of it that I am 100% sure have not changed that I expect to be in the patched Aquaman.mko as well. Theres a large section of readable text starting at 0x00011355 - the majority of which should not have changed.  The section starting at 0x00027059 has minor changes but a lot of it should be the same as well.
[OriginalExtracted-Char_Aquaman.rar](https://xentaxbackup.github.io/file/6332_OriginalExtracted-Char_Aquaman.rar)
## Post #5
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2013-04-16T04:59:14+00:00
- Post Title: Injustice - MKO Files

Hmm, I think it may just be my code for using the lzo1x decompression, or not knowing the offsets etc. I ran a loop starting at different offsets but couldn't get a successful decompress. Doesn't seem 100% consistent either (sometimes different output sizes?). 

Using minilzo and if I use the decompress_safe then I don't get any filesizes that are close to expected, but if I just do the straight decompress (not decompress_safe), I get a file thats almost the right size but a little smaller. Which seems okay because I'm pretty sure it doesn't contain the header. However, values in it aren't right and it still gives me an error on decompression

----



EDIT: Yeah, I'm at a total loss as to where to go from here. Not sure what type of compression it is or what offset it starts from. The files are tiny so I was hoping it would be easy to figure out, buuut, its not lol .. well, at least, not easy for me with my experience level.  HEEELP howfie
## Post #6
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-04-16T16:58:04+00:00
- Post Title: Injustice - MKO Files

edit

i looked at your extracted file
0x813F5FC1 is your sig/header for the .mko everything before that is related to the .XXX file

after the sig its trivial  almost same as mk9

first 4 bytes after header 00 00 01 49 is the amount of the first block of bytes (table),look closer and you will see a pattern.
they are numbered till 01 49
second 4 bytes after header 00 00 07 F3,is the amount of the second block of bytes(table),this is easily checked because they have a fixed size of 16 bytes
check it if you select everything from the second block you will get 0x7F30   

well the rest as i said is trivial



for ps3 will be a different story,after decompressing the char_xxx file the .mko is still compressed with .slz extension within the decompressed char file

already tried several things to decompress it,still no luck yet

if someone can help here is the ps3 decompressed .mko from bitman,and the compressed .slz of bitman
[slzmko.rar](https://xentaxbackup.github.io/file/6334_slzmko.rar)
## Post #7
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2013-04-17T02:42:46+00:00
- Post Title: Injustice - MKO Files

> Reply from darksoul
>
> edit

i looked at your extracted file
0x813F5FC1 is your sig/header for the .mko everything before that is related to the .XXX file

after the sig its trivial  almost same as mk9

first 4 bytes after header 00 00 01 49 is the amount of the first block of bytes (table),look closer and you will see a pattern.
they are numbered till 01 49
second 4 bytes after header 00 00 07 F3,is the amount of the second block of bytes(table),this is easily checked because they have a fixed size of 16 bytes
check it if you select everything from the second block you will get 0x7F30   

well the rest as i said is trivial



for ps3 will be a different story,after decompressing the char_xxx file the .mko is still compressed with .slz extension within the decompressed char file

already tried several things to decompress it,still no luck yet

if someone can help here is the ps3 decompressed .mko from bitman,and the compressed .slz of bitman

Thx for the info, but I have the MKO from the decompressed file of course. However, this data changes when they release new patches.  I'd like to be able to compare the new files with the old (these files contain the data for the moves (damages etc)). When I extracted the files from the latest patch, it contained a bunch of compressed MKO files (attachment in first post), and I don't know what to extract THOSE mko files (theyre like, different compressed versions of the mko files or something).  To decompress the char.xxx files it was LZO1x so I could extract that one MKO with a hex editor, but now for the patch files it appears its something else. 

Thanks for the info on the tables though. I'll take a look and see if that helps me make any other sense out of this.
## Post #8
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2013-04-17T13:22:54+00:00
- Post Title: Injustice - MKO Files

> Reply from darksoul
>
> edit
if someone can help here is the ps3 decompressed .mko from bitman,and the compressed .slz of bitman

Kind of a dumb question, but how do you have the decompressed .mko if you're looking to decompress it? Is it pulled directly from PS3 while its running? (if so I need to learn how to do that lol). Pls PM if you're more comfortable that way.  I assume you want to know how to decompress it so you modify values/recompress it?
## Post #9
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-04-17T15:18:09+00:00
- Post Title: Injustice - MKO Files

> Reply from sh0ck1
>
> Thx for the info, but I have the MKO from the decompressed file of course. However, this data changes when they release new patches.  I'd like to be able to compare the new files with the old (these files contain the data for the moves (damages etc)). When I extracted the files from the latest patch, it contained a bunch of compressed MKO files (attachment in first post), and I don't know what to extract THOSE mko files (theyre like, different compressed versions of the mko files or something).  To decompress the char.xxx files it was LZO1x so I could extract that one MKO with a hex editor, but now for the patch files it appears its something else. 

Thanks for the info on the tables though. I'll take a look and see if that helps me make any other sense out of this.

Perhaps the MKOs stack? For instance, the game loads the original, then loads patch info atop, and thus the patch version contains only changes since release? Just a shot in the dark.
## Post #10
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2013-04-18T11:35:59+00:00
- Post Title: Injustice - MKO Files

> Reply from Teancum
>
> 
Perhaps the MKOs stack? For instance, the game loads the original, then loads patch info atop, and thus the patch version contains only changes since release? Just a shot in the dark.

Even if this were true, the problem right now is the compression on the Patched MKO.  Without being able to decompress it, I'm stuck
## Post #11
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-04-27T07:54:26+00:00
- Post Title: Injustice - MKO Files

> Reply from sh0ck1
>
> 
Kind of a dumb question, but how do you have the decompressed .mko if you're looking to decompress it? Is it pulled directly from PS3 while its running? (if so I need to learn how to do that lol). Pls PM if you're more comfortable that way.  I assume you want to know how to decompress it so you modify values/recompress it?
yes i want to know what compression method they used

ok i used comtype scan from aluigi on the .slz deleting the first 12 bytes
286.dmp gave me a decompressed header,but only the header
i looked up 286 and its bzip2 (correct me if im wrong)
it decompressed the .slz until the padding started

this is what i got decompressed from .slz after useing comtype scan in 286.dmp



```

00000000  00 00 00 01 0A 3E 77 69 00 00 01 85 00 00 09 17  .....>wi...…....
00000010  00 00 00 B5 00 00 00 0C 00 00 00 AB 00 00 00 40  ...µ.......«...@
00000020  00 01 03 D4 00 00 00 31 00 03 FB 00 00 00 88 04  ...Ô...1..û...ˆ.
00000030  00 01 3E B0 00 00 07 F3 00 00 E3 1C 00 00 20 B8  ..>°...ó..ã... ¸
00000040  00 00 00 50 00 00 00                             ...P...

```


here is the first 128 bytes of the original .slz (after deleting the first 12 bytes)

```

00000000  00 00 00 00 01 0A 3E 77 69 82 01 07 85 00 00 09  ......>wi‚..…...
00000010  17 01 10 B5 A8 01 14 0C 01 04 AB 01 08 40 00 01  ...µ¨.....«..@..
00000020  21 03 D4 01 10 31 00 03 FB 01 13 00 88 04 00 01  !.Ô..1..û...ˆ...
00000030  3E B0 00 00 00 07 F3 00 00 E3 1C 00 00 2F 20 B8  >°....ó..ã.../ ¸
00000040  01 28 50 01 2C 00 01 FF 00 01 FF 00 01 FF E0 00  .(P.,..ÿ..ÿ..ÿà.
00000050  01 FF 00 01 FF 00 31 B0 01 21 E2 B9 D4 05 93 00  .ÿ..ÿ.1°.!â¹Ô.“.
00000060  00 04 E4 01 DD 5C 65 4C E1 62 5C 07 21 06 F5 BB  ..ä.Ý\eLáb\.!.õ»
00000070  F4 3F 8F 61 8B 00 35 8B 22 73 E7 00 00 05 51 40  ô?.a‹.5‹"sç...Q@


```


and here is the first 128 bytes original already decompressed .slz to .mko (no first 12 bytes deleted)

```

00000000  00 00 00 01 0A 3E 77 69 00 00 01 85 00 00 09 17  .....>wi...…....
00000010  00 00 00 B5 00 00 00 0C 00 00 00 AB 00 00 00 40  ...µ.......«...@
00000020  00 01 03 D4 00 00 00 31 00 03 FB 00 00 00 88 04  ...Ô...1..û...ˆ.
00000030  00 01 3E B0 00 00 07 F3 00 00 E3 1C 00 00 20 B8  ..>°...ó..ã... ¸
00000040  00 00 00 50 00 00 00 00 00 00 00 00 00 00 00 00  ...P............
00000050  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000060  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000070  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................

```


the first 12 bytes from the .slz consist of header,size and compressed size

```

00000000  53 4C 5A 00 00 07 9C 80 00 01 C2 28              SLZ...œ€..Â(

```


anyone know the algo of bzip2 or maybe its a modified bzip2 compression,or its just a part of the bzip compression?

edit:

got the wrong algorithm,286.dmp is decompressed with coreonline,decompressor is made by Ekey
## Post #12
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-04-27T20:47:41+00:00
- Post Title: Injustice - MKO Files

@ Ekey can you have a look at the .slz file?
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-04-29T07:49:24+00:00
- Post Title: Injustice - MKO Files

have you already tried slz.bms?
[http://aluigi.org/papers/bms/slz.bms](http://aluigi.org/papers/bms/slz.bms)
## Post #14
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-04-29T15:19:06+00:00
- Post Title: Injustice - MKO Files

Yes its the first thing i tried 

But gave me this error 

```
------------------------------
  00000010 2157709056 CHAR_BATMAN.SLZ.unslz

Error: impossible to write -2137258240 bytes (total -2137258240), check your dis
k space

Press RETURN to quit
```


offset of data begins at 0xC in these .slz file
and is endian big 

i searched for coreonline algo but without result
## Post #15
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-05-12T10:51:35+00:00
- Post Title: Injustice - MKO Files

so this is what i figured out thus far

after looking and comparing the the compressed .slz and the compressed .mko for xbox
i think they are compressed the same way

if im correct it reads 1 byte/8 bits which determines if the next 8 bytes are compressed or not

so in the example i posted earlier in the thread of the compressed .slz

```

00000000  00 00 00 00 01 0A 3E 77 69 82 01 07 85 00 00 09  ......>wi‚..…...
00000010  17 01 10 B5 A8 01 14 0C 01 04 AB 01 08 40 00 01  ...µ¨.....«..@..
00000020  21 03 D4 01 10 31 00 03 FB 01 13 00 88 04 00 01  !.Ô..1..û...ˆ...
00000030  3E B0 00 00 00 07 F3 00 00 E3 1C 00 00 2F 20 B8  >°....ó..ã.../ ¸
00000040  01 28 50 01 2C 00 01 FF 00 01 FF 00 01 FF E0 00  .(P.,..ÿ..ÿ..ÿà.
00000050  01 FF 00 01 FF 00 31 B0 01 21 E2 B9 D4 05 93 00  .ÿ..ÿ.1°.!â¹Ô.“.
00000060  00 04 E4 01 DD 5C 65 4C E1 62 5C 07 21 06 F5 BB  ..ä.Ý\eLáb\.!.õ»
00000070  F4 3F 8F 61 8B 00 35 8B 22 73 E7 00 00 05 51 40  ô?.a‹.5‹"sç...Q@
```


the first byte is 00 which means first 8 bytes are uncompressed then you will get 
82 \ 10000010 unsigned so the second byte of the next 8 bytes is compressed and the last of the 8 bytes

(this is correct if you compare the decompressed and compressed file)

this means 07 \ 00000111 is compressed and 01 \ 00000001 is compressed? after that i cant make any sense out of it anymore
