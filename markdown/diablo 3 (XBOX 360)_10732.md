## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-08-31T01:44:00+00:00
- Post Title: diablo 3 (XBOX 360)

hey guys i just wanted to know if anyone is willing to open up the cpk files of diablo 3 i used the cpk script but it didnt work 

here is a small sample i took off the game 

[http://www.mediafire.com/download/q26n6 ... c/CPKs.rar](http://www.mediafire.com/download/q26n6f96bzvio7c/CPKs.rar)
## Post #2
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-08-31T13:35:26+00:00
- Post Title: diablo 3 (XBOX 360)

It's not criware cpk, it's custom blizzard format, and seems it's have encrypt filetable, on ps3 used zlib compression, don't know about xbox

ps xbox version also use zlib
## Post #3
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-05T16:50:26+00:00
- Post Title: diablo 3 (XBOX 360)

The main header has a few bits of info.  
-File entry count
-zlib blocks start
-possible checksum before padding near end of main header
-a few other unknowns

The next section looks encrypted.
There is a section after the one that looks encrypted that seems to go up kind of sequentially.
After that the name pointer table starts, and after that the names table.

Next the zlib blocks start.
Zlib blocks go:

```
{
    ushort decompressedSize;
    ushort unkFlag; //maybe compression level
    ushort compressedSize;
    char    zlibBlock[compressedSize];
}

```


The zlib blocks are not in the same order as the name table afaik.  It may be for small files like enUS_Patch.cpk from the title updates.
Also I found encrypted blocks intermingled with the zlib blocks.  Its a simple xor key and routine to decrypt them.  Decrypted data is more zlib blocks for the ones I've decrypted so far.
Once the zlib blocks are decompressed I see a lot of files with 0xDEADBEEF magic.  Some of the decompressed file entries are made up of 2 or more of the decompressed blocks.

This format is slightly reminding me of the Dead or Alive 5 format.
