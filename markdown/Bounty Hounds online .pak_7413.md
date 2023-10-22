## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-24T16:59:20+00:00
- Post Title: Bounty Hounds online .pak

Here is a bms extractor
[http://en.bountyhounds.com/start/register](http://en.bountyhounds.com/start/register)


```
get files long
comtype LZMA_86DEC
for i = 0 < files
getdstring name 0x34
get offset long
get size long
get zsize long
if size == zsize
log name offset zsize
else
clog name offset zsize size
endif
next i

```
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-24T17:10:38+00:00
- Post Title: Bounty Hounds online .pak

[http://www.2shared.com/file/9BTKGoZN/extracted.html](http://www.2shared.com/file/9BTKGoZN/extracted.html)

The newer .nif file format so if someone (Szkaradek123 or some other guru) can look at it, would be fab. Tried with the catherine blender importer but get memory error
