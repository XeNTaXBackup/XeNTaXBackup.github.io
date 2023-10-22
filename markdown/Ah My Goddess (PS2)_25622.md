## Post #1
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-07-15T12:30:44+00:00
- Post Title: Ah My Goddess (PS2)

This game's models and textures appear to be stored on GRP.bin and there's no script/tools made to extract its content. It seems to have a list of names of its content at the beginning and the data it contains has a 'PKv0' header and they may have some kind of compression. I can find vertices of characters in Model Researcher but they come out flat probably because of that compression. I get better results on the vertices when I open the eeMemory with Model Researcher but I couldn't seem to find the faces. Would it be possible to make some script to extract the model/texture files from the eeMemory and at least get the meshes displayed on Model Researcher? It would probably be harder to get the models/textures from GRP.bin though because of some compression it may possibly have. I have also taken a portion from the eeMemory that I think contains some mesh data and I have made a list of offsets, counts and paddings where I can find some possibly proper vertices.

Here's the portion of eeMemory: [eememory_part](https://drive.google.com/file/d/1D_X7D_KqFjt7SMQgNiapxRtkjJ-nZexW)

```
offset: 0x12a2c4
count: 19
padding: 84

offset: 0x12ac48
count: 15
padding: 84

offset: 0x12b44c
count: 15
padding: 84

offset: 0x12c394
count: 16
padding: 84

offset: 0x12cbf8
count: 28
padding: 84

offset: 0x12d8dc
count: 17
padding: 84

offset: 0x13fb00
count: 8
padding: 84
```




vertices.png (33.56 KiB) Viewed 215 times



