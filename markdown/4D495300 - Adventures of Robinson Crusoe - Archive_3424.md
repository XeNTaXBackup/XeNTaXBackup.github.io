## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-06T14:53:08+00:00
- Post Title: 4D495300 - Adventures of Robinson Crusoe - Archive

I'll appreciate any help or guidance to unpack the "mainmenu.pak" archive from "Adventures of Robinson Crusoe". 
The head.bin and tail.bin may be downloaded here: [http://motionpress.com/uploads/Robinson ... d_tail.rar](http://motionpress.com/uploads/Robinson_Crusoe_head_and_tail.rar)

Thanks in advance!
## Post #2
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-12-27T19:46:05+00:00
- Post Title: 4D495300 - Adventures of Robinson Crusoe - Archive

Head-and-tail link updated.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-27T19:52:10+00:00
- Post Title: 4D495300 - Adventures of Robinson Crusoe - Archive

```

idstring "MIS"
goto 12
get FILES long
goto 32
filerot 0xa8
for i = 0 < FILES
    getdstring NAME 32
    get SIZE long
    get OFFSET long
    get DUMMY long
    log NAME OFFSET SIZE
next i
```
