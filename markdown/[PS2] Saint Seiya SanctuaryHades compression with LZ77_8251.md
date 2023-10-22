## Post #1
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-02-10T16:54:11+00:00
- Post Title: [PS2] Saint Seiya Sanctuary/Hades compression with LZ77

In both games there are lots of images and textures compressed using some variation of LZ77 algorithm. There is a plugin that comes with Noesis that can decompress some of those files. But it can open only the first image when the file has multiple images, and can't open some files which have a different structure than expected.

My goal is to develop a [Java] tool to decompress the files Noesis can't. I would appreciate if someone could explain me in more detail the code below, that was extracted from Noesis plugin and seem to be a good starting point for me.

```
{
	BYTE			id[4]; //"CMPS"
	int				cmpType;
	int				decompSize;
	int				resv;
} gmiCmpHdr_t;

//decompress data
static BYTE *Model_GMI_Decompress(BYTE *src, int &len, noeRAPI_t *rapi)
{
	gmiCmpHdr_t *cmpHdr = (gmiCmpHdr_t *)src;
	int srcLen = len;
	int dstLen = cmpHdr->decompSize;
	BYTE *dst = (BYTE *)rapi->Noesis_PooledAlloc(dstLen);
	int srcPtr = sizeof(gmiCmpHdr_t);
	int dstPtr = 0;

	while (srcPtr < srcLen && dstPtr < dstLen)
	{
		BYTE ctrl = src[srcPtr++];
		for (int i = 0; i < 8 && srcPtr < srcLen && dstPtr < dstLen; i++)
		{
			if (ctrl & (1<<i))
			{ //literal
				dst[dstPtr++] = src[srcPtr++];
			}
			else
			{ //ofs+len
				WORD ol = *(WORD *)(src+srcPtr);
				srcPtr += sizeof(WORD);
				int len = 3 + ((ol>>8) & 15);
				int relOfs = (ol & 255) | ((ol>>12) << 8);
				int ofs = dstPtr - ((dstPtr-18-relOfs) & 4095);
				for (int j = 0; j < len && dstPtr < dstLen; j++)
				{
					if (ofs+j < 0 || ofs+j >= dstPtr)
					{
						dst[dstPtr++] = 0;
					}
					else
					{
						dst[dstPtr++] = dst[ofs+j];
					}
				}
			}
		}
	}
	assert(srcPtr <= srcLen);
	assert(dstPtr <= dstLen);

	len = dstLen;
	return dst;
}

```
## Post #2
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2012-02-10T18:36:28+00:00
- Post Title: [PS2] Saint Seiya Sanctuary/Hades compression with LZ77

You need to understand how structs work for this to make any sense.
First, look in the code for gmiCmpHdr_t and noeRAPI_t.  They're like classes, except they usually only define variables.  A struct is like a window, which is placed over a part of memory and tells you what kinds of data are there.  In java you would have to read the data a few bytes at a time and interpret it manually, then use getters and setters to build your object.  Using a struct, you direct it at a part of memory and all of the variables will be defined with whatever data is there.

Secondly, -> is used to access a class member.  It's the same as using  .  in java.

Lastly, the code uses pointer math to scan through all the data.  In java you would have to use a stream to read in bytes one by one, or at least use a ByteBuffer.  I would definitely recommend studying how pointers work in C in order for all of this code to make sense.
## Post #3
- Username: gustavofarias
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-11T01:10:20+00:00
- Post Title: [PS2] Saint Seiya Sanctuary/Hades compression with LZ77

You're mistaken about Noesis not handling the files with multiple images. It loads them all. You just have to select textures in the data viewer to see them.

Beyond that... I think the bitwise operations (which is where most of the complexity is) should translate right over to Java.
## Post #4
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-02-15T01:55:38+00:00
- Post Title: [PS2] Saint Seiya Sanctuary/Hades compression with LZ77

> It's extremely simple, about as standard-fare as you can get with LZ77-based algorithms (8-bit flag with 16-bit offset+length pairs for non-literals)
What is the "flag" in LZ77? How long is a literal and the Window? How a NULL offset+length is represented? How do I identify if the next byte is an offset+length pair or a literal?

