## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T13:29:01+00:00
- Post Title: Freestyle 2 Street Basketball (*.PAK)

For [this](http://fs2.joycity.com/) game 

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PACK"
get TABLEOFFSET long
get FILES long
math FILES /= 136

for i = 0 < FILES
	getdstring NAME 128
	get OFFSET long
	get SIZE long
	log NAME OFFSET SIZE
next i
```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-09T15:34:59+00:00
- Post Title: Freestyle 2 Street Basketball (*.PAK)

2 suggestions:
- "writed" -> "written"
- "\x50\x41\x43\x4B" -> "PACK", it helps to find the script on google
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T15:43:28+00:00
- Post Title: Freestyle 2 Street Basketball (*.PAK)

Corrected
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-07-18T18:33:35+00:00
- Post Title: Freestyle 2 Street Basketball (*.PAK)

thanks a lot for help aluigi and ekey, very nice work.
