## Post #1
- Username: MiLØ
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-24T18:39:03+00:00
- Post Title: Siren New Translation (PS3)

Here is a bms script to extract these archives.

```
#quickbms script
#Siren PS3
#from chrrox

endian big

open FDDE DAT 0
open FDDE HED 1


get id long 1
get Unk01 long 1
get Unk02 long 1
get Unk03 long 1
get NameBase long 1
get TableBase long 1
get Unk06 long 1
get files long 1
for i = 0 < files
    goto TableBase 1
    get Nameoff long 1
    get offset long 1
    get zsize long 1
    get size long 1
    savepos TableBase 1
    math Nameoff + NameBase
    goto Nameoff 1
    get name string 1
        log name offset zsize
next i


```
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-11-24T21:32:20+00:00
- Post Title: Siren New Translation (PS3)

yay thanks man ^,^
## Post #3
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2011-01-17T13:32:22+00:00
- Post Title: Siren New Translation (PS3)

and how to pack it back?
i want to translate this game into Russian
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-20T10:39:53+00:00
- Post Title: Siren New Translation (PS3)

tried my hand in the model extraction, but the UVs don't work  sigh!
the UVs seem to require some divisior to scale them properly. I used 10000000000000 but they're stretched to hell. lol go figure  maybe I'm reading them wrong?

miy_h_298.rsx


> Miy_h_001_Eye_00.dds 		256x128		DXT1
>
> Miy_h_001_Eye_00_r.dds 		128x128		DXT1
>
> Miy_h_001_Eye_00_sp.dds  	128x64		DXT1
>
> Miy_h_011_Hair_00.dds  		512x512		DXT5
>
> Miy_h_011_Hair_00_sp.dds 	256x256		DXT1
>
> Miy_h_011_Hairfront_00.dds 	512x128		DXT5
>
> Miy_h_011_Hairplus_00.dds 	256x256		DXT5
>
> Miy_h_011_matsuge_00.dds 	256x256		DXT5
>
> Miy_h_046_All_00.dds  		1024x1024	DXT1
>
> Miy_h_046_All_00_n.dds  	512x512		DXT5
>
> Miy_h_280_blood.dds  		128x128		DXT5
>
> Miy_h_280_blood_n.dds  		128x128		DXT5


maxscript:

