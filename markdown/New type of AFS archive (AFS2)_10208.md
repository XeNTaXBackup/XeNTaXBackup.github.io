## Post #1
- Username: soneek
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Oct 20, 2011 5:43 am
- Post datetime: 2013-03-09T06:34:49+00:00
- Post Title: New type of AFS archive (AFS2)

Seems Criware is packing stuff with this now. Does anyone know how to get a solid unpacking script for this?

[AFS2 sample](http://rghost.net/43895242)
## Post #2
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-03-09T19:49:40+00:00
- Post Title: New type of AFS archive (AFS2)

I would also like this to be done.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-09T20:42:29+00:00
- Post Title: New type of AFS archive (AFS2)

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "AFS2"
get DUMMY long
get FILES long
get DUMMY long
for i = 0 < FILES
    get DUMMY short
next i

    get OFFSET long
for i = 0 < FILES
    get NEXT_OFFSET long
    math OFFSET x= 0x10
    math SIZE = NEXT_OFFSET
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
next i
```
## Post #4
- Username: soneek
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Oct 20, 2011 5:43 am
- Post datetime: 2013-03-17T22:49:47+00:00
- Post Title: New type of AFS archive (AFS2)

> Reply from aluigi
>
> Code: Select all# AWB AFS2
# script for QuickBMS http://quickbms.aluigi.org

idstring "AFS2"
get DUMMY long
get FILES long
get DUMMY long
for i = 0 < FILES
    get DUMMY short
next i

    get OFFSET long
for i = 0 < FILES
    get NEXT_OFFSET long
    math OFFSET x= 0x10
    math SIZE = NEXT_OFFSET
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
next i

Thank you so much! Works great!
