## Post #1
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2013-09-30T09:38:06+00:00
- Post Title: Quick BMS Parser difficulties (text string to text string)

Looking at the 'quick bms guide' post [viewtopic.php?f=29&t=3525](http://forum.xentax.com/viewtopic.php?f=29&t=3525)
I am a beginner and im getting the hang of my HEX model exploration but this tutorial doesnt make logical sence and it seems like the conclusions reached are without proper explanation.  This tutorial doesnt work for my model file, possibibly due to its multiple headers.  My model file has a PAKS header then an IPAC header then a HRCM header and then repeated HRCM (hrcm being the start of the model file)  

I just need a way to parse the files from one HRCM text string to the next, using quick BMS 

I can manually select bookmark and extract data manually with Hexworkshop, but Its time consuming , I spent about 5 hours ripping 131 files yesterday that quickbms could have done in seconds.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-09-30T13:57:09+00:00
- Post Title: Quick BMS Parser difficulties (text string to text string)

I guess you mean something like the following, remember to replace the 2 occurrencies of "NGCA" with "HRCM":
[http://aluigi.org/papers/bms/_findloc.bms](http://aluigi.org/papers/bms/_findloc.bms)
## Post #3
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2013-10-07T12:10:47+00:00
- Post Title: Quick BMS Parser difficulties (text string to text string)

> Reply from aluigi
>
> I guess you mean something like the following, remember to replace the 2 occurrencies of "NGCA" with "HRCM":
http://aluigi.org/papers/bms/_findloc.bms

Worked great Thank you,  I can rename the .Dat files that are output ,but what would I add to get it to output a defined extension (.abc)?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-07T13:53:53+00:00
- Post Title: Quick BMS Parser difficulties (text string to text string)

the only way is building the name by hand:

```
math i = 0
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET string "HRCM" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET
    string NAME p= "%08x.abc" i
    log NAME OFFSET SIZE
    math i += 1
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""
```
## Post #5
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2013-10-14T09:18:22+00:00
- Post Title: Quick BMS Parser difficulties (text string to text string)

Not sure what you mean by 'rebuilding by hand', this code outputs files as 00000000.dat, 0000000a.dat etc.  It would be useful if i could define a prefix and the extension output.  I used to have a mass renamer program that could change the extension, supid windows wont do it and I cant believe that BMS doesnt have a line of text to do it.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-14T10:05:43+00:00
- Post Title: Quick BMS Parser difficulties (text string to text string)

the script I pasted in my previous post dumps sequential files with abc extension, not dat.
## Post #7
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2013-10-22T13:22:30+00:00
- Post Title: Quick BMS Parser difficulties (text string to text string)

Ah thankyou again , It didnt work the first time because i was using an ancient version of QuickBms
