## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-23T02:27:54+00:00
- Post Title: Mabinogi Heros

This game uses the half life engine and would be great to have access to the resources in these archives.
I am confused a little on the file structure and what compression type is used it is definitely zlib but I am not sure what else there is.

I found this in one of the dll files.

```

Signsrch 0.1.5a
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
  optimized search function from Andrew http://www.team5150.com/~andrew/

- open file "C:\Nexon\Heroes\ko-KR\dbghelp.dll"
- 1080672 bytes allocated
- load signatures
- open file C:\signsrch\signsrch.sig
- 1772170 bytes allocated for the signatures
- 2263 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  0000c500 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  00106676 188  SSH RSA id-sha1 OBJ.ID. oiw(14) secsig(3) algorithms(2) 26 [..15]

- 2 signatures found in the file


```


```
goto 0
for i = 0 < files
get HF long
get UNK1 long
get UNK2 long
get UNK3 long
get UNK4 short
get ZSIZE long
get ZSIZE long
get NSIZE long
getdstring NAME NSIZE
savepos OFFSET
clog NAME1 OFFSET ZSIZE SIZE
math OFFSET += ZSIZE
goto OFFSET
next i
```


I have attached a few sample files and all the dll's and main exe. the problem with the main exe is themida protection.
[http://www.MegaShare.com/1274323](http://www.MegaShare.com/1274323)
video
[http://www.youtube.com/watch?v=A6_dC9N7LoQ&e](http://www.youtube.com/watch?v=A6_dC9N7LoQ&e)
[](http://img29.imageshack.us/img29/9629/mabifinal.jpg)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-23T19:49:35+00:00
- Post Title: Mabinogi Heros

It might not be a protected exe it could just be some weird launcher that loads the exe I am not sure.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-23T22:58:45+00:00
- Post Title: Mabinogi Heros

I looked at some client dll files and found something interesting

```
- 6881280 bytes allocated
- load signatures
- open file c:\signsrch\signsrch.sig
- 1772170 bytes allocated for the signatures
- 2263 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  005ab528 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  00534a10 1693 ICE ice_smod [32.le.64]
  00534a50 1695 ICE ice_sxor [32.le.64]
  00534a90 1697 ICE ice_pbox [32.le.128]
  002208fc 1767 anti-debug: Dongle protection [..3]
  005ab1b0 1768 anti-debug: IsDebuggerPresent [..17]

- 6 signatures found in the file

```


and this in another file.

```

Signsrch 0.1.5a
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
  optimized search function from Andrew http://www.team5150.com/~andrew/

- open file "C:\Nexon\Heroes\ko-KR-x-TEST\bin\engine.dll"
- 6643712 bytes allocated
- load signatures
- open file c:\signsrch\signsrch.sig
- 1772170 bytes allocated for the signatures
- 2263 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  0051bb40 73   CRC-16-IBM poly 0x8005 [16.le rev.512]
  0050c418 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  005e0460 121  MS ADPCM AdaptationTable [32.le.64]
  005e0460 127  Creative ADPCM table [32.le.32]
  005e8d18 382  Bzip2 BZ2_rNums [32.le.2048]
  00542a88 384  Jpeg dct 14 bit aanscales [16.le.128]
  00542b08 388  Jpeg dct AA&N scale factor [double.le.64]
  005d3c70 551  Windows CryptCreateHash [..16]
  005d3c04 552  Windows CryptImportKey [..15]
  005d3c60 553  Windows CryptHashData [..14]
  005d3c3a 555  Windows CryptDeriveKey [..15]
  005d3ba6 556  Windows CryptDecrypt [..13]
  00207084 1483 TEA1_DS [32.le.4]
  0050c278 1525 zinflate_lengthExtraBits [32.le.116]
  0050c275 1526 zinflate_lengthExtraBits [32.be.116]
  0050c2f0 1529 zinflate_distanceExtraBits [32.le.120]
  0050c2ed 1530 zinflate_distanceExtraBits [32.be.120]
  00501ca0 1693 ICE ice_smod [32.le.64]
  00501ce0 1695 ICE ice_sxor [32.le.64]
  00501d20 1697 ICE ice_pbox [32.le.128]
  0050143c 1768 anti-debug: IsDebuggerPresent [..17]
  0051b978 2088 libavcodec libmp3lame sBitRates [32.le.360]
  00541340 2095 libavcodec ff_mjpeg_val_ac_luminance [..162]
  005413f8 2096 libavcodec ff_mjpeg_val_ac_chrominance [..162]
```


it seems to be using the ice encryption algorithm " I am guessing"
and apparently seems to be a more secure des.
so the only way to see the files is to find the key as brute force does not seem possible.
[http://www.darkside.com.au/ice/](http://www.darkside.com.au/ice/)
