## Post #1
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-01-23T20:52:25+00:00
- Post Title: AGS file format description

I was asked by private message to publish the file format for AGS (Adventure Game studio).
This format has a lot of dependencies and can't be described as a "format" directly, but rather as an algorithm.
May this description help you.

General container file structure

```
START_HEADER		;Start-Marker of the container
NUMOFVOLUMES		;DWORD, Number of available volume files
VOLUMENAME_TABLE	;File names for each volume file
			; length depends on SUBFORMAT
			;LENGTH_0fh=20, MAXLENGTH_14h=50
NUMOFFILES		;WORD, number of files
FILENAME_TABLE		;File names;
			; entry length and encryption depends on SUBFORMAT,
			; unused space may be filled with garbage
			;MAXLENGTH_0ah=13, MAXLENGTH_0fh=25, MAXLENGTH_14h=100
LENGTH_TABLE		;DWORDS, Length entries for each file
OFFSET_TABLE		;DWORDS, offsets for each file relative to START_HEADER 
VOLUMEINDEX_TABLE	;BYTES, zero-based indices for VOLUMENAME_TABLE
DATA
[END_HEADER]		;Header at the end of a file if INSTALL_EXE_DATA is available

```

END_HEADER

```
BYTES	END_MAGIC:"CLIB",1,2,3,4,"SIGE"

```

START_HEADER	;Header at the start of the container

```
BYTE	SUBFORMAT:06h/0ah/0bh/0fh/14h
BYTE	CRYPT_BYTE/VOLUME_INDEX
 ;SUBFORMAT < 0ah:
[BYTE	dummy
 WORD	NUMOFFILES]

```

File name encryption key for SUBFORMAT>0ah

```

```

FILENAME_TABLE

```
BYTES(13)	;unencrypted filename

SUBFORMAT<=0bh:
BYTES(13)	;substract CRYPT_BYTE from BYTE[name_index] until BYTE[name_index+1]=0

SUBFORMAT=0fh:
BYTES(25)	;use KEY as a ring buffer
		;substract BYTE[KEY_index] from BYTE[name_index] until result is zero

SUBFORMAT=14h:
WORD		;number of following bytes, multiplied by 5
BYTES		;variable number of bytes, 100 maximum
		;use KEY as a ring buffer
		;substract BYTE[KEY_index] from BYTE[name_index] until result is zero

```
