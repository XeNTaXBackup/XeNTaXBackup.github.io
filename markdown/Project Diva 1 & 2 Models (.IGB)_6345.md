## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-04-04T00:10:11+00:00
- Post Title: Project Diva 1 & 2 Models (*.IGB)

Seriously I stared at this for a week day after day O_o

anyway I'm gonna have to let this go for a bit until I get some more free time. until then I just wanted to drop any samples and information I had. encase someone more experienced could take on the format structure.

here's a converter someone made but has manually inputed offsets, so only works on one file. but you can find samples in the zip there too, and I've also included the logs from my maxscript. it details the results from reading through the tables.
[http://www.mediafire.com/?zjp9y40vzfv94v5](http://www.mediafire.com/?zjp9y40vzfv94v5)

here's a quick overview of the format, theres 6 sets of sizes and counts, then a bunch of tables. most of the sizes and counts are for those tables. I've been able to read through the tables, but then I get stuck at the raw data. all I have is a count, and a size.. but no other offsets to split the data up.. so I'm unable to break down the mesh parts..

here's the maxscript I came up with, reads down to the end of raw data section then stops. I confident that I'm reading the tables properly. But I just cant make sense of the numbers.
and sorry the script is a big mess...

below the script I'll try to explain the format a bit more in detail...

```
-- fsource="C:\\Program Files (x86)\\MikuMikuDanceE_v713\\PMDEditor_0094b\\_data\\vmd\\stand.vmd"
-- fsource="C:\\Users\\ACER_PREDATOR\\Downloads\\Hatsune_Miku_Project_DIVA_2nd_JAP_PSP\\PSP_GAME\\USRDIR\\media\\afs\\skin00_000b.igb"
-- fsource="C:\\Program Files (x86)\\MikuMikuDanceE_v713\\UserFile\\Model\\_edits\\AirDoucheAitoro\\New folder\\bm\\book.igb"

fsource = GetOpenFileName \
caption:"PMD Importer" \
types: "igb(*.igb)|*.IGB|All files (*.*)|*.*|"
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
print (fname+fext+"\n"+localTime+"\n")
--===========================================================================
undo off(

fn ReadFixedString bstream fixedLen =
(
    local str = ""
    for i = 1 to fixedLen do
    (
        str0 = ReadByte bstream #unsigned
        if str0==0x0A do str+="\r\n"
        if str0!=0xFD AND str0!=0xFC do str+= bit.intAsChar str0
    )
    str
)
with redraw off (
nameArray=#()

Face_array=#()
Vert_array=#()
UV_array=#()
countArray=#()

ukn1=readlong f #unsigned -- Size of Section
ukn2=readlong f #unsigned -- Count for Section

ukn3=readlong f #unsigned -- Size of Section
ukn4=readlong f #unsigned -- Count for Section

ukn5=readlong f #unsigned
ukn6=readlong f #unsigned

ukn7=readlong f #unsigned
ukn8=readlong f #unsigned -- RAW Data count

ukn9=readlong f #unsigned
ukn10=readlong f #unsigned

ukn11=readlong f #unsigned
ukn12=readlong f #unsigned

nameTableSize=readlong f #unsigned
nameTableCount=readlong f #unsigned

append countArray ukn2
append countArray ukn4
append countArray ukn6
append countArray ukn8
append countArray ukn10
append countArray ukn12
append countArray nameTableCount


print "=========================================================="
Print ("Name Table @ 0x"+((bit.intAsHex(ftell f))as string))
print "=========================================================="
for x = 1 to nameTableCount do(
ResName=ReadFixedString f (readlong f #unsigned)
append nameArray ResName
print ((x as string)+".) "+resName)
)


stringLength=#()
for x = 1 to ukn10 do( -- index table giving name to every section?
uknB1=readlong f #unsigned -- stringSize
uknB2=readlong f #unsigned -- flag ? always 1 ?
uknB3=readlong f #unsigned -- flag ? always 0 ?
if (uknB2+uknB3)!=1.0 do PRINT "FLAG CHANGE!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
append stringLength uknB1
)


print "=========================================================="
Print ("Call Table @ 0x"+((bit.intAsHex(ftell f))as string))
print "=========================================================="
nameArray2=#()
for x = 1 to ukn10 do(
ResName=readFixedString f stringLength[x]
append nameArray2 ResName
print ((x as string)+".) "+resName)
)    


print "=========================================================="
Print ("New Section @ 0x"+((bit.intAsHex(ftell f))as string))
print "=========================================================="
uknC1=readlong f #unsigned
uknC2=readlong f #unsigned
uknC3=readlong f #unsigned
uknC4=readlong f #unsigned
uknC5=readlong f #unsigned
uknC6=readlong f #unsigned
uknC7=readlong f #unsigned
uknC8=readlong f #unsigned
-- Print nameArray[uknC2]
Print ("0x"+((bit.intAsHex(uknC1))as string))
Print ("0x"+((bit.intAsHex(uknC2))as string))
Print ("0x"+((bit.intAsHex(uknC3))as string))
Print ("0x"+((bit.intAsHex(uknC4))as string))
Print ("0x"+((bit.intAsHex(uknC5))as string))
Print ("0x"+((bit.intAsHex(uknC6))as string))
Print ("0x"+((bit.intAsHex(uknC7))as string))
Print ("0x"+((bit.intAsHex(uknC8))as string))
print "=========================================================="
for x = 1 to uknC3 do( -- no count?
ResName=readstring f
print ((x as string)+".) "+resName)
)    
append countArray uknC3
print "=========================================================="
Print ("UKN 4 @ 0x"+((bit.intAsHex(ftell f))as string))
print "=========================================================="
dataLen=#()
for x = 1 to ukn4 do(
uknD1=readlong f
uknD2=readlong f
uknD3=readlong f
uknD4=readlong f
uknD5=readlong f
uknD6=readlong f
Print ""
Print ((uknD1 as string)+", "+(uknD2 as string)+", "+(uknD3 as string)+", "+(uknD4 as string)+", "+(uknD5 as string)+", "+(uknD6 as string))
append dataLen [uknD1,uknD4,uknD6]
)


print "=========================================================="

namespace=""
nameArray3=#()
for x = 1 to dataLen.count do(
print ""
ResName=ReadFixedString f (dataLen[x][1])
append nameArray3 ResName
Print ((x as string)+".) "+resName)

for y = 1 to ((dataLen[x][2]*6)/2) do(
uknD7=readshort f #unsigned
-- Print uknD7
namespace+=((uknD7 as string)+", ")
)
-- print "------------"
print namespace
namespace=""
)











print "=========================================================="
Print ("New Section 2 @ 0x"+((bit.intAsHex(ftell f))as string))
print "=========================================================="

uknE1=readlong f #unsigned -- always 0x17
uknE2=readlong f #unsigned -- always 1
uknE3=readlong f #unsigned -- always 1
uknE4=readlong f #unsigned -- string Length
uknE5=readFixedString f uknE4 -- always called system?

Print ("0x"+((bit.intAsHex(uknE1))as string))
Print ("0x"+((bit.intAsHex(uknE2))as string))
Print ("0x"+((bit.intAsHex(uknE3))as string))
Print ("0x"+((bit.intAsHex(uknE4))as string))


print "=========================================================="
Print ("New Section 3 @ 0x"+((bit.intAsHex(ftell f))as string))
print "=========================================================="
uknE6=readlong f #unsigned -- Size or offset to next table?
uknE7=readlong f #unsigned -- Count ?
append countArray uknE7
nameArray4=#()
for x = 1 to uknE7 do(
ResName=readstring f
append nameArray4 ResName
Print ((x as string)+".) "+resName)
)    

print "=========================================================="
print "UKN 2"
print "=========================================================="
cnt3=0
cnt4=0
for x = 1 to ukn2 do( -- no count?
chunkID=readlong f
if chunkID==3 do cnt3+=1
if chunkID==4 do cnt4+=1
chunkSize=readlong f-8
Print ("ByteID: "+(chunkID as string))

    
-- fseek f chunkSize #seek_cur
for y = 1 to chunkSize/4 do(
uknE8=readlong f #unsigned -- Count ?
Print uknE8
)
-- Print "====================="    
)
Print "====================="    
Print ukn2
Print cnt3
Print cnt4
    Print ("Read @ 0x"+((bit.intAsHex(ftell f))as string))

print "=========================================================="
Print ("New Section 4 @ 0x"+((bit.intAsHex(ftell f))as string))
print "=========================================================="
uknF1=readlong f #unsigned
uknE2=readlong f #unsigned
append countArray uknE2
Print uknF1
for x = 1 to uknE2 do( -- bones?
uknF1=readshort f #unsigned
-- print uknF1
Print ((x as string)+".) "+(uknF1 as string))
)


    Print ("Read @ 0x"+((bit.intAsHex(ftell f))as string))

    
print "=========================================================="
Print ("New Section 5 @ 0x"+((bit.intAsHex(ftell f))as string))
print "=========================================================="
uknG1=readlong f
Print nameArray[uknG1+1]
    
namespace=""
print "Count"
        Print nameTableCount
for x = 1 to ukn6 do(
uknG2=readlong f #unsigned -- Type
uknG3=readlong f #unsigned -- Size
-- print uknG2
-- print uknG3
Print ((x as string)+".) "+(nameArray3[uknG2+1])+" ["+(((uknG3-8)/4)as string)+"]")
for y = 1 to (uknG3-8)/4 do(
uknG4=readlong f #unsigned
namespace+=(uknG4 as string)
namespace+=", "
)
Print namespace
print ""
namespace=""
)



-- for x = 1 to ukn8 do(

-- )
-- uknH1=readlong f #unsigned -- ??

-- for x = 1 to 108/3 do(
-- vx=readfloat f
-- vy=readfloat f
-- vz=readfloat f
-- -- nx=readfloat f
-- -- ny=readfloat f
-- nz=readfloat f
-- append Vert_array[vx,vy,vz]
-- append UV_array[0,0,0]
-- )



-- fa=1
-- fb=2
-- fc=3
-- for x = 1 to Vert_array.count/3 do(
-- append Face_array[fc,fb,fa]
-- fa+=1
-- fb+=2
-- fc+=3
-- )



-- msh = mesh vertices:Vert_array faces:Face_array
-- msh.numTVerts = UV_array.count
-- buildTVFaces msh
-- msh.name=modelName
-- convertTo msh PolyMeshObject
-- for j = 1 to UV_array.count do setTVert msh j UV_array[j]
--for j = 1 to Face_array.count do setTVFace msh j Face_array[j]


print "=========================================================="
print ("Data Count: "+(ukn8 as string))
print "=========================================================="



print "=========================================================="
print "Counts"
print "=========================================================="
print countArray






--===========================================================================
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
enableSceneRedraw()
flushLog()
closeLog()
if logON==false do deleteFile (fpath+fname+"_log.txt")
gc()
fclose f
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
))) else (Print "Aborted.")
```


> struct IGB_HEADER { // 56bytes
>
> LONG Size1
>
> LONG Count1
>
> 
>
> LONG Size2
>
> LONG Count2
>
> 
>
> LONG Size3
>
> LONG Count3
>
> 
>
> LONG Size4
>
> LONG Count4
>
> 
>
> LONG Size5
>
> LONG Count5
>
> 
>
> LONG Ukn1 // Size is out of range? no idea
>
> LONG Ukn2 // Looks like 24bite+8Bit Count? maybe bit flags?
>
> 
>
> LONG StrTableSize
>
> LONG StrTableCount
>
> }
>
> 
>
> Example:
>
> Code: Select all00000000   E0 00 00 00 0A 00 00 00  A8 04 00 00 14 00 00 00
>
> 00000010   14 02 00 00 0D 00 00 00  10 00 00 00 02 00 00 00
>
> 00000020   B5 06 00 00 33 00 00 00  DA FA 00 00 09 00 00 F0
>
> 00000030   C8 00 00 00 0D 00 00 00
>
> 
>
> So we Pull out these counts:
>
> Size1 : 224
>
> Count1 : 10
>
> 
>
> Size2 : 1192
>
> Count2 : 20
>
> 
>
> Size3 : 532
>
> Count3 : 13
>
> 
>
> Size4 : 16
>
> Count4 : 2
>
> 
>
> Size5 : 1717
>
> Count5 : 51
>
> 
>
> Ukn1 : 64218
>
> Ukn2 : 9 & 240
>
> 
>
> StrTableSize : 200
>
> StrTableCount : 13
>
> 
>
> 
>
> The First tble we see seems to be the master string table, contains names of the resource contents.
>
> struct STR_TABLE {
>
> LONG ChrCount
>
> CHAR resName[ChrCount]
>
> }
>
> 
>
> Example:
>
> Code: Select all00000030                            0B 00 00 00 69 67 49 6E           ....igIn
>
> 00000040   66 6F 4C 69 73 74 00 0E  00 00 00 69 67 54 65 78   foList.....igTex
>
> 00000050   74 75 72 65 4C 69 73 74  00 08 00 00 00 69 67 47   tureList.....igG
>
> 00000060   72 6F 75 70 00 0B 00 00  00 69 67 4E 6F 64 65 4C   roup.....igNodeL
>
> 00000070   69 73 74 00 0C 00 00 00  69 67 54 72 61 6E 73 66   ist.....igTransf
>
> 00000080   6F 72 6D 00 10 00 00 00  69 67 47 72 61 70 68 50   orm.....igGraphP
>
> 00000090   61 74 68 4C 69 73 74 00  0C 00 00 00 69 67 53 63   athList.....igSc
>
> 000000A0   65 6E 65 49 6E 66 6F 00  0B 00 00 00 6F 62 6A 5F   eneInfo.....obj_
>
> 000000B0   6D 6F 6F 6E 30 30 00 0C  00 00 00 53 63 65 6E 65   moon00.....Scene
>
> 000000C0   20 47 72 61 70 68 00 0B  00 00 00 6F 62 6A 5F 6D    Graph.....obj_m
>
> 000000D0   6F 6F 6E 30 31 00 0B 00  00 00 53 63 65 6E 65 20   oon01.....Scene 
>
> 000000E0   52 6F 6F 74 00 0B 00 00  00 6F 62 6A 5F 6D 6F 6F   Root.....obj_moo
>
> 000000F0   6E 30 32 00 00 00 00 00                            n02.....
>
> 
>
> from the string table we get the following
>
> 
>
> 01.) igInfoList
>
> 02.) igTextureList
>
> 03.) igGroup
>
> 04.) igNodeList
>
> 05.) igTransform
>
> 06.) igGraphPathList
>
> 07.) igSceneInfo
>
> 08.) obj_moon00
>
> 09.) Scene Graph
>
> 10.) obj_moon01
>
> 11.) Scene Root
>
> 12.) obj_moon02
>
> 13.) ""
>
> 
>
> the last entry always seems to be empty?
>
> 
>
> Next theres an index, with string counts and 2 flags, or indexes?
>
> struct CALL_TABLE { // xCount5
>
> LONG ChrCount
>
> LONG Ukn1 // Always 0, Could by a flag
>
> LONG Ukn2 // Always 0, Could by a flag
>
> }
>
> 
>
> Example
>
> Code: Select all000000F0                            18 00 00 00 01 00 00 00
>
> 00000100   00 00 00 00 15 00 00 00  01 00 00 00 00 00 00 00
>
> 00000110   10 00 00 00 01 00 00 00  00 00 00 00 12 00 00 00
>
> 00000120   01 00 00 00 00 00 00 00  0F 00 00 00 01 00 00 00
>
> 00000130   00 00 00 00 15 00 00 00  01 00 00 00 00 00 00 00
>
> 00000140   14 00 00 00 01 00 00 00  00 00 00 00 17 00 00 00
>
> 00000150   01 00 00 00 00 00 00 00  12 00 00 00 01 00 00 00
>
> 00000160   00 00 00 00 11 00 00 00  01 00 00 00 00 00 00 00
>
> 00000170   12 00 00 00 01 00 00 00  00 00 00 00 10 00 00 00
>
> 00000180   01 00 00 00 00 00 00 00  15 00 00 00 01 00 00 00
>
> 00000190   00 00 00 00 1C 00 00 00  01 00 00 00 00 00 00 00
>
> 000001A0   11 00 00 00 01 00 00 00  00 00 00 00 10 00 00 00
>
> 000001B0   01 00 00 00 00 00 00 00  10 00 00 00 01 00 00 00
>
> 000001C0   00 00 00 00 1D 00 00 00  01 00 00 00 00 00 00 00
>
> 000001D0   18 00 00 00 01 00 00 00  00 00 00 00 1A 00 00 00
>
> 000001E0   01 00 00 00 00 00 00 00  19 00 00 00 01 00 00 00
>
> 000001F0   00 00 00 00 1D 00 00 00  01 00 00 00 00 00 00 00
>
> 00000200   12 00 00 00 01 00 00 00  00 00 00 00 19 00 00 00
>
> 00000210   01 00 00 00 00 00 00 00  16 00 00 00 01 00 00 00
>
> 00000220   00 00 00 00 18 00 00 00  01 00 00 00 00 00 00 00
>
> 00000230   1E 00 00 00 01 00 00 00  00 00 00 00 1D 00 00 00
>
> 00000240   01 00 00 00 00 00 00 00  1C 00 00 00 01 00 00 00
>
> 00000250   00 00 00 00 17 00 00 00  01 00 00 00 00 00 00 00
>
> 00000260   16 00 00 00 01 00 00 00  00 00 00 00 17 00 00 00
>
> 00000270   01 00 00 00 00 00 00 00  1A 00 00 00 01 00 00 00
>
> 00000280   00 00 00 00 15 00 00 00  01 00 00 00 00 00 00 00
>
> 00000290   16 00 00 00 01 00 00 00  00 00 00 00 15 00 00 00
>
> 000002A0   01 00 00 00 00 00 00 00  17 00 00 00 01 00 00 00
>
> 000002B0   00 00 00 00 15 00 00 00  01 00 00 00 00 00 00 00
>
> 000002C0   11 00 00 00 01 00 00 00  00 00 00 00 11 00 00 00
>
> 000002D0   01 00 00 00 00 00 00 00  11 00 00 00 01 00 00 00
>
> 000002E0   00 00 00 00 12 00 00 00  01 00 00 00 00 00 00 00
>
> 000002F0   12 00 00 00 01 00 00 00  00 00 00 00 18 00 00 00
>
> 00000300   01 00 00 00 00 00 00 00  18 00 00 00 01 00 00 00
>
> 00000310   00 00 00 00 15 00 00 00  01 00 00 00 00 00 00 00
>
> 00000320   16 00 00 00 01 00 00 00  00 00 00 00 1A 00 00 00
>
> 00000330   01 00 00 00 00 00 00 00  11 00 00 00 01 00 00 00
>
> 00000340   00 00 00 00 14 00 00 00  01 00 00 00 00 00 00 00
>
> 00000350   1C 00 00 00 01 00 00 00  00 00 00 00
>
> 
>
> Follows is another string table, nothing special. this is what we get.
>
> I'm assuming these are different memory storage types that the format
>
> can invoke the game to use. so now any flags found could possibly
>
> reference to either the master string table or this call table.
>
> 
>
> 01.) igUnsignedCharMetaField
>
> 02.) igObjectRefMetaField
>
> 03.) igCharMetaField
>
> 04.) igStructMetaField
>
> 05.) igIntMetaField
>
> 06.) igCharArrayMetaField
>
> 07.) igIntArrayMetaField
>
> 08.) igUnsignedIntMetaField
>
> 09.) igRawRefMetaField
>
> 10.) igShortMetaField
>
> 11.) igStringMetaField
>
> 12.) igBoolMetaField
>
> 13.) igMemoryRefMetaField
>
> 14.) igMemoryDescriptorMetaField
>
> 15.) igFloatMetaField
>
> 16.) igLongMetaField
>
> 17.) igEnumMetaField
>
> 18.) igIGBMetaInfoStructMetaField
>
> 19.) igUnsignedLongMetaField
>
> 20.) igObjectRefArrayMetaField
>
> 21.) igStatisticDataMetaField
>
> 22.) igUnsignedCharArrayMetaField
>
> 23.) igDoubleMetaField
>
> 24.) igUnsignedShortMetaField
>
> 25.) igDependencyMetaField
>
> 26.) igVirtualCFuncMetaField
>
> 27.) igUnsignedShortArrayMetaField
>
> 28.) igUnsignedLongArrayMetaField
>
> 29.) igUnsignedIntArrayMetaField
>
> 30.) igStringArrayMetaField
>
> 31.) igShortArrayMetaField
>
> 32.) igRawRefArrayMetaField
>
> 33.) igMemoryRefArrayMetaField
>
> 34.) igLongArrayMetaField
>
> 35.) igFloatArrayMetaField
>
> 36.) igEnumArrayMetaField
>
> 37.) igDoubleArrayMetaField
>
> 38.) igBoolArrayMetaField
>
> 39.) igVec3fMetaField
>
> 40.) igVec2fMetaField
>
> 41.) igVec4fMetaField
>
> 42.) igVec3ucMetaField
>
> 43.) igVec4ucMetaField
>
> 44.) igVec3fAlignedMetaField
>
> 45.) igVec4fAlignedMetaField
>
> 46.) igMatrix44fMetaField
>
> 47.) igVec4fArrayMetaField
>
> 48.) igTrackedElementMetaField
>
> 49.) igVec4iMetaField
>
> 50.) igItemDataBaseField
>
> 51.) igInterfaceDeclarationField
>
> 
>
> 
>
> Next we see start of new header data, and likely anything that follows will be link to either the call table or name table
>
> 
>
> Example
>
> Code: Select all000007A0                                           5B 00 00                [..
>
> 000007B0   00 01 00 00 00 05 00 00  00 09 00 00 00 0A 00 00   ................
>
> 000007C0   00 10 00 00 00 0D 00 00  00 0B 00 00 00 43 6C 75   .............Clu
>
> 000007D0   74 44 61 74 61 00 49 6D  61 67 65 44 61 74 61 00   tData.ImageData.
>
> 000007E0   56 65 72 74 65 78 41 72  72 61 79 44 61 74 61 00   VertexArrayData.
>
> 000007F0   47 43 56 65 72 74 65 78  44 61 74 61 00 56 65 72   GCVertexData.Ver
>
> 00000800   74 65 78 44 61 74 61 00                            texData.
>
> 
>
> not much can be deduced from this header, it always appears the same. same size, same info etc..
>
> the first LONG, 0x5B is the size of this entire section.
>
> 
>
> 1.) ClutData
>
> 2.) ImageData
>
> 3.) VertexArrayData
>
> 4.) GCVertexData
>
> 5.) VertexData
>
> 
>
> Ok.. so now some more indexes...
>
> 
>
> struct INFO_LIST { // xCount2
>
> LONG ChrCount
>
> LONG Ukn1 // Always 1, Flag?
>
> LONG Ukn2 // Always 1, Flag?
>
> LONG Size // calc: (Size*6) = bytes
>
> LONG Ukn3 // ??Index
>
> LONG Ukn4 // ??Index
>
> }
>
> 
>
> 01.) 10, 1, 0, 0, -1, 2
>
> 02.) 14, 1, 0, 1, 0, 3
>
> 03.) 12, 1, 0, 1, 1, 7
>
> 04.) 18, 1, 0, 3, 2, 13
>
> 05.) 18, 1, 0, 6, 2, 14
>
> 06.) 20, 1, 0, 4, 2, 11
>
> 07.) 22, 1, 0, 4, 5, 11
>
> 08.) 24, 1, 0, 5, 2, 13
>
> 09.) 20, 1, 0, 4, 2, 10
>
> 10.) 8, 1, 0, 2, 1, 5
>
> 11.) 12, 1, 0, 9, 9, 12
>
> 12.) 12, 1, 0, 3, 0, 5
>
> 13.) 14, 1, 0, 3, 11, 5
>
> 14.) 12, 1, 0, 3, 12, 5
>
> 15.) 14, 1, 0, 3, 12, 5
>
> 16.) 12, 1, 0, 3, 12, 5
>
> 17.) 8, 1, 0, 3, 1, 7
>
> 18.) 8, 1, 0, 4, 16, 8
>
> 19.) 16, 1, 0, 3, 12, 5
>
> 20.) 12, 1, 0, 7, 17, 11
>
> 
>
> 
>
> I haven't broken down the information that each section give yet. but they all seem like counts stored as SHORT's
>
> 
>
> 
>
> Example
>
> Code: Select all00000800                            0A 00 00 00 01 00 00 00           ........
>
> 00000810   00 00 00 00 00 00 00 00  FF FF FF FF 02 00 00 00   ........yyyy....
>
> 00000820   0E 00 00 00 01 00 00 00  00 00 00 00 01 00 00 00   ................
>
> 00000830   00 00 00 00 03 00 00 00  0C 00 00 00 01 00 00 00   ................
>
> 00000840   00 00 00 00 01 00 00 00  01 00 00 00 07 00 00 00   ................
>
> 00000850   12 00 00 00 01 00 00 00  00 00 00 00 03 00 00 00   ................
>
> 00000860   02 00 00 00 0D 00 00 00  12 00 00 00 01 00 00 00   ................
>
> 00000870   00 00 00 00 06 00 00 00  02 00 00 00 0E 00 00 00   ................
>
> 00000880   14 00 00 00 01 00 00 00  00 00 00 00 04 00 00 00   ................
>
> 00000890   02 00 00 00 0B 00 00 00  16 00 00 00 01 00 00 00   ................
>
> 000008A0   00 00 00 00 04 00 00 00  05 00 00 00 0B 00 00 00   ................
>
> 000008B0   18 00 00 00 01 00 00 00  00 00 00 00 05 00 00 00   ................
>
> 000008C0   02 00 00 00 0D 00 00 00  14 00 00 00 01 00 00 00   ................
>
> 000008D0   00 00 00 00 04 00 00 00  02 00 00 00 0A 00 00 00   ................
>
> 000008E0   08 00 00 00 01 00 00 00  00 00 00 00 02 00 00 00   ................
>
> 000008F0   01 00 00 00 05 00 00 00  0C 00 00 00 01 00 00 00   ................
>
> 00000900   00 00 00 00 09 00 00 00  09 00 00 00 0C 00 00 00   ................
>
> 00000910   0C 00 00 00 01 00 00 00  00 00 00 00 03 00 00 00   ................
>
> 00000920   00 00 00 00 05 00 00 00  0E 00 00 00 01 00 00 00   ................
>
> 00000930   00 00 00 00 03 00 00 00  0B 00 00 00 05 00 00 00   ................
>
> 00000940   0C 00 00 00 01 00 00 00  00 00 00 00 03 00 00 00   ................
>
> 00000950   0C 00 00 00 05 00 00 00  0E 00 00 00 01 00 00 00   ................
>
> 00000960   00 00 00 00 03 00 00 00  0C 00 00 00 05 00 00 00   ................
>
> 00000970   0C 00 00 00 01 00 00 00  00 00 00 00 03 00 00 00   ................
>
> 00000980   0C 00 00 00 05 00 00 00  08 00 00 00 01 00 00 00   ................
>
> 00000990   00 00 00 00 03 00 00 00  01 00 00 00 07 00 00 00   ................
>
> 000009A0   08 00 00 00 01 00 00 00  00 00 00 00 04 00 00 00   ................
>
> 000009B0   10 00 00 00 08 00 00 00  10 00 00 00 01 00 00 00   ................
>
> 000009C0   00 00 00 00 03 00 00 00  0C 00 00 00 05 00 00 00   ................
>
> 000009D0   0C 00 00 00 01 00 00 00  00 00 00 00 07 00 00 00   ................
>
> 000009E0   11 00 00 00 0B 00 00 00  69 67 4F 62 6A 65 63 74   ........igObject
>
> 000009F0   00 00 69 67 4E 61 6D 65  64 4F 62 6A 65 63 74 00   ..igNamedObject.
>
> 00000A00   0A 00 02 00 04 00 69 67  44 69 72 45 6E 74 72 79   ......igDirEntry
>
> 00000A10   00 00 0A 00 02 00 04 00  69 67 4F 62 6A 65 63 74   ........igObject
>
> 00000A20   44 69 72 45 6E 74 72 79  00 00 0A 00 02 00 04 00   DirEntry........
>
> 00000A30   04 00 0B 00 04 00 04 00  0C 00 04 00 69 67 4D 65   ............igMe
>
> 00000A40   6D 6F 72 79 44 69 72 45  6E 74 72 79 00 00 0A 00   moryDirEntry....
>
> 00000A50   02 00 04 00 04 00 07 00  04 00 04 00 0A 00 04 00   ................
>
> 00000A60   0B 00 0B 00 01 00 04 00  0C 00 04 00 04 00 0D 00   ................
>
> 00000A70   04 00 69 67 45 78 74 65  72 6E 61 6C 44 69 72 45   ..igExternalDirE
>
> 00000A80   6E 74 72 79 00 00 0A 00  02 00 04 00 0A 00 07 00   ntry............
>
> 00000A90   04 00 0A 00 08 00 04 00  04 00 09 00 04 00 69 67   ..............ig
>
> 00000AA0   45 78 74 65 72 6E 61 6C  49 6D 61 67 65 45 6E 74   ExternalImageEnt
>
> 00000AB0   72 79 00 00 0A 00 02 00  04 00 0A 00 07 00 04 00   ry..............
>
> 00000AC0   0A 00 08 00 04 00 04 00  09 00 04 00 69 67 45 78   ............igEx
>
> 00000AD0   74 65 72 6E 61 6C 49 6E  64 65 78 65 64 45 6E 74   ternalIndexedEnt
>
> 00000AE0   72 79 00 00 0A 00 02 00  04 00 04 00 07 00 04 00   ry..............
>
> 00000AF0   04 00 08 00 04 00 04 00  0A 00 04 00 04 00 0C 00   ................
>
> 00000B00   04 00 69 67 45 78 74 65  72 6E 61 6C 49 6E 66 6F   ..igExternalInfo
>
> 00000B10   45 6E 74 72 79 00 0A 00  02 00 04 00 0A 00 07 00   Entry...........
>
> 00000B20   04 00 04 00 08 00 04 00  0A 00 09 00 04 00 69 67   ..............ig
>
> 00000B30   49 6E 66 6F 00 00 0A 00  02 00 04 00 0B 00 04 00   Info............
>
> 00000B40   01 00 69 67 53 63 65 6E  65 49 6E 66 6F 00 0A 00   ..igSceneInfo...
>
> 00000B50   02 00 04 00 0B 00 04 00  01 00 01 00 05 00 04 00   ................
>
> 00000B60   01 00 06 00 04 00 01 00  07 00 04 00 0F 00 08 00   ................
>
> 00000B70   08 00 0F 00 09 00 08 00  26 00 0A 00 0C 00 01 00   ........&.......
>
> 00000B80   0B 00 04 00 69 67 44 61  74 61 4C 69 73 74 00 00   ....igDataList..
>
> 00000B90   04 00 02 00 04 00 04 00  03 00 04 00 0C 00 04 00   ................
>
> 00000BA0   04 00 69 67 4F 62 6A 65  63 74 4C 69 73 74 00 00   ..igObjectList..
>
> 00000BB0   04 00 02 00 04 00 04 00  03 00 04 00 0C 00 04 00   ................
>
> 00000BC0   04 00 69 67 4E 6F 64 65  4C 69 73 74 00 00 04 00   ..igNodeList....
>
> 00000BD0   02 00 04 00 04 00 03 00  04 00 0C 00 04 00 04 00   ................
>
> 00000BE0   69 67 54 65 78 74 75 72  65 4C 69 73 74 00 04 00   igTextureList...
>
> 00000BF0   02 00 04 00 04 00 03 00  04 00 0C 00 04 00 04 00   ................
>
> 00000C00   69 67 49 6E 66 6F 4C 69  73 74 00 00 04 00 02 00   igInfoList......
>
> 00000C10   04 00 04 00 03 00 04 00  0C 00 04 00 04 00 69 67   ..............ig
>
> 00000C20   4E 6F 64 65 00 00 0A 00  02 00 04 00 01 00 03 00   Node............
>
> 00000C30   04 00 04 00 05 00 04 00  69 67 47 72 6F 75 70 00   ........igGroup.
>
> 00000C40   0A 00 02 00 04 00 01 00  03 00 04 00 04 00 05 00   ................
>
> 00000C50   04 00 01 00 07 00 04 00  69 67 47 72 61 70 68 50   ........igGraphP
>
> 00000C60   61 74 68 4C 69 73 74 00  04 00 02 00 04 00 04 00   athList.........
>
> 00000C70   03 00 04 00 0C 00 04 00  04 00 69 67 54 72 61 6E   ..........igTran
>
> 00000C80   73 66 6F 72 6D 00 0A 00  02 00 04 00 01 00 03 00   sform...........
>
> 00000C90   04 00 04 00 05 00 04 00  01 00 07 00 04 00 2D 00   ..............-.
>
> 00000CA0   08 00 40 00 04 00 09 00  04 00 01 00 0A 00 04 00   ..@.............
>
> 
>
> ======================================================================
>
> igInfoList
>
> ======================================================================
>
> 1.) igObject
>
> 
>
> 2.) igNamedObject
>
> 10, 2, 4
>
> 
>
> 3.) igDirEntry
>
> 10, 2, 4
>
> 
>
> 4.) igObjectDirEntry
>
> 10, 2, 4, 4, 11, 4, 4, 12,4
>
> 
>
> 5.) igMemoryDirEntry
>
> 10, 2, 4, 4, 7, 4, 4, 10, 4, 11, 11, 1, 4, 12, 4, 4, 13, 4
>
> 
>
> 6.) igExternalDirEntry
>
> 10, 2, 4, 10, 7, 4, 10, 8, 4, 4, 9, 4
>
> 
>
> 7.) igExternalImageEntry
>
> 10, 2, 4, 10, 7, 4, 10, 8, 4, 4, 9, 4
>
> 
>
> 8.) igExternalIndexedEntry
>
> 10, 2, 4, 4, 7, 4, 4, 8, 4, 4, 10, 4, 4, 12, 4
>
> 
>
> 9.) igExternalInfoEntry
>
> 10, 2, 4, 10, 7, 4, 4, 8, 4, 10, 9, 4
>
> 
>
> 10.) igInfo
>
> 10, 2, 4, 11, 4, 1
>
> 
>
> 11.) igSceneInfo
>
> 10, 2, 4, 11, 4, 1, 1, 5, 4, 1, 6, 4, 1, 7, 4, 15, 8, 8, 15, 9, 8, 38, 10, 12, 1, 11, 4
>
> 
>
> 12.) igDataList
>
> 4, 2, 4, 4, 3, 4, 12, 4, 4
>
> 
>
> 13.) igObjectList
>
> 4, 2, 4, 4, 3, 4, 12, 4, 4
>
> 
>
> 14.) igNodeList
>
> 4, 2, 4, 4, 3, 4, 12, 4, 4
>
> 
>
> 15.) igTextureList
>
> 4, 2, 4, 4, 3, 4, 12, 4, 4
>
> 
>
> 16.) igInfoList
>
> 4, 2, 4, 4, 3, 4, 12, 4, 4
>
> 
>
> 17.) igNode
>
> 10, 2, 4, 1, 3, 4, 4, 5, 4
>
> 
>
> 18.) igGroup
>
> 10, 2, 4, 1, 3, 4, 4, 5, 4, 1, 7, 4
>
> 
>
> 19.) igGraphPathList
>
> 4, 2, 4, 4, 3, 4, 12, 4, 4
>
> 
>
> 20.) igTransform
>
> 10, 2, 4, 1, 3, 4, 4, 5, 4, 1, 7, 4, 45, 8, 64, 4, 9, 4, 1, 10, 4
>
> 
>
> 
>
> 
>
> The next section doesn't make alot of sense O_o...
>
> if we follow the theory that each section is in line of our Name table.
>
> then this section should be the "igTextureList" but there isnt any unique data
>
> observed here...
>
> 
>
> data always appears to be the same.. defines size, some counts and a string.
>
> 
>
> Example
>
> Code: Select all00000CB0   17 00 00 00 01 00 00 00  01 00 00 00 07 00 00 00   ................
>
> 00000CC0   73 79 73 74 65 6D 00                               system.
>
> 
>
> 
>
> ======================================================================
>
> igTextureList
>
> ======================================================================
>
> Next is another string table
>
> 
>
> LONG Size, Long Count, STRING
>
> 
>
> Example
>
> Code: Select all00000CC0                                     4C 00 00 00 42              L...B
>
> 00000CD0   6F 6F 74 73 74 72 61 70  00 53 79 73 74 65 6D 00   ootstrap.System.
>
> 00000CE0   53 79 73 74 65 6D 32 00  53 74 61 74 69 63 00 4D   System2.Static.M
>
> 00000CF0   65 74 61 44 61 74 61 00  53 74 72 69 6E 67 00 4E   etaData.String.N
>
> 00000D00   6F 6E 54 72 61 63 6B 65  64 00 44 65 66 61 75 6C   onTracked.Defaul
>
> 00000D10   74 00 46 61 73 74 00 41  47 50 00 56 52 41 4D 00   t.Fast.AGP.VRAM.
>
> 00000D20   41 75 78 69 6C 69 61 72  79 00 4C 6F 6E 67 54 65   Auxiliary.LongTe
>
> 00000D30   72 6D 00 4D 65 64 69 75  6D 54 65 72 6D 00 53 68   rm.MediumTerm.Sh
>
> 00000D40   6F 72 74 54 65 72 6D 00  41 70 70 6C 69 63 61 74   ortTerm.Applicat
>
> 00000D50   69 6F 6E 00 56 69 73 75  61 6C 43 6F 6E 74 65 78   ion.VisualContex
>
> 00000D60   74 00 41 53 50 00 50 50  46 58 00 45 66 66 65 63   t.ASP.PPFX.Effec
>
> 00000D70   74 00 53 74 61 74 69 73  74 69 63 73 00 4C 65 76   t.Statistics.Lev
>
> 00000D80   65 6C 00 57 6F 72 6C 64  00 41 63 74 6F 72 00 41   el.World.Actor.A
>
> 00000D90   6E 69 6D 61 74 69 6F 6E  44 61 74 61 00 47 65 6F   nimationData.Geo
>
> 00000DA0   6D 65 74 72 79 00 56 65  72 74 65 78 00 49 6D 61   metry.Vertex.Ima
>
> 00000DB0   67 65 00 49 6D 61 67 65  4F 62 6A 65 63 74 00 41   ge.ImageObject.A
>
> 00000DC0   74 74 72 69 62 75 74 65  00 4E 6F 64 65 00 50 68   ttribute.Node.Ph
>
> 00000DD0   79 73 69 63 73 00 41 49  00 41 75 64 69 6F 00 56   ysics.AI.Audio.V
>
> 00000DE0   69 64 65 6F 00 54 65 6D  70 6F 72 61 72 79 00 44   ideo.Temporary.D
>
> 00000DF0   4D 41 00 53 68 61 64 65  72 00 52 65 6E 64 65 72   MA.Shader.Render
>
> 00000E00   4C 69 73 74 00 54 65 78  74 75 72 65 00 43 6C 75   List.Texture.Clu
>
> 00000E10   74 00 44 72 69 76 65 72  44 61 74 61 00 48 61 6E   t.DriverData.Han
>
> 00000E20   64 6C 65 73 00 4C 69 73  74 00 55 73 65 72 30 00   dles.List.User0.
>
> 00000E30   55 73 65 72 31 00 55 73  65 72 32 00 55 73 65 72   User1.User2.User
>
> 00000E40   33 00 55 73 65 72 34 00  55 73 65 72 35 00 55 73   3.User4.User5.Us
>
> 00000E50   65 72 36 00 55 73 65 72  37 00 55 73 65 72 38 00   er6.User7.User8.
>
> 00000E60   55 73 65 72 39 00 55 73  65 72 31 30 00 55 73 65   User9.User10.Use
>
> 00000E70   72 31 31 00 55 73 65 72  31 32 00 55 73 65 72 31   r11.User12.User1
>
> 00000E80   33 00 55 73 65 72 31 34  00 55 73 65 72 31 35 00   3.User14.User15.
>
> 00000E90   55 73 65 72 31 36 00 55  73 65 72 31 37 00 55 73   User16.User17.Us
>
> 00000EA0   65 72 31 38 00 55 73 65  72 31 39 00 55 73 65 72   er18.User19.User
>
> 00000EB0   32 30 00 55 73 65 72 32  31 00 55 73 65 72 32 32   20.User21.User22
>
> 00000EC0   00 55 73 65 72 32 33 00  55 73 65 72 32 34 00 55   .User23.User24.U
>
> 00000ED0   73 65 72 32 35 00 55 73  65 72 32 36 00 55 73 65   ser25.User26.Use
>
> 00000EE0   72 32 37 00 55 73 65 72  32 38 00 55 73 65 72 32   r27.User28.User2
>
> 00000EF0   39 00 55 73 65 72 33 30  00 55 73 65 72 33 31 00   9.User30.User31.
>
> 
>
> 01.) Bootstrap
>
> 02.) System
>
> 03.) System2
>
> 04.) Static
>
> 05.) MetaData
>
> 06.) String
>
> 07.) NonTracked
>
> 08.) Default
>
> 09.) Fast
>
> 10.) AGP
>
> 11.) VRAM
>
> 12.) Auxiliary
>
> 13.) LongTerm
>
> 14.) MediumTerm
>
> 15.) ShortTerm
>
> 16.) Application
>
> 17.) VisualContext
>
> 18.) ASP
>
> 19.) PPFX
>
> 20.) Effect
>
> 21.) Statistics
>
> 22.) Level
>
> 23.) World
>
> 24.) Actor
>
> 25.) AnimationData
>
> 26.) Geometry
>
> 27.) Vertex
>
> 28.) Image
>
> 29.) ImageObject
>
> 30.) Attribute
>
> 31.) Node
>
> 32.) Physics
>
> 33.) AI
>
> 34.) Audio
>
> 35.) Video
>
> 36.) Temporary
>
> 37.) DMA
>
> 38.) Shader
>
> 39.) RenderList
>
> 40.) Texture
>
> 41.) Clut
>
> 42.) DriverData
>
> 43.) Handles
>
> 44.) List
>
> 45.) User0
>
> 46.) User1
>
> 47.) User2
>
> 48.) User3
>
> 49.) User4
>
> 50.) User5
>
> 51.) User6
>
> 52.) User7
>
> 53.) User8
>
> 54.) User9
>
> 55.) User10
>
> 56.) User11
>
> 57.) User12
>
> 58.) User13
>
> 59.) User14
>
> 60.) User15
>
> 61.) User16
>
> 62.) User17
>
> 63.) User18
>
> 64.) User19
>
> 65.) User20
>
> 66.) User21
>
> 67.) User22
>
> 68.) User23
>
> 69.) User24
>
> 70.) User25
>
> 71.) User26
>
> 72.) User27
>
> 73.) User28
>
> 74.) User29
>
> 75.) User30
>
> 76.) User31
>
> 
>
> Looks like another name index, that may describe later information sections
>
> 
>
> ======================================================================
>
> igGroup
>
> ======================================================================
>
> 
>
> Next, I'm confused there is another table. this may be the actual "igInfoList"
>
> But it falls out of the flow of the data, example the basic structure seemed like
>
> counts,tables,indexes,(size,data), (size,data), (size,data)repeated.. now I have this table that jumps in.
>
> O_O
>
> 
>
> struct INDEX4 { // xCount1
>
> LONG Type // Either 3 or 4
>
> LONG Size
>
> }
>
> 
>
> includes additional data in the loop based on the Size given
>
> 
>
> Example
>
> Code: Select all00000F00   03 00 00 00 14 00 00 00  0C 00 00 00 0F 00 00 00   ................
>
> 00000F10   1E 00 00 00 04 00 00 00  20 00 00 00 0C 00 00 00   ........ .......
>
> 00000F20   04 00 00 00 01 00 00 00  01 00 00 00 FF FF FF FF   ............yyyy
>
> 00000F30   1E 00 00 00 03 00 00 00  14 00 00 00 0C 00 00 00   ................
>
> 00000F40   0A 00 00 00 1E 00 00 00  03 00 00 00 14 00 00 00   ................
>
> 00000F50   0C 00 00 00 11 00 00 00  1E 00 00 00 04 00 00 00   ................
>
> 00000F60   20 00 00 00 0C 00 00 00  0C 00 00 00 01 00 00 00    ...............
>
> 00000F70   01 00 00 00 FF FF FF FF  1E 00 00 00 03 00 00 00   ....yyyy........
>
> 00000F80   14 00 00 00 0C 00 00 00  13 00 00 00 1D 00 00 00   ................
>
> 00000F90   03 00 00 00 14 00 00 00  0C 00 00 00 0D 00 00 00   ................
>
> 00000FA0   1D 00 00 00 03 00 00 00  14 00 00 00 0C 00 00 00   ................
>
> 00000FB0   0E 00 00 00 1E 00 00 00  03 00 00 00 14 00 00 00   ................
>
> 00000FC0   0C 00 00 00 12 00 00 00  1E 00 00 00 03 00 00 00   ................
>
> 00000FD0   14 00 00 00 0C 00 00 00  0D 00 00 00 1E 00 00 00   ................
>
> 
>
> Only 2 Types are seen, type 3 and type 4, info varys depending on which one.
>
> Haven't Figured out was any of it means yet 
>
> 
>
> 1.)
>
> 3, 12, 12, 15, 30
>
> 
>
> 2.)
>
> 4, 24, 12, 4, 1, 1, -1, 30, 
>
> 
>
> 3.)
>
> 3, 12, 12, 10, 30
>
> 
>
> 4.)
>
> 3, 12, 12, 17, 30
>
> 
>
> 5.)
>
> 4, 24, 12, 12, 1, 1, -1, 30
>
> 
>
> 6.)
>
> 3, 12, 12, 19, 29
>
> 
>
> 7.)
>
> 3, 12, 12, 13, 29
>
> 
>
> 8.)
>
> 3, 12, 12, 14, 30
>
> 
>
> 9.)
>
> 3, 12, 12, 18, 30
>
> 
>
> 10.)
>
> 3, 12, 12, 13, 30
>
> 
>
> 
>
> 
>
> 
>
> ======================================================================
>
> igNodeList
>
> ======================================================================
>
> Next back to the size, then data formula
>
> 
>
> LONG Size, LONG Count, SHORT Data
>
> Code: Select all00000FE0   26 00 00 00 0F 00 00 00  02 00 09 00 07 00 01 00
>
> 00000FF0   00 00 09 00 03 00 04 00  08 00 05 00 06 00 05 00
>
> 00001000   06 00 05 00 06 00 04
>
> 
>
> 01.) 2
>
> 02.) 9
>
> 03.) 7
>
> 04.) 1
>
> 05.) 0
>
> 06.) 9
>
> 07.) 3
>
> 08.) 4
>
> 09.) 8
>
> 10.) 5
>
> 11.) 6
>
> 12.) 5
>
> 13.) 6
>
> 14.) 5
>
> 15.) 6
>
> 
>
> gah :'( another index.. getting hard to keep track of em.
>
> 
>
> 
>
> 
>
> ======================================================================
>
> igTransform
>
> ======================================================================
>
> 
>
> the following data resembles that of a matrix, which follows the Name table,
>
> if these are indeed transform.
>
> 
>
> so it can be assumed that the count is the same as the NameTable.
>
> 
>
> LONG Ukn1
>
> Struct {
>
> LONG Count // ?ID?
>
> LONG Size
>
> Matrix
>
> }
>
> 
>
> Data types change between integers and floats?
>
> 
>
> and I can't seem to break it down logically...
>
> like why is there transform information for things in the Name lists.. that were just lists them selves
>
> Like I get that theres a transform for the mesh objects.. but the rest dont need it.
>
> either theres another trick to this, or its just a bad programing practice.
>
> 
>
> past this seems to be RAW data.. some samples I had this is where the file ended O_o
>
> I'm wondering is the files are capible of linking with another relating file?
>
> 
>
> I'm going to be looking at the actual mesh files which contain both texture and geometry.
>
> 
>
> *uPDATE* Confirmed, igb files link to other files. finds file by name, no extension required.
>
> every item in the name list must have an ID for that type of lookup to work
## Post #2
- Username: Julinha
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Sep 15, 2010 9:24 am
- Post datetime: 2011-06-23T18:35:41+00:00
- Post Title: Project Diva 1 & 2 Models (*.IGB)

wow o.o
## Post #3
- Username: BolinhaRedonda
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 10:26 am
- Post datetime: 2011-12-01T16:37:25+00:00
- Post Title: Project Diva 1 & 2 Models (*.IGB)

Wish I could help ):
## Post #4
- Username: BolinhaRedonda
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 10:26 am
- Post datetime: 2012-01-07T12:00:33+00:00
- Post Title: Project Diva 1 & 2 Models (*.IGB)

Hey i dont know if double post is allowed here but i didnt find the rules TT_TT...
I think you should check this out [http://www.cute.or.jp/~makuchan/pce/diva2b.html#igAABox](http://www.cute.or.jp/~makuchan/pce/diva2b.html#igAABox) it might help, im desperate TT_TT
