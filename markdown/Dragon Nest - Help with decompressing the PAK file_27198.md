## Post #1
- Username: dnblank123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 13, 2023 7:37 pm
- Post datetime: 2023-09-13T11:55:45+00:00
- Post Title: Dragon Nest - Help with decompressing the PAK file

The game is Dragon Nest, and I'm using QuickBMS to extract files, and the devs of the game updated their files, and the output file when using QuickBMS is looks like encrypted (I'm not sure), every output file starts with hex 
```
51 F8 1A 80 4A 73 30 73 65 E4 A6 52 C6 AC 62 56
```
 Here is the link if anyone wants to check it. [https://drive.google.com/drive/folders/ ... drive_link](https://drive.google.com/drive/folders/1nsALxUsEPo6oKKC0gmqsT1k3uLg29ptq?usp=drive_link)
## Post #2
- Username: dnblank123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 13, 2023 7:37 pm
- Post datetime: 2023-09-15T11:17:45+00:00
- Post Title: Dragon Nest - Help with decompressing the PAK file

Help, is there a to read the offset without messing up with the next file offset?

```
	set CHECK_AES ""
	set CHECK_STRING ""
    	getdstring NAME 256
    	get XSIZE long
    	get SIZE long
    	get ZSIZE long
    	get OFFSET long
    	get DUMMY long
    	getdstring DUMMY 40
    	goto OFFSET # This part fails the next files.
	getdstring OFFSET 16 # probably this also
	#set CHECK_STRING binary "CHECK_AES"
	if(CHECK_AES == "Qø€Js0seä¦RÆ¬bV")
	math OFFSET += 16
	clog NAME OFFSET ZSIZE SIZE
	else
	clog NAME OFFSET ZSIZE SIZE # unencrypted / old paks
	endif
next i

```

Edit: Already fixed it.
