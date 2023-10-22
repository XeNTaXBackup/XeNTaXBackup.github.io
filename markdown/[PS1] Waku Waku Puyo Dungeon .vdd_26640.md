## Post #1
- Username: elel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 08, 2023 6:44 pm
- Post datetime: 2023-04-08T11:00:20+00:00
- Post Title: [PS1] Waku Waku Puyo Dungeon .vdd

hello all! i am interested in extracting sprites from the PlayStation game "waku waku puyo dungeon", but the files are compressed in a strange format i cant find anything about online. looking up "vdd playstation" just gets me hardware discussion, which isnt what im looking for.
any help would be appreciated!

sample:
[https://www.mediafire.com/file/kk6vu90w ... Q.VDD/file](https://www.mediafire.com/file/kk6vu90wdyd9h3e/FIL_SEQ.VDD/file)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-04-08T11:41:29+00:00
- Post Title: [PS1] Waku Waku Puyo Dungeon .vdd

It looks like an archive with a lot of "SEQ" files stored inside.
Each SEQ file starts with "CNX" signature, which indicates that maybe some custom audio format has been created for this game.
## Post #3
- Username: elel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 08, 2023 6:44 pm
- Post datetime: 2023-04-08T19:43:26+00:00
- Post Title: [PS1] Waku Waku Puyo Dungeon .vdd

yeah. a lot of the files contained inside seem to be using weird, possibly proprietary formats. the sprites (in FIL_GRP.VDD) are in .BTX and .FMP

[worth noting that someone on TSR ripped a couple of the sprites at some point](https://www.spriters-resource.com/playstation/wakupuyodungeonketteiban/)


EDIT: I checked out some of Compile's other PS1 offerings, and Puyo Puyo BOX uses the same .VDD compression format. Once again, some of the sprites are available on TSR
puyo puyo box sample: [https://www.mediafire.com/file/ms2usuj6 ... P.VDD/file](https://www.mediafire.com/file/ms2usuj682ddng1/MIN_GRP.VDD/file)
