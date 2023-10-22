## Post #1
- Username: sakamaka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 19, 2011 2:41 am
- Post datetime: 2012-01-16T21:32:13+00:00
- Post Title: [PS2] Fire Pro Wrestling Returns - Texture format

Hello everyone!

Recently, I've been looking into the format of graphics in Fire Pro Wrestling Returns (FPR) on PS2 ([Youtube video](https://www.youtube.com/watch?v=Q7jzDsu5L5s)).

Basically, all game resources are lumped in one .ROM file. Inside this file, there are sections marked with unique headers (probably there's an embedded file system, but I didn't look into that). It seems like the graphics are archived under TXA (texture archive?) sections. So far, this is what I was able to find about the format of TXA:

TXA header (length: variable):

offset: 0x0
length: 4
description: magic number 'TXA ' (0x54 0x58 0x41 0x20).

offset: 0x4
length: 2
description: length of TXA section in blocks of 0x2000 (8192) bytes.

offset: 0x6
length: 2
description: number of files.

offset: 0x8
length: 2
description: data start offset (from beginning of TXA).

offset: 0xA
length: 6
description: zeros padding?

offset: 0x10
length: variable (<= data start offset - 0x10)
description: file headers section
-------------------------

The file headers section contains (number of files) entries, each entry has the following format:

File header (length: variable):

offset: 0x0
length: 2
description: header length.

offset: 0x2
length: 2
description: image width?

offset: 0x4
length: 2
description: image height?

offset: 0x6
length: 6
description: ???

offset: 0xC
length: header length - 0xC
description: file name (terminated with one or more 0x0).
-------------------------

The part starting at 0x6 in each header is the part I couldn't decode. However, it seems like it contains the specification of the bit depth, presence of color maps, and maybe the offset of file start.
The first two bytes seem to always start as 0x0 0x0 and then increase with each consequent entry.
The third byte seems to always have an even value: 0x2, 0x4, 0x6, 0x8, 0xA, 010.
The fourth byte seems to be always 0x13.
The fifth and sixth bytes seem to increase with each consequent entry.

The first two bytes, however, seem to give the offset of the file start (from the end of the header), but I didn't check that.

After the end of the header, the files follow. I have tried to extract the bytes and display them as images, but I couldn't get anything that resembles a valid image. Given the size of the TXA section and the dimensions of the images, it seems like most of the graphics are stored in 8-bit (indexed?) format. Some other files (again, given the size and dimensions) are probably 16 bit (direct color?).

Also, most of the file names have a .tga extension, yet the format of the data does not match the TGA format. Given their size, they don't seem to be RLE either.

The following is a [link to an archive](http://www.mediafire.com/?1jtm9sgze41iu6i) containing four different TXA sections (extracted in separate files). I would much appreciate it if anybody can help with identifying the graphics format and how to decode those bitmaps.
