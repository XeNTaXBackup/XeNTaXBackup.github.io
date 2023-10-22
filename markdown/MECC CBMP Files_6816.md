## Post #1
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-20T05:09:33+00:00
- Post Title: MECC CBMP Files

Sorry for the additional post on this subject, but I think at this point the thread needs to be in this section since it's a graphic file format I'm dealing with.

Basically, the files I'm trying to demystify are what I think are RLE bitmap files missing the correct headers.  Instead of the regular 40 byte bitmap header, each file has a slimmed down 14 byte header with image specific information in it.  The color palette that belongs to these images resides in a separate directory called "COLRLST."

I have all the parts to make a bitmap here, but I can't seem to get it to work.  The structure of the CBMP image file is this:

01 00   <-- first 2 bytes.  I believe this is telling us that it is RLE-8 compression
XX XX  <-- size x
XX XX <--  size y
0E 00 00 00 <-- size of compressed header
XX XX XX XX <--size of bitmap data
XX XX ....  <---  RLE Bitmap Data

The color list file that is the palette for the images seems incomplete, though I am hardly an expert at this.  Does a 256 color bitmap need to have 256 colors in the palette?  If it doesn't, do zeros have to pad out the rest of the 1024 bits for the color palette?  Does the palette information start directly after the 40 byte bitmap header?

I'm attaching a couple CBMP files and the Colorlist file for anyone who is experienced with bitmaps or can help me out.  

Any help would be greatly appreciated.

