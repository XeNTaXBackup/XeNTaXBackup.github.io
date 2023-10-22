## Post #1
- Username: SNP
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 22, 2022 11:49 am
- Post datetime: 2022-04-22T04:12:25+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

Hello everyone. I would like to ask for some help in regards to this game

I used game extractor on the Dat files on disc however I spit out plenty of "Unknown" and "Empty"  files. 

But some unknown files do seem to be texture files. The problem is I don't know how to properly view them. I used texture finder but it ended looking off

Some other stuff.

The unknown files when looked in a hex editor have a PQRS set of letters in a vertical view. I looked around and couldn't find any method that could be used to read these. there's supposedly a bms script that can parse them but I haven't found it. 

Would like any help in regarded to these files. I would have put this in the graphic section but I'm not sure if every unknown file is a texture one

Here's some examples 

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1LKjNvxT8vH6VoliwD3103iKarKsDrwZ3?usp=sharing)
[Capture.PNG](https://xentaxbackup.github.io/file/22117_Capture.PNG)
## Post #2
- Username: mn1712trungson
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 20, 2023 2:59 pm
- Post datetime: 2023-05-20T07:11:20+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

###UPDATED
You ripped the /0*.DAT/ files incorrectly.

Use this code on quickbms and upload the file again.This code should work on 00 to 04.DAT files.
After parsing all files in *DAT, you will find some files that have an offset table.
They are archive files. Run this script again on them, parsing more files inside.

```
# script for QuickBMS http://quickbms.aluigi.org

get unknownValue long
get sameValue long
for i = 0 < fileCount
	get pointer long
	get file_Size long
	math pointer *= 0x800
	math file_Size *= 0x800
	
	if file_Size != 0
		savepos position
		goto pointer
		string file_Name = ""
		string file_Name + i
		log file_Name pointer file_Size
		goto position
	endif
next i
```

Maybe someone knows this format. Don't bother with 05, 06, and 07; they are just MPEG2 videos.
## Post #3
- Username: SNP1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 09, 2021 5:23 am
- Post datetime: 2023-05-21T07:19:13+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

Hi. I didn't think I get any response (I'm TC I'm just using this spare account to reply), I actually didn't do any kind of ripping. That's how they're like on the actual disc.

I know its possible to properly extract the files from these games I just can't figure out the method to it myself, still its close. And I can tell I'm close to looking for what I want out of the files. so thanks
## Post #4
- Username: mn1712trungson
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 20, 2023 2:59 pm
- Post datetime: 2023-05-21T15:17:12+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

It's good to hear someone is interested in this game (I think it's an underrated gem and kind of unique).
This time, I'm only working on Flight-Plan's NDS games, but I also have plans for translating this game in the future.

