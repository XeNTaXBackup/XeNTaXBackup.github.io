## Post #1
- Username: TFM
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 02, 2010 3:52 pm
- Post datetime: 2010-11-02T17:39:03+00:00
- Post Title: Perfect Dark Zero

Anyone bothered extracting models from this game? Especially Joanna and that other crazy chick, don't remember her name... stupid game   Oh well. Any takers?
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-11-02T20:00:36+00:00
- Post Title: Perfect Dark Zero

used luigi's offzip program to extract the compressed files. the problem is that the files are just raw dumps with hex addresses as names. Thousands of them! it doesnt help that PDZ already has cryptic file names. I think the file names are all hash numbers to begin with, its just a pain to locate model data
## Post #3
- Username: TFM
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 02, 2010 3:52 pm
- Post datetime: 2010-11-03T06:46:52+00:00
- Post Title: Perfect Dark Zero

Thanks, good to know, no need for false hopes then!
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-03-13T04:30:11+00:00
- Post Title: Perfect Dark Zero

Bump!

I was doing some work on this old game, I'm just going to post up a maxscript I wrote tonight.
the format seems soo crazy I'm not sure if i'll continue with it, I'm having alot of trouble cutting through the file structure 

On the disk you'll find a folder called PackageData, inside are PKG files, use luigi's offzip program to unpack them, they are zlib
[http://aluigi.altervista.org/mytoolz/](http://aluigi.altervista.org/mytoolz/)

I used a simple BAT script to unpack everything

```
offzip.exe -a %%1 . 0
REN "00000000.caf" %%~n1.caf
::DEL %%1
)

```


after unpacking you'll get CAF files, from what I gather the CAF files are resource containers.
they do hold models, textures etc but much more. the CAF holds alot of "XML" references, so I'm expecting some sort of element structure

here's my maxscript, all it does is work into the package. no models yet, NCDyson was working on it, but he wasn't able to locate the UVs

```


fsource = "D:\\MaxScripts\\PerfectDarkZeroo\\00000000.caf"
fsource = "D:\\MaxScripts\\PerfectDarkZeroo\\darkcharacter.bin"
fsource = "D:\\MaxScripts\\PerfectDarkZeroo\\PackageData\\1154195372.caf"




fn ReadBEfloat fstream = (
bit.intAsFloat (bit.swapBytes (bit.swapBytes (readlong fstream #unsigned) 1 4) 2 3)
)
fn ReadBElong fstream = (
bit.swapBytes (bit.swapBytes (readlong fstream #unsigned) 1 4) 2 3
)
fn readBEHalfFloat fstream = (
hf=bit.swapBytes (readshort fstream #unsigned) 1 2
sign = bit.get hf 16
exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
fraction = bit.and hf (bit.hexasint "03FF")
if sign==true then sign = 1 else sign = 0
exponentF = exponent + 127
outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
(bit.shift exponentF 23)) (bit.shift sign 31)
return bit.intasfloat outputasfloat*2)
fn ReadBEshort fstream = (
(bit.swapBytes (readshort fstream #unsigned) 1 2)
)
fn getpadding num alignment = ((mod (alignment-(mod num alignment)) alignment))



if ((doesFileExist fsource)==true) then ( 
delete $*
f = fopen fsource "rb"

-- fseek f 0x1C3D988 #seek_set

-- count = 2000

-- vertArray = #()
-- uvwArray = #()
-- faceArray = #()
struct darkheader (res)
struct darkshit (flag,name,cnt1,cnt2,size,ukn1,ukn2,ukn3,ukn4,size2)

darkArray = (darkheader \
	res:(darkshit \
		flag:#() \
		name:#() \
		cnt1:#() \
		cnt2:#() \
		size:#() \
		ukn1:#() \
		ukn2:#() \
		ukn3:#() \
		ukn4:#() \
		size2:#() \
		)
	)

cafid = readstring f;format "%\n\n" cafid
fseek f 0x14 #seek_set -- weird padding?
ukn001 = readBElong f -- hash?
ukn002 = readBElong f -- count
ukn003 = readBElong f -- count
ukn004 = readBElong f
ukn005 = readBElong f
ukn006 = readBElong f
ukn007 = readBElong f
ukn008 = readBElong f
ukn009 = readBElong f -- offsets to a string list of external packages to include
ukn010 = readBElong f -- offsets to resource start
ukn011 = readbyte f #unsigned
ukn012 = readbyte f #unsigned -- count
ukn013 = readbyte f #unsigned
ukn014 = readbyte f #unsigned



for i = 1 to ukn012 do (
darkArray.res.flag[i] = readbyte f #unsigned -- always 0x2E?
darkArray.res.name[i] = readstring f
fseek f (getpadding (ftell f) 8) #seek_cur
darkArray.res.cnt1[i] = readBElong f
darkArray.res.cnt2[i] = readBElong f
darkArray.res.size[i] = readBElong f
darkArray.res.ukn1[i] = readBElong f
darkArray.res.ukn2[i] = readBElong f
darkArray.res.ukn3[i] = readBElong f
darkArray.res.ukn4[i] = readBElong f
darkArray.res.size2[i] = readBElong f
)

res_start = ukn010
for res = 1 to ukn012 do (
format "% @ 0x%\n" darkArray.res.name[res] ((bit.intAsHex(res_start))as string)
fseek f res_start #seek_set
case darkArray.res.name[res] of (
"data":(
darkpkg = readstring f
fseek f (getpadding (ftell f) 16) #seek_cur
if darkpkg == "darkpackage" then (
darkpkg_version = readBElong f
fseek f (getpadding (ftell f) 16) #seek_cur

offsetTable = #()
ukn015 = readBElong f
for i = 1 to ukn015 do (
ukn01 = readBElong f
ukn02 = readBElong f
ukn03 = readBElong f
ukn04 = readBElong f
ukn05 = readBElong f
ukn06 = readBElong f
ukn07 = readBElong f
ukn08 = readBElong f
if ukn01!=0 do (ukn01+=res_start)
if ukn02!=0 do (ukn02+=res_start)
offsetTable[i] = [ukn01,ukn02]
)

struct name_table (name,ext,fpath)
stringTable = (name_table name:#() ext:#() fpath:#())


for i = 1 to ukn015 do (
fseek f offsetTable[i][1] #seek_set
stringTable.name[i]=readstring f
fseek f (getpadding (ftell f) 8) #seek_cur
)


for i = 1 to ukn015 do (
if offsetTable[i][2]!=0 then (
format "%\n\t@ 0x%\n" stringTable.name[i] ((bit.intAsHex(offsetTable[i][2]))as string)
fseek f offsetTable[i][2] #seek_set
ukn016 = readstring f
fseek f (getpadding (ftell f) 4) #seek_cur
if ukn016 == "xml" then (
ukn017 = readBElong f
ukn018 = readBElong f
ukn019 = readBElong f
ukn020 = readBElong f
ukn021 = readBElong f
ukn022 = readBElong f
ukn023 = readBElong f
ukn024 = readBElong f -- count
ukn025 = readstring f
fseek f (getpadding (ftell f) 4) #seek_cur
format "XML: %\n" ukn025
ukn025b = ftell f
for x = 1 to ukn024 do (
ukn026 = readBElong f
ukn027 = (readBElong f) + (ftell f) + 4
ukn028 = readBElong f
ukn029 = readBElong f
ukn030 = readBElong f
ukn031 = readBElong f
fseek f ukn027 #seek_set
ukn032 = readstring f
fseek f (getpadding (ftell f) 4) #seek_cur
ukn033 = readBElong f
ukn034 = readBElong f -- should be -1
format "File(%): %\n" x ukn032
)
)else(format "! New: %\n" ukn016)

format "Data Errrnded @ 0x%\n" ((bit.intAsHex(ftell f))as string)


)
)



format "Data Ended @ 0x%\n" ((bit.intAsHex(ftell f))as string)
)else(print "not darkpackage?")
) -- End of Data Block
"gpu":(

) -- End of Texture Block
"stream":(

) -- End of Stream Block
default:(format "! New Data Block: %\n" darkArray.res.name[res])
)
res_start +=darkArray.res.size[res]
)


format "Last Read @ 0x%\n\n\nDone!\n" ((bit.intAsHex(ftell f))as string)
fclose f
) else (Print "Aborted.")

```
## Post #5
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-13T16:09:10+00:00
- Post Title: Perfect Dark Zero

i don't know if this concerns this, but actually Is Kameo the same format as this?? actually both games were developed by rare.
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-06-14T11:30:38+00:00
- Post Title: Perfect Dark Zero

So is there still no surefire way to get the UV's fixed?
