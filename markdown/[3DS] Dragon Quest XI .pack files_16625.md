## Post #1
- Username: Drwho94
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 02, 2017 3:50 am
- Post datetime: 2017-08-01T19:53:46+00:00
- Post Title: [3DS] Dragon Quest XI .pack files

Not sure how to open these ones. Tried the two BMS scripts for .pack and had no luck. 

If it helps here is one of them opened in HxD.


The text is stored in these ones thats why I ask.
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-08-01T21:31:54+00:00
- Post Title: [3DS] Dragon Quest XI .pack files

Can you upload multiple samples? gdkchan sent me two, but we need multiple to confirm the format is correct.
## Post #3
- Username: Drwho94
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 02, 2017 3:50 am
- Post datetime: 2017-08-01T21:48:28+00:00
- Post Title: [3DS] Dragon Quest XI .pack files

> Reply from Anexenaumoon
>
> Can you upload multiple samples? gdkchan sent me two, but we need multiple to confirm the format is correct.

Sure here are some examples:
[https://mega.nz/#F!K1si2bZK!99zw94MNDJidv1FxhXAFGQ](https://mega.nz/#F!K1si2bZK!99zw94MNDJidv1FxhXAFGQ)
## Post #4
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-08-05T21:17:48+00:00
- Post Title: [3DS] Dragon Quest XI .pack files

I can't seem to figure out the compression type on the compressed ones labeled "PACA". It's apparently some sort of LZ variant, but I just don't know the type of it. This script portion will unpack the uncompressed "PACK" .pack files:

```

if ID == "PACK" 
get ARKSIZE long
get VER short
get ENDIANESS short
get FCOUNT short
getdstring NULL 0xA
get HEADER long
goto HEADER
get ETABLELN long
math ETABLELN - 0x4
savepos DATASTART

for i = 0 < FCOUNT
get SIZE long
putarray 0 i SIZE
get NAME string
putarray 1 i NAME
next i

savepos DATAEND
xmath PADDING "ETABLELN - (DATAEND - DATASTART)"
getdstring PAD PADDING
savepos OFFSET


for i = 0 < FCOUNT
getarray SIZE 0 i
getarray NAME 1 i
log NAME OFFSET SIZE
math OFFSET + SIZE
next i


elif ID == "PACA"



endif

```

Wasn't sure if any of the uncompressed ones held multiple files, so I accounted for that just in case.
## Post #5
- Username: Drwho94
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 02, 2017 3:50 am
- Post datetime: 2017-08-06T20:39:23+00:00
- Post Title: [3DS] Dragon Quest XI .pack files

> Reply from Anexenaumoon
>
> I can't seem to figure out the compression type on the compressed ones labeled "PACA". It's apparently some sort of LZ variant, but I just don't know the type of it. This script portion will unpack the uncompressed "PACK" .pack files:
Code: Select allgetdstring ID 0x4

if ID == "PACK" 
get ARKSIZE long
get VER short
get ENDIANESS short
get FCOUNT short
getdstring NULL 0xA
get HEADER long
goto HEADER
get ETABLELN long
math ETABLELN - 0x4
savepos DATASTART

for i = 0 < FCOUNT
get SIZE long
putarray 0 i SIZE
get NAME string
putarray 1 i NAME
next i

savepos DATAEND
xmath PADDING "ETABLELN - (DATAEND - DATASTART)"
getdstring PAD PADDING
savepos OFFSET


for i = 0 < FCOUNT
getarray SIZE 0 i
getarray NAME 1 i
log NAME OFFSET SIZE
math OFFSET + SIZE
next i


elif ID == "PACA"



endif

Wasn't sure if any of the uncompressed ones held multiple files, so I accounted for that just in case.

I appreciate it. I tried using quickbms and it's working on files in images_cs.
I hope we can crack the PACA ones!
