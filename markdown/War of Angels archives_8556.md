## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T03:47:58+00:00
- Post Title: War of Angels archives

Game site: [http://warofangels.gamigo.com/en/](http://warofangels.gamigo.com/en/)

Interface files: [http://www.mediafire.com/?blcbl8su89ayosy](http://www.mediafire.com/?blcbl8su89ayosy)
gamedata.head: [http://www.mediafire.com/?3blxyk9ntwncdf9](http://www.mediafire.com/?3blxyk9ntwncdf9)
Client: [http://www.mediafire.com/?qo2yhnm0v7rqzts](http://www.mediafire.com/?qo2yhnm0v7rqzts)

Here is what I've written down for the dat archive. It looks like if you see the sequence 0x E0 A4 25 3C, that is the start of a file. Maybe they don't use a file count.

The gamedata.head might be useful. It lists all of the archives and has some data there as well, but it follows the same scheme as below.

```
dword size
dword null
dword compress size
dword null
word length
char[length] path name

```


The file path is encrypted
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-15T10:02:04+00:00
- Post Title: War of Angels archives

Executable protected with Themida. Unpacked [here](http://www.progamercity.net/other-mmo/3317-dev-war-angels-themida-unpacked.html)

```
  --------------------------------------------
  005f80f8 31   Adler CRC32 (0x191b3141) [32.le.1024]
  005f90f8 32   Adler CRC32 (0x191b3141) [32.be.1024]
  005f84f8 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  005f94f8 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  005f88f8 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  005f98f8 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  004c7ee8 307  SHA1 / SHA0 / RIPEMD-160 initialization [32.le.20&]
  0073f529 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]
  005fa340 357  Zlib dist_code [..512]
  005fa540 358  Zlib length_code [..256]
  005fa640 360  Zlib base_length [32.le.116]
  005fa6b8 362  Zlib base_dist [32.le.120]
  00612ab0 855  Generic bitmask table [32.le.128]
  00e2fb30 1176 Vorbis FLOOR1_fromdB_LOOKUP [float.le.1024]
  00611170 1523 zinflate_lengthStarts [32.le.116]
  005f9cf8 1525 zinflate_lengthExtraBits [32.le.116]
  006111ed 1526 zinflate_lengthExtraBits [32.be.116]
  00611270 1527 zinflate_distanceStarts [32.le.120]
  005f9d80 1529 zinflate_distanceExtraBits [32.le.120]
  0108648f 1767 anti-debug: IsDebuggerPresent [..17]
  00e7630e 1795 anti-debug: Softice \\.\SICE [..9]
  00e76322 1796 anti-debug: Softice \\.\NTICE [..10]
  00e76317 1797 anti-debug: Softice \\.\SIWVID [..11]
  00612ab4 1810 bitmask [32.le.128]
  01088dec 2253 PADDINGXXPADDING [..16]
  00612460 2259 unlzx table_three [32.le.64]
```
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-09-05T18:12:22+00:00
- Post Title: War of Angels archives

I got files from it by using offzip -a
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-09-05T18:15:31+00:00
- Post Title: War of Angels archives

meshes start with MESH in header and animationos with ANIM. Havent we seen that before
