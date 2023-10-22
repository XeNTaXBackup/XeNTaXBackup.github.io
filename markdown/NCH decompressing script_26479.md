## Post #1
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2023-02-16T17:47:36+00:00
- Post Title: NCH decompressing script

Hi everyone!

I got BMS script that uncompressing XEPACK archives from Spider-Man 3 the game (X360). But sometimes it doesn't work and throws an error:

```
Info:  algorithm   8
       offset      00280020
       input size  0x0007f3c5 521157
       output size 0x0007f3c5 521157
       result      0xffffffff -1

Error: the uncompressed data (-1) is bigger than the allocated buffer (892315)
       It usually means that data is not compressed or uses another algorithm
       
       Last script line before the error or that produced the error:
  27  clog MEMORY_FILE OFFSET ZSIZE SIZE
```


Could anyone tell what's wrong with it? Cause most of files I can decompress.

Here is the BMS script:

```
comtype lzo1x
get PCPACK_SIZE asize
log MEMORY_FILE 0 0
append 1
for i = 0
    savepos TMP_OFF
    if TMP_OFF == PCPACK_SIZE
        break
    endif
    idstring "NCH\0"
    get ZSIZE long
    get DUMMY_CRC long
    get SIZE long
    get XOFFSET long
    get DUMMY_CRC long
    get XSIZE long
    get ZIP long
    savepos OFFSET
    goto XOFFSET MEMORY_FILE
    if ZIP == 0
        log MEMORY_FILE OFFSET ZSIZE
    else
        clog MEMORY_FILE OFFSET ZSIZE SIZE
    endif
    math TMP_OFF + XSIZE
    goto TMP_OFF
    padding 0x1000
next i
append
get NAME basename
get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE
```


And here is some files that doesn't work with the script:
[https://mega.nz/file/kUdR0TqD#LVYkigvhm ... 4znQnYMBT4](https://mega.nz/file/kUdR0TqD#LVYkigvhmErwM84IuJ8ortwxAgIyvCkFA4znQnYMBT4)
