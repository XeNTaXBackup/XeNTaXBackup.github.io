## Post #1
- Username: Ada Radames
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 24, 2021 1:03 am
- Post datetime: 2022-01-15T11:11:59+00:00
- Post Title: Baldur's Gate: Dark Alliance .tex Format Conversion

Hi all, first time posting here so apologies if this is in the wrong place.

Quick summary: I need help converting normal image formats back into the .tex format used by Baldur's Gate: Dark Alliance II.

I am currently developing a mod for Baldur's Gate: Dark Alliance II on the PS2. Using various tools available online, as well as developing my own, I have begun to learn about the game's file formats and how to edit and manipulate them. So far I can swap and edit models, animations, audio, and text. I am currently struggling with the following issue regarding the game's textures: creating a converter to convert from .tex to any readable image format (let's say, BMP) and convert a BMP back into a .tex file.

If I can share what I've learned so far (which may be wrong of course):
The format of a Dark Alliance .tex file is very similar to an 8bit BMP file. In the following example, in a 32x32 pixels .tex file we have a header, a palette made up of 256 palette entries (1024 bytes of 256x4 bytes) with RGBA data, some kind of separating byte block, and then a block of 1024 bytes comprising the pixels. In an 8-bit BMP, the length of the headers (and thus the palette + pixel offsets) are different, but the palette and pixel blocks are the same length.

Using existing tools (Console Texture Explorer, for example) it's possible to convert .tex into a BMP, so I can compare the two and try to develop a way to convert from a BMP back into .tex.

In my code I adapted the algorithm presented in the bgda explorer to unswizzle the .tex palette into the format of a BMP palette:

```
		result = dict()
		for x in range(0, len(palette)):
			result[x] = paletteNode()
		i = 0
		j = 0
		while (i < 256):
			for x in range(0,8):
				result[i+x] = palette[j+x]
			for x in range(0,8):
				result[i+x+16] = palette[j+x+8]
			for x in range(0,8):
				result[i+x + 8] = palette[j+x + 16]
			for x in range(0,8):
				result[i+x + 24] = palette[j+x + 24]
			j+=32
			i+=32
		result=paletteFunctions.swapRGBAandBGRA(result)
		result=paletteFunctions.flipAlpha(result)
		return result

```


Once unswizzled the palette is the same as the BMP's palette. I can then "reswizzle" the palette back into a .tex palette by running the function in reverse:

```
		palette=paletteFunctions.flipAlpha(palette)
		palette=paletteFunctions.swapRGBAandBGRA(palette)
		result = copy.deepcopy(palette)
		i = 256
		j = 256
		while (i > 0):
			j-=32
			i-=32
			for x in range(0,8):
				palette[i+x + 24] = result[j+x + 24]
			for x in range(0,8):
				palette[i+x + 8] = result[j+x + 16]
			for x in range(0,8):
				palette[i+x+16] = result[j+x+8]
			for x in range(0,8):
				palette[i+x] = result[j+x]
		
		return palette

```


I think I understand how to deal with a palette in this way. However, I am currently stuck on how to deal with the pixel block. From what I understand, a BMP's pixel block is read last in first out, so the last bytes read become the top left pixels. I think the order of the pixels in a .tex file compared to a BMP are also swizzled in some way, but I have unfortunately become very much stuck and confused with what to do about the BMP pixel block to convert it into a .tex pixel block. I don't know how many bytes make up a pixel in this format (4?), what each byte in this pixel block means, and how they need to be processed or rearranged. The palette block was much easier to understand as it was basically just flipping alpha values, swapping bytes between palette blocks, and rearranging some of the blocks to reswizzle into the .tex format. But I'm completely stuck about how to deal with the pixels. bgda-explorer does something to apply a palette to these pixels to get what I think is a much larger set of pixel bytes appropriate for a PNG file. Perhaps it is possible for me to reverse that algorithm to regain the original pixel data block from this expanded one, but the code dealing with this process is very long and involved and not something I yet understand well.

I uploaded the .tex file and its conversion to a .bmp made by Console Texture Explorer. Interestingly, converting .tex to a PNG using bgda-explorer, and then converting the PNG into a BMP, seems to change not only the pixel data, but the palette data as well, which makes understanding the conversion process even more challenging.

If anyone has any information or any tools which can allow me to convert an image into a .tex file usable by Dark Alliance I would really appreciate it.
[innlamp.zip](https://xentaxbackup.github.io/file/21611_innlamp.zip)
