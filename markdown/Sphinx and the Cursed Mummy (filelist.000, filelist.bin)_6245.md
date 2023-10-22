## Post #1
- Username: darkjak
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 19, 2011 10:00 pm
- Post datetime: 2011-03-19T15:15:51+00:00
- Post Title: Sphinx and the Cursed Mummy (filelist.000, filelist.bin)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-19T17:28:47+00:00
- Post Title: Sphinx and the Cursed Mummy (filelist.000, filelist.bin)

script for QuickBMS:

```
#   other Eurocom games?
#   http://en.wikipedia.org/wiki/Eurocom
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

open FDDE "bin" 0

get DUMMY long
get BINSZ long
get FILES long
get DUMMY long
get DUMMY_OFF long

math NAME_OFF = FILES
math NAME_OFF *= 4
math NAME_OFF += 16
math NAME_OFF += DUMMY_OFF
math NAME_SIZE = BINSZ
math NAME_SIZE -= NAME_OFF
log MEMORY_FILE NAME_OFF NAME_SIZE

set OLD_EXT long -1
for i = 0 < FILES
savepos XXX
    get SIZE long
    get FLAGS1 long
    get FLAGS2 long
    get FLAGS3 long
    get FLAGS4 long
    get OFFSET long
    get EXT long
    if EXT != OLD_EXT
        string TMP p= "%03d" EXT
        open FDDE TMP 1
        set OLD_EXT long EXT
    endif
    for j = 1 < FLAGS4
        get DUMMY long
        get DUMMY long
    next j
    get NAME string MEMORY_FILE
    log NAME OFFSET SIZE 1
next i
```

I guess it's not much possible to write a script for any Eurocom game mainly because some of them (like Vancouver) have a file format that is not much clear and others (G-Force) use encryption.
in short would be necessary to have all the bin/000 files of the Eurocom games for making something more generic but it's enough hard
## Post #3
- Username: darkjak
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 19, 2011 10:00 pm
- Post datetime: 2011-03-19T21:04:20+00:00
- Post Title: Sphinx and the Cursed Mummy (filelist.000, filelist.bin)

The contents of this post was deleted because of possible forum rules violation.
