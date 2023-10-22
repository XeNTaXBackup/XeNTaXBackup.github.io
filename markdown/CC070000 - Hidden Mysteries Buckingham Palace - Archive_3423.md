## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-06T14:52:21+00:00
- Post Title: CC070000 - Hidden Mysteries: Buckingham Palace - Archive

I'll appreciate any help or guidance to unpack the "scenes.dat" archive from "Hidden Mysteries - Buckingham Palace". 
The head.bin and tail.bin may be downloaded here: [http://motionpress.com/uploads/Buckingh ... d_tail.rar](http://motionpress.com/uploads/Buckingham_Palace_head_and_tail.rar)

Thanks in advance!
## Post #2
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-12-27T19:51:34+00:00
- Post Title: CC070000 - Hidden Mysteries: Buckingham Palace - Archive

Head-and-tail link updated.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-27T19:56:17+00:00
- Post Title: CC070000 - Hidden Mysteries: Buckingham Palace - Archive

```

get FILES long
goto 0x20
for i = 0 < FILES
    getdstring NAME 0x200
    set NAME unicode NAME
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
