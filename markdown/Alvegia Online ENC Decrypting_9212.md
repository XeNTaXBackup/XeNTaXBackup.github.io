## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-06T01:39:07+00:00
- Post Title: Alvegia Online ENC Decrypting

All resource stored in default ZIP and encrypted by XOR + CRC32. All files have extension .enc

Algo:

```
	0x97, 0xC3, 0x95, 0x77, 0x2D, 0xFB, 0x45, 0x33, 0xB2, 0xDD, 0x35, 0x89,
	0x22, 0x0F, 0x3F, 0x31, 0x78, 0xD2, 0x4E, 0xFC, 0x35, 0xBD, 0x47, 0x5C,
	0x81, 0x99, 0x4C, 0x9B, 0xD7, 0x9F, 0x4B, 0x5A, 0xEB, 0xBE, 0x75, 0x7A,
	0xE0, 0x2E, 0x43, 0x02, 0x93, 0xBF, 0x9C, 0x3B, 0xCB, 0xBA, 0x48, 0x8C,
	0xF1, 0x8D, 0xF5, 0x7B, 0x78, 0x27, 0x40, 0x0E, 0xAA, 0xFC, 0x5C, 0x38,
	0x74, 0x96, 0x2E, 0x3B, 0x0C, 0xC4, 0x13, 0x95, 0xF9, 0x57, 0x42, 0x29,
	0xA0, 0x90, 0x8D, 0xE2, 0xA6, 0x26, 0x03, 0xA2, 0xFC, 0x63, 0xDF, 0x3D,
	0x39, 0xCE, 0x4E, 0x01, 0xB8, 0xCD, 0xB8, 0xA3, 0x9E, 0xD4, 0xDC, 0x82,
	0x02, 0xC0, 0xA5, 0xD8, 0xD8, 0xDB, 0x46, 0x69, 0xA8, 0x7B, 0x71, 0xE1,
	0x9C, 0xB7, 0xFF, 0xF0, 0x06, 0xE6, 0x43, 0xE3, 0x2E, 0x09, 0x48, 0xEF,
	0xBB, 0xBC, 0x4F, 0xE3, 0x87, 0xD9, 0xFF, 0x5F};
```


```

typedef unsigned char _BYTE;

int __stdcall AlvegiaDecrypt(signed int a1, int a2, int a3)
{
  int v3;
  int v4;
  int v5;
  int result;
  char v7;

  v3 = a3;
  v4 = a2;
  v5 = a1 % 8;
  result = a1 & 0x7F;
  while ( v3 > 0 )
  {
    --v3;
    v7 = ROL(*(_BYTE *)v4, v5);
    ++result;
    ++v4;
    *(_BYTE *)(v4 - 1) = AlvegiaKey[result] ^ v7;
    if ( (unsigned int)result >= 0x80 )
      result = 0;
    ++v5;
    if ( v5 >= 8 )
      v5 = 0;
  }
  return result;
}
```


a1 = Calculated CRC32 hash for file name
a2 = Buffer
a3 = Size

How it work (Example):

Game opening file inside archive -> resources.xml.enc and eliminate extension from full filename .enc = resources.xml
Next this file name resources.xml passes through the CRC32 and calculate hash = A40D64DF

And last phase - AlvegiaDecrypt(0xA40D64DF,buffer,size)

PS: ROL (Rotate left) maybe not work correctly dunno. Maybe useful to someone and it seems nothing hard
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-06T02:37:51+00:00
- Post Title: Alvegia Online ENC Decrypting

cool the models look interesting.
got the down-loader from their site.
downloaders.alvegia.ru/InstallAlvegiaOnline.exe
this is a torrent client that downloads this torrent
alvegia-client.s3.amazonaws.com/0.0.1.1057_v4/torrent/AlvegiaOnlineData_0_0_1_1057_lt_0_15_9_0.torrent
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-06T12:39:23+00:00
- Post Title: Alvegia Online ENC Decrypting

Me didn't impress
