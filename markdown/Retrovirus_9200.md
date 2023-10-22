## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-03T17:50:02+00:00
- Post Title: Retrovirus

```
# script for QuickBMS http://quickbms.aluigi.org

for
    get NAMESZ byte
    if NAMESZ == 0
        cleanexit
    endif
    getdstring NAME NAMESZ
    get OFFSET longlong
    savepos TMP_OFF

    get TMP byte
    if TMP == 0
        get SIZE asize
    else
        getdstring TMP TMP
        get SIZE longlong
    endif
    goto TMP_OFF

    math SIZE -= OFFSET
    log NAME OFFSET SIZE
next
```
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-02-07T06:48:52+00:00
- Post Title: Retrovirus

Hi, thanks the the bms, it creates the folders and subfolders but not extract the files, only i get a big file.
Thanks.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-06T13:42:35+00:00
- Post Title: Retrovirus

do you have a sample file that doesn't work with the script?
## Post #4
- Username: Controller
- Rank: n00b
- Number of posts: 11
- Joined date: Mon May 25, 2009 8:44 am
- Post datetime: 2021-01-27T10:37:43+00:00
- Post Title: Retrovirus

Seems there is another version of Retrovirus dat files. Only difference is the data size is added, making the parsing a little easier.
Works for all .dat files except except Entities.dat (which is an executable, dll or something alike)
However there is some issue with this set of files for some of the archive files (must be named manually):



```
# script for QuickBMS http://quickbms.aluigi.org
# Updated: Format additionally has the size of the data stored! (updated by Jan Vorel)

for
    get NAMESZ byte
    if NAMESZ == 0
        cleanexit
    endif
    getdstring NAME NAMESZ
    get OFFSET longlong
    get SIZE longlong
    log NAME OFFSET SIZE
next

```
