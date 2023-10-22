## Post #1
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2021-12-12T02:31:30+00:00
- Post Title: Final Fantasy VIII: Remastered Android OBB [BMS]

Structure:

```
file[fileCount]

file:
uint strLen
char[strLen] path
uint64 filePtrAbs;
uint32 fileSize
```


BMS:

```
get FILES long
for i = 0 < FILES
    get NAMESZ long
    getdstring NAME NAMESZ
    get OFFSET longlong
    get SIZE long
    log NAME OFFSET SIZE
next i

```
