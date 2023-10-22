## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-11-25T22:32:14+00:00
- Post Title: Next Car Game

Could someone have a look at the new bug bear game format? The underlying format looks to be similar if not the same as previous bfs files from this developer (looking in the memory) but there appears to be some decryption which is occurring first.
I found what looks like a 24 byte key at  0x944CC0 - 7D 21 12 DD A6 4F 3E 28 50 C3 3C D9 99 45 37 C9 EC 66 BB 00 00 00 00 00
which could be 3DES? But some quick tests don't come back with the expected results.
Debugging with IDA there appears to be a decryption function after one of the references to the key sub_734DF0

Here is the first 32768 bytes of the file (0x8000 is the size of the first chunk to get decrypted)
[https://dl.dropboxusercontent.com/u/9950356/start.bin](https://dl.dropboxusercontent.com/u/9950356/start.bin)

If anyone needs the exe just drop me a message.

update:
I'm pretty sure the encryption used is now tea - [http://en.wikipedia.org/wiki/Tiny_Encryption_Algorithm](http://en.wikipedia.org/wiki/Tiny_Encryption_Algorithm)
I'll do another update if i make any progress.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-26T20:49:15+00:00
- Post Title: Next Car Game

Bfs used by double encryption with different algos (not XTEA). Full archive and file data.

1st - You need decrypt full archive by blocks with size 0x2000 (algo N1)
2nd - After decrypt you need read header, calc table size and decrypt it again (algo N2)

Algo 1 - Decrypt archive

```

void __cdecl bfs_decrypt_block(int pBuffer, int pKey, signed int pBlockSize)
{
  int pCounter;
  unsigned int pPosition;
  int i;

  if ( pBlockSize > 1 )
  {
    pPosition = *(DWORD *)(pBuffer + 4 * pBlockSize - 4);
    pCounter = 0;
    i = pBlockSize - 1;
    if ( i > 0 )
    {
      do
      {
        *(DWORD *)(pBuffer + 4 * pCounter) -= ((pPosition ^ 0x9E3779B9)
                                              + (*(DWORD *)(pBuffer + 4 * pCounter + 4) ^ *(DWORD *)(pKey + 4 * (((BYTE)pCounter ^ 0xFE) & 3)))) ^ ((4 * pPosition ^ (*(DWORD *)(pBuffer + 4 * pCounter + 4) >> 5)) + ((pPosition >> 3) ^ 16 * *(DWORD *)(pBuffer + 4 * pCounter + 4)));
        pPosition = *(DWORD *)(pBuffer + 4 * pCounter++);
      }
      while ( pCounter < i );
    }
    *(DWORD *)(pBuffer + 4 * pCounter) -= ((pPosition ^ 0x9E3779B9)
                                          + (*(DWORD *)pBuffer ^ *(DWORD *)(pKey + 4 * (((BYTE)pCounter ^ 0xFE) & 3)))) ^ ((4 * pPosition ^ (*(DWORD *)pBuffer >> 5)) + ((pPosition >> 3) ^ 16 * *(DWORD *)pBuffer));
  }
}

void bfs_decrypt (int pData, int pSize) {
    int pBlockSize = 0x2000;
    int pNextBlock = 0x8000;
    int pBlocks = pSize/ pNextBlock;
    for (int i = 0; i < pBlocks; i++, pData += pNextBlock) 
        bfs_decrypt_block((int)pData, (int)&pKey, pBlockSize);
}

```

Algo 2 - Decrypt file data

```

void __cdecl bfs_decrypt_data(unsigned int *pBuffer, int pKey, unsigned int pSize)
{
  unsigned int v3;
  unsigned int v4;
  unsigned int v5;
  int v6;
  int v7;
  int v8;
  char v9;
  int v10;
  unsigned int v11;

  v3 = pSize;
  if ( pSize > 1 )
  {
    v5 = *pBuffer;
    v4 = 0x9E3779B9 * (0x34 / pSize + 6);
    v11 = 0x9E3779B9 * (0x34 / pSize + 6);
    do
    {
      v6 = v3 - 1;
      v10 = (v4 >> 2) & 3;
      if ( v3 != 1 )
      {
        do
        {
          pBuffer[v6] -= ((v11 ^ v5) + (pBuffer[v6 - 1] ^ *(DWORD *)(pKey + 4 * (v10 ^ v6 & 3)))) ^ ((4 * v5 ^ (pBuffer[v6 - 1] >> 5)) + ((v5 >> 3) ^ 16 * pBuffer[v6 - 1]));
          --v6;
          v5 = pBuffer[v6 + 1];
        }
        while ( v6 );
        v3 = pSize;
      }
      v7 = (v5 >> 3) ^ 16 * pBuffer[v3 - 1];
      v8 = 4 * v5 ^ (pBuffer[v3 - 1] >> 5);
      v3 = pSize;
      *pBuffer -= ((v11 ^ v5) + (pBuffer[pSize - 1] ^ *(DWORD *)(pKey + 4 * (v10 ^ v6 & 3)))) ^ (v8 + v7);
      v5 = *pBuffer;
      v9 = v11 == 0x61C88647u;
      v4 = v11 + 0x61C88647;
      v11 += 0x61C88647u;
    }
    while ( !v9 );
  }
}

void bbfs_decrypt_data (int pData, int dwLength)
{
   bbfs_decrypt_block_data((unsigned int*)pData, (int)pKey_Data, dwLength);
}

```
## Post #3
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-11-26T22:15:53+00:00
- Post Title: Next Car Game

awesome, thanks!

Edit:
I'm guessing you ripped those functions out of the executable but any idea how to encrypt?
## Post #4
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-11-27T11:27:00+00:00
- Post Title: Next Car Game

this game looks tits. 

 I hope we can not just decrypt but also import in the future cause some of the cars I do would be great in soft body. but I'd have to see how they compartmentalize their meshes and also how it's skinned and dummied before that. I know past flatouts were modable to a degree as my buddies used to do this and well this is bugbear after all. I might ask them if this game will be modable. till then I can only play the demo and dream of the car damage to my favorite cars.
## Post #5
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-11-27T11:52:56+00:00
- Post Title: Next Car Game

> Reply from octaviousrex
>
> this game looks tits. 

 I hope we can not just decrypt but also import in the future cause some of the cars I do would be great in soft body. but I'd have to see how they compartmentalize their meshes and also how it's skinned and dummied before that. I know past flatouts were modable to a degree as my buddies used to do this and well this is bugbear after all. I might ask them if this game will be modable. till then I can only play the demo and dream of the car damage to my favorite cars.

Well, if we can't work out how to encrypt the files again I think we might be able to just remove the decryption calls in the executable and it will carry on with the already decrypted archive. This is just theory though, whether it will work in practice is another question.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-27T13:08:09+00:00
- Post Title: Next Car Game

Currently nothing useful here simple tool for decrypt only archives.

```
        NCGDecrypt <pInFile> <pOutFile>

[Example]
        NCGDecrypt 00__nextcargame__ 00__nextcargame__.dec
```

[NCGDecrypt_0.1.rar](https://xentaxbackup.github.io/file/6805_NCGDecrypt_0.1.rar)
## Post #7
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-11-29T19:03:45+00:00
- Post Title: Next Car Game

I got a slightly different size:  3195
decrypted tables:
00 - [https://db.tt/SGq4rzMx](https://db.tt/SGq4rzMx)
01 - [https://db.tt/pPNGQOrp](https://db.tt/pPNGQOrp)

Any idea how the files are contained? From previous versions I guessed zlib but offzip doesn't result in much.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-30T09:18:47+00:00
- Post Title: Next Car Game

Ok.. 3195 it's not table size, seems rounds for full table.

```
{
	BYTE	 pID[4];	//bbfs
	DWORD	dwVersion;
	WORD	 wTableSize;
	WORD	 wUnknown;
	DWORD	dwFilesCount;	//???
	DWORD	dwType;	//1 ??? 
};
```


```
int dwRounds = pHeader.wTableSize - 20 >> 2

bfs_decrypt_data(pBuffer, &Key, dwRounds)
```
## Post #9
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-12-03T19:44:47+00:00
- Post Title: Next Car Game

Probably not much use but here's a list of filenames (yes I'm aware there's duplicates, I couldn't be bothered to filter them out)
[http://pastebin.com/6WABkCXn](http://pastebin.com/6WABkCXn)

Working on hooking file requests and replacing them.

Edit (04/12/2013)
Making progress 

[http://pastebin.com/MbEs8a8u](http://pastebin.com/MbEs8a8u)
## Post #10
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-12-10T23:51:15+00:00
- Post Title: Next Car Game

seems someone was able to grab a tire from the game. 

[http://tf3dm.com/3d-model/tire-21722.html](http://tf3dm.com/3d-model/tire-21722.html)



 not sure if this is a help or not they seem to have been able to get the tire into Cinema 4D as that is the main format shown.
## Post #11
- Username: dimon4ik6565
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 22, 2012 10:48 pm
- Post datetime: 2013-12-11T10:56:55+00:00
- Post Title: Next Car Game

> Reply from octaviousrex
>
> seems someone was able to grab a tire from the game. 

http://tf3dm.com/3d-model/tire-21722.html



 not sure if this is a help or not they seem to have been able to get the tire into Cinema 4D as that is the main format shown.

3D Rippers..
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-22T18:13:46+00:00
- Post Title: Next Car Game

[Post](http://forum.xentax.com/viewtopic.php?p=90450#p90450) updated. Added key for data's (2nd algo). After decrypting we get table without file names but with hashes (every hash by 0x14). [here](http://www.sendspace.com/file/7ajo5b) example table from 00__nextcargame__  archive. Any ideas?
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-03-01T10:03:55+00:00
- Post Title: Next Car Game

have you tried the script I released some months ago?
[http://aluigi.org/papers/bms/others/next_car_game.bms](http://aluigi.org/papers/bms/others/next_car_game.bms)
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-01T10:14:02+00:00
- Post Title: Next Car Game

Oh my God. I thought there just 2 encryption algo . Thanks Luigi.
## Post #15
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2014-04-02T03:29:29+00:00
- Post Title: Next Car Game

> Reply from dimon4ik6565
>
> octaviousrex wrote:seems someone was able to grab a tire from the game. 

http://tf3dm.com/3d-model/tire-21722.html



 not sure if this is a help or not they seem to have been able to get the tire into Cinema 4D as that is the main format shown.

3D Rippers..

actually I've tried all but 3D VIA PRINTSCREEN because via won't work for me at all and none of the rippers will go ingame. so this still makes one ask the question as to what could be used to rip it. will check out the tools thanks.
## Post #16
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-04-02T10:54:57+00:00
- Post Title: Re: Next Car Game

> Reply from octaviousrex
>
> 
[snip]

actually I've tried all but 3D VIA PRINTSCREEN because via won't work for me at all and none of the rippers will go ingame. so this still makes one ask the question as to what could be used to rip it. will check out the tools thanks.

NinjaRipper kind of worked for me, but the UVs it exports are way too large. I tried exporting one of the cars, but resizing UVs manually one-by-one for every car part was a tedious task.
## Post #17
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2014-04-03T14:42:15+00:00
- Post Title: Re: Next Car Game

> Reply from barti
>
> octaviousrex wrote:
[snip]

actually I've tried all but 3D VIA PRINTSCREEN because via won't work for me at all and none of the rippers will go ingame. so this still makes one ask the question as to what could be used to rip it. will check out the tools thanks.

NinjaRipper kind of worked for me, but the UVs it exports are way too large. I tried exporting one of the cars, but resizing UVs manually one-by-one for every car part was a tedious task.

 I tried ripper. the only mode that would work for me was the first option none of the direct x options worked and even then it said "unhandled expection.
## Post #18
- Username: s6tvxstz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 19, 2018 2:40 am
- Post datetime: 2018-06-18T18:43:26+00:00
- Post Title: Re: Next Car Game

> Reply from aluigi
>
> have you tried the script I released some months ago?
http://aluigi.org/papers/bms/others/next_car_game.bms
Any chance to update this for the current version of the game? Thanks.
