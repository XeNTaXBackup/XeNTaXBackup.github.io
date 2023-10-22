## Post #1
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-06-13T14:39:58+00:00
- Post Title: (PC) iBomber Defense

Hi guys,
Please, can somebody write a quickBMS script for unpacking res.dat file from iBomber Defense?

Here are first and the last megabyte of that file.


I can upload whole .dat file if it's necessary.

Thanks in advance.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-13T20:15:43+00:00
- Post Title: (PC) iBomber Defense

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "CBRS"
get FILES long
get BASE_OFF long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    getdstring NAME 0x80
    math OFFSET += BASE_OFF
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-06-13T21:30:34+00:00
- Post Title: (PC) iBomber Defense

I knew it. Aluigi will be the first. 
Thank you very much, it works like a charm
