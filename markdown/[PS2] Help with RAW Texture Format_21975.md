## Post #1
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2020-04-06T20:44:42+00:00
- Post Title: [PS2] Help with RAW Texture Format

Wassup! So, i have finally got the decompressed textures from RACJIN Naruto Uzumaki Chronicles 2, now i need help to extract them, i'm pretty sure that it is a raw format, i can see a bit with TextureFinder:

[Textures.zip](https://xentaxbackup.github.io/file/17894_Textures.zip)
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-04-08T10:20:15+00:00
- Post Title: [PS2] Help with RAW Texture Format

I'm no expert here but just recently I have been looking into ps2 textures for sc3. I typically do 3d importing so normally I use 3dsmax for making programs. So as I was getting into texture import I just used the API in 3dsmax to render my images instead of directly writing to an external format like .jpg Mainly .jpg and .png are so complex you need to use an established library which seemed a bit over my head so anyway if I do direct export it would be to .bmp or .tga

Okay so what I figured out so far is that somewhere down the file 
in a hex editor around the 0x300 region you'll see a a hex pattern like this

```
FFFFFFFF 03000101 00000000 00010001
```

It will appear just before the image data starts and after it will be a table to the image data

So to give an example; in file "Naruto Texture.decompressed" the image data table starts at offset 0x2A8

```
000002A8:   00 00 00 00 68 00 00 00  80 00 80 00 00 01 00 33  00 00 00 00 58 00 01 00  10 00 10 00 04 00 24 3F
000002C8:   00 00 00 00 48 04 01 00  80 00 80 00 00 01 00 34  00 00 00 00 38 04 02 00  10 00 10 00 04 00 28 3F
```


As far as I can tell the second 32bit integer is the address to the image data, so in this case its [0x00000068]
But the address is relative to the start of the list entry, so in this case we take 0x2A8 + 0x68 so the image address is at 0x310

Now for the image data, I'm like very confused about it honestly, but I was able to extract this;


The image is broken into two parts the Image data (pixel indices) and CLUT (Colour Lookup Table)

in the samples for some reason the image is chopped into squares of 256x256 however the table I read in the beginning doesn't appear to offset to the parts So i really don't know how to pull the full image.... also it seems theres a little sub header inbetween and possible multiple CLUT's for colour swaps?

Anyway here is the maxscript I wrote to render the image I posted above (only runs on the "Naruto Texture.decompressed" sample)

```
	local Buf = #()
	local y = 1, x = 1, block_location = 0, byte_num = 0
	local swap_selector = 0, posY = 0, column_location = 0
	
	Buf[Swizzled.count] = 0
	for y = 1 to Height do (
		for x = 1 to Width do (
			block_location = (bit.and (y - 1) -16) * Width + (bit.and (x - 1) -16) * 2
			swap_selector = (bit.and (bit.shift (y + 1) -2) 0x1) * 4
			posY = bit.and ((bit.shift (bit.and (y - 1) -4) -1) + (bit.and (y - 1) 1)) 0x7
			column_location = posY * Width * 2 + (bit.and ((x - 1) + swap_selector) 0x7) * 4
			
			byte_num = (bit.and (bit.shift (y - 1) -1) 1) + (bit.and (bit.shift (x - 1) -2) 2)
			
			Buf[((y - 1) * Width) + x] = Swizzled[block_location + column_location + byte_num + 1]
			)
		)
	Buf
	)

fn correct_clut &palette = (
	local i = 1, vb = white, vSum = 0, storeAddr = 0
	local CurrOfs = 1, ResultPal = #()
	
	ResultPal[palette.count] = white
	for i = 1 to palette.count do (ResultPal[i] = white)
	
    for i = 1 to palette.count - 1 do (
		vSum = (
			case (mod (((i - 1) / 8) as integer) 4) of (
				1: 8
				2: -8
				default: 0
				)
			)
        storeAddr = (i - 1) + vSum + 1
        ResultPal[storeAddr].red = palette[CurrOfs].red
        ResultPal[storeAddr].green =  palette[CurrOfs].green
		ResultPal[storeAddr].blue =  palette[CurrOfs].blue
		ResultPal[storeAddr].alpha =  palette[CurrOfs].alpha
		CurrOfs += 1
		)
	ResultPal
	)

fn correctGamma c gamma:2.4 = (
	local f = c / 255.0
	if f <= 0.03928 then (
		(f / 12.92) * 255.0
		)
	else (
		(pow ((f + 0.055) / (1.0 + 0.055)) gamma) * 255.0
		)
	)

fn main file = (
	local f = undefined
	local width = 0, height = 0, i = 1, b
	local pix = #(), pal = #(), pal_size = 256
	local x = 1, y = 1
	
	f = try(fopen file "rbS")catch(undefined)
	if f != undefined do (
		width = 256
		height = 256
		
		fseek f 0x00000310 #seek_set -- first image
		pix[width * height] = 0
		for i = 1 to (width * height) do (
			pix[i] = readbyte f #unsigned
			)
		
		-- Unswizzle Image
		pix = unswizzle_8bit pix width height
		
		
		pal[pal_size] = 0
		for i = 1 to pal_size do (
			pal[i] = (
				color \
					(readbyte f #unsigned) \
					(readbyte f #unsigned) \
					(readbyte f #unsigned) \
					(readbyte f #unsigned)
				)
			
			-- Correct the Gamma
			pal[i].red = correctGamma pal[i].red
			pal[i].green = correctGamma pal[i].green
			pal[i].blue = correctGamma pal[i].blue
			pal[i].alpha = correctGamma pal[i].alpha
			
			-- Swap BGRA to RGBA
			pal[i] = color pal[i].a pal[i].r pal[i].g pal[i].b
			)
		
		format "Location:\t0x%\n" (bit.intAsHex ((ftell f) as integer))
		
		-- Order Palette (Required for 8Bit)
		pal = correct_clut pal
		
		
		-- Combine Palette and Image Data
		b = bitmap width height color:(color 255 0 255)
		for y = 1 to height do (
			for x = 1 to width do (
				setPixels b [x - 1, y - 1] #(pal[pix[x + (width * (y - 1))] + 1])
				)
			)
		
		-- Render Image
		display b
		
		-- Close file
		fclose f
		)
	)
main "G:\\_HACKS&MODS\\SoulCalibur\\SC3_Playstation\\Textures\\Naruto Texture.decompressed"

```


* be aware i'm new to dealing with ps2 image data, so my code may not be entirely functional or accurately convert the images
## Post #3
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2020-04-15T14:49:16+00:00
- Post Title: [PS2] Help with RAW Texture Format

> Reply from mariokart64n ↑Wed Apr 08, 2020 6:20 pm at Wed Apr 08, 2020 6:20 pm
>
> 
I'm no expert here but just recently I have been looking into ps2 textures for sc3. I typically do 3d importing so normally I use 3dsmax for making programs. So as I was getting into texture import I just used the API in 3dsmax to render my images instead of directly writing to an external format like .jpg Mainly .jpg and .png are so complex you need to use an established library which seemed a bit over my head so anyway if I do direct export it would be to .bmp or .tga

Okay so what I figured out so far is that somewhere down the file 
in a hex editor around the 0x300 region you'll see a a hex pattern like this
Code: Select allFFFFFFFF 03000101 00000000 00010001
It will appear just before the image data starts and after it will be a table to the image data

So to give an example; in file "Naruto Texture.decompressed" the image data table starts at offset 0x2A8
Code: Select allOffset
000002A8:   00 00 00 00 68 00 00 00  80 00 80 00 00 01 00 33  00 00 00 00 58 00 01 00  10 00 10 00 04 00 24 3F
000002C8:   00 00 00 00 48 04 01 00  80 00 80 00 00 01 00 34  00 00 00 00 38 04 02 00  10 00 10 00 04 00 28 3F

As far as I can tell the second 32bit integer is the address to the image data, so in this case its [0x00000068]
But the address is relative to the start of the list entry, so in this case we take 0x2A8 + 0x68 so the image address is at 0x310

Now for the image data, I'm like very confused about it honestly, but I was able to extract this;


The image is broken into two parts the Image data (pixel indices) and CLUT (Colour Lookup Table)

in the samples for some reason the image is chopped into squares of 256x256 however the table I read in the beginning doesn't appear to offset to the parts So i really don't know how to pull the full image.... also it seems theres a little sub header inbetween and possible multiple CLUT's for colour swaps?

Anyway here is the maxscript I wrote to render the image I posted above (only runs on the "Naruto Texture.decompressed" sample)
Code: Select allfn unswizzle_8bit Swizzled& Width Height = ( -- PSMT8
	local Buf = #()
	local y = 1, x = 1, block_location = 0, byte_num = 0
	local swap_selector = 0, posY = 0, column_location = 0
	
	Buf[Swizzled.count] = 0
	for y = 1 to Height do (
		for x = 1 to Width do (
			block_location = (bit.and (y - 1) -16) * Width + (bit.and (x - 1) -16) * 2
			swap_selector = (bit.and (bit.shift (y + 1) -2) 0x1) * 4
			posY = bit.and ((bit.shift (bit.and (y - 1) -4) -1) + (bit.and (y - 1) 1)) 0x7
			column_location = posY * Width * 2 + (bit.and ((x - 1) + swap_selector) 0x7) * 4
			
			byte_num = (bit.and (bit.shift (y - 1) -1) 1) + (bit.and (bit.shift (x - 1) -2) 2)
			
			Buf[((y - 1) * Width) + x] = Swizzled[block_location + column_location + byte_num + 1]
			)
		)
	Buf
	)

fn correct_clut &palette = (
	local i = 1, vb = white, vSum = 0, storeAddr = 0
	local CurrOfs = 1, ResultPal = #()
	
	ResultPal[palette.count] = white
	for i = 1 to palette.count do (ResultPal[i] = white)
	
    for i = 1 to palette.count - 1 do (
		vSum = (
			case (mod (((i - 1) / 8) as integer) 4) of (
				1: 8
				2: -8
				default: 0
				)
			)
        storeAddr = (i - 1) + vSum + 1
        ResultPal[storeAddr].red = palette[CurrOfs].red
        ResultPal[storeAddr].green =  palette[CurrOfs].green
		ResultPal[storeAddr].blue =  palette[CurrOfs].blue
		ResultPal[storeAddr].alpha =  palette[CurrOfs].alpha
		CurrOfs += 1
		)
	ResultPal
	)

fn correctGamma c gamma:2.4 = (
	local f = c / 255.0
	if f <= 0.03928 then (
		(f / 12.92) * 255.0
		)
	else (
		(pow ((f + 0.055) / (1.0 + 0.055)) gamma) * 255.0
		)
	)

fn main file = (
	local f = undefined
	local width = 0, height = 0, i = 1, b
	local pix = #(), pal = #(), pal_size = 256
	local x = 1, y = 1
	
	f = try(fopen file "rbS")catch(undefined)
	if f != undefined do (
		width = 256
		height = 256
		
		fseek f 0x00000310 #seek_set -- first image
		pix[width * height] = 0
		for i = 1 to (width * height) do (
			pix[i] = readbyte f #unsigned
			)
		
		-- Unswizzle Image
		pix = unswizzle_8bit pix width height
		
		
		pal[pal_size] = 0
		for i = 1 to pal_size do (
			pal[i] = (
				color \
					(readbyte f #unsigned) \
					(readbyte f #unsigned) \
					(readbyte f #unsigned) \
					(readbyte f #unsigned)
				)
			
			-- Correct the Gamma
			pal[i].red = correctGamma pal[i].red
			pal[i].green = correctGamma pal[i].green
			pal[i].blue = correctGamma pal[i].blue
			pal[i].alpha = correctGamma pal[i].alpha
			
			-- Swap BGRA to RGBA
			pal[i] = color pal[i].a pal[i].r pal[i].g pal[i].b
			)
		
		format "Location:\t0x%\n" (bit.intAsHex ((ftell f) as integer))
		
		-- Order Palette (Required for 8Bit)
		pal = correct_clut pal
		
		
		-- Combine Palette and Image Data
		b = bitmap width height color:(color 255 0 255)
		for y = 1 to height do (
			for x = 1 to width do (
				setPixels b [x - 1, y - 1] #(pal[pix[x + (width * (y - 1))] + 1])
				)
			)
		
		-- Render Image
		display b
		
		-- Close file
		fclose f
		)
	)
main "G:\\_HACKS&MODS\\SoulCalibur\\SC3_Playstation\\Textures\\Naruto Texture.decompressed"


* be aware i'm new to dealing with ps2 image data, so my code may not be entirely functional or accurately convert the images

Many thanks for the reply, so, I don't think that it gonna be so useful but i figured out that the texture itself starts at 1D0 (the first bytes are his script)
plus: at least in the script the Naruto texture is chopped into five parts:
