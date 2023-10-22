## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-06-27T15:18:06+00:00
- Post Title: The Kreed (*.PAK)

Very simple.

```
# 
# Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "\x50\x41\x4B\x20"
get DUMMY long
get FILES long

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get SIZE long
    get OFFSET long
    math OFFSET + 4
    log NAME OFFSET SIZE
next i
```
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-06-29T06:15:32+00:00
- Post Title: The Kreed (*.PAK)

Thanks!
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T02:48:19+00:00
- Post Title: The Kreed (*.PAK)

is it "The Kreed" game of the 2004?
the demo of that old game didn't have pak archives
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-06-30T03:33:43+00:00
- Post Title: The Kreed (*.PAK)

Yeah game of 2004
