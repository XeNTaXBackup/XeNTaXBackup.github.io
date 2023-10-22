## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2018-12-04T21:45:11+00:00
- Post Title: Just Cause 4 .arc/tab

I can make out some stuff in HEX like some FSB5 file headers, but so far seems the rest is compressed.
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-12-05T15:14:22+00:00
- Post Title: Just Cause 4 .arc/tab

Uses Oodle lib V7
TAB structure

```
//--- 010 Editor v6.0.2 Binary Template
//
// File:avalanche tab
// Author:Lukas Cone
// Revision: Just Cause 4
// Purpose:
//--------------------------------------
SetBackColor( cLtGreen );
struct {
	uint ID;
	ushort version1, version2;
    uint allignment;
	int null;
}Header;

typedef struct {
	int hash;
	int unk;
}HashEntry;

HashEntry unkHash;
int numHashes;
HashEntry hashes[numHashes];

while (FileSize() > FTell())
{
	struct {
		int hash, offset, compressed_size, size;
		short HashEntryID;
		char unk0, unk1;
	}FileEntry;
}


```


Compressed files are beyond me, they probably use individual compression, depending on file type since I could see strings within compressed script/animation files.

Compressed file layout:

```
//--- 010 Editor v6.0.2 Binary Template
//
// File:arc compressed entry
// Author:Lukas Cone
// Revision: Just Cause 4
// Purpose:
//--------------------------------------
SetBackColor( cLtGreen );
struct {
	short ID; // Always 0x8c06
	char unk0, 
		unk1;
	int hash; //crc?
	char headerID[8]; // first 8 bytes from file
}Header;



```
## Post #3
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2018-12-14T19:36:24+00:00
- Post Title: Just Cause 4 .arc/tab

Ok here is temporary bms script which can unpack some of arc files. QBMS obviously can't handle other oodle compression algo... Filenames are hashed so....
Thanks PredatorCZ for initial struct.

```
comtype OODLE

open FDDE "tab" 0
open FDDE "arc" 1
get FILES asize
idstring "TAB"
getdstring DUMMY 0x15
get HASHTABLE long
for i = 0 < HASHTABLE
	get HASH0 long
	get HASH1 long
next i
savepos STARTOFF
math FILES -= STARTOFF
math FILES /= 20
for i = 0 < FILES
endian big
get NAME long
endian little
get OFFSET long
get ZSIZE long
get SIZE long
get FILETYPE byte
get FILETYPE1 byte
get COMPRESSION byte
get COMPTYPE byte

if ZSIZE == SIZE
	callfunction SETEXTUNC
else
	callfunction SETEXTCOM
   endif
next i

startfunction SETEXTUNC
if SIZE u> 16
	log MEMORY_FILE OFFSET SIZE 1
	goto 0 MEMORY_FILE
	get SIGN1 byte MEMORY_FILE
	goto 0 MEMORY_FILE
	getdstring SIGN3 3 MEMORY_FILE
	goto 0 MEMORY_FILE
	getdstring SIGN4 4 MEMORY_FILE
	goto 4 MEMORY_FILE
	getdstring SIGN8 4 MEMORY_FILE
	goto 12 MEMORY_FILE
	getdstring SIGN12 4 MEMORY_FILE
	goto 16 MEMORY_FILE
	getdstring SIGN16 4 MEMORY_FILE
	
	if SIGN4 == "KB2j" || SIGN4 == "BIKi"
        set EXT string "bik"
	elif SIGN4  == " FDA" || SIGN12 == " FDA"
        set EXT string "fda"
	elif SIGN4 == "RTPC"
        set EXT string "rtpc"
	elif SIGN4 == "AVTX"
        set EXT string "avtx"
	elif SIGN4 == "DDS "
        set EXT string "dds"
	elif SIGN4 == "RIFF"
        set EXT string "riff"		
	elif SIGN8 == "TAG0"
        set EXT string "tag"
	elif SIGN8 == "SARC"
        set EXT string "sarc"
	elif SIGN16 == "FSB5"
        set EXT string "fsb"
	elif SIGN3 == "CFX" || SIGN3 == "GFX"
        set EXT string "swf"
	elif SIGN1 == 0x04
        set EXT string "4"
    else
        string EXT f= dat
	endif
endif	
	string NAME p "%s/%08X.%s" game NAME EXT
	log NAME OFFSET SIZE 1
endfunction

startfunction SETEXTCOM
if SIZE u> 16
	log MEMORY_FILE OFFSET ZSIZE 1
	goto 0 MEMORY_FILE
	get SIGN short MEMORY_FILE
	if SIGN == 1676
		clog MEMORY_FILE OFFSET ZSIZE SIZE 1		
		goto 0 MEMORY_FILE
		get SIGN1 byte MEMORY_FILE
		goto 0 MEMORY_FILE
		getdstring SIGN3 3 MEMORY_FILE
		goto 0 MEMORY_FILE
		getdstring SIGN4 4 MEMORY_FILE
		goto 4 MEMORY_FILE
		getdstring SIGN8 4 MEMORY_FILE
		goto 12 MEMORY_FILE
		getdstring SIGN12 4 MEMORY_FILE
		goto 16 MEMORY_FILE
		getdstring SIGN16 4 MEMORY_FILE

		if SIGN4 == "KB2j" || SIGN4 == "BIKi"
			set EXT string "bik"
		elif SIGN4  == " FDA" || SIGN12 == " FDA"
			set EXT string "fda"
		elif SIGN4 == "RTPC"
			set EXT string "rtpc"
		elif SIGN4 == "AVTX"
			set EXT string "avtx"
		elif SIGN4 == "DDS "
			set EXT string "dds"
		elif SIGN4 == "RIFF"
			set EXT string "riff"		
		elif SIGN8 == "TAG0"
			set EXT string "tag"
		elif SIGN8 == "SARC"
			set EXT string "sarc"
		elif SIGN16 == "FSB5"
			set EXT string "fsb"
		elif SIGN3 == "CFX" || SIGN3 == "GFX"
			set EXT string "swf"
		elif SIGN1 == 0x04
			set EXT string "4"
		else
			string EXT f= dat
		endif
			string NAME p "%s/%08X.%s" game NAME EXT
			clog NAME OFFSET ZSIZE SIZE 1
	else
		string NAME p "%s/%s/%08X.comp" game compressed NAME
		log NAME OFFSET ZSIZE 1
	endif	
endif
endfunction

```


EDiT: Updated with extension support.
EDiT1: Now unpack all files. Those which can't be decompressed are located in "compressed" folder.
## Post #4
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2019-01-08T05:53:55+00:00
- Post Title: Just Cause 4 .arc/tab

well done~~;;
## Post #5
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2019-05-17T17:25:25+00:00
- Post Title: Just Cause 4 .arc/tab

it's can be update for rage 2 please is use same engine

-------------------
*EXCEPTION HANDLER*
-------------------
An error or crash occurred:

*EH* ExceptionCode      c0000005 access violation
*EH* ExceptionFlags     00000000
*EH* ExceptionAddress   76FE91AD
                        76F60000 + 000891ad msvcrt.dll
*EH* NumberParameters   00000002
*EH*                    00000001
*EH*                    114C1FFF

Last script line before the error or that produced the error:
  38  log MEMORY_FILE OFFSET SIZE 1