Thanks,
[extract.rar](https://xentaxbackup.github.io/file/4361_extract.rar)
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-07-27T10:26:44+00:00
- Post Title: MECC CBMP Files

So, uh, is anyone here willing to reverse-engineer this format? I've been waiting for someone to tap into this for my American Girls Premiere modding experiments.
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-08-31T04:08:40+00:00
- Post Title: MECC CBMP Files

It's like I'm talking to air here. Can't anyone actually lend a hand?
## Post #4
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2016-09-08T18:47:23+00:00
- Post Title: MECC CBMP Files

Okay!  

Well, it's been a few years, but I decided to take another crack at this.  After re-reading all my old threads on this, and taking another look at everything, I've discovered some new things. 

I've made a small change to my initial QuickBMS script so that it doesn't extract different files with the same name and prompt you to overwrite the old one.  This was happening with the font files and colorlist files.

Unlike the main game archive, the file headers appear to be using little endian numbers.

I've been focusing on the CBMP files.  Here's a list of what I believe is at each offset of the 14 byte header:

00 01 : A 2 byte value that shows the type of compression used on the Bitmap pixel data.  Most are "01" I believe for RLE 8 bit compression.
02 03: A 2 byte value of the horizontal size of the image.
04 05: A 2 byte value of the vertical size of the image.
06 07 08 09: Offset of the first byte of Bitmap Data
10 11 12 13: Length of Bitmap Data in bytes.

I've also made progress on the COLORLST files that are extracted from the archive.  As far as I can tell, there are 2 of them and they're identical, not sure why.  But the basic format of them appears to be:

00 01: A 2 byte value of the number of colors in the color palette. 
02 03...etc : the color palette entries as RR GG BB 00.

It looks like a color palette ripped straight out of a .BMP file, but i've tried building a bitmap file by hand and adding the palette from the COLORLST and bitmap data from the CBMP files, but have wound up with a garbled mess.  

I think the problem lies in figuring out what type of compression is actually being used on the bitmap data pulled out of the CBMP file.  

I'm attaching the QuickBMS script, as well as the CBMP file, COLORLST file, and the bitmap I made myself.  Can someone take a look at this bitmap file and tell me if i did something wrong?  I'm stumped.  :/

```
Get HEADERSIZE Short;
Get UNK1 Long;
IDString "MECC";
Goto 0x56;
Get DIRS Short;
Get FILES Long;
Math DIRS *= 16;
Math DIRS += 92;
Goto DIRS;
For i = 0 < FILES;
Getdstring TYPE 0x08;
Get NAMEV Long;
Set NAME = "";
String NAME += i;
String NAME += ".";
String NAME += NAMEV;
String NAME += ".";
String NAME += TYPE;
Get OFFSET Long;
Get FILESIZE Long;
log NAME FILESIZE OFFSET;
Set NAME = "";
next i;
```


Here's a link to the files: [http://www.fast-files.com/getfile.aspx?file=121020](http://www.fast-files.com/getfile.aspx?file=121020)
[test2.bmp](https://xentaxbackup.github.io/file/11676_test2.bmp)
## Post #5
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2016-09-10T01:34:23+00:00
- Post Title: MECC CBMP Files

Five years that is. The case with A Treehouse of my Own was rather trivial, as Imaginengine merely used TGAs with a different header or something.
## Post #6
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2016-09-10T14:51:10+00:00
- Post Title: MECC CBMP Files

New news!

I figured out what that first value is in the CBMP files and it makes the format make a little more sense.  I first thought the "01 00" value at the beginning of each file had to do with the compression algorithm used on the bitmap data, but i was wrong.  It's an index number.  I noticed that the larger CBMP files had a value at the beginning that was larger than "01 00."  

Basically, each CBMP file has the potential of having multiple bitmaps inside of it.  This first value shows you how many are in it.  The format is:

1. # of bitmaps in CBMP file
2. All headers for each bitmap showing Xsize, Ysize, offset of bitmap data, length of bitmap data
3. All bitmap data

Here's a screenshot of one of the multi-entry files.  Notice how at offset 00 it's a value of "37," and the find feature in Hex Workshop found the CBMP headers 37 times!


[CBMP_Index.png](https://xentaxbackup.github.io/file/11689_CBMP_Index.png)
## Post #7
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2016-09-10T15:49:14+00:00
- Post Title: MECC CBMP Files

Some more updates:

The RLES files seem to have the same exact header format as the CBMP files, but the byte order is Big Endian instead of Little.  Not sure why.

The CBMP appear to have a second header at the start of the bitmap data.  It's 12 bytes long and the first byte is always "0c" aka "12" in decimal, the length of the header.  The values stored in it don't seem to make any sense to me.  My theory is that they're variables passed to the program and have something to do with non-bitmap related stuff.


These are just some headers pulled from the start of the CBMP bitmap data so you can see what I'm talking about:

0C0003019C010000004C040002DEE6C6.......
0C000301C0000000004C040001DEE6C0.......
0C00030144770100004C040024DBC31D.......
0C00030114200200004C04002BD4DB1D.......
0C000301D6530300002C010062DDD6DE........
## Post #8
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2016-09-10T18:12:01+00:00
- Post Title: MECC CBMP Files

Okay, so I pretty much verified the CBMP header at this point.

I did a test.  The icons in the game are measured at 80x80 pixels.  I found a CBMP i suspected of being one of them given the values, and found it in the archive and changed the BMP data to all 00's.  I launched the game, and found this waiting for me.

I just need to figure out how the hell this bitmap data is compressed/encoded.  Anyone with experience in RLE compression want to lend a hand?
[mecc mod.png](https://xentaxbackup.github.io/file/11690_mecc mod.png)
## Post #9
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2016-09-10T19:05:43+00:00
- Post Title: MECC CBMP Files

In an effort to try and figure out how the bitmap data was encoded, I modded the archive again and pasted "FF" over the 2nd half of the Bitmap Data only and left the rest as is.  This was the result.

I'm not really sure what it means.  I also tried removing/modifying that 2nd header that appears right before the bitmap data as well (the one that begins with "0C").  Modifying that header caused the program to crash when the icon was loaded.  I think that second header might be more data crucial to the image itself.

I don't get why if it's Bitmap or DIB data that it would be drawing the pixels in the order that it's drawing them in.  I thought Bitmaps were drawn one horizontal row at a time?   This seems to be drawing it in a top to bottom fashion in blocks, rather than horizontal rows like a printer.  All I did to the bitmap data was change the second half of it to all "FF's" and got this result.  

I'm stumped again.
[meccmod2.png](https://xentaxbackup.github.io/file/11691_meccmod2.png)
## Post #10
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2016-09-10T20:29:08+00:00
- Post Title: MECC CBMP Files

I alternated ff and 00 randomly in the bitmap data to see what would happen, and all changes appear to happen in 8 pixel by 8 pixel blocks.  I think that's how the images are encoded.  


Is this a known image format?  Seems weird.
[meccmod3.png](https://xentaxbackup.github.io/file/11692_meccmod3.png)
## Post #11
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2016-09-11T06:07:30+00:00
- Post Title: MECC CBMP Files

That's some findings you got there. But how'd you repack the files into their respective archives? The localisation files seem more or less trivial to edit as the strings are exposed and aren't encoded in some weird way, but editing them in a hex editor seems kludgy and as such may not account for longer or shorter text entries.
## Post #12
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2016-09-11T14:43:48+00:00
- Post Title: MECC CBMP Files

I didn't repack it.  I was directly modifying the bitmap data in the archive itself at the file's offset just for testing.

I have a feeling that repacking is going to be a whole other beast to tackle.
## Post #13
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2016-09-12T01:04:57+00:00
- Post Title: MECC CBMP Files

> Reply from jawharp
>
> I didn't repack it.  I was directly modifying the bitmap data in the archive itself at the file's offset just for testing.

I have a feeling that repacking is going to be a whole other beast to tackle.

From the looks of it it may be similar to the archive formats as used in the early GTA games in terms of how they're packed, i.e. a header, a list/directory of what's inside, and the files themselves being stacked together at different offsets.