I really don't know anything about the CPU MIPS or the file structure of the PS2. I simply analyzed the binary format to see
what was interesting inside and found something (a binary bitmap font with filename extension *BIT)
related to the game (Shining Force Feather) I was working on.
The main problem is that I don't know any PS2 debugger good enough to trace back the scripting interpreter
(all of Flight-Plan's games used that with different filename extension: *PSI3, *RTZ, *BIN, *PS, etc.).

If you know more about this game's binary format, please share it. I loved to hear that.
## Post #5
- Username: SNP1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 09, 2021 5:23 am
- Post datetime: 2023-05-21T18:24:36+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

> Reply from mn1712trungson ↑Sun May 21, 2023 11:17 pm at Sun May 21, 2023 11:17 pm
>
> 
The main problem is that I don't know any PS2 debugger good enough to trace back the scripting interpreter
(all of Flight-Plan's games used that with different filename extension: *PSI3, *RTZ, *BIN, *PS, etc.).
If you know more about this game's binary format, please share it. I loved to hear that.

Well I don't know much either sadly. That's why I turned to this place in hopes of having someone who understands it more than I could, though I did use script one some other Flight Plan games too with similar DAT structures like Black/matrix  or summon night and it works on them too, it doesn't work on something like Eternal poison which has its own unique dat format

I guess the DAT files are basically like containers for common formats of the time I recognize some PS2 sound format names in the header and BMP names too. Just hidden under whatever compression/encryption its using
## Post #6
- Username: mn1712trungson
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 20, 2023 2:59 pm
- Post datetime: 2023-05-22T05:11:08+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

The information you share about Black Matrix (Saturn) and Summon Night (PS2) is really interesting.

I still spare some free time for analyzing the binary format in this game.

So far, I knew the 03-04.DAT only contained BD and HD audio banks.
I extracted it and tested it on the Awave Studio (a lot of voices), but VGMtrans doesn't work (maybe I'm missing the sequence BQ file). 
00.DAT may contain the main() function.
01-02.DAT contained a lot of textures without header (not TIM2 file for sure), some mesh (I see some files contain the string "BONE*"),
an archive (nearly 200 files), and some unknown programs. MODULES.DAT maybe compressed.

The total size of the program and graphics maybe is only 650 MB.
If there is no compressing format, this game is really smaller than another RPG-Tactics title on PS2.
I also tested this game on real PS2 hardware. And it's loading really fast, LOL.
That's the main reason; I guess the game doesn't contain so many compressed or encrypted files.

I will update more information every Sunday if I have free time.
## Post #7
- Username: mn1712trungson
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 20, 2023 2:59 pm
- Post datetime: 2023-05-30T11:49:45+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

Sorry for the delay; I don't have time to analyze each format one by one.
So I wrote a script that splits the small archives inside 01-02.DAT files.
You can edit it again if it fails, and check the file format.

Small archive with little-endian header (usually no file name):

```
# script for QuickBMS http://quickbms.aluigi.org

endian little
get FILES short
get DUMMY short
get DUMMY long

if FILES != 0
	for i = 1 <= FILES
		get F_POINTER long
		get F_SIZE long
		math F_POINTER *= 0x10
		math F_SIZE *= 0x10
		if F_SIZE != 0
			savepos F_POS
			goto F_POINTER
			string F_NAME = ""
			string F_NAME + i
			log F_NAME F_POINTER F_SIZE
			goto F_POS
		endif
	next i + 1
else
	print "File total: %i%"
	cleanexit
endif
```


Small archive with big-endian header (usually size over 1mb with some string like SCRIPT, CAMERA, etc):

```
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0x8
get NAMES byte
padding 4
get NAME_TABLE byte
padding 4
get FILES byte
padding 4
get FILE_TABLE byte

//get files with extension
if NAMES != 0 && FILES != 0
	goto NAME_TABLE
	for n = 1 <= NAMES
	getdstring F_EXT 0x16
	get F_NUM byte
	get DUMMY byte
	get F_SUM byte
	get DUMMY byte
	savepos N_POS
		//extract the first extension
		if F_SUM == 0 && F_NUM != 0
			callfunction EXTRACT_FILE_1
		//extract the second extension and so on
		elif F_SUM != 0 && F_NUM != 0
			callfunction EXTRACT_FILE_2
		//return
		else
			goto N_POS
		endif
	next n + 1
	xmath F_TOTAL "j + k"
	print "File total: %F_TOTAL%"
//get files without extension
elif NAMES == 0 && FILES != 0
	print "Files with extension not found. Try extract files without extension."
	callfunction EXTRACT_FILE_0
	print "File total: %i%"
else
	print "Error!"
	cleanexit
endif

//function
startfunction EXTRACT_FILE_1
	goto F_TABLE
	for j = 1 <= F_NUM
		get F_POINTER threebyte
		get F_SIZE threebyte
		get NULL short
		math F_POINTER *= 0x10
		math F_SIZE *= 0x10
		if F_SIZE != 0
			savepos F_POS
			goto F_POINTER
			string F_NAME = ""
			string F_NAME = j
			string F_NAME + .
			string F_NAME + F_EXT
			log F_NAME F_POINTER F_SIZE
			goto F_POS
		endif
	next j + 1
endfunction

startfunction EXTRACT_FILE_2
	goto F_POS
	for k = j <= F_NUM
		get F_POINTER threebyte
		get F_SIZE threebyte
		get NULL short
		math F_POINTER *= 0x10
		math F_SIZE *= 0x10
		if F_SIZE != 0
			savepos F_POS
			goto F_POINTER
			string F_NAME = ""
			string F_NAME = k
			string F_NAME + .
			string F_NAME + F_EXT
			log F_NAME F_POINTER F_SIZE
			goto F_POS
		endif
	next k + 1
endfunction

startfunction EXTRACT_FILE_0
	goto F_TABLE
	for i = 1 <= FILES
	get F_POINTER threebyte
	get F_SIZE threebyte
	get NULL short
	math F_POINTER *= 0x10
	math F_SIZE *= 0x10
		if F_SIZE != 0
			savepos F_POS
			goto F_POINTER
			string F_NAME = ""
			string F_NAME + i
			string F_NAME + .
			log F_NAME F_POINTER F_SIZE
			goto F_POS
		endif
	next i + 1
endfunction
//end
```
## Post #8
- Username: SNP1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 09, 2021 5:23 am
- Post datetime: 2023-05-30T21:48:13+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

Thanks again.

I tested the scripts with the 01-02 dat files. The big endian one spitted some new formats I don't quite recognize alongside the usual script/camera strings and mostly smaller dat files 

The small bms script just mostly outputted smaller generic files 

[https://www.mediafire.com/folder/cni9itltg7w4e/1-2dat](https://www.mediafire.com/folder/cni9itltg7w4e/1-2dat)   here's the result folder with using the big endian bms script. Feel free to take your time with this.
## Post #9
- Username: mn1712trungson
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 20, 2023 2:59 pm
- Post datetime: 2023-05-31T12:16:10+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

##QUICKLY FIXES
First, sorry for my bad.The script I wrote is wrong. I updated with a new script.

1. Use this script to cut the ##.DAT file on DVD.

```
# script for QuickBMS http://quickbms.aluigi.org

endian little
get FILES short
get DUMMY short
get DUMMY long

if FILES != 0
	for i = 0 < FILES
		get F_POINTER long
		get F_SIZE long
		math F_POINTER *= 0x800
		math F_SIZE *= 0x800
		//Don't extract empty file
		if F_SIZE != 0
			savepos F_POS
			goto F_POINTER
			string F_NAME = "0"
			string F_NAME + i
			string F_NAME + .
			string F_NAME + dat
			log F_NAME F_POINTER F_SIZE
			goto F_POS
		endif
	next i
	print "File total: %i%"
else
	print "Error!"
	cleanexit
endif

```


2. Use this script to cut the little-endian archives after cut ##.DAT file.
I didn't check all files for this, but the first file inside ##.DAT is little-endian.
This file is like a dict or offset table.

```
# script for QuickBMS http://quickbms.aluigi.org

endian little
get FILES short
get DUMMY short
get DUMMY long

if FILES != 0
	for i = 0 < FILES
		get F_POINTER long
		get F_SIZE long
		math F_POINTER *= 0x10
		math F_SIZE *= 0x10
		//Don't extract empty file
		if F_SIZE != 0
			savepos F_POS
			goto F_POINTER
			string F_NAME = "0"
			string F_NAME + i
			string F_NAME + .
			string F_NAME + dat
			log F_NAME F_POINTER F_SIZE
			goto F_POS
		endif
	next i
	print "File total: %i%"
else
	print "Error!"
	cleanexit
endif

```


3. Use this script to cut the big-endian archives after cut ##.DAT file.
The big-endian archives had strings like BI, SCRIPT, MAP, AI, Script, Screen, AspDat, QspDat, Camera, Unit, ADPCM, SE,
システム (system),  タイトル (title),  勝利条件 (victory condition), 敗北条件 (defeat condition), etc.
So far, I've checked. No single file or archive has a file name.

```
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0x8
get NAMES byte
padding 4
get NAME_TABLE byte
padding 4
get FILES byte
padding 4
get FILE_TABLE byte

//get files with extension
if NAMES != 0 && FILES != 0
	codepage 932
	goto NAME_TABLE
	for n = 0 < NAMES
	getdstring F_EXT 0x10
	get F_NUM byte
	get DUMMY byte
	get F_SUM byte
	get DUMMY byte
	savepos N_POS
		//extract the first extension
		if F_NUM != 0 && F_SUM == 0
			goto FILE_TABLE
			for j = 0 < F_NUM
				get F_POINTER threebyte
				get F_SIZE threebyte
				get NULL short
				math F_POINTER *= 0x10
				math F_SIZE *= 0x10
				savepos T_POS
				if F_SIZE != 0
					goto F_POINTER
					string F_NAME = "0"
					xmath F_COUNT "j + F_SUM"
					string F_NAME + F_COUNT
					string F_NAME + _
					string F_NAME + F_EXT
					string F_NAME + .
					log F_NAME F_POINTER F_SIZE
				endif
			goto T_POS
			next j
		//extract the second extension and so on
		elif F_NUM != 0 && F_SUM != 0
			goto T_POS
			for k = 0 < F_NUM
				get F_POINTER threebyte
				get F_SIZE threebyte
				get NULL short
				math F_POINTER *= 0x10
				math F_SIZE *= 0x10
				savepos T_POS
				if F_SIZE != 0
					goto F_POINTER
					string F_NAME = "0"
					xmath F_COUNT "k + F_SUM"
					string F_NAME + F_COUNT
					string F_NAME + _
					string F_NAME + F_EXT
					string F_NAME + .
					log F_NAME F_POINTER F_SIZE
				endif
			goto T_POS
			next k
		endif
	goto N_POS
	next n
	xmath F_TOTAL "F_SUM + F_NUM"
	print "File total: %F_TOTAL%"
//get files without extension
elif NAMES == 0 && FILES != 0
	callfunction EXTRACT_FILE_0
else
	print "Error!"
	cleanexit
endif

//function
startfunction EXTRACT_FILE_0
	goto FILE_TABLE
	for i = 0 < FILES
	get F_POINTER threebyte
	get F_SIZE threebyte
	get NULL short
	math F_POINTER *= 0x10
	math F_SIZE *= 0x10
	savepos T_POS
		if F_SIZE != 0
			goto F_POINTER
			string F_NAME = "0"
			string F_NAME + i
			string F_NAME + .
			log F_NAME F_POINTER F_SIZE
		endif
	goto T_POS
	next i
	print "File total: %i%"
endfunction
//end
```


4. About the PQRS file: This file contains custom graphics made by Flight-Plan's in-house tool. Still analyzing.
Usually more complex than the format used on NDS and GBA. There are still some files like that and I don't know how it works.
Some are simple, some are confusing (swizzling).

```
# script for QuickBMS http://quickbms.aluigi.org
/*
NAME long
VERSION long
MAPPING long
DUMMY long
COUNT long
UNKNOWN long
GRAPHIC long
PALETTE long

goto GRAPHIC
	DUMMY 0x10
	WIDTH short
	HEIGHT short
	UNKNOWN short
	UNKNOWN short
	OFFSET long
	SIZE long #SIZE*10	
goto PALETTE
	DUMMY 0x10
	WIDTH short
	HEIGHT short
	UNKNOWN long
	OFFSET long
	BPP long #BPP*10; 40 = 4bpp, 400 = 8bpp
*/
```



So what is important to do? Since all files do not have a file name. And the number of files is huge (maybe around 7000–9000).
We need to make a spreadsheet or text file that indexes each file and directory.
This will help us know which file format is in which directory. In case someone wants to translate this game, LOL.

I can handle this by myself. But that takes a very long time to finish. That's just finding and indexing all files and directories.
## Post #10
- Username: SNP1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 09, 2021 5:23 am
- Post datetime: 2023-06-01T01:44:08+00:00
- Post Title: Sacred Blaze (PS2) Unknown Files help

Ohh. I see now. I just got back home.

Alright I'll test the scripts again and see what happens.

Although, I'm not invested in actually translating the games persay. I do think the thread would be a useful sort of information just in case someone does decide to tackle them. Since the last time I looked around these games stumped just about everyone else on places like Zenhax/gbatemp etc etc

There certainly is a lot of files, but I've never been quite at good as I could be at organizing them

Hm. I think the last script isn't working properly, the PQRS one (or maybe I misunderstood it)
