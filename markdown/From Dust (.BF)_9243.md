## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T22:39:44+00:00
- Post Title: From Dust (*.BF)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "ABE"
goto 0x18
get TABLEOFFSET long
goto 0x2C
get FILES long
goto TABLEOFFSET

for i = 0 < FILES
	get DUMMY long
	get DUMMY longlong
	getdstring NAME 108
	get OFFSET long
	get DUMMY long
	get SIZE long
	getdstring TRASH 68
    log NAME OFFSET SIZE
next i
```
## Post #2
- Username: tarique
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 20, 2014 12:03 am
- Post datetime: 2015-05-17T11:12:29+00:00
- Post Title: From Dust (*.BF)

thanks for the script ekey. 

when I extract a file with this script, new files has different extensions. I want to trasnlate this game. I think text files has .oli extension.its in attachment.

ı searched google and ı find a topic in a forum, a russian forum, so ı can't understand anything. there are tools but the links are dead.
topic is this: [http://www.zoneofgames.ru/forum/lofiver ... 23644.html](http://www.zoneofgames.ru/forum/lofiversion/index.php/t23644.html) 

anybody help me?
[examples.rar](https://xentaxbackup.github.io/file/9206_examples.rar)
