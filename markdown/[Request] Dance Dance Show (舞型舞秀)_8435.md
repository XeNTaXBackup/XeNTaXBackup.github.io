## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-29T07:18:24+00:00
- Post Title: [Request] Dance Dance Show (舞型舞秀)

Format: PAK



[Dance Dance Show Archive Research](http://www.mediafire.com/download.php?d7abjwmdihyf6bo)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-29T14:39:12+00:00
- Post Title: [Request] Dance Dance Show (舞型舞秀)

Cute models. Hope it's not 2d
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-29T15:52:14+00:00
- Post Title: [Request] Dance Dance Show (舞型舞秀)

let me know if the size of the extracted folder is equal or almost close to the one of the archive because I don't know if FILES is really the number of files being a sequential archive:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "FileEnt\0"
get DUMMY long
get DUMMY long
get FILES long
get OFFSET long
for i = 0 < FILES
    goto OFFSET
    get SIZE long
    getdstring NAME 0x10c
    savepos OFFSET
    log NAME OFFSET SIZE
    math OFFSET += SIZE
next i
```
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-29T17:05:47+00:00
- Post Title: [Request] Dance Dance Show (舞型舞秀)

thanks a lot aluigi, now let me know, when get it? just overwrite files? or what do?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-29T17:08:57+00:00
- Post Title: [Request] Dance Dance Show (舞型舞秀)

use 'r', it will automatically rename all the subsequent files with same name.
I don't know why they make archives with duplicated filenames, maybe they are like older and newer versions of the file
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-29T17:43:24+00:00
- Post Title: [Request] Dance Dance Show (舞型舞秀)

ok thanks a lot aluigi again, really you help me a lot, here some samples of files 

Format: Gamebryo 20.5.0.0
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-29T17:54:34+00:00
- Post Title: [Request] Dance Dance Show (舞型舞秀)

> Reply from aluigi
>
> use 'r', it will automatically rename all the subsequent files with same name.
I don't know why they make archives with duplicated filenames, maybe they are like older and newer versions of the file

Is it possible that there is some directory structure?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-29T21:17:25+00:00
- Post Title: [Request] Dance Dance Show (舞型舞秀)

no, the filenames already contain directories
