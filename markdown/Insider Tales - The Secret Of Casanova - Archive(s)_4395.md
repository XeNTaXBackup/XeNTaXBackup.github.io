## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-04-26T22:42:54+00:00
- Post Title: Insider Tales - The Secret Of Casanova - Archive(s)

I'll appreciate any help or guidance to unpack the "*.pak"-archives from "The Secret Of Casanova". 
The head.bin and tail.bin may be downloaded here: [http://www.motionpress.com/uploads/Secr ... adTail.rar](http://www.motionpress.com/uploads/SecretOfCasanovaHeadTail.rar)

Thanks in advance!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-26T23:44:45+00:00
- Post Title: Insider Tales - The Secret Of Casanova - Archive(s)

```

getdstring DUMMY 5
get FILES long
for i = 0 < FILES
    get NAMESZ short
    getdstring NAME NAMESZ
    get SIZE long
    get OFFSET long
    log NAME OFFSET SIZE
next i
```
