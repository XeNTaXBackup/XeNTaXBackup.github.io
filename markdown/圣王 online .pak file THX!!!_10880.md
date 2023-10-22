## Post #1
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2013-10-16T06:58:28+00:00
- Post Title: 圣王 online .pak file THX!!!

Free MMO

Name:圣王
HP:[http://sw.wanmei.com/](http://sw.wanmei.com/)
DL page:[http://sw.wanmei.com/download/index.shtml](http://sw.wanmei.com/download/index.shtml)
Direct link:[http://download102.wanmei.com/shengwang ... 0927.2.zip](http://download102.wanmei.com/shengwang/client/Install-1.13.0927.2.zip)
size:3.05G

Could you please look at this *.pak file,THX!!!
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-16T11:04:11+00:00
- Post Title: 圣王 online .pak file THX!!!

Where samples?
## Post #3
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2013-10-16T12:59:41+00:00
- Post Title: 圣王 online .pak file THX!!!

> Reply from Ekey
>
> Where samples?
samples:[http://pan.baidu.com/s/1nA1Wf](http://pan.baidu.com/s/1nA1Wf)
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-10-16T13:59:38+00:00
- Post Title: 圣王 online .pak file THX!!!

Quickbms script:

```
# website: http://sw.wanmei.com/download/index.shtml
# Package: PAK
# by Fatduck     Oct 2013
# script for QuickBMS http://quickbms.aluigi.org

get ID long
get UKN long
getdstring VER 0x40

for i = 0 < 112
   getdstring RES_NAME 0x40
   get OFS_RES long
   get USIZE long
   get CSIZE long
   get UKN long
   get NULL longlong
   
   if OFS_RES == 0
      cleanexit
   endif
   
   clog RES_NAME OFS_RES CSIZE USIZE

next i
```


yianti, you should learn how to read this simple archive!
## Post #5
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2013-10-17T03:19:10+00:00
- Post Title: 圣王 online .pak file THX!!!

> Reply from fatduck
>
> Quickbms script:
Code: Select all# Game: 圣王 Online / SW online (PC)
# website: http://sw.wanmei.com/download/index.shtml
# Package: PAK
# by Fatduck     Oct 2013
# script for QuickBMS http://quickbms.aluigi.org

get ID long
get UKN long
getdstring VER 0x40

for i = 0 < 112
   getdstring RES_NAME 0x40
   get OFS_RES long
   get USIZE long
   get CSIZE long
   get UKN long
   get NULL longlong
   
   if OFS_RES == 0
      cleanexit
   endif
   
   clog RES_NAME OFS_RES CSIZE USIZE

next i

yianti, you should learn how to read this simple archive!
 
My Quickbms  error:
Error: the compressed zlib/deflate input is wrong or incomplete <-3>
Error: there is an error with the decompression 
        the returned output size is negative <-1>
[1.jpg](https://xentaxbackup.github.io/file/6704_1.jpg)
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T06:17:18+00:00
- Post Title: 圣王 online .pak file THX!!!

huh try this

```
# website: http://sw.wanmei.com/download/index.shtml
# Package: PAK
# by Fatduck     Oct 2013
# script for QuickBMS http://quickbms.aluigi.org

get ID long
get UKN long
getdstring VER 0x40

for i = 0 < 112
   getdstring RES_NAME 0x40
   get OFS_RES long
   get USIZE long
   get CSIZE long
   get UKN long
   get NULL longlong
  
   if OFS_RES == 0
      cleanexit
   endif

   if USIZE == CSIZE
   	log RES_NAME OFS_RES USIZE
   else if CSIZE == 0
   	log RES_NAME OFS_RES USIZE
   else
	clog RES_NAME OFS_RES CSIZE USIZE
   endif
next i
```
## Post #7
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2013-10-17T07:18:04+00:00
- Post Title: 圣王 online .pak file THX!!!

Thanks to Ekey and fatduck！
## Post #8
- Username: 194klakla
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Apr 28, 2013 1:18 pm
- Post datetime: 2013-10-17T13:33:21+00:00
- Post Title: 圣王 online .pak file THX!!!

@fatduck or @Ekay

Can help-me with this .pak ?? Please
[viewtopic.php?f=10&t=10785](http://forum.xentax.com/viewtopic.php?f=10&t=10785)


Thanks
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T17:26:37+00:00
- Post Title: 圣王 online .pak file THX!!!

I remember this game. Encrypted pak's
## Post #10
- Username: 194klakla
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Apr 28, 2013 1:18 pm
- Post datetime: 2013-10-19T07:50:20+00:00
- Post Title: 圣王 online .pak file THX!!!

But you can help-me extract theses files? I Need to make an translation :/
