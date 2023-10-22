## Post #1
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2014-10-17T17:15:07+00:00
- Post Title: 斗战神-DZS (.vfs)

I want open this vfs. Very beautiful game.
all vfs bms not work.

斗战神-DZS: [http://dzs.qq.com/](http://dzs.qq.com/)
download: [http://down-update.qq.com/wgame/full/Dz ... signed.exe](http://down-update.qq.com/wgame/full/DzsFullSetup_1.6.10.3474_VIPDL_signed.exe)
vfs file: [https://mega.co.nz/#!TE4WFKRL!eQ04FHQFn ... A7vxPWPAAQ](https://mega.co.nz/#!TE4WFKRL!eQ04FHQFnW51dXVGpyNB9N-VR4hjbCM8wA7vxPWPAAQ)

help me please, thank you.
## Post #2
- Username: Sleepy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jun 23, 2015 1:59 am
- Post datetime: 2016-01-07T08:35:36+00:00
- Post Title: 斗战神-DZS (.vfs)

0x2C -  4byte String table pointer 
in front of the filename it contains the lenght of filename with "/"  

for example:



05 00 - 5 
5C 64 61 74 61 - /data

I hope it's useful.

update: I made a tool for open the file and loaded the string table which contains the name of the files.
and also added them to treeview  

update 2: 



now It's opened but for exporting from this archive need more work
## Post #3
- Username: Sleepy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jun 23, 2015 1:59 am
- Post datetime: 2016-10-23T09:24:22+00:00
- Post Title: 斗战神-DZS (.vfs)

Worked on a bit and now I know that it's using zlib for compression 

I have avatarinfo.xml decompressed
