## Post #1
- Username: damndoe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 13, 2019 9:14 am
- Post datetime: 2019-12-15T10:52:16+00:00
- Post Title: Help with Apex .starpak files

A tool called Legion used to unpak .rpak files easily and pulled all the assets, this tool has not been updated and is no longer working. I tried using 
Bigchillghost's BMS script but it no longer works for the starpak files.
Here it is:

```
goto -8 0 SEEK_END
savepos entryOffset
get entryCount longlong
set entrySize longlong entryCount
math entrySize * 0x10
math entryOffset - entrySize
log MEMORY_FILE entryOffset entrySize
get Path basename
for i = 0 < entryCount
	get Offset longlong MEMORY_FILE
	get Size longlong MEMORY_FILE
	goto Offset
	get Magic longlong
	set Flag longlong Size
	math Flag & 0x0FFF
	if Magic == 0x1800000007
		set Ext string ".msh"
	elif Flag == 0
		set Ext string ".tex"
	else
		set Ext string ".dat"
	endif
	set Name string ""
	string Name p "%s/%08d%s" Path i Ext
	log Name Offset Size
next i
```


Does anyone have any updated information they can share or updated bms scripts to get these dang files open for apex legends? 

Thank you.
## Post #2
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2020-05-25T05:16:15+00:00
- Post Title: Help with Apex .starpak files

Which file? It doesn't look like the format has changed.
