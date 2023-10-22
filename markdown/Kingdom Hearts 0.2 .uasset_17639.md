## Post #1
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-01-31T17:20:55+00:00
- Post Title: Kingdom Hearts 0.2 *.uasset

KH 0.2 works fine with UModel for models, however the textures display wrong. I don't know if this is a case of it being a PS4 specific format like GNF that UModel can't read or some other issue, but the uassets can be exported from UModel at least. I don't know much about textures so some assistance would be appreciated for this, thanks!
[http://www112.zippyshare.com/v/uMmmTjBw/file.html](http://www112.zippyshare.com/v/uMmmTjBw/file.html)
## Post #2
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-02-01T11:02:09+00:00
- Post Title: Kingdom Hearts 0.2 *.uasset

DDS versions extracted from umodel, in case this is any help, don't know much about swizzling but it could be that.
[http://www44.zippyshare.com/v/yTYSnZCJ/file.html](http://www44.zippyshare.com/v/yTYSnZCJ/file.html)
## Post #3
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2018-02-07T12:33:38+00:00
- Post Title: Kingdom Hearts 0.2 *.uasset

how did you unpack the PKG?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-07T20:07:47+00:00
- Post Title: Kingdom Hearts 0.2 *.uasset

> Reply from TRDaz
>
> DDS versions extracted from umodel, in case this is any help, don't know much about swizzling but it could be that.
http://www44.zippyshare.com/v/yTYSnZCJ/file.html

just posting a solution in case others find your thread   
use the instruction here to convert the dds headers to gnf headers with the bms script then open the gnf files with Noesis. 
[http://www.gildor.org/smf/index.php?PHP ... 1#msg26641](http://www.gildor.org/smf/index.php?PHPSESSID=7ae13b8feced0820cad554e7856a1235&topic=5999.msg26641#msg26641)

local copy of post:

> Reply from chrrox
>
> here is a bms script to convert these textures to ps4 sdk format.
use umodel to export the textures with the -dds option.
then run this quickbms script on them to convert them to ps4 sdk format.
Code: Select allget NAME basename
string NAME += _fixed
string NAME += .gnf
goto 0xC
get WIDTH long
get HEIGHT long
get SIZE long
set SIZE2 SIZE
math SIZE2 + 0x30
goto 0x54
getdstring TYPE 4
set MEMORY_FILE binary "\x47\x4E\x46\x20\x28\x00\x00\x00\x02\x01\x00\x00\x30\x00\x10\x00\x00\x00\x00\x00\x01\x00\x50\x92\xFF\xC3\xFF\x70\xAC\x0F\xD0\xA4\x01\xE0\x7F\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00"
math WIDTH - 1
math WIDTH + 0xC000
math HEIGHT - 1
math HEIGHT > 2
math HEIGHT + 0x7000
print "%HEIGHT%"
putVarChr MEMORY_FILE 0X1A HEIGHT short
putVarChr MEMORY_FILE 0x18 WIDTH short
putVarChr MEMORY_FILE 0xC SIZE2 long
putVarChr MEMORY_FILE 0x2C SIZE long
if TYPE == "DXT1"
    putVarChr MEMORY_FILE 0x16 0x30 BYTE
    putVarChr MEMORY_FILE 0x17 0x92 BYTE
elif TYPE == "DXT5"
    putVarChr MEMORY_FILE 0x16 0x50 BYTE
    putVarChr MEMORY_FILE 0x17 0x92 BYTE
elif TYPE == "ATI2"
    putVarChr MEMORY_FILE 0x16 0x70 BYTE
    putVarChr MEMORY_FILE 0x17 0x92 BYTE
endif

append
log MEMORY_FILE 0x80 SIZE
append

log NAME 0 SIZE2 MEMORY_FILE
