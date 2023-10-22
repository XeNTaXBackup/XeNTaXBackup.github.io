## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-09T06:55:45+00:00
- Post Title: Sanjie PAK Unpacker

Ok here unpacker of this chinese MMORPG, thanks for support of finale00.



> #Sanjie Online PAK Unpacker
>
> 
>
> idstring "PAKF3001"
>
> get FSIZE long
>
> get FILES long
>
> 
>
> set FOLDER_NAME = "/"
>
> for i = 0 < FILES do
>
>    getdstring NAME 32
>
>    get OFFSET long
>
>    get SIZE long
>
>    get IS_FOLDER long
>
>    get unk2 long
>
> 
>
>    if IS_FOLDER = 1
>
>       set FOLDER_NAME = NAME
>
>       string FOLDER_NAME += "/"
>
>    else
>
>       set TEMP = FOLDER_NAME
>
>       string TEMP += NAME
>
>       print %TEMP%
>
>       log TEMP OFFSET SIZE   
>
>    endif
>
> next i
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-09T07:06:27+00:00
- Post Title: Sanjie PAK Unpacker

Trying unpack UI.pak 138MB

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select the BMS script or plugin to use
- select the input archives/files to extract, type "" for whole folder and subfo
lders
- select the output folder where extracting the files
- open input file D:\Sanjie\ui.pak
- open script D:\Sanjie Online.bms
- set output folder D:\Sanjie\ui

  offset   filesize   filename
------------------------------
- SCRIPT's MESSAGE:
  baobei/block.bmp

  07a4763f 63         baobei/block.bmp
- SCRIPT's MESSAGE:
  baobei/block2.bmp

  07a4767e 62         baobei/block2.bmp
- SCRIPT's MESSAGE:
  item/ItemView.a16

  085071a6 92         item/ItemView.a16
- SCRIPT's MESSAGE:
  msgdlg/NODRAG.tga

  0850fcef 427        msgdlg/NODRAG.tga

- 4 files found in 0 seconds

Press RETURN to quit
```


Maps (1,2,3,4) Paks

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select the BMS script or plugin to use
- select the input archives/files to extract, type "" for whole folder and subfo
lders
- select the output folder where extracting the files
- open input file D:\Sanjie\map1.pak
- open script D:\Sanjie Online.bms
- set output folder D:\Sanjie\map1

  offset   filesize   filename
------------------------------

- 0 files found in 0 seconds

Press RETURN to quit
```

[map1.rar](https://xentaxbackup.github.io/file/5046_map1.rar)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T09:46:14+00:00
- Post Title: Sanjie PAK Unpacker

Anyone want to amuse themselves with a recursion exercise?
Each folder is just another archive. And naturally, all of the offsets referenced in that archive are relative to the start of its offset relative to its parent archive. Easiest way is to just toss the entire script into a function, and then just call it recursively, passing in a base offset that is the offset in the root archive (your input) as well as the folder name up until now.

And that's pretty much it. So if IS_FOLDER is true, just recursively call the function.

Here is the non-recursive script to get anyone started.

```

comtype COMP_LZO1X
get FOLDER_NAME filename

#you can pass arguments to the function
CallFunction Unpack 1 0 FOLDER_NAME

#the actual function. Implement the recursive calls appropriately.
StartFunction Unpack

	###retrieve arguments like this###
	set BASE_OFFSET Unpack_arg1
	set FOLDER_NAME Unpack_arg2
	print "%BASE_OFFSET% %FOLDER_NAME%"
	#####################
	idstring "PAKF3001"
	get FSIZE long
	get FILES long

	for i = 0 < FILES do
		getdstring NAME 32
		get OFFSET long
		get SIZE long
		get IS_FOLDER long
		get unk2 long
		savepos BACK

		if IS_FOLDER = 1
			
			#set up the folder name
			string NEW_FOLDER_NAME = Unpack_arg2
			
			#set up new offset relative to parent offset
			math NEW_OFFSET = Unpack_arg1
			math NEW_OFFSET += OFFSET
			
			#you should be recursively calling the function here
			#unpack NEW_OFFSET NEW_FOLDER_NAME
		else
			goto OFFSET
			getdstring header 2
			if header = "NZ"
				get null short
				get SIZE long
				get ZSIZE long
				math OFFSET += 12
				clog NAME OFFSET ZSIZE SIZE
			else
				log NAME OFFSET SIZE
			endif
		endif

		goto BACK
	next i
EndFunction

```
