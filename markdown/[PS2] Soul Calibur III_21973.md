## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-04-06T04:18:17+00:00
- Post Title: [PS2] Soul Calibur III

For current work on this game, please see the Soul Calibur 3 megathread.

The textures appear to be kept in a container where there can be multiple images and multiple image palettes for each image.

I'm examining a container with just a single palette and image so that I know they belong to each other.

Ran PCSX2 and dumped the texture so I know what its suppose to look like


I've read the image data and palette and tried to marry them but the output appears wrong


I tried doing some colour manipulation to atleast get the right colours, but that appears not working either


I believe the images are swizzled, the only information I could find are on 4bit and 8bit by nick7
[https://gta.nick7.com/ps2/swizzling/](https://gta.nick7.com/ps2/swizzling/)

```
{
    dbw = dbw >> 1;
    int index = 0;
    int num2 = dbp * 0x40;
    for (int i = dsay; i < (dsay + rrh); i++)
    {
        for (int j = dsax; j < (dsax + rrw); j++)
        {
            int num5 = j / 0x80;
            int num6 = i / 0x40;
            int num7 = num5 + (num6 * dbw);
            int num8 = j - (num5 * 0x80);
            int num9 = i - (num6 * 0x40);
            int num10 = num8 / 0x10;
            int num11 = num9 / 0x10;
            int num12 = this.block8[num10 + (num11 * 8)];
            int num13 = num8 - (num10 * 0x10);
            int num14 = num9 - (num11 * 0x10);
            int num15 = num14 / 4;
            int num16 = num13;
            int num17 = num14 - (num15 * 4);
            int num18 = this.columnWord8[num15 & 1, num16 + (num17 * 0x10)];
            int num19 = this.columnByte8[num16 + (num17 * 0x10)];
            int num20 = ((((num2 + (num7 * 0x800)) + (num12 * 0x40)) + (num15 * 0x10)) + num18) * 4;
            data[index] = this.gsmem[num20 + num19];
            index++;
        }
    }
}

private void writeTexPSMCT16(int dbp, int dbw, int dsax, int dsay, int rrw, int rrh, byte[] data)
{
    int index = 0;
    int num2 = dbp * 0x40;
    for (int i = dsay; i < (dsay + rrh); i++)
    {
        for (int j = dsax; j < (dsax + rrw); j++)
        {
            int num5 = j / 0x40;
            int num6 = i / 0x40;
            int num7 = num5 + (num6 * dbw);
            int num8 = j - (num5 * 0x40);
            int num9 = i - (num6 * 0x40);
            int num10 = num8 / 0x10;
            int num11 = num9 / 8;
            int num12 = this.block16[num10 + (num11 * 4)];
            int num13 = num8 - (num10 * 0x10);
            int num14 = num9 - (num11 * 8);
            int num15 = num14 / 2;
            int num16 = num13;
            int num17 = num14 - (num15 * 2);
            int num18 = this.columnWord16[num16 + (num17 * 0x10)];
            int num19 = this.columnHalf16[num16 + (num17 * 0x10)];
            int num20 = ((((num2 + (num7 * 0x800)) + (num12 * 0x40)) + (num15 * 0x10)) + num18) * 4;
            this.gsmem[num20 + num19] = data[index];
            this.gsmem[(num20 + num19) + 1] = data[index + 1];
            index += 2;
        }
    }
}

public byte[] Unswizzle(byte[] data, int width, int height)
{
    byte[] buffer = new byte[data.Length];
    this.gsmem = new byte[0x400000];
    if (this.textureInfo.BitsPerPixel == 8)
    {
        int rrw = width / 2;
        int rrh = height / 2;
        this.readTexPSMT8(0, width / 0x40, 0, 0, width, height, ref buffer);
    }

    this.gsmem = null;
    GC.Collect();
    return buffer;
}

```


But I'm having a difficult time understanding how the code works, wondering if someone could give me a hand


Sample:
[texture_sample1.zip](https://cdn.discordapp.com/attachments/493153150820286464/696570513581015130/texture_sample1.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-04-09T02:21:12+00:00
- Post Title: [PS2] Soul Calibur III

i'm not a programmer so i can't explain how that code works.   
i assume you are trying to translate it to maxscript and i don't use that either.
fortunately the legwork has already been done by those before us and they
leave behind tools that do the job well.   
here is a Noesis python script that opens your one vpt sample.  


 tex_SoulCalibur3_PS2_vpt.zip
(891 Bytes) Downloaded 33 times


included in the script is a python function translated by Allen from Zenhax
for PS2 unswizzle that can do the same job as the Noesis imageUntwiddlePS2 
command, you may be able to understand that easier, don't know.   
it is currently unused in the script but you can comment line 23 and uncomment line 22 to use it.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-09T04:30:49+00:00
- Post Title: [PS2] Soul Calibur III

thx, Ace!  
My question is what that swizzled bytearray is good for (local copy)? Seems to work without it:

```
    out = bytearray(width * height)
    for y in range(height):
        for x in range(width):
            block_location = (y & (~0xf)) * width + (x & (~0xf)) * 2
            swap_selector = (((y + 2) >> 2) & 0x1) * 4
            posY = (((y & (~3)) >> 1) + (y & 1)) & 0x7
            column_location = posY * width * 2 + ((x + swap_selector) & 0x7) * 4
            byte_num = ((y >> 1) & 1) + ((x >> 2) & 2) # 0,1,2,3
            out[(y * width) + x] = buf[block_location + column_location + byte_num]
    return out
```


> Reply from Acewell ↑Thu Apr 09, 2020 10:21 am at Thu Apr 09, 2020 10:21 am
>
> 
i'm not a programmer so i can't explain how that code works.I'm a programmer (well, some sort of  ) and can't explain it, too.
You could insert some debug print line such as
print(swap_selector,posY,column_location,byte_num)
in the inner loop to see more (but you need to reduce height to 16 for example (for y in range(16):) or the debug log window's buffer will overflow).

```
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
0 0 20 0
0 0 24 0
0 0 28 0
0 0 0 2
0 0 4 2
0 0 8 2
0 0 12 2
0 0 16 2
0 0 20 2
0 0 24 2
0 0 28 2
0 0 0 0
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
0 0 20 0
0 0 24 0
0 0 28 0
0 0 0 2
0 0 4 2
0 0 8 2
0 0 12 2
0 0 16 2
0 0 20 2
0 0 24 2
0 0 28 2
0 0 0 0
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
0 0 20 0
0 0 24 0
0 0 28 0
0 0 0 2
0 0 4 2
0 0 8 2
0 0 12 2
0 0 16 2
0 0 20 2
0 0 24 2
0 0 28 2
0 0 0 0
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
0 0 20 0
0 0 24 0
0 0 28 0
0 0 0 2
0 0 4 2
0 0 8 2
0 0 12 2
0 0 16 2
0 0 20 2
0 0 24 2
0 0 28 2
0 0 0 0
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
0 0 20 0
0 0 24 0
0 0 28 0
0 0 0 2
0 0 4 2
0 0 8 2
0 0 12 2
0 0 16 2
0 0 20 2
0 0 24 2
0 0 28 2
0 0 0 0
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
0 0 20 0
0 0 24 0
0 0 28 0
0 0 0 2
0 0 4 2
0 0 8 2
0 0 12 2
0 0 16 2
0 0 20 2
0 0 24 2
0 0 28 2
0 0 0 0
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
0 0 20 0
0 0 24 0
0 0 28 0
0 0 0 2
0 0 4 2
0 0 8 2
0 0 12 2
0 0 16 2
0 0 20 2
0 0 24 2
0 0 28 2
0 0 0 0
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
0 0 20 0
0 0 24 0
0 0 28 0
0 0 0 2
0 0 4 2
0 0 8 2
0 0 12 2
0 0 16 2
0 0 20 2
0 0 24 2
0 0 28 2
0 0 0 0
0 0 4 0
0 0 8 0
0 0 12 0
0 0 16 0
.....
```
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-04-10T06:50:11+00:00
- Post Title: [PS2] Soul Calibur III

> Reply from shakotay2 ↑Thu Apr 09, 2020 12:30 pm at Thu Apr 09, 2020 12:30 pm
>
> My question is what that swizzled bytearray is good for (local copy)? Seems to work without it
i don't know i didn't write it, maybe is a catch-all or something.
## Post #5
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-04-14T00:38:53+00:00
- Post Title: [PS2] Soul Calibur III

I have already reversed engineered the VTX format completely. And I posted a semi-working code here written in QT.
I will post an updated unswizzling code here in 1-2 days, gotta clean up the code a bit.

I have even published some fruits of my work over on 8WAYRUN.
## Post #6
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-04-14T00:43:19+00:00
- Post Title: [PS2] Soul Calibur III

To elaborate:

It is the good ol' PS2 swizzling. Here is the code I use for KH2FM which works with SC3 with a minor edit. The swizzling itself is as follows:

```
{
    QImage InputIMG = Parse8();
    QImage OutputIMG(InputIMG.size(), InputIMG.format());

    QList<QColor> PixelList;

    for (int y = 0; y < InputIMG.height(); y++)
    for (int x = 0; x < InputIMG.width(); x++)
       PixelList.append(InputIMG.pixelColor(x, y));

    int PixelCount = PixelList.count();
    int Width = InputIMG.width();

    int TrueX = 0;
    int TrueY = 0;

    int BoolY = 0;
    int BoolPixel = 0;

    for (int p = 0; p < PixelCount; p++)
    {
        int x = TrueX;
        int y = TrueY;

        if (p != 0)
        {
            if ((p % (Width * 2)) == 0)
            {
                switch (BoolY)
                {
                    case 0:
                    {
                        TrueY += 1;
                        break;
                    }

                    case 1:
                    {
                        TrueY += 3;
                        BoolSwitch(BoolPixel);
                        break;
                    }
                }

                TrueX = 0;
                BoolSwitch(BoolY);
            }

            else if (p % 32 == 0)
            TrueX += 16;
        }

        int TruePixel = p % 16;
        int cp = (p / 16) % 2;

        if (BoolPixel == 1)
            BoolSwitch(cp);

        switch (cp)
        {
            case 0:
            {
                x = TrueX + ((TruePixel % 4) * 4) + (TruePixel / 4);
                break;
            }

            case 1:
            {
                int a = 4;

                if (TruePixel % 4 >= 2)
                    a = 12;

                x = TrueX + (a - ((TruePixel % 2) * 4)) + (TruePixel / 4);
                break;
            }
        }

        if (p % 2 == 1)
            y = TrueY + 2;

        OutputIMG.setPixelColor(x, y, PixelList[p]);
    }

    return OutputIMG;
}

```


(I get the swizzled image as an image then I unswizzle it to PROFIT. Slow, but works)

The indexes are also obfuscated as such:

```
            {
                int x = Data[i];

                if (x >= 0)
                {
                    int remainder = x % 32;
                    if (remainder > 7 && remainder < 16)
                    {
                        x += 8;
                    }
                    else if (remainder > 15 && remainder < 24)
                    {
                        x -= 8;
                    }
                }

                indexList.append(x);
            }

```


I have worked on Soulcalibur 3 for way too long. I have even made a toolkit which I lost the source of to a dead HDD. I ay actually return and finish it now since NOW people want to mod the game apparently.
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-04-17T17:23:22+00:00
- Post Title: [PS2] Soul Calibur III

I was able to convert image data with the function Acewell posted, however the colours are wrong

here is the 8bit unswizzle function transcoded to maxscript

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

```


my issue after that was the colours seemed pixelilated, I found out through a GTA post that 8bit CLUT's need to be reordered


A dephi function was shared by mumma-ra on the xentax discord, and I've transcoded that to maxscript as well

```
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

```


However this doesn't seem to be working 100%


I compared the ripped texture I got through the emulator with the output from noesis (using the plugin Acewell posted) and they are identical.

I believe there is something wrong with my CLUT (palette) function, the 8bit unswizzle function for the image indices appears okay

In the noesis script I can see 2 functions being called

```
rapi.imageDecodeRawPal()

```


Now I had a look at TopazTK code and I say index re-ordering but nothing such as colour correcting, so I'm not sure how to adapt this correctly to maxscript

Here I've transcoded both functions into maxscript as follows, there was another function called BoolSwitch which was not shown but I assumed it just inverted a bool?


```
	(if BoolPixel == 1 then 0 else 1)
	)

```


```
	local PixelList = #()

    local TrueX = 0
    local TrueY = 0

    local BoolY = 0
    local BoolPixel = 0
	local p = 1, x = 1, y = 1
	
	local TruePixel = 1
	local cp = 1, a = 1
	
	PixelList[pixels.count] = 1
	for p = 1 to pixels.count do (PixelList[p] = 1)
	
	for p = 1 to pixels.count do (
        x = TrueX
        y = TrueY
		
        if p != 0 do (
            if (mod p (Width * 2)) == 0 then (
                case BoolY of (
                    0: (
                        TrueY += 1
						)
                    1: (
                        TrueY += 3
                        BoolPixel = BoolSwitch(BoolPixel)
						)
					)
				
                TrueX = 0
                BoolY = BoolSwitch(BoolY)
				)
            else if (mod p 32) == 0 do (
				TrueX += 16
				)
			)
		
        TruePixel = mod p 16
        cp = mod (p / 16) 2
		
        if BoolPixel == 1 do (
			cp = BoolSwitch(cp)
			)
		
        case cp of (
            0: (
                x = TrueX + ((mod TruePixel 4) * 4) + (TruePixel / 4)
				)
            1: (
                a = 4
                if (mod TruePixel 4) >= 2 do (
					a = 12
					)
                x = TrueX + (a - ((mod TruePixel 2) * 4)) + (TruePixel / 4)
				)
			)
		
        if mod p 2 == 1 do (
			y = TrueY + 2
			)
		PixelList[(y * Width) + x + 1] = pixels[p]
		)
	PixelList
	)

```


```
	local i = 1, x = 1, remainder = 0, indexList = #()
	for i = 1 to data.count do (
		x = Data[i]
		if x >= 0 do (
			remainder = mod x 32
			if remainder > 7 and remainder < 16 then (
				x += 8
				)
			else if remainder > 15 and remainder < 24 do (
				x -= 8
				)
			)
		append indexList x
		)
	indexList
	)

