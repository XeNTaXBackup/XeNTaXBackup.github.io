## Post #1
- Username: MadDriver
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 14, 2011 7:39 am
- Post datetime: 2011-07-13T23:51:18+00:00
- Post Title: How to extract .big files of TDU 2??

Hey guys and sorry for my bad english, but i need your help, reading the topic...

I have installed TDU2 (buy) in this root: D:\Atari\TDU2

And also i have Quick BMS Tool (Last Version)

But, when i go to extract car .bnk files packed in bigfile_RU_5.big the Quick BMS launch this error:

0 Files found in 1 sec.

I use this .bms script called tdu2.bms and i tried to rename to tdu2_bnk.bms:

```
Open FDDE big 1
Endian big
GetDString DUMMY 12
Get OFFS long
GoTo OFFS
Get DUMMY long
Get NUMHASHES long
Get HASHOFFSET long
Math HASHOFFSET += OFFS
Get NUMFILEREC long
Get FILERECOFFSET long
Math FILERECOFFSET += OFFS
If NUMHASHES != NUMFILEREC
  CleanExit
EndIf
For I = 0 < NUMHASHES
  GoTo HASHOFFSET
  Get HASH1 long
  Get HASH2 long
  String NAME p= "%08X%08X.bin" HASH1 HASH2
  SavePos HASHOFFSET
  GoTo FILERECOFFSET
  Get FILESIZE long
  Get DUMMY long # compression?
  Get FILEOFFSET long
  SavePos FILERECOFFSET
  Math MEMSIZE = FILESIZE
  Math MEMSIZE x 4
  Log MEMORY_FILE FILEOFFSET MEMSIZE 1
  If MEMSIZE != FILESIZE
    Math MEMSIZE -= 4
    GetVarChr TMP MEMORY_FILE MEMSIZE long
    Math TMP ^= 0xD7A8E2D4
    PutVarChr MEMORY_FILE MEMSIZE TMP long
  EndIf
  FileXOR "\xD7\xA8\xE2\xD4"
  Log NAME 0 FILESIZE MEMORY_FILE
  FileXOR ""
Next I
```


Also i tried with this .bms script:

```
Set NAME string ""
Log MEMORY_FILE 0 0
PutVarChr MEMORY_FILE 0 4 long
GetDString DUMMY 8
GetDString ID 4
If ID != "KNAB"
  CleanExit
EndIf
GoTo 0x28
Get NUMFILES long
Get DUMMY long
Get FATOFFSET long
Math FATOFFSET += 8
Get DUMMY long
Get NAMESOFFSET long
Math NAMESOFFSET += 8
Get FILESORDER long
Math FILESORDER += 8
PutVarChr MEMORY_FILE 0 FILESORDER long
GoTo NAMESOFFSET
If NUMFILES != 0
  CallFunction Parser
EndIf

StartFunction Parser
  Get NAMESZ byte
  If NAMESZ > 0x7F
    String FULLNAME += NAME
    String FULLNAME += \
    Get FOLDERS byte
   If FOLDERS > 0x7F
     Get TMP byte
     Math TMP < 7
     Math FOLDERS & 0x0000007F
     Math FOLDERS | TMP
#     Print %FOLDERS%
   EndIf
    Math NAMESZ ^= 0xFF
    Math NAMESZ += 1
    GetDString NAME NAMESZ
    For I = 0 < FOLDERS
      CallFunction Parser
    Next I
  Else
    GetDString BASENAME NAMESZ
    String FULLNAME += BASENAME
    String FULLNAME += NAME
#   Print %FULLNAME%
   SavePos NAMESOFFSET
   GetVarChr FILESORDER MEMORY_FILE 0 long
   GoTo FILESORDER
   If NUMFILES > 0x100
     Get FILENUMBER word
   Else
     Get FILENUMBER byte
   EndIf
   SavePos FILESORDER
   PutVarChr MEMORY_FILE 0 FILESORDER long
   Math FILENUMBER *= 0x14
   Math FATOFFSET += FILENUMBER
   GoTo FATOFFSET
   Get OFFSET long
   Get SIZE long
   GetDString DUMMY 12
    Log FULLNAME OFFSET SIZE
   GoTo NAMESOFFSET
  EndIf
EndFunction Parser
```


And i have the problem again 

My questions:

- Whats the working script for extract content in .big files (like .bnk or other files)
- I go to convert the Bugatti Veyron SS to GTA SA can you give me the model (including rims) and textures??

Thanks for reading
