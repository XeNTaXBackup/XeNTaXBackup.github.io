## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-28T18:46:03+00:00
- Post Title: [Request] Luxory Online

Ok a very cool game stored in .PAK archivs, the header is this.





[Luxory Online Archive Research](http://www.mediafire.com/download.php?ny4o82zaeub5idh)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-28T18:54:52+00:00
- Post Title: [Request] Luxory Online

Hmm reminds me of lunia with their weird numbers everywhere.
Looks like a nice game.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-29T19:11:52+00:00
- Post Title: [Request] Luxory Online

Archive seems the same -> [Xiang Long Zhi Jian](http://forum.xentax.com/viewtopic.php?f=10&t=8423)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-29T21:31:42+00:00
- Post Title: [Request] Luxory Online

```
# script for QuickBMS http://quickbms.aluigi.org

comtype lzo1x
idstring "KGPK"
goto 0x78
get OFFSET longlong
get MAX_OFFSET asize
for OFFSET = OFFSET < MAX_OFFSET
    goto OFFSET
    get SIZE longlong
    get ZSIZE longlong
    get ZIP long
    get DUMMY longlong
    get DUMMY long
    savepos OFFSET
    if ZIP == 0
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
    math OFFSET += ZSIZE
next
```
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-29T23:39:28+00:00
- Post Title: [Request] Luxory Online

thanks a lot aluigi, what you think about it? I get this with another scripts and never posted, but I'm curious
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-01T00:06:20+00:00
- Post Title: [Request] Luxory Online

check if you have the same error using quickbms_4gb_files
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-03-01T04:49:29+00:00
- Post Title: [Request] Luxory Online

no still same aluigi :/
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-01T18:12:05+00:00
- Post Title: [Request] Luxory Online

maybe check if the following works better:

```
# script for QuickBMS http://quickbms.aluigi.org

comtype lzo1x
idstring "KGPK"
goto 0x78
get OFFSET long
get DUMMY long
get MAX_OFFSET asize
for OFFSET = OFFSET < MAX_OFFSET
    goto OFFSET
    get SIZE long
    get DUMMY long
    get ZSIZE long
    get DUMMY long
    get ZIP long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    savepos OFFSET
    if ZIP == 0
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
    math OFFSET += ZSIZE
next
```
I have converted the 64bit fields in 32bit, so I don't know if it's correct
## Post #9
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-03-02T02:41:36+00:00
- Post Title: [Request] Luxory Online

ummm this is what I get mate.
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-02T08:59:43+00:00
- Post Title: [Request] Luxory Online

in this case I can do nothing
## Post #11
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-03-02T13:26:30+00:00
- Post Title: [Request] Luxory Online

ok no problem aluigi, thanks a lot for effort, take care.
