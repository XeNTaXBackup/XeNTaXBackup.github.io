## Post #1
- Username: AnthonyFiveSixTwo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 24, 2008 11:52 am
- Post datetime: 2008-10-24T10:55:34+00:00
- Post Title: Gears of War 2 Compression

The past few days I have been modding Gears of War 2, but now I think its time to move from modding the ini's to actually modding the game assets.

There are many .xxx files which are compressed, The compression I am unsure of but I am aware that the original Gears of War used LZO.

Each file has a header signature of 0x9E2A83C1 at offset 0x00. From there I have seen two formats, The first one being which looks like a table followed by the compressed data, and the second which seems to be just the compressed data.

I am more interested in the files with what seems like a table, here's what I have noted so far. All these values are in Big Endian being that it is for the Xbox 360.

struct xxxHeader{   
   int signature; // Must be 0x9E2A83C1
   int unknown; // Always 0x00020000 (May be a block size)
   int totalCompressedLen; // The total compressed len of every entry in the table added
   int totalDecompressedLen; // The total decompressed len of every entry added

   xxxTableEntry[] tableEntries; // An array of xxxTableEntry blocks 
}

struct xxxTableEntry{
   int compressedLen; // Length of the compressed block
   int decompressedLen; // Length of the decompressed block
}

To get the number of table entries you can use this simple formula.
int totalTableEntries = ( totalDecompressedLen / 0x20000 ) + 1;

It seems that the 0x20000 that is used in the total entries calculation is the same value that the "Unknown" is which also leads me to believe that is a block size.

After the table is the compressed data blocks so the layout looks like the following.

-xxxHeader
-compressedDataBlock[]

For the texture file (".tfc") it is the same layout as above, but after the compressed data is another header and more compressed data.

So as you can see, I've done my homework because I figured it wouldn't be fair for me to just come here and ask for someone else to do all the work as I have seen others do. So what I would like a bit of help with is identifying that the compression used is in fact LZO and maybe tell me what tool you decompressed with or what library if you created your own application. And if its not LZO maybe help me figure out what it truly is.

I have attached 3 files that you can work with. I would appreciate if you could post any thoughts or comments even if you are unsure how to actually decompress as this could help me in figuring it out.

Thank you,
-Anthony
[Gears of War 2.rar](https://xentaxbackup.github.io/file/1696_Gears of War 2.rar)
## Post #2
- Username: AnthonyFiveSixTwo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 24, 2008 11:52 am
- Post datetime: 2008-10-24T20:36:50+00:00
- Post Title: Gears of War 2 Compression

Alright good news! Well for me at least. 

I figured out the compression used for Gears of War 2, it is LZX. It is supplied as a library through the Xbox 360 XeXDK. I can't talk much about how to get it or how its used, but I can say that it is in fact LZX and I have gotten the files to decompress.

It seems that the Unreal Engine on the Xbox 360 uses LZX rather then LZO now. What tipped me off was that it was mentioned that Unreal Tournament 3 used LZX here [viewtopic.php?f=21&t=3078](http://forum.xentax.com/viewtopic.php?f=21&t=3078). So I did some reverse engineering by looking at the disassembled xex and I found the same error code that juskrey had mentioned.

I created a DLL out of the .lib and created a wrapper for that to use within C# which works great for decompressing the game files. If anyone has anymore questions feel free to ask.
## Post #3
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-10-25T14:18:18+00:00
- Post Title: Gears of War 2 Compression

Please see PM
## Post #4
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2008-11-08T16:18:06+00:00
- Post Title: Gears of War 2 Compression

See PM for me as well, thanks.
