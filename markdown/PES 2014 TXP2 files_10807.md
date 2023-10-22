## Post #1
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2013-09-26T11:06:14+00:00
- Post Title: PES 2014 TXP2 files

Hey

i try to unpack the txp2 files from the new pes2014.
These files are packed with zlib. After unpacking they look like this:
I think the first 20 bytes don't belong to the TXP2 file.

```
0010h: 00 06 C6 98 54 58 50 32 00 01 04 02 00 04 05 00  ..Æ˜TXP2........ 
0020h: 00 06 C6 84 00 00 00 6C 00 03 7F DF 00 00 00 01  ..Æ„...l..ß.... 
0030h: 00 00 00 6C 00 00 08 48 00 00 00 02 00 00 00 78  ...l...H.......x 
0040h: 00 00 08 70                                                     ...p

```

In the middle i found the following:

```
0A80h: 04 00 0F 11 22 10 1A DC FF E9 F2 F4 F0 E0 FB FB  ...."..Üÿéòôðàûû 
0A90h: FF FF E8 F3 EF 9E E7 5D F8 F7 E8 FF FA 2E 06 7D  ÿÿèóïžç]ø÷èÿú..} 
0AA0h: E7 3D 7A F7 7A 5E 7E 2E 05 E7 3D DF 1C EF AA BE  ç=z÷z^~..ç=ß.ïª¾ 
0AB0h: 2A 2A 4E 06 5D E7 3D                             **N.]ç=

```

and at the end of the file there is always the name with a apk extension.

```
6:C6A0h: 65 43 6F 6D 6D 6F 6E 2E 61 70 6B 00              eCommon.apk.

```

I used a debugger to get more information about the files:

```
0010h: 6C 00 00 00 DF 7F 03 00 01 00 00 00 6C 00 00 00  l...ß......l... 
0020h: 48 08 00 00 02 00 00 00 78 00 00 00 70 08 00 00  H.......x...p... 

```

Some bytes from the header? are switched, but the TXDT part is the same. Do
anybody knows the format or the compression methode?
## Post #2
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2013-11-27T10:46:58+00:00
- Post Title: PES 2014 TXP2 files

I have found some new Information.

Some guy on a forum shows an example of a decrypted file but don't tell how he do it.
He said the decrypted part is a simple bitmap array.

[Image (encrypted file)](http://i1136.photobucket.com/albums/n490/jenkey1002/1_zpseb90fe62.png)
[Image (decrypted file)](http://i1136.photobucket.com/albums/n490/jenkey1002/2_zps90029e51.png)

I have uploaded an example file, maybe somebody could take a look.
[file](http://www16.zippyshare.com/v/9937391/file.html)
## Post #3
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2014-07-30T20:30:07+00:00
- Post Title: PES 2014 TXP2 files

After some break i take a closer look at these files. Unfortunately i still can't unpack these files.

The important part (texture file) starts at TXDT.
The first DWORD is the unpacked file size, the second one is the packed file size. (Big Endian)

```
0010h: 00 FE F2 F2 04 00 40 01 00 01 00 4F 11 22 10 15  .þòò..@....O.".. 
0020h: DC FF E9 F2 03 DD FE 07 FF FF FF 2E 0F 40 0F 52  Üÿéò.Ýþ.ÿÿÿ..@.R 
0030h: 0F 64 0F 76 0F 00 88 0F 9A 0F AC 0F BE 0F D0 0F  .d.v..ˆ.š.¬.¾.Ð. 
0040h: E2 0F F4 0F 06 1F 00 18 1F 2A 1F 3C 1F 4E 1F 60  â.ô......*.<.N.` 

```

The decryption starts by reading the byte at 1A8 (FF)and all the files start with the same bytes:

```
FF 54 58 44 54 00 01 02 00 FE F2 F2
```

After the decompression is finished, the file looked like this:

```
0010h: 01 00 01 00 11 22 10 15 00 00 00 00 00 00 00 00  .....".......... 
0020h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 03  ................ 
0030h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0040h: 00 FF FF FF 00 FF FF FF 00 FF FF FF 00 FF FF FF  .ÿÿÿ.ÿÿÿ.ÿÿÿ.ÿÿÿ 

```

It's just a simple Bitmap array.
Result image:


I think the fiiles are somehow compressed but i can't find out in which way.
Has somebody an idea in which way the decompress works?

If somebody wants some example files just pm me.
## Post #4
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2015-02-01T22:47:08+00:00
- Post Title: PES 2014 TXP2 files

I'm pretty sure Konami use the prs compression like in the Phantasy Star Portable 1/2 nmll files.
I tryed [https://github.com/FraGag/prs.net](https://github.com/FraGag/prs.net) to unpack it but it doesn't work.
The first chunk works correctly but then i get an error because the lookBehindOffset is wrong.
Has somebody informations about the ptr compression or can somebody tell me which parameter i need to change?
