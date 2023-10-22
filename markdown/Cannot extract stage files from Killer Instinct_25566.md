## Post #1
- Username: Kupo603
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 21, 2021 2:20 am
- Post datetime: 2022-07-01T04:52:10+00:00
- Post Title: Cannot extract stage files from Killer Instinct

I've tried using the KI.bms script but i get this error. i've been making custom recolors for KI for awhile but i can never get the stage pak files to extract.


this is the script

IDSTRING PAK_
get VERSION long
get NULL00 long
get TYPE long
get COUNT00 long
get COUNT01 long
get COUNT02 long
for i = 0 < COUNT02
get NULL01 long
get COUNT03 long
get COUNT04 long
math COUNT03 * 4
getdstring NULL02 COUNT03
next i
for i = 0 < COUNT01
get HASH long
get NSIZE long
getdstring NVAR NSIZE
#print "%NVAR%"
next i
for i = 0 < COUNT00
getdstring NAME 0xF0
get VAR00 short
get VAR01 short
get OFFSET long
get VAR02 long
get SIZE long
get VAR03 short
get VAR04 short
get VAR05 short
if VAR03 == 0
elif VAR03 == 1
elif VAR03 == 2
set VAR03 string "kimesh"
elif VAR03 == 3
set VAR03 string "kimat"
elif VAR03 == 4
set VAR03 string "kitex"
elif VAR03 == 13
set VAR03 string "CinematicShot.xml"
elif VAR03 == 21
set VAR03 string "EventList.xml"
elif VAR03 == 22
set VAR03 string "MeshAttachmentInfo.xml"
elif VAR03 == 28
set VAR03 string "kihkx"
elif VAR03 == 29
set VAR03 string "hkAnim"
elif VAR03 == 53
set VAR03 string "ProceduralAnimationData.xml"
endif
string NAME += .
string NAME += VAR03
print "%NAME%"
log NAME OFFSET SIZE
next i
[Untitled.png](https://xentaxbackup.github.io/file/22439_Untitled.png)
