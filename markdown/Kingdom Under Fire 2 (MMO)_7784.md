## Post #1
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-01T03:06:55+00:00
- Post Title: Kingdom Under Fire 2 (MMO)

Here is a quickbms script to extract and decrypt these game pkg files.

```
get tablesize long
for
FileXor ""
get xor byte
get nsize byte
getdstring name nsize
get offset long
get size long
FileXor xor
log name offset size
savepos tmp
if tmp == tablesize
cleanexit
endif
next

```


Client download can be got from here

> http://115.com/file/anh3l97h
>
> http://115.com/file/anh3l4ez
>
> http://115.com/file/be85e52x
>
> http://115.com/file/e7zu6y9o
>
> http://115.com/file/dpxcnchk
## Post #2
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-12-01T11:33:55+00:00
- Post Title: Kingdom Under Fire 2 (MMO)

Awesome! Thank you chrrox!  i've been waiting for this for ages. i hope you'll release a script for importing models very soon.
## Post #3
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2014-01-16T11:40:19+00:00
- Post Title: Kingdom Under Fire 2 (MMO)

Hello, 
the bms  above doesn't work anymore with pkg files from the latest beta client.
You can find more détails and links in my post here 

[viewtopic.php?p=91623#p91623](http://forum.xentax.com/viewtopic.php?p=91623#p91623)

Thank you
## Post #4
- Username: zhade
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 16, 2011 5:51 am
- Post datetime: 2014-01-21T23:22:00+00:00
- Post Title: Kingdom Under Fire 2 (MMO)

Tested on a few files with patch 10006 and rev.255444

```
idstring "BEAR"
get BNAME basename
string BNAME += "/"
get DUMMY long
get FILES long
get DUMMY long
set EMPTY 65536
for i = 0 < FILES
    get DUMMY long
    get DUMMY long
    get ZSIZE long
    get SIZE long
    get START long
    get DUMMY long
    xmath START "16+(FILES*24)+(START*8)"
    savepos NEXTFILE
    goto START
    log TEMPORARY_FILE 0 0
    append
    do
        get OFFSET long
        get CZSIZE short
        get CSIZE short
        if CSIZE == 0
             if CZSIZE == 0
                 log TEMPORARY_FILE OFFSET EMPTY
             else
                 clog TEMPORARY_FILE OFFSET CZSIZE EMPTY
             endif
        else
            if CZSIZE == 0
                log TEMPORARY_FILE OFFSET CSIZE
            else
                clog TEMPORARY_FILE OFFSET CZSIZE CSIZE
            endif
        endif
    while CSIZE == 0
    append
    open "." TEMPORARY_FILE 1
    get FILESIZE asize 1
    log BNAME 0 FILESIZE 1
    goto NEXTFILE
next i

```
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-01-22T01:52:08+00:00
- Post Title: Kingdom Under Fire 2 (MMO)

The game uses hashes so the file names have to be dumped from the exe to much of  a pain to do.
Thats why i have not posted anything the compression is just zlib.
## Post #6
- Username: zhade
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 16, 2011 5:51 am
- Post datetime: 2014-01-24T15:47:16+00:00
- Post Title: Kingdom Under Fire 2 (MMO)

I see.
I edited my post above and included a bms script that is able to extract the files. I haven't done any bms scripts before, so if it can be optimized feel free to edit.
