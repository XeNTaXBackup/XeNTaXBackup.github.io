## Post #1
- Username: danny
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Apr 11, 2011 6:16 pm
- Post datetime: 2013-01-17T07:12:18+00:00
- Post Title: Dark arcane the carnnival  .cub file  help !

Hi i have a file called game_.cub but, i can  not decompress with the code for .cub archives:

filexor 0x96
idstring "cub\0"
get VER string
get FILES long
getdstring DUMMY 0x100
for i = 0 < FILES
    getdstring NAME 0x100
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-17T15:36:26+00:00
- Post Title: Dark arcane the carnnival  .cub file  help !

Files inside archive not xored 

```
get VER string
get FILES long
getdstring DUMMY 0x100
for i = 0 < FILES
 getdstring NAME 0x100
 get OFFSET long
 get SIZE long
 log NAME OFFSET SIZE
next i
```
