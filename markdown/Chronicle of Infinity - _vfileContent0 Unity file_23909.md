## Post #1
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-05-19T10:24:32+00:00
- Post Title: Chronicle of Infinity - _vfileContent0 Unity file

Official Web: https://zs.wanmei.com/#

Game CG: [https://www.youtube.com/watch?v=XEwVT8R ... =archosaur](https://www.youtube.com/watch?v=XEwVT8RpSZY&ab_channel=archosaur)

Client Download Link:
PC: [https://zsyjydhd.wmupd.com/zsyjydhd/cli ... 210519.zip](https://zsyjydhd.wmupd.com/zsyjydhd/client/ZSYJ_0.6.8_20210519.zip)
Android: [https://download552110.wmupd.com/alo/qh ... qfbczf.apk](https://download552110.wmupd.com/alo/qhs/ubb/akq/dvqfbczf.apk)


 

Chronicle of Infinity will public test in 5.20, the model is very nice in Unity engine.The main resource file can not load with AssetStudio.Hope someone can make it happen.
## Post #2
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-05-19T11:39:02+00:00
- Post Title: Chronicle of Infinity - _vfileContent0 Unity file

Anyone?
## Post #3
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-05-25T03:44:06+00:00
- Post Title: Chronicle of Infinity - _vfileContent0 Unity file

Someone can make it work?
## Post #4
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-12-24T10:23:33+00:00
- Post Title: Chronicle of Infinity - _vfileContent0 Unity file

I checked it because I had a chance, but this is a very strange format. There is no header area common to all files.
Normally, UnityFS is followed by the size for version information, file size, and compression information, but the assets in this game do not have that data in common.

The info block information is also very strange. There should be as many repeating areas as there are stored assets, but none.
The size of the info block is almost the same for all files. The CAB information of the info block is XOR encrypted and can be decrypted by XOR with 0x1E1E0101FC, but it is not useful because the information in the header area is insufficient.

Some Asian games have some custom files, which may be one of them.
It is unlikely that a regular UnityFS bundle can dynamically create a header area. It causes a read error even if the difference is 1 byte.

*EDIT



infinity.png (54.99 KiB) Viewed 60 times


I was able to guess and generate a header and convert it to a readable UnityFS, which is crazy. I'm very interested in how this game accurately and dynamically generates headers.
