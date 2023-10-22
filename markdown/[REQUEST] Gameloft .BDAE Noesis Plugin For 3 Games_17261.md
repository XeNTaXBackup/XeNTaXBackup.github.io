## Post #1
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2017-11-07T08:15:31+00:00
- Post Title: [REQUEST] Gameloft .BDAE Noesis Plugin For 3 Games

I've been trying all afternoon to create my own Noesis plugin, to no avail so I was wondering if anyone would be able / willing to create plugin for:

Batman: Dark Knight Rises;
Captain America: The Winter Soldier;
Disney Magic Kingdom;

I know that there is a script available for 3DS Max, but I don't have it and I doubt it would run properly with my current configuration ( Which is next Gen abso-shitty box ). Acewell created a script for Spider-Man: Unlimited which isn't compatible with these models, so hopefully someone can quickly update it to support these three titles. I've uploaded samples of each title to my Drive account: [https://drive.google.com/open?id=0B2nb4 ... Wd0aktkV2c](https://drive.google.com/open?id=0B2nb4mY93-PXZHJIbWd0aktkV2c)

Acewell's Original script:

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("Spider-Man Unlimited", ".bdae")    #change this extension
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

def noepyCheckType(data):
    bs = NoeBitStream(data)
    Magic = bs.readBytes(4).decode("ASCII")
    print(Magic, ":magic")
    if Magic != "BRES":
        return 0
    ByteOrderMark = bs.readShort()
    padding = bs.readShort()
    version = bs.readInt()
    print(version, ":version")
    if version != 64: #32, 60, 64
        return 0
    return 1   

def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    rapi.setPreviewOption("setAngOfs","0 270 0")  #set the default preview angle        
    bs = NoeBitStream(data)
    myString = bs.readBytes(len(data))
    myIndex = myString.find(b"\x30\x2C\x30\x2C\x30\x2C")
    print(hex(bs.tell()), ":here 1")
    bs.seek(myIndex - 0xc, NOESEEK_ABS)
    print(hex(bs.tell()), ":here 2")
    start = bs.readInt()
    print(hex(start), ":start")
    bs.seek(start + 0x8, NOESEEK_ABS)
    print(hex(bs.tell()), ":here 3")
    jumpToFC = bs.readInt()
    TMP = bs.getOffset()
    print(hex(TMP), ":TMP")
    bs.seek(0x8, NOESEEK_REL)
    VCount = bs.readInt()
    print(hex(VCount), ":VCount")
    if VCount == 0:
        skip = bs.readInt()
        print(hex(bs.tell()), ":before VCount") 
        VCount = bs.readInt()
        print(hex(VCount), ":VCount final")
    bs.seek(0x30, NOESEEK_REL)
    VOffset = bs.readInt()
    print(hex(VOffset), ":VOffset")
    bs.seek(0x3c, NOESEEK_REL)
    VBytes = bs.readInt()                                
    print(hex(VBytes), ":VBytes")
    bs.seek(TMP + jumpToFC + 0x18, NOESEEK_ABS) #d8 
    print(hex(bs.tell()), ":here 4") 
    FCount = bs.readInt()
    print(hex(FCount), ":FCount")
    bs.seek(0xc, NOESEEK_REL)
    FIOffset = bs.readInt()
    bs.seek(VOffset, NOESEEK_ABS)
    VBuf = bs.readBytes(VCount * VBytes)
    rapi.rpgBindPositionBufferOfs(VBuf, noesis.RPGEODATA_FLOAT, VBytes, 0)   #position of vertices
    rapi.rpgBindNormalBufferOfs(VBuf, noesis.RPGEODATA_FLOAT, VBytes, 12)   #normals -optional
    rapi.rpgBindUV1BufferOfs(VBuf, noesis.RPGEODATA_FLOAT, VBytes, 24)   #UV1
    IBuf = bs.readBytes(FCount * 2)                       #multiply by 2 for word, 4 for dword indices 
    checkTri = int(FCount % 3)                            #check if FCount is evenly divisible by 3
    if checkTri == 0:
        rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_SHORT, FCount, noesis.RPGEO_TRIANGLE, 1)
    else:
        rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_SHORT, FCount, noesis.RPGEO_TRIANGLE_STRIP, 1) 
    mdl = rapi.rpgConstructModel()                                                          
    mdlList.append(mdl)
    rapi.rpgClearBufferBinds()
    return 1
```
## Post #2
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2017-11-11T01:41:44+00:00
- Post Title: [REQUEST] Gameloft .BDAE Noesis Plugin For 3 Games

Just bumping this, in the hopes that someone will help!
## Post #3
- Username: Honorsoft
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 25, 2021 3:55 am
- Post datetime: 2022-09-09T04:09:16+00:00
- Post Title: [REQUEST] Gameloft .BDAE Noesis Plugin For 3 Games

I'd also like to get a Noesis script for BDAE, specifically for "Iron Man 3", please and thank you.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-09T07:40:05+00:00
- Post Title: [REQUEST] Gameloft .BDAE Noesis Plugin For 3 Games

> Reply from Honorsoft ↑Fri Sep 09, 2022 12:09 pm at Fri Sep 09, 2022 12:09 pm
>
> 
I'd also like to get a Noesis script for BDAE, specifically for "Iron Man 3", please and thank you.Why bump dead threads?
What about this one:

> Reply from Durik256 ↑Sat Sep 03, 2022 6:32 am at Sat Sep 03, 2022 6:32 am
>
>