```


I ran both TopazTK's functions on the image indices, not the CLUT and got the following


Seems the image data is not unswizzled correctly so I'm not sure if its a mistake in my implementation to maxscript or not?

Anyways using the function Acewell posted to correct the indices, the delphi function to correct the CLUT order and applying a gamma correction the converted image is pretty close, but its still not correct..

Original (dumped from the PCSX2 emulator)


Imported (Maxscript, With Gamma Correction)



Here's my current maxscript


 vpt_imp.zip
(2.45 KiB) Downloaded 20 times



any thoughts?
## Post #8
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-04-17T19:27:38+00:00
- Post Title: [PS2] Soul Calibur III

Hmm, interesting, the colors are not changed in the SC3 imaging format at all. Well, except or the Alpha. 
Let me experiment in QT again, Let me see what results I get.
## Post #9
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-04-17T19:31:53+00:00
- Post Title: [PS2] Soul Calibur III

Looking trough my old posts in 8WAYRUN, I have found this: [https://imgur.com/SD72FGz](https://imgur.com/SD72FGz)
I think I still have this tool in my archives, gotta be sure.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-04-18T01:44:18+00:00
- Post Title: [PS2] Soul Calibur III

> Reply from mariokart64n ↑Sat Apr 18, 2020 1:23 am at Sat Apr 18, 2020 1:23 am
>
> my issue after that was the colours seemed pixelilated, I found out through a GTA post that 8bit CLUT's need to be reordered
the reordering of palette in the Noesis python script  is done with the noesis.DECODEFLAG_PS2SHIFT command.
this python code does the same thing as that command:

```
for i in range(8):                  #do this 8 times
    for j in range(32):              #read 1st 32 byte block of palette
        read = bs.readUByte()
        paletteData.append(read)
    bs.seek(0x20, 1)
    for j in range(32):              #read 3rd 32 byte block of palette
        read = bs.readUByte()
        paletteData.append(read)
    bs.seek(-0x40, 1)
    for j in range(32):              #read 2nd 32 byte block of palette
        read = bs.readUByte()
        paletteData.append(read)
    bs.seek(0x20, 1)
    for j in range(32):              #read 4th 32 byte block of palette
        read = bs.readUByte()
        paletteData.append(read)
