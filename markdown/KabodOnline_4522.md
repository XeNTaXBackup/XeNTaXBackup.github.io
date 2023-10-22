## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-28T22:22:23+00:00
- Post Title: KabodOnline

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-05-29T00:36:36+00:00
- Post Title: KabodOnline

nif files.....*drool*

can't helpt with compression though, I just saw NIF shader in exe
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T10:27:35+00:00
- Post Title: KabodOnline

```
get DUMMY long
get DUMMY long
get FILES long
get INFO_SIZE long
savepos OFFSET
encryption 3des2 "\xEA\x89\xB6\x57\x6B\xC4\xAC\x28\x03\xFF\x3A\x97\x99\x9B\x52\x74" "\0\0\0\0\0\0\0\0"
log MEMORY_FILE OFFSET INFO_SIZE
encryption "" ""

comtype deflate
goto 16 MEMORY_FILE
for i = 0 < FILES
    getdstring NAME 0x104 MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE
    math SIZE *= ZSIZE
    math OFFSET += 2
    math ZSIZE -= 2
    clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-29T11:07:33+00:00
- Post Title: KabodOnline

it seems to work perfect on the config pack but there are 2 other pac files tools.pac and Kabod.pac it does not work on.

i got the files without names using offzip.


offzip.exe -a -z -15 C:\Downloads\KabodOnline\Kabod.pak C:\Downloads\KabodOnline\test 0x757C8
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T12:02:04+00:00
- Post Title: KabodOnline

for the others try the key "\xAB\xC4\xB4\xA3\x69\xB9\xE0\xC1\xE9\xCE\xAC\xC5\x5A\x9A\xF8\xAE"
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-29T12:05:52+00:00
- Post Title: KabodOnline

that worked on the tools pac there must be one last key.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T12:08:01+00:00
- Post Title: KabodOnline

no problem, place a breakpoint at offset 00546370 and the key is the first argument on the stack
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T12:09:58+00:00
- Post Title: KabodOnline

note that the key will change with different files and versions because the key is based on the content of the files.
I'm not interested in finishing the last part of the reversing
## Post #9
- Username: Emir
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 10, 2010 5:37 pm
- Post datetime: 2010-07-14T11:22:21+00:00
- Post Title: KabodOnline

Where is the 3des2 key to find out??

this game is newer version in 7/15 to CBT


Signsrch 0.1.5a
by Luigi Auriemma
e-mail: [aluigi@autistici.org](mailto:aluigi@autistici.org)
web:    aluigi.org
  optimized search function from Andrew [http://www.team5150.com/~andrew/](http://www.team5150.com/~andrew/)

- open file "kabod.exe"
- 2484736 bytes allocated
- load signatures
- open file D:\KabodOnline\signsrch.sig
- 1774060 bytes allocated for the signatures
- 2278 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  0021bde0 31   Adler CRC32 (0x191b3141) [32.le.1024]
  0021cde0 32   Adler CRC32 (0x191b3141) [32.be.1024]
  0021c1e0 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  0021d1e0 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  0021c5e0 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  0021d5e0 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  0021b9e0 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  0021c9e0 84   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.be rev.1024]
  0021fa50 145  SHA256 Hash constant words K (0x428a2f98) [32.le.256]
  0021fb50 149  Hash constant words K for SHA-384 and SHA-512 [64.le.640]
  00255f40 163  AES Rijndael Logtable [..256]
  00256040 164  AES Rijndael Alogtable [..256]
  00220760 165  AES Rijndael S / ARIA S1 [..256]
  00220860 166  AES Rijndael Si / ARIA X1 [..256]
  00220960 167  Rijndael Te0 (0xc66363a5U) [32.le.1024]
  00256340 168  Rijndael Te0 (0xc66363a5U) [32.be.1024]
  00220d60 169  Rijndael Te1 (0xa5c66363U) [32.le.1024]
  00256740 170  Rijndael Te1 (0xa5c66363U) [32.be.1024]
  00221160 171  Rijndael Te2 (0x63a5c663U) [32.le.1024]
  00256b40 172  Rijndael Te2 (0x63a5c663U) [32.be.1024]
  00221560 173  Rijndael Te3 (0x6363a5c6U) [32.le.1024]
  00256f40 174  Rijndael Te3 (0x6363a5c6U) [32.be.1024]
  00221960 176  Rijndael Td0 (0x51f4a750U) [32.le.1024]
  00257340 177  Rijndael Td0 (0x51f4a750U) [32.be.1024]
  00221d60 178  Rijndael Td1 (0x5051f4a7U) [32.le.1024]
  00257740 179  Rijndael Td1 (0x5051f4a7U) [32.be.1024]
  00222160 180  Rijndael Td2 (0xa75051f4U) [32.le.1024]
  00257b40 181  Rijndael Td2 (0xa75051f4U) [32.be.1024]
  00222560 182  Rijndael Td3 (0xf4a75051U) [32.le.1024]
  00257f40 183  Rijndael Td3 (0xf4a75051U) [32.be.1024]
  00222960 185  Rijndael rcon [32.le.40]
  00259440 186  Rijndael rcon [32.be.40]
  00135665 307  SHA1 / SHA0 / RIPEMD-160 initialization [32.le.20&]
  0021e028 357  Zlib dist_code [..512]
  0021e228 358  Zlib length_code [..256]
  0021e328 360  Zlib base_length [32.le.116]
  0021e3a0 362  Zlib base_dist [32.le.120]
  0013c1b4 855  Generic bitmask table [32.le.128]
  0021fe20 1163 DES permuted choice table (key) [..56]
  0021fe68 1164 DES permuted choice key (table) [..48]
  001374b2 1287 RIPEMD-128 InitState [32.le.16&]
  0021ff60 1314 RawDES sbox1 [32.le.256]
  00220060 1316 RawDES sbox2 [32.le.256]
  00220160 1318 RawDES sbox3 [32.le.256]
  00220260 1320 RawDES sbox4 [32.le.256]
  00220360 1322 RawDES sbox5 [32.le.256]
  00220460 1324 RawDES sbox6 [32.le.256]
  00220560 1326 RawDES sbox7 [32.le.256]
  00220660 1328 RawDES sbox8 [32.le.256]
  0021d9e0 1525 zinflate_lengthExtraBits [32.le.116]
  0021da58 1529 zinflate_distanceExtraBits [32.le.120]
  0021da55 1530 zinflate_distanceExtraBits [32.be.120]
  0025945c 1637 Noekeon Nessie round [32.le.68]
  00259459 1638 Noekeon Nessie round [32.be.68]
  0013c1b8 1810 bitmask [32.le.128]
  0021ff4c 1830 RNG (original numbers) [32.le.8&]
  0013c1b4 2259 unlzx table_three [32.le.64]

- 57 signatures found in the file
## Post #10
- Username: Emir
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 10, 2010 5:37 pm
- Post datetime: 2010-07-14T13:25:14+00:00
- Post Title: KabodOnline

I had Found the Key , Thank you very much!!!!
## Post #11
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-11T22:03:32+00:00
- Post Title: KabodOnline

somebody get extraction of Kabod.pak? because I can't get this files with tool found in net
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-12T14:38:45+00:00
- Post Title: KabodOnline

Is kabod.pak part of kabodonline?
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-12T16:37:29+00:00
- Post Title: KabodOnline

> Reply from finale00
>
> Is kabod.pak part of kabodonline?yes is the part where alocated files (models,textures,etc)
## Post #14
- Username: s25jin
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 15, 2011 1:11 am
- Post datetime: 2012-02-13T17:32:26+00:00
- Post Title: KabodOnline

i can't find Kabod.pak


,,,,,,,
Graphic.pak .........Graphic_BG1.pak.........Graphic_VEHICLE1.pak
maybe change filename..
