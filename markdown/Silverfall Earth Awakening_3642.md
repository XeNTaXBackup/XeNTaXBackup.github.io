## Post #1
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-08-09T17:26:37+00:00
- Post Title: Silverfall Earth Awakening

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-09T18:10:47+00:00
- Post Title: Silverfall Earth Awakening

try this quick bms script it will error at the end but thats fine I just don;t know how many files are in each archive.

```
for i = 0 < FILES
getdstring NULL 0x12
get ZSIZE long
get SIZE long
get NSIZE long
getdstring NAME NSIZE
savepos OFFSET
log NAME OFFSET SIZE
math OFFSET += SIZE
goto OFFSET
next i
cleanexit
```

[item_donj_dirz_machines2item_donj_dirz_machines2_spec.JPG](https://xentaxbackup.github.io/file/2268_item_donj_dirz_machines2item_donj_dirz_machines2_spec.JPG)
## Post #3
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-08-09T19:00:31+00:00
- Post Title: Silverfall Earth Awakening

Thanks
## Post #4
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-08-09T23:57:02+00:00
- Post Title: Silverfall Earth Awakening

Hi there, you could also try this: [http://www.moddb.com/games/silverfall/d ... 00-by-elys](http://www.moddb.com/games/silverfall/downloads/silverfall-unpacker-v0200-by-elys)

I was able to unpack archives from Silverfall and Earth Awakening.
