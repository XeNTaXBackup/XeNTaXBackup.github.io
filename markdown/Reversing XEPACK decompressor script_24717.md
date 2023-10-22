## Post #1
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-11-09T14:02:22+00:00
- Post Title: Reversing XEPACK decompressor script

Hi everyone!
Guys, need your help. There is *XEPACK decompressor BMS script:

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


I need to reverse this code and make *XEPACK compressor BMS script..
Do you have any ideas how to do that??

p.s. here are samples of compressed and decompressed *XEPACK files
[https://mega.nz/folder/xE00lB7S#lk3fYxOrWDFPWNYcIAlYYw](https://mega.nz/folder/xE00lB7S#lk3fYxOrWDFPWNYcIAlYYw)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-09T21:49:33+00:00
- Post Title: Reversing XEPACK decompressor script

> Do you have any ideas how to do that??
Well, you need quickbms documentation [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
and source code [http://aluigi.zenhax.com/papers/quickbms-src-0.11.0.zip](http://aluigi.zenhax.com/papers/quickbms-src-0.11.0.zip)

Check also some tutorials from this list [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

Good luck
## Post #3
- Username: likedonkey
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 18, 2021 2:09 pm
- Post datetime: 2022-01-22T09:59:29+00:00
- Post Title: Reversing XEPACK decompressor script

Do u know about script for decompressing your packed file?
As aluigi said, you must see the document.
The older script is opened already.
But new bms must be used for new packed.
