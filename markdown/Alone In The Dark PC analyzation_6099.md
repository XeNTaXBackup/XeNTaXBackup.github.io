## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-19T00:04:44+00:00
- Post Title: Alone In The Dark PC analyzation

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2011-02-21T03:18:14+00:00
- Post Title: Alone In The Dark PC analyzation

.fat format is slightly different from TDU2 .map, but files in .big are compressed in 4096 b chunks, decompressing in bms script is pretty hard (but not impossible). maybe someday...
till then, script to extract compressed streams from fat+big:

```
Open FDDE big 1
Endian little
GetDString DUMMY 12
Get OFFS long
GoTo OFFS
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
  Get HASH2 long
  Get HASH1 long
  String NAME p= "%08X%08X.bin" HASH1 HASH2
  SavePos HASHOFFSET
  GoTo FILERECOFFSET
  Get FILESIZE longlong
  Get DUMMY longlong # compressed size?
  Get DUMMY longlong # uncompressed size?
  Get FILEOFFSET longlong
  SavePos FILERECOFFSET
  Log NAME FILEOFFSET FILESIZE 1
Next I
```

use it on .fat file
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-21T04:10:29+00:00
- Post Title: Alone In The Dark PC analyzation

THANKS!!!!!
## Post #4
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2011-03-02T17:18:27+00:00
- Post Title: Alone In The Dark PC analyzation

> Reply from qwerty
>
> maybe someday...
Today is that day  
The beta version of the script is ready. It unpacks (and decompress) files from the cut you provided. But there are only 5 files there, so now I'm downloading the full game to check if the script will work on it. If it will - I'll post the script.
## Post #5
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2011-03-03T14:43:40+00:00
- Post Title: Alone In The Dark PC analyzation

Tested on russian version of the game - extracted 3 full fat+big files, with 1 minor bug fixed in the script 
So, there is the script:

```
Open FDDE big 1
Endian little
GetDString DUMMY 12
Get OFFS long
GoTo OFFS
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
  Get HASH2 long
  Get HASH1 long
  String NAME p= "%08X%08X.bnk" HASH1 HASH2
  SavePos HASHOFFSET
  GoTo FILERECOFFSET
  Get FILESIZE longlong
  Get DUMMY longlong # compressed size?
  Get DUMMY longlong # uncompressed size?
  Get FILEOFFSET longlong
  SavePos FILERECOFFSET
  #Log NAME FILEOFFSET FILESIZE 1
  CallFunction UnpackFile
Next I

########################
StartFunction UnpackFile
  Endian big
  ComType lzo
  Log MEMORY_FILE FILEOFFSET FILESIZE 1
  GoTo 0x10 MEMORY_FILE
  Get CHUNKSZ long MEMORY_FILE
  Get FATOFFSET long MEMORY_FILE
  Get ZDATAOFFSET long MEMORY_FILE
  Get DUMMY long MEMORY_FILE
  Get DATASIZE longlong MEMORY_FILE
  Get ZDATASIZE longlong MEMORY_FILE
  Get BUFFSIZE long MEMORY_FILE
  Math BUFF = ZDATAOFFSET
  Math BUFF += BUFFSIZE
  Math NUMCHUNKS = ZDATAOFFSET
  Math NUMCHUNKS -= FATOFFSET
  Math NUMCHUNKS /= 4
  Log MEMORY_FILE2 0 0
  PutVarChr MEMORY_FILE2 DATASIZE 0
  Log MEMORY_FILE2 0 0
  Append
  GoTo FATOFFSET MEMORY_FILE
  For J = 0 < NUMCHUNKS
    Get ZCHUNKSZ long MEMORY_FILE
    Math ZDATAOFFSET += ZCHUNKSZ
    If ZDATAOFFSET > BUFF
      Math ZDATAOFFSET -= ZCHUNKSZ
      Math ZDATAOFFSET x= 0x800
      Math BUFF = ZDATAOFFSET
      Math BUFF += BUFFSIZE
    Else
      Math ZDATAOFFSET -= ZCHUNKSZ
    EndIf
    If ZCHUNKSZ == 0
      Break
    ElseIf ZCHUNKSZ < CHUNKSZ
      CLog MEMORY_FILE2 ZDATAOFFSET ZCHUNKSZ CHUNKSZ MEMORY_FILE
    Else
      Log MEMORY_FILE2 ZDATAOFFSET ZCHUNKSZ MEMORY_FILE
    EndIf
    Math ZCHUNKSZ x= 0x10
    Math ZDATAOFFSET += ZCHUNKSZ
  Next J
  Append
  Log NAME 0 DATASIZE MEMORY_FILE2
  Endian little
EndFunction
########################
```

