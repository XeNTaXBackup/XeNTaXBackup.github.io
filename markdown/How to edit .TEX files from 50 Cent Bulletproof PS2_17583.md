## Post #1
- Username: TjVatio
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 13, 2017 12:50 pm
- Post datetime: 2018-01-20T01:58:22+00:00
- Post Title: How to edit .TEX files from 50 Cent Bulletproof PS2

So, basically i want to convert this format to any  image to modify and re convert to .TEX

tried some tools around the web and only texture finder give me some result.

TextureFinder preview.


TEX file samples
[http://www.mediafire.com/file/cb86158u7 ... GAL_EN.TEX](http://www.mediafire.com/file/cb86158u7zsa9t0/LEGAL_EN.TEX)
[http://www.mediafire.com/file/nro1nafpt ... GRBRDR.TEX](http://www.mediafire.com/file/nro1nafpt3j515j/PGRBRDR.TEX)
[http://www.mediafire.com/file/q6lbrgofajblh4f/FAIL.TEX](http://www.mediafire.com/file/q6lbrgofajblh4f/FAIL.TEX)

Thankies!!
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-20T05:18:48+00:00
- Post Title: How to edit .TEX files from 50 Cent Bulletproof PS2

LEGAL_EN.png (98.46 KiB) Viewed 241 times


all 3 samples use the same settings 
i've never done a Noesis python script for ps2 images but i may give it a try later.
## Post #3
- Username: TjVatio
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 13, 2017 12:50 pm
- Post datetime: 2018-01-20T18:14:58+00:00
- Post Title: How to edit .TEX files from 50 Cent Bulletproof PS2

> Reply from AceWell
>
> LEGAL_EN.png
all 3 samples use the same settings 
i've never done a Noesis python script for ps2 images but i may give it a try later.

OMG!!! thank you so much, that program works like a charm , actually ive downloaded noesis and loaded some scripts from forum but none of them working in this .TEX, maybe was only for a specific game that already posted  

edit: i got lost to convert back my edited image to .TEX, i have to use the same program?

once again thank you for helping me!!!
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-21T01:49:49+00:00
- Post Title: How to edit .TEX files from 50 Cent Bulletproof PS2

> Reply from TjVatio
>
> so, i got lost to convert back my edited image to .TEX, i have to use the same program?
no, you have to break it back down to paletted data and retwiddle to rebuild it, i can't help with this.
i tried making a Noesis python script to open the TEX files but i can't get the result like the one in "Console Texture Explorer".
## Post #5
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-01-21T18:48:59+00:00
- Post Title: How to edit .TEX files from 50 Cent Bulletproof PS2

> Reply from AceWell
>
> TjVatio wrote:so, i got lost to convert back my edited image to .TEX, i have to use the same program?
no, you have to break it back down to paletted data and retwiddle to rebuild it, i can't help with this.
i tried making a Noesis python script to open the TEX files but i can't get the result like the one in "Console Texture Explorer".

i don't like sad pals. you forgot something.  i borrowed some code from [there](http://zenhax.com/viewtopic.php?f=7&t=7053) and unshuffled this bitch, ps2 style.  you gotta do the pointer dance. 

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("50cent Bulletproof TEX Textures", ".tex")
	noesis.setHandlerTypeCheck(handle, TEXCheckType)
	noesis.setHandlerLoadRGBA(handle, TEXLoadRGBA)
	#noesis.logPopup()
	return 1

def TEXCheckType(data):
	return 1

def TEXLoadRGBA(data, texList):
	bs = NoeBitStream(data)
	filename = bs.read("32B")
	hash = bs.readInt()
	width = bs.readUShort()
	height = bs.readUShort()
	#dummy1 = bs.readUByte()
	size_bmapdata = width * height #bs.readUInt()
	#print(str(size_bmapdata))
	#dummy2 = bs.readUByte()
	#ofs_palette = bs.readUInt()
	bs.seek(0x40, NOESEEK_ABS)
	texData = bs.readBytes(size_bmapdata)
	#bs.seek(ofs_palette + 0x40, NOESEEK_ABS)
	palData = []
	for x in range(8):
		for p in range(32):
			read = bs.readUByte()
			palData.append(read)
		bs.seek(32, NOESEEK_REL)
		for p in range(32):
			read = bs.readUByte()
			palData.append(read)
		bs.seek(-64, NOESEEK_REL)
		for p in range(32):
			read = bs.readUByte()
			palData.append(read)
		bs.seek(32, NOESEEK_REL)
		for p in range(32):
			read = bs.readUByte()
			palData.append(read)

	palData = bytearray(palData)
	pic = rapi.imageUntwiddlePS2(texData, width, height, 8)
	pic = rapi.imageDecodeRawPal(pic, palData, width, height, 8, "r8g8b8a8")
	texList.append(NoeTexture(str(filename), width, height, pic, noesis.NOESISTEX_RGBA32))

	return 1

```


butchered and commented out are data pointer safeguards. assuming the layout is always aligning the image followed by the pallette without padding.

reversing is not possible like that. you'd need to explicit export a indexed bitmap with a palette. tga does that. and you gotta reshuffle the palette the same way. the twiddlePS2 should work as it is tho.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-22T04:31:10+00:00
- Post Title: How to edit .TEX files from 50 Cent Bulletproof PS2

> Reply from episoder
>
>  and unshuffled this bitch, ps2 style.  you gotta do the pointer dance.
ah yes that works great! thanks  
it seems i didn't do that palette unshuffle thing and was getting some pixelated areas, 
is that a standard procedure in parsing PS2 textures?
## Post #7
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-01-22T05:02:34+00:00
- Post Title: How to edit .TEX files from 50 Cent Bulletproof PS2

> Reply from AceWell
>
> episoder wrote: and unshuffled this bitch, ps2 style.  you gotta do the pointer dance.
ah yes that works great! thanks  
it seems i didn't do that palette unshuffle thing and was getting some pixelated areas, 
is that a standard procedure in parsing PS2 textures?

i assume yes. and it's only on 8-bit textures. the texture finder seems to always do it. those i scripted, needed it. gits, resident evil dead aim, onimusha3. all of them shuffled. i could check dmc too, but this got more block size fuckery in some of it's files. later maybe.
## Post #8
- Username: TjVatio
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 13, 2017 12:50 pm
- Post datetime: 2018-01-23T04:28:51+00:00
- Post Title: How to edit .TEX files from 50 Cent Bulletproof PS2

> Reply from episoder
>
> AceWell wrote:episoder wrote: and unshuffled this bitch, ps2 style.  you gotta do the pointer dance.
ah yes that works great! thanks  
it seems i didn't do that palette unshuffle thing and was getting some pixelated areas, 
is that a standard procedure in parsing PS2 textures? 

i assume yes. and it's only on 8-bit textures. the texture finder seems to always do it. those i scripted, needed it. gits, resident evil dead aim, onimusha3. all of them shuffled. i could check dmc too, but this got more block size fuckery in some of it's files. later maybe.

Wow!!! you guys rock!!!!   now noesis work fine loading this .TEX file
also when i export from preview and i choose tga or png, it save with transparency by default, there's a way to change this?

and with ConsoleTextureExplorer i followed your advices AceWell and the only way that program import the edited texture succesfully into the .TEX, is doing with .TM2 format image, this gives an almost none support, the only Proprietary software that let me save it in that format is one calling OPTPiX iMageStudio. :shame:

Edit: digging more, i found one program calls [Rainbow](https://www.romhacking.net/utilities/1069/) that support saving .tm2 and does the trick  the against on this. is too much work around to get this working, AceWell will you plain to do some changes in noesis to fully support this? saving maybe into tm2? or back to .TEX? im being too much greedy?  

many many thanks @AceWell and @episoder!!!!!
