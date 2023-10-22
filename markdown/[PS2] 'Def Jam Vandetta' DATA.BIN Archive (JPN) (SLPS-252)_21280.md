## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2019-10-22T04:06:34+00:00
- Post Title: [PS2] 'Def Jam Vandetta' DATA.BIN Archive (JPN) (SLPS-252)

I've written a python script that works as a plugin for noesis to extract contents from the ISO of the japanese version of def jam vandetta (PS2).

two files are required;
-SLPS_252.75
-DATA/DATA.BIN

Note that there was a BMS script written by aluigi previously for the european version, which does a signature scan on the DATA.BIN file. It may work on all regions so if your interested in that checkout the old thread
[viewtopic.php?t=6480](https://forum.xentax.com/viewtopic.php?t=6480)

The python script I wrote reads the file table in the ELF file to dump the files instead of doing a signature scan. This is a more true way of doing the dump on the DATA.BIN however requires that ELF file and also means it'll only work on that one region. :\

python script:

```
#
# requires two files;
# SLPS_252.75
# Data/data.bin
#
# Author: mariokart64n
# Date:   October 20 2019
# 

from inc_noesis import *

gameID = "SLPS_252.75"

def registerNoesisTypes():
	#noesis.logPopup()
	handle = noesis.register("Def Jam Vandetta (PS2-JPN)", ".75")
	noesis.setHandlerExtractArc(handle, binExtractArc)
	return 1

def binExtractArc(fileName, fileLen, justChecking):
	fname = rapi.getLocalFileName(fileName)
	datafile = rapi.getDirForFilePath(fileName) + "DATA\\DATA.BIN"
	
	if justChecking:
		if fname.upper() != gameID:
			noesis.messagePrompt("Extraction Failed:\nUnsupported ELF File '" + fname + "'")
			return 0
		if (rapi.checkFileExists(datafile)) == False:
			noesis.messagePrompt("Extraction Failed:\nUnable to Find the data file 'DATA\\DATA.BIN'")
			return 0
		return 1
	
	elf = open(fileName, "rb")
	data = open(datafile, "rb")
	
	table_count = 293
	
	num = "000"
	file_ext = ".bin"
	for entry in range(0, table_count):
		elf.seek(0x0015A088 + (entry * 0x08))
		file_offset = noeUnpack("<I", elf.read(4))[0] * 0x0800
		file_size = noeUnpack("<I", elf.read(4))[0] * 0x0800
		
		data.seek(file_offset)
		file_ext = "."
		num = ("000" + str(entry + 1))[-3:]
		for c in range(0, 4):
			cc = data.read(1)[0]
			if cc > 47 and  cc < 91:
				if cc != 32:
					file_ext += chr(cc)
			else:
				if cc != 32:
					file_ext = ".bin"
					break
				
			
		
		file_ext = file_ext.lower()
		if file_ext == ".tim2": file_ext = ".tm2"
		
		data.seek(file_offset)
		rapi.exportArchiveFile("data_" + num + file_ext, data.read(file_size))
	
	elf.close()
	data.close()
	
	return 1

```

[fmt_defjamvandetta_SLPS_252.zip](https://xentaxbackup.github.io/file/16937_fmt_defjamvandetta_SLPS_252.zip)
## Post #2
- Username: MaouYumisu
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 29, 2019 9:05 am
- Post datetime: 2020-12-11T17:30:35+00:00
- Post Title: [PS2] 'Def Jam Vandetta' DATA.BIN Archive (JPN) (SLPS-252)

Thanks for this. Been looking for something that could dump the .bin file but it looks like now there's .PAK and more random .bin files to go through. I'll look for tools for them.
