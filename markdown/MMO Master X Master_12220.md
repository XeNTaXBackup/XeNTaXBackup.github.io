## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-11T04:46:03+00:00
- Post Title: MMO Master X Master

Here are the client download links
[http://mxmkor.ncdn.gscdn.com/MXM_KOR/20 ... MSetup.exe](http://mxmkor.ncdn.gscdn.com/MXM_KOR/2014092501/MXMSetup.exe)
[http://mxmkor.ncdn.gscdn.com/MXM_KOR/2014092501/MXM.7z](http://mxmkor.ncdn.gscdn.com/MXM_KOR/2014092501/MXM.7z)
or the downloader
http://mxm_kor.ncdn.plaync.co.kr/MXM_KOR/MXM_KOR.exe

Files are encrypted pak files if someone wants to take a look.

[http://mxm.plaync.com/master/index](http://mxm.plaync.com/master/index)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-11-12T13:16:18+00:00
- Post Title: MMO Master X Master

Hybrid algo - AES + XOR. AES used only for initialize key. Data is XORing by key initialized from AES.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-12T13:50:18+00:00
- Post Title: MMO Master X Master

Yeah looking at the files I thought it was xored because I could get file names by xoring it but the key changed each time like you said.
Any more info on getting the initial key?
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-11-12T14:52:40+00:00
- Post Title: MMO Master X Master

AES Key for creating XOR keys is \x22\xE0\xF3\x80\x7D\xD0\x65\xA5\xD7\x9E\xA6\x26\xD2\x74\x06\x9A

For example
XOR Key for offset 0x8 with size 0x10 - \x8D\x28\x60\xEC\x3F\x5C\xD9\x0F\x6B\x10\x33\xFD\xB7\x0A\x68\x25
XOR Key for offset 0x18 with size 0x4 - \xBD\xD5\xB5\xAB\x63\x91\xF9\xED\x6B\x13\x65\xD0\xB0\xD0\xDD\x25

Now I'm trying to understand how the keys are updated
## Post #5
- Username: MalachiTheLight
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 01, 2019 8:47 am
- Post datetime: 2019-09-01T00:51:37+00:00
- Post Title: MMO Master X Master

I know this is post is ancient, but if anyone still has the korean 2014 files from the dead links still saved somewhere, could you please inform me.
## Post #6
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2019-09-10T02:52:51+00:00
- Post Title: MMO Master X Master

> Reply from MalachiTheLight ↑Sun Sep 01, 2019 8:51 am at Sun Sep 01, 2019 8:51 am
>
> 
I know this is post is ancient, but if anyone still has the korean 2014 files from the dead links still saved somewhere, could you please inform me.

lol i havn't visited this forum for a long time and now i do because i have this one unknown installer i decided to check today in my download folder which happens to be this game.

 i believe its one of the latest or latest version because i got it feb/2019 before shutdown and its chinese version, do you know a simple host i can upload to, 3.94gb

has anyone managed to workaround this game's .pak files?
## Post #7
- Username: Delta47
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 14, 2020 10:50 pm
- Post datetime: 2020-02-14T14:58:52+00:00
- Post Title: MMO Master X Master

You can upload it to mega or Google Drive or somewhere else. Then i compare it if we have it already in the archive.
archive of NCWest versions: [https://archive.org/details/MasterXMaster](https://archive.org/details/MasterXMaster)
archive of Tencent (Chinese) versions: [https://archive.org/details/MasterXMasterTencent](https://archive.org/details/MasterXMasterTencent)
As for the pak file extraction we need to extract the decryption key which can be done with a proxy dll (I think/ I hope) but gameguard blocks that so need to make a gameguard emulator first. The games exe is also packed so it's just garbage in decompiler.
## Post #8
- Username: Delta47
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 14, 2020 10:50 pm
- Post datetime: 2020-03-10T20:24:29+00:00
- Post Title: MMO Master X Master

Google Drive, Microsoft OneDrive, Mega are all straightforward hosts
## Post #9
- Username: Delta47
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 14, 2020 10:50 pm
- Post datetime: 2020-07-01T18:26:36+00:00
- Post Title: MMO Master X Master

So someone unpacked and removed gameguard from the client. Would it be possible that someone takes a look at it again to make an extractor.
Link to client: [https://drive.google.com/file/d/1HMrqTY ... sp=sharing](https://drive.google.com/file/d/1HMrqTYwfGYS24HuBbaWVSzJwdKo5H4SR/view?usp=sharing)
The client is the latest version of the ncwest version. [https://archive.org/download/MasterXMas ... /12147%20/](https://archive.org/download/MasterXMaster/Full%20Install/Release/12147%20/)
I have added a small pak file as example.
[FileList.xml.pak.7z](https://xentaxbackup.github.io/file/18412_FileList.xml.pak.7z)
## Post #10
- Username: Delta47
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 14, 2020 10:50 pm
- Post datetime: 2020-07-31T19:52:55+00:00
- Post Title: MMO Master X Master

So a quick update we have an unpacker now for the game, atm it supports pak files with magic PAKW which are versions starting 2017 (maybe some 2016 versions). Older versions have magic PAKA and aren't supported because different compression and maybe different encryption. [https://github.com/LordSk/MXM-Research/tree/server](https://github.com/LordSk/MXM-Research/tree/server)
## Post #11
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2021-05-30T21:04:21+00:00
- Post Title: MMO Master X Master

Can we view and export the .kf animations of the characters?
As i'm unable to load the .kf animations in Noesis..
