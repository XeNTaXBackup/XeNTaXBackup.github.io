## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-07T16:43:43+00:00
- Post Title: Shoot Many Robots *.SAR

Hey guys. Can someone look ? 

[http://www.mediafire.com/?02f53fabx988wb1](http://www.mediafire.com/?02f53fabx988wb1)
## Post #2
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-09T14:23:34+00:00
- Post Title: Shoot Many Robots *.SAR

> Reply from Ekey
>
> Hey guys. Can someone look ? 

http://www.mediafire.com/?02f53fabx988wb1
Done, and done.   

Check Unpakke's homepage. And don't forget to read the upkk_sar.txt !
The module probably works for the XBOX and PS3 versions too.

Now here's a duck:
[duck.jpg](https://xentaxbackup.github.io/file/5286_duck.jpg)
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-09T15:58:14+00:00
- Post Title: Shoot Many Robots *.SAR

if someone is interested in the encryption algorithm and format the following is the script for QuickBMS:

```
# script for QuickBMS http://quickbms.aluigi.org

get DUMMY long
get DUMMY long
get OFFSET longlong
get FILES long
goto OFFSET
for i = 0 < FILES
    get OFFSET longlong
    get SIZE longlong
    get NAMESZ long
    getdstring NAME NAMESZ
    log MEMORY_FILE OFFSET SIZE
    callfunction CRYPT 1
    log NAME 0 SIZE MEMORY_FILE
next i

startfunction CRYPT
    math KEY = 0x54007b47
    strlen NAMESZ NAME
    string NAME l= NAME
    for j = 0 < NAMESZ
        math T = KEY
        math T u<<= 5
        math KEY += T
        getvarchr C NAME j
        math KEY += C
    next j
    for j = 0 < SIZE
        math T = j
        math T /= 4
        math T *= 0x65
        math T += KEY
        getvarchr C MEMORY_FILE j
        math C ^= T
        putvarchr MEMORY_FILE j C
        math KEY r= 8
    next j
endfunction
```
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-09T17:44:23+00:00
- Post Title: Shoot Many Robots *.SAR

Thanks you guys
