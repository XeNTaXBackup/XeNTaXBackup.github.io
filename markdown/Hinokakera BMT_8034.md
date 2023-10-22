## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-12T01:40:39+00:00
- Post Title: Hinokakera BMT

```
int16 height
int16 width

pixel data

```


That should be all there is to it lol
But I don't know the pixel format.

Anyone?
[obj.7z](https://xentaxbackup.github.io/file/4978_obj.7z)
## Post #2
- Username: finale00
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-12T02:35:40+00:00
- Post Title: Hinokakera BMT

Pretty straightforward format, though it is a little unusual to store an arbitrarily-sized color palette like that, not to mention the short-sized indices for pixel data. The "self.unk" may be the format type which could dictate a different stride or type of pixel data or something, couldn't tell just from the files you uploaded because the value is 2 for all of them.

```

def registerNoesisTypes():
	handle = noesis.register("BMT Texture", ".bmt")
	noesis.setHandlerTypeCheck(handle, bmtCheckType)
	noesis.setHandlerLoadRGBA(handle, bmtLoadRGBA)
	return 1

BMT_HEADER_SIZE = 11

class BMTFile:
	def __init__(self, bs):
		self.bs = bs

	def parseImageInfo(self):
		bs = self.bs
		if bs.dataSize < BMT_HEADER_SIZE:
			return 0
		bs.seek(0, NOESEEK_ABS)
		if bs.readInt() != 0x5F544D42:
			return 0
		self.width = bs.readUShort()
		self.height = bs.readUShort()
		if self.width <= 0 or self.height <= 0:
			return 0
		self.stride = bs.readUByte()
		self.numColors = bs.readBits(8*self.stride) + 1
		if self.numColors <= 0:
			return 0
		self.clrOfs = bs.tell()
		self.pixOfs = self.clrOfs + self.numColors*4
		return 1

	def convertImage(self):
		bs = self.bs
		bs.seek(self.clrOfs, NOESEEK_ABS)
		clrPal = bs.readBytes(self.numColors*4)
		pix = bytearray()
		for i in range(0, self.width*self.height):
			palOfs = bs.readBits(8*self.stride) * 4
			clr = clrPal[palOfs:palOfs+4]
			pix += clr
		return NoeTexture("bmt_texture", self.width, self.height, pix, noesis.NOESISTEX_RGBA32)

def bmtCheckType(data):
	bmt = BMTFile(NoeBitStream(data))
	if bmt.parseImageInfo() == 0:
		return 0
	return 1

def bmtLoadRGBA(data, texList):
	bmt = BMTFile(NoeBitStream(data))
	if bmt.parseImageInfo() == 0:
		return 0

	tex = bmt.convertImage()
	if tex is not None:
		texList.append(tex)
		return 1
	return 0

```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-12T06:24:26+00:00
- Post Title: Hinokakera BMT

Here's some other textures with a different value for the unk you wrote.

I imagine that unk is significant because the samples I attached all had value 2 (along with other ones I've been looking through) and are loading, but the ones with value 1 aren't.
[obj.7z](https://xentaxbackup.github.io/file/4979_obj.7z)
## Post #4
- Username: finale00
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-12T07:15:05+00:00
- Post Title: Hinokakera BMT

Yeah it was the stride. Updated the script.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-12T07:19:27+00:00
- Post Title: Hinokakera BMT

Texture reversal seems fun.
Should be somewhat easier than 3D models I guess?
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-12T08:07:57+00:00
- Post Title: Hinokakera BMT

Until you run into new image compression or twiddling/tiling schemes that you aren't familiar with, at least. 

Also, in case you intend to actually use/distribute this script with something else you're working on, it's worth noting that you can make the script a lot faster by using the Noesis built-in to combine the palette and pixels instead of doing the logic in Python.

```
		bs = self.bs
		bs.seek(self.clrOfs, NOESEEK_ABS)
		clrPal = bs.readBytes(self.numColors*4)
		pix = rapi.imageDecodeRawPal(bs.readBytes(self.stride*self.width*self.height), clrPal, self.width, self.height, self.stride*8, "r8g8b8a8")
		return NoeTexture("bmt_texture", self.width, self.height, pix, noesis.NOESISTEX_RGBA32)

```
