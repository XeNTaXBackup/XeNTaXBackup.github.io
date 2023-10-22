## Post #1
- Username: slush
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 24, 2007 8:04 am
- Post datetime: 2007-04-24T12:19:34+00:00
- Post Title: Final Fantasy 1 for PSP (*.dpk)

Hello i was wondering if there is any extractor for ff1's dpk file. Unfortuneatly there is only one big .dpk file in the game and it's 100MiB big so i had to use that filecutter anyways.

It seems to only contain "F1 07" at the start, after that it begins to list all the files in the archive.

Which looks like this: (9) - (00) - (3) - (00) - (21 - filename) - (00)
so it has 36 "chunks"

the first one looks like this:

```

..0H..........SE000.NPK.............
```


while the 2nd one look like this

```

?.@×>.PÉ..PÉ..SE001.NPK.K...........
```


im not sure if this got included in the zip but it seems like every file ends with something like 

```
ss0000.bmp.test2.Wed Feb 21 19:19:ÿ...37 2007.GimConv 1.40
```


Since the filesize was too big for the zip i uploaded it at my site [ff1psp.dpk.zip (1.4MiB)](http://4chan.eu/ff1psp.dpk.zip)

The file contains .gim files (i think one is included on the head.bin)
If you want to test them out use [this gim/mig to bmp](http://pspdum.my.land.to/files/gim2bmp_070414.zip) extract it somewhere and put the files you want to convert in /convfiles/ and run the bat (i think, not really sure since its japanese and i dont have any gim to test it on)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-03T05:54:12+00:00
- Post Title: Final Fantasy 1 for PSP (*.dpk)

I've taken a look at them,haven't come up with anything useful yet.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-07-03T08:53:49+00:00
- Post Title: Final Fantasy 1 for PSP (*.dpk)

byte 7-10 and 11-14(same value) looks like a offset value in Big-Endian

I want to take a look as well, but the link above is not working!
## Post #4
- Username: samwh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 25, 2007 8:13 am
- Post datetime: 2007-07-27T02:24:33+00:00
- Post Title: Final Fantasy 1 for PSP (*.dpk)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2009-05-03T22:14:28+00:00
- Post Title: Final Fantasy 1 for PSP (*.dpk)

Ah, this is something I've been wondering about as well. I've wanted to extract sprites from this game but everything is compressed into one big .dpk file. It'd be very nice if someone could figure this out for us.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-04T10:53:39+00:00
- Post Title: Final Fantasy 1 for PSP (*.dpk)

the extraction of the files is not a problem, for example the following script does the job:

```
get FULLSIZE long
get DUMMY long
get DUMMY long

for i = 0 < FILES
    getdstring NAME 24
    get OFFSET long
    get ZSIZE long
    get SIZE long

    if ZSIZE != SIZE
        # Wp16 compression not supported, file is saved in compressed form
        log NAME OFFSET ZSIZE
    else
        log NAME OFFSET SIZE
    endif
next i
```
(note that the PCK and NPK files are just other archives like DPK so must be extracted in the same way).

the real problem is the so called "Wp16" compression, which is not clear.
these compressed files start with the "Wp16" signature, followed by the 32 bit uncompressed size and (probably) the raw compressed data.

so as final solution the following script extracts directly ANY file (gim and music files) from the non-compressed archives in the dpk file:

```

get FILES long
get FULLSIZE long
get DUMMY long
get DUMMY long

for i = 0 < FILES
    getdstring NAME 24
    get PCK_OFFSET long
    get ZSIZE long
    get SIZE long
    savepos INFO_OFFSET

    if ZSIZE != SIZE
        # skip the compressed Wp16 archives (not supported)
    else
        goto PCK_OFFSET

        get XFILES long
        get FULLSIZE long
        get DUMMY long
        get DUMMY long
        for j = 0 < XFILES
            getdstring NAME 24
            get OFFSET long
            get ZSIZE long
            get SIZE long

            math OFFSET += PCK_OFFSET
            log NAME OFFSET SIZE
        next j
    endif

    goto INFO_OFFSET
next i
```
usage: quickbms script.bms ff1psp.dpk output_folder
## Post #7
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-08-20T18:45:07+00:00
- Post Title: Final Fantasy 1 for PSP (*.dpk)

Sorry to necropost if I am, but I've been looking for a batch script that extracts both .npk and .pck files from this archive. The script above extracts most things, but it's still missing vital graphics files, which I am primarily concerned with.
## Post #8
- Username: LordSith
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 16, 2012 2:55 am
- Post datetime: 2012-04-16T14:20:36+00:00
- Post Title: Final Fantasy 1 for PSP (*.dpk)

> Reply from Doctor Loboto
>
> Sorry to necropost if I am, but I've been looking for a batch script that extracts both .npk and .pck files from this archive. The script above extracts most things, but it's still missing vital graphics files, which I am primarily concerned with.

sorry to necropost but did you manage to extract those file (extracts both .npk and .pck files) from the Final Fantasy 1 package?
