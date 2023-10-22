## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-04-28T13:27:39+00:00
- Post Title: Love Chronicles: The Spell - Archive

I'll appreciate any help or guidance to unpack the "*.vst"-archive from the "Love Chronicles" game. 
The head.bin and tail.bin may be downloaded here: [http://www.motionpress.com/uploads/Love ... adTail.rar](http://www.motionpress.com/uploads/LoveChroniclesTheSpellHeadTail.rar)

Thanks in advance!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-28T13:41:08+00:00
- Post Title: Love Chronicles: The Spell - Archive

I can't test it but should work:

```

comtype unzip_dynamic
goto -4
get OFFSET long
goto OFFSET
get FILES long
for i = 0 < FILES
    get NAMESZ long
    getdstring NAME NAMESZ
    get OFFSET long
    get ZSIZE long
    clog NAME OFFSET ZSIZE ZSIZE
next i
```
