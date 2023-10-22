## Post #1
- Username: SergioF
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 16, 2012 2:59 am
- Post datetime: 2014-06-11T17:40:33+00:00
- Post Title: How to Extract\Insert dataS.gar of Farming Simulator PC?

Sorry my english
I tried to extract using a bms script:

```
# Farming Simulator 2009/2011/2013
# Demolition Company
# Ski Region Simulator
# script for QuickBMS http://quickbms.aluigi.org

comtype copy

idstring "Copyright (C) GIANTS"
get DUMMY string
savepos OFFSET
math OFFSET x= 0x10
goto OFFSET
idstring "GAR "
get DUMMY short
get DUMMY short
get FILES long

set KEY binary "2W957B]2X782622c" # Farming Simulator 2013
putarray 0 0 KEY
set KEY binary "En48g5fFqmMuM9Q9" # Ski Region Simulator 2012
putarray 0 1 KEY
set KEY binary "vMngHM7HWBxPX4lU" # Farming Simulator 2009 / 2011
putarray 0 2 KEY
putarray 0 3 ""

for i = 0
getarray KEY 0 i
if KEY == ""
print "Error: unknown key, contact me"
cleanexit
endif
encryption aes_128_cbc KEY "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0"
log MEMORY_FILE 0x200 16
get DUMMY long MEMORY_FILE
get ZERO long MEMORY_FILE
if ZERO == 0
break
endif
next i
print "use key %KEY%"

encryption aes_128_cbc KEY "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0"
math TMP = FILES
math TMP *= 0x200
log MEMORY_FILE 0x200 TMP

for i = 0 < FILES
get DUMMY longlong MEMORY_FILE
get XSIZE longlong MEMORY_FILE
get SIZE longlong MEMORY_FILE
get OFFSET longlong MEMORY_FILE
get DUMMY longlong MEMORY_FILE
getdstring NAME 0x1d8 MEMORY_FILE

encryption aes_128_cbc KEY "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0"
clog NAME OFFSET XSIZE SIZE
next i
```

Extract all files correctly, but when you open the game shows the error: "Error:. Data files corrupt Please reinstall application" 
Compared with the orignal and saw that only the last bytes were different.

Now I tested the latest version (0.3.1.a) [http://aluigi.altervista.org/papers/bms ... ftware.bms](http://aluigi.altervista.org/papers/bms/giants_software.bms), the error continues, but now only the beginning and end of the files are equal. 
At the end of the extraction and insertion I get this message from the Command Prompt.

```
  coverage file 0    90%   4472963    4928000
  coverage file -1  100%   225288     225280
  coverage file -3    0%   0          315904
```

I wonder if:
1 - There is an error in the script (maybe not because the bms script extracts normal, even the repack being different from the original)
2 - The game may be using some protection against modification

If 1 could make me a script for dataS.gar? I'd like to translate it to Portuguese-Brazil.
Or explain to me how the file structure works, I even tried to draw something using Header that is encoded, but I can only faulty.
Example:

```
<achievements>
    <achievement id="1" idName="Money1Million" score="0" targetScore="1000000" showScore="false" imageFilename="dataS2/menu/achievements/achievement_money1Million.png" />
    <achievement id="2" idName="Money5Million" score="0" targetScore="5000000" showScore="false" imageFilename="dataS2/menu/achievements/achievement_money5Million.png" />
    <achievement id="3" idName="Money10Million" score="0" targetScore="10000000" showScore="false" imageFilename="dataS2/menu/achievements/achievement_money10Million.png" />
    <achievement id="4" idName="OutOfDebt" score="0" targetScore="0" showScore="false" imageFilename="dataS2/menu/achievements/achievement_outOfDebt.png" />
    <achievement id="5" idName="TraveledDistance100" score="0" targetScore="100" showScore="false" imageFilename="dataS2/menu/achievements/achievement_traveledDistance100.png" />
    <achievement id="6" idName="TraveledDistance1000" score="0" targetScore="1000" showScore="false" imageFilename="dataS2/menu/achievements/achievement_traveledDistance1000.png" />
    <achievement id="7" idName="PlayTime10" score="0" targetScore="10" showScore="false" imageFilename="dataS2/menu/achievements/achievement_playTime10.png" />
    <achievement id="8" idName="ThreshedHectares10" score="0" targetScore="10" showScore="false" imageFilename="dataS2/menu/achievements/achievement_threshedHectares10.png" />
    <achievement id="9" idName="ThreshedHectares100" score="0" targetScore="100" showScore="false" imageFilename="dataS2/menu/achievements/achievement_threshedHectares100.png" />
    <achievement id="10" idName="SeededHectares10" score="0" targetScore="10" showScore="false" imageFilename="dataS2/menu/achievements/achievement_seededHectares10.png" />
    <achievement id="11" idName="SeededHectares100" score="0" targetScore="100" showScore="false" imageFilename="dataS2/menu/achievements/achievement_seededHectares100.png" />
    <achievement id="12" idName="FoundHorseshoes25" score="0" targetScore="25" showScore="false" imageFilename="dataS2/menu/achievements/achievement_foundHorseshoes25.png" />
    <achievement id="13" idName="FoundHorseshoes50" score="0" targetScore="50" showScore="false" imageFilename="dataS2/menu/achievements/achievement_foundHorseshoes50.png" />
    <achievement id="14" idName="FoundHorseshoes100" score="0" targetScore="100" showScore="false" imageFilename="dataS2/menu/achievements/achievement_foundHorseshoes100.png" />
    <achievement id="15" idName="MissionsDone50" score="0" targetScore="50" showScore="false" imageFilename="dataS2/menu/achievements/achievement_missionsDone50.png" />
    <achievement id="16" idName="Bankruptcy" score="0" targetScore="1" showScore="false" imageFilename="dataS2/menu/achievements/achievement_bankruptcy.png" />
</achievements>
```

Thanks in advance
## Post #2
- Username: lollogamer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 27, 2017 1:09 am
- Post datetime: 2017-06-26T17:14:06+00:00
- Post Title: How to Extract\Insert dataS.gar of Farming Simulator PC?

For make this work u need to make a new FS17.exe

Sostitute the original files from fs17.exe (python)

Next u need to put the new file scripted in to the correct line (thinking 1094B1)

The same things has been doed for fs15 for xbox

Nice man.

If u do this we are able to change the fs17 video/logo/and image.

I hope u can do this

Say info

Lorenzo
