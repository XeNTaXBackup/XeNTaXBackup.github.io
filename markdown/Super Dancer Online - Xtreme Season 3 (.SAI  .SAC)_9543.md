## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-24T20:08:37+00:00
- Post Title: Super Dancer Online - Xtreme Season 3 (*.SAI / *.SAC)

Datas.sac - Main Archive
Datas.sai - FileTable

Before run script you need decrypt FileTable (Use tool in attach) -> Just copy in game folder and run BAT. After use script.

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

open FDSE "Datas.sai.dec" 0
open FDSE "Datas.sac" 1

idstring "SDO\x00" 0
get FILES long 0
get NAMETABLESIZE long 0
get NULLS long 0

get SIZE asize 0
math NAMETABLEOFF = SIZE
math NAMETABLEOFF -= NAMETABLESIZE

for i = 0 < FILES
	get FLAG long 0
	get SIZE long 0
	get OFFSET long 0
	get NAMEOFF long 0
	savepos TEMP 0
	math NAMETABLEOFF += NAMEOFF
	goto NAMETABLEOFF 0
	get NAME string 0
	log NAME OFFSET SIZE 1
	math NAMETABLEOFF -= NAMEOFF
	goto TEMP 0
next i
```


1)Open script
2)Open Datas.sac
3)Select Out Put Directory
4)Profit 
[SDOESAITool.rar](https://xentaxbackup.github.io/file/5710_SDOESAITool.rar)
