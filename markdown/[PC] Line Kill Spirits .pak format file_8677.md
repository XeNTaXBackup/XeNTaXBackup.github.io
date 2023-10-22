## Post #1
- Username: sufour
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 07, 2010 11:22 am
- Post datetime: 2012-04-01T18:31:16+00:00
- Post Title: [PC] Line Kill Spirits .pak format file

* snip

I had a friend look at this file, and they said it might be either compressed, encrypted, or both.  All of the games assets except for its audio are stored within.  Can anyone here take a look at this?

*UPDATED* 
Here is the link to the game's install files (in cue, cdm, & img format in a RAR:)
* snip
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-02T15:08:10+00:00
- Post Title: [PC] Line Kill Spirits .pak format file

Post download link game or official site. Game full named Line-Kill Spirits ?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-06T19:15:54+00:00
- Post Title: [PC] Line Kill Spirits .pak format file

Here algo for decrypt

```
{
  unsigned int result; // eax@1
  unsigned int v5; // ecx@1
  int v6; // esi@2
  int v7; // edi@2
  int v8; // ebp@2
  __int64 v9; // qax@3
  int v10; // ebx@3
  signed __int64 v11; // qax@3
  int v12; // [sp+Ch] [bp+Ch]@2
  dword_576394    dd 0

  result = a4;
  v5 = 0;
  if ( a4 )
  {
    v6 = a3;
    v7 = 1103515245 * a1 + 12345;
    v8 = a1 - a3;
    v12 = a2 - a3;
    do
    {
      v9 = 1103515245 * (signed int)*(_BYTE *)((unsigned int)(v6 + v8) % *(_DWORD *)(dword_576394 - 8) + dword_576394) + 12345;
      v10 = (WORD2(v9) + (signed int)v9) >> 16;
      v11 = v7 & 0xFFFFFFFFFFFFi64;
      v7 += 1103515245;
      LOBYTE(v10) = *(_BYTE *)v6 ^ ((HIDWORD(v11) + (signed int)v11) >> 16) ^ (unsigned __int8)(41 * (a1 + (_BYTE)v5++) + (_BYTE)v10);
      *(_BYTE *)(v12 + v6) = v10;
      result = a4;
      ++v6;
    }
    while ( v5 < a4 );
  }
  return result;
}
```
## Post #4
- Username: sufour
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 07, 2010 11:22 am
- Post datetime: 2012-04-08T05:58:15+00:00
- Post Title: [PC] Line Kill Spirits .pak format file

Which program do I use to run this algorithm?
