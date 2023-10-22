## Post #1
- Username: kessmo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 29, 2018 7:06 pm
- Post datetime: 2018-01-29T11:35:42+00:00
- Post Title: dreamcast BIN extraction (SARC archive) PLEASE HELP

Hello,
I'm here asking for help to extract some files.
They are contained in BIN files, and every included filename appear in clear text in HEX in the following lines.
But i can't find any clue on how this works... 

I join a small file that I would like to extract.

Thanks for your help!
See ya
## Post #2
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-29T14:38:52+00:00
- Post Title: dreamcast BIN extraction (SARC archive) PLEASE HELP

quick and dirty, there you go...


greetz WV
[SARCReader.zip](https://xentaxbackup.github.io/file/13858_SARCReader.zip)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-29T17:36:12+00:00
- Post Title: dreamcast BIN extraction (SARC archive) PLEASE HELP

and a bms script just for kicks  

```

get FOLDER basename 
idstring "SARC"
get FILES long
for i = 1 to FILES
	get COMP_FLAG long //0 = not compressed, 1 = compressed ??
	get ZSIZE long //compressed size??
	get SIZE long
	get OFFSET long
	getdstring NAME 0x100
	string NAME ! \
	string NAME p "%s\%s" FOLDER NAME
	if COMP_FLAG == 0
		log NAME OFFSET SIZE
	//else 
	//	comtype ??
	//	clog NAME OFFSET ZSIZE SIZE
	endif
next i
```

not enough samples to confirm any compression stuff so i commented those parts out
## Post #4
- Username: kessmo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 29, 2018 7:06 pm
- Post datetime: 2018-01-29T22:22:43+00:00
- Post Title: dreamcast BIN extraction (SARC archive) PLEASE HELP

Big thanks!!!! Very quick solution!
You made my day!

It's perfectly working with the file I provided but with files from other region version of the game, it produces some texture files that have different headers.

Maybe devs made some serious changes between versions.

I'll figure it out, so once again: Thanks!!!
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-06T03:13:51+00:00
- Post Title: dreamcast BIN extraction (SARC archive) PLEASE HELP

here is Noesis python script to open the txr textures extracted from the bin sample  


 tex_SegaRally2_DC_txr.zip
(623 Bytes) Downloaded 38 times


supports r5g6b5 format
## Post #6
- Username: kessmo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 29, 2018 7:06 pm
- Post datetime: 2018-02-17T12:13:51+00:00
- Post Title: dreamcast BIN extraction (SARC archive) PLEASE HELP

Thanks for the help mates!
