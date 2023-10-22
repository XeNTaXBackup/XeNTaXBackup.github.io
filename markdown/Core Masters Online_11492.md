## Post #1
- Username: zdsmdbh
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-07T21:48:20+00:00
- Post Title: Core Masters Online

[http://www.coremasters.jp/](http://www.coremasters.jp/)
Game is using 
```
Gamebryo File Format, Version 40.0.0.5
```

Game archives look like they might be xored or lightly encrypted.
The launcher can decrypt the files i see them in memory during file checks and patching.
If anyone wants an account and the client i can make one for you to look at the game.
some game info
[http://games.mail.ru/pc/games/core_masters/](http://games.mail.ru/pc/games/core_masters/)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-08T05:11:25+00:00
- Post Title: Core Masters Online

Do you have link for download client?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-08T10:37:49+00:00
- Post Title: Core Masters Online

sure you need
[https://ic.gamepot.co.jp/Content/module ... taller.msi](https://ic.gamepot.co.jp/Content/modules/GPEXEInstaller.msi)
and then
[http://dl.coremasters.jp/coremasters/Pr ... _Setup.exe](http://dl.coremasters.jp/coremasters/Production/SetUp/CoreMasters_Setup.exe)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-08T16:31:46+00:00
- Post Title: Core Masters Online

Encryption is Salsa20
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-08T16:36:34+00:00
- Post Title: Core Masters Online

Do you need any files from me or can you find the key in those existing files.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-08T19:16:06+00:00
- Post Title: Core Masters Online

Key and IV generating by next function

```
{
  int Size;
  int pResult;
  unsigned int dwSeed;

  Size = dwSize;
  if ( dwSize )
  {
    pResult = pKeyIV;
    do
    {
      --Size;
      dwSeed = 48271 * *(DWORD *)(this + 4) % 0xADC8u - 3399 * *(DWORD *)(this + 4) / 0xADC8u;
      if ( (signed int)dwSeed <= 0 )
        *(DWORD *)(this + 4) = dwSeed + 0x7FFFFFFF;
      else
        *(DWORD *)(this + 4) = dwSeed;
      ++pResult;
      *(BYTE *)(pResult - 1) = *(BYTE *)(this + 4) ^ (*(WORD *)(this + 4) >> 8) ^ (unsigned __int8)((*(DWORD *)(this + 4) >> 16) ^ (unsigned __int8)(*(DWORD *)(this + 4) >> 24));
    }
    while ( Size );
  }
}
```


Param 1 - Unknown
Param 2 - Output key or iv
Param 3 - Size ( for Key > 32, for IV > 8 )
## Post #7
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2015-05-15T07:03:43+00:00
- Post Title: Core Masters Online

Could anyone share the unpacker?
I am not a programmer!

Thanks
## Post #8
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2015-06-23T10:21:22+00:00
- Post Title: Core Masters Online

Any News on this unpacker!? Please~
## Post #9
- Username: Pal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 16, 2015 12:48 pm
- Post datetime: 2015-10-22T22:03:58+00:00
- Post Title: Core Masters Online

Bumping out of interest. Game has closed down in Korea and Japan, only the SEA version remains:
[http://cm.garena.com/home](http://cm.garena.com/home)

I'd love to salvage the resources from it before its imminent closure on January. I can upload a file if needed. Any help appreciated.