palette = bytearray(paletteData)

```
## Post #11
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-04-18T12:33:43+00:00
- Post Title: [PS2] Soul Calibur III

The palette isn't being reordered. Here's some output from my fixed-up code, which I shall publish after a clean-up:
[build-SC3Convert-Desktop_Qt_5_14_2_MinGW_64_bit-Debug.rar](https://xentaxbackup.github.io/file/17956_build-SC3Convert-Desktop_Qt_5_14_2_MinGW_64_bit-Debug.rar)
## Post #12
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-04-18T13:26:37+00:00
- Post Title: [PS2] Soul Calibur III

Here is the repository for all whom want to check it out. It is still not complete (cannot parse 4-bits, sometimes cannot correct W/H).
However, this is more than enough to prove a point. Also: IF YOU ARE GOING TO CONVERT THIS TO MAXSCRIPT, MIND THE DIFFERENCES BETWEEN IT AND QT

[https://github.com/Topaz-Reality/SC3IMG](https://github.com/Topaz-Reality/SC3IMG)
## Post #13
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-04-18T16:31:17+00:00
- Post Title: [PS2] Soul Calibur III

Thanks for posting your repository, once I was able to see your texture functions in a fuller context I was able to get it working in maxscript



After applying a gamma correction of 2.2 the imported image is identical to the one dumped from PCSX2 

This is going to make it much easier to get SC3 models textured, thank you soo much 


[vpt_imp.zip](https://xentaxbackup.github.io/file/17958_vpt_imp.zip)
## Post #14
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-04-18T16:57:58+00:00
- Post Title: [PS2] Soul Calibur III

> Reply from mariokart64n ↑Sun Apr 19, 2020 12:31 am at Sun Apr 19, 2020 12:31 am
>
> 
Thanks for posting your repository, once I was able to see your texture functions in a fuller context I was able to get it working in maxscript



After applying a gamma correction of 2.2 the imported image is identical to the one dumped from PCSX2 

This is going to make it much easier to get SC3 models textured, thank you soo much

Gamma Correction is unnecessary because it's just a filter on the main menu. Since dumpers like NinjaRipper catch these from DX9/DX11, they cannot bypass this filter.

Also, are you working on an exporter of some sort for the models? If so, maybe I could port your code for it to QtC++? I am working on a project to mod Soulcalibur 3 o the fullest extend and your script for model extraction would really make my job one step easier. You will be credited, of course.
## Post #15
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-04-18T17:17:45+00:00
- Post Title: [PS2] Soul Calibur III

Yeah theres another topic in the 3D section

[viewtopic.php?f=16&t=5648&start=30](https://forum.xentax.com/viewtopic.php?f=16&t=5648&start=30)

I actually need help with the format, my maxscript is attached in my post
