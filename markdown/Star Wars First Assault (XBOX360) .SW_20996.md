## Post #1
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2019-08-19T10:49:20+00:00
- Post Title: Star Wars: First Assault (XBOX360) .SW

Hello all,
  I've extracted all the .sw textures from Star Wars: First Assault but I'm only able to successfully convert some of the textures, mainly the larger ones (1024x1024 and 2048x2048). It crashes when trying to read most of the smaller textures (512x512 and 256x256) and also fails to de-swizzle a lot of them. I was hoping someone could modify or fix the script to successfully read all of the textures. I don't know how to script with python or I would do it myself. I'm missing a lot of the needed textures for the higher poly game models since the script won't properly convert them. Any help would be appreciated, thanks!

```

def registerNoesisTypes():
	handle = noesis.register("Xbox swizzled texture", ".sw")
	noesis.setHandlerTypeCheck(handle, noeCheckGeneric)
	noesis.setHandlerLoadRGBA(handle, MUA2LoadRGBA)
	#noesis.logPopup()
	return 1

def MUA2LoadRGBA(data, texList):
    datasize = len(data)
    bs = NoeBitStream(data)
    #bs.seek(0x1000, NOESEEK_ABS)
    data = bs.readBytes(datasize)

    if datasize == 4194304:
        imgWidth = 2048
        imgHeight = 2048
        texFmt = noesis.NOESISTEX_DXT5
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
    elif datasize == 2097152:
        imgWidth = 2048
        imgHeight = 2048
        texFmt = noesis.NOESISTEX_DXT1
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
    elif datasize == 1048576:
        imgWidth = 1024
        imgHeight = 1024
        texFmt = noesis.NOESISTEX_DXT5
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
    elif datasize == 524288:
        imgWidth = 1024
        imgHeight = 1024
        texFmt = noesis.NOESISTEX_DXT1
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
    elif datasize == 262144:
        imgWidth = 512
        imgHeight = 512
        texFmt = noesis.NOESISTEX_DXT5
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
    elif datasize == 131072:
        imgWidth = 512
        imgHeight = 512
        texFmt = noesis.NOESISTEX_DXT1
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
    else:
        imgWidth = 256    # 45k
        imgHeight = 256
        texFmt = noesis.NOESISTEX_DXT1
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
    #normal
    #imgHeight = 512
    #imgWidth = 512
    #data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
    #data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_ATI2)
    #texFmt = noesis.NOESISTEX_RGBA32
    texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, texFmt))
    return 1

```

I can provide the entire collection of textures if needed but here are just some of the textures I'm struggling with:
Texture samples: [http://www.mediafire.com/file/ph6w6t34s ... s.zip/file](http://www.mediafire.com/file/ph6w6t34sayppez/Star_Wars_First_Assault_SW_Texture_Samples.zip/file)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-24T01:57:07+00:00
- Post Title: Star Wars: First Assault (XBOX360) .SW

your samples are headerless, you must guess width, height and format
and set that in your script accordingly, or find a better way to extract the
textures along with their header info so no need to guess.
