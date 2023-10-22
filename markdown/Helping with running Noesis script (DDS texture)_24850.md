## Post #1
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-12-13T21:46:16+00:00
- Post Title: Helping with running Noesis script (DDS texture)

HI everyone!
I'm little bit new here and I got little problem with using Noesis. 

I need to make some operations with my *dds texture using python script with Noesis. But when I'm trying to open my *dds texture, Noesis only opens it in preview window without any operations. 

Is that any way to run this script in noesis that textures could be edited before preview?
Here is the script:

```

def registerNoesisTypes():
    handle = noesis.register("Some unknown X360 texture", ".dds")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadRGBA(handle, noepyLoadRGBA)
    #noesis.logPopup()
    return 1

def noepyCheckType(data):
    return 1

def noepyLoadRGBA(data, texList):
    bs = NoeBitStream(data)
    dataOffset = 0x180       #set the data offset
    datasize = bs.getSize() - dataOffset
    imgFmt = 1               #set image format (1 - 7)
    imgWidth = 256          #set image width
    imgHeight = 2048          #set image height
    bs.seek(dataOffset, NOESEEK_ABS)
    data = bs.readBytes(datasize)
    #DXT1
    if imgFmt == 1:
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
        texFmt = noesis.NOESISTEX_DXT1
    #DXT3
    elif imgFmt == 2:
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
        texFmt = noesis.NOESISTEX_DXT3
    #DXT5
    elif imgFmt == 3:
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
        texFmt = noesis.NOESISTEX_DXT5
    #DXT5 packed normal map
    elif imgFmt == 4:
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
        data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_ATI2)
        texFmt = noesis.NOESISTEX_RGBA32
    #DXT5 packed normal map2
    elif imgFmt == 5:
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
        data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_ATI1)
        texFmt = noesis.NOESISTEX_RGBA32
    #DXT1 packed normal map
    elif imgFmt == 6:
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
        data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_DXT1NORMAL)
        texFmt = noesis.NOESISTEX_RGBA32
    #raw
    elif imgFmt == 7:
        data = rapi.imageUntile360Raw(data, imgWidth, imgHeight, 4)
        data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "a8r8g8b8")
        texFmt = noesis.NOESISTEX_RGBA32
    #unknown, not handled
    else:
        print("WARNING: Unhandled image format")
        return None
    texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, texFmt))
    return 1
```


Would be so appreciate for the answer