Could you use the attachment below to show me an example of the flag, offset+length pair and literal?
[CMPS binary file.PNG](https://xentaxbackup.github.io/file/5066_CMPS binary file.PNG)
## Post #5
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-02-25T23:20:59+00:00
- Post Title: [PS2] Saint Seiya Sanctuary/Hades compression with LZ77

I did my homework and studied the algorithm. Please correct me if I'm wrong. The 8 bit flag tells which of the next 8 bytes/words are literals and which are off+length pairs.

I still have some very low level questions:

```
int len = 3 + ((ol>>8) & 15);
```

Why do you add 3 to the 4-bit length?

```
int relOfs = (ol & 255) | ((ol>>12) << 8);
```

How did you figure that you should take the first 4 bits and the last 8 bits?

```
int ofs = dstPtr - ((dstPtr-18-relOfs) & 4095);
```

Why all this calculation to get the offset? Where does this 18 come from?

Thanks for all the help to date.
## Post #6
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-02-27T14:40:30+00:00
- Post Title: [PS2] Saint Seiya Sanctuary/Hades compression with LZ77

A question about endianess:

```
{
  if (ctrl & (1<<i))
```

In this code the bits of ctrl are processed from right to left.

```
WORD ol = *(WORD *)(src+srcPtr);
```

In the above code, how are the two bytes of the WORD organized? Big or Little Endian? And the bits in each byte?

Random question:

```
srcPtr += sizeof(WORD);
```

Is this the same as srcPtr += 2;?
## Post #7
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-02-28T12:00:15+00:00
- Post Title: [PS2] Saint Seiya Sanctuary/Hades compression with LZ77

Here is the first version of the translation of the Noesis decompression code to a Java code. It doesn't work yet. Maybe you can help me find the bugs. 

```
	// create a stream to read the input
	DataInputStream is = new DataInputStream(new FileInputStream(compressedFile));
	// skip the first 8 bytes
	is.skipBytes(8); // C M P S 01 00 00 00
	// read the next int which is the decompressed size
	int dstLen = Integer.reverseBytes(is.readInt()); // The 4 bytes are read in the reverse order
	// skip 4 more bytes
	is.skipBytes(4); // 00 00 00 00

	// for the sake of simplicity reads the entire file to a byte array, ignoring the first 16 bytes that have already been read.
	int srcLen = (int)compressedFile.length() - 16;
	System.out.println("Source length: " + srcLen);
	byte[] src = new byte[srcLen];
	is.read(src);
	// creates a byte array to store the decompressed bytes
	byte[] dst = new byte[dstLen];
	System.out.println("output length: " + dstLen);

	int srcPtr = 0; // by skipping 16 bytes I can start from 0
	int dstPtr = 0;

	while (srcPtr < srcLen && dstPtr < dstLen) {
		byte ctrl = src[srcPtr++];

		for (int i = 0; i < 8 && srcPtr < srcLen && dstPtr < dstLen; i++) {
			if ( (ctrl & (1 << i)) != 0 ) {
				dst[dstPtr++] = src[srcPtr++];
			}
			else {
				// The line below is different from the original. I'm just reading two bytes from te input
				short ol = (short)(src[srcPtr] << 8 | src[srcPtr + 1]); // should I reverse the byte order?
				// I've read 2 bytes, so I mode the pointer 2 bytes ahead
				srcPtr += 2;
				int len = 3 + ((ol >> 8) & 15); // why +3?
				int relOfs = (ol & 255) | ((ol >> 12) << 8);
				int ofs = dstPtr - ((dstPtr - 18 - relOfs) & 4095); // can't get this 18 and the rest
				for (int j = 0; j < len && dstPtr < dstLen; j++) {
					if (ofs + j < 0 || ofs + j >= dstPtr) {
						dst[dstPtr++] = 0;
					}
					else {
						dst[dstPtr++] = dst[ofs + j];
					}
				}
			}
		}
	}
	// check consistency
	if (srcPtr > srcLen || dstPtr > dstLen) {
		throw new Exception("Out of bounds.");
	}
	// write the decompressed bytes to a file
	OutputStream os = new FileOutputStream( new File(compressedFile.getParent(), compressedFile.getName() + "_DECMPS") );
	os.write( dst );
	os.flush();
}

```

[LZS_SaintSeiya.rar](https://xentaxbackup.github.io/file/5113_LZS_SaintSeiya.rar)
