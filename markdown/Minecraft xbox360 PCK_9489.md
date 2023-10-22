## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T18:51:45+00:00
- Post Title: Minecraft xbox360 PCK

tested with Minecraft skins1.pck of the DLC:

```
#   tested with skins1.pck
# script for QuickBMS http://quickbms.aluigi.org

endian big
get DUMMY long
get NAMES long
for i = 0 < NAMES
    get DUMMY long
    get NAMESZ long
    math NAMESZ *= 2
    getdstring NAME NAMESZ
    set NAME unicode NAME
    get DUMMY long
next i

savepos INFO_OFF
for EXTRACT = 0 < 2
    goto INFO_OFF
    get FILES long
    for i = 0 < FILES
        get SIZE long
        get DUMMY long
        get NAMESZ long
        math NAMESZ *= 2
        getdstring NAME NAMESZ
        set NAME unicode NAME
        get DUMMY long
        if EXTRACT != 0
            set FNAME string NAME

            savepos TMP
            goto OFFSET
            get ENTRIES long
            for j = 0 < ENTRIES
                get DUMMY long
                get NAMESZ long
                math NAMESZ *= 2
                getdstring NAME NAMESZ
                set NAME unicode NAME
                get DUMMY long
            next j
            savepos OFFSET
            goto TMP

            log FNAME OFFSET SIZE
            math OFFSET += SIZE
        endif
    next i
    savepos OFFSET
next EXTRACT
```
## Post #2
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-15T20:22:47+00:00
- Post Title: Minecraft xbox360 PCK

hey  do you know of any pck repackers ?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T20:44:48+00:00
- Post Title: Minecraft xbox360 PCK

you can use the reimport feature of quickbms if your new file has the same size or smaller than the original one (section 3 of quickbms.txt)
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-15T22:57:42+00:00
- Post Title: Minecraft xbox360 PCK

okay that worked thanks you soo much
## Post #5
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2014-06-10T18:03:09+00:00
- Post Title: Minecraft xbox360 PCK

This script isn't detecting the end of file names correctly in the latest PCK files released, so they have to be manually corrected. This is only a minor issue, just thought you should know aluigi.
Thanks for the script though, I've archived every DLC skin for use with the PC version.
## Post #6
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-06-23T13:53:40+00:00
- Post Title: Minecraft xbox360 PCK

hello  aluigi i just wanted to know if you can update the script i will pm you the small rar tonight

just in case anyone eles wants to try i will post it here
[https://www.mediafire.com/?rl8dby72s98z8qf](https://www.mediafire.com/?rl8dby72s98z8qf)