```
caption:"[PS3] BloodCurse" \
types: "ReSourceX(*.rsx)|*.rsx|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fext=         getFilenameType fsource
fpath=         getFilenamePath fsource
fbatch=        getFiles (fpath+"*"+fext)
fname=     getFilenameFile fsource
fsize=         getFileSize fsource
st = timestamp() --get start time in milliseconds
clearlistener()
openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
print (localTime+"\n"+fname+fext+"\n")
--===========================================================================
undo off(

fn readBEshort fstream = (
short = readshort fstream #unsigned
short = bit.swapBytes short 2 1
return short
) 

fn readBElong fstream = (
long = readlong fstream #unsigned
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)
fn ReadBEfloat fstream = (
    fpt=readfloat fstream
    itger = bit.floatAsInt fpt
    hih = bit.intashex itger
    while hih.count < 8 do hih = "0" + hih
    shn = (substring hih 7 2) + \
    (substring hih 5 2) + \
    (substring hih 3 2) + \
    (substring hih 1 2)
    bit.intAsFloat (bit.hexasint shn)
    )
fn ReadFixedString bstream fixedLen = (
   local str = ""
   for i = 1 to fixedLen do
   (
      str += bit.intAsChar (ReadByte bstream #unsigned)
   )
   str
)


--===========================================================================
with redraw off (
offsetArray=#()
offsetArray2=#()

while (ftell f) != fsize do (
if keyboard.escPressed then exit
byte1 = readshort f
if (byte1==512) do(
byte2 = readshort f
if (byte2==512) then(
byte3 = readshort f
if (byte3==0) then(
byte4 = readshort f
if (byte4==0) then(
fseek f 28 #seek_cur
byte5 = readlong f
if (byte5==-1) then(
fseek f 4 #seek_cur
byte6 = readlong f
if (byte6==-1) then(
append offsetArray ((ftell f)-48)
)else(fseek f -40 #seek_cur)
)else(fseek f -32 #seek_cur)
)else(fseek f -6 #seek_cur)
)else(fseek f -4 #seek_cur)
)else(fseek f -2 #seek_cur)
)
if (byte1==256) do(
byte2 = readshort f
if (byte2==256) then(
byte3 = readshort f
if (byte3==0) then(
byte4 = readshort f
if (byte4==0) then(
fseek f 28 #seek_cur
byte5 = readlong f
if (byte5==-1) then(
-- append offsetArray ((ftell f)-40)
)else(fseek f -32 #seek_cur)
)else(fseek f -6 #seek_cur)
)else(fseek f -4 #seek_cur)
)else(fseek f -2 #seek_cur)
)
)





for m = 1 to offsetArray.count do(
vertsArray=#()
facesArray=#()
uvsArray=#()


fseek f offsetArray[m] #seek_set
Print ("Sub Mesh "+(m as string)+": @ 0x"+((bit.intAsHex(ftell f))as string))
subMeshID=readBEshort f -- ?? 02 02?? 2 NEW MESH HEADER! >BALLS
subMeshCount=readBEshort f-1 -- ??? UV Count
print subMeshID
print "f"
    print subMeshCount

ukn=readBElong f -- pad??
ukn=readBElong f -- offsets to another offset that offsets to the vert start
faceOffset=readBElong f -- offsets to face header ? can also get count here ?maybe is apart of vert header
faceOffset2=readBElong f -- real face header?
ukn=readBElong f -- offsets to table aftet verts
ukn=readBElong f -- offsets to table aftet verts
ukn=readBElong f -- pad??
vertOffset=readBElong f -- Offsets to Vertex Section
ukn=readBElong f -- FF??
tvertOffset=0
for x = 1 to subMeshCount do(
tvertOffset=readBElong f -- Offset to UV section
ukn=readBElong f -- FF??
)

fseek f faceOffset #seek_set
tvertcount=readBEshort f

if subMeshCount==1 then(
fseek f tvertOffset #seek_set
for uv = 1 to tvertcount do(
tu=((readBElong f/10000000.0)-100)*0.15
tv=((readBElong f/10000000.0)-100)*0.15
append uvsArray[tu,tv,0]
))else(
tvertOffset=faceOffset
for x = 1 to tvertcount do(
append uvsArray[0,0,0]
)
)

vertcount=((tvertOffset-vertOffset))/tvertcount
if vertcount!=24 AND vertcount!=40 do(
--Print ("..............................................................................................................................................ERROR!! @ 0x"+((bit.intAsHex(vertOffset))as string))
vx=0
vy=0
vz=0
tvertcount+=1
vertcount=((tvertOffset-vertOffset)/tvertcount)
tu=readBElong f
tv=readBElong f
append uvsArray[tu,tv,0]
)
if vertcount!=24 AND vertcount!=40 do(
Print ("..............................................................................................................................................ERROR!! @ 0x"+((bit.intAsHex(vertOffset))as string))
)

print "test"
print vertcount
print tvertcount

fseek f vertOffset #seek_set
Print ("Vert Data @ 0x"+((bit.intAsHex(ftell f))as string))
for x = 1 to tvertcount do(
if vertcount==24 do(
vx=readBEfloat f*39.34
vy=readBEfloat f*39.34
vz=readBEfloat f*-39.34
nx=readBEfloat f
ny=readBEfloat f
nz=readBEfloat f

)    
if vertcount==40 do(
vx=readBEfloat f*39.34
vy=readBEfloat f*39.34
vz=readBEfloat f*-39.34
nx=readBEfloat f
ny=readBEfloat f
nz=readBEfloat f
tu=readBElong f
tv=readBElong f
uknZ3=readBEfloat f
uknX4=readBEfloat f
)
if vertcount==48 do(
vx=readBEfloat f*39.34
vy=readBEfloat f*39.34
vz=readBEfloat f*-39.34
nx=readBEfloat f
ny=readBEfloat f
nz=readBEfloat f
tu=readBElong f
tv=readBElong f
uknZ3=readBEfloat f
uknX4=readBEfloat f
uknZ3=readBEfloat f
uknX4=readBEfloat f
)

append vertsArray[vx,vz,vy]
-- append uvsArray[tu,tv,0]

)
-- Print ("END Vert Data @ 0x"+((bit.intAsHex(ftell f))as string))
    
    
fseek f faceOffset2 #seek_set
Print ("Faces @ 0x"+((bit.intAsHex(ftell f))as string))
faceCountArray=#()
do(
if keyboard.escPressed then exit
faceCount=readBEshort f
pad=readBEshort f --?
faceOffset=readBElong f
ukn=readBElong f;print ukn
if ukn==-1 do(
append faceCountArray [faceCount,faceOffset]
)
)while ukn==-1
    
print "fuk"
print faceCountArray.count

faceCount=faceCountArray.count
faceCount=1 -- new faces cause bad faces? 
for x = 1 to faceCount do(
fseek f faceCountArray[x][2] #seek_set    
for x = 1 to faceCountArray[x][1] do(
fa=readBEshort f+1
fb=readBEshort f+1
fc=readBEshort f+1
append facesArray[fa,fb,fc]
)    
)



    

    


    
    
    

msh = mesh vertices:vertsArray faces:facesArray   --build mesh
msh.numTVerts = uvsArray.count
buildTVFaces msh

for j = 1 to uvsArray.count do setTVert msh j uvsArray[j]
for j = 1 to facesArray.count do setTVFace msh j facesArray[j]
-- for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]










) -- ends sub mesh read
    
    








Print ("Done ! @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
flushLog()
closeLog()
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
))) else (Print "Aborted.")
```
## Post #5
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2011-03-06T14:14:57+00:00
- Post Title: Siren New Translation (PS3)

