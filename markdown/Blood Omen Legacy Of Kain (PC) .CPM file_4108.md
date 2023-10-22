## Post #1
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2010-02-02T21:30:36+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .CPM file

Hi, i'm trying to figure format of that file: 


 file.zip
(51.22 KiB) Downloaded 34 times



This is (possibly) tile image file from Blood Omen 1 PC version, bunch of images compressed with some clever technique. 

What i'am figured out:

// pos /  description
// 0: 4 bytes - data size
// 4: 4 bytes - ?
// 8: 4 bytes - ?
// 12: 4 bytes - ?
// 16: 4 bytes - ?
// 20: 4 bytes - ?
// 24: 2 bytes - ?
// 26: colormap chunks
// {
//     8 bytes - coding 4 16-bit colors (palette chunk)
//     1 byte - 'separator byte', 255 if there is another chunk, otherwize break 
// }
// x: image data

image data is somewhat stream compressed with 255 byte being separator. I'm guessing each data chunk (from 255 to 255) is encoded with certain palette chunk using 2-bit palette (each byte codes 4 pixels). But i got stuck determining futher info. Maybe i'm got in the wrong way.

in the zip archive you will found:
 file.dat - a file
 file_bytemap.tga - file part bytemap (each pixel of image is a byte)
 file_only_255_with_trailing.bat - this is only data part with only 255 pixels and their trail pixel showing stream structure 
 file_palette_chunks.tga - palette chunks (4x64 image, each row is chunk), this file has 55 chunks

please help!
