## Post #1
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-07-31T11:40:31+00:00
- Post Title: Orcs Must Die 2! .rear language files.

Hello everyone!
I would like to make the Hungarian translation of this game. The game stores the string files in an xml in the data.zip file. But the game load the string from a data/langfilename.rear file. 
If someone can make an xml-rear or a rear exporter/importer it would be great. I have some .rear files if needed. 

Thanks for any helpers!
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-09-07T08:54:36+00:00
- Post Title: Orcs Must Die 2! .rear language files.

I'm also interested.

I would like to know what these green bytes are. RIPEMD160/SHA-1 checksum? Because every lang file has different values there and even change of 1 byte after that green area makes data validation check error.

(4 blue bytes are text block length)

And signsrch report of main executable:

```
  --------------------------------------------
  0080e920 31   Adler CRC32 (0x191b3141) [32.le.1024]
  0080f920 32   Adler CRC32 (0x191b3141) [32.be.1024]
  0080ed20 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  0080fd20 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  0080f120 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  00810120 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  0082caa0 135  libavutil ff_log2_tab [..256]
  0083b250 145  SHA256 Hash constant words K (0x428a2f98) [32.le.256]
  0083b350 149  Hash constant words K for SHA-384 and SHA-512 [64.le.640]
  0083afa8 165  AES Rijndael S / ARIA S1 [..256]
  0083b0a8 166  AES Rijndael Si / ARIA X1 [..256]
  0083b1a8 185  Rijndael rcon [32.le.40]
  0085cd78 186  Rijndael rcon [32.be.40]
  0044bbf6 307  SHA1 / SHA0 / RIPEMD-160 initialization [32.le.20&]
  00811860 357  Zlib dist_code [..512]
  00811a60 358  Zlib length_code [..256]
  00811b60 360  Zlib base_length [32.le.116]
  00811bd8 362  Zlib base_dist [32.le.120]
  0082f8c0 384  Jpeg dct 14 bit aanscales [16.le.128]
  0082fa50 388  Jpeg dct AA&N scale factor [double.le.64]
  008156b0 815  libavcodec ff_zigzag_direct [..64]
  0082cda0 855  Generic bitmask table [32.le.128]
  00817a10 1228 rfc3548 Base 64 Encoding with URL and Filename Safe Alphabet [..62]
  00817a10 1237 B64EncodeTable [..64]
  005f2b82 1287 RIPEMD-128 InitState [32.le.16&]
  0040e401 1483 TEA1_DS [32.le.4]
  00811218 1525 zinflate_lengthExtraBits [32.le.116]
  00811290 1529 zinflate_distanceExtraBits [32.le.120]
  0081128d 1530 zinflate_distanceExtraBits [32.be.120]
  00815850 1730 Electronic Arts TQI base_table2 [..64]
  0087b58a 1767 anti-debug: IsDebuggerPresent [..17]
  0082cd20 1810 bitmask [32.le.128]
  0082f598 2094 libavcodec ff_mjpeg_val_ac_luminance [..162]
  0082f4c8 2095 libavcodec ff_mjpeg_val_ac_chrominance [..162]
  00d11f64 2253 PADDINGXXPADDING [..16]
  0082cda0 2259 unlzx table_three [32.le.64]
  0082cd93 2271 compression algorithm seen in the game DreamKiller [32.le.12&]
  0081ed7f 2272 compression algorithm seen in the game DreamKiller [32.be.12&]

- 38 signatures found in the file

```

UPDATE: I hate, what I find answer right after I asked publicly    It's a SHA-1 checksum.
## Post #3
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2013-07-19T10:01:00+00:00
- Post Title: Orcs Must Die 2! .rear language files.

I'm still looking for a tool, to create a lang file. If any pro can take a look on it, it would be very nice. Because now i don't even know, if it is a very hard codec file, or just need some minor tricks just nobody cares. If anyone could help me in this, thank you!
## Post #4
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2014-01-24T14:05:28+00:00
- Post Title: Orcs Must Die 2! .rear language files.

nothing new?
## Post #5
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2014-01-27T19:02:39+00:00
- Post Title: Orcs Must Die 2! .rear language files.

Nothing. Sadly.
