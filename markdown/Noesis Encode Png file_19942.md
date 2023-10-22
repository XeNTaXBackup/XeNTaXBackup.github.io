## Post #1
- Username: dgl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 28, 2019 1:32 pm
- Post datetime: 2019-04-04T02:55:59+00:00
- Post Title: Noesis Encode Png file?

I'm writing an exporter for Noesis for a model format that uses internal png files to store textures.

```
	def __init__(self, name, width, height, pixelData, pixelType = noesis.NOESISTEX_RGBA32):
		self.name = name
		self.width = width
		self.height = height
		self.pixelData = pixelData
		self.pixelType = pixelType
		self.flags = 0
		self.mipCount = 0
```


I'm guessing the pixel data is the raw RGB or RGBA data. I've been looking through the rapi interface, but can't find what I'm looking for. Is there a way to encode png files through the python API?

Edit:

FML, found it right after posting:

```
data = rapi.imageEncodeRaw(pixelData, width, height, ".png")
```


Another edit:

Found that textures are not included by default on export. This line is needed as well.

```
texList = rapi.loadMdlTextures(mdl)
```


Edit:

I'm getting 0 bytes of output from "data = rapi.imageEncodeRaw(pixelData, width, height, ".png")", is there a code snippet for encoding png's?
