## Post #1
- Username: stephanehl
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 20, 2008 2:25 am
- Post datetime: 2011-05-03T16:43:06+00:00
- Post Title: Decrypt psp .PGD

Please anyone can help me to decrypt this file with compression .PGD


Here is a sample.

```
http://www.megaupload.com/?d=WFYOZ1YB
```


Please i really need your help.

Best Regards,
Mensinhl
## Post #2
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-05-25T18:50:20+00:00
- Post Title: Decrypt psp .PGD

[PGD File header]:
Code:
0x00: 00 50 47 44 01 00 00 00 01 00 00 00 00 00 00 00 -> " PGD" and three bit fields that act as flags for version and encryption mode.
0x10: AES-128 bit hash key used for header decryption.
0x20: Generated hash from the 0x10 key.
0x30 - 0x50: Encrypted header of the PGD which when decrypted reveals a new hash key and four bit fields. The first is NULL, the second represents the decrypted data size, the third is the decrypting chunk size and the fourth is the data hash address.
0x60: File hash.
0x70: Hash generated from the sceIoIoctl key.
0x80: Encrypted hash generated from the sceIoIoctl key.
0x90: Data hash.
0xA0: Encrypted data hash.
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-05-26T14:20:54+00:00
- Post Title: Decrypt psp .PGD

load the game using JPCSP and flag in the option to save decrypted files or just install the game content so it will decrypt it for you...
## Post #4
- Username: ninuzzu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 20, 2011 6:33 pm
- Post datetime: 2011-11-25T15:22:07+00:00
- Post Title: Decrypt psp .PGD

> Reply from alon
>
> [PGD File header]:
Code:
0x00: 00 50 47 44 01 00 00 00 01 00 00 00 00 00 00 00 -> " PGD" and three bit fields that act as flags for version and encryption mode.
0x10: AES-128 bit hash key used for header decryption.
0x20: Generated hash from the 0x10 key.
0x30 - 0x50: Encrypted header of the PGD which when decrypted reveals a new hash key and four bit fields. The first is NULL, the second represents the decrypted data size, the third is the decrypting chunk size and the fourth is the data hash address.
0x60: File hash.
0x70: Hash generated from the sceIoIoctl key.
0x80: Encrypted hash generated from the sceIoIoctl key.
0x90: Data hash.
0xA0: Encrypted data hash.

using the info provided, can anyone write a bms script for this? thx
## Post #5
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-09-28T15:11:57+00:00
- Post Title: Decrypt psp .PGD

> Reply from ninuzzu
>
> alon wrote:[PGD File header]:
Code:
0x00: 00 50 47 44 01 00 00 00 01 00 00 00 00 00 00 00 -> " PGD" and three bit fields that act as flags for version and encryption mode.
0x10: AES-128 bit hash key used for header decryption.
0x20: Generated hash from the 0x10 key.
0x30 - 0x50: Encrypted header of the PGD which when decrypted reveals a new hash key and four bit fields. The first is NULL, the second represents the decrypted data size, the third is the decrypting chunk size and the fourth is the data hash address.
0x60: File hash.
0x70: Hash generated from the sceIoIoctl key.
0x80: Encrypted hash generated from the sceIoIoctl key.
0x90: Data hash.
0xA0: Encrypted data hash.

using the info provided, can anyone write a bms script for this? thxWish I had the great god resolve this issue, or the pointing direction
