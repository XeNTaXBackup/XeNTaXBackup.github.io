## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-27T06:42:06+00:00
- Post Title: [Request] Wan Mei Shi Jie - Hei Ye Chuan Shuo

Ok this game have very cool models, I see and format stored in PCK files, I upload some samples.




[Wan Mei Shi Jie - Hei Ye Chuan Shuo Archive Research](http://www.mediafire.com/download.php?552g7dua2h1ccqy)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-27T12:44:53+00:00
- Post Title: [Request] Wan Mei Shi Jie - Hei Ye Chuan Shuo

Oh look another perfect world game.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-27T12:47:30+00:00
- Post Title: [Request] Wan Mei Shi Jie - Hei Ye Chuan Shuo

offzip can extract the files.
i see the file names in the small files extracted i remember there was some trick to these archives i do not remember what it was tho.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-27T15:18:15+00:00
- Post Title: [Request] Wan Mei Shi Jie - Hei Ye Chuan Shuo

yeah go with offzip because there are some fields unavailable or obfuscated.

in short at the end of the archives there is the list of filenames+offset+size+zsize (0x114 bytes).
each entry is compressed with zlib but in the archive I have found no offset that specifies where this list starts.
and each entry is preceded by 8 bytes where the first 4 are probably a long xored with 0xa8937462 or similar that specifies the size of the compressed entry.

the archives starts with a constant, the full archive size and another constant.
the end of models.pck and textures.pck is different so there are no info at th end which can tell where the file entries start.

so the easiest way is using offzip and when you start to see a long list of 0x114 bytes files quit it.
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-27T18:00:12+00:00
- Post Title: [Request] Wan Mei Shi Jie - Hei Ye Chuan Shuo

yes I know can be extracted but without file names, I know the game use same engine of PW and package are encrypted with XOR but for some reason the tool I have extract all of them except models.pck, anyway somebody can figure out the format for write BMS Script for get file names maybe can do a contribution in paypal account
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-27T20:31:45+00:00
- Post Title: [Request] Wan Mei Shi Jie - Hei Ye Chuan Shuo

Link for download client
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-27T23:26:35+00:00
- Post Title: [Request] Wan Mei Shi Jie - Hei Ye Chuan Shuo

> Reply from Ekey
>
> Link for download client[Client Download](http://wmgj.dl.wanmei.com/w2i/client/w2i_clientV863.rar)
