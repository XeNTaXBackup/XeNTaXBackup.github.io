## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-11-09T16:19:03+00:00
- Post Title: Saints Row: The Third - script for all *.???_xbox2 archives

Hi there!

I'm currently writing a script to extract all the different archives from Saints Row 3 (Xbox 360 currently, but PC should be similar) like *.vpp_xbox2 and those inside them. I'll post the final script here when it's done.
Currently supported file types:

*.vpp_xbox2
*.bnk_xbox2

```
get IDENT long
get FOLDER basename
string FOLDER += "/"
if IDENT == 0x51890ace
	callfunction vpp_xbox2 1
elif IDENT == 0x424B4844 # BKHD, bnk_xbox2 (var1)
	callfunction bnk 1
elif IDENT == 0x42535756 # BSWV063X, bnk_xbox2 (var2)
	callfunction bswv
endif

startfunction vpp_xbox2
	goto 0x154
	get FILES long
	goto 0x800
	callfunction getnameoff 1
	callfunction getdatastart 1
	for i = 1 <= FILES
		get DUMMY long
		get DUMMY long
		get OFFSET long
		math OFFSET += DATASTART
		get SIZE long
		get FF long
		get ZERO long
		savepos MYOFF
		goto NAMEOFF
		get NAME2 string
		savepos NAMEOFF
		goto MYOFF
		set NAME FOLDER
		string NAME += NAME2
		log NAME OFFSET SIZE
	next i
endfunction

startfunction getnameoff
	set NAMEOFF FILES
	math NAMEOFF *= 0x18
	math NAMEOFF += 0x800
	math NAMEOFF /= 0x800
	math NAMEOFF += 1
	math NAMEOFF *= 0x800
	goto 0x800
endfunction

startfunction getdatastart
	goto NAMEOFF
	for i = 1 <= FILES
		get NAME string
	next i
	savepos DATASTART
	math DATASTART /= 0x800
	math DATASTART += 1
	math DATASTART *= 0x800
	goto 0x800
endfunction

startfunction bnk
	FindLoc DIDX string "DIDX" 0 ""
	if DIDX == ""
	   print "DIDX section missing!"
	   cleanexit
	endif
	math DIDX += 0x08
	FindLoc DATA string "DATA" 0 ""
	set FILES DATA
	math FILES -= DIDX
	math FILES /= 12
	math DATA += 8
	goto DIDX
	get FNAME basename
	string FNAME += "_"

	endian big
	for i = 1 <= FILES
	   get IDENT long
	   get OFFSET long
	   math OFFSET += DATA
	   get SIZE long
	   math SIZE += 2
	   set NAME FOLDER
	   string NAME += FNAME
	   string NAME += IDENT
	   string NAME += ".wav"
	   log NAME OFFSET SIZE
	next i
endfunction

startfunction bswv
	goto 0
	idstring "BSWV063X"
	goto 0x18
	get FILES short
	get ZERO short
	for i = 1 <= FILES
		get IDENT long
		get OFFSET long
		get ZERO long
		get SIZE long
		set NAME FOLDER
		get NAME2 basename
		string NAME += NAME2
		string NAME += "_"
		string NAME += IDENT
		string NAME += ".wav"
		log NAME OFFSET SIZE
	next i
endfunction
```


Until further update.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-11-09T16:39:05+00:00
- Post Title: Saints Row: The Third - script for all *.???_xbox2 archives

Above script won't work for some of the vpp_xbox2 files, so I'll double-check it. Just to inform you about my process. 

Edit: Problem wasn't in the script. Seems like some of the files are actually truncated! :-\ 
The truncated files are

cutscene_tables.vpp_xbox2
da_tables.vpp_xbox2
high_mips.vpp_xbox2
misc.vpp_xbox2
misc_tables.vpp_xbox2
shaders.vpp_xbox2
soundboot.vpp_xbox2
sound_turbo.vpp_xbox2
startup.vpp_xbox2
vehicles_preload.vpp_xbox2
Nothing I can do about that currently...
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-11-09T17:08:31+00:00
- Post Title: Saints Row: The Third - script for all *.???_xbox2 archives

Something seems to be different with these because I found lots of other files inside the main archives with the same problem. It could be some kind of compression...

PLEASE HELP: [http://www.gamefront.com/files/20975664 ... x2_comp.7z](http://www.gamefront.com/files/20975664/SR3_vpp_xbox2_comp.7z)
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-11-09T17:21:07+00:00
- Post Title: Saints Row: The Third - script for all *.???_xbox2 archives

Added *.bnk_xbox2 suppport!
## Post #5
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2011-11-09T18:19:24+00:00
- Post Title: Saints Row: The Third - script for all *.???_xbox2 archives

your script seems to unpack the table files compared to the old RF:A tools but i still think its extracting them wrong or they are encrypting the xtbl files this time. because i get "Error: incomplete input file number 0, can't read 27004 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted"

and the extracted files are like this: 
ammo.xtbl
[http://www.multiupload.com/HARRPX16OD](http://www.multiupload.com/HARRPX16OD)
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-11-09T18:39:01+00:00
- Post Title: Saints Row: The Third - script for all *.???_xbox2 archives

As I wrote above, it could be some compression. I've already asked for help.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-11-10T07:58:00+00:00
- Post Title: Saints Row: The Third - script for all *.???_xbox2 archives

Do you know where are texts and fonts located please ? i mean what files ?

thx
