## Post #1
- Username: MaDetho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 15, 2012 7:09 am
- Post datetime: 2012-04-15T08:55:04+00:00
- Post Title: QiuckBMS and .arc files

well hi there ,

so im trying my first attempts with QuickBMS to extract some sort of .arc file.
i know there might be some tools that works allready, but i really wanna learn to make this myself.

Heres i show u the start part of its file :



so as we can see we got 9 files

From start of file :
1. long is the idstring
2. short is some unkown yet
3. short are the files number

4. getdstring NAME 0x40  (including the 0's)  is the filename
5. now heres the first long which i predict is the filetype of the archived file. so : get FILETYPE long
- first file : 07 D5 90 9F
6. get ZSIZE long (compressed)
- first file : 00 00 01 F0
7. get SIZE long (decompressed)
- first file : 00 00 8E 52
8. get OFFSET long (start offset of file)
- first file : 00 00 02 D8

When we look at our offset 0x2D8 we see the header : "68 81" which is some rare zlib compression header.

ok so now i have build a little script.
quickbms reverses all the values, which it shouldnt do because i.e. the offset "00 00 02 D8" should be "00 00 02 D8", but quickbms does "D8 02 00 00".



so my question is how i tell quickbms to not reverse my values?

another question would be: as i said the header of the beginning file is 68 81 (zlib compression) how do i decompress the unpacked file?

Thanks so much.
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-15T09:05:52+00:00
- Post Title: QiuckBMS and .arc files

Maybe, it's the same format with re5, MvC3.
[viewtopic.php?p=49010#p49010](http://forum.xentax.com/viewtopic.php?p=49010#p49010)
## Post #3
- Username: MaDetho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 15, 2012 7:09 am
- Post datetime: 2012-04-15T09:18:01+00:00
- Post Title: QiuckBMS and .arc files

wow that was a quick respnse thank you very much.

so all i needed was "endian big" this reverses the values to the right order.

and it also auto decompresses the files.

well thats all i needed for now, thank you!

EDIT: what does "comtype zlib_noerror" actually mean?
