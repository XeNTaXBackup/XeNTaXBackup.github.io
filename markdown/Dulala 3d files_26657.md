## Post #1
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2023-04-13T21:17:34+00:00
- Post Title: Dulala 3d files

3d Unity game with unencrypted metadata and encrypted .data, some of which load an image but cannot preview/export. 
The unity .pkg in apk also looks different than files from in-game.
in game file data, dump.cs [https://mega.nz/folder/56BC1TAJ#QSKPlU85V2oDreSasLhYZA](https://mega.nz/folder/56BC1TAJ#QSKPlU85V2oDreSasLhYZA) 
(apk from [https://www.biligame.com/detail/?id=109958](https://www.biligame.com/detail/?id=109958)) 
all data is downloaded at launch, but I can provide an account if needed
## Post #2
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2023-04-14T04:03:44+00:00
- Post Title: Dulala 3d files

ask some people in the unitypy discord server to help you

< link removed by moderator>
## Post #3
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2023-04-14T09:32:00+00:00
- Post Title: Dulala 3d files

> Reply from MrYouKnowItAll ↑Fri Apr 14, 2023 12:03 pm at Fri Apr 14, 2023 12:03 pm
>
> 
ask some people in the unitypy discord server to help you

< link removed by moderator>

I did, there's no reply so I am asking here
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-05-06T21:07:18+00:00
- Post Title: Dulala 3d files

Alternative english title for the game is "Go Lala Go". The package format is quite interesting, kind of archive with each entry consists of preuso unity bundle header and entry can be any file (actual bundle, audio file, etc) - which is implementation of PhysFS. Last entry in archive is index with obfuscated names (probably xored), wrapped in the same way. But even if you'll extract bundles, part of the header is obfuscated along with paths in directoryinfo, and data chunks are zstd compressed with dictionary, while some chunks are marked as uncompressed, but they seem like fully encrypted.

The following script can extract separate entries from pkg archives as-is (index is ignored though). It may be useful for at least audio package, since files are not additionally obfuscated there.



 unity_pkg_extract.zip
(584 Bytes) Downloaded 22 times
## Post #5
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2023-05-08T09:00:49+00:00
- Post Title: Dulala 3d files

Oo thank you so much ><
