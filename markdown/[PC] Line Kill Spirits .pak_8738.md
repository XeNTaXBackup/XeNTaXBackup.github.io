## Post #1
- Username: sufour
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 07, 2010 11:22 am
- Post datetime: 2012-04-10T05:25:21+00:00
- Post Title: [PC] Line Kill Spirits *.pak

Thanks to Ekey, I have the algorithm needed to decrypt my .pak file ([http://www.mediafire.com/?5vxvhgcbd3pyn5u](http://www.mediafire.com/?5vxvhgcbd3pyn5u)).

Could someone please convert this to QuickBMS or Unpakke?

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