You've got a lot of .bnk files in output folder, they can be unpacked using [bnk script from tdu2](http://forum.xentax.com/viewtopic.php?p=49209#p49209).
To extract them all at once (it's a loooong process) just run 

```
quickbms.exe -o tdu2_bnk.bms d:\input_folder_with_all_bnks d:\output_folder
```

Some types of resources are in xmbf databases (with different extensions - xmt, xmm, xmg, xmi and others). I have no idea how to get them. But sounds, scripts and some other are in plain formats.
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-03-03T22:04:32+00:00
- Post Title: Alone In The Dark PC analyzation

You are my hero 

will try this out
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-03-04T03:37:35+00:00
- Post Title: Alone In The Dark PC analyzation

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2011-03-04T03:53:22+00:00
- Post Title: Alone In The Dark PC analyzation

> Reply from OrangeC
>
> any chance to support x360 version?
Yes! just change the endianess to big  

```
Open FDDE big 1
Endian big
GetDString DUMMY 12
Get OFFS long
GoTo OFFS
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
  Get HASH2 long
  Get HASH1 long
  String NAME p= "%08X%08X.bnk" HASH2 HASH1
  SavePos HASHOFFSET
  GoTo FILERECOFFSET
  Get FILESIZE longlong
  Get DUMMY longlong # compressed size?
  Get DUMMY longlong # uncompressed size?
  Get FILEOFFSET longlong
  SavePos FILERECOFFSET
  #Log NAME FILEOFFSET FILESIZE 1
  CallFunction UnpackFile
Next I

########################
StartFunction UnpackFile
  #Endian big
  ComType lzo
  Log MEMORY_FILE FILEOFFSET FILESIZE 1
  GoTo 0x10 MEMORY_FILE
  Get CHUNKSZ long MEMORY_FILE
  Get FATOFFSET long MEMORY_FILE
  Get ZDATAOFFSET long MEMORY_FILE
  Get DUMMY long MEMORY_FILE
  Get DATASIZE longlong MEMORY_FILE
  Get ZDATASIZE longlong MEMORY_FILE
  Get BUFFSIZE long MEMORY_FILE
  Math BUFF = ZDATAOFFSET
  Math BUFF += BUFFSIZE
  Math NUMCHUNKS = ZDATAOFFSET
  Math NUMCHUNKS -= FATOFFSET
  Math NUMCHUNKS /= 4
  Log MEMORY_FILE2 0 0
  PutVarChr MEMORY_FILE2 DATASIZE 0
  Log MEMORY_FILE2 0 0
  Append
  GoTo FATOFFSET MEMORY_FILE
  For J = 0 < NUMCHUNKS
    Get ZCHUNKSZ long MEMORY_FILE
    Math ZDATAOFFSET += ZCHUNKSZ
    If ZDATAOFFSET > BUFF
      Math ZDATAOFFSET -= ZCHUNKSZ
      Math ZDATAOFFSET x= 0x800
      Math BUFF = ZDATAOFFSET
      Math BUFF += BUFFSIZE
    Else
      Math ZDATAOFFSET -= ZCHUNKSZ
    EndIf
    If ZCHUNKSZ == 0
      Break
    ElseIf ZCHUNKSZ < CHUNKSZ
      CLog MEMORY_FILE2 ZDATAOFFSET ZCHUNKSZ CHUNKSZ MEMORY_FILE
    Else
      Log MEMORY_FILE2 ZDATAOFFSET ZCHUNKSZ MEMORY_FILE
    EndIf
    Math ZCHUNKSZ x= 0x10
    Math ZDATAOFFSET += ZCHUNKSZ
  Next J
  Append
  Log NAME 0 DATASIZE MEMORY_FILE2
  #Endian little
EndFunction
########################
```

but xbox bnks are different too (maybe just endianess, like in .fat, maybe not), so tdu2_bnk script won't work. 

UPDATE: Yes, it's just big endian, so I modified tdu2_bnk script. All 3 scripts are in attachment: two scripts for PC and X360 versions of big+fat, and one universal bnk script for both platforms 
[AitD.rar](https://xentaxbackup.github.io/file/4007_AitD.rar)
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-03-04T13:13:58+00:00
- Post Title: Alone In The Dark PC analyzation

Once again you saved!! 

thanks!!
## Post #10
- Username: NewHewkas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 19, 2011 12:11 am
- Post datetime: 2011-06-18T16:19:33+00:00
- Post Title: Alone In The Dark PC analyzation

Hi!

I'm new here, so i hope this is the right topic to ask.

I used your script on AITD 5's big files to .bnks then i extract them with the tdu2's script. Now, i have the files what i would like to have (the language files .lng), but how can I find the fonts, in which file(s)?

Can you help me, please?
## Post #11
- Username: chronicle
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 17, 2012 10:24 am
- Post datetime: 2012-05-17T04:05:39+00:00
- Post Title: Alone In The Dark PC analyzation

Can anyone help with script for .bnk files after when extracted .big files?
I tryed this code

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

but when I use it quickbms write me 0 files found
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-05-17T09:37:33+00:00
- Post Title: Alone In The Dark PC analyzation

> Reply from NewHewkas
>
> Hi!

I'm new here, so i hope this is the right topic to ask.

I used your script on AITD 5's big files to .bnks then i extract them with the tdu2's script. Now, i have the files what i would like to have (the language files .lng), but how can I find the fonts, in which file(s)?

Can you help me, please?

yeah i would like to know this as well?
