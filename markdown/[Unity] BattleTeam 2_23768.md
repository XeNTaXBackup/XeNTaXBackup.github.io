## Post #1
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-04-20T12:14:19+00:00
- Post Title: [Unity] BattleTeam 2

website:[https://www.ssjj.cn/](https://www.ssjj.cn/)
Sample:[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1kbGMFWftJVuLxNkw_JZCYlq-u6MSzWpQ?usp=sharing)

The game files seems to be encrypted.And AssetStudio/UnityStudio failed to load them correctly. Is there anyone write a script to extract assets  



20210420201237.png (30.45 KiB) Viewed 161 times
## Post #2
- Username: mama2023
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 20, 2023 2:26 am
- Post datetime: 2023-08-09T19:18:57+00:00
- Post Title: [Unity] BattleTeam 2

Yes, the .ab files are not encrypted, but the index file .assets is encrypted. Hoping for an expert to step in and decrypt this game.
The following are all index files“[https://drive.google.com/drive/folders/ ... VFD03cevv-](https://drive.google.com/drive/folders/1N5v88i9-Ar1JNusS203ExZVFD03cevv-)”
## Post #3
- Username: bionicjellyfish
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 07, 2023 1:46 pm
- Post datetime: 2023-08-11T11:55:30+00:00
- Post Title: [Unity] BattleTeam 2

I have been trying to unpack this game recently, but I encountered problems. So I am very happy that there are other people working on this game too. 

I found that its AssetBundle file is different from the regular UnityFS. In the file, flag value of blocks info may be 0x05, may correspond to the encryption method designed by the developer. When using AssetRipper to unpack, it will get "Error Bundle compression '5' isn't supported". I have tried to test comtype_scan2.bms on one data block, but I did not get the correct algorithm that uncompressed size is consistent with the "uncompressed block size" in UnityFS blocks info.

I am a novice in unpacking and I hope to get some help. Thanks in advance.  

This is a .ab sample: [https://we.tl/t-in3II09QV0](https://we.tl/t-in3II09QV0) (PM me if expired)
## Post #4
- Username: xiong1524877065
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 14, 2023 11:52 pm
- Post datetime: 2023-10-02T06:37:59+00:00
- Post Title: [Unity] BattleTeam 2

BattleTeam 2 Has anyone solved it?
