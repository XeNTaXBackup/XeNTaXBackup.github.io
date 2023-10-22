## Post #1
- Username: PaK
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue May 29, 2007 7:43 pm
- Post datetime: 2007-05-29T17:52:15+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Im trying to extract the textures of this ps2 game.

I have searched inside files to find any header, and I found that:



- red marks, are what I supossed as the header tags
- blue marks, i didnt know still nothing about this..
- red marks, first & second are sizeX, sizeY of image ( little endian ), the last one mark I suppused is color depth pixels.

Looking at data, seems to be raw RGBA, 8 depht, images.

I coded an easy program in C to try to extract this kind of images.
Here are some raws I extracted.



Seems that my extractor works. My problem now is how to interlace or unswizzle the images. Anyone have a idea?

some files with textures inside
[http://personales.ya.com/paks/tmp/files.rar](http://personales.ya.com/paks/tmp/files.rar)

some raw extracted images
[http://personales.ya.com/paks/tmp/extract_images.rar](http://personales.ya.com/paks/tmp/extract_images.rar)
## Post #2
- Username: triton
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Mar 05, 2007 10:41 am
- Post datetime: 2007-05-29T20:11:19+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Here's a code algorithm for xbox swizzle and unswizzle


```
{
	if(SegWidth == 2 && SegHeight == 2)
	{
       ((byte *)WriteArray)[WriteOffset                ] = ((byte *)ReadArray)[ReadOffset + 0];
       ((byte *)WriteArray)[WriteOffset + 1            ] = ((byte *)ReadArray)[ReadOffset + 1];
       ((byte *)WriteArray)[WriteOffset + DataWidth    ] = ((byte *)ReadArray)[ReadOffset + 2];
       ((byte *)WriteArray)[WriteOffset + DataWidth + 1] = ((byte *)ReadArray)[ReadOffset + 3];
	   ReadOffset += 4;
	}
	else
	{
		UnSwizzle(ReadArray, WriteArray, ReadOffset, WriteOffset, SegWidth/2, SegHeight/2, DataWidth);
		UnSwizzle(ReadArray, WriteArray, ReadOffset, WriteOffset + SegWidth/2, SegWidth/2, SegHeight/2, DataWidth);
		UnSwizzle(ReadArray, WriteArray, ReadOffset, WriteOffset + DataWidth*(SegHeight/2), SegWidth/2, SegHeight/2, DataWidth);
		UnSwizzle(ReadArray, WriteArray, ReadOffset, WriteOffset + DataWidth*(SegHeight/2) + SegWidth/2, SegWidth/2, SegHeight/2, DataWidth);
	}
}

void Swizzle(void *WriteArray, void *ReadArray, unsigned long int &WriteOffset, unsigned long int ReadOffset, unsigned long int SegWidth, unsigned long int SegHeight, unsigned long int DataWidth)
{
	if(SegWidth == 2 && SegHeight == 2)
	{
       ((byte *)WriteArray)[WriteOffset                ] = ((byte *)ReadArray)[ReadOffset + 0];
       ((byte *)WriteArray)[WriteOffset + 1            ] = ((byte *)ReadArray)[ReadOffset + 1];
       ((byte *)WriteArray)[WriteOffset + 2            ] = ((byte *)ReadArray)[ReadOffset + DataWidth];
       ((byte *)WriteArray)[WriteOffset + 3            ] = ((byte *)ReadArray)[ReadOffset + DataWidth + 1];
	   WriteOffset += 4;
	}
	else
	{
		Swizzle(WriteArray, ReadArray, WriteOffset, ReadOffset, SegWidth/2, SegHeight/2, DataWidth);
		Swizzle(WriteArray, ReadArray, WriteOffset, ReadOffset + SegWidth/2, SegWidth/2, SegHeight/2, DataWidth);
		Swizzle(WriteArray, ReadArray, WriteOffset, ReadOffset + DataWidth*(SegHeight/2), SegWidth/2, SegHeight/2, DataWidth);
		Swizzle(WriteArray, ReadArray, WriteOffset, ReadOffset + DataWidth*(SegHeight/2) + SegWidth/2, SegWidth/2, SegHeight/2, DataWidth);
	}
}

```


Original post by jasmine, hope it helps.
## Post #3
- Username: PaK
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue May 29, 2007 7:43 pm
- Post datetime: 2007-06-08T13:03:01+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Thx Triton, I found some info about ps2 GS, PSMCT32 and swizzling:

[http://playstation2-linux.com/files/ezs ... zzling.pdf](http://playstation2-linux.com/files/ezswizzle/TextureSwizzling.pdf)
[http://playstation2-linux.com/download/ ... _code.html](http://playstation2-linux.com/download/p2lsd/sparkys_swizzle_code.html)
[http://playstation2-linux.com/projects/ezswizzle/](http://playstation2-linux.com/projects/ezswizzle/)

that help me much to unswizzle the textures that I extrated. Now I can see lot of 4/8 bit textures, but not all. Here are some shots.




Unswizzling a 32 bit texture you can obtain 4,8 or 16 bit images, my problem now is to know Originaldepth of each image and then switch each case to unswizzle well. By the moment the only weird way I found is unswizzle 32bit to 4bit when sizeX >= 4*sizeY. Obviusly this doesnt work for all cases, for example: original image 4bit 256x512, after swizzle it will become a 32 bit 128x128. Then a flag of original depth must be at header...but isnt or I dont understant it

This is what I supose as the QRS image format:

```
00000010h: 00 00 00 00 00 00 00 00 3F 00 00 00 00 00 00 00 ; ........?.......
00000020h: 00 00 00 00 00 00 00 00 00 00 00 00 07 04 00 50 ; ...............P
00000030h: 03 80 00 00 00 00 00 10 0E 00 00 00 00 00 00 00 ; .€..............
00000040h: 00 00 00 00 00 00 00 00 51 00 00 00 00 00 00 00 ; ........Q.......
00000050h: 80 00 00 00 20 00 00 00 52 00 00 00 00 00 00 00 ; €... ...R.......
00000060h: 00 00 00 00 00 00 00 00 53 00 00 00 00 00 00 00 ; ........S.......
00000070h: 00 84 00 00 00 00 00 08 00 00 00 00 00 00 00 00 ; .„..............
```


```
{
  UCHAR8 headerTag[32]
  UCHAR8 dummy1[12] = 0x00
  UCHAR8 ImageType
  UCHAR8 unknow1
  UINT16 dummy2 = 5
  UCHAR8 headerTag2[16]
  UINT64 dummy3 = 0
  UINT64 QTag = 0x51
  UINT32 sizeX
  UINT32 sizeY
  UINT64 RTag = 0x52
  UINT64 dummy4 = 0
  UINT64 STag = 0x53
  UINT32 unknow2
  UCHAR8 dummy4[12]
}

ImageType: 07 for images, [47, 0B, 27, 87] for palettes
unknow1: 00 for palettes, [01,02,04,08,10,20,40] for images
unknow2: from [0x8040] to [C000]


```


The other problem are some images are bad, that seems not 4 or 8bit, either 16bit, or bad way extracted, pehaps unknow flags mean files per qrs or layers or blocs of subimages.. Here are some debugs of images found:

[http://personales.ya.com/paks/tmp/debug.rar](http://personales.ya.com/paks/tmp/debug.rar)

I have founded fonts, map_textures, characters, flares, effects, etc.. but big problem is that all menu textures and resources are in a pak files, and I cant extract them because surely are compressed/encrypted.

More info about this pak files:
[viewtopic.php?t=2641](http://forum.xentax.com/viewtopic.php?t=2641)
## Post #4
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2007-06-10T00:21:36+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

"unknow2" contained the size of image data.

the formular may look like this:
("unknow2" & mask) * sizeof(DQWord) = imageWidth * imageHeight * imageDepth
where mask = 0x7FFF; sizeof(DQWord) = 16Byte

since all swizzled image are become 32bit in image depth, the size may be useless.

The header just look a little bit similar to Soul Calibur 3.
it tells *how to load* instead of *how to use* of the image data.
i think that it hard to know the originl depth by this header.
in sc3, the orginal image dimension was stored at another place.
## Post #5
- Username: PaK
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue May 29, 2007 7:43 pm
- Post datetime: 2007-06-23T14:51:50+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Thx Mike!, I didnt note that but u are right, unknow2 is the masked size of image. As you say, that seems in the direct way to load it to ps2 GS by PSMCT32.

Searching more I have found something interesting, the FOD header, that seem to contain the filenames, and I still dont know if there is also original sizex,sizey, depth or image_offset:

```
00038dadh: B0 03 FE 00 04 00 02 9C FE 00 18 FE B0 01 6C 61 ; °.þ....œþ..þ°.la
00038dbdh: 6E 67 75 61 67 65 5F 73 65 6C 65 63 74 5F 30 30 ; nguage_select_00
00038dcdh: 30 00 18 FE B0 01 6C 61 6E 67 75 61 67 65 5F 73 ; 0..þ°.language_s
00038dddh: 65 6C 65 63 74 5F 30 30 31 00 18 00 80 FE 01 6C ; elect_001...€þ.l
00038dedh: 61 6E 67 75 61 67 65 5F 73 65 6C 65 63 74 5F 30 ; anguage_select_0
00038dfdh: 30 32 00 18 FE 01 20 00 6C 61 6E 67 75 61 67 65 ; 02..þ. .language
00038e0dh: 5F 73 65 6C 65 63 74 5F 30 30 33 00 18 00 20 00 ; _select_003... .
00038e1dh: 20 00 6C 61 6E 67 75 61 67 65 5F 73 65 6C 65 63 ;  .language_selec
00038e2dh: 74 5F 30 30 34 00 18 FE 01 40 00 6C 61 6E 67 75 ; t_004..þ.@.langu
00038e3dh: 61 67 65 5F 73 65 6C 65 63 74 5F 30 30 35 00 03 ; age_select_005..
```


```
000000d8h: 02 00 03 00 07 00 07 EB 00 04 00 05 00 06 00 08 ; .......ë........
000000e8h: 00 09 00 0A 00 0B 00 02 85 EB 00 11 00 80 EB 01 ; ........…ë...€ë.
000000f8h: 6D 61 69 6E 6D 65 6E 75 5F 30 30 30 00 11 EB 02 ; mainmenu_000..ë.
00000108h: 40 00 6D 61 69 6E 6D 65 6E 75 5F 30 30 31 00 11 ; @.mainmenu_001..
00000118h: EB 02 40 00 6D 61 69 6E 6D 65 6E 75 5F 30 30 32 ; ë.@.mainmenu_002
00000128h: 00 11 00 40 00 40 00 6D 61 69 6E 6D 65 6E 75 5F ; ...@.@.mainmenu_
00000138h: 30 30 33 00 11 EB 02 40 00 6D 61 69 6E 6D 65 6E ; 003..ë.@.mainmen
00000148h: 75 5F 30 30 34 00 11 EB 02 40 00 6D 61 69 6E 6D ; u_004..ë.@.mainm
00000158h: 65 6E 75 5F 30 30 35 00 11 00 20 00 20 00 6D 61 ; enu_005... . .ma
00000168h: 69 6E 6D 65 6E 75 5F 30 30 36                   ; inmenu_006
```


Then I have found that there are lots of images with the exakt qrs format seen before, and others some extrange qrs format, maybe compressed.

The problem now are with the textures bad seen:

- Normal QRS: lots of images didnt match with the size they are suposed to be, for example at progress.unk( the file that content select language menu textures):
   one texture found at position 1758258 is partial view, has sizeX=64, sizeY=32, and totalsize=0x8200 & 0x7FFF *0x10 = 64*32*4 = 8192, but it really has 8196, the result is that is bad unswizzled because there are 6bytes exceded in size, and only can see well the upper part of texture. If i toke the lower 8192, the result is the opposite, lower part of texture is good but now fails the upper. At this case there real size is bigger than the suppossed to be.

texture1 

other texture, found at position 430258 cant view anything, has sizeX=100, sizeY=20, totalsize= 0x8800 & 0x7FFF * 0x10 = 32768, but it only have 20547bytes. Then what is happening to this rare textures?

As all textures are raw 32bit RGBA swizzled, pehaps they are compressed with a special form of RLE, or huffman, but I couldnt determine if they use any special control characters as in RLE.

- special QRS: reallly i cant understant that, why they make other formats of qrs like:

```
0000021dh: 40 C9 80 C9 52 ED FA C9 53 ED 88 FA 00 08       ; @É€ÉRíúÉSíˆú..
```


```
00023ca0h: 6B 00 51 6B 6B 6B 00 10 6B 00 10 6B 00 52 6B 6B ; k.Qkkk..k..k.Rkk
00023cb0h: 6B 6B 6B 6B 6B 00 53 6B 6B 6B 00 40 80 6B 6B 00 ; kkkkk.Skkk.@€kk.
00023cc0h: 08 6B 6B 6B 6B 6B 01 80 6B 00 80 6B 06 80 6B 04 ; .kkkkk.€k.€k.€k.
```


```
00019d47h: AD 00 47 AD 50 03 80 99 00 10 0E 99 99 99 AD 00 ; ­.G­P.€™...™™™­.
00019d57h: 51 99 AD 00 10 AD 00 10 AD 00 52 99 99 99 AD 00 ; Q™­..­..­.R™™™­.
00019d67h: 53 99 AD 00 40 80 99 00 08 99 99 49 42 35 7F 54 ; S™­.@€™..™™IB5T
00019d77h: 4B 3B 7F 5A 50 3E 7F 5B 54                      ; K;ZP>[T
```


compressed? encripted? masked? xored? :S

[http://personales.ya.com/paks/tmp/wfiles.rar](http://personales.ya.com/paks/tmp/wfiles.rar)
[http://personales.ya.com/paks/tmp/samples.zip](http://personales.ya.com/paks/tmp/samples.zip)
## Post #6
- Username: Stuck
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 22, 2008 10:35 am
- Post datetime: 2008-04-22T17:04:38+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Hi All,

I'm having trouble trying to unswizzle some PS2 textures. I've figured out how to unswizzle 8 bit textures by looking at

[http://playstation2-linux.com/download/ ... _code.html](http://playstation2-linux.com/download/p2lsd/sparkys_swizzle_code.html)

but I can't seem to get 4 bit textures unswizzled.

Can anyone help me out? Does anyone have to source to the ezSwizzle app?
The following url doesn't work for me:
[https://playstation2-linux.com:9999/viewcvs/ezswizzle](https://playstation2-linux.com:9999/viewcvs/ezswizzle)

Thanks

[http://download.polytechnic.edu.na/pub4 ... le_bin.zip](http://download.polytechnic.edu.na/pub4/download.sourceforge.net/pub/sourceforge/k/project/ke/kernelloader/Sony%20Linux%20Toolkit/Package%20Update%20Files/ezswizzle/ezSwizzle_bin.zip)

> The Victor Suba code is an extremely fancy tool that supports swizzling from any GS layout to any GS layout.
>
> 
>
> Since the only swizzling you typically want to do is 8to32, 4to32 and 16to32 I've made much simpler functions to do just this for you. They're like memcopy functions made slightly more complicated. Very easy to grasp and they don't require any additional memory though the input texels and output texels may not overlap, enjoy.
>
> 
>
> 
>
> ///////// swizzlers /////////
>
> 
>
> void Swizzle8to32(void * pSwizTexels, const void * pInTexels, const int32 width,
>
>       const int32 height)
>
> {
>
>    // this function works for the following resolutions
>
>    // Width:       any multiple of 16 smaller then or equal to 4096
>
>    // Height:      any multiple of 4 smaller then or equal to 4096
>
> 
>
>    // the texels must be uploaded as a 32bit texture
>
>    // width_32bit = width_8bit / 2
>
>    // height_32bit = height_8bit / 2
>
>    // remember to adjust the mapping coordinates when
>
>    // using a dimension which is not a power of two
>
> 
>
>    for(int y=0; y<height; y++)
>
>       for(int x=0; x<width; x++)
>
>       {
>
>          const uint8 uPen = ((const uint8 *) pInTexels)[y*width+x];
>
> 
>
>          const int32 block_location = (y&(~0xf))*width + (x&(~0xf))*2;
>
>          const uint32 swap_selector = (((y+2)>>2)&0x1)*4;
>
>          const int32 posY = (((y&(~3))>>1) + (y&1))&0x7;
>
>          const int32 column_location = posY*width*2 + ((x+swap_selector)&0x7)*4;
>
> 
>
>          const int32 byte_num = ((y>>1)&1) + ((x>>2)&2);     // 0,1,2,3
>
> 
>
>          ((uint8 *) pSwizTexels)[block_location + column_location + byte_num] = uPen;
>
>       }
>
> }
>
> 
>
> void Swizzle4to32(void * pSwizTexels, const void * pInTexels, const int32 width,
>
>       const int32 height)
>
> {
>
>    // this function works for the following resolutions
>
>    // Width:       32, 64, 96, 128, any multiple of 128 smaller then or equal to 4096
>
>    // Height:      16, 32, 48, 64, 80, 96, 112, 128, any multiple of 128 smaller then or equal to 4096
>
> 
>
>    // the texels must be uploaded as a 32bit texture
>
>    // width_32bit = height_4bit / 2
>
>    // height_32bit = width_4bit / 4
>
>    // remember to adjust the mapping coordinates when
>
>    // using a dimension which is not a power of two
>
> 
>
>    for(int y=0; y<height; y++)
>
>       for(int x=0; x<width; x++)
>
>       {
>
>          // get the pen
>
>          const int32 index = y*width+x;
>
>          const uint8 uPen = (((const uint8
>
>                      *) pInTexels)[(index>>1)]>>((index&1)*4))&0xf;
>
> 
>
>          // swizzle
>
>          const int32 pageX = x & (~0x7f);
>
>          const int32 pageY = y & (~0x7f);
>
> 
>
>          const int32 pages_horz = (width+127)/128;
>
>          const int32 pages_vert = (height+127)/128;
>
> 
>
>          const int32 page_number = (pageY/128)*pages_horz + (pageX/128);
>
> 
>
>          const int32 page32Y = (page_number/pages_vert)*32;
>
>          const int32 page32X = (page_number%pages_vert)*64;
>
> 
>
>          const int32 page_location = page32Y*height*2 + page32X*4;
>
> 
>
>          const int32 locX = x & 0x7f;
>
>          const int32 locY = y & 0x7f;
>
> 
>
>          const int32 block_location = ((locX&(~0x1f))>>1)*height + (locY&(~0xf))*2;
>
>          const uint32 swap_selector = (((y+2)>>2)&0x1)*4;
>
>          const int32 posY = (((y&(~3))>>1) + (y&1))&0x7;
>
> 
>
>          const int32 column_location = posY*height*2 + ((x+swap_selector)&0x7)*4;
>
> 
>
>          const int32 byte_num = (x>>3)&3;     // 0,1,2,3
>
>          const int32 bits_set = (y>>1)&1;     // 0,1            (lower/upper 4 bits)
>
> 
>
>          uint8 &setPix = ((uint8 *) pSwizTexels)[page_location + block_location +
>
>             column_location + byte_num];
>
>          setPix = (setPix & (-bits_set)) | (uPen<<(bits_set*4));
>
>       }
>
> }
>
> 
>
> 
>
> void Swizzle16to32(void * pSwizTexels, const void * pInTexels, const int32 width,
>
>       const int32 height)
>
> {
>
>    // this function works for the following resolutions
>
>    // Width:       16, 32, 48, 64, any multiple of 64 smaller then or equal to 4096
>
>    // Height:      8, 16, 24, 32, 40, 48, 56, 64, any multiple of 64 smaller then or equal to 4096
>
> 
>
>    // the texels must be uploaded as a 32bit texture
>
>    // width_32bit = height_16bit
>
>    // height_32bit = width_16bit / 2
>
>    // remember to adjust the mapping coordinates when
>
>    // using a dimension which is not a power of two
>
> 
>
>    for(int y=0; y<height; y++)
>
>       for(int x=0; x<width; x++)
>
>       {
>
>          const uint16 uCol = ((const uint16 *) pInTexels)[y*width+x];
>
> 
>
>          const int32 pageX = x & (~0x3f);
>
>          const int32 pageY = y & (~0x3f);
>
> 
>
>          const int32 pages_horz = (width+63)/64;
>
>          const int32 pages_vert = (height+63)/64;
>
> 
>
>          const int32 page_number = (pageY/64)*pages_horz + (pageX/64);
>
> 
>
>          const int32 page32Y = (page_number/pages_vert)*32;
>
>          const int32 page32X = (page_number%pages_vert)*64;
>
> 
>
>          const int32 page_location = (page32Y*height + page32X)*2;
>
> 
>
>          const int32 locX = x & 0x3f;
>
>          const int32 locY = y & 0x3f;
>
> 
>
>          const int32 block_location = (locX&(~0xf))*height + (locY&(~0x7))*2;
>
>          const int32 column_location = ((y&0x7)*height + (x&0x7))*2;
>
> 
>
>          const int32 short_num = (x>>3)&1;       // 0,1
>
> 
>
>          ((short *) pSwizTexels)[page_location + block_location + column_location
>
>             + short_num] = uCol;
>
>       }
>
> }
## Post #7
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2015-09-28T17:59:42+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

I know this is a very old post but has anyone figured this out?
I can not get 4bit swizzled PS2 textures to unswizzle.
I have tried every bit of code I can find and they all produce junk
If anyone has some working code for this I'd love to see it!
## Post #8
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-09-28T20:34:05+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

> Reply from Coffee
>
> I know this is a very old post but has anyone figured this out?
I can not get 4bit swizzled PS2 textures to unswizzle.
I have tried every bit of code I can find and they all produce junk
If anyone has some working code for this I'd love to see it!
Try reading the 4 bit indices into a byte array by reading a byte and bitmasking that into two different indices.
Then afterwards run the 8 bit unswizzle on it. It worked for me once.

Read it like this:

```
{
	indicesArray = new byte[width * height];
	for (int y = 0; y < height; y++)
	{
		for (int x = 0; x < width; x += 2)
		{
			byte indices = reader.ReadByte();
			indicesArray[x + y * width] = (byte)(indices & 0x0F);
			indicesArray[(x + 1) + y * width] = (byte)((indices & 0xF0) >> 4);
		}
	}
}

```


And then just call the 8 bit unswizzle on the array.
## Post #9
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2015-09-28T21:16:13+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Thank you!
I'll give it a shot
## Post #10
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2015-09-28T21:39:21+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Does this look right to you? Every 2nd position in the out_img2 is zero.

```
            While x < width

                ' get the pen
                upen = out_img((y * width) + x)

                block_location = (y And (Not &HF)) * width + (x And (Not &HF)) * 2
                swap_selector = (((y + 2) >> 2) And &H1) * 4
                posY = (((y And (Not 3)) >> 1) + (y And 1)) And &H7
                column_location = posY * width * 2 + ((x + swap_selector) And &H7) * 4

                byte_num = ((y >> 1) And 1) + ((x >> 2) And 2) ' 0,1,2,3

                out_img2(block_location + column_location + byte_num) = upen

                x += 1
            End While
            x = 0
            y += 1
        End While
```


edit:
This is how I load the out_img array:

```
            'get byte from img_bytes
            'split and store upper and lower nibbles
            i = img_bytes(p)
            u = ((img_bytes(p) And &HF0) >> 4) * 4
            l = (img_bytes(p) And &HF) * 4

            out_img(pos) = l
            out_img(pos + 1) = u
 
            pos += 2
        Next

```
## Post #11
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2015-09-29T05:57:03+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

3 days... sore eyes... frustration to near anger.
I still can not get this thing to unswizzle.
I found this and will dig deeper later but because its hard to find different ways of doing this, Im posting this here.
Im not even sure it will work for anyone.
(Wish we had spoiler tags here)

```
    {
        public const int ID = 2;
        private int _size;
        public const string FourCC = "TMX0";
        private int _unknownField1;
        private bool _hasCLUT;
        private PixelFormats _CLUTFormat;
        private ushort _width;
        private ushort _height;
        private PixelFormats _pixelFormat;
        private byte _mipMapCount;
        private byte _mipMapK;
        private byte _mipMapL;
        private ushort _unknownField2;
        private int _textureID;
        private int _clutID;
        private string _comment;
        private Bitmap _bitmap;
        public Bitmap BitmapImage { get { return _bitmap; } }
        public string Comment 
        {
            get { return _comment; }
            set
            {
                if (Encoding.ASCII.GetByteCount(value) > 28)
                    throw new ArgumentException("Description length can not be longer than 28 characters");
                _comment = value;
            }
        }

        public static byte ConvertAlphaToPC(byte original)
        {
            if ((int)original - 0x80 <= 0)
                return (byte)(((float)original / 0x80) * 0xFF);
            else
                return (byte)(0xFF - ((((float)original - 0x80) / 0x80) * 0xFF)); //wrap around
        }

        public static byte ConvertAlphaToPS2(byte original)
        {
            return (byte)(((float)original / 0xFF) * 0x80);
        }

        public static void ReadPSMCT32(BinaryReader reader, int width, int height, out Color[] colorArray)
        {
            colorArray = new Color[height * width];
            for (int i = 0; i < colorArray.Length; i++)
            {
                uint color = reader.ReadUInt32();
                colorArray[i] = Color.FromArgb(
                    (byte)ConvertAlphaToPC((byte)((color >> 24) & 0xFF)),
                    (byte)(color & 0xFF),
                    (byte)((color >> 8) & 0xFF),
                    (byte)((color >> 16) & 0xFF));
            }
        }

        public static void ReadPSMCT24(BinaryReader reader, int width, int height, out Color[] colorArray)
        {
            colorArray = new Color[height * width];
            for (int i = 0; i < colorArray.Length; i++)
            {
                uint color = reader.ReadUInt32();
                colorArray[i] = Color.FromArgb(
                    (byte)0xFF,
                    (byte)(color & 0xFF),
                    (byte)((color >> 8) & 0xFF),
                    (byte)((color >> 16) & 0xFF));
            }
        }

        public static void ReadPSMCT16(BinaryReader reader, int width, int height, out Color[] colorArray)
        {
            colorArray = new Color[width * height];
            for (int i = 0; i < colorArray.Length; i++)
            {
                ushort color = reader.ReadUInt16();
                    colorArray[i] = Color.FromArgb(
                    (byte)0xFF,
                    (byte)((color & 0x001F) << 3),
                    (byte)(((color & 0x03E0) >> 5) << 3),
                    (byte)(((color & 0x7C00) >> 10) << 3));
            }
        }

        public static void ReadPSMCT16S(BinaryReader reader, int width, int height, out Color[] colorArray)
        {
            colorArray = new Color[width * height];
            for (int i = 0; i < colorArray.Length; i++)
            {
                short color = reader.ReadInt16();
                colorArray[i] = Color.FromArgb(
                (byte)0xFF,
                (byte)((color & 0x001F) << 3),
                (byte)(((color & 0x03E0) >> 5) << 3),
                (byte)(((color & 0x7C00) >> 10) << 3));
            }
        }

        public static void ReadPSMT8(BinaryReader reader, int width, int height, ref Color[] clutArray, out Color[] colorArray)
        {
            colorArray = new Color[width * height];
            for (int y = 0; y < height; y++)
            {
                for (int x = 0; x < width; x++)
                {
                    colorArray[x + y * width] = clutArray[reader.ReadByte()];
                }
@h@            }
        }

        public static void ReadPSMT4(BinaryReader reader, int width, int height, ref Color[] clutArray, out Color[] colorArray)
        {
            colorArray = new Color[width * height];
            for (int y = 0; y < height; y++)
            {
                for (int x = 0; x < width; x+=2)
                {
                    byte indices = reader.ReadByte();
                    colorArray[x + y * width] = clutArray[indices & 0x0F];
                    colorArray[x + 1 + y * width] = clutArray[(indices & 0xF0) >> 4];
                }
            }
        }

        public static void TilePalette(Color[] colorArray, out Color[] newColorArray)
        {
            newColorArray = new Color[colorArray.Length];
            int newIndex = 0;
            int oldIndex = 0;
            for (int i = 0; i < 8; i++)
            {
                for (int x = 0; x < 8; x++)
                {
                    newColorArray[newIndex++] = colorArray[oldIndex++];
                }
                oldIndex += 8;
                for (int x = 0; x < 8; x++)
                {
                    newColorArray[newIndex++] = colorArray[oldIndex++];
                }
                oldIndex -= 16;
                for (int x = 0; x < 8; x++)
                {
                    newColorArray[newIndex++] = colorArray[oldIndex++];
                }
                oldIndex += 8;
                for (int x = 0; x < 8; x++)
                {
                    newColorArray[newIndex++] = colorArray[oldIndex++];
                }
            }
        }

        public TMX0(string sourceFilePath)
        {
            using (BinaryReader reader = new BinaryReader(new FileStream(sourceFilePath, FileMode.Open)))
            {
                ReadTMX0(reader);
            }
        }

        public TMX0(BinaryReader reader)
        {
            ReadTMX0(reader);
        }

        public void ReadTMX0(BinaryReader reader)
        {
            if (reader.ReadInt32() != ID)
                Console.WriteLine("WARNING: TMX0 Chunk ID mismatch!");
            _size = reader.ReadInt32();
            if (new string(reader.ReadChars(4)) != FourCC)
            {
                Console.WriteLine("This is not a TMX file!");
                return;
            }
            _unknownField1 = reader.ReadInt32();
            _hasCLUT = (reader.ReadByte() == 1 ? true : false);
            _CLUTFormat = (PixelFormats)reader.ReadByte();
            _width = reader.ReadUInt16();
            _height = reader.ReadUInt16();
            _pixelFormat = (PixelFormats)reader.ReadByte();
            _mipMapCount = reader.ReadByte();
            _mipMapK = reader.ReadByte();
            _mipMapL = reader.ReadByte();
            _unknownField2 = reader.ReadUInt16();
            _textureID = reader.ReadInt32();
            _clutID = reader.ReadInt32();
            _comment = new string(reader.ReadChars(28)).Replace("\0", "");

            Color[] tmp;
            Color[] palette = null;

            if (_hasCLUT)
            {
                switch (_CLUTFormat)
                {
                    case PixelFormats.PSMCT32:
                        ReadPSMCT32(reader, 16, 16, out palette);
                        TilePalette(palette, out tmp);
                        palette = tmp;
                        break;
                    case PixelFormats.PSMCT24:
                        ReadPSMCT24(reader, 16, 16, out palette);
                        TilePalette(palette, out tmp);
                        palette = tmp;
                        break;
                    case PixelFormats.PSMCT16:
                        ReadPSMCT16(reader, 8, 8, out palette);
                        break;
                    case PixelFormats.PSMCT16S:
                        ReadPSMCT16S(reader, 8, 8, out palette);
                        break;
                    default:
                        Console.WriteLine("WARNING: Unknown CLUT format! Format: {0}", _CLUTFormat);
                        return;
                }
            }

            Color[] image = null;

            switch (_pixelFormat)
            {
                case PixelFormats.PSMCT32:
                    ReadPSMCT32(reader, _width, _height, out image);
                    break;
                case PixelFormats.PSMCT24:
                    ReadPSMCT24(reader, _width, _height, out image);
                    break;
                case PixelFormats.PSMCT16:
                    ReadPSMCT16(reader, _width, _height, out image);
                    break;
                case PixelFormats.PSMCT16S:
                    ReadPSMCT16S(reader, _width, _height, out image);
                    break;
                case PixelFormats.PSMT8:
                    ReadPSMT8(reader, _width, _height, ref palette, out image);
                    break;
                case PixelFormats.PSMT4:
                    ReadPSMT4(reader, _width, _height, ref palette, out image);
                    break;
                default:
                    Console.WriteLine("WARNING: Unknown pixel format! Format: {0}", _pixelFormat);
                    break;
            }

            _bitmap = new Bitmap(_width, _height, PixelFormat.Format32bppArgb);
            for (int y = 0; y < _height; y++)
            {
                for (int x = 0; x < _width; x++)
                {
                    _bitmap.SetPixel(x, y, image[x + y * _width]);
                }
            }
        }
    }

    public enum PixelFormats : ulong
    {
        PSMCT32 = 0x00,
        PSMCT24 = 0x01,
        PSMCT16 = 0x02,
        PSMCT16S = 0x0A,
        PSMT8 = 0x13,
        PSMT4 = 0x14,
        PSMT8H = 0x1B,
        PSMT4HL = 0x24,
        PSMT4HH = 0x2C,
        PSMZ32 = 0x30,
        PSMZ24 = 0x31,
        PSMZ16 = 0x32,
        PSMZ16S = 0x3A
    }
```
## Post #12
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-09-29T09:53:34+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Yeah that's my code from a project I had been working on. Hey if you just give me the raw data (palette & indices) along with the width and height you need to convert I'll try to see if my code works on it in case something was lost in translation.
## Post #13
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2015-09-29T15:14:56+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Really?.. Sorry bout that but.. 
These are not single texture files. they are pack .bin files.
If you have Neosis, there is a python script that loads these .bins. 
I can load them.. that's not the issue but you will need to unpack the file.
It's called "fmt_RGBA_Unswizzle.py" and it does work using neo's RAPI unswizzler. (Can't get that code)
It will show you how to unpack the .bin

I'll PM you with a link to download these .bin files. Its probably copyrighted and I don't want trouble.
Im also sending you a zip with the files exported from Neosis so you know what they are spose to look like 
Thanks !
## Post #14
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2015-10-04T20:36:19+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

Ok.. 
After giving up on this for time, I decide to look at it again.
I found this code.

```
        public static void UnSwizzle8(byte[] Buf, int Width, int Height, int Where)
        {
            // Make a copy of the swizzled input
            byte[] Swizzled = new byte[Buf.Length - Where];
            Array.Copy(Buf, Where, Swizzled, 0, Swizzled.Length);

            for (int y = 0; y < Height; y++)
            {
                for (int x = 0; x < Width; x++)
                {
                    int block_location = (y & (~0xf)) * Width + (x & (~0xf)) * 2;
                    int swap_selector = (((y + 2) >> 2) & 0x1) * 4;
                    int posY = (((y & (~3)) >> 1) + (y & 1)) & 0x7;
                    int column_location = posY * Width * 2 + ((x + swap_selector) & 0x7) * 4;

                    int byte_num = ((y >> 1) & 1) + ((x >> 2) & 2);     // 0,1,2,3

                    Buf[Where + (y * Width) + x] = Swizzled[block_location + column_location + byte_num];
                }
            }
        }
```


It looks the same as all the code I have found and still.. the texture un-swizzles wrong. In fact, Its not even close.
I really would like to sort this out.
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-05T04:45:54+00:00
- Post Title: Sparking Neo ( PS2 ) texture files

> Reply from Coffee
>
> If you have Neosis, there is a python script ... called "fmt_RGBA_Unswizzle.py" ...
Where can i find this python script? Search doesn't return anything except your post.
## Post #16
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2015-10-05T15:19:20+00:00
- Post Title: Re: Sparking Neo ( PS2 ) texture files

Its part of Neosis plugins under Python
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-05T19:19:42+00:00
- Post Title: Re: Sparking Neo ( PS2 ) texture files

Its not part of mine and its not included with a newer build package from here either
[http://www.richwhitehouse.com/index.php ... sv4165.zip](http://www.richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4165.zip)
and neither google or XeNTaX site search returns anything. Can you share this script please?  

edit
nevermind, Futballo sent me a link to the script
It is here if anyone else is curious
[https://www.dropbox.com/s/rywzcpsfgb6pe ... le.py?dl=0](https://www.dropbox.com/s/rywzcpsfgb6pec6/fmt_RGBA_Unswizzle.py?dl=0)
## Post #18
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2015-10-11T18:55:47+00:00
- Post Title: Re: Sparking Neo ( PS2 ) texture files

> Reply from AceWell
>
> Its not part of mine and its not included with a newer build package from here either
http://www.richwhitehouse.com/index.php ... sv4165.zip
and neither google or XeNTaX site search returns anything. Can you share this script please?  

edit
nevermind, Futballo sent me a link to the script
It is here if anyone else is curious
https://www.dropbox.com/s/rywzcpsfgb6pe ... le.py?dl=0
Strange.. I downloaded Neosis and it was 2 folders in under plugins under python.
No big.. 
If you get this working please let me know. I spent 3 days trying to unswizzle those bin textures.
Happy coding...
## Post #19
- Username: zetper
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 23, 2014 2:39 am
- Post datetime: 2016-04-20T23:20:36+00:00
- Post Title: Re: Sparking Neo ( PS2 ) texture files

> Reply from AceWell
>
> Its not part of mine and its not included with a newer build package from here either
http://www.richwhitehouse.com/index.php ... sv4165.zip
and neither google or XeNTaX site search returns anything. Can you share this script please?  

edit
nevermind, Futballo sent me a link to the script
It is here if anyone else is curious
https://www.dropbox.com/s/rywzcpsfgb6pe ... le.py?dl=0
Where can i find this python script fmt_RGBA_Unswizzle.py ?
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-04-20T23:25:21+00:00
- Post Title: Re: Sparking Neo ( PS2 ) texture files

here  


 fmt_RGBA_Unswizzle.zip
(2.32 KiB) Downloaded 113 times
## Post #21
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2017-04-20T08:47:40+00:00
- Post Title: Re: Sparking Neo ( PS2 ) texture files

> Reply from AceWell
>
> here  
fmt_RGBA_Unswizzle.zip 
I have download the noesis core to launch your script but I dont find the noesis.py module

Can someone share it?
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-21T01:39:16+00:00
- Post Title: Re: Sparking Neo ( PS2 ) texture files

not sure what you mean, all dependencies are included with the Noesis installation, 
you just need to place the python plugin into the \noesis\plugins\python folder.
## Post #23
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2017-04-21T08:36:49+00:00
- Post Title: Re: Sparking Neo ( PS2 ) texture files

> Reply from AceWell
>
> not sure what you mean, all dependencies are included with the Noesis installation, 
you just need to place the python plugin into the \noesis\plugins\python folder.

EDIT: Found it and working! thanks

A question, where can I see the noesis methos? I mean, the documentation, to be able to write a script for it.

EDIT: I found those methos haha, :p
