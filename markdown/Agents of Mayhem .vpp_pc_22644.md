## Post #1
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2020-09-05T18:13:04+00:00
- Post Title: Agents of Mayhem .vpp_pc

Hello everyone, can you help me extract this file?



Captura.PNG (39.2 KiB) Viewed 57 times



[ files vpp_pc](https://mega.nz/file/4cBDGKxT#Tf0_e5FBsbiC9qlnKP5RNHjNzx56_K1daeoa7EmUg8U)
## Post #2
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2020-09-07T03:38:22+00:00
- Post Title: Agents of Mayhem .vpp_pc

> Reply from aoba200941 ↑Sun Sep 06, 2020 2:13 am at Sun Sep 06, 2020 2:13 am
>
> 
Hello everyone, can you help me extract this file?

Captura.PNG


 files vpp_pc

i have tried this acewell script
but it does not work
[download/file.php?id=13957](https://forum.xentax.com/download/file.php?id=13957)

```
get UKN long
get UKN2 long
get UNK3 long
get STR2PC_SZ long
get UNK4 long
get FILES long
get OFF_TABLE_SZ long
get STR_TABLE_SZ long
get SIZE long
get ZSIZE long
savepos TMPB
xmath BASE_OFF "TMPB + OFF_TABLE_SZ + STR_TABLE_SZ" 
if ZSIZE != 0xFFFFFFFF
	comtype zlib_noerror
	clog memory_file1 BASE_OFF ZSIZE SIZE
	for i = 1 to FILES
		get STR_OFF longlong
		xmath STR_OFF "TMPB + OFF_TABLE_SZ + STR_OFF"
		get OFFSET long
		get SIZE long
		get ZSIZE long
		get FLAG1 short //compression flag?? 0=no, 1=yes
		get FLAG2 short //0x10 = 16 byte alligned??
		savepos TMP 0
		goto STR_OFF
		get NAME string
		string NAME p "%s\%s" FOLDER NAME
		if i == 1
			xmath NEXT_OFF "OFFSET + SIZE"
			goto NEXT_OFF -1
			savepos NEXT_OFF -1
			log NAME OFFSET SIZE -1
		else
			log NAME NEXT_OFF SIZE -1
			math NEXT_OFF + SIZE
		endif
		goto TMP 0
	next i
else
	for i = 1 to FILES
		get STR_OFF longlong
		xmath STR_OFF "TMPB + OFF_TABLE_SZ + STR_OFF"
		get OFFSET long
		xmath OFFSET "TMPB + OFF_TABLE_SZ + STR_TABLE_SZ + OFFSET"
		get SIZE long
		get ZSIZE long
		get FLAG1 short
		get FLAG2 short
		savepos TMP
		goto STR_OFF
		get NAME string
		string NAME p "%s\%s" FOLDER NAME
		log NAME OFFSET SIZE
		goto TMP
	next i
endif 




```


```
       Can't read 465181 bytes from offset 00000000202a4903.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0    99%   539176974  539642115  . offset 00000000202a4903

Last script line before the error or that produced the error:
  18  clog memory_file1 BASE_OFF ZSIZE SIZE

Press ENTER or close the window to quit
```
