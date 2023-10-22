## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-06-13T09:08:59+00:00
- Post Title: bhd&bnd file PSP

Hi all
Can anybody tell me how to extract bhd&bnd data?
bhd&bnd data Another Century's Episode Portable PSP.

Thanks in advance.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-13T09:40:20+00:00
- Post Title: bhd&bnd file PSP

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

open FDDE "bhd"
open FDDE "bnd" 1
idstring "LDMU"
get DUMMY long
get FILES long
goto 0x1c
for i = 0 < FILES
    get DUMMY long
    get OFFSET long
    get SIZE long
    get ZSIZE long
    getdstring DUMMY 0x18
    math OFFSET *= 0x400
    clog "" OFFSET ZSIZE SIZE 1
next i
```
## Post #3
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-06-13T22:47:21+00:00
- Post Title: bhd&bnd file PSP

Thank you very much