The entire [eeMemory](https://drive.google.com/file/d/1G-cAMkRdDC57rF2wYD2Jn5xfC00vIx1N) and [GRP.bin](https://drive.google.com/file/d/1whSiinH1jqaKQbZY8284QRPmcLbVnXMX)

There have been a few mentions of this game here a long time ago but they didn't really got anywhere and nobody had taken a deeper look at it.
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-15T15:25:55+00:00
- Post Title: Ah My Goddess (PS2)

> Reply from Natsuki Okusawa ↑Fri Jul 15, 2022 8:30 pm at Fri Jul 15, 2022 8:30 pm
>
> 
GRP.bin

i made unpacker 'GRP.BIN'
(I'll look at the unpacked files later)
[fmt_GRP_BIN.zip](https://xentaxbackup.github.io/file/22499_fmt_GRP_BIN.zip)
## Post #3
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-07-15T17:05:44+00:00
- Post Title: Ah My Goddess (PS2)

Thank you very much, I'll be looking forward for more progress
## Post #4
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-01-31T08:05:00+00:00
- Post Title: Ah My Goddess (PS2)

Sorry for bumping but, any news on this?
## Post #5
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-28T14:16:58+00:00
- Post Title: Ah My Goddess (PS2)

I managed to extract 3d models from pcsx2 memory dumping.
And wrote a simple maxscript to build 3d models without weight data.
Searching old disks atm,,not sure if i still keep the scripts..
I posted it on mariokart's forum,,which was closed.

what i remember is,,before the header,,there are few values need to be saved as array..
then you have to add those values into your polygon face index read from raw data..
That will be the real vertex index to generate 3d models.

ripped model.
[bell.jpg](https://xentaxbackup.github.io/file/23728_bell.jpg)
## Post #6
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-04-30T09:59:44+00:00
- Post Title: Ah My Goddess (PS2)

do you remember what the forum was called? maybe its archived somewere?
anyway I think it would be better to go for the memory dump or eememory because the files in the grp.bin appears to be compressed (unless someone is willing to figure out the compression)
anyway hopefully you'll find the script
## Post #7
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-30T13:42:43+00:00
- Post Title: Ah My Goddess (PS2)

That site/thread was closed more than 10 years.
Annnd .you're lucky I found it.

```
-- fsource="C:\\Users\\ACER_PREDATOR\\Documents\\My Received Files\\new dump.dat"

fsource = GetOpenFileName \
caption:"[PS2] Oh! My Goddess" \
types: "MemoryDump(*.dat)|*.CEM|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fext=           getFilenameType fsource
fpath=          getFilenamePath fsource
fbatch=         getFiles (fpath+"*"+fext)
fname=  getFilenameFile fsource
fsize=          getFileSize fsource
st = timestamp() --get start time in milliseconds
clearlistener()
openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
--===========================================================================
undo off(
with redraw off (

vertsArray = #()
facesArray = #()
uvsArray = #()
mscale=39.34



/*
Instructions!

Please manually add the offset where the header starts
the script will read 96bytes from that and try to read the header from there
*/

fseek f 0x00000000 #seek_set --Important must be set at the RIGHT location, else will return Error Message!

startPos=0
read=0
meshInfo=false
for scan = 1 to 96 do(
read=readbyte f #unsigned
if read==0x70 do(
read=(readbyte f #unsigned)-(readbyte f #unsigned)-(readbyte f #unsigned)
if read==0x00 do(
fseek f -4 #seek_cur
read=readlong f #unsigned
if read==0x70 do(
meshInfo=true
startPos=ftell f
))))
fseek f startPos #seek_set

meshArray=#()
if meshInfo==true then(
fseek f startPos #seek_set --try to scan for those headers.. using 0x0140 as an ID
do(

ukn=readlong f
ukn=readlong f
ukn=readlong f
ukn=readlong f
faceAddition=readlong f #unsigned
ukn=readlong f
ukn=readlong f
faceCount=readlong f #unsigned
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
fseek f 0x30 #seek_cur --Skips FF's
read=readlong f #unsigned
append meshArray[faceCount,faceAddition]
)
while read==0x70


fseek f -0x20 #seek_cur
newPos=0
for tst = 1 to 0x10 do(
read=readlong f
if read==1 do(
newPos=ftell f+4
))
fseek f newPos #seek_set


vertCount=readlong f #unsigned
ukn=readlong f #unsigned
faceCount=readlong f #unsigned
ukn=readlong f #unsigned

Print ("Reading Verts @ 0x"+((bit.intAsHex(ftell f))as string))
for x = 1 to vertCount do(
vx=readfloat f*mscale
vy=readfloat f*mscale
vz=readfloat f*mscale
ukn1=readfloat f
ukn2=readfloat f
ukn3=readfloat f
ukn4=readfloat f
nx=readfloat f
ny=readfloat f
nz=readfloat f
ukn5=readfloat f
tv=readfloat f
tu=readfloat f*-1
ukn=readlong f #unsigned
append vertsArray[vx,vz,vy]
append uvsArray[tv,tu,0]
)

Print ("Reading Faces @ 0x"+((bit.intAsHex(ftell f))as string))
for tst = 1 to 0x10 do(
read=readlong f
if read==1 then EXIT
)
fseek f -8 #seek_cur
	

for x = 1 to meshArray.count do(
fd=1+meshArray[x][2]
for z = 1 to meshArray[x][1] do (
fa=readlong f #unsigned+fd
fb=readlong f #unsigned+fd
fc=readlong f #unsigned+fd
append facesArray[fc,fb,fa]
)
msh = mesh vertices:vertsArray faces:facesArray   --build mesh
msh.numTVerts = uvsArray.count
buildTVFaces msh
meshop.deleteIsoVerts msh
for j = 1 to uvsArray.count     do setTVert  msh j uvsArray[j]
for j = 1 to facesArray.count   do setTVFace msh j facesArray[j]
facesArray = #()
)






)
else(messageBox "ERROR!!!!!!")
--===========================================================================
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
flushLog()
closeLog()
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
))) else (Print "Aborted.")

```
## Post #8
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-30T13:48:33+00:00
- Post Title: Ah My Goddess (PS2)

Also,,I remember there was Dreamcast version,,I had few samples remaining,,if you want to analysis them too.

[https://www.sendspace.com/file/f1cif4](https://www.sendspace.com/file/f1cif4)
## Post #9
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-04-30T14:23:49+00:00
- Post Title: Ah My Goddess (PS2)

Thank you very much for sharing, I'm really glad you found it
anyway how do I get the memory dump that will work with the script though...
## Post #10
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-30T14:43:39+00:00
- Post Title: Ah My Goddess (PS2)

I remember some hexeditor had ability to do it.
it's done over 10 years ago,,some detail,,hexeditor name i don't remember well..
I will post some i dumpped.
[https://www.sendspace.com/file/75cd0i](https://www.sendspace.com/file/75cd0i)

Here is maxscript more easier to read than previous one.

```
fsource="D:\\Workspace\\megamisama\\new dump.dat"

-- fsource = GetOpenFileName \
-- caption:"[PS2] Oh! My Goddess" \
-- types: "MemoryDump(*.dat)|*.dat|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fext=           getFilenameType fsource
fpath=          getFilenamePath fsource
fbatch=         getFiles (fpath+"*"+fext)
fname=  getFilenameFile fsource
fsize=          getFileSize fsource
st = timestamp() --get start time in milliseconds
clearlistener()
openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
--===========================================================================
undo off(
with redraw off (

IDV_array = #() -------------------------------------index difference value array
TriCount_array = #()  ------------------------------------Triangle(face) count array
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
vtcount = 3217
---------------------------------------------------------------------------------------------------
fseek f 0x26DB4 #seek_set---------------IDV offset

for i = 1 to 22 do
(
 idv = readlong f
 append IDV_array [idv]        ----------load idv to IDV_array
 readlong f
 readlong f
 tric =readshort f
 append TriCount_array [tric]   ----------------------load tric to TricCount_array
 fseek f 86 #seek_cur
 )

 

--------------------------------------------------------------------------------------------------




fseek f 0x27650 #seek_set---------------vertex offset

for i=1 to vtcount do
(   
    vx = readfloat f
    vy = readfloat f
    vz = readfloat f
    append Vert_array [vx,vy,vz]
   
	fseek f 44 #seek_cur
)

fseek f 0x2766C #seek_set  


for i=1 to vtcount do
(   
    nx = readfloat f
    ny = readfloat f
    nz = readfloat f
    append Normal_array [nx,ny,nz]
   
	fseek f 44 #seek_cur
)

fseek f 0x276b4 #seek_set  ---------uv offset


for i=1 to vtcount do
(   
    tu = readfloat f
    tv = readfloat f 
    append UV_array [tu,tv,0]
   
	fseek f 48 #seek_cur
)

------------------------------------------------------------------------------------------------------
fseek f 0x53640 #seek_set --face index start offset

for i =1 to 22 do(  ----------------totally 22 meshes
Triface_count = TriCount_array [i] 
idv0 = IDV_array [i] +1

  for j= 1 to Triface_count do(
 

  fa=readlong f + idv0
  fb=readlong f + idv0
  fc=readlong f + idv0
  append Face_array [fa,fb,fc]
  )

)


msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh

for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

fclose f


```
## Post #11
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-04-30T14:55:08+00:00
- Post Title: Ah My Goddess (PS2)

I get error when I try to run your new script



error.png (55.81 KiB) Viewed 73 times
## Post #12
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-30T15:12:15+00:00
- Post Title: Ah My Goddess (PS2)

to rip the hex data for pcsx2,,you can use cheatengine.[https://cheatengine.org/](https://cheatengine.org/)
my OS got reinstalled lots of times..3dsmax is not installed atm.you have to wait a bit when i have time to check the scripts line by line later after i reinstall it.but file structure should be correct since i used it construct the models.
## Post #13
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-30T15:23:30+00:00
- Post Title: Ah My Goddess (PS2)

try to use maxsript cutsume2 import.ms
in the sample file i sent,,excute it and open cutsume2 import.dat
lots of things i don't remember it well now,,b/c it's ripped hex data,so it's file structure is not compelete..have to set a correct location to start reading the file,,,sorry,,it was done more than 10 year ago,really don't remember it well.
## Post #14
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-04-30T15:34:32+00:00
- Post Title: Ah My Goddess (PS2)

I got another error



error.png (61.98 KiB) Viewed 63 times
## Post #15
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-04-30T15:38:17+00:00
- Post Title: Ah My Goddess (PS2)

Its fine if you don't remember everything since it was a long time ago, I understand that.
I highly appreciate your help and I'm really grateful for that.
## Post #16
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-30T15:48:52+00:00
- Post Title: Re: Ah My Goddess (PS2)

there is a file called cutsume2_log.txt.
if i remember it correct,it recored where you should read vertices count,face index data,try to use those values to edit my script and execute my script again.


```
"Reading Faces @ 0x33068"
"Last Read @ 0x3c3c4"

```


i totally forgot what 'last read' meaning now .lol
## Post #17
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-04-30T16:05:32+00:00
- Post Title: Re: Ah My Goddess (PS2)

hmm... well I'm not sure where I'm supposed to place the vertex and face offsets in the script
## Post #18
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-30T16:06:32+00:00
- Post Title: Re: Ah My Goddess (PS2)

Another model sample ripped from ram dump.
with logs i wrote you need to change some values in the script.
[https://www.sendspace.com/file/yvuv3d](https://www.sendspace.com/file/yvuv3d)
## Post #19
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-04-30T16:07:37+00:00
- Post Title: Re: Ah My Goddess (PS2)

I'm trying very hard to remember it too
## Post #20
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-05-01T11:37:57+00:00
- Post Title: Re: Ah My Goddess (PS2)

alright,,finally reinstalled every thing.it seems my scripts still working.

```
-- fsource="C:\\Users\\ACER_PREDATOR\\Documents\\My Received Files\\new dump.dat"

fsource = GetOpenFileName \
caption:"[PS2] Oh! My Goddess" \
types: "MemoryDump(*.dat)|*.CEM|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fext=           getFilenameType fsource
fpath=          getFilenamePath fsource
fbatch=         getFiles (fpath+"*"+fext)
fname=  getFilenameFile fsource
fsize=          getFileSize fsource
st = timestamp() --get start time in milliseconds
clearlistener()
openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
--===========================================================================
undo off(
with redraw off (

vertsArray = #()
facesArray = #()
uvsArray = #()
mscale=39.34



/*
Instructions!

Please manually add the offset where the header starts
the script will read 96bytes from that and try to read the header from there
*/

fseek f 0x00000000 #seek_set --Important must be set at the RIGHT location, else will return Error Message!

startPos=0
read=0
meshInfo=false
for scan = 1 to 96 do(
read=readbyte f #unsigned
if read==0x70 do(
read=(readbyte f #unsigned)-(readbyte f #unsigned)-(readbyte f #unsigned)
if read==0x00 do(
fseek f -4 #seek_cur
read=readlong f #unsigned
if read==0x70 do(
meshInfo=true
startPos=ftell f
))))
fseek f startPos #seek_set

meshArray=#()
if meshInfo==true then(
fseek f startPos #seek_set --try to scan for those headers.. using 0x0140 as an ID
do(

ukn=readlong f
ukn=readlong f
ukn=readlong f
ukn=readlong f
faceAddition=readlong f #unsigned
ukn=readlong f
ukn=readlong f
faceCount=readlong f #unsigned
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
ukn=readshort f
fseek f 0x30 #seek_cur --Skips FF's
read=readlong f #unsigned
append meshArray[faceCount,faceAddition]
)
while read==0x70


fseek f -0x20 #seek_cur
newPos=0
for tst = 1 to 0x10 do(
read=readlong f
if read==1 do(
newPos=ftell f+4
))
fseek f newPos #seek_set


vertCount=readlong f #unsigned
ukn=readlong f #unsigned
faceCount=readlong f #unsigned
ukn=readlong f #unsigned

Print ("Reading Verts @ 0x"+((bit.intAsHex(ftell f))as string))
for x = 1 to vertCount do(
vx=readfloat f*mscale
vy=readfloat f*mscale
vz=readfloat f*mscale
ukn1=readfloat f
ukn2=readfloat f
ukn3=readfloat f
ukn4=readfloat f
nx=readfloat f
ny=readfloat f
nz=readfloat f
ukn5=readfloat f
tv=readfloat f
tu=readfloat f*-1
ukn=readlong f #unsigned
append vertsArray[vx,vz,vy]
append uvsArray[tv,tu,0]
)

Print ("Reading Faces @ 0x"+((bit.intAsHex(ftell f))as string))
for tst = 1 to 0x10 do(
read=readlong f
if read==1 then EXIT
)
fseek f -8 #seek_cur
	

for x = 1 to meshArray.count do(
fd=1+meshArray[x][2]
for z = 1 to meshArray[x][1] do (
fa=readlong f #unsigned+fd
fb=readlong f #unsigned+fd
fc=readlong f #unsigned+fd
append facesArray[fc,fb,fa]
)
msh = mesh vertices:vertsArray faces:facesArray   --build mesh
msh.numTVerts = uvsArray.count
buildTVFaces msh
meshop.deleteIsoVerts msh
for j = 1 to uvsArray.count     do setTVert  msh j uvsArray[j]
for j = 1 to facesArray.count   do setTVFace msh j facesArray[j]
facesArray = #()
)






)
else(messageBox "ERROR!!!!!!")
--===========================================================================
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
flushLog()
closeLog()
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
))) else (Print "Aborted.")
```

[max script out.jpg](https://xentaxbackup.github.io/file/23747_max script out.jpg)
## Post #21
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-05-01T11:43:50+00:00
- Post Title: Re: Ah My Goddess (PS2)

I checked few differnt characters dump,,only few characters working.This script is still not compelete.but you should be able to see it's basic vertex ,face index data pattern from the script.
## Post #22
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-05-01T12:23:45+00:00
- Post Title: Re: Ah My Goddess (PS2)

> Reply from Natsuki Okusawa ↑Sun Apr 30, 2023 11:34 pm at Sun Apr 30, 2023 11:34 pm
>
> 
I got another error
error.png

change the line 35 in my script last posted.

```

```

0x144 ..this value is for cutsume2.dat
original should be 0x00000000  ,b/c it's ripped from memory,so i have no idea about it's header,,it's judged by lots of dumped data.

then you should be able to get the model. you have to use hex editor to look those model's pattern,should not be hard to judge the correct offset value.
[max script out 2.jpg](https://xentaxbackup.github.io/file/23748_max script out 2.jpg)
## Post #23
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-05-01T14:44:22+00:00
- Post Title: Re: Ah My Goddess (PS2)

I finally got it, once again thank you very much I really appreciate your help



cutsume2.png (86.34 KiB) Viewed 86 times



well hopefully one day there will be an easier way to get models from this game
## Post #24
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-05-01T20:10:29+00:00
- Post Title: Re: Ah My Goddess (PS2)

np,glad it can help,,
also,,if you have tool to unpack the raw packge archieve file.try feed dumped hex data with encrypted data into chatgpt.
if you're lucky,maybe it will find the function to decrypt raw data for us.
## Post #25
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2023-05-02T09:02:25+00:00
- Post Title: Re: Ah My Goddess (PS2)

Durik made a GRP.BIN extractor that can be found in the first page.

here's one of the extracted files from GRP.BIN:


 OB0026O.rar
(116.06 KiB) Downloaded 16 times
