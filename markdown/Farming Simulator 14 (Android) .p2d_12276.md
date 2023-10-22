## Post #1
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-26T14:14:40+00:00
- Post Title: Farming Simulator 14 (Android) .p2d

Hello,
Does anyone recognize the compression on this texture file?
[https://www.sendspace.com/file/9o4pul](https://www.sendspace.com/file/9o4pul)

Thanks in advance.

EDIT: Figured it out. (p2d to pvr script)

```
string NAME += ".pvr"

idstring "\x0c\0\0\0"
get WIDTH    long
get HEIGHT   long
get MIPMAPS  long
get DUMMY    long

get SIZE asize
math SIZE -= 20

set MEMORY_FILE compressed eNp9w7ENAAAIAjAJDxoH/j+FDTabdHWcB7IMMl0A/w==

putvarchr MEMORY_FILE 8  6 long # stands for ETC1 RGB

putvarchr MEMORY_FILE 24 WIDTH   long
putvarchr MEMORY_FILE 28 HEIGHT  long
putvarchr MEMORY_FILE 44 MIPMAPS long

append
log MEMORY_FILE 20 SIZE
append

get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE
```
