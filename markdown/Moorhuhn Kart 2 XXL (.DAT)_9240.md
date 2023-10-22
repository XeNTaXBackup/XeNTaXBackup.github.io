## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T15:29:05+00:00
- Post Title: Moorhuhn Kart 2 XXL (*.DAT)

Again birds  

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "Moorhuhn Kart 2"
goto 0x20
get FILES long
goto 0x40

for i = 0 < FILES
	getdstring NAME 104
	get OFFSET long
	get SIZE long
	get DUMMY longlong
	get DUMMY longlong
    log NAME OFFSET SIZE
next i
```
## Post #2
- Username: dipo33
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 04, 2019 8:19 pm
- Post datetime: 2019-04-04T12:21:43+00:00
- Post Title: Moorhuhn Kart 2 XXL (*.DAT)

What language is this ?
