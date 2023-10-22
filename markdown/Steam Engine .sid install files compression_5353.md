## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-05T08:12:24+00:00
- Post Title: Steam Engine *.sid install files compression

After quite a long search for a program that can extract the the *.sid files from Steam game installations I've finally given up and written my own QuickBMS script (I don't want to install steam games just to look at their contents). However, the *.sid files are compressed or encrypted. Can anyone provide me with the correct algorithm ot implement into my script? Thanks!
Here's my script without the compression/encryption info:

```
string SIDNAME += "_0.sid" # only multiple when data files bigger than 4GB
open FDSE SIDNAME 1

get SIGN long 0
get UNK long 0
get UNK long 0
get DATINFO long 0
savepos MYOFF 0
math DATINFO += MYOFF
goto DATINFO 0
get TABLESIZE long 0
get FILES long 0
savepos DATINFO 0
goto MYOFF 0
get DUMMY short
savepos NAMEPOS 0

for i = 1 <= FILES
	
	goto NAMEPOS 0
	get FNAME string 0
	strlen EXT FNAME
	if EXT == 0
		goto NAMEPOS 0
		get ZERO byte 0
		savepos NAMEPOS 0
		get FNAME string 0
		strlen EXT FNAME
	endif
	math EXT -= 4
	getVarChr TEST FNAME EXT
	# all files in one folder are successively listed
	# so only change the folder when the read name
	# has no extension i.e. is a folder
	# (the folder variable is only changed when 
	# the function is called)
	if TEST != 0x2e
		callfunction getfolder 1
	endif
	set NAME FOLDER
	string NAME += \
	string NAME += FNAME
	savepos NAMEPOS 0
		goto DATINFO 0
		get NAMEPOS long 0
		#math NAMEPOS += 0x10
		#savepos MYOFF 0
		#goto NAMEPOS 0
		#get NAME string 0
		#goto MYOFF 0
		get UNK2 long 0
		get UNK3 long 0
		get OFFSET long 0
		get ZERO long 0
		get SIZE long 0
		get ZERO long 0
		get ONE long 0
		savepos DATINFO 0
	log NAME OFFSET SIZE 1
next i

startfunction getfolder
	goto NAMEPOS 0
	for
		get FNAME string 0
		strlen EXT FNAME
		math EXT -= 4
		getVarChr TEST FNAME EXT
		if TEST == 0x2e
			break
		else
			set FOLDER FNAME
		endif
	next
endfunction
```
 I've based it on the R.U.S.E. Demo, downloadable here: [http://www.gamershell.com/download_62790.shtml](http://www.gamershell.com/download_62790.shtml)
Thanks for your help!
## Post #2
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-11-05T08:28:22+00:00
- Post Title: Steam Engine *.sid install files compression

Try phoenix or simpack. they are both for that very purpose (amongst other things), and are both updated regularly.
The encryption keys are unique for each specific game also, some of the the technical specifications of the sim/sid/sis files differ throughout steam releases.
Hopefully this at least answers part of your query
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-11-05T13:37:13+00:00
- Post Title: Steam Engine *.sid install files compression

I don't know about the encryption, but the compression is simple PKZip
