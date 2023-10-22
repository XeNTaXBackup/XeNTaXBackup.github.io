## Post #1
- Username: EIREXE
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 16, 2012 1:29 am
- Post datetime: 2015-09-17T13:59:52+00:00
- Post Title: Shrek SuperSlam gamecube MASTER.DIR and MASTER.DAT

Hello there, I'm trying to extract the files from this game, I found some threads dating back to 2007 and one from 2009 that contained a tool that could uncompress extracted files,  I have not found a way to extract the files though, which is very weird.

It seems to be split into two parts, the MASTER.DIR that contains file paths and probably where they are located and the MASTER.DAT that contains the actual content, since I can post the whole files, here are a few samples:

MASTER.DIR header and when file paths start:
[http://i.imgur.com/dpmhTAy.png](http://i.imgur.com/dpmhTAy.png)
[http://i.imgur.com/LtnYgMl.png](http://i.imgur.com/LtnYgMl.png)

MASTER.DAT

[http://i.imgur.com/eqlhndp.png](http://i.imgur.com/eqlhndp.png)

Chances are the engine for this game could have been reused, anyone recognise this files?
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-09-18T21:36:53+00:00
- Post Title: Shrek SuperSlam gamecube MASTER.DIR and MASTER.DAT

You can always upload the files somewhere else and point here, OR use the FileCutter to upload snippets. Here are some options: [viewtopic.php?f=10&t=6747](http://forum.xentax.com/viewtopic.php?f=10&t=6747)
## Post #3
- Username: EIREXE
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 16, 2012 1:29 am
- Post datetime: 2015-09-18T23:34:23+00:00
- Post Title: Shrek SuperSlam gamecube MASTER.DIR and MASTER.DAT

> Reply from Mr.Mouse
>
> You can always upload the files somewhere else and point here, OR use the FileCutter to upload snippets. Here are some options: viewtopic.php?f=10&t=6747
The file is very big and contains all the game's assets, wouldn't that be warez?
## Post #4
- Username: OperateSystemP
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 04, 2015 9:26 am
- Post datetime: 2015-09-18T23:40:40+00:00
- Post Title: Shrek SuperSlam gamecube MASTER.DIR and MASTER.DAT

> Reply from EIREXE
>
> Mr.Mouse wrote:You can always upload the files somewhere else and point here, OR use the FileCutter to upload snippets. Here are some options: viewtopic.php?f=10&t=6747
The file is very big and contains all the game's assets, wouldn't that be warez?
Warez is the entire game in a disc format. You can post files from the game as long as its not the entire game itself.
## Post #5
- Username: EIREXE
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 16, 2012 1:29 am
- Post datetime: 2015-11-14T12:17:37+00:00
- Post Title: Shrek SuperSlam gamecube MASTER.DIR and MASTER.DAT

> Reply from OperateSystemP
>
> EIREXE wrote:Mr.Mouse wrote:You can always upload the files somewhere else and point here, OR use the FileCutter to upload snippets. Here are some options: viewtopic.php?f=10&t=6747
The file is very big and contains all the game's assets, wouldn't that be warez?
Warez is the entire game in a disc format. You can post files from the game as long as its not the entire game itself.

Sorry for the terribly late answer, but here are the files:

[https://mega.nz/#!CU1B1Qba!zSRUqwPa5hGU ... bwoYg21c2o](https://mega.nz/#!CU1B1Qba!zSRUqwPa5hGULtgpJJltR0NAqDuG1bk4ebwoYg21c2o)
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-14T13:18:41+00:00
- Post Title: Shrek SuperSlam gamecube MASTER.DIR and MASTER.DAT

```
# Written by Ekey (h4x0r)
# script for QuickBMS http://quickbms.aluigi.org

open FDDE "dat" 0
open FDDE "dir" 1

get DSIZE asize 1
endian big

for
   if END_POS == DSIZE
      cleanexit
   endif
   
   get ENTRY_OFFSET long 1
   savepos TEMP 1
   goto ENTRY_OFFSET 1
   get OFFSET long 1
   get SIZE long 1
   get ZSIZE long 1
   get NAME string 1
   savepos END_POS 1
   
   if ZSIZE == SIZE
       log NAME OFFSET SIZE 0
   else
       #clog NAME OFFSET ZSIZE SIZE 0
       log NAME OFFSET ZSIZE 0
   endif
   goto TEMP 1
next

```


Unknown compression method
## Post #7
- Username: EIREXE
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 16, 2012 1:29 am
- Post datetime: 2015-11-20T18:45:12+00:00
- Post Title: Shrek SuperSlam gamecube MASTER.DIR and MASTER.DAT

> Reply from Ekey
>
> Code: Select all# Shrek SuperSlam (GameCube) (DIR/DAT format)
# Written by Ekey (h4x0r)
# script for QuickBMS http://quickbms.aluigi.org

open FDDE "dat" 0
open FDDE "dir" 1

get DSIZE asize 1
endian big

for
   if END_POS == DSIZE
      cleanexit
   endif
   
   get ENTRY_OFFSET long 1
   savepos TEMP 1
   goto ENTRY_OFFSET 1
   get OFFSET long 1
   get SIZE long 1
   get ZSIZE long 1
   get NAME string 1
   savepos END_POS 1
   
   if ZSIZE == SIZE
       log NAME OFFSET SIZE 0
   else
       #clog NAME OFFSET ZSIZE SIZE 0
       log NAME OFFSET ZSIZE 0
   endif
   goto TEMP 1
next


Unknown compression method

Thanks!
