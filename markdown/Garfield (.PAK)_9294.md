## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-18T16:08:08+00:00
- Post Title: Garfield (*.PAK)

Perhaps was script but I not found 

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PACK"
get TABLEOFFSET long
get FILES long
goto TABLEOFFSET

for i = 0 < FILES
	getdstring NAME 52
	get SIZE long
	get OFFSET long
	get DUMMY long
	log NAME SIZE OFFSET
next i
```

[jigpic02.png](https://xentaxbackup.github.io/file/5583_jigpic02.png)
