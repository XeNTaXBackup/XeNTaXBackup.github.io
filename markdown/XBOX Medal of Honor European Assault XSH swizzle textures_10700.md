## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-08-20T00:21:29+00:00
- Post Title: XBOX Medal of Honor European Assault XSH swizzle textures

Some months ago I found the way for extract models and textures from Gamecube version of this game , the models are the same that xbox but the texture quality es low, only on xbox the textures are decent 
but when I tried to convert the xsh to bmp I only obtain swizzle texture in some cases.



searching on internet i found references about a tool called unswizzle_swizzle_FIFA07 that can unswizzle xsh textures but all links are down.

anyone know how to unswizzle the bmp files?

here some fsh files + fshED viewer

[http://www.mediafire.com/download/37sah ... me/fsh.rar](http://www.mediafire.com/download/37sahpi8ulpt8me/fsh.rar)

thanks
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-20T01:40:45+00:00
- Post Title: XBOX Medal of Honor European Assault XSH swizzle textures

if its xbox 1 its most likely morton order.
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-08-20T02:55:58+00:00
- Post Title: XBOX Medal of Honor European Assault XSH swizzle textures

> Reply from chrrox
>
> if its xbox 1 its most likely morton order.

I can't find any tool for fix the texture under morton order,only algorithms.
you know any tool?
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-09-02T01:18:22+00:00
- Post Title: XBOX Medal of Honor European Assault XSH swizzle textures

I watched the textures from PS2 they are in *.SSH format and the files are the same that xbox version (same resolution) , but all files are compressed.

there are a way for decompress ps2 textures?

Electronic Arts Graphics Tools v0.1.0 can read *.SSH files but when I tried to load the textures the result is error.
## Post #5
- Username: Scoundrels
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 12, 2022 8:27 am
- Post datetime: 2022-01-12T00:32:46+00:00
- Post Title: XBOX Medal of Honor European Assault XSH swizzle textures

good night, I have a question. Where are the textures and models of Medal of Honor European Assault and how can I extract them? I want your answer, I also want to know what program I should use. I thank you all
## Post #6
- Username: jaygee243
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 25, 2023 10:16 am
- Post datetime: 2023-09-05T23:34:56+00:00
- Post Title: XBOX Medal of Honor European Assault XSH swizzle textures

I am also interested in progress on this one.

Solved this piece of the puzzle: QuickBMS code for ripping textures in .FSH format below. The streaming data archives "level_a.str" contain the level assets. As others have said, many of the larger textures (512x512 and up) are swizzled. Surprisingly, many of them are not. You can load like 85% of them without issue. I still haven't found a way to un-swizzle the larger ones though. I can confirm these can be opened in fshed and converted to PNG.

(Orginal code template by Bartlomiej Duda (Ikskoks) )

```
	FindLoc SIGN_OFFSET STRING "SHPX"
	if SIGN_OFFSET == ""
		cleanexit
	endif
	goto SIGN_OFFSET
	GetDString SIGN 4
	get TOTAL_SIZE long
	XMATH F_COUNT "i+1"
	set F_OUT_NAME string "file"
	string F_OUT_NAME += F_COUNT
	string F_OUT_NAME += ".fsh"
	log F_OUT_NAME SIGN_OFFSET TOTAL_SIZE
next i
```
## Post #7
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2023-09-08T16:29:11+00:00
- Post Title: XBOX Medal of Honor European Assault XSH swizzle textures

Here is solution... 
rewriten bms to dump textures from archives without names:

```

for
	FindLoc SHPXOffset string "\x53\x48\x50\x58"
	if SHPXOffset == ""
		cleanexit
	endif
	goto SHPXOffset
	getdstring Dummy 0x4
	get FileSize long
	string Name p= "%s/%x08.xsh" FileName SHPXOffset
	log Name SHPXOffset FileSize
next
```


And Noesis python script which covers some of formats:

```
import noesis
import rapi
import os

def registerNoesisTypes():
   handle = noesis.register("Medal of Honor European Assault - Texture", ".xsh")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadRGBA(handle, noepyLoadRGBA)
   noesis.logPopup()
   return 1
        
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 20:
      return 0
   if bs.readUInt() != 0x58504853:
      return 0
   return 1
   
def noepyLoadRGBA(data, texList):
	bs = NoeBitStream(data)
	baseName = rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getInputName()))
	bs.readBytes(112)
	PixelFormatFlag = bs.readUByte()
	bs.readBytes(3)
	TexWidth = bs.readUShort()
	TexHeight = bs.readUShort()
	bs.readBytes(8)
	
	if PixelFormatFlag == 123:
		bs.TexSize = TexWidth * TexHeight
		data = bs.readBytes(bs.TexSize)
		bs.readBytes(56)
		PalColors = bs.readUInt() * 4
		bs.readBytes(4)
		Palette = bs.readBytes(PalColors)
		bs.Palette = Palette
		data = rapi.imageDecodeRawPal(data, bs.Palette, TexWidth, TexHeight, 8, "b8 g8 r8 a8")
		data = rapi.imageFromMortonOrder(data, TexWidth, TexHeight, 4)
		texFmt = noesis.NOESISTEX_RGBA32
		
	bs.seek(0x80, NOESEEK_ABS)
	if PixelFormatFlag == 96:
		bs.TexSize = TexWidth * TexHeight // 2
		data = bs.readBytes(bs.TexSize)
		texFmt = noesis.NOESISTEX_DXT1
	elif PixelFormatFlag == 97:
		bs.TexSize = TexWidth * TexHeight
		data = bs.readBytes(bs.TexSize)
		texFmt = noesis.NOESISTEX_DXT3
	elif PixelFormatFlag == 125:
		bs.TexSize = TexWidth * TexHeight * 4
		data = bs.readBytes(bs.TexSize)
		data = rapi.imageDecodeRaw(data, TexWidth, TexHeight, "b8 g8 r8 a8")
		data = rapi.imageFromMortonOrder(data, TexWidth, TexHeight, 4)
		texFmt = noesis.NOESISTEX_RGBA32
	texList.append(NoeTexture(rapi.getInputName(), TexWidth, TexHeight, data, texFmt))
	return 1
```
## Post #8
- Username: jaygee243
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 25, 2023 10:16 am
- Post datetime: 2023-09-09T11:43:52+00:00
- Post Title: XBOX Medal of Honor European Assault XSH swizzle textures

^^ Dude. This worked BEAUTIFULLY! I just needed to delete the word "top" at the end of the script. Knocked it out of the park on this one. Thank you so much!!
