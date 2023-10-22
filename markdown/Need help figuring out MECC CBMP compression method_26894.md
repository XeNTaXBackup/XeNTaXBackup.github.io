## Post #1
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-06-23T19:58:50+00:00
- Post Title: Need help figuring out MECC CBMP compression method

Hey guys,

I've been working on extracting all of the game content from the main archive of a 1995 MECC game called "Opening Night."  I've successfully been able to extract and rebuild all of the compressed RLE encoded bitmaps from the game.  There are 2 types of bitmaps in the game however, and the second one, only called "CBMP" files have been a mystery to me for years now.

I'm trying to find out via what method the CBMP image data was compressed.

Here is everything I know about the format for anyone who is interested in taking a look at it:

CBMP files are capable of containing multiple bitmaps in one file.
Each image in the CBMP has 2 12 byte headers, one at the beginning of the file, and one at the offset of the data.

Here is an example of what the file structure would look like for a CBMP file containing one image:

Bytes 00 - 01: 16-bit value of how many images are in this CBMP file
Bytes 02 - 13: First 12 byte header
Bytes 14 - 25: Second 12 byte header
Bytes 26...: Image data

The headers are structured like this:
HEADER 1
X Size in pixels (16-bit value)
Y Size in pixels (16-bit value)
Offset of this image in CBMP file (32-bit value) [at the stated offset would be the second header followed by the image data]
Size of this image's data in CBMP file (32-bit value)

HEADER 2
"12" the length of this header in bytes (16 bit value)
"259" (16-bit value)
A value who's purpose is unknown, aka "mystery number" (32 bit value, varies based on the CBMP file)
The total number of pixels in the final decompressed image (32-bit value)

As for the image data that follows these headers, what I've been able to figure out is that the byte immediately after header #2 is the total number of colors in the image, followed by their values.  Each color value appears to be stored as an 8-bit value that corresponds to the game's color palette (the same palette used for the RLE bitmaps I extracted.)  By altering these values I am able to switch the colors in the CBMP file in-game and have them correspond to the palette I've already extracted.

The color list is where my knowledge of the format stops.  I've randomly changed bits around to achieve changing some pixels' color in game, but it appears to change all other groups of pixels in the image that are of the same number of pixels and the same color.  It looks like it's storing the image in chunks.  I think identical chunks all correspond to single entry in the image data, which made me think it's some sort of LZW compression, but I don't know that much about LZW.  

Here's a picture of the MECC logo in-game unedited, and one that I was able to change the colors of:





I've attached some example files in a zip if anyone wants to take a peak at them.  One is the 223x54 3 color MECC logo from the images above.  The other is an 80x80 icon from the game.  I've also included the color palette file.

If anyone can take a look, all help is appreciated.  Even if it's just telling me what type of compression you think this is.  I'm kind of stumped.

