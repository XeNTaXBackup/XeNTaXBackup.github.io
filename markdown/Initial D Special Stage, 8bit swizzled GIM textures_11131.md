## Post #1
- Username: root670
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 18, 2010 6:11 am
- Post datetime: 2014-01-13T02:04:01+00:00
- Post Title: Initial D Special Stage, 8bit swizzled GIM textures

I'm trying to write a tool to convert textures from Initial D Special Stage to PNG. I've figure out how to extract the raw texture files off the disc (AFS->PAC->GIM), but after unswizzling the textures, they aren't coming out right. There are tools to export GIM files, but this game seems to use a nonstandard header that throws off the extractors. Here's my findings for the GIM textures' header:

0x30	Width (2 bytes)
0x32	Height (2 bytes)
0x3c	Data Offset (4 bytes)
0x4c	Pallet Offset (4 bytes)

Data is 8BPP, pallet is stored as RGBA. Alpha value is usually 128.

If I use "Console Texture Explorer" the textures are viewable, but that tool doesn't like width/height values that aren't powers of 2. My tool produces lots of noise not present in the original image... have I swizzled the texture properly?

from Console Texture Explorer (width should be 448, had to use 256):

from my tool:

Original GIM file: [http://rghost.net/51608656](http://rghost.net/51608656)


Here's the source for my broken tool. png.h is located here: [http://nothings.org/stb/stb_image_write.h](http://nothings.org/stb/stb_image_write.h). It's a little messy   , I apologize

```

#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <assert.h>
#include <string.h>
#include "png.h"

// Based on https://github.com/neko68k/rtftool/blob/master/RTFTool/rtfview/p6t_v2.cpp
// which looks like a port from puyotools.
void deswizzle(uint8_t *inpixels, uint8_t *outpixels, size_t width, size_t height)
{
	int i = 0;

    for (int y = 0; y < height; y++)
    {
        for (int x = 0; x < width; x++)
        {
            int block_location = (y & (~0xf)) * width + (x & (~0xf)) * 2;
            int swap_selector = (((y + 2) >> 2) & 0x1) * 4;
            int posY = (((y & (~3)) >> 1) + (y & 1)) & 0x7;
            int column_location = posY * width * 2 + ((x + swap_selector) & 0x7) * 4;

            int byte_num = ((y >> 1) & 1) + ((x >> 2) & 2);     // 0,1,2,3

            outpixels[(y * width) + x] = inpixels[block_location + column_location + byte_num];
        }
    }

}

int main(int argc, char* argv[])
{
	FILE* 			fGim = NULL;
	FILE*			fPng = NULL;
	unsigned char*	gimData;
	uint32_t*		pngData;
	uint32_t*		imageData;
	size_t 			gimLength;
	size_t 			pngLength;

	/* Parts of GIM header */
	uint16_t 	width;
	uint16_t 	height;
	uint8_t* 	dataPtr;
	uint32_t* 	cltPtr;

    printf("gim2png - Converts Initial D Special Stage GIM textures to PNG files.\n");
    assert(argc >= 3);
    fGim = fopen(argv[1], "rb");

    printf("Reading GIM to memory...\n");
    /* Read GIM into memory */
    fseek(fGim, 0, SEEK_END);
    gimLength = ftell(fGim);
    fseek(fGim, 0, SEEK_SET);
    gimData = malloc(gimLength);
    assert(gimData != NULL);
    fread(gimData, 1, gimLength, fGim);
    fclose(fGim);

    /* Read parts of the header for relevant values */
	width = 		*((uint16_t *)(gimData+0x30));
	height = 		*((uint16_t *)(gimData+0x32));
	dataPtr = 		gimData + *((uint32_t *)(gimData+0x3c));
	cltPtr = 		gimData + *((uint32_t *)(gimData+0x4c));
	printf("Data starts at 0x%x, CLT is at 0x%x\n", dataPtr, cltPtr);

	unsigned char *original = malloc(width*height);
	memcpy(original, dataPtr, width*height);
	
	printf("Un-Swizzling...\n");
	deswizzle(original, dataPtr, width, height);

	printf("Converting to RGBA...\n");
	/* Read the image as RGBA (4 bytes per pixel) */
	imageData = malloc(width * height * 4);
	for(int i = 0; i < (width*height); i++)
	{
		uint8_t pixel = *(dataPtr + i);
		imageData[i] = cltPtr[pixel] | (0xFF << 24);
	}

	printf("Saving PNG...\n");
	int ret = stbi_write_png(argv[2], width, height, 4, imageData, width*4);
	//int ret = stbi_write_tga(argv[2], width, height, 4, imageData);
	if(ret == 0)
	{
		printf("Error writing PNG...\n");
		return EXIT_FAILURE;
	}
	else
	{
		printf("Saved to %s.\n", argv[2]);
		return EXIT_SUCCESS;
	}

    return 0;
}

```


Any help is appreciated, thank you.
## Post #2
- Username: root670
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 18, 2010 6:11 am
- Post datetime: 2014-08-18T04:18:27+00:00
- Post Title: Initial D Special Stage, 8bit swizzled GIM textures

So I figured this out. The palette has to be filtered before it can be in a usable form, and I found a function in rainbow ([https://github.com/marco-calautti/Rainbow](https://github.com/marco-calautti/Rainbow)) that can do just that. The alpha channel also needs to be scaled from 0-128 to 0-256 which can be done using shift operations. Now the textures extract as they should and I've begun work on the game's other file formats. Here you can see the textures look the way they should after filtering the palette:



I put a post on my site about my findings so far if anyone is interested: [http://wescastro.com/2014/08/17/initial ... anslation/](http://wescastro.com/2014/08/17/initial-d-special-stage-translation/).
## Post #3
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-09-24T20:07:26+00:00
- Post Title: Initial D Special Stage, 8bit swizzled GIM textures

Wow, glad to see this game is getting some love (and that there is another JDM car fan on these boards    ). Tell me, have you ever heard of Tokyo Xtreme Racer Drift 2? It's a game similar to Initial D Street Stage that features both Akina, Myogi, Haruna (Akina) and many many more togue routes and with over 200 cars (I think) including special D1 Drift machines.

Perhaps if I uploaded some files, you'd be interested in taking alook? Only theoretically, don't feel forced but the game is like Special Stage, only with 10x more choice.
