## Post #1
- Username: filu23
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-02-26T23:43:17+00:00
- Post Title: data0.pkg [Banished]

Request
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-27T13:23:40+00:00
- Post Title: data0.pkg [Banished]

Table and files compressed by blocks with custom algo. Each block = max decompressed size is 0x8000

```
{
   DWORD dwTableOffset;
};

goto dwTableOffset

struct PKGTableHeader
{
   DWORD dwTableSize;
   DWORD dwTableBlockCount;
};

struct PKGTableBlockEntry
{
   DWORD dwBlockPosition;
   WORD dwBlockTableZSize;
   WORD dwBlockTableSize;
};

File data compressed too and have custom header

struct PKGFileDataHeader
{
   DWORD dwBlockCount;
};

struct PKGFileDataEntry
{
   DWORD dwBlockOffset;
   WORD dwBlockZSize;  //can be 0 , don't know how avoid it
   WORD dwBlockSize;
};

// for Table
struct PKGDataEntry
{
   DWORD dwNameLength;
   String pFileName; // Unicode
   DWORD dwOffset;
   DWORD dwSize;
};

```


Decompress algo:

```
{
  unsigned int v4; // eax@1
  unsigned int v5; // ebx@1
  unsigned int v6; // edi@1
  unsigned int v7; // edx@2
  int v8; // edx@3
  int v9; // edx@6
  int v10; // esi@6
  unsigned int v11; // esi@6
  int v12; // ecx@8
  int v13; // ecx@10
  int v15; // [sp+14h] [bp+8h]@1
  unsigned int v16; // [sp+1Ch] [bp+10h]@1

  v5 = pDstBuffer;
  v6 = pScrBuffer;
  v16 = pScrBuffer + pScrSize;
  v4 = v5;
  v15 = v5 + pDstSize;
  while ( 1 )
  {
    v7 = *(BYTE *)v6++;
    if ( v7 >= 0x20 )
      break;
    v8 = v7 + 1;
    if ( v8 + v4 > v15 )
      return 0;
    do
    {
      *(BYTE *)v4++ = *(BYTE *)v6++;
      --v8;
    }
    while ( v8 );
LABEL_12:
    if ( v6 >= v16 )
      return v4 - v5;
  }
  v11 = v7;
  v9 = (v7 & 0x1F) << 8;
  v10 = v11 >> 5;
  if ( v10 == 7 )
    v10 = *(BYTE *)v6++ + 7;
  v12 = v4 - v9 - 1 - *(BYTE *)v6++;
  if ( v10 + v4 + 2 <= v15 && v12 >= v5 )
  {
    *(BYTE *)v4 = *(BYTE *)v12;
    *(BYTE *)(v4 + 1) = *(BYTE *)(v12 + 1);
    v4 += 2;
    v13 = v12 + 2;
    do
    {
      *(BYTE *)v4++ = *(BYTE *)v13++;
      --v10;
    }
    while ( v10 );
    goto LABEL_12;
  }
  return 0;
}
```


I make unpacker but i don't know how avoid this: Entry number > 54 > file have entry where PKGFileDataEntry.dwBlockZSize equal 0 for all blocks.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-27T18:22:49+00:00
- Post Title: data0.pkg [Banished]

Well here unpacker. Some files (music above all) can't be unpacked. 
[BPKGUnpacker_r1.rar](https://xentaxbackup.github.io/file/7048_BPKGUnpacker_r1.rar)
## Post #4
- Username: Hereintheblack
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 05, 2014 10:31 pm
- Post datetime: 2014-09-05T15:15:35+00:00
- Post Title: data0.pkg [Banished]

Sadly doesn't provide us with anything the modkit didn't already come with, which is to say, all we get out of it are .crs files. It would be cool if you could decouple the .crs from other datafiles like textures and models. Also only works on v1.0.0 of the data file.

But a really cool effort, nonetheless!
## Post #5
- Username: Josephhh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 17, 2016 10:40 pm
- Post datetime: 2016-03-17T14:48:49+00:00
- Post Title: data0.pkg [Banished]

I get the information message "PKG Archive Successfully Unpacked" but no files are created on disk and the list inside the program remains blank. This unpacker doesn't work.
## Post #6
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2019-02-08T21:02:06+00:00
- Post Title: data0.pkg [Banished]

Is there a way to pack all the files back or create a new archive with the files?
