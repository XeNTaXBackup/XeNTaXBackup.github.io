## Post #1
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-01T13:44:15+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-02T18:30:01+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

I saw that in the middle of the file is the file names within the wad, will I preciasr upload it to someone help me?

If so I up to 4GB, no problem, just wondering if anyone can help me.

Thanks.
## Post #3
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-19T11:04:51+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

can someone help me with it?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-19T11:16:07+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

just try the pc script only use the endian switch command in quickbms.
the command is in the readme of quickbms.
## Post #5
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-19T12:37:33+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

I am trying with this script.

[viewtopic.php?f=10&t=6505](http://forum.xentax.com/viewtopic.php?f=10&t=6505)

I switched the Apak LWAd to the 0x50 to 0x57.

only that the error intricately'm wrong?

then became so

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
idstring "LWAD"
get DUMMY long
get FILES long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get NAMES_SIZE long
get OFFSET1 long
get OFFSET2 long

math NAME_BASE = 0x57
math OFFSET3 = NAME_BASE
math OFFSET3 += NAMES_SIZE

for i = 0 < FILES
    goto OFFSET3
    getdstring DUMMY 0x14
    get NAME_OFF long
    getdstring DUMMY 0x14
    get SIZE long
    getdstring DUMMY 0x10
    savepos OFFSET3

    goto OFFSET1
    get NUM long
    get OFFSET long
    get DUMMY long
    get DUMMY long
    savepos OFFSET1

    math NAME_OFF += NAME_BASE
    goto NAME_OFF
    get NAME string
    goto TMP

    math OFFSET += OFFSET2
    log NAME OFFSET SIZE
next i
```
## Post #6
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-25T14:00:36+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

can someone help me with the script?

I do not know if this is indicated by the rick.

if anyone has the script for the PC please show me.
## Post #7
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-29T13:04:23+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

UP.
## Post #8
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T14:37:46+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

I here again, friends, has some way to extract this. WAD?
[GAMEDATA-edit.rar](https://xentaxbackup.github.io/file/5993_GAMEDATA-edit.rar)
## Post #9
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T19:13:49+00:00
- Post Title: Star Wars The Force Unleashed - .WAD PS3

Updates her > [viewtopic.php?f=10&t=6505](http://forum.xentax.com/viewtopic.php?f=10&t=6505)

New script extracts. wad
