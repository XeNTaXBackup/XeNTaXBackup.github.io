## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-16T00:58:39+00:00
- Post Title: Beasts and Bumpkins MFB files (unknown RLE compression)

Need some help with these graphic files from an older 2D-game Beasts and Bumpkins.
It uses DirectDraw (if this helps somehow).
The files seem to contain static graphics as well as animations. Mix.dat and reflect.dat might be some sort of palette, but I'm not sure.
[mfbs.rar](https://xentaxbackup.github.io/file/1472_mfbs.rar)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-23T22:42:24+00:00
- Post Title: Beasts and Bumpkins MFB files (unknown RLE compression)

Current status:

```
char version[3]; // should be 101d (= 65h)
ushort width; // is the width of a single image
ushort height; // is the height of a single image
ushort uk3; // not used?
ushort uk4; // not used?
ushort flags; // bit 2 means compressed, 1 and 4 are unknown
ushort numImages; // number of images

if((flags & 2) == 0) // uncompressed data
{
	struct {
		struct {
			byte data[width];
		} lines[height] <optimize=false>;
	} images[numImages] <optimize=false>;
}
else // compressed data
{
	struct {
		uint size;
		byte data[size];
	} images[numImages]<optimize=false>;
}
```
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-04-01T19:46:59+00:00
- Post Title: Beasts and Bumpkins MFB files (unknown RLE compression)

The compression used is something along the lines of RLE. One color in the palette will be the transparency, which will occur a lot.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-11-10T18:05:06+00:00
- Post Title: Beasts and Bumpkins MFB files (unknown RLE compression)

Mix.dat and reflect.dat are lookup tables for reflection etc.
The images use palettes stored in the main game executable.
Unfortunately I still don't know the RLE algorithm 
[exe.rar](https://xentaxbackup.github.io/file/2520_exe.rar)
## Post #5
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-14T14:44:52+00:00
- Post Title: Beasts and Bumpkins MFB files (unknown RLE compression)

```
 * Uncompress a Beast and Bumpkins RLE-encoded data block.
 *
 * [in] in: The input (compressed) data.
 * [in] inSize: The size of the input data.
 * [out] out: The output (uncompressed) data.
 * [out] outSize: The size of the output data.
 *
 * (For images, outSize = width * height).
 *
 * TODO: Add bounds checking.
 */
bool unRLE(const uint8_t *in, size_t inSize, uint8_t *out, size_t outSize)
{
    size_t inPos = 0, outPos = 0;
    uint8_t copyByte = in[0];

    while (outPos < outSize)
    {
        if (in[inPos] == copyByte)
        {
            uint8_t count = in[inPos + 1];
            inPos += 2;

            while (count--)
                out[outPos++] = copyByte;
        }
        else
        {
            out[outPos++] = in[inPos++];
        }
    }

    return true;
}

```


The palettes are in the resources section of the EXE.
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-11-15T14:28:57+00:00
- Post Title: Beasts and Bumpkins MFB files (unknown RLE compression)

Woohoo thanks a lot!
Did you find it out by disassembling or just with the file?
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-12-29T15:14:42+00:00
- Post Title: Beasts and Bumpkins MFB files (unknown RLE compression)

Works like a charm
