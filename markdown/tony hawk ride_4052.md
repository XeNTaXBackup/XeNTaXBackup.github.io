## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2010-01-17T02:55:24+00:00
- Post Title: tony hawk ride

hey could anyone make a extractor/packer for this file please, it doesnt seem to be compressed and you can plainly see all the files one after another, looks like the offsets of each file are stored at the start followed by a list of all their names. 

Thanks.
[scripts.rar](https://xentaxbackup.github.io/file/2729_scripts.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-17T11:25:09+00:00
- Post Title: tony hawk ride

```

endian big
idstring "PAK\0"
get DUMMY short
get DUMMY short
get FILES long
get NAME_SIZE long

math OFFSET = FILES
math OFFSET *= 24
math OFFSET += 0x10
log MEMORY_FILE OFFSET NAME_SIZE

for i = 0 < FILES
    get CRC long
    get NAME_OFF long
    get DUMMY long
    get DUMMY long
    get OFFSET long
    get SIZE long

    goto NAME_OFF MEMORY_FILE
    get NAME string MEMORY_FILE

    log NAME OFFSET SIZE
next i
```
