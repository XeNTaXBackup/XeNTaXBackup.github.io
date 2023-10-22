## Post #1
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-04T23:58:46+00:00
- Post Title: MECC Opening Night Bitmap Files

Hey Guys,

I've successfully written a small tool for extracting files from a game called "Opening Night" made by MECC in the 90's.  

The compression on the bitmap files has me a bit stumped though, and I was wondering if it looked like anything you've encountered before.

I'm 99.9% sure this is data for an indexed color bitmap file cause there is a file called "COLRLST" I extracted that is a color table for 245 colors that the game uses.  The "CBMP" files as they're called in the game archive consist of a stripped down BMP header, including sizeX, sizeY, etc, then the bitmap data itself.  Here's a screen shot of the highlighted bitmap data that's confusing me.  This particular file is 80 by 80 pixels when it's uncompressed.

At first I thought it could be RLE compression, but I don't see any 00's for line breaks and stuff.  Anyone know what kind of compression this is?
[80x80File.png](https://xentaxbackup.github.io/file/15124_80x80File.png)
## Post #2
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-05T05:16:28+00:00
- Post Title: MECC Opening Night Bitmap Files

I started dicking around with changing some of the values in the file data then relaunching the program.  

I first changed the second byte of bitmap data to "c9" (just a random value) and it appears to have changed a color in the image, not the pixel data.  I think there might be additional color information at the beginning of these files after the header I initially posted about.

I then started changing every second byte of bitmap data to "c9" to see if more colors would be replaced and they were.  

I posted some images here so you can see what I'm talking about.


The 80x80 pixel icon I originally posted about.



The byte I changed to "c9"


The result.


More bytes changed to "c9"


The second result.
## Post #3
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2018-11-05T08:39:53+00:00
- Post Title: MECC Opening Night Bitmap Files

It would help if you post a few sample files somewhere along the colorlst file if you want somebody take a look, looking at mere hex code isn't always useful.

The data could be uncompressed for all we know as you've not provided any filesize infos either, alternatively presence of 00s is not mandatory for RLE executions (of which there are many), not all of them declare line ends etc.
## Post #4
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-05T12:49:36+00:00
- Post Title: MECC Opening Night Bitmap Files

Here is a link to some cbmp files and the colorlst file:

[http://s000.tinyupload.com/index.php?fi ... 8712648431](http://s000.tinyupload.com/index.php?file_id=89436660318712648431)

This data is most likely compressed since 80 x 80 pixels = 6400 pixels worth of data, and the file is only 2380 bytes in length.

If anyone wants to take a look, any info you might have would be most appreciated.  Here's what I have for the header info:

offset 00 - 13:
header containing # of images in the cbmp file, horizontal size, vertical size, length of this header, size of bmp data

offset 13 - 25:
second header containing length of second header, i *think* total # of colors, a 4 byte mystery number, then the total number of pixels in the final image. 

offset 26 and on: bitmap data
## Post #5
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2018-11-10T11:11:42+00:00
- Post Title: MECC Opening Night Bitmap Files

I looked at this a bit but there is odd problems, first of all, the colorlist does not match 100% at all vs the screenshot image content, there is noticeable quality deteriorating matching back to it which should not be the case or there is other colorlist that is used as I tried both RGB and BGR orders to be sure.

Other curious thing is the amount of colors chosen 245, one would expect 255, perhaps the remaining 10 were reserved for art specific colors or are used for file encoding method.

Now if we google up BMP compression spec: [https://docs.microsoft.com/en-us/window ... ompression](https://docs.microsoft.com/en-us/windows/desktop/gdi/bitmap-compression)

and we can also test save one of those 80x80 into a bmp with rle indexed, we get 5492 bytes or so and also looking at the data vs spec, it definitely does not look like the BMP RLE method which can't achieve 2391 bytes filesize. There is the possibility of the huffman 1d encoding which is stated to be one method to encode for bmps but it just remains vague mention on the net and most apps just use the RLE method.

Curiously enough, pcx achieves 3917 bytes with it's RLE for comparison and again, it seems ever more likely it is not RLE and we are dealing with something like GIF's LZW compress but that is just a guess.

Would need to figure out which art is which file and have the screenshotted same art match properly into the colorlist so the file encoding can be compared and figured out easier, worst case scenario is reverse engineering the executable relevant code how it accesses those files.
As of now, it can't be told what the precise encoding method is used.
## Post #6
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-10T21:49:06+00:00
- Post Title: MECC Opening Night Bitmap Files

Sadly I figured as much.  I've opened up the exe in OllyDbg and IDA, and I've definitely found the functions that are doing things with CBMP files, but I don't know how to read the assembly and the pseudocode isn't much help either for me.

Here are some files that are in a folder in the archive called "RLES."  I'm pretty sure given the name these are RLE bitmaps.  What I've made of the header so far is: 

2 bytes: # of images in RLE file
2 bytes: Size X
2 bytes: Size Y
4 bytes: offset of pixel data
4 bytes: length of pixel data in bytes

All header values are big endian.  There is no color information, so I'm assuming it's using the same COLORLST file as the CBMP files.

I'm attaching a zip of 4 of the RLE files.  Do these look like regular RLE pixel data?
[MECC RLES files.zip](https://xentaxbackup.github.io/file/15151_MECC RLES files.zip)
## Post #7
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2018-11-11T10:31:33+00:00
- Post Title: MECC Opening Night Bitmap Files

> Reply from jawharp
>
> 
Here are some files that are in a folder in the archive called "RLES."  I'm pretty sure given the name these are RLE bitmaps.  What I've made of the header so far is: 

2 bytes: # of images in RLE file
2 bytes: Size X
2 bytes: Size Y
4 bytes: offset of pixel data
4 bytes: length of pixel data in bytes

All header values are big endian.  There is no color information, so I'm assuming it's using the same COLORLST file as the CBMP files.

I'm attaching a zip of 4 of the RLE files.  Do these look like regular RLE pixel data?

Your header info checks out all good from quick look.

Yeap, look definitely RLE coding, I've looked up the pattern and it seems that for example with file 4016.RLES, the actual pixel data starts by 67,0 (0x43,0x00) where first byte is RLE count so how many times to repeat the next byte, thus 67 times of zero and zero here is possibly background transparent pixels (white is curious choice of background tho). Since full dimension is 76x91, it does make sense so far leaving us with 9 pixels from full width for first line and it does not seem there is any line end markers.

Now then when there is 0x80 (128) given for the RLE count field, it seems to be that you must copy following amount of bytes as is command thus 128=1 byte to copy,129=2 byte,130=3 bytes... and after that fall back to RLE parsing thus every value is RLE unless get 0x80+++ tell to copy as is instead. It should be noted that all data is RLEd, not just background zero pixels from my glance.

In any case, you'll have to code a tool and see if get something sensible from that as raw bytes and of course enough output bytes to fill the full dimension, else there may be still something overlooked.

Oh yes, those CBMP files could be 24-bit with unknown compression thus why color list doesn't match them properly as one explanation.
## Post #8
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-11T14:12:14+00:00
- Post Title: MECC Opening Night Bitmap Files

Thanks for the intel!  I'll start on that tool.

As for the CBMP files being 24-bit, do you think they could still be 24-bit even though the game installer says the game requires 256 Color mode in Windows?
## Post #9
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2018-11-13T09:57:36+00:00
- Post Title: MECC Opening Night Bitmap Files

> Reply from jawharp
>
> Thanks for the intel!  I'll start on that tool.

As for the CBMP files being 24-bit, do you think they could still be 24-bit even though the game installer says the game requires 256 Color mode in Windows?

It's just a one theory for the color mismatch issue, other scenario is that they are also 256 color but there are other color lists matching them (or the missing additional 10 colors) or color list is within under compression or there is look up table that brightens etc the color list colors when app is opened throwing it off but thats not likely.

It would help if could determine what content visually specific CBMP holds by potentially switching them around but given game uses archives this would be tricky at best to swap in them just to get better clue on uncompressed size vs the compressed.

See the png for example, I loaded the colors on it and many are changed if compare to the screenshot original in closer zoom.
[research2x.png](https://xentaxbackup.github.io/file/15171_research2x.png)
## Post #10
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-13T19:51:58+00:00
- Post Title: MECC Opening Night Bitmap Files

So, I wrote a utility to decompress the RLE data and replace the pixels with the entries from the colorlst file.  This is the most progress I've made in a while.  I used 7yuv to view the raw pixel data generated from my tool, and once I learned that the x and y sizes are reversed in the RLES files, I was greeted with this:



It's an asset in the game for a unicorn prop.  Here's a shot of it in the game:



I can't figure out why the colors are all smearing like that.  When I try to add this data into a bmp file, windows says the file is corrupted.  

Not sure what's going on with the colors, but I would call this progress.
## Post #11
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-13T20:01:09+00:00
- Post Title: MECC Opening Night Bitmap Files

Here is the generated pixel color data file.  It is 91 pixels wide by 76 pixels tall.
[4016.RLES.ColorDataAdded.zip](https://xentaxbackup.github.io/file/15172_4016.RLES.ColorDataAdded.zip)
## Post #12
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-13T20:33:31+00:00
- Post Title: MECC Opening Night Bitmap Files

Here's another one.




original in game:



[4002.RLES.zip](https://xentaxbackup.github.io/file/15173_4002.RLES.zip)
## Post #13
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2018-11-13T23:10:39+00:00
- Post Title: MECC Opening Night Bitmap Files

Disregard last 2 posts.  My decompress function had an error.  

It worked!

RLE files handled.  Going to write up something that exports the bitmap files.
[fixedDog.png](https://xentaxbackup.github.io/file/15175_fixedDog.png)
## Post #14
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2018-11-14T05:56:19+00:00
- Post Title: MECC Opening Night Bitmap Files

Looks like my RLE hunch was pretty close since got results, however I realised there is likely a background vs content issue apparently, the zero used as white inside the dog is not supposed to be 'hole' yet the dog outer edges of same zeroes is, it may be that the rle count byte zeros (1-127,0) should be changed to something else in RGB to separate the background (had this issue in other game too...) while 128+ ones kept as white, if this fixes the issue, else you will have to hand paint the edges for any of your own project use as I doubt your just decoding just to view the arts.

You got 4002.rle original to add here? would be useful to check the theory a bit
## Post #15
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-06-15T00:13:44+00:00
- Post Title: MECC Opening Night Bitmap Files

Hey!

So, it's been a while, but I'm back to working on this lifelong puzzle haha.

RLE files are completely done as of last time I was working on this.  I was able to successfully dump all RLE files from the game into regular bitmap images.  They were RLE compressed and used the color table I posted earlier about.

The CBMP files still remain a mystery to me.  I've done some more work on the files and was able to figure out some more information, and get a solid example file that is viewable in the game to work on.

So the CBMP images each have 2 headers: one 12 byte header at the beginning of the cbmp file, and one 12 byte header at the image's data offset in the cbmp file.

The first 2 bytes of a cbmp file is a 16 bit value telling the number of images in the particular cbmp file.
The next 12 bytes (multiplied by the number of images in the file) are the first headers for each image in the file.
The rest of the file is the image(s) data.  At each image's offset, there is a second 12 byte header before the image's data.

Here is what I've been able to deduce about the headers:

1st Header (at the beginning of the file):
X size (16 bit value)
Y size (16 bit value)
Data offset (32 bit value)
Length of image data (32 bit value)

2nd Header (at image offset):
"12", the length of this header (16 bit value)
"259" (16 bit value)
A value, aka the "mystery number" (32 bit value)
The total number of pixels in the final expanded image (32 bit value)

Most of this is straightforward, except for the value of "259" and the "mystery number."  The 259 is the same in every single cbmp file in the game.  I've scrolled through at all of them in an app I made and verified it.  The mystery number, on the other hand, is different in each file.  Some files have the same mystery number, some have different ones, and there doesn't appear to be any apparent rhyme or reason for what the value is.

I'm attaching some example files to this post for anyone interested.  The file 10.cbmp is the one that I think is the most promising for reverse engineering these files.  It is a 223x54 image of the MECC logo that appears in the about screen in the game.  It's mystery number is 11653.  It contains 3 colors.



I've been modifying some values after the 2nd header to see the effect created in the game.  Based on what's happening to the images I don't think these files are compressed with RLE compression.  The changes appear to happen to various unrelated parts of the image.  I've attached 2 images to this post.  One is of the unmodified MECC logo (10.cbmp) in the game's about window.  The second is the same logo with the 2nd byte after the 2nd header changed to "AA."  I think it's weird that it doesn't changed the color on the whole image.



Anyone want to help take a stab at this?
[cbmp_files.zip](https://xentaxbackup.github.io/file/23935_cbmp_files.zip)
## Post #16
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-06-28T05:15:04+00:00
- Post Title: Re: MECC Opening Night Bitmap Files

It looks like an 8x8 tilemap like used in so many older 2D consoles (NES, SMS, SNES...), where indices point to graphic 8x8 tiles. If you mess with the graphics of 1 tile, all the other tiles of the same index are also affected. Don't rule out RLE compression quite yet though, as most games would apply RLE compression to their graphics too. I can't tell exactly the size because there's some blurry DPI scaling applied to the posted image, but 8x8 is common, and assuming 0xDF (223) is the width, then 223/8 looks like about how many 8x8 chunks I see. You can probably find the tilemap and graphics by messing with more bytes afterward. Otherwise, OllyDbg and IDA it is :b...
## Post #17
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-06-28T21:19:33+00:00
- Post Title: Re: MECC Opening Night Bitmap Files

Hey!

Thanks for your reply.  The size is indeed 8x8!  

Do you have any info on references or examples of this tiling method you could reccommend?  Maybe if I can look at another example I can piece together how they were doing it.  Randomly changing bytes has led to some weird stuff and a whole lot of crashes.

How would you go about using Ollydbg and IDA to figure this out?  I've used them in the past for simple stuff, but not really reverse engineering something like this.  Any help is appreciated.  I understand you can't post a detailed tutorial on using Ollydbg or anything, I am just wondering what the broad strokes would be.

Thanks!
## Post #18
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-07-03T10:26:06+00:00
- Post Title: Re: MECC Opening Night Bitmap Files

> Do you have any info on references or examples of this tiling method you could recommend?

Look up how the SNES or Sega Genesis worked (e.g. [https://en.wikibooks.org/wiki/Super_NES ... s_tutorial](https://en.wikibooks.org/wiki/Super_NES_Programming/Graphics_tutorial)) where each tilemap element in the 2D array pointed to an 8x8 graphic tile (0-1023 on the SNES, 0-2047 on the Sega Genesis, 0-255 on the Gameboy), but this case is probably much simpler than those were, probably just a 2D array of uint8 tile indices (and no consideration of tile flipping or subpalette indices).

> How would you go about using Ollydbg and IDA to figure this out?

I haven't used Ollydbg since ~2004, but like any debugger, if you set a breakpoint on the function of interest (e.g. CreateFile in kernel32.dll when the .cbmp file is opened), you can follow how it's moving data around from input to expanded output. Assembly is hard to follow the bigger picture, but it's actually really easy (as a language) to understand what's happening on a per-instruction basis since it's (typically) only a single value being moved or modified by math operation, not a whole complex equation on a line. There are loads of free resources (e.g. [https://en.wikibooks.org/wiki/X86_Assem ... structions](https://en.wikibooks.org/wiki/X86_Assembly/X86_Instructions)).
