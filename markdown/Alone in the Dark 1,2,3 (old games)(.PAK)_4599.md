## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-06-13T05:26:42+00:00
- Post Title: Alone in the Dark 1,2,3 (old games)(.PAK)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-14T15:37:06+00:00
- Post Title: Alone in the Dark 1,2,3 (old games)(.PAK)

unknown compression algorithm, in some files it's tagged as pkware explode but it's not correct.
only for informative reasons I post the script that DOESN'T WORK:

```

set TMP long 0x7fffffff
get DUMMY long
for i = 0
    savepos TMP_OFF
    if TMP_OFF >= TMP
        break
    endif
    get OFFSET long
    putarray 0 i OFFSET
    if OFFSET < TMP
        math TMP = OFFSET
    endif
next i
math FILES = i

for i = 0 < FILES
    getarray OFFSET 0 i

    savepos TMP
    goto OFFSET
    get DUMMY long
    get ZSIZE long
    get SIZE long
    get DUMMY long
    savepos OFFSET
    goto TMP

    clog "" OFFSET ZSIZE SIZE
next i
```
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-15T14:30:17+00:00
- Post Title: Alone in the Dark 1,2,3 (old games)(.PAK)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-06-15T14:41:34+00:00
- Post Title: Alone in the Dark 1,2,3 (old games)(.PAK)

The contents of this post was deleted because of possible forum rules violation.
[AloneintheDarkTestFilesPlusAboutPAKStructure.rar](https://xentaxbackup.github.io/file/3146_AloneintheDarkTestFilesPlusAboutPAKStructure.rar)
## Post #5
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2010-06-15T18:22:30+00:00
- Post Title: Alone in the Dark 1,2,3 (old games)(.PAK)

Try this: [http://www.extractor.ru/ipb/index.php?showtopic=2030](http://www.extractor.ru/ipb/index.php?showtopic=2030)
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-06-16T09:25:00+00:00
- Post Title: Alone in the Dark 1,2,3 (old games)(.PAK)

Tried, but not so: to all files expansion is attributed .out
And it seems to me data change, as unpacker it is based on port source codes Free in the Dark on soundforge.

Therefore also has made this topic for the purpose of creation normal unpacker and has involved in it aluigi, which can make bms script for unpacking.
## Post #7
- Username: jomalin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 29, 2010 2:11 pm
- Post datetime: 2015-05-07T10:49:09+00:00
- Post Title: Alone in the Dark 1,2,3 (old games)(.PAK)

Now PAK files from Alone in the dark are supported in QuickBMS using "pak_explode" decompression algorithm
See the script:
[http://aluigi.altervista.org/papers/bms/alonedark.bms](http://aluigi.altervista.org/papers/bms/alonedark.bms)
## Post #8
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-08-15T16:41:24+00:00
- Post Title: Alone in the Dark 1,2,3 (old games)(.PAK)

It seems I can't reimport them with reimport.bat, it always writes an error to me. Any ideas?

EDIT: It says:

Error: Unsupported compression 176 in reimport mode

Last script line before the error or that produced the error:
37 clog NAME OFFSET discSize uncompressedSize
