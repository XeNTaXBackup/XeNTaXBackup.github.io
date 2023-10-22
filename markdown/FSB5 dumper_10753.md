## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-09-04T21:47:38+00:00
- Post Title: FSB5 dumper

I have this bms from aluigi

```
# script for QuickBMS http://quickbms.aluigi.org

for
    findloc OFFSET string "FSB" 0 ""
    if OFFSET == ""
        cleanexit
    endif
    goto OFFSET
    getdstring FSB_SIGN 3
    get FSB_VER byte
    get DUMMY long
    get HEADER_SIZE long
    get DATA_SIZE long
    if FSB_VER == '4'
        math SIZE = 0x30
    elif FSB_VER == '3'
        math SIZE = 0x18
    elif FSB_VER == '2'
        math SIZE = 0x10
    elif FSB_VER == '1'
        math SIZE = 0x10
        math DATA_SIZE = HEADER_SIZE
        math HEADER_SIZE = 0
    else
        #print "FSB version %FSB_VER% not supported"
        #cleanexit
        math SIZE = -1
    endif
    if SIZE == -1
        math SIZE = 4
    else
        math SIZE += HEADER_SIZE
        math SIZE += DATA_SIZE
        log "" OFFSET SIZE
    endif
    math OFFSET += SIZE
    goto OFFSET
next

```


How i can upgrade for FSB5?

Thanks!
