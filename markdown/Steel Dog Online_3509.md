## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-25T20:39:39+00:00
- Post Title: Steel Dog Online

I have been trying to figure out this archive format and it has me stumped.
this is what I have done so far witch I think is most of the format.

```
goto 0x10
get OFFTBL1 long # 35A28
get NULL long
get OFFTBL2 long # 35848
get NULL long
get FILES2 long
get FILES long

#OFFTBL1
#0x18 x 0x16
for j = 0 < FILES2
get OFFSET long
get NULL long
get ZSIZE long
get NULL long
get SIZE long
get NULL long
next j

#OFFTBL2
for k = 0 < FILES
getdstring UNK 0x10
get OFFSET long
get NULL long
next k

#8th entry in OFFTBL2
#Name table
for l = 0 < FILES
getdstring UNK 0x10
get 1 long #indicates start of name
getdstring NAME X #little edian
get null long #terminates name string
next l


for i = 0 < FILES
clog NAME OFFSET SIZE ZSIZE
next i

```

also each compressed file starts with 0x4 bytes that all seem different followed bye 78 5E
I have attached the main exe and some sample small archives if anyone can help me figure out what kind of compression this is.
I tried to re create this archive with 1 file in it but I can not get it to decompress.
[http://www.MegaShare.com/949451](http://www.MegaShare.com/949451)
here is an exe scan

```

Signsrch 0.1.4
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
  optimized search function from Andrew http://www.team5150.com/~andrew/

- open file "F:\Program Files\Steeldog_alpha\gear.exe"
- 5005312 bytes allocated
- load signatures
- open file C:\signsrch\signsrch.sig
- 1294834 bytes allocated for the signatures
- 1869 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  003b78b8 31   Adler CRC32 (0x191b3141) [32.le.1024]
  003b88b8 32   Adler CRC32 (0x191b3141) [32.be.1024]
  003b7cb8 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  003b8cb8 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  003b80b8 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  003b90b8 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  003b74b8 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  003b84b8 84   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.be rev.1024]
  0042d8df 188  SSH RSA id-sha1 OBJ.ID. oiw(14) secsig(3) algorithms(2) 26 [..15]
  003b70c8 357  Zlib dist_code [..512]
  003b72c8 358  Zlib length_code [..256]
  003b73c8 359  Zlib base_length [32.le.116]
  003b7440 361  Zlib base_dist [32.le.120]
  004a7dd2 549  Windows CryptAcquireContext [..21]
  004a7eea 550  Windows CryptCreateHash [..16]
  004a7dc0 551  Windows CryptImportKey [..15]
  004a7eda 552  Windows CryptHashData [..14]
  004a7efc 554  Windows CryptDeriveKey [..15]
  00193e19 567  classical random incrementer 0x343FD 0x269EC3 [32.le.8&]
  003b9690 862  Generic bitmask table [32.le.128]
  003b73c8 1085 Rar29 LDecode [32.le.112]
  004b8880 1188 Vorbis FLOOR1_fromdB_LOOKUP [float.le.1024]
  0020686e 1303 RIPEMD-128 InitState [32.le.16&]
  004a9780 1402 seed_SS0 [32.le.1024]
  004a9b80 1404 seed_SS1 [32.le.1024]
  004a9f80 1406 seed_SS2 [32.le.1024]
  004aa380 1408 seed_SS3 [32.le.1024]
  003b9cc8 1539 zinflate_lengthStarts [32.le.116]
  003b6a80 1541 zinflate_lengthExtraBits [32.le.116]
  003b6a7d 1542 zinflate_lengthExtraBits [32.be.116]
  003b9dc8 1543 zinflate_distanceStarts [32.le.120]
  003b6b08 1545 zinflate_distanceExtraBits [32.le.120]
  000ab6e6 1783 anti-debug: Dongle protection [..3]
  004a7832 1784 anti-debug: IsDebuggerPresent [..17]
  003b9694 1827 bitmask [32.le.128]

- 35 signatures found in the file
```


NCSOFT seems to be using this format in their games.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-26T12:02:56+00:00
- Post Title: Steel Dog Online

Well all indications point to zlib, don't they?
Though that 78 5E is quite uncommon.

78 01 - No Compression/low 
78 9C - Default Compression 
78 DA - Best Compression
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-26T19:28:29+00:00
- Post Title: Steel Dog Online

I though it would be zlib but when I tried quickbms on the archive I just get errors and I even tried using a hex editor to create all the parts of the archive but I could not get that type of zlib to decompress.
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-26T21:46:47+00:00
- Post Title: Steel Dog Online

They are zlib compression! I can uncompress them manually!
Try offzip should work!
