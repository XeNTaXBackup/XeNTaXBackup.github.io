## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T17:25:28+00:00
- Post Title: Feng Yun (風雲)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-20T18:33:06+00:00
- Post Title: Feng Yun (風雲)

```
# script for QuickBMS http://quickbms.aluigi.org

comtype lzo1x
get FILESIZE long
get BASE_OFF long
get FILES long
for i = 0 < FILES
    filexor 0xff
    getdstring NAME 0x100
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get XSIZE long
    get CRC long
    get FLAG long
    filexor ""
    clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-22T02:01:52+00:00
- Post Title: Feng Yun (風雲)

thanks a lot for support guys, now sorry for offtopic but what is the web site of this game?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T02:10:04+00:00
- Post Title: Feng Yun (風雲)

HP: [http://www.fy0.cn/](http://www.fy0.cn/)
Client: [http://dlc2.sdo.com/FTP/fengyun/2011062 ... .0.105.exe](http://dlc2.sdo.com/FTP/fengyun/20110628/1/ZSZZ_Setup1.9.0.105.exe)
