## Post #1
- Username: ScorpyX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 16, 2011 12:38 pm
- Post datetime: 2012-04-03T03:28:55+00:00
- Post Title: [PC] Death Road (*.xbin)

Hello Guys - I would like to Mod the game Death Road ([video](http://www.youtube.com/watch?v=1p4g4Gf10xc))
but most of game files have compressed.. things.. or something

All this files have file extension *.xbin
this is small txt (i think..) file ([version.xbin](http://www.2shared.com/file/wirF419D/version.html)) in root directory

[](http://www.2shared.com/file/wirF419D/version.html)
(click on image for download file)

Anyone can help me and say what is this compress method?.. or any other words..

ps. this is can be texture dds-file ([sample.xbin](http://www.2shared.com/file/ESFlH1iy/sample.html))
this is can be some text script file ([menu.xbin](http://www.2shared.com/file/90CoZKPm/menu.html))
.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-03T19:50:21+00:00
- Post Title: [PC] Death Road (*.xbin)

Not compressed. XOR'ed by Key 1024 (0x400). Algo 0048B100 (SKIDROW version)

```
0x90, 0x07, 0x6C, 0xFD, 0x58, 0x24, 0xFC, 0x97, 0x95, 0x2C, 0x0B, 0xB8, 0x25, 0x9E, 0x4C,
0xF9, 0xF8, 0xD0, 0xC1, 0x1C, 0x15, 0xAD, 0x24, 0x06, 0x3C, 0x5A, 0xF7, 0x19, 0xD0, 0xB0,
0x39, 0x68, 0x33, 0xF7, 0x25, 0x45, 0xC5, 0x53, 0xDB, 0x7E, 0x02, 0x1D, 0x90, 0xAF, 0x38,
0x31, 0x03, 0xCF, 0x8B, 0xAE, 0xB4, 0x3A, 0x59, 0xE6, 0x53, 0xAB, 0x4B, 0xCE, 0x58, 0x10,
0xFC, 0x2D, 0x2E, 0xBC, 0xBB, 0x81, 0x8A, 0xB6, 0x5E, 0x2D, 0x49, 0x86, 0xE1, 0x4F, 0x29,
0x60, 0x59, 0xEB, 0xCA, 0x89, 0xE5, 0x18, 0x99, 0x00, 0xE1, 0xFB, 0x24, 0x6C, 0xF4, 0x6A,
0x51, 0x99, 0x93, 0x20, 0xB6, 0x29, 0x2E, 0x3C, 0xF9, 0xFA, 0x4F, 0x56, 0xBE, 0xFC, 0x4C,
0x8B, 0x8D, 0x9D, 0x78, 0xAC, 0x92, 0x9D, 0xCB, 0xBE, 0x67, 0x69, 0x56, 0x51, 0x38, 0x90,
0x14, 0x11, 0xF3, 0xA0, 0x22, 0xE4, 0xE7, 0x6C, 0xEF, 0xAB, 0x45, 0x68, 0x11, 0x03, 0x5E,
0x30, 0x49, 0xEA, 0x0F, 0x31, 0x85, 0xDE, 0x48, 0xB6, 0xB3, 0x3A, 0xDB, 0xB4, 0x44, 0x2E,
0x68, 0xFB, 0x90, 0x51, 0x12, 0xD0, 0x7D, 0x05, 0x3B, 0x82, 0xB5, 0xA6, 0x38, 0xF0, 0x9A,
0x77, 0x11, 0xE4, 0xB1, 0x3A, 0x4D, 0xBB, 0x7E, 0x37, 0x10, 0x10, 0x6F, 0x64, 0xFD, 0x70,
0x23, 0x2A, 0xA9, 0x1C, 0x85, 0xAC, 0xA4, 0x5D, 0xF1, 0x5D, 0xCF, 0x23, 0x6B, 0xD0, 0x03,
0x76, 0x2D, 0x54, 0xC9, 0x99, 0x5F, 0xCD, 0xB9, 0xFA, 0x49, 0xF9, 0x3F, 0x66, 0x95, 0x8C,
0xA2, 0xC3, 0x8C, 0x2B, 0x73, 0x0D, 0x07, 0x9D, 0x49, 0xB2, 0x2A, 0x07, 0x05, 0x91, 0x34,
0x37, 0x90, 0xA9, 0xEF, 0xA0, 0xFF, 0x80, 0xBE, 0xB4, 0xA6, 0xC0, 0x12, 0xB9, 0x82, 0xFD,
0x16, 0xBF, 0x8A, 0x72, 0xB8, 0x50, 0x82, 0x84, 0xF4, 0x81, 0xA6, 0x97, 0x2E, 0x7F, 0x9E,
0x41, 0xC0, 0x78, 0x3F, 0xA2, 0xBE, 0x9B, 0xBC, 0x84, 0xFC, 0x71, 0x26, 0x14, 0xE2, 0x8B,
0x37, 0xAA, 0x05, 0xF4, 0xC7, 0x9C, 0xEC, 0x72, 0x4A, 0x0F, 0x8C, 0xC4, 0x0A, 0x63, 0x7E,
0x72, 0xF5, 0x9B, 0xC2, 0x23, 0x67, 0xA5, 0x13, 0xCA, 0x78, 0x73, 0x4E, 0xCD, 0xB5, 0x3E,
0xCE, 0xAF, 0xC7, 0x2B, 0x49, 0x18, 0xCD, 0x75, 0xE2, 0x25, 0x80, 0xCE, 0x2E, 0x17, 0xFD,
0xCE, 0x42, 0x32, 0x98, 0x6F, 0x1D, 0x62, 0x28, 0x2E, 0xA8, 0x49, 0x87, 0xEA, 0x63, 0x3D,
0x27, 0xC0, 0xC3, 0x14, 0xDF, 0x47, 0xB7, 0x62, 0x1E, 0xE4, 0xBF, 0x22, 0x15, 0x9B, 0x02,
0xDB, 0xD5, 0x80, 0x7B, 0x85, 0xCE, 0xDF, 0x9D, 0x23, 0x61, 0xA3, 0xC0, 0x41, 0x3A, 0x1B,
0x80, 0x10, 0xF6, 0x61, 0x3A, 0x27, 0x05, 0xD4, 0x8C, 0xB2, 0x63, 0x28, 0x27, 0x02, 0xC9,
0xC5, 0x3D, 0xC8, 0xD2, 0x52, 0xBE, 0xC4, 0xB8, 0x23, 0x18, 0xDE, 0x2D, 0xE2, 0x6F, 0x93,
0x3B, 0xFA, 0xD7, 0x1D, 0xF5, 0x09, 0xFC, 0xD1, 0xB3, 0x62, 0x7F, 0xC9, 0xD4, 0x1F, 0x80,
0xA7, 0x86, 0x00, 0x7D, 0x47, 0x55, 0xA7, 0x01, 0xC2, 0x55, 0x34, 0xE8, 0x48, 0xC4, 0x82,
0xF6, 0x86, 0x7F, 0x92, 0x01, 0x3A, 0x4A, 0xAC, 0x04, 0x5E, 0xB3, 0x45, 0x26, 0x8F, 0x65,
0x8D, 0xA0, 0xD2, 0xAF, 0xDA, 0x69, 0x57, 0xE7, 0x0E, 0x2C, 0x31, 0x70, 0x0D, 0x17, 0xE7,
0x7D, 0x98, 0x2B, 0x43, 0x07, 0x8A, 0x04, 0x9E, 0x91, 0x00, 0x4D, 0x19, 0x7A, 0x97, 0x06,
0x94, 0x50, 0xF5, 0x9D, 0xBC, 0x46, 0x5C, 0x49, 0xFA, 0xC5, 0x85, 0xD9, 0x06, 0x2C, 0x75,
0xF6, 0x48, 0xCF, 0x30, 0x2C, 0x0B, 0x84, 0x1B, 0x64, 0x87, 0xD1, 0xA1, 0x65, 0x7E, 0x25,
0x44, 0x8A, 0x0B, 0x50, 0xB4, 0x82, 0x8B, 0x60, 0x96, 0x28, 0x0E, 0x6C, 0xF3, 0x45, 0x10,
0x13, 0xA8, 0xF1, 0x0D, 0x5F, 0xE6, 0x7E, 0xC7, 0xC8, 0x0C, 0x8D, 0x28, 0x78, 0x19, 0x69,
0x4D, 0xDE, 0x32, 0x32, 0x21, 0xE3, 0x0F, 0xB2, 0xE4, 0x7C, 0x23, 0xDB, 0xA5, 0xD5, 0x45,
0x36, 0x10, 0x7D, 0x17, 0x37, 0xFE, 0xB3, 0xAF, 0x2C, 0x8D, 0xE6, 0x81, 0x50, 0x5A, 0xDA,
0xAA, 0xAE, 0x98, 0x40, 0x14, 0x3F, 0x56, 0x71, 0x64, 0x06, 0x31, 0xC6, 0xC5, 0x5E, 0xEE,
0x36, 0xA2, 0xB0, 0xFC, 0xD3, 0xB3, 0xCA, 0x6C, 0xC0, 0xE6, 0x3C, 0x8D, 0xCB, 0x6D, 0xD5,
0x53, 0x21, 0xA8, 0x89, 0xD2, 0x6E, 0x68, 0x52, 0x64, 0x3A, 0x95, 0xA8, 0xB7, 0x77, 0x6A,
0x42, 0xBF, 0x96, 0x5B, 0x8E, 0x28, 0x95, 0x0E, 0x1F, 0xB5, 0x33, 0xE4, 0x1C, 0x2C, 0x1D,
0xEA, 0xFE, 0x82, 0x07, 0xFD, 0x45, 0x66, 0x54, 0xF5, 0x0C, 0xB9, 0xE1, 0x35, 0x9E, 0x73,
0x9E, 0x03, 0x15, 0x69, 0x35, 0x98, 0x26, 0x05, 0x6D, 0x3B, 0x89, 0x03, 0x9A, 0x03, 0x2D,
0x95, 0xE6, 0x46, 0xD0, 0xED, 0x79, 0xFF, 0x78, 0x6A, 0x37, 0x1A, 0x2F, 0xB1, 0x37, 0x7D,
0x72, 0xB6, 0x35, 0x1A, 0x11, 0x2D, 0xFD, 0x5E, 0x71, 0x40, 0x8E, 0xDA, 0x13, 0x04, 0x17,
0x97, 0xCE, 0x9A, 0x7B, 0x0D, 0x6E, 0x1B, 0x7E, 0xFE, 0x61, 0x64, 0x61, 0x85, 0xD9, 0x5A,
0xFE, 0x62, 0xCA, 0x61, 0x0D, 0xB2, 0x25, 0xDA, 0x6B, 0x29, 0xDB, 0x3D, 0xB0, 0xCE, 0x24,
0x65, 0xA1, 0x8F, 0x04, 0x63, 0x19, 0x46, 0x2A, 0x23, 0x39, 0xB1, 0x0B, 0x07, 0xD2, 0x97,
0xED, 0x6F, 0xFF, 0xC9, 0xB8, 0xE3, 0xE6, 0x67, 0xF2, 0x0A, 0xAC, 0x5F, 0xAA, 0x36, 0x1D,
0x01, 0x7D, 0xC2, 0xF2, 0x10, 0xD2, 0x10, 0x4D, 0x56, 0xF9, 0x7F, 0x3D, 0x36, 0xA8, 0x35,
0x48, 0xEA, 0xC5, 0xE5, 0x6F, 0x56, 0x31, 0x04, 0xFD, 0x6F, 0x0F, 0xDE, 0x80, 0x07, 0x42,
0x90, 0xBB, 0x9B, 0xEA, 0x19, 0x03, 0x0A, 0x88, 0xEA, 0xC7, 0xDA, 0x9C, 0xB3, 0xBF, 0xB5,
0x01, 0x81, 0xD2, 0x71, 0xA6, 0xC7, 0x8B, 0x50, 0xA3, 0x8C, 0x98, 0x90, 0xA5, 0x62, 0x3C,
0xEB, 0x88, 0xF8, 0xC6, 0xA1, 0xD9, 0xF4, 0xAC, 0xF6, 0x15, 0x80, 0x18, 0x76, 0xB2, 0xF6,
0x05, 0xF6, 0x55, 0x86, 0x42, 0xE3, 0x0E, 0x63, 0x0B, 0x8E, 0xB3, 0x3E, 0x46, 0x45, 0xE8,
0x6F, 0xD3, 0x23, 0x66, 0x07, 0xCB, 0x91, 0x83, 0xA3, 0x8E, 0x5C, 0x89, 0x53, 0xC2, 0xCD,
0xBA, 0x0B, 0x66, 0x57, 0xFF, 0xE8, 0x4E, 0x6D, 0x63, 0xD3, 0x25, 0xB1, 0xCE, 0xBA, 0x76,
0x13, 0x62, 0x46, 0x4A, 0xF1, 0xEB, 0x24, 0x9B, 0xBF, 0x7E, 0xD0, 0xA4, 0x78, 0xEF, 0x9F,
0x5E, 0x8D, 0xCE, 0xA5, 0x8F, 0xDA, 0x90, 0x69, 0xBA, 0x4D, 0x2A, 0xF4, 0xCC, 0x14, 0x62,
0x80, 0xFB, 0x2E, 0xEA, 0x9C, 0xA7, 0x97, 0xC2, 0x2A, 0x45, 0xFC, 0xF9, 0xE3, 0x54, 0xB5,
0xF1, 0x23, 0x4E, 0x1C, 0x33, 0x2B, 0xA3, 0xAD, 0xD8, 0x47, 0x66, 0x15, 0xE6, 0x25, 0xE6,
0x18, 0xB7, 0xA4, 0x08, 0x03, 0xD2, 0xFF, 0x4C, 0xB0, 0xA8, 0x7F, 0xB6, 0xE5, 0x70, 0x3D,
0x07, 0x98, 0x19, 0x49, 0x4A, 0x5F, 0x9B, 0xC2, 0x68, 0x8A, 0xAC, 0x29, 0xDC, 0xBE, 0xE9,
0xC2, 0x5C, 0x36, 0x43, 0x33, 0x04, 0x78, 0x30, 0xAE, 0xFB, 0x66, 0x50, 0x0C, 0xE1, 0xC1,
0xB1, 0x61, 0xEF, 0x98, 0x03, 0x65, 0xE2, 0x5B, 0x2C, 0x6B, 0xDA, 0x7C, 0xCD, 0x66, 0x60,
0xE3, 0xEB, 0xF2, 0x48, 0x95, 0x02, 0x0A, 0x19, 0xB6, 0x90, 0xAE, 0x93, 0xB6, 0xFF, 0x3D,
0x40, 0x68, 0x5E, 0x16, 0x03, 0x13, 0x8C, 0x35, 0x29, 0xB6, 0x11, 0x07, 0x88, 0xE2, 0x38,
0x31, 0x5C, 0x17, 0x14, 0x85, 0xD1, 0xC0, 0x3C, 0x8A, 0x0A, 0x9B, 0x82, 0xDD, 0x70, 0x80,
0xD5, 0x2C, 0xE4, 0xF8};

```


```
{
  signed int v2; // ebx@1
  int v3; // esi@1
  int v4; // edi@1
  signed int v5; // eax@1

  v2 = a2;
  LOBYTE(a2) = a2
             + ((signed int)(a2 + ((unsigned __int64)(-2139062143i64 * a2) >> 32)) >> 7)
             + ((unsigned int)(a2 + ((unsigned __int64)(-2139062143i64 * a2) >> 32)) >> 31);
  BYTE1(a2) = v2
            + 93
            * (((signed int)((unsigned __int64)(210795941i64 * v2) >> 32) >> 3)
             + ((unsigned int)((unsigned __int64)(210795941i64 * v2) >> 32) >> 31));
  BYTE2(a2) = v2
            - 119
            * (((signed int)((unsigned __int64)(1154949189i64 * v2) >> 32) >> 5)
             + ((unsigned int)((unsigned __int64)(1154949189i64 * v2) >> 32) >> 31));
  v3 = 0;
  BYTE3(a2) = v2 % 9;
  v4 = 0;
  sub_53030F("XOR buffer: BufferSize: %d  KeySize: %d\r\n", v2);
  v5 = 1;
  for ( *(_BYTE *)a1 ^= a2 ^ sz_Key[0]; v5 != v2; *(_BYTE *)(v5 + a1 - 1) ^= sz_Key[v3] ^ *((_BYTE *)&a2 + v4) )
  {
    v3 = (v3 + 1) % 1024;
    v4 = (v4 + 1) % 4;
    ++v5;
  }
  return 0;
}
```
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-06-21T11:06:08+00:00
- Post Title: [PC] Death Road (*.xbin)

Tool [here](http://forum.xentax.com/viewtopic.php?f=32&t=9123)