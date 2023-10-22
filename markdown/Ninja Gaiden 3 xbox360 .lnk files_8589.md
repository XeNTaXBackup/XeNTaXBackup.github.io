## Post #1
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-19T02:43:01+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

Deleted due to the new rules.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-19T10:58:49+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

the file you uploaded is just an index file
## Post #3
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-19T18:20:52+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

Deleted due to the new rules.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-20T00:04:37+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

they use a modified version of the model format they used last time with he same tmc header.
also you can extract the files with offzip as they used zlib compression ill work on figuring out the correct way to get files but this will work if you want to look before then.
## Post #5
- Username: terios
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 14, 2010 10:24 am
- Post datetime: 2012-03-22T06:17:30+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

The DOA5 demo that comes with NG3 also appears to use this format. I was unable to extract the data with the method you described, perhaps my command was incorrect, but would you be willing to look at this as well? You can find the single .lnk file along with it's archive data [here](http://home.comcast.net/~doa7/d5.7z).
## Post #6
- Username: terios
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-22T10:21:03+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

the files are uncompressed in the demo that is the reason offzip does not work.
Anyway I should be able to find some time bye the weekend to post an extractor script if no one else does by then.

this will extract the .lnk files without original names for now.

```
idstring "D5TX"
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
if zsize == size
log "" offset size
else
clog "" offset zsize size
endif
next i
```
## Post #7
- Username: terios
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-22T23:15:18+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

this will extract the files with names just hit r if it mentions a duplicate file name.
its not perfect yet not sure what exactly is going on if someone else wants to look at it feel free.

```
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 id name
next i
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
getarray name 0 i
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i
```
## Post #8
- Username: terios
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-24T13:37:17+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

this will get the correct names they skip a file name for some reason.

```
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 i name
next i
getarray name 0 0
putarray 0 files name
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
set id i
math id + 1
getarray name 0 id
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i

```
## Post #9
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-04-11T18:31:43+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

> Reply from chrrox
>
> this will get the correct names they skip a file name for some reason.
Code: Select allendian BIG
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 i name
next i
getarray name 0 0
putarray 0 files name
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
set id i
math id + 1
getarray name 0 id
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i

hi chrrox, for an unknown reason i receive an error from the quickbms script. What version of quickbms do you use?
the erros is : error in src \ file.h line 187 myf open <>   ..... Error no such file or directory. I've never found this type of error and the ink archive is not damaged.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-11T18:44:16+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

You are most likely not using quickbms correctly.
## Post #11
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-29T21:30:41+00:00
- Post Title: Ninja Gaiden 3 xbox360 .lnk files

> Reply from Ares722
>
> chrrox wrote:this will get the correct names they skip a file name for some reason.
Code: Select allendian BIG
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 i name
next i
getarray name 0 0
putarray 0 files name
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
set id i
math id + 1
getarray name 0 id
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i


hi chrrox, for an unknown reason i receive an error from the quickbms script. What version of quickbms do you use?
the erros is : error in src \ file.h line 187 myf open <>   ..... Error no such file or directory. I've never found this type of error and the ink archive is not damaged.

I am try extract files frol DOA5 and appear for me the same error.
