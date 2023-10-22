## Post #1
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-07-08T10:24:23+00:00
- Post Title: help with getdstring

still learning and run into a problem using getdstring to get the name of the files

here's the script I made

```
get PACKhead1 long
get FILENUM long
get UNK1 long
get PACKhead3 long
get UNK2 long
get startfo long
xMath sizeoff "FILENUM * 4 + 20"
xMath nameoff "FILENUM * 4 + 40"
set filetbloff 0x14
set sizetbloff sizeoff
set nametbloff nameoff
for i = 0 < FILENUM
	goto filetbloff
	get OFFSET long
	savepos filetbloff
	goto sizetbloff
	get SIZE long
	savepos sizetbloff
	goto nametbloff
	get NAMEPOS long
	savepos nametbloff
	goto NAMEPOS
	get NAMESZ byte
	getdstring NAME NAMESZ
	log "NAME" offset size
next i
```


the file have 5 files but only can extract 4 since it encountered this problem


```
- open script test3.bms
- set output folder TEST

  offset   filesize   filename
--------------------------------------
  00000050 1744       ui_base.tmd2
  00000730 2392       ui_main_win.tmd2
  000010b0 1376       ui_select_line.tmd2
  00001630 2376       ui_sub_win.tmd2

Error: incomplete input file 0: F:\Script ng natsuiro\PACK1.001
       Can't read 101 bytes from offset 00002800.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0    82%   8456       10240

Last script line before the error or that produced the error:
  25  getdstring NAME NAMESZ
```


because the name 5th file is on the end of the big file and it doesn't meet the byte length on the "get NAMESZ byte" and now only 0xf long
[a.jpg](https://xentaxbackup.github.io/file/11263_a.jpg)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-08-01T23:09:20+00:00
- Post Title: help with getdstring

is it possible that 
```
get NAMESZ byte
```
 is actually the wrong value? it could just be a null-terminated string at the position you have.

other filenames work because quickbms treats the string as a c-string anyway.. so any larger filenames are accepted, but trimmed to the first 00 byte.

something like

```
get NAME string

```
