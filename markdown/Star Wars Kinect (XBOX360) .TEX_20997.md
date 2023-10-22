## Post #1
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2019-08-19T11:51:23+00:00
- Post Title: Star Wars Kinect (XBOX360) .TEX

Hello,
I've been using a Noesis python script to extract the game's textures but I'm having an issue with the displayed image dimensions when viewing the .tex files. I've mostly been using the game's .tga texture files with no problems but I've noticed the .tex files seem to include some higher resolution textures and it would be nice to properly extract these! This might be due to the .tex files being containers rather than just textures but I don't really know for sure. Here is an example of what is displayed in Noesis when viewing the .tga and .tex files respectively:

Here are the .tex file samples:
[http://www.mediafire.com/file/4lqbkmr3g ... s.zip/file](http://www.mediafire.com/file/4lqbkmr3gq47qtb/Star_Wars_Kinect_TEX_Texture_Samples.zip/file)
Noesis python script:

```

def registerNoesisTypes():
	handle = noesis.register("Star Wars Kinect TEX", ".tex")
	noesis.setHandlerTypeCheck(handle, StarWarsKinectCheckType)
	noesis.setHandlerLoadRGBA(handle, StarWarsKinectLoadRGBA)
	return 1

def StarWarsKinectCheckType(data):
	bs = NoeBitStream(data)
	Magic = bs.readInt()
	if Magic != 8:
		return 0
	return 1   

def StarWarsKinectLoadRGBA(data, texList):
	datasize = len(data) - 0x34
	bs = NoeBitStream(data)
	bs.seek(0x18, NOESEEK_ABS)
	imgFmt = bs.readInt()
	imgWidth = bs.readInt() // 2
	imgHeight = bs.readInt() // 2
	if imgHeight == 2:
		imgHeight = 4
	data01 = bs.readInt()
	data02 = bs.readInt()
	bs.seek(0x34, NOESEEK_ABS)
	data = bs.readBytes(datasize)
	#DXT1
	if imgFmt == 0x28:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
		texFmt = noesis.NOESISTEX_DXT1
	#DXT5
	elif imgFmt == 0x33:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
		texFmt = noesis.NOESISTEX_DXT5
	#DXT5 packed normal map
	elif imgFmt == 0x1C:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
		data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_ATI2)
		texFmt = noesis.NOESISTEX_RGBA32
	#DXT5 packed normal map2
	elif imgFmt == 0x36:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
		data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_ATI1)
		texFmt = noesis.NOESISTEX_RGBA32
	#DXT1 packed normal map
	elif imgFmt == 0x16:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
		data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_DXT1NORMAL)
		texFmt = noesis.NOESISTEX_RGBA32
	#raw
	elif imgFmt == 0x1B:
		data = rapi.imageUntile360Raw(rapi.swapEndianArray(data, 4), imgWidth, imgHeight, 4)
		texFmt = noesis.NOESISTEX_RGBA32
	#unknown, not handled
	else:
		print("WARNING: Unhandled image format " + repr(imgFmt) + " - " + repr(imgWidth) + "x" + repr(imgHeight) + " - " + repr(len(data)))
		return None
	texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, texFmt))
	return 1
```
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-24T02:37:37+00:00
- Post Title: Star Wars Kinect (XBOX360) .TEX

try this 


 tex_SWKinect_X360_tga_tex.zip
(877 Bytes) Downloaded 48 times
## Post #3
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2019-12-15T01:04:51+00:00
- Post Title: Star Wars Kinect (XBOX360) .TEX

Thank you Acewell, your script works great!
