## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-07-20T07:39:11+00:00
- Post Title: [Request] KwonHo: The Hero of Fist encryption/compression

It is a closed down fighting MMO game but the client is still availiable at [Gameershell](http://www.gamershell.com/download_20419.shtml)(Only 260M)
the archives are paq, and the basic structure is:

```
dword		version
dword 		Num_Resource
dword		unknown		//when it is 0, the resource is direct store!

struct ResIndex {
   dword	length_Resource
   dword	offset_Resource
   dword	unknown
   byte[80]	encrypted_filename_and_something
}

And Resource data start right after the ResIndex table.
```


I had manage to unpacking the models(KH_B*,KH_C*) sound(KH_S*) Scripts(KH_U*) and Texture(KH_I*) files with filenames
Bones and models are supported in FatImporter S2 update already.

Unfortunelately, textures without filename are too hard to match with models!
And animations are somehow encrypted?

So I need help on cracking this archive. I am hoping at least to get the animation unpack.
Thank in advance!
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-08-13T06:09:12+00:00
- Post Title: [Request] KwonHo: The Hero of Fist encryption/compression

Try another look on this PAQ.
With signsrch get these!

- open file "C:\MySoftware\QuickBMS\signsrch016\KwonHoClient.exe"
- 2101248 bytes allocated
- load signatures
- open file C:\MySoftware\QuickBMS\signsrch016\signsrch.sig
- 1774060 bytes allocated for the signatures
- 2278 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  0046639a 289  MD5 digest [32.le.272&]
  0046651c 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]
  00543c87 357  Zlib dist_code [..512]
  00543c63 358  Zlib length_code [..256]
  00545d28 360  Zlib base_length [32.le.116]
  00545e70 362  Zlib base_dist [32.le.120]
  005dc39e 550  Windows CryptAcquireContext [..21]
  005dc404 551  Windows CryptCreateHash [..16]
  005dd310 552  Windows CryptImportKey [..15]
  005dc3f4 553  Windows CryptHashData [..14]
  005dc438 555  Windows CryptDeriveKey [..15]
  005dc44a 556  Windows CryptDecrypt [..13]
  00528d64 568  classical random incrementer 0x343FD 0x269EC3 [32.le.8&]
  00573570 855  Generic bitmask table [32.le.128]
  0056ac28 1176 Vorbis FLOOR1_fromdB_LOOKUP [float.le.1024]
  004ec89b 1228 rfc3548 Base 64 Encoding with URL and Filename Safe Alphabet [..62]
  004ec8af 1237 B64EncodeTable [..64]
  005ee004 1386 seed_SS0 [32.le.1024]
  005ee404 1388 seed_SS1 [32.le.1024]
  005ee804 1390 seed_SS2 [32.le.1024]
  005eec04 1392 seed_SS3 [32.le.1024]
  00548ce2 1523 zinflate_lengthStarts [32.le.116]
  00545d15 1525 zinflate_lengthExtraBits [32.le.116]
  005acaed 1526 zinflate_lengthExtraBits [32.be.116]
  00548d29 1527 zinflate_distanceStarts [32.le.120]
  00545e61 1529 zinflate_distanceExtraBits [32.le.120]
  005abf15 1530 zinflate_distanceExtraBits [32.be.120]
  005c955c 1810 bitmask [32.le.128]
  0054076c 1866 GameGuard files encryption public key [..84]
  005a0e83 1882 base64 map [..80]
  00af9560 2253 PADDINGXXPADDING [..16]
  0057369b 2259 unlzx table_three [32.le.64]

- 32 signatures found in the file

But can't found any zlibed!? Maybe encrypted!
Anyone can help to encrypted the paq, please!

For those paq without any compression/encryption, you can use thes bms to unpack them! And imported them with FatImporter.

```
# by Fatduck     July 2012
# http://aluigi.altervista.org/quickbms.htm

idstring "KHO1"
get VER long
get UKN1 long
get NUMRES word
get UKN2 word
set OFS_RES_START NUMRES
math OFS_RES_START *= 0x5C
math OFS_RES_START += 0x10
savepos OFSTBL
for i = 1 to NUMRES
   goto OFSTBL
   get LEN_RES long
   get OFS_RES long
   get UKN long
   if UKN != 0 then
      print "Unsupportted PAQ"
      cleanexit
   endif
   getdstring DMY 0x50
   savepos OFSTBL
   math OFS_RES += OFS_RES_START
   goto OFS_RES
   get HDR word
   get RES_NAME basename 
   if i < 10 then
      string RES_NAME += "_000"
   elif i < 100
      string RES_NAME += "_00"
   elif i < 1000
      string RES_NAME += "_0"
   else
      string RES_NAME += _
   endif
   string RES_NAME += i
   if HDR == 0x7368 then
      string RES_NAME += .msh
   elif HDR == 0x696E then
      string RES_NAME += .chr
   elif HDR == 0x6972 then
      string RES_NAME += .wav
   elif HDR == 0x4D42 then
      string RES_NAME += .bmp
   elif HDR == 0X4444 then
      string RES_NAME += .dds
   elif HDR == 0 then
      string RES_NAME += .tga
   elif HDR == 0xD8FF then
      string RES_NAME += .jpg
   elif HDR == 0x5089 then
      string RES_NAME += .jpg
   elif HDR == 0x3F3C then
      string RES_NAME += .xml
   elif HDR == 0x5746 then
      string RES_NAME += .swf
   else
      string RES_NAME += .dat
   endif
   log RES_NAME OFS_RES LEN_RES
next i
```
## Post #3
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-08-18T21:46:47+00:00
- Post Title: [Request] KwonHo: The Hero of Fist encryption/compression

simple PAQ unpacker
run it from a folder with PAQ files you want to unpack. it will decrypt and save the files with names.
also you can find the source code in the same archive.
cheers
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-19T06:03:36+00:00
- Post Title: [Request] KwonHo: The Hero of Fist encryption/compression

script for QuickBMS:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "KHO1"
getdstring DUMMY 8
get FILES short
math INFO_OFF = 0x10
math BASE_OFF = FILES
math BASE_OFF *= 0x5c
math BASE_OFF += INFO_OFF
for i = 0 < FILES
    goto INFO_OFF
    getdstring KEY 0xc
    log MEMORY_FILE INFO_OFF 0xc
    math INFO_OFF += 0xc
    encryption rc4 KEY "" 0 0xc
    append
    log MEMORY_FILE INFO_OFF 0x50
    append
    encryption "" ""
    math INFO_OFF += 0x50

    goto 0 MEMORY_FILE
    get SIZE long MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get CRYPT long MEMORY_FILE
    getdstring NAME 0x50 MEMORY_FILE

    if CRYPT != 0
        goto 0 MEMORY_FILE
        getdstring KEY 0x5c MEMORY_FILE
        encryption rc4 KEY "" 0 0x5c
    endif
    math OFFSET += BASE_OFF
    log NAME OFFSET SIZE
    encryption "" ""
next i
```
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-08-19T08:38:23+00:00
- Post Title: [Request] KwonHo: The Hero of Fist encryption/compression

Thanks b0ny and aluigi, both work great!

Will update my FatImporter soon!
