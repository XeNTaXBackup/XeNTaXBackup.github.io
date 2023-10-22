## Post #1
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-09-15T16:33:09+00:00
- Post Title: Black Clover Quartet Knights

Would anyone be willing to make a script/tool to unpack the files from Black Clover Quartet Knights?
I'd upload the files, but they're pretty big and would take too long to upload, but looks like the DATH files are for file directories I think, but can be grabbed down below.

> 
[GxArchivedFile000.rar](https://xentaxbackup.github.io/file/14849_GxArchivedFile000.rar)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T13:13:16+00:00
- Post Title: Black Clover Quartet Knights

You can use the following BMS commands to unpack the dat archives:

```
get EXT extension
if EXT != "dath"
	cleanexit
endif
get DatName basename
set Path string ArcName
string Path + \
string DatName + ".dat"
open "." DatName 1
get Count long
for i = 0 < Count
	get Unknown longlong
	get Offset longlong
	get Size longlong
	set Name string Path
	string Name + i
	string Name + ".dmp"
	log Name Offset Size 1
next i
```

Select the dath files as input and the files within the dat archive would be dumped into a folder with the same name as the archive.
But the filenames are at the start of the corresponding data chunk in the dat file, which seem to be encrypted. 
The code above instead would name the output files using the loop index.
