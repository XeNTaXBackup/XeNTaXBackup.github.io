## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-05-12T07:36:18+00:00
- Post Title: Naruto ultimate storm 3 full burst xfbin <=> DDS BMS script

I made xfbin to DDS BMS script for Naruto series. Enjoy it.  

```

endian big

goto 0x1C
get TYPE long

if TYPE < 9
math jump = 0xAC
else
math jump = 0x10C
endif

FindLoc GIDX_off string "GIDX" 0 ""
#goto 0x2A4
#savepos GIDX_off
xmath file_num_off "GIDX_off - jump"

goto file_num_off
get files long

goto 0x20
get names_jump1 long
goto 0x28
get names_jump2 long
goto 0x30
get names_jump3 long
xmath noff "0x44 + names_jump1 + names_jump2 + 1"

for i = 0 < files
goto noff
get name string

if name = "Page0"
xmath noff "noff + 0xC"
goto noff
get name string
string name += ".dds"
savepos noff

else
string name += ".dds"
savepos noff
endif

goto GIDX_off
xmath base_off "GIDX_off - 0x38"

goto base_off
get SIZE long
get UNK1 long
get UNK2 long
get WIDTH short
get HEIGHT short
savepos tmp
xmath OFFSET "tmp + 0x38"

callfunction addDDSheader

get packname filename
string packname += _unpacked/
string packname += name
log packname 0 SIZE MEMORY_FILE
append
xmath GIDX_off "OFFSET + SIZE + 0x88"

if GIDX_off > EOF
cleanexit

else

goto GIDX_off
getdstring TEST 0x4
    if TEST == "GIDX"
    else
    cleanexit
    endif
endif

next i

startfunction addDDSheader
endian little
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0xC HEIGHT long
endian big
append

log MEMORY_FILE OFFSET SIZE
endfunction
```

[test.rar](https://xentaxbackup.github.io/file/9190_test.rar)
## Post #2
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-05-12T09:56:42+00:00
- Post Title: Naruto ultimate storm 3 full burst xfbin <=> DDS BMS script

1. Generate DDS file.


2. After generate DDS image from xfin file, edit dds file (using Photoshop or etc..) and save it.
Remember save it as no mimmap.


3. Backup dds image.


4. Create Remove folder and Remove DDS header using bms script

```
savepos OFFSET

goto EOF
savepos End

xmath SIZE "End - OFFSET"

get packname filename
log packname OFFSET SIZE
```


5. Copy DDS file from remove folder and past it to current folder.
And reimport.bat => Select below bms script => adv_dcs_text00.xfbin => Save


```
endian big

goto 0x1C
get TYPE long

if TYPE < 9
math jump = 0xAC
else
math jump = 0x10C
endif

FindLoc GIDX_off string "GIDX" 0 ""
#goto 0x2A4
#savepos GIDX_off
xmath file_num_off "GIDX_off - jump"

goto file_num_off
get files long

goto 0x20
get names_jump1 long
goto 0x28
get names_jump2 long
goto 0x30
get names_jump3 long
xmath noff "0x44 + names_jump1 + names_jump2 + 1"

for i = 0 < files
goto noff
get name string

if name = "Page0"
xmath noff "noff + 0xC"
goto noff
get name string
string name += ".dds"
savepos noff

else
string name += ".dds"
savepos noff
endif

goto GIDX_off
xmath base_off "GIDX_off - 0x38"

goto base_off
get SIZE long
get UNK1 long
get UNK2 long
get WIDTH short
get HEIGHT short
savepos tmp
xmath OFFSET "tmp + 0x38"

get packname filename
string packname += _unpacked/
string packname += name
log packname OFFSET SIZE
xmath GIDX_off "OFFSET + SIZE + 0x88"

if GIDX_off > EOF
cleanexit

else

goto GIDX_off
getdstring TEST 0x4
    if TEST == "GIDX"
    else
    cleanexit
    endif
endif

next i
```


6. Check results.

Original


Result
## Post #3
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-05-12T10:51:56+00:00
- Post Title: Naruto ultimate storm 3 full burst xfbin <=> DDS BMS script

That great! Thanks!
