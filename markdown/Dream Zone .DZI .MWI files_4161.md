## Post #1
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-02-22T05:34:10+00:00
- Post Title: Dream Zone .DZI .MWI files

I need some help with these file-types .DZI and .MWI, they are images used in the game. What i am trying to do
is to be able to open them and save them to a common format. Is there any program which can do this?

Samples:

[http://www.speedyshare.com/files/21070402/TITLE.DZI](http://www.speedyshare.com/files/21070402/TITLE.DZI)
[http://www.speedyshare.com/files/21070405/P9.MWI](http://www.speedyshare.com/files/21070405/P9.MWI)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-26T19:32:17+00:00
- Post Title: Dream Zone .DZI .MWI files

This looks like CGA format. Do you have the complete game? Can't be that big?
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-26T23:16:12+00:00
- Post Title: Dream Zone .DZI .MWI files

Okay, never mind, I got it. They are CGA/VGA files. The TITLE file shows a screen resolution of 320 x 200 in the header, and a 'line'of bytes of 41 per row. Each byte depicts 8 pixels, in nibbles. So a hex value of FF means two consecutive rows of 4 pixels, with 0 - 15 combinations (e.g. F = 1111 (binary), meaning all pixels on with foreground colour). a byte of 0xF1 means 11110001. The total size of a screen is then 328 (41x8) * 200 = 8200 bytes, The TITLE file has 4 screens that depict one of four colours (320x200 mode has 4 colours max in CGA mode) and at the back there is a tail of 300 bytes.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-27T08:30:26+00:00
- Post Title: Dream Zone .DZI .MWI files

Actually, each bit is simply a pixel (disregard the nibble part above). The highest bit comes first, so bit 7 (dec 128) is pixel 0, bit 6 (dec 64) is pixel 1 etc. 

If I expand the first of the screens in the TITLE file like that to a 8-bit bitmap this is what you get:
[screen1.raw.png](https://xentaxbackup.github.io/file/2816_screen1.raw.png)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-27T22:04:02+00:00
- Post Title: Dream Zone .DZI .MWI files

So it seems these files have 4 colour bit layers. By chosing the right palette you can show the picture in VGA or CGA mode, when the palette is CGA compatible. 

Check out the title screen, I've converted it from the data in TITLE.DZI to what it would look like in VGA mode:



TITLE.DZI.png (10.18 KiB) Viewed 360 times
## Post #6
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-02-28T09:26:05+00:00
- Post Title: Dream Zone .DZI .MWI files

I'm sorry I don't quite follow, How do I display these these as .RAW files in Photoshop?
Do I have to use the TITLE.DZI as the palette?
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-28T10:13:03+00:00
- Post Title: Dream Zone .DZI .MWI files

well, like I said. There are 4 layers of pixel information. Each byte in a layer represents 8 pixels , the left most pixel being the 8th bit (decimal value 128). If a bit is set, then the pixel at that location is set. However, there are 4 layers, so each pixel has 4 bits of colour information (4 layers). For instance, the upper left pixel of each picture has a 4-bit colour value consisting of the 8th bit of byte 1 of layer 1, then the 8th bit of byte 1 of layer 2 etc. up to a 4 bit value. A 4 bit value allows for 16 possible combinations: 16 colours in VGA mode. 

In CGA mode there are only 4 colours possible. The game uses Palette 1 of CGA at high intensity, with white, light magenta and light cyan as constant colours, and black as the variable 4th colour. Each of the 16 possible bit-combinations of layer 1 through 4 then depicts either of the 4 CGA colours in CGA mode. There are 4 combinations that lead to white, 4 that lead to light cyan, 4 that lead to light magenta and 4 that will depict black. 

I've tested each combination in the game and noted the resulting colour in VGA mode. This palette I then used on the whole reconstructed bitmap and the picture above was the result.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-28T21:57:35+00:00
- Post Title: Dream Zone .DZI .MWI files

Okay, so the game uses 4 palettes, I noticed. 2 CGA and 2 VGA. The MWI files that have CGA in their name have a slightly tweaked CGA palette (colour 12 is white instead of black). Also, those MWI files that have a CGA in their name have a VGA counterpart, with a gray-scale VGA palette, as opposed to the colour VGA palette also used in the title screen. 

Here are examples of pictures I converted in either palette:



P1.MWI.png (3.64 KiB) Viewed 260 times





P2.MWI.png (8.9 KiB) Viewed 260 times





FINAL.DZI.png (14.57 KiB) Viewed 261 times





P2CGA.MWI.png (8.97 KiB) Viewed 263 times





P3.MWI.png (9.9 KiB) Viewed 263 times





P5CGA.MWI.png (2.18 KiB) Viewed 262 times





P7.MWI.png (6.64 KiB) Viewed 258 times





P20.MWI.png (8.83 KiB) Viewed 258 times





P62.MWI.png (9.32 KiB) Viewed 257 times





P62.MWIc.png (9.32 KiB) Viewed 257 times



Here are the four palettes for photoshop Indexed colour mode.


 DreamZone_Palettes_Photoshop_XNTX.zip
(3.39 KiB) Downloaded 23 times
## Post #9
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-03-01T05:45:34+00:00
- Post Title: Dream Zone .DZI .MWI files

Thanks for the palettes, I'm still having one problem though, do I have to modify the images themselves in a hex editor to view them properly
or do I change some settings? When I open them as RAW files they appear garbled, Sorry if im overlooking something basic.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-01T08:46:26+00:00
- Post Title: Dream Zone .DZI .MWI files

Well, each file has a header: 

```
uint16 Image height
uint16 dummy
uint16 bytes per row in each layer (each byte is 8 pixels, remember, so to get to the actual width, multiple this with 8)
uint16 (number of bytes in each layer in theory / 8 ), so multiply with 8 to get to the total theoretical amount 

```


after which each layer follows. 

You need to know exactly how many bytes there are per layer, and I advise to use Image height * Bytes per row. 

The first layer always starts &ha (decimal 10, starting from 0). So you load up each layer and check the bits of each parallel byte to retreive the colour codes for the bitmap reconstruction. 

For instance, just an example :
L = layer, B = byte

L1B0 = 0xFF
L2B0 = 0x01
L3B0 = 0x01
L4B0 = 0x02

In binary they are: 

L1B0 = 11111111
L2B0 = 00000001
L3B0 = 00000001
L4B0 = 00000010

read as most significant bit - least significant bit ( or left to right, in decimal value order 128, 64, 32, 16, 8, 4, 2, 1)

So the first colour code is retrieved from the most significant bits (bit 7) of each byte: in L1B0 the bit is set, so the first bit of the 4-bit value is 1, the others are 0, so the 4-bit colour code is 1000 in binary, the bits represent 8, 4, 2, 1 respectively in decimal value, so 1000 = 8 + 0 + 0 + 0 = 8. 
Bits 6 - 5 have the same colour code value (8). All bits 1 combined gives: 1001 in binary, or 8 + 0 + 0 + 1 = 9.
Finally all four bits 0 give: 1110 in binary, or 8+4+2+0 = 14. 

So in our bitmap reconstruction, where we let each byte represent the colourcode of 1 pixel is as follows for the first 8 pixels: 8, 8, 8, 8, 8, 8, 9, 14. 

We repeat this process for all bytes. You will end up with a reconstructed bitmap. If you then apply one of the palettes to this raw image (first set the mode to Indexed colour after you load it), you will have the reconstructed picture in full.
## Post #11
- Username: StarQuake
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-01T20:35:10+00:00
- Post Title: Dream Zone .DZI .MWI files

Ok, here's a crude converter for you. It will create BMPs.


 Converter1_1.zip
(9 KiB) Downloaded 29 times
## Post #12
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-03-04T09:01:16+00:00
- Post Title: Dream Zone .DZI .MWI files

Could you supply me with the VGA palette for the other images? (if it isn't too much work) As the one provided seems to be exclusively
for the title image.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-04T09:13:22+00:00
- Post Title: Dream Zone .DZI .MWI files

Use the converter to create a picture with one of the four palettes. Then load the resulting BMP in Photoshop. The BMP has the palette, right? So you can save the .act file yourself, this way you can get all four palettes as act files. The vga palette is not only for the title screen, but for most  other pictures as well. The vga grayscale is only used for the early images (at home in the game). All others in the Dream world are with the same palette as the title screen.
## Post #14
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-03-04T11:55:05+00:00
- Post Title: Dream Zone .DZI .MWI files

I cant seem to get the desired effect (Example pictured below), I load up the converted .BMP into Photoshop and save the .ACT file but it still gives me the same
colors.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-04T15:13:43+00:00
- Post Title: Dream Zone .DZI .MWI files

Please upload the original and a screenshot how it looks on screen. Which version of the game are you using?
## Post #16
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-03-04T21:42:02+00:00
- Post Title: Re: Dream Zone .DZI .MWI files

I am using the DOS version of the game, I've attached an image comparison between the converted image and the in-game image in VGA mode.
[images.zip](https://xentaxbackup.github.io/file/2837_images.zip)
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-05T06:47:59+00:00
- Post Title: Re: Dream Zone .DZI .MWI files

Yes, I've now seen it too. It looks likethe palette differs much more per picture. Unfortunately, it may even be decided in the executable, as I've not seen any reference to any palette in the picture files themselves.
## Post #18
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-03-05T07:33:58+00:00
- Post Title: Re: Dream Zone .DZI .MWI files

I have created VGA palettes for some of the pictures by taking a
screenshot of the game in VGA mode and creating it's .ACT file. Then i got a converted version of the same picture and loaded it in Photoshop. With
this image i used the .ACT file i created but the colors were out of place so i looked at the screenshot and changed around the colors in the .ACT file
until the image looked like it did in the game.

I then saved this new ACT and renamed it to vga.bin and replaced the old one, i converted the .MWI
again and the colors were correct but only for this specific image, so this means that each image has its own palette.
Maybe if i get all the palettes from screenshots, it might be possible to put them all into one for use with every picture.

Here is the attached vga.bin file which i made using the screenshot, it is only for P2CGA.MWI:


 vgaP2.rar
(130 Bytes) Downloaded 23 times