Thanks
[Mecc CBMP Examples.zip](https://xentaxbackup.github.io/file/23968_Mecc CBMP Examples.zip)
## Post #2
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-06-26T20:36:18+00:00
- Post Title: Need help figuring out MECC CBMP compression method

So I opened up the 2 example files at diffnow.com to see if there were any similarities between them.  It looks like there are, but I can't make any sense out of them yet.
[diffnow.png](https://xentaxbackup.github.io/file/23978_diffnow.png)
## Post #3
- Username: LudaX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 01, 2021 6:23 am
- Post datetime: 2023-07-11T19:46:44+00:00
- Post Title: Need help figuring out MECC CBMP compression method

I tried exploring the samples you shared a little bit. Unfortunately haven't figured out how to go from the raw image bytes to pixels yet, but in the process, I created some Kaitai structs to make my exploration easier. Thought I'd share for anyone else exploring this 

CBMP.ksy:

```
  id: cbmp
  title: MECC CBMP File
  file-extension: cbmp
  endian: le
doc: |
  Compressed BMP archive
seq:
  - id: header
    type: header
  - id: images
    type: image
    repeat: expr
    repeat-expr: header.num_images
types:
  header:
    seq:
      - id: num_images
        type: u2
  image:
    seq:
      - id: width
        type: u2
      - id: height
        type: u2
      - id: image_offset
        type: u4
      - id: data_size
        type: u4
    instances:
      image_data:
        pos: image_offset
        type: image_data(data_size)
  image_data:
    params:
      - id: data_size
        type: u4
    seq:
      - id: len_header
        type: u2
      - id: unknown
        type: u2
      - id: mystery
        type: u4
      - id: num_pixels
        type: u4
      - id: num_colors
        type: u1
      - id: palette_colors
        type: u1
        repeat: expr
        repeat-expr: num_colors
      - id: image_data
        size: data_size - num_colors - 13
```

COLRLST.ksy:

```
  id: colrlst
  title: MECC Color Palette
  file-extension: colrlst
  endian: le
doc: |
  MECC Color Palette
seq:
  - id: num_colors
    type: u2
  - id: color_entries
    type: color_entry
    repeat: expr
    repeat-expr: num_colors + 1
types:
  color_entry:
    seq:
      - id: red
        type: u1
      - id: green
        type: u1
      - id: blue
        type: u1
      - id: zero # alpha?
        type: u1
```
## Post #4
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-08-14T22:28:30+00:00
- Post Title: Need help figuring out MECC CBMP compression method

I decided to send a CBMP file's image data to ChatGPT to see if it could figure out what type of compression method it was using.  ChatGPT is convinced that it's LZ77 compression.  I have zero experience with LZ77 compression, so I'm kind of stumped.  I've been trying to watch some videos on it to see if I can figure out how to write a decompressor, but this shit is complicated haha.  I have more to learn about LZ77 it seems.

I also through reading about LZ77 think I figured out the value of "259" and the mystery number in the second header.  I think that's LZ77 info.  I thihnk the 259 refers to the number of symbols in the LZ compression dictionary, and I think the large 32 bit value is a checksum of some kind.
## Post #5
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-08-19T01:30:14+00:00
- Post Title: Need help figuring out MECC CBMP compression method

Alright, call me crazy, but the fact that this compression seems to be lz77 related, and this game was cross platform mac/windwos3.1/windows95 at the time it was released, could it make sense that these were just gifs?  Could this just be the compressed GIF data?

I feel like the more I try to figure this out the further I get.
## Post #6
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-08-19T13:48:15+00:00
- Post Title: Need help figuring out MECC CBMP compression method

I was reading up on old gifs, and they used to utilize the ability to have multiple images stored in the gif file and render them one on top of the other so you could use transparencies to build up a still image out of parts.  This would coincide with the backgrounds in this game, since they contained elements that the characters could walk behind.  I know the backgrounds are CBMP files, and I know they can hold multiple images in them.  This seems like a good bet.  Here's the part where it discusses it:

> The next byte gives us the background color index. This byte is only meaningful if the global color table flag is 1, and if there is no global color table, this byte should be 0.. To understand it you have to remember the original "picture wall" rendering model for GIFs in which sub-images are composited onto a larger canvas. It represents which index in the global color table should be used for pixels on the virtual canvas that aren't overlayed by an image. GIFLIB supports reading and setting this byte, but modern viewers and browsers generally have no use for it.

The original article is here: [https://giflib.sourceforge.net/gifstand ... ained.html](https://giflib.sourceforge.net/gifstandard/LZW-and-GIF-explained.html)
## Post #7
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-08-25T16:23:29+00:00
- Post Title: Need help figuring out MECC CBMP compression method

I've been playing around with swtiching out bits after the header information I know in the Mecc logo in the game credits.  It's produced some weird results.  It does look like the compression of the image is being broken up into 8x8 pixel chunks starting from the top left and going down a column, then starting the next column at the top, and so on.  Here is a picture of the start of the file 10.cbmp that I linked earlier with the header info highlighted and labelled, along with a preview of how the mecc logo looks in the game normally:



I started changing around some values.  Here are some after pictures with the bytes i changed highlighted and the results in game:

Example 1:


Example 2:


Example 3:


Anyone got any ideas how this is being stored or what any of the values in between the modified bytes refer to?  I'm stumped.

Attached also is the 10.CBMP file again for anyone who wants to take a look at it in a hex editor.
[10cbmp.zip](https://xentaxbackup.github.io/file/24269_10cbmp.zip)
## Post #8
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2023-08-26T02:54:29+00:00
- Post Title: Need help figuring out MECC CBMP compression method

It seems that you are very persistent, so I decided to help take a look.
Since it is a windows3.x program, win11 64-bit cannot run. I installed win10 32-bit on the virtual machine and set up a debugging environment.
The game has 16-bit and 32-bit installation packages. The 16-bit version needs to enable the NTVDM function. Here I debugged the 32-bit version of the game.
First create a breakpoint in CreateFileA, but did not find the relevant code to read the cbmp file.
I then searched for the "CBMP" string and placed breakpoints on multiple code references to that string.
After several days of continuous tracking, the location of the key code was confirmed.
sub_409E4A This function is the key function for decompressing data.
At present, the code is still being analyzed. At first glance, it is bit-level compression, similar to the LZH compression algorithm. First, a 32-bit flag is read, and each flag occupies 2 bits, and then processed according to the flag.
Then the game is an 8-bit index image, and the pixels are stored in Tile 8x8, so each block is 64 bytes after decompression.
If you want to see it, you can directly set a breakpoint on the function. Of course, you need to learn some knowledge of 80x86 assembly code instructions.

File structure:

```
//--- 010 Editor v13.0.1 Binary Template
//------------------------------------------------
short   numTex;
struct{
    short   width;
    short   height;
    uint    offset;
    uint    dataSize;
}TexHeader[numTex];

local int i;
for (i=0;i<numTex;i++)
{
    FSeek(TexHeader[i].offset);
    struct{
        ushort  dataOffset;// Relative to data start offset
        byte    flag1;
        byte    flag2;//  if ( *(_BYTE *)(cmpBufferOffset + 3) & 1 )
        int     u2;
        uint    decompressSize;// numBlock = (decompressSize + 63) / 64; BlockSize = 64. Tile 8x8 index color
        byte    data[TexHeader[i].dataSize-12];
    }Data;
}
```
## Post #9
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-08-26T16:48:43+00:00
- Post Title: Need help figuring out MECC CBMP compression method

Holy crap, thanks for the response!

Yeah, i know nothing about reading assembly haha.  This sounds promising, I'm curious what you find!  

I'll try to take a look at sub_409E4A.  I can't read assembly, but I can kind of piece together stuff form ida's pseudocode.  Not sure how accurate that is though.
## Post #10
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-08-26T17:31:52+00:00
- Post Title: Need help figuring out MECC CBMP compression method

Not sure if any of this helps you, but I pasted the function's pseudocode into the Llama 2 chat bot and asked it to explain in general terms how the function was decompressing the data it was reading.  This is what it spat out:  

> The function you provided appears to be a custom implementation of a decompression function, specifically designed to work with a certain type of compressed data stream. Here's a high-level overview of the steps it takes to decompress the data stream:
>
> 
>
> The function initializes several variables:
>
> v10 is set to the address of the compressed data stream.
>
> v11 is set to the address of the first byte of the compressed data stream.
>
> v12 is set to a value calculated from the size of the compressed data stream.
>
> v7 is set to 0.
>
> v8 is set to an initial value (the meaning of which is not immediately clear from the code snippet you provided).
>
> The function then performs a series of operations on the compressed data stream, which appear to be some form of entropy coding or Huffman coding. It's difficult to say for certain without more context, but it looks like the function is exploiting the fact that the compressed data stream contains repeated patterns of bytes, and is using those patterns to encode the data more efficiently.
>
> The function then iterates over the compressed data stream, performing the following operations:
>
> It reads a byte from the compressed data stream and stores it in v8.
>
> It increments v11 to point to the next byte of the compressed data stream.
>
> It updates v6 based on the value of v8. The exact meaning of this step is not clear from the code snippet, but it appears to be some form of bit manipulation or flags manipulation.
>
> It repeats the above steps until a certain condition is met (the exact condition is not clear from the code snippet, but it appears to be related to the value of v6).
>
> Once the loop completes, the function appears to perform some final processing on the decompressed data, such as padding it with 0s or 255s.
>
> The function then returns the decompressed data.
>
> It's worth noting that this is just a high-level overview of the steps the function takes, and there may be important details that are not immediately apparent from the code snippet you provided. Additionally, it's possible that the function is using a custom compression algorithm or technique that is not widely used or documented.

> The decompression function described in the document appears to be a custom implementation of a LZ77-like decompression algorithm. LZ77 is a lossless compression algorithm that uses a fixed-size sliding window of 32 KB to compress data.
>
> 
>
> The algorithm works by searching for repeated patterns in the data and replacing them with a reference to the previous occurrence of the pattern. The reference is stored in a 16-bit value, with the high byte containing the offset of the previous occurrence and the low byte containing the length of the pattern.
>
> 
>
> The decompression function in the document appears to be similar to this, as it uses a sliding window of 256 bytes and searches for repeated patterns in the data. However, there are some differences in the implementation, such as the use of a 16-bit value to store the offset and length of the pattern, and the use of a custom dictionary to store the patterns.
>
> 
>
> It's worth noting that this is not a standard compression algorithm, but rather a custom implementation designed to work with the specific compression format used in the document.
## Post #11
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2023-09-15T06:55:00+00:00
- Post Title: Need help figuring out MECC CBMP compression method

After nearly a month, I only had some time in the evening and finally made some progress.
It has to be said that debugging is very tiring, and it is necessary to constantly debug contextual functions to obtain useful information.

This compression appears to have 4 subtypes. I underestimated it and had to analyze it one by one.

The decompressed data is stored in Tile 8xheight blocks. Because it is 8bpp, each block is always Tile 8x8=64 bytes. It is equivalent to dividing the image into a column with a width of 8 pixels.

Image storage is a block of 8x8, so both the height and width are multiples of 8. If not enough, data padding is required. To restore the image, cropping must be performed.

So you will find that decompression size=storage width * storage height.

Additionally, it seems that there are so many cbmp files, but they share the same color palette: 1008.COLRLST files.
This palette only has 246 colors.
The 8-bit indexed image has 256 colors, which is 10 less.
Through debugging, it was found that the first 10 colors and the last 10 calls in the game were from the system palette.
But I found that some colors are different from the colors in the 1008.COLRLST file and still need to be tracked and debugged.
The attachment 10.dbmp is the decompressed data (and untile) of 10.cbmp, which is the logo of MECC.
10_Tiled.dbmp is the raw data after decompression.

[](https://gifyu.com/image/S4hOn)
[10_dbmp.zip](https://xentaxbackup.github.io/file/24347_10_dbmp.zip)
## Post #12
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-09-15T12:55:55+00:00
- Post Title: Need help figuring out MECC CBMP compression method

Holy shit!

This is far more complicated than I had initially thought.  Excellent work.  If there is any way I can help you should you choose to continue, let me know.  I've stepped back a bit from it since tracing assembly is way above my skillset, and haven't had the time to learn yet.  Thanks for all your help so far!
## Post #13
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2023-09-15T15:49:24+00:00
- Post Title: Need help figuring out MECC CBMP compression method

The debugging process of the color palette was quite smooth, and it was found that they always used the same color palette.
So I dumped the color palette.
The attachment is an extraction tool.
The source code is here, and you can also modify it yourself.
[https://github.com/leeao/DE_MECC_OPENNIGHT_LZCMP](https://github.com/leeao/DE_MECC_OPENNIGHT_LZCMP)

I have only tested a few files and there may be issues.

 
[DE_MECC_OPENNIGHT_LZCMP.zip](https://xentaxbackup.github.io/file/24350_DE_MECC_OPENNIGHT_LZCMP.zip)
## Post #14
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2023-09-17T23:29:44+00:00
- Post Title: Need help figuring out MECC CBMP compression method

HOLY SHIT YOU BEAUTIFUL BASTARD!

lol thank you so much for doing this.  I'm going to test some more files, but from what I'm seeing it works like a charm!

I just told my brother that you did this and that it was like I was talking into a void for 10 years and then you came along.  I feel like Tom Hanks in castaway lol.
