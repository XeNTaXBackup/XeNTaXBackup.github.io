## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-03T17:57:55+00:00
- Post Title: Perpetuum GBF Decrypting

Target: [Victim](http://www.perpetuum-online.com)
Format: GBF (Encrypted file table and contained files)

Algo:

```
#define LOBYTE(x) (*((_BYTE*)&(x)))

typedef unsigned char _BYTE;
typedef unsigned int _DWORD;

__int16 __stdcall GBF_Decrypt(int a1, int a2, unsigned __int64 a3)
{
  unsigned int v3;
  unsigned int v4;
  __int16 result;
  unsigned __int8 v6;

  v3 = 0;
  v4 = 0;
  if ( a3 > 0 )
  {
    do
    {
      do
      {
        result = (char)(v3 + 1) * (char)((_BYTE)v3 ^ 0xCA);
        LOBYTE(result) = *(_BYTE *)(v3 + a1) ^ (result - 84);
        v6 = v3++ >= 0xFFFFFFFF;
        *(_BYTE *)(v3 + a2 - 1) = result;
        v4 += v6;
      }
      while ( v4 < HIDWORD(a3) );
    }
    while ( v4 <= HIDWORD(a3) && v3 < (_DWORD)a3 );
  }
  return result;
}
```


a1 - InBuffer 
a2 - OutBuffer
a3 - Size

Usage:

```
GBF_Decrypt((int)InBuffer,(int)OutBuffer,size);
```


For those who will make unpacker. Test source's attached 
[PGBFDecrypt.rar](https://xentaxbackup.github.io/file/5632_PGBFDecrypt.rar)
