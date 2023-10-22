## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-27T20:30:13+00:00
- Post Title: Dance Mission 2 【勁舞團2】

This game is using the nif file format so once this is extracted anyone can access the nif files.
full installer
[ftp://ftp.games.seed.net.tw/pub/games/g ... 1.1.2).exe](ftp://ftp.games.seed.net.tw/pub/games/gm_insrea/GAME/BongDigo/BD_WebFull%281.1.2%29.exe)
website [http://www.bongdigo.com.tw/index.asp](http://www.bongdigo.com.tw/index.asp)

```
next 4 bytes files in archive ( after this file table begins)
begin and end with 00
1st 4 bytes are archive number / something to do with weather its a file or folder / unkown pattern?
2nd 4 bytes are location
Next 4 bytes are un compressed size
next 4 bytes are length of file
Next 4 bytes indicate compression seems to always be 01 00 00 00 ( I don't see any un compressed files :) )
next32 bytes are encrypted file name / file name hash?
```


here is a scan of the game.

```
  --------------------------------------------
  004a8d00 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  0054a660 142  ACSS reverse sbox [..256]
  004cd470 145  SHA256 Hash constant words K (0x428a2f98) [32.le.256]
  003eed66 147  SHA256 Initial hash value H (0x6a09e667UL) [32.le.32&]
  0041732e 289  MD5 digest [32.le.272&]
  00542d88 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]
  004ccd40 1173 DES initial permutation IP [..64]
  004cce10 1175 DES permuted choice table (key) [..56]
  004cce48 1176 DES permuted choice key (table) [..48]
  004cce88 1177 DES S-boxes [..512]
  0054a660 1210 FFT and FHT routines rv_tbl [..128]
  004a8b10 1539 zinflate_lengthStarts [32.le.116]
  004a8b90 1541 zinflate_lengthExtraBits [32.le.116]
  004a8b8d 1542 zinflate_lengthExtraBits [32.be.116]
  004a8c10 1543 zinflate_distanceStarts [32.le.120]
  004a8c88 1545 zinflate_distanceExtraBits [32.le.120]
  004ccd80 1572 DES_fp [..64]
  004ccdc0 1573 DES_ei [..48]
  004ccdf0 1574 DES_p32i [..32]
  004cd574 1604 Crypton kp [32.le.16]
```


I am guessing it is using md5 for the file names like spike girls did?
Then it uses the default zlib is my guess due to each file starting with 78 9C

Here are the main exe files and some sample pac files.
[http://www.MegaShare.com/821033](http://www.MegaShare.com/821033)

a screen shot from the game
[](http://xs.to/xs.php?h=xs538&d=09181&f=dance1979.jpg)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-28T00:14:37+00:00
- Post Title: Dance Mission 2 【勁舞團2】

I have made a quick script [here](http://aluigi.org/papers/bms/dancemission2.bms)
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-28T02:26:22+00:00
- Post Title: Dance Mission 2 【勁舞團2】

Thanks so much  I found where the file names are stored and I am going to tryy and use your great program to extract the files with their names. Ill post anything I find.
