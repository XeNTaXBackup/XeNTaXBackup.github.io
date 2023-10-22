## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-09T19:21:34+00:00
- Post Title: Pangya

Here is an exe scan of this game.

```

  offset   num  description [bits.endian.size]
  --------------------------------------------
  003eb594 31   Adler CRC32 (0x191b3141) [32.le.1024]
  003ec594 32   Adler CRC32 (0x191b3141) [32.be.1024]
  003eb994 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  003ec994 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  003ebd94 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  003ecd94 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  003e90d8 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  003ec194 84   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.be rev.1024]
  0044894c 142  ACSS reverse sbox [..256]
  00444810 190  Blowfish bfp table [32.le.72]
  00444858 192  Blowfish ks0 table [32.le.1024]
  00444c58 194  Blowfish ks1 table [32.le.1024]
  00445058 196  Blowfish ks2 table [32.le.1024]
  00445458 198  Blowfish ks3 table [32.le.1024]
  00297b74 289  MD5 digest [32.le.272&]
  00444830 325  Haval hash pass2 [32.le.128&]
  004508c4 549  Windows CryptAcquireContext [..21]
  0045084e 550  Windows CryptCreateHash [..16]
  0045083c 551  Windows CryptImportKey [..15]
  00450860 552  Windows CryptHashData [..14]
  0045081a 554  Windows CryptDeriveKey [..15]
  0045082c 555  Windows CryptDecrypt [..13]
  0044894c 1210 FFT and FHT routines rv_tbl [..128]
  00444810 1315 Haval init [32.le.32&]
  004448b0 1317 Haval mc3 [32.le.128]
  00444930 1319 Haval mc4 [32.le.128]
  004449b0 1321 Haval mc5 [32.le.128]
  0044bef4 1402 seed_SS0 [32.le.1024]
  0044c2f4 1404 seed_SS1 [32.le.1024]
  0044c6f4 1406 seed_SS2 [32.le.1024]
  0044caf4 1408 seed_SS3 [32.le.1024]
  00444990 1467 HAVAL1_DS [32.le.32]
  00444910 1469 HAVAL2_DS [32.le.32]
  003e8ee8 1539 zinflate_lengthStarts [32.le.116]
  003e8f68 1541 zinflate_lengthExtraBits [32.le.116]
  003e8f65 1542 zinflate_lengthExtraBits [32.be.116]
  003e8fe8 1543 zinflate_distanceStarts [32.le.120]
  003e9060 1545 zinflate_distanceExtraBits [32.le.120]
  00444858 1577 Blowfish_s_init [32.le.4096]

- 39 signatures found in the file

```


I have attached the decrpted main exe file and some sample archives.
[http://www.MegaShare.com/877969](http://www.MegaShare.com/877969)
Here is the website
[http://www.pangya.jp/](http://www.pangya.jp/)
this game seems to be using 3ds files
[](http://img58.imageshack.us/my.php?image=screen03.jpg)

Thanks in advance.
## Post #2
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-10-17T09:50:16+00:00
- Post Title: Pangya

unpacker can found here and importer in max
```
http://pangya.shadosoft-tm.com/
```

some tools for convert mpet2mqo and pack [http://multi-up.com/357316](http://multi-up.com/357316)
mqo can open with bones, and put in game in Metasequoia 
```
http://www.metaseq.net/english/index.html
```
