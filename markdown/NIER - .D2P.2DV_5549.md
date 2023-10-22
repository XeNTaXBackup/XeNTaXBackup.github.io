## Post #1
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2010-12-14T19:27:07+00:00
- Post Title: NIER - .D2P/.2DV

i want to edit this type of files, example:
GAME_EVENT.2DP
GAME_EVENT.2DV

[Download](http://www.megaupload.com/?d=KYNEZ6YC)

I want to translate them.

Thanks.
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-28T18:03:28+00:00
- Post Title: NIER - .D2P/.2DV

why would you want to translate them? I extracted that file, and it already contains different languages besides english

it be a bit difficult, you would need to convert these to TGA with the xbox SDK. Edit them, then reconvert them back using the SDK. then hex them back into the file...

had to modify my old max script to read the different extension, get info on using it in chrrox nier topic [requires sdk]

```
/*
　　　　　　　　　　　　　　 　 ／　　　　　｀y　´　　　 　 　 　 　 　 　 　 　 　 |
　　　　　 　 　 　 　 　 　 ／　　　 　 　 , '　　　　　　　　　　 　 　 　 　 　 　 |
　　　　　　　　　 　 　 ／　　＿＿＿__/ _　　-―――――＝＝== ､＿_　　:!
　　　　 ＿＿＿__　,_.′_'"￣　 　 　 / _　　　　　　　　 　 ヾ＞'￣￣￣`ヾ、 |
　　　 ！r､――.､〉∠´　　_　　 ￣｀,'"　　　　　　　　　　／　　　　　 ／7ヘに)､
　　　　 ＼＼ イ/1｢二￣ _　　　＿__ 　 　 　 　 　 　 ／　　　　　　　| ./ .//./｢｀＼
　　　　　_｣＞`7　{｢ ﾌ￣,. -　　 ;´:i￣:: : .: . . .　　 ／　　　　 　 　 　 |∧// .| |＿〉_〉
.　 　 ／ 1「ﾌ/　　∨ ／　　　　:::::i::::::::::::::::::: : :.／　　　　　　　　　 　 >ァ'　 ヽヽ￣
　 ／ ′／ｲ′　　∨=__　　 　 ::::i!::::::::::::::: :: ,."　　　　　　　　　　 ／／ 　 　 |＼＼
. / /　 / /.′　　　 ヽ⌒　.: :. .. ::::i!:::::::::::::::〃　　　　　　　　　　／ /　　 　 　 !　 〉 〉
〈._」 　 ! :! !　　　　　　＼:: .: .:: :: :::ヽ::::::::::〃　　　　　　　　　　/　./　　　　 　 |／／
　　 　 |_｣ ! 　 　 　 　 　 ヽ:. :: ::.,:::::::＼::ｲ′　　　　　　　　　　`ｰ′　　 　 　 i／
.　　　　　 i　　　 　 　 　 　 ＼'"::::::ヽ:＼{　　　　　　　　　　　　　　　　　　　　|
　　　　　　!　　　　　　　　　 　 `.＜':;:::::::ﾍ 　 　 　 ,...　　　　　　　　　　 　 　 !
.　 　 　 　 ',　　　　　　　 　 　 　 　 ヽ::ヾ:::ヽ　,　'´　　　　　　　　　　　 　 　 l
.　　　 　 　 '　　　　　　　　　　　　　, '´` ｰ→　　　　　　　　　　　　　　　　　!
　　　　　　　 ' ,　　　　　　　　　　　　　　　y′　　　　　　　 　 　 　 　 　 　 l
　 　 　 　 　 　 ' ,　 　 　 　 　 　 　 　 　 /　　　　　　　　　　　　　　　　　　l
　　　　　 　 　 　 ＼　　　　　　　　　　　,′　　　　　　　　　　　　　　 　 　 l
　　　　　　　　 　 　 ヽ　　　　　　　　　 ,　　　　　　　　　　　　　　　　　　　! 
*/
--===========================================================================
-- fsource="C:\\Mascript\\GAME_EVENT.2DV"

mkXPR=true --dump swizzled textures as XPR
useXDK=true --Use xbox360 SDK to unswizzle textures from generated XPRs

clearlistener()
fsource = getOpenFileName \
caption:"NIER Model File" \
types: "Model Dump Volume(*.MDV)|*.mdv|2D Dump Volume(*.2DV)|*.2dv|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) do(
f = fopen fsource "rb"
fext=           getFilenameType fsource
fpath=          getFilenamePath fsource
fbatch=         getFiles (fpath+"*"+fext)
fname=  getFilenameFile fsource
fsize=          getFileSize fsource
fname2 = (fpath + fname + ".MDP.dec")
unbundler=(fpath+"UnBundler.exe")
if fext==".2DV" OR fext==".2dv" do fname2 = (fpath+fname+".2DP")
if (doesFileExist fname2)==false do fname2 = (fpath+fname+".MDP")
if (fname2!=undefined) AND ((doesFileExist fname2)==true) do(
g = fopen fname2 "rb"
test=readlong g #unsigned
fseek g 0x0 #seek_set
if test!=0x006F7A6C then(
st = timestamp() --get start time in milliseconds
openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
print (fname+fext+"\n"+localTime+"\n")
--===========================================================================
undo off(
fn ReadFixedString bstream fixedLen = (
    local str = ""
    for i = 1 to fixedLen do
    (
        str += bit.intAsChar (ReadByte bstream #unsigned)
    )
    str
)
fn readBElong fstream = (
long = readlong fstream #unsigned
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)

with redraw off (

fseek f 0x110#seek_set
NODToff = ReadBElong f + 0x100
heapoff = ReadBElong f + 0x100
fseek f heapoff#seek_set

check=readBElong f -- 0x48454150 = HEAP
if check!=0x48454150 do (
fseek f 0 #seek_set
skip=true
do (
byte1 = readbyte f#unsigned
if (byte1==0x48) then(
byte2 = readbyte f#unsigned
if (byte2==0x45) then(
byte3 = readbyte f#unsigned
if (byte3==0x41) then(
byte4 = readbyte f#unsigned
if (byte4==0x50) then(
skip=false
fseek f -4 #seek_cur
))))) while skip==true AND (ftell f)!=fsize
Print ("HEAP FOUND @ 0x"+((bit.intAsHex(ftell f))as string))
)

check=readBElong f -- 0x48454150 = HEAP
fseek f 4 #seek_cur --pad
if check==0x48454150 do(
heapPos=(ftell f)-8 --gets current position of heap, required for local jumps
heapHeaderSize=readBElong f -- 0x20 constant?
nameTable=readBElong f -- jump from heapPos
propertyTable=readBElong f -- jump from heapPos
ukn=readBElong f --another offset?
ukn=readBElong f  -- 0?
for x = 1 to (readBElong f) do(
heapID=readfixedstring f 4
nameOffset=readBElong f
ukn=readBElong f  -- 0?
dataInfo=readBElong f  -- holds swizzle info for textures
dataType=readBElong f  -- 0x40=textures
dataOffset=readBElong f  -- global offset for MDP file, if no data = -1
dataSize=readBElong f  
ukn=readBElong f  -- 0?

if heapID=="TX2D" do(
getPos=ftell f
if mkXPR==true do(
fseek f (heapPos+nameTable+nameOffset) #seek_set
dataName=readstring f
createFile (fpath+dataName+".xpr")
s = fopen (fpath+dataName+".xpr") "ab"
write=writebyte s 0x58
write=writebyte s 0x50
write=writebyte s 0x52
write=writebyte s 0x32
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x08
write=writebyte s 0x00
write=writelong s (bit.swapBytes (bit.swapBytes dataSize 1 4) 2 3)
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x01
write=writebyte s 0x54
write=writebyte s 0x58
write=writebyte s 0x32
write=writebyte s 0x44
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x40
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x34
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x18
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writestring s dataName
for x = 1 to (40-(dataName.count+1)) do(
write=writebyte s 0x00
)
fseek f (heapPos+propertyTable+dataInfo) #seek_set
for x = 1 to (16*4) do(
read=readbyte f #unsigned
write=writebyte s read
)
for x = 1 to 1920 do(
write=writebyte s 0x00
)
fseek g dataOffset #seek_set
for x = 1 to dataSize do(
read=readbyte g #unsigned
write=writebyte s read
)


)
gc()
fclose s
if useXDK==true do(
if (unbundler!=undefined) AND ((doesFileExist unbundler)==true) do(
print ("\"\""+unbundler+"\""+" "+"\""+(fpath+dataName+".xpr")+"\"\"")
DOSCommand ("\"\""+unbundler+"\" \""+(fpath+dataName+".xpr")+"\"\"")
deleteFile (fpath+dataName+".xpr")
deleteFile (fpath+dataName+".xpr.rdf")
deleteFile (fpath+dataName+"_1.tga")
deleteFile (fpath+dataName+"_2.tga")
deleteFile (fpath+dataName+"_3.tga")
deleteFile (fpath+dataName+"_4.tga")
deleteFile (fpath+dataName+"_5.tga")
deleteFile (fpath+dataName+"_6.tga")
deleteFile (fpath+dataName+"_7.tga")
deleteFile (fpath+dataName+"_8.tga")
deleteFile (fpath+dataName+"_9.tga")
deleteFile (fpath+dataName+"_10.tga")
deleteFile (fpath+dataName+"_11.tga")
deleteFile (fpath+dataName+"_12.tga")
deleteFile (fpath+dataName+"_miptail.tga")
))
fseek f getPos #seek_set    
)

-- Print ("last loop @ 0x"+((bit.intAsHex(ftell f))as string))

)


)


























--===========================================================================
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
fclose g
fclose s
flushLog()
closeLog()
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
))) else (Print "Aborted: MDP Maybe Incorrect!")))
```
## Post #3
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2010-12-30T17:11:49+00:00
- Post Title: NIER - .D2P/.2DV

Hi, i wanted to translate to spanish, but i havent sdk...
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-31T19:15:51+00:00
- Post Title: NIER - .D2P/.2DV

thats what I mean, I see multi language textures.. the game must already be in spanish
## Post #5
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2010-12-31T21:18:27+00:00
- Post Title: NIER - .D2P/.2DV

> Reply from mariokart64n
>
> thats what I mean, I see multi language textures.. the game must already be in spanish Fr, Ita, Jap and Eng
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-10T07:39:35+00:00
- Post Title: NIER - .D2P/.2DV

Thanks Mario, script works perfect.
## Post #7
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2011-01-11T11:43:34+00:00
- Post Title: NIER - .D2P/.2DV

> Reply from Gromber
>
> Hi, i wanted to translate to spanish, but i havent sdk...

I though every game is always translated in Spanish...

Is this title unreleased in Spain? Or do they sell English version?
## Post #8
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2011-01-11T14:02:11+00:00
- Post Title: NIER - .D2P/.2DV

In spain was released the pal versión:Fr, Ita, Jap and Eng... but no in spanish.

We translated the game, but we wanted to translate also the menu, loading icon, level .etc
## Post #9
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2011-01-11T15:53:03+00:00
- Post Title: NIER - .D2P/.2DV

> Reply from Gromber
>
> In spain was released the pal versión:Fr, Ita, Jap and Eng... but no in spanish.

We translated the game, but we wanted to translate also the menu, loading icon, level .etc
strange... why?

is it very rare when a game in spain releases without spanish translation?
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-12T05:33:42+00:00
- Post Title: NIER - .D2P/.2DV

Hi, Mario, i have problem with extracting *.mdp files from BG folder, almost every time unbundler.exe gives error (just crashing).
