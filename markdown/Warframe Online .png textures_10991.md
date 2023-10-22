## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-11-25T14:41:20+00:00
- Post Title: Warframe Online .png textures

Hi everyone, I'm trying to open/convert textures from game Warframe [https://warframe.com](https://warframe.com)
Textures have .png extention, but of course they aren't .png files. I want to write a model-import script, but if there's no option to get textures it's pointless. If anyone could help it will be awesome, any help or advice will be highly appreciated.
Some samples attached
[General_Textures.7z](https://xentaxbackup.github.io/file/6799_General_Textures.7z)
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-03T18:56:21+00:00
- Post Title: Warframe Online .png textures

I want to bump this thread, because my first sample textures were bad. Sorry about that, dont know why they were extracted like that. Here's good sample textures [https://www.mediafire.com/?m6bu7doz5gho3mh](https://www.mediafire.com/?m6bu7doz5gho3mh)
## Post #3
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-01-20T16:47:09+00:00
- Post Title: Warframe Online .png textures

> Reply from zaramot
>
> I want to bump this thread, because my first sample textures were bad. Sorry about that, dont know why they were extracted like that. Here's good sample textures https://www.mediafire.com/?m6bu7doz5gho3mhThe problem has been a long time, how to explain this textures？
## Post #4
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2015-02-01T14:38:42+00:00
- Post Title: Warframe Online .png textures

> Reply from chrrox
>
> I have looked at some of the textures it looks like the textures are only getting half extracted.
If you add a normal DDS header on the images you will see the image go in and out like only half is there. Maybe there is some more compression on the textures. But I am also not the best on image formats so I am not sure.

I'm looking at a texture about which the H-cache PNG file says max. res. = 2048 pixels.
Assuming this indicates a square size this would result in a DXT1 file of 2,796,344 bytes (with full MipMaps).
A DDS header size is 128 bytes, and adding the size of the B-cache PNG file, plus the size of the F-cache PNG file, results in the same number. Still the image is mixed up: it's kind of 'interlaced', structures can be recognized but are repeated twice horizontally.

Looking at the model's UVs, it looks like indeed the image should be repeated twice (for left and right), only the image rows should be reordered. Such reordering strongly suggest a non-DXT1 encoding per MipMap, although it seems similar.
The file size of the F-cache PNG file strongly suggests 4bpp, which only leaves the options of (1) DXT1 or (2) RGB with a 16-color palette. Another option (3) might be 2048x1024 (non-square) 8bpp with full MipMaps.

Taking the last 2,097,152 bytes from an F-cache PNG file, and adding a BMP header with a 4bpp 256-color palette, results in a mixed up image: it's kind of 'interlaced', structures can be recognized, and there is no repetition.

Another example is an F-cache PNG file of 1,376,256 bytes, about which the H-cache PNG file says: "Compression=COLOR_SMOOTH_ALPHA". So I'm guessing this must be a square 1024 pixel DXT5 image, and again the file size fits the bill: 128 + 21872 + 1376256 = size of DXT5 1024 pixels square with full MipMaps. Again the image is mixed up: structures can be recognized but are repeated horizontally.

The size of B-cache PNG files suggests that they actually hold some of the smaller MipMaps.
In case of the above supposed DXT5 file, the size of the B-cache PNG file corresponds to a DXT5 image of 128 pixels square with full MipMaps. Putting a header on it produces a garbled image.

In the contents of H-cache PNG files there are indications about max. res., compression and color space.
At the end of such a file I'm typically seeing ~22 floats, quite often equal to 1 or ~0.5. Maybe these numbers indicate gamma correction / color correction per MipMap. This all suggest that the textures have been saved with a tool that offers much more control over the pixel format. Looking at a tool like PVRTexTool you can see that there are much more options for creating a MipMapped texture than the relatively simple (!) NVidia plugin for Photoshop.

Warframe uses a DLL called 'libEGL.dll', which provides support for OpenGL ES 2.0.
With PVRTexTool it's possible to encode for this pixel format.
Encoding and MipMapping with 'OpenGL ES 2.0 ETC1' results in a file size that corresponds to a Warframe texture size, only now there is an 148 bytes header.
I can add such a header to Warframe files, but now I have no program to view the result..

Anyway, maybe "Game Format Scanner" can solve this  ( [viewtopic.php?f=18&t=12224](http://forum.xentax.com/viewtopic.php?f=18&t=12224) ).
## Post #5
- Username: enpinion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 24, 2012 4:11 am
- Post datetime: 2015-04-05T07:15:39+00:00
- Post Title: Warframe Online .png textures

Hello guys.

I'm currently working on the texture converter.
Actually EE's png is block based DDS with reversed stream.

My converter is almost done but still not perfect.

anyway, every non-ASCII files used by EE are headerless. (e.g. wav files are headerless xwm)
If anyone knows get proper header info like image width/height, let me know.

check the attached image for proof the converter.

APPENDIX -- my progress on the header file 

1C 14 22 8B A4 D7 E9 82 BC 8B 4B C4 9D 1C 00 4B 01 00 00 00 3A 00 00 00 2F 4C 6F 74 75 73 2F 43 68 61 72 61 63 74 65 72 73 2F 47 72 69 6E 65 65 72 2F 47 65 6E 65 72 61 6C 2F 47 72 69 6E 65 65 72 47 65 6E 65 72 61 6C 42 6F 64 79 5F 64 2E 70 6E 67 16 00 00 00 4D 61 78 52 65 73 6F 6C 75 74 69 6F 6E 3D 4D 52 5F 32 30 34 38 0A 00 A3 00 00 00 09 03 01 00 02 00 00 00 A3 95 01 00 97 7D 07 00 00 00 00 11 00 00 00 11 00 00 08 00 08 00 01 00 01 01 00 00 00 01 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 3F 00 00 80 3F 00 00 80 3F 00 00 80 3F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 3F 00 00 80 3F 00 00 80 3F 00 00 80 3F 00 00 80 3F 4B D5 4F 3D 65 16 22 3D FA 43 01 3D 00 00 80 3F 65 F6 5E 3D F9 AF 46 3D 97 3B 12 3D 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 3F 05 CC 70 3F E8 FC 5D 3F C1 C2 28 3F 00 00 80 3F 00 00 00 00


----
1C 14 22 8B A4 D7 E9 82 BC 8B 4B C4 9D 1C 00 4B
16 bytes: Hash(?) - Not Sure.

01 00 00 00
4 bytes: headerType - File format version

3A 00 00 00
4 bytes: pathFieldByte - Signed integer

2F 4C 6F 74 75 73 2F 43 68 61 72 61 63 74 65 72 73 2F 47 72 69 6E 65 65 72 2F 47 65 6E 65 72 61 6C 2F 47 72 69 6E 65 65 72 47 65 6E 65 72 61 6C 42 6F 64 79 5F 64 2E 70 6E 67
58 bytes: filePath - CHAR

16 00 00 00
4 bytes: fileParameterByte - Signed integer

4D 61 78 52 65 73 6F 6C 75 74 69 6F 6E 3D 4D 52 5F 32 30 34 38 0A
16 bytes: fileParameter - CHAR

00
1 byte: fileParamterEOL - If fileParamter Prsents, 0x00 must be there.

A3 00 00 00
4 bytes: fileType - DWORD
known file types:
163 = png | AT_TEXTURE_RESOURCE
135 = wav | Sound
477 = fbx | AT_MESH_RESOURCE
237 = fbx | AT_EULER
126 = fbx | AT_ANIMATION_RESOURCE
311 = fbx | unknown
4 = swf | AT_FLASH_RESOURCE (scaleform)
314 = fbx | map
184 = png | AT_TEXTURE_RESOURCE

09 03 01 00 
4bytes: unknown

02 00 00 00
4byes: Additional DWORD - signed integer


least 160 bytes is unknown.

If anyone have an idea, please let me know.
[GrineerGeneralBody_d.jpg](https://xentaxbackup.github.io/file/8948_GrineerGeneralBody_d.jpg)
## Post #6
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2015-04-07T09:04:51+00:00
- Post Title: Warframe Online .png textures

> .. block based DDS with reversed stream..
Could you post your code for reversing the these png's?
## Post #7
- Username: enpinion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 24, 2012 4:11 am
- Post datetime: 2015-04-08T15:00:48+00:00
- Post Title: Warframe Online .png textures

> Reply from Pesmontis
>
> Could you post your code for reversing the these png's?

My experimental converter is quite primitive and it's really complicated to use.
So here is the actual algorithm in psuedo-code.

```
  fileDestination = blah.dds.raw
  bufBlockBuffer_0 []
  bufBlockBuffer_1 []
  sizeBlock = 0x2000
  posBlock []

func init(){
  posBlock[0] = 0
  posBlock[1] = 1
  convertThread()
}

func convertThread(){
  bufBlockBuffer_0 = read(fileSource, posBlock[0], sizeBlock) ;read (char filename, int seek location, int bytes to read)
  bufBlockBuffer_1 = read(fileSource, posBlock[1]*sizeBlock, sizeBlock)
  while (bufBlockBuffer_0 == 0; bufBlockBuffer_1 == 0):
    write DWORD from bufBlockBuffer_0 to fileDestination
    write DWORD from bufBlockBuffer_1 to fileDestination
  posBlock[0] += 2
  posBlock[1] += 2
}

init()
while (until bufBlockBuffer reached to the end of file)
{
  convertThread()
}

```


Currently I'm working on a explorer for extract, convert resources. By that, I don't want to rewrite this for standalone application.

If you have any question related with this, please let me know.
## Post #8
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2015-04-08T19:58:00+00:00
- Post Title: Warframe Online .png textures

That seems to work just fine (for an assumed DXT1 DDS file).
How did you find that sizeBlock = 0x2000 ?
## Post #9
- Username: enpinion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 24, 2012 4:11 am
- Post datetime: 2015-04-09T05:29:16+00:00
- Post Title: Warframe Online .png textures

> Reply from Pesmontis
>
> That seems to work just fine (for an assumed DXT1 DDS file).
How did you find that sizeBlock = 0x2000 ?

As you know DDS format have simple format and when I just put standard DXT1 header on the file (png thing), I can recognize rough view of the image.
and I found some binary density pattern and it wasn't hard at all.
[123.png](https://xentaxbackup.github.io/file/8993_123.png)
## Post #10
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2015-04-15T07:17:17+00:00
- Post Title: Warframe Online .png textures

That's a nice program for detecting patterns, what is it?

> ".. get proper header info like image width/height.."
I guess there's only one way of doing this: preparing your own table of <file size>, <width>, <height>, <DDS type>, <# MIPmaps>.
So far I've only split off the largest MIPmap off of some png's (at the end of an F-cache png file). Then I ran through your reversal method,
and then I put a DXT1 header on top of it (no MIPmaps):
- 2,752,512 bytes = DXT1 2048x2048, full MIPmaps;
-   655,360 bytes = DXT1 1024x1024, full MIPmaps;
-   131,072 bytes = DXT1 512x512, only one MIPmap.

Here's a bit of eye-candy for the result:



Ember Prime as Highelve in Sacred 2 Ember Prime 43.jpg (72.47 KiB) Viewed 695 times
## Post #11
- Username: enpinion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 24, 2012 4:11 am
- Post datetime: 2015-04-20T11:13:52+00:00
- Post Title: Warframe Online .png textures

> Reply from Pesmontis
>
> That's a nice program for detecting patterns, what is it?

It's called "Binglide" ([https://github.com/wapiflapi/binglide](https://github.com/wapiflapi/binglide)).

quite useful when I unpack some executable too.
## Post #12
- Username: Basurci
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 24, 2014 6:26 am
- Post datetime: 2015-06-08T03:27:49+00:00
- Post Title: Warframe Online .png textures

Any updates on this thread? xd
## Post #13
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2015-10-05T01:09:04+00:00
- Post Title: Warframe Online .png textures

Ah, great stuff here. So far I've had some success with extracting model data, however I ended up using NinjaRipper to extract the textures from memory. i know it's not the most intuitive way to do it. But it is one way.

That was, perhaps, almost a year ago. I think it's time I'd upgraded my level of interpretation.
## Post #14
- Username: tnt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 03, 2017 6:02 am
- Post datetime: 2017-02-24T15:38:44+00:00
- Post Title: Warframe Online .png textures

Here is my attempt at re-creating the psuedocode you provided for converting the F.cache files into DDS textures. Seems like my output is lacking color and different from the desired output that I'm hoping for.

wfpngc.c (compiled with gcc on a linux O.S.)

```
#include <string.h>
#include <assert.h>

#if defined(MSDOS) || defined(OS2) || defined(WIN32) || defined(__CYGWIN__)
#  include <fcntl.h>
#  include <io.h>
#  define SET_BINARY_MODE(file) setmode(fileno(file), O_BINARY)
#else
#  define SET_BINARY_MODE(file)
#endif

typedef int DWORD;

#define		DDSD_CAPS					0x1
#define		DDSD_HEIGHT				0x2
#define		DDSD_WIDTH				0x4
#define		DDSD_PITCH				0x8
#define		DDSD_PIXELFORMAT			0x1000
#define		DDSD_MIPMAPCOUNT			0x20000
#define		DDSD_LINEARSIZE			0x80000
#define		DDSD_DEPTH				0x800000

#define		DDPF_ALPHAPIXELS			0x1
#define		DDPF_ALPHA				0x2
#define		DDPF_FOURCC				0x4
#define		DDPF_RGB					0x40
#define		DDPF_YUV					0x200
#define		DDPF_LUMINANCE				0x20000

#define		DDSCAPS_COMPLEX			0x8
#define		DDSCAPS_MIPMAP				0x400000
#define		DDSCAPS_TEXTURE			0x1000

#define		DDSCAPS2_CUBEMAP			0x200
#define		DDSCAPS2_CUBEMAP_POSITIVEX	0x400
#define		DDSCAPS2_CUBEMAP_NEGATIVEX	0x800
#define		DDSCAPS2_CUBEMAP_POSITIVEY	0x1000
#define		DDSCAPS2_CUBEMAP_NEGATIVEY	0x2000
#define		DDSCAPS2_CUBEMAP_POSITIVEZ	0x4000
#define		DDSCAPS2_CUBEMAP_NEGATIVEZ	0x8000
#define		DDSCAPS2_VOLUME			0x200000


typedef struct {
  DWORD dwSize;
  DWORD dwFlags;
  DWORD dwFourCC;
  DWORD dwRGBBitCount;
  DWORD dwRBitMask;
  DWORD dwGBitMask;
  DWORD dwBBitMask;
  DWORD dwABitMask;
} DDS_PIXELFORMAT;

typedef struct {
  DWORD           dwSize;
  DWORD           dwFlags;
  DWORD           dwHeight;
  DWORD           dwWidth;
  DWORD           dwPitchOrLinearSize;
  DWORD           dwDepth;
  DWORD           dwMipMapCount;
  DWORD           dwReserved1[11];
  DDS_PIXELFORMAT ddspf;
  DWORD           dwCaps;
  DWORD           dwCaps2;
  DWORD           dwCaps3;
  DWORD           dwCaps4;
  DWORD           dwReserved2;
} DDS_HEADER;

#define blockSize 0x2000
#define cpySize 0x0004 //0x0020
#define blankSize 0x0

long posBlock[2];
long totalBlocks;

int convertOneBlock(FILE* src, FILE* dst)
{
	unsigned char block1_in[blockSize];
	unsigned char block1_out[blockSize];
	unsigned char block2_in[blockSize];
	unsigned char block2_out[blockSize];
	unsigned char block_out[cpySize];
	int read1_ret, read2_ret;
	fseek(src, (posBlock[0]*blockSize), SEEK_SET);
	read1_ret = fread(block1_in, 1, blockSize, src);
	fseek(src, (posBlock[1]*blockSize), SEEK_SET);
	read2_ret = fread(block2_in, 1, blockSize, src);

	if ( !(read1_ret == 0 || read2_ret == 0) )
	{
		if (cpySize < blockSize)
		{
			size_t remainingSize = blockSize;
			unsigned char* block1_ptr = (unsigned char *) &block1_in;
			unsigned char* block2_ptr = (unsigned char *) &block2_in;
			while (remainingSize > 0)
			{
				memcpy(&block_out, block1_ptr, cpySize);
				fwrite(block_out, 1, cpySize, dst);
				memcpy(&block_out, block2_ptr, cpySize);
				fwrite(block_out, 1, cpySize, dst);
				
				block1_ptr += cpySize;
				block2_ptr += cpySize;
				remainingSize -= cpySize;
			}
			
			posBlock[0] += 2;
			posBlock[1] += 2;
			
			totalBlocks += 2;
		}
		else
		{
			memcpy(&block_out, &block1_in, cpySize);
			fwrite(block_out, 1, cpySize, dst);
			memcpy(&block_out, &block2_in, cpySize);
			fwrite(block_out, 1, cpySize, dst);
	
			posBlock[0] += 2;
			posBlock[1] += 2;
	
			totalBlocks += 2;
		}

		return 0;
	}
	else
	{
		posBlock[0] += 2;
		posBlock[1] += 2;

		return 1;
	}
}

int init(FILE* src, FILE* dst)
{
	if (src == NULL || dst == NULL)
	{
		return -1;
	}
	
	fseek(src, 0L, SEEK_END);
	long srcFileSize = ftell(src);
	fseek(src, 0L, SEEK_SET);
	
	DDS_HEADER fileOutHeader;
	memset(&fileOutHeader, 0, sizeof(DDS_HEADER));
	fileOutHeader.dwSize = 124;

	fileOutHeader.dwFlags = DDSD_CAPS | DDSD_HEIGHT | DDSD_WIDTH | DDSD_PIXELFORMAT | DDSD_MIPMAPCOUNT;
	fileOutHeader.ddspf.dwSize = 32;
	fileOutHeader.ddspf.dwFlags = DDPF_RGB | DDPF_ALPHAPIXELS | DDPF_FOURCC | DDPF_ALPHA;
	fileOutHeader.ddspf.dwFourCC = 0x31545844; // "DXT1"
	fileOutHeader.ddspf.dwRGBBitCount = 32;
	fileOutHeader.ddspf.dwRBitMask = 0xff000000;
	fileOutHeader.ddspf.dwGBitMask = 0x00ff0000;
	fileOutHeader.ddspf.dwBBitMask = 0x0000ff00;
	fileOutHeader.ddspf.dwABitMask = 0x000000ff;
	fileOutHeader.dwCaps = DDSCAPS_TEXTURE | DDSCAPS_MIPMAP;
	
	printf("file size: %ld  ", srcFileSize);
	if (srcFileSize == 0)
	{
		return -2;
	}
	else if (srcFileSize < 131100)
	{
		fileOutHeader.dwWidth = 512;
		fileOutHeader.dwHeight = 512;
		fileOutHeader.dwPitchOrLinearSize = (( (512*32)+7 ) / 8);
		fileOutHeader.dwMipMapCount = 1;
		printf("writing 512x512 32-bit dds file\n");
	} else if (srcFileSize < 655400)
	{
		fileOutHeader.dwWidth = 1024;
		fileOutHeader.dwHeight = 1024;
		fileOutHeader.dwPitchOrLinearSize = (( (1024*32)+7 ) / 8);
		fileOutHeader.dwMipMapCount = 1;
		printf("writing 1024x1024 32-bit dds file\n");
	}
	else if (srcFileSize < 1376260)
	{
		fileOutHeader.dwWidth = 1024;
		fileOutHeader.dwHeight = 1024;
		fileOutHeader.dwPitchOrLinearSize = (( (512*32)+7 ) / 8);
		fileOutHeader.dwMipMapCount = 1;
		printf("writing ?x? 32-bit dds file\n");
	}
	else
	{
		fileOutHeader.dwWidth = 2048;
		fileOutHeader.dwHeight = 2048;
		fileOutHeader.dwPitchOrLinearSize = 0; //(( (2048*32)+7 ) / 8);
		fileOutHeader.dwMipMapCount = 0;
		fileOutHeader.ddspf.dwFlags = DDPF_FOURCC;
		fileOutHeader.dwFlags = DDSD_CAPS | DDSD_HEIGHT | DDSD_WIDTH | DDSD_PIXELFORMAT; /// | DDSD_MIPMAPCOUNT;
		fileOutHeader.ddspf.dwRGBBitCount = 0;
		fileOutHeader.ddspf.dwRBitMask = fileOutHeader.ddspf.dwGBitMask = fileOutHeader.ddspf.dwBBitMask = fileOutHeader.ddspf.dwABitMask = 0x00000000;
		fileOutHeader.dwCaps = DDSCAPS_TEXTURE;
		printf("writing 2048x2048 0-bit dds file\n");
	}
	
	// Write DDS prefix (0x44445320)
	totalBlocks = 0;
	fwrite("DDS ", 4, 1, dst);

	// Write DDS header
	fwrite(&fileOutHeader, 1, sizeof(DDS_HEADER), dst);

	posBlock[0] = 0;
	posBlock[1] = 1;
	convertOneBlock(src, dst);

	return 0;
}

int convertWFPNG(FILE* src, FILE* dst)
{
	init(src, dst);

	while (feof(src) == 0)
	{
		if (convertOneBlock(src, dst) == 1)
		{
			break;
		}
	}

	if (blankSize > 0)
	{
		unsigned char zeroSpace[blankSize];
		memset(&zeroSpace, 0, blankSize);
		int i = 0;
		for (i = 0; i < totalBlocks; i++)
		{
			fwrite(zeroSpace, 1, blankSize, dst);
		}
		printf("wrote some more zeros at file end\n");
	}

	return 0;
}

int main(int argc, char **argv)
{
	FILE* srcFile1 = NULL;
	FILE* dstFile1 = NULL;

	if (argc != 3)
	{
		fprintf(stderr, "Usage: wfpngc input-file.png output-file.dds\n");
		return 1;
	}

	srcFile1 = fopen(argv[1], "r");
	if (srcFile1 == NULL)
	{
		fprintf(stderr, "Error opening file for reading: %s\n", argv[1]);
		return 5;
	}

	dstFile1 = fopen(argv[2], "w");
	if (dstFile1 == NULL)
	{
		fclose(srcFile1);
		srcFile1 = NULL;
		fprintf(stderr, "Error opening file for writing: %s\n", argv[2]);
		return 5;
	}

	convertWFPNG(srcFile1, dstFile1);

	fclose(srcFile1);
	fclose(dstFile1);
}

```




Desired output (Mirage body skin) Desired output for Mirage body skin (shrunk).png (123.61 KiB) Viewed 427 times



Desired output for Mirage body skin (original):
[http://core.dbq.tnt.gs/i/HarlequinBody.tga](http://core.dbq.tnt.gs/i/HarlequinBody.tga)

Input provided to program:
[http://core.dbq.tnt.gs/i/HarlequinBody_d.png.F](http://core.dbq.tnt.gs/i/HarlequinBody_d.png.F)

Result of program:
[http://core.dbq.tnt.gs/i/HarlequinBody_d.png.F.dds](http://core.dbq.tnt.gs/i/HarlequinBody_d.png.F.dds)

Also, there has to be a better way of determining image width/height than just going off of file size alone.
## Post #15
- Username: tnt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 03, 2017 6:02 am
- Post datetime: 2017-02-24T15:43:26+00:00
- Post Title: Warframe Online .png textures

This is what the output looks like when you view it in Microsoft's DirectX texture tool. Other programs seem to throw an exception about the file format.



HarlequinScreenCap.jpg (219.83 KiB) Viewed 427 times



Again, grayscale. And there appears to be mipmaps in the top-half of the image.

edit: Sorry in advance for bumping a really old thread
## Post #16
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2017-02-28T13:34:51+00:00
- Post Title: Re: Warframe Online .png textures

This is what I use:

```
{	
	FILE* fIn = NULL;
	FILE* fOut = NULL;
	char* pixels0;
	char* pixels1;
	char* pixOut;

	fIn = fopen( pngFileWF, "rb" );

	strcat( pngFileWF, "_reversed.png" );
	fOut = fopen( pngFileWF, "wb+" );

	fseek( fIn, 0, SEEK_END );
	int fSz = ftell( fIn );
	fseek( fIn, 0, SEEK_SET );

	pixels0 = (char*)malloc( WFBLOCKSZ );
	pixels1 = (char*)malloc( WFBLOCKSZ );
	pixOut = (char*)malloc( fSz );

	for( int i = 0; i < fSz / (2 * WFBLOCKSZ); i++ )
	{
		fread( pixels0, WFBLOCKSZ, 1, fIn );
		fread( pixels1, WFBLOCKSZ, 1, fIn );

		for( int j = 0; j < WFBLOCKSZ / WriteBlockSz; j++ )
		{
			memcpy( pixOut + 2 * i * WFBLOCKSZ + ( 2 * j + 0) * WriteBlockSz, &pixels0[ j * WriteBlockSz ], WriteBlockSz );
			memcpy( pixOut + 2 * i * WFBLOCKSZ + ( 2 * j + 1) * WriteBlockSz, &pixels1[ j * WriteBlockSz ], WriteBlockSz );
		}
	}

	fwrite( pixOut, fSz, 1, fOut );

	fclose( fIn );
	fclose( fOut );

	free(pixels0);
	free(pixels1);
	free(pixOut);

	return 0;
}
```


It's quite some time ago that I've used this, but I think this is only for the body of the DDS file.
Depending on the size of the output I think I manually added an appropriate DDS header.
## Post #17
- Username: dedok179
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 20, 2016 1:41 pm
- Post datetime: 2018-01-05T06:34:58+00:00
- Post Title: Re: Warframe Online .png textures

> Reply from Pesmontis
>
> This is what I use:
Code: Select allint convertWarframe(char* pngFileWF)
{	
	FILE* fIn = NULL;
	FILE* fOut = NULL;
	char* pixels0;
	char* pixels1;
	char* pixOut;

	fIn = fopen( pngFileWF, "rb" );

	strcat( pngFileWF, "_reversed.png" );
	fOut = fopen( pngFileWF, "wb+" );

	fseek( fIn, 0, SEEK_END );
	int fSz = ftell( fIn );
	fseek( fIn, 0, SEEK_SET );

	pixels0 = (char*)malloc( WFBLOCKSZ );
	pixels1 = (char*)malloc( WFBLOCKSZ );
	pixOut = (char*)malloc( fSz );

	for( int i = 0; i < fSz / (2 * WFBLOCKSZ); i++ )
	{
		fread( pixels0, WFBLOCKSZ, 1, fIn );
		fread( pixels1, WFBLOCKSZ, 1, fIn );

		for( int j = 0; j < WFBLOCKSZ / WriteBlockSz; j++ )
		{
			memcpy( pixOut + 2 * i * WFBLOCKSZ + ( 2 * j + 0) * WriteBlockSz, &pixels0[ j * WriteBlockSz ], WriteBlockSz );
			memcpy( pixOut + 2 * i * WFBLOCKSZ + ( 2 * j + 1) * WriteBlockSz, &pixels1[ j * WriteBlockSz ], WriteBlockSz );
		}
	}

	fwrite( pixOut, fSz, 1, fOut );

	fclose( fIn );
	fclose( fOut );

	free(pixels0);
	free(pixels1);
	free(pixOut);

	return 0;
}

It's quite some time ago that I've used this, but I think this is only for the body of the DDS file.
Depending on the size of the output I think I manually added an appropriate DDS header.
Is there no progress on?
## Post #18
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-22T17:22:44+00:00
- Post Title: Re: Warframe Online .png textures

Who can provide a correct conversion tool for PNG and FBX?
## Post #19
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-24T14:54:48+00:00
- Post Title: Re: Warframe Online .png textures

Can you provide a tool?
## Post #20
- Username: Hidaomari
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 21, 2015 4:47 am
- Post datetime: 2019-06-07T21:44:45+00:00
- Post Title: Re: Warframe Online .png textures

Can we up this theme again?
I saw tons of posts and informations and at laest now I understand why PNG don't want to open.
But still, what I must do to make it work?

I beg you for help!
## Post #21
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2019-06-30T11:51:41+00:00
- Post Title: Re: Warframe Online .png textures

Well that sucks. Coming in here only to find theres no tools that have actually been released.
Welp.
## Post #22
- Username: Puxtril
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 24, 2018 5:13 am
- Post datetime: 2021-03-23T02:13:08+00:00
- Post Title: Re: Warframe Online .png textures

Resurrecting a dead thread, but just wanted to add more info since this seems to be the only place talking about extracting textures.

I wanted to extract the PS4/Xbox/Switch exclusive skins from the archive (Warframe devs are lazy and leave those in the PC version) so I took a close look at the .png formats. I used Pesmontis's code as a base and went from there. His code allows you to extract BC1 compressed textures, but each BC has a different swizzle (not sure if swizzle is the right term). It's not obvious which texture is which BC, I take a best-guess from the metadata.

I'll look into dumping all textures from the game, but right now I'm working on extracting models from an older version of WF. A recent update dubbed "The Great Ensmallening" changed their archive format. GMman's cache extractor doesn't work anymore, and Ninjaripper yields squished models.

But anyway, Excalibur's BC5-compressed PS4 Emission map:
