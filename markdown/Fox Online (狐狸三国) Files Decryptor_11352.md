## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-23T17:16:33+00:00
- Post Title: Fox Online (狐狸三国) Files Decryptor

Official site: [here](http://fox.xoyo.com)
Download: [here](http://fox.xoyo.com/download)

Unreal Engine

Here simple decryptor  

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

get SIZE asize
idstring "KFXArchive"
goto 0x32
savepos OFFSET
math SIZE -= 0x32
get NAME filename
string NAME += ".dec"
filexor "\x9D"
log NAME OFFSET SIZE
filexor ""
```
## Post #2
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2014-03-24T14:16:16+00:00
- Post Title: Fox Online (狐狸三国) Files Decryptor

work great，nice job，thanks~~
