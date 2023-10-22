## Post #1
- Username: Mas
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 31, 2011 7:52 pm
- Post datetime: 2013-12-02T12:45:44+00:00
- Post Title: Script unpacks main but not individual archives (.DAT)

Hi, I'm using QuickBMS to try & extract .DAT archives from a game, it works on the main archives that hold shared 3D models, textures, sfx etc. but not on individual archives (for specific pieces of content).

When I try that it extracts some files, shows the filesize & names of others within QuickBMS but I get this message:
Error: the compressed zlib/deflate input is wrong or incomplete (-3)

Error: there is an error with the decompression
the returned output size is negative (-1)

Any idea's?  Using HxD I can't see much difference between the two archives, I've been told they might be encrypted based on a user key, but I'm not so sure having tried file(s) from other distributions and encountering the same problem.

Here's the script:

```
get DUMMY short
get INFO_SIZE long
get DUMMY long
savepos INFO_OFF
math INFO_SIZE += 10
for INFO_OFF = INFO_OFF < INFO_SIZE
    get DUMMY short
    get SIZE long
    get ZSIZE long
    get OFFSET long
    get NAMESZ byte
    getdstring NAME NAMESZ
    get DUMMY byte  # filename null del?
    if SIZE == ZSIZE
        log NAME OFFSET SIZE
    else
        math ZSIZE -= 8
        math OFFSET += 8
        clog NAME OFFSET ZSIZE SIZE
    endif
    savepos INFO_OFF
next
```

Cheers for any help
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-12-02T14:24:19+00:00
- Post Title: Script unpacks main but not individual archives (.DAT)

what game is it?
iracing_alpha ?
## Post #3
- Username: Mas
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 31, 2011 7:52 pm
- Post datetime: 2013-12-02T16:42:36+00:00
- Post Title: Script unpacks main but not individual archives (.DAT)

Yep.
