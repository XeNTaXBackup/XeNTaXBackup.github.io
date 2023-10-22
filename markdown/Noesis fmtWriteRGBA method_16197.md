## Post #1
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2017-04-25T09:13:38+00:00
- Post Title: Noesis fmtWriteRGBA method

I am trying to generate a file with Noesis from a PNG file.

So, I load a PNG file with Noesis, and I try to export it to my own format
The next code is launched.

```
	datasize = len(data)
	print(datasize)
	image = rapi.imageEncodeRaw(data, width, height, "r8g8b8a8")
	datasize = len(image)
	print(datasize)
	bsOut = NoeBitStream(image)
	return 1

```


My doubt is, datasize is not null, but when I do 
bsOut = NoeBitStream(image) or bsOut = NoeBitStream(data)
noesis generates a 0bytes file with of course 0 len.

How can I export this PNG file?
## Post #2
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2017-04-25T13:12:45+00:00
- Post Title: Noesis fmtWriteRGBA method

Got it

```
mipData = rapi.imageResample(data, width, height, width, height)
bsOut.writeBytes(mipData)

```


this write the previous png to bytearray file