> Reply from chrrox
>
> Here is a bms script to extract these archives.
Code: Select all
#quickbms script
#Siren PS3
#from chrrox

endian big

open FDDE DAT 0
open FDDE HED 1


get id long 1
get Unk01 long 1
get Unk02 long 1
get Unk03 long 1
get NameBase long 1
get TableBase long 1
get Unk06 long 1
get files long 1
for i = 0 < files
    goto TableBase 1
    get Nameoff long 1
    get offset long 1
    get zsize long 1
    get size long 1
    savepos TableBase 1
    math Nameoff + NameBase
    goto Nameoff 1
    get name string 1
        log name offset zsize
next i

How can i use it

I try to common.dat, common.hed file

but quickbms got error - 1403: myfopen()

ps : i have  Siren_New_Translation_JPN version
## Post #6
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2011-03-10T00:42:47+00:00
- Post Title: Siren New Translation (PS3)

add my screenshot
help me
[www1.jpg](https://xentaxbackup.github.io/file/4034_www1.jpg)
## Post #7
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2011-03-10T00:47:14+00:00
- Post Title: Siren New Translation (PS3)

pic2
[www2.jpg](https://xentaxbackup.github.io/file/4035_www2.jpg)
## Post #8
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2011-03-14T15:19:59+00:00
- Post Title: Siren New Translation (PS3)

any1 tried to translate this game? where subtitles are located? i mean text. haven't found them in graphic format.
and how to pack archives back?
## Post #9
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2011-03-15T05:29:42+00:00
- Post Title: Siren New Translation (PS3)

Ok, Now I solved  this problem. lol
## Post #10
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2011-03-24T02:21:09+00:00
- Post Title: Siren New Translation (PS3)

[http://www.filesonic.com/file/333020084/sug_s_141.zip](http://www.filesonic.com/file/333020084/sug_s_141.zip)
this is a zipped rsx file  i cant separate dds
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-09T20:02:48+00:00
- Post Title: Siren New Translation (PS3)

here is a texture converter for rsx files.

```
goto 0x10
get textable long
goto textable
get files long
get start long
for i = 1 to files
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
endian big
goto start
get offset long
get mips short
print "%mips%"
get type byte
print "%type%"
#86 = dxt1
#87 = dxt3
#88 = dxt5
get unk byte
getdstring null 0x10
get height short
get width short
getdstring null 0x10
savepos start
get size long
if i == files
get size asize
endif
math size - offset
endian little
putVarChr MEMORY_FILE 0x1C mips short
putVarChr MEMORY_FILE 0xC width short
putVarChr MEMORY_FILE 0x10 height short
if type == 134
putVarChr MEMORY_FILE 0x57 0x31 byte
putVarChr MEMORY_FILE 0x16 0x08 byte
endif
if type == 135
putVarChr MEMORY_FILE 0x57 0x33 byte
endif
if type == 136
putVarChr MEMORY_FILE 0x57 0x35 byte
putVarChr MEMORY_FILE 0x16 0x10 byte
endif
if type == 133
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x00 byte
putVarChr MEMORY_FILE 0x55 0x00 byte
putVarChr MEMORY_FILE 0x56 0x00 byte
putVarChr MEMORY_FILE 0x57 0x00 byte
putVarChr MEMORY_FILE 0x58 0x20 long
putVarChr MEMORY_FILE 0x5E 0xFF Short
putVarChr MEMORY_FILE 0x61 0xFF Short
putVarChr MEMORY_FILE 0x64 0xFF Short
putVarChr MEMORY_FILE 0x6B 0xFF Short
endif
get name basename
string name + _
string name + i
string name + .dds
print "%offset%"
append
log MEMORY_FILE offset size
append
math size + 0x80
log name 0 SIZE MEMORY_FILE
next i

```
## Post #12
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2011-04-10T15:51:37+00:00
- Post Title: Siren New Translation (PS3)

Oh, holy shit 

I don't know how to thanks chrrox!!
## Post #13
- Username: AndylgRu
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 29, 2009 9:15 pm
- Post datetime: 2011-04-22T07:00:40+00:00
- Post Title: Siren New Translation (PS3)

Anyone found where the subtitles (dss or where?)?
## Post #14
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2011-04-27T07:12:01+00:00
- Post Title: Siren New Translation (PS3)

> Reply from AndylgRu
>
> Anyone found where the subtitles (dss or where?)?

no
## Post #15
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-27T11:41:06+00:00
- Post Title: Siren New Translation (PS3)

it extracts text files, for a translation??

if Yes, I will translate for my language.
## Post #16
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2011-08-05T07:53:18+00:00
- Post Title: Re: Siren New Translation (PS3)

chrrox
mariokart64n
You are the best! Awesome scripts!
I have found some kind of debug file with debug options, like Wireframe mode and other stuff (changed some loading screen):
[http://youtu.be/vVpa48ErCeU](http://youtu.be/vVpa48ErCeU) - video from ps3
[](http://radikal.ru/F/i055.radikal.ru/1108/83/e13b0b049110.jpg.html)[](http://radikal.ru/F/s013.radikal.ru/i325/1108/86/04bddb3e79ec.jpg.html)[](http://radikal.ru/F/s46.radikal.ru/i111/1108/73/34a500a697ad.jpg.html)[](http://radikal.ru/F/i054.radikal.ru/1108/df/cfdade15c127.jpg.html)[](http://radikal.ru/F/s009.radikal.ru/i309/1108/2c/dfe5b01ac5ba.jpg.html)
---
UPD: also: 
[http://psx-scene.com/forums/f180/%5Brel ... od-111171/](http://psx-scene.com/forums/f180/%5Brel%5D-siren-blood-curse-new-translation-true-hd-crystal-clear-picture-mod-111171/)
## Post #17
- Username: ViToTiV
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 11, 2009 12:38 am
- Post datetime: 2015-02-16T09:38:35+00:00
- Post Title: Re: Siren New Translation (PS3)

> Reply from AndylgRu
>
> Anyone found where the subtitles (dss or where?)?
Found, but hard to understand the algorithm of chars coding.
Text for menu/system msg in dds files, subtitle text in es0x.dat files (can unpack by bms script in first post)
For Example:

contents of unpacked file es01.dat/es01.hed:
......
script\msg\s011.dds ([https://yadi.sk/d/MWbShw9dehcEC](https://yadi.sk/d/MWbShw9dehcEC)) - used font chars (only required, not the entire alphabet)
script\msg\s011.dat ([https://yadi.sk/d/J8an0QA3ehcQg](https://yadi.sk/d/J8an0QA3ehcQg)) - text in coordinates or anything else (can't understand)
......

structure of s011.dat:

```
4-byte - Unk
4-byte - text strings count

for each string:
4-byte - string data offset+0x10 (most likely in coords)
4-byte - string label offset+0x10
```

somebody can understand type of coordinates? (or not coordinates, charcodes?   )
