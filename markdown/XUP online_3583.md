## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-13T23:47:37+00:00
- Post Title: XUP online

Here is the game Xup Online.
[http://www.xuponline.com/Main.asp](http://www.xuponline.com/Main.asp)
This game uses nif files that are compatible with existing nif scope tools.
The archives have some kind of compressed table that I can not figure out how to decompress.
I have successfully extracted all the files except the file table with offzip using the -5 and -15 switches.
this is all I can figure out without the table which starts at 0x10 in the archive.

```
get UNK1 long
get UNK2 long
get FILES long
for i = 0 < files

clog NAME OFFSET ZSIZE SIZE
next i
```

[http://www.MegaShare.com/1238534](http://www.MegaShare.com/1238534)

also here is a quick exe scan of the game.

```
--------------------------------------------
00092e68 31   Adler CRC32 (0x191b3141) [32.le.1024]
00093e68 32   Adler CRC32 (0x191b3141) [32.be.1024]
00093268 33   Adler CRC32 (0x01c26a37) [32.le.1024]
00094268 34   Adler CRC32 (0x01c26a37) [32.be.1024]
00093668 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
00094668 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
00092a68 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
00093a68 84   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.be rev.1024]
00096b00 145  SHA256 Hash constant words K (0x428a2f98) [32.le.256]
00096c00 149  Hash constant words K for SHA-384 and SHA-512 [64.le.640]
00097828 165  AES Rijndael S / ARIA S1 [..256]
00097928 166  AES Rijndael Si / ARIA X1 [..256]
00097a28 167  Rijndael Te0 (0xc66363a5U) [32.le.1024]
00097e28 169  Rijndael Te1 (0xa5c66363U) [32.le.1024]
00098228 171  Rijndael Te2 (0x63a5c663U) [32.le.1024]
00098628 173  Rijndael Te3 (0x6363a5c6U) [32.le.1024]
00098a28 176  Rijndael Td0 (0x51f4a750U) [32.le.1024]
00098e28 178  Rijndael Td1 (0x5051f4a7U) [32.le.1024]
00099228 180  Rijndael Td2 (0xa75051f4U) [32.le.1024]
00099628 182  Rijndael Td3 (0xf4a75051U) [32.le.1024]
00099a28 185  Rijndael rcon [32.le.40]
0004e966 307  SHA1 / SHA0 / RIPEMD-160 initialization [32.le.20&]
000b0208 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]
000950b0 357  Zlib dist_code [..512]
000952b0 358  Zlib length_code [..256]
000953b0 360  Zlib base_length [32.le.116]
00095428 362  Zlib base_dist [32.le.120]
0005c159 568  classical random incrementer 0x343FD 0x269EC3 [32.le.8&]
00042c84 855  Generic bitmask table [32.le.128]
00096ed0 1163 DES permuted choice table (key) [..56]
00096f18 1164 DES permuted choice key (table) [..48]
00097028 1314 RawDES sbox1 [32.le.256]
00097128 1316 RawDES sbox2 [32.le.256]
00097228 1318 RawDES sbox3 [32.le.256]
00097328 1320 RawDES sbox4 [32.le.256]
00097428 1322 RawDES sbox5 [32.le.256]
00097528 1324 RawDES sbox6 [32.le.256]
00097628 1326 RawDES sbox7 [32.le.256]
00097728 1328 RawDES sbox8 [32.le.256]
00094a68 1525 zinflate_lengthExtraBits [32.le.116]
00094ae0 1529 zinflate_distanceExtraBits [32.le.120]
00094add 1530 zinflate_distanceExtraBits [32.be.120]
00042c88 1811 bitmask [32.le.128]
00097018 1831 RNG (original numbers) [32.le.8&]
000b8868 2254 PADDINGXXPADDING [..16]
00042c84 2260 unlzx table_three [32.le.64]

46 signatures found in the file
```


Thanks in advance for anyone who can help 
[](http://img375.imageshack.us/img375/1026/xup111024x768.jpg/)
