## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-15T06:52:46+00:00
- Post Title: Love Hina: Smile Again (Dreamcast) .pac images

Noesis recently got support for LH:SA .pac models, but a lot of the sprites and static images in the game are also in .pac files that Noesis can't really easily recognize because they contain no distinct headers and the file extension is totally generic. So here's a script to load them.

```

def registerNoesisTypes():
	handle = noesis.register("Love Hina Hack", ".pac")
	noesis.setHandlerTypeCheck(handle, noeCheckGeneric)
	noesis.setHandlerLoadRGBA(handle, hinaLoadRGBA)
	return 1

def hinaLoadRGBA(data, texList):
	bs = NoeBitStream(data)
	numOfs = bs.readInt()
	ofsInfos = bs.read("<" + "i"*numOfs*2)
	for i in range(0, numOfs):
		bs.seek(ofsInfos[i*2])
		width = bs.readInt()
		height = bs.readInt()
		if width < 8 or width > 1024 or height < 8 or height > 1024:
			continue
		fmt = bs.readInt()
		fmtStr = "b5g5r5a1" if fmt == 2 else "b4g4r4a4"
		pix = rapi.imageDecodeRaw(bs.readBytes(width*height*2), width, height, fmtStr)
		texList.append(NoeTexture("hinatex", width, height, pix, noesis.NOESISTEX_RGBA32))
	return 1

```


I don't recommend leaving the script in your scripts folder because it overrides all .pac files and has no data integrity check.
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-09-08T12:15:07+00:00
- Post Title: Love Hina: Smile Again (Dreamcast) .pac images

I've been feeling nostalgic lately and looking back on nostalgic games.

The BACKGROUND directory *.BIN's for this game contains in-game CG pictures, but can't open them with Noesis.
However, the format is the same as pac.

02 00 00 00 14 00 00 00 24 00 00 00 38 00 00 00 0C 00 08 00 00 00 00 00 00 00 C0 42 00 00 F0 41 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00

Just add it to the header in the hex editor and save it with pac. We can now open it.
[EV_S20_8out.jpg](https://xentaxbackup.github.io/file/20747_EV_S20_8out.jpg)
