## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-09T12:27:52+00:00
- Post Title: Nintendo DS *.sdat

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-06T12:50:43+00:00
- Post Title: Nintendo DS *.sdat

Just re-uploaded the file if anyone wants to take a look!
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-04-07T09:05:45+00:00
- Post Title: Nintendo DS *.sdat

i cheated twice. first, there was a fairly complete spec, and second, this only extracts the final section of files you said the dump tool stopped at.

```
#    xentax.com

# Format specification: http://pkhax.elpenguino.net/sdat.html#sdat

#! Only written to extract STRM (stream) file types !#


## HEADER
idstring "SDAT"
goto 16

get pSYMBOL long	# pointer to filename tables (8)
get sSYMBOL long

get pINFO long		# pointer to file info tables (8)
get sINFO long

get pFAT long		# pointer to file allocation table
get sFAT long


## FILENAME TABLES
goto pSYMBOL

idstring "SYMB"

savepos STRMPOS
math STRMPOS += 4	# skip size
math STRMPOS += 28	# STRM is the last of 8 pointers (skips 7 * sizeof(int))
goto STRMPOS

get STRMTABLE long	# pointer to STRM filename table
math STRMTABLE += pSYMBOL
goto STRMTABLE

get FILES long		# number of filenames in the table (hence, number of files to extract)

for i = 1 to FILES

	get FNOFFSET long
	savepos NEXTI

	math FNOFFSET += pSYMBOL
	goto FNOFFSET
	get NAME string
	string NAME += ".strm"	# suggested extension

	# now we need to lookup the fileid to find the pointer from the FAT table

	## FILE INFO TABLES
	goto pINFO

	idstring "INFO"

	savepos STRMINFOPOS		# see file name table notes
	math STRMINFOPOS += 4
	math STRMINFOPOS += 28
	goto STRMINFOPOS

	get STRMINFO long		# pointer to STRM info table
	math STRMINFO += pINFO

	goto STRMINFO
	# get FILES2 long 
	set PTR 4
	math PTR *= i # starts at 1, so will always skip 4

	savepos INFOLOOKUP
	math INFOLOOKUP += PTR
	goto INFOLOOKUP
	
	get INFOPTR long
	math INFOPTR += pINFO
	goto INFOPTR

	get FILEID short # :D

	# now we need to lookup the pointer from the FAT table

	## FAT
	goto pFAT

	idstring "FAT "

	get NULL long			# size of entire FAT block
	get FILECOUNT long		# files in table

	if FILEID > FILECOUNT
		print "could not continue with %NAME% (id:%FILEID%)"
		cleanexit
	endif

	math FILEID *= 16 ## offset + size + 8-byte padding
	savepos XX
	math XX += FILEID
	goto XX

	get OFFSET long
	get SIZE long

	log NAME OFFSET SIZE

	goto NEXTI

next i

```
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-07T11:05:13+00:00
- Post Title: Nintendo DS *.sdat

Thanks a lot! 
Would have taken me ages to code it myself I guess...
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-23T00:56:51+00:00
- Post Title: Nintendo DS *.sdat

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2010-12-25T05:31:00+00:00
- Post Title: Nintendo DS *.sdat

[VGMToolbox](https://sourceforge.net/projects/vgmtoolbox/) can unpack SDATs completely.  On top of extracting all files, it'll also unpack the SWAR archives (to SWAVs) contained within the SDAT.  You can find the tool under "Misc. Tools > Extraction Tools > Nintendo DS > SDAT Extractor".
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-25T18:30:58+00:00
- Post Title: Nintendo DS *.sdat

Cool, will give it a try when I'm home again! Thanks for the info!
