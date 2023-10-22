## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-22T14:16:31+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

I try to convert indexed TIM2 to full Color bitmap image with alpha channel.
I 1st create a full color table array(RGBA) by looking at the end of the color table. Then get the index and write to full color pixel eg: colorArray[index].

But the result are not correct? What did I doing wrong?



[DMC3_tim2.rar](https://xentaxbackup.github.io/file/1225_DMC3_tim2.rar)
## Post #2
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2007-06-22T22:47:04+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

I'm glad to see someone trying to correct the mistakes that I had with that program.  I really would like to see some apps come out for the game and graphics format.  This information should tell you all that you need to know about the tim2 file format.  Look in the tim2.h for the header specs.
[Tim2Format.zip](https://xentaxbackup.github.io/file/1228_Tim2Format.zip)
## Post #3
- Username: PaK
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue May 29, 2007 7:43 pm
- Post datetime: 2007-06-23T01:38:18+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

I think that bmp has no standart support for 32bits bitmaps, only if you make your own version of bmp supporting it. I suposse that u know that converting 8bit image indexed with 32bit RGBA palette to 32bit RGBA image without palette, size will become four times greater, lossing the advantatge that image only use 256 colors.

If you only want visualice it well interlaced you can use XnView, Game Grafics Studio or Optix Image Studio for example, and export to the format you want to edit. Also there are batch converters for tim2. 

But if you want to draw the texture in your own aplicattion you have to interlace the palette before calculate colorArray[index], this way:

divide the palette in blocks of 8 RGBA colors, and for every 4 blocks swap it 

1 3
2 4

or what is the same, for every 32 RGBA colors swap

0,  1,  2,   3,   4,   5,  6,   7,  16, 17, 18, 19, 20, 21, 22, 23,
8,  9, 10, 11, 12, 13, 14, 15, 24, 25, 26, 27, 28, 29, 30, 31
## Post #4
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-06-23T09:23:39+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

Isn't your problem related to the fact that your TIM2 files have several palettes? Each palette being to be applied on a specific part of the texture. This is already the case for TIM files. You then use palette #0 for the left part, and palette #1 for the right part.
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-23T13:07:27+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

PmData, the files are 8bits RGBA indexed with only have 1 palette, the correct images above are from photoshop, it works for standard TIM2 but can't export!

And for the interlace stuff, I am really confused!
Is it like this:
for 8bits RGBA of 256 color palette, 256/8=32, so each block have 32 RGBA color?
for the palette samples here (start at 10040). 

block[0,0]=color 01 01 01 80, block[0,1]=color 17 05 02 80
block[1,0]=color 05 08 0E 80, block[1,1]=color 1A 04 01 80

block[0,2]=color 04 0C 17 80, block[0,3]=color 29 00 10 80
block[1,2]=color 22 03 01 80, block[1,3]=color 10 10 11 80

block[0,4]=color 3B 04 04 80, block[0,5]=color 10 17 21 80
block[1,4]=color 10 16 1E 80, block[1,5]=color 3C 04 0E 80
..

now lookup:
colorAry[4] = block[0,4] = color 3B 04 04 80
colorAry[33] = block[1,2] = color 22 03 01 80

Am I correct?
[256X256.jpg](https://xentaxbackup.github.io/file/1231_256X256.jpg)
## Post #6
- Username: PaK
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue May 29, 2007 7:43 pm
- Post datetime: 2007-06-23T14:07:24+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

Excuse my bad english xD

each block has 8 RGBA colors, then you have 32 blocks for the 256 color palette. Swap block 2 with 3, 6 with 7, and so..

then apply colorArray[index], and thats all. I think it will help you ; )
[file_DMC3_0140_01.zip](https://xentaxbackup.github.io/file/1232_file_DMC3_0140_01.zip)
## Post #7
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2007-06-30T17:02:48+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

So, it's somehow possible the dmc3-tm2 textures editing?
I want the modified textures put into the game.
I try 2 Photoshop plugin out, but not the best. (Tim2Format.8bi, tm2xFormat.8bi)
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-30T22:17:15+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

I don't think there is a ready-made tool out yets! That's what I start my own! It's not hard to convert indexed color to full color(I finally managed), but the other way round is difficult for a beginner like me!

And what's the different between tim2 and tim2x plugin!
## Post #9
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2007-07-02T11:12:56+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

> Reply from fatduck
>
> I don't think there is a ready-made tool out yets! That's what I start my own! It's not hard to convert indexed color to full color(I finally managed), but the other way round is difficult for a beginner like me!

And what's the different between tim2 and tim2x plugin!

Tim2 - Jasmine's plugin, cant' correct handle the alpha channel(if i modify the tim2 image, that is modify the alpha channel)
tim2x - this can not handle the alpha channel, but i can choose many settings by saving (mipmap, 4-32bit format, swizzle and more coding format) I think this is an official plugin, because in the setting window, i see a "Sony" text. But this plugin is created in 2001.
[tm2x.zip](https://xentaxbackup.github.io/file/1247_tm2x.zip)
## Post #10
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-22T12:49:31+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

can anyone help me? i used this swapping trick but i still get errors like so:



texture5.png (10.54 KiB) Viewed 276 times
## Post #11
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-09-22T18:32:58+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

this may be a premultiplied  rgb+a texture , first you need to extract the alpha chanel and rebuild the rgb colors then get the alpha mash to get a valid one...
## Post #12
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-22T19:15:42+00:00
- Post Title: How to convert Indexed TIM2 to Full Color

can you explain in a little more detail please?
