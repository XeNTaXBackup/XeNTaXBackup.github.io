## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-04-28T12:33:03+00:00
- Post Title: Kuros - Archive

I'll appreciate any help or guidance to unpack the "*.boo"-archive of the Kuros game. 
The head.bin and tail.bin may be downloaded here: [http://www.motionpress.com/uploads/KurosHeadTail.rar](http://www.motionpress.com/uploads/KurosHeadTail.rar)

Thanks in advance!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-28T13:32:26+00:00
- Post Title: Kuros - Archive

```

comtype bzip2_file
set NAME string ""
set PATH string ""
get DUMMY long
get SUB_ENTRIES long
callfunction EXTRACT

startfunction EXTRACT
    string PATH += NAME
    string PATH += /
    set ENTRIES long SUB_ENTRIES
    for i = 0 < ENTRIES
        get NAMESZ long
        getdstring NAME NAMESZ
        get FOLDER byte
        get OFFSET long
        get SIZE long
        get DUMMY long
        get SUB_ENTRIES long
        if FOLDER == 0
            savepos TMP         # ugly work-around because this stupid game
            math TMP2 = OFFSET  # saves the uncompressed size and not the
            math TMP2 += 10     # size of the bzip files... blah
            goto TMP2
            findloc ZSIZE string "BZh91AY&SY" ""
            if ZSIZE == ""
                get ZSIZE asize
            endif
            math ZSIZE -= OFFSET
            goto TMP
            set FULLNAME string PATH
            string FULLNAME += NAME
            clog FULLNAME OFFSET ZSIZE SIZE
        else
            callfunction EXTRACT
        endif
    next i
endfunction
```

a small technical info: it's really ugly how this game stores the compressed files, but it has a sense in its environment because the bzip2 input would be the file descriptor at OFFSET and the output the allocated memory of SIZE bytes
## Post #3
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-04-29T14:54:48+00:00
- Post Title: Kuros - Archive

The bms-script crash QuickBMS at line "044da1e5 4130 /scripts/object.txt"
Any suggestions?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-29T16:29:59+00:00
- Post Title: Kuros - Archive

don't know why it crashes, if you can upload the first 70 megabytes of this file I will take it a look
