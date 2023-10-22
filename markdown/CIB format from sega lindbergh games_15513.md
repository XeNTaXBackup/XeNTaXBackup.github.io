## Post #1
- Username: luffytam
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 06, 2012 10:35 am
- Post datetime: 2016-11-20T01:04:42+00:00
- Post Title: CIB format from sega lindbergh games

here's 2 cib files from a sega lindbergh game "rambo" uses criware technology
with the filename said is a graphic file for criware and sega logo
all .cib files cannot decode or even recognize, is a never before seen

here's the cib
[https://mega.nz/#!AwMR0JAC!vQRcVKd1nBPK ... kzDZr-a4mo](https://mega.nz/#!AwMR0JAC!vQRcVKd1nBPKfADMSGrvEpWC2lwubcRnGkzDZr-a4mo)
## Post #2
- Username: luffytam
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 06, 2012 10:35 am
- Post datetime: 2017-02-02T14:40:38+00:00
- Post Title: CIB format from sega lindbergh games

NEWS HERE:Silent hill arcade which develop by Konami also use cib format. both game have a ObjInit folder and .oni script inside. the exe/elf data show us there's a tool/engine called "Clarithplayer" because Rambo game data have clarith folder. So i import rambo cib files into Silent hill arcade, it work perfectly. somebody could reverse engineering exe files and write bms export script for cib files with this discovery:)

[KSHG 2017-02-02 22-29-11-15.png](https://xentaxbackup.github.io/file/12373_KSHG 2017-02-02 22-29-11-15.png)
## Post #3
- Username: luffytam
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 06, 2012 10:35 am
- Post datetime: 2017-05-05T07:56:14+00:00
- Post Title: CIB format from sega lindbergh games

Decompile code that handle CIB file from silent hill arcade via. IDA Pro

```
{
  int v4; // ebx@1
  unsigned int v5; // edx@1
  unsigned int v6; // eax@2
  _DWORD *v7; // eax@5
  int v8; // ecx@6
  int result; // eax@11
  unsigned int v10; // eax@14
  bool v11; // zf@15
  void *v12; // edi@18
  bool v13; // cf@24

  v4 = a1;
  v5 = *(_DWORD *)(a1 + 24);
  if ( v5 < 0x10 )
    v6 = a1 + 4;
  else
    v6 = *(_DWORD *)(a1 + 4);
  if ( (unsigned int)a3 < v6
    || ((v7 = (_DWORD *)(a1 + 4), v5 < 0x10) ? (v8 = a1 + 4) : (v8 = *v7), v8 + *(_DWORD *)(v4 + 20) <= (unsigned int)a3) )
  {
    if ( a4 > 0xFFFFFFFE )
      sub_66A8E3(v4);
    v10 = *(_DWORD *)(v4 + 24);
    if ( v10 >= a4 )
    {
      v11 = a4 == 0;
      if ( !a4 )
      {
        *(_DWORD *)(v4 + 20) = 0;
        if ( v10 < 0x10 )
        {
          *(_BYTE *)(v4 + 4) = 0;
          result = v4;
        }
        else
        {
          **(_BYTE **)(v4 + 4) = 0;
          result = v4;
        }
        return result;
      }
    }
    else
    {
      sub_402050(a4, *(_DWORD *)(v4 + 20));
      v11 = a4 == 0;
    }
    if ( !v11 )
    {
      if ( *(_DWORD *)(v4 + 24) < 0x10u )
        v12 = (void *)(v4 + 4);
      else
        v12 = *(void **)(v4 + 4);
      qmemcpy(v12, a3, a4);
      v13 = *(_DWORD *)(v4 + 24) < 0x10u;
      *(_DWORD *)(v4 + 20) = a4;
      if ( !v13 )
      {
        *(_BYTE *)(*(_DWORD *)(v4 + 4) + a4) = 0;
        return v4;
      }
      *(_BYTE *)(v4 + 4 + a4) = 0;
    }
    result = v4;
  }
  else
  {
    if ( v5 >= 0x10 )
      v7 = (_DWORD *)*v7;
    result = sub_402690(v4, (_BYTE *)a3 - (_BYTE *)v7, a4);
  }
  return result;
}
```
