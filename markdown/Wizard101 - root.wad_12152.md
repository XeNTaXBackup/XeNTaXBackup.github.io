## Post #1
- Username: Zedek
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 24, 2014 9:06 pm
- Post datetime: 2014-10-24T13:33:01+00:00
- Post Title: Wizard101 - root.wad

Years ago, someone posted [this thread](http://forum.xentax.com/viewtopic.php?f=10&t=4434) asking about Wizard101's wad files, and while the answer was most helpful, there's still a problem extracting root.wad. This is the error message I get when trying with that script:



Also, [here](http://www.megafileupload.com/en/file/573902/Root-wad.html) is the root.wad file.
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-10-24T14:32:14+00:00
- Post Title: Wizard101 - root.wad

```
get DUMMY long
get FILES long
get DUMMY byte     # fix for root.wad
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get ZSIZE long
    get DUMMY byte
    get ZIP long
    get NAMESZ long
    getdstring NAME NAMESZ
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

```


Result of extraction
## Post #3
- Username: Zedek
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 24, 2014 9:06 pm
- Post datetime: 2014-10-24T14:49:02+00:00
- Post Title: Wizard101 - root.wad

That worked. Thank you.
