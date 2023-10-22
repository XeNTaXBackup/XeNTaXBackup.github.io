## Post #1
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-02-03T13:48:31+00:00
- Post Title: How to Open/Convert Metal Slug Antology PSP .tex files

Hi, I'm looking for a way to view the Art Gallery of Metal Slug Anthology PSP. The game was developed/ported by Terminal Reality. The POD archives are standard POD3 archives, so I had no problem extracting them. But the .tex files themselves are a bit problematic. I tried 2 different BloodRaye TEX converters, none of which worked. Then I tried Ghostbusters TEX Converter, which succeeded in converting them to .dds, but I couldn't open them. Can anyone, please, help? [Here](https://cloud.mail.ru/public/9e9ace0d9566/texexamples.zip) are some examples of the aforementioned files. Thanks in advance.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-03T14:11:20+00:00
- Post Title: How to Open/Convert Metal Slug Antology PSP .tex files

try Texturefinder.



01_Tex.JPG (72.77 KiB) Viewed 191 times


But you must care for the correct palette
## Post #3
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-02-03T15:06:06+00:00
- Post Title: How to Open/Convert Metal Slug Antology PSP .tex files

Well, I couldn't do much more than what you show in the screenshot. Thanks, though.
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-02-13T18:18:53+00:00
- Post Title: How to Open/Convert Metal Slug Antology PSP .tex files

Script for [Noesis](http://www.richwhitehouse.com/index.php?content=inc_projects.php):

```
import noesis
import rapi

def registerNoesisTypes():
	'''Register the plugin'''

	handle = noesis.register("Metal Slug Anthology", ".tex")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadRGBA(handle, noepyLoadRGBA)
	return 1

def noepyCheckType(data):
	'''Verify that the format is supported by this plugin.'''

	return 1

def noepyLoadRGBA(data, texList):
	'''Load the texture(s)'''

	parser = texFile(data)
	parser.parse_file()
	texList.extend(parser.texList)
	return 1

class texFile(object):

	def __init__(self, data):
		self.inFile = NoeBitStream(data)
		self.texList = []

	def parse_file(self):
		sign = self.inFile.readInt()
		unk = self.inFile.readInt()
		width = self.inFile.readInt()
		height = self.inFile.readInt()
		unk = self.inFile.readInt()
		mipmaps = self.inFile.readInt()
		dummy = self.inFile.readInt()
		unk = self.inFile.readInt()

		palette = self.inFile.readBytes(1024)
		pixMap = self.inFile.readBytes(width*height)

		pixData = rapi.imageDecodeRawPal(pixMap, palette, width, height, 8, "r8g8b8a8")

		tex = NoeTexture("tex", width, height, pixData, noesis.NOESISTEX_RGBA32)
		self.texList.append(tex)

```
## Post #5
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-02-15T07:23:10+00:00
- Post Title: How to Open/Convert Metal Slug Antology PSP .tex files

Thank you so much, barti! I tried and it works like a charm for the PSP. Not to sound unthankful or anything, I really appreciate your work, I tried the script on the PS2 and Wii versions and it, sadly, didn't work. Can you, guys, please, help me with these too? I don't know anything about scripting myself. I probably should've posted all the files together, but I was stupid enough to think they would be the same format. The examples are [here](https://cloud.mail.ru/public/785a92acc98c/ps2wiiexamples.zip). Thanks again.
