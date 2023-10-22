## Post #1
- Username: Emir
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 10, 2010 5:37 pm
- Post datetime: 2013-10-26T10:37:17+00:00
- Post Title: What is this dds file pack format???

some game dds file packed

seem zlib , but not to work....
anyone help me to find the format?
[18000002.rar](https://xentaxbackup.github.io/file/6733_18000002.rar)
## Post #2
- Username: Emir
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 10, 2010 5:37 pm
- Post datetime: 2013-10-28T19:37:46+00:00
- Post Title: What is this dds file pack format???

any help?

Signsrch 0.1.6a
by Luigi Auriemma
e-mail: [aluigi@autistici.org](mailto:aluigi@autistici.org)
web:    aluigi.org
  optimized search function from Andrew [http://www.team5150.com/~andrew/](http://www.team5150.com/~andrew/)
  disassembler engine from Oleh Yuschuk

- open file "musicman.exe"
- 2144896 bytes allocated
- load signatures
- open file G:\MusicMan\D1XN\signsrch.sig
- 1774060 bytes allocated for the signatures
- 2278 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  001c1ed8 31   Adler CRC32 (0x191b3141) [32.le.1024]
  001c2ed8 32   Adler CRC32 (0x191b3141) [32.be.1024]
  001c22d8 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  001c32d8 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  001c26d8 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  001c36d8 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  001b97b8 142  ACSS reverse sbox [..256]
  0020a076 188  SSH RSA id-sha1 OBJ.ID. oiw(14) secsig(3) algorithms(2) 26 [..15
]
  001c4980 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]
  001c43b0 357  Zlib dist_code [..512]
  001c45b0 358  Zlib length_code [..256]
  001c46b0 360  Zlib base_length [32.le.116]
  001c4728 362  Zlib base_dist [32.le.120]
  001bd458 384  Jpeg dct 14 bit aanscales [16.le.128]
  001bd4d8 388  Jpeg dct AA&N scale factor [double.le.64]
  001f532e 550  Windows CryptAcquireContext [..21]
  001f531c 551  Windows CryptCreateHash [..16]
  001f530c 553  Windows CryptHashData [..14]
  001f52fa 555  Windows CryptDeriveKey [..15]
  001f52c2 556  Windows CryptDecrypt [..13]
  00109714 855  Generic bitmask table [32.le.128]
  001b97b8 1198 FFT and FHT routines rv_tbl [..128]
  001c3d68 1525 zinflate_lengthExtraBits [32.le.116]
  001c3df0 1529 zinflate_distanceExtraBits [32.le.120]
  001f4102 1767 anti-debug: IsDebuggerPresent [..17]
  00109718 1810 bitmask [32.le.128]
  001bd098 2094 libavcodec ff_mjpeg_val_ac_luminance [..162]
  001bd150 2095 libavcodec ff_mjpeg_val_ac_chrominance [..162]
  00209958 2253 PADDINGXXPADDING [..16]
  00109714 2259 unlzx table_three [32.le.64]
