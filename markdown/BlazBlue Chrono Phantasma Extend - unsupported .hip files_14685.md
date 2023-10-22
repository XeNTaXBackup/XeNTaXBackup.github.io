## Post #1
- Username: appleken
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 26, 2016 6:20 am
- Post datetime: 2016-07-26T15:32:49+00:00
- Post Title: BlazBlue: Chrono Phantasma Extend - unsupported .hip files

First time poster here, please bear with me  

There's hip files in this game that seem to contain character sprites, but the format for some of the .hip files has changed since the older games and I'd like to figure out how to extract them.

Things I've tried:

 exah3pac from http://asmodean.reverse.net/pages/exah3pac.html - this extracts one type of hip file with ID 0x0101, compression type identified as 8bit RLE. These seem to contain sprites for secondary assets that aren't the main character sprite (weapons, flames, etc.). The type I'm interested (0x0410) in is explicitly stated to be not supported by this code.
 Basic python script to create the image that loads the palette and reads the data as indexed colors, I included the output below.


My understanding of the structure of these hip files is as follows:

0x000 to 0x030 - HIP file header with file information
0x040 to 0x430 - 32 bit palette with 256 entries
0x440 - First two integers are repeated info found in HIP file header (seems to be related to resolution), next 8 bytes always 0's
0x450 onwards - raw data seems to begin, though the first 8 bytes almost look like they could be some additional header data? 
I read up a bit on texture swizzling but I'm not sure if that's what is going on here with the raw data. 

I included a sample hip file in the attachment.

EDIT: I forgot to add another file with the same naming scheme, .jonbin files. In total it seems to be three files: *.hip files, *.hpl files and *.jonbin files. This jonbin file seems to have a header which has JONB followed by filename.bmp in all cases, so it might help in putting together the data from the hip file correctly, just have no idea how.
[sample.zip](https://xentaxbackup.github.io/file/11381_sample.zip)
