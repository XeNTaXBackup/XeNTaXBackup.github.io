## Post #1
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-12-18T17:36:21+00:00
- Post Title: [HELP]Compiling this C script...URGENT

I need it badly guys..but i dont have a compiler installed to compile this this..

Its for mhp3

named tpu posted this script..for what am i requesting..it can decrypt the file..
if anyone can compile..can you do it for me guys..and just upload it..thankss

oh and by the way.. dont have any idea what or to put the codes below
but if you need the lba here it is 

55968

```

u8 byte_table[256] = {
   0xcb, 0x96, 0x85, 0xa6, 0x5f, 0x3e, 0xab, 0x03, 0x50, 0xb7, 0x9c, 0x5c, 0xb2, 0x40, 0xef, 0xf6,
   0xff, 0x61, 0x15, 0x29, 0xa2, 0xf1, 0xec, 0x52, 0x35, 0x28, 0xd9, 0x68, 0x24, 0x36, 0xc4, 0x74,
   0x26, 0xe2, 0xd5, 0x8c, 0x47, 0x4d, 0x2c, 0xfa, 0x86, 0x66, 0xc1, 0x4f, 0x0b, 0x81, 0x5b, 0x1b,
   0xc0, 0x0a, 0xfd, 0x17, 0xa4, 0xa9, 0x6d, 0x63, 0xad, 0xf3, 0xf4, 0x6e, 0x8d, 0x89, 0x14, 0xdd,
   0x59, 0x87, 0x4a, 0x30, 0xce, 0xfe, 0x3f, 0x7e, 0x06, 0x49, 0xa5, 0x04, 0x5e, 0xd0, 0xde, 0xe8,
   0x0f, 0xd4, 0x13, 0x1f, 0xba, 0xb9, 0x69, 0x71, 0x3d, 0xe4, 0xdc, 0x58, 0x90, 0x34, 0x3a, 0x3c,
   0xca, 0x10, 0x76, 0xc7, 0xc8, 0x45, 0x33, 0xc3, 0x92, 0x1d, 0x2b, 0x1c, 0x8f, 0x6f, 0x05, 0x07,
   0x38, 0x57, 0x51, 0xd6, 0xda, 0x2d, 0xb3, 0xc6, 0x2e, 0x64, 0x32, 0x1e, 0x43, 0xb1, 0x5d, 0xe1,
   0xbb, 0x8e, 0x9d, 0x72, 0x77, 0xf2, 0x27, 0xc9, 0x7f, 0x9e, 0xaa, 0x6a, 0x2f, 0x6c, 0xf9, 0x48,
   0xe7, 0xa0, 0x09, 0x56, 0xb8, 0xbd, 0x20, 0x41, 0xcd, 0x95, 0x80, 0xd7, 0x23, 0x0c, 0x42, 0xe5,
   0xae, 0x8b, 0x7d, 0xbc, 0x54, 0x39, 0xbf, 0x65, 0x01, 0x88, 0xe0, 0x7b, 0xb6, 0x16, 0x18, 0x4b,
   0xcc, 0x22, 0x5a, 0xb5, 0xeb, 0xfc, 0xf8, 0x9b, 0x4e, 0xe6, 0xa8, 0xbe, 0x67, 0x73, 0x97, 0x94,
   0x00, 0x62, 0xb4, 0xd2, 0x21, 0x25, 0x11, 0x82, 0xdb, 0x93, 0x02, 0x84, 0x7c, 0xd3, 0xb0, 0xa3,
   0x91, 0xa7, 0xf7, 0x55, 0x70, 0x7a, 0x08, 0x75, 0x8a, 0x53, 0x79, 0xfb, 0x9f, 0x46, 0xf5, 0x83,
   0xd8, 0x0e, 0xe9, 0xed, 0x12, 0xd1, 0xdf, 0xf0, 0x37, 0x2a, 0x44, 0x19, 0x9a, 0x31, 0xcf, 0xa1,
   0xaf, 0xe3, 0x3b, 0x1a, 0x4c, 0x78, 0xc2, 0x60, 0xee, 0x98, 0x6b, 0x0d, 0x99, 0xea, 0xc5, 0xac,
};


u32 key0 = 0x00007F8D;
u32 key1 = 0x00002345;

void init_key(u32 seed)
{
   key0 = seed&0xffff;
   if(key0==0)
      key0 = 0x7F8D;

   key1 = seed>>16;
   if(key1==0)
      key1 = 0x2345;
}

u32 get_key(void)
{
   key0 *= 0x7F8D;
   key0 %= 0xFFF1;

   key1 *= 0x2345;
   key1 %= 0xFFD9;

   return key0+(key1<<16);
}

void mhp3_decrypt(u8 *buf, u32 len)
{
   int i;
   u32 key;

   for(i=0; i<len; i+=4){
      buf[0] = byte_table[buf[0]];
      buf[1] = byte_table[buf[1]];
      buf[2] = byte_table[buf[2]];
      buf[3] = byte_table[buf[3]];

      key = get_key();
      *(u32*)buf ^= key;

      buf += 4;
   }
}

/*************************************************************/

```


How to use:
Use LBA offset as the seed:

```
    mhp3_decrypt(buf, len);
```


Offset of 0 is index table.
## Post #2
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-21T13:20:45+00:00
- Post Title: [HELP]Compiling this C script...URGENT

This code is from tpu so never forget to mention that. This file is compiled using relative LBA - so posting global LBA of .iso wont help you.
Also this code cannot be compiled as it is - it lacks all the functions needed to open files, extract LBA table from first block (34 KB size) and then decode rest of files.

It not as easy as you think... And If you want to understand a bit about C, then please learn it first.
Also in plain C there are no variable types u32 and u8 - you should change them to other type indentifiers:
For visual studio it would be _uint32 and _uint8 and for gcc based familly (Mingw-w32, Mingw-w64, cygwin) it would be uint32_t and uint8_t.
## Post #3
- Username: Tonyhunterblade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 20, 2010 7:56 pm
- Post datetime: 2010-12-22T15:45:00+00:00
- Post Title: [HELP]Compiling this C script...URGENT

Be patient Kenn 
Nimmer tell me on another topic that he will upload a compiler soon ( tomorow ? ). I wait its release ^^
## Post #4
- Username: SiPlus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 05, 2011 6:30 pm
- Post datetime: 2012-04-20T12:15:20+00:00
- Post Title: [HELP]Compiling this C script...URGENT

Where's main function?
