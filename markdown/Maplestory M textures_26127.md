## Post #1
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2022-12-29T09:29:24+00:00
- Post Title: Maplestory M textures

Not sure how to fix these images (decrypted from assetbundles from kr maplestory M), if anyone can decompress this ><
purely a guess, from the image name containing crab and shader name crabby this (just might) be related? [https://github.com/mainroach/crabby](https://github.com/mainroach/crabby)
[samples.zip](https://xentaxbackup.github.io/file/23222_samples.zip)
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-01-07T11:25:37+00:00
- Post Title: Maplestory M textures

Jenny, can you share additional samples of tile/index/palette triplets to better diagnose this (maybe 2 more), or do you have screenshots of what one of the full sprites looks like in gameplay? For curiosity, I looked at the PNG's and shader code, and temporarily hacked one of my C++ apps that displays tilemaps to try these images instead, but the palette looks only partially reasonable. The indices to rearrange the blocks look correct though.

- The 512x152 CrabBlock stores 8x8 pixel tiles as paletted 8-bit (curiously stored in the alpha channel rather than as monochrome grayscale or the red channel).
- The 16x16 palette holds the 256 colors in the 16x16 pixels directly (rather than a PNG PLTE chunk), with indices 0-255 starting at the bottom left of the 16x16 image (rather than top-left, due to OpenGL texture flipping). Applying the palette doesn't look quite right for the coat (only gray), but shiny sparks look reasonable (yellow and purple).
- The 64x32 CrabIndex image holds indices to the final reassembled texture size of 512x256 (64x32 times 8x8). It's similar in concept to how the SNES displayed tilemap graphics, except that rather than a single tile index (e.g. 0 through 1023 on the SNES), each 8x8 tile is indexed by 4 coordinates in each RGBA CrabIndex pixel (keep non-premultiplied). To compute the corresponding 8x8 block in CrabBlock, divide each CrabIndex pixel channel's RGBA / 17 (mapping 0-255 to 0-15), then compute {x = (b * 16 + a) * 8; y = (r * 16 + g) * 8}. You have to flip the images vertically too (height - y - 1) since it's using OpenGL ES (rather than D3D/Metal/Vulkan, which put the 0,0 origin at the top left).
[Maplestory-M-reassembled-CashLongCoat-2107-000136@CrabBlock@.png](https://xentaxbackup.github.io/file/23294_Maplestory-M-reassembled-CashLongCoat-2107-000136@CrabBlock@.png)
## Post #3
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-01-12T07:01:39+00:00
- Post Title: Maplestory M textures

So I'm guessing the palette issue in CashLongCoat-2107-000136@CrabBlock@ is a shader mismatch. Rather than "Transparent Colored", it may use one like "Transparent Colored+MixColor" or "Transparent Colored+SingleColor", which could tint the grayscale coat (but who knows where to find the tint color...). Multiple other images work fine (e.g. below). Well, armed with that info, I leave the rest to you.
[Maplestory-M-reassembled-MiniGame_Character@CrabBlock@.png](https://xentaxbackup.github.io/file/23293_Maplestory-M-reassembled-MiniGame_Character@CrabBlock@.png)
## Post #4
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2023-06-21T19:31:34+00:00
- Post Title: Maplestory M textures

> Reply from piken ↑Thu Jan 12, 2023 3:01 pm at Thu Jan 12, 2023 3:01 pm
>
> 
So I'm guessing the palette issue in CashLongCoat-2107-000136@CrabBlock@ is a shader mismatch. Rather than "Transparent Colored", it may use one like "Transparent Colored+MixColor" or "Transparent Colored+SingleColor", which could tint the grayscale coat (but who knows where to find the tint color...). Multiple other images work fine (e.g. below). Well, armed with that info, I leave the rest to you.

Sorry for being so late! Thank you so much for the help, but as I don't know much about how codes work, is there possibly any tool to achieve this unswizzle and palette? Again, sorry for bothering and it's completely fine if there isn't too><
## Post #5
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-06-26T03:09:49+00:00
- Post Title: Maplestory M textures

Maybe there are existing tools, but it feels like a rather game-specific format. Learning coding will definitely help you in your endeavor. For the images I shared, I just temporarily hacked a little C++ viewer app I've been working on, but it's not generic or user friendly. Though, with a little Python, numpy, and PIL imaging library, you can export them:

```
What:
    Reassemble indexed/palettized graphics.

Usage:
    python ReassembleGraphics.py block.png index.png palette.png output.png

Requirements:
    Python 3.9.17+
    pip install:
        numpy==1.25.0
        Pillow==10.0.0
"""

import sys
import numpy
from PIL import Image

tileHeight   = 8  # Height of a single graphic tile
tileWidth    = 8  # Width of a single graphic tile
indicesScale = 17

def ReassembleGraphics(filenames):
    if len(filenames) != 4:
        raise ValueError("Pass 4 filenames: graphic tiles, indices, color palette, output image")
    #endif

    # Open all 3 images
    graphicsImage = Image.open(filenames[0])
    indexImage = Image.open(filenames[1])
    paletteImage = Image.open(filenames[2])
    outputFilename = filenames[3]

    indices = numpy.asarray(indexImage)
    graphics = numpy.asarray(graphicsImage)
    palette = numpy.asarray(paletteImage)
    palette = numpy.flip(palette, 0).reshape(-1)   # Palette is a 2D image stored upside down. So restore it to 1D.
    print(f"Indices:  {indices.dtype} {indices.shape}")
    print(f"Graphics: {graphics.dtype} {graphics.shape}")
    print(f"Palette:  {palette.dtype} {palette.shape}")

    # The graphics are actually grayscale (not full color, despite the original file storing them so)
    # The palette index 0 through 255 is stored in the alpha channel.
    graphics = graphics[:, :, 3]

    indicesWidth      = indices.shape[1] # [height, width, channel]
    indicesHeight     = indices.shape[0] # [height, width, channel]
    graphicTilesWide  = graphics.shape[1] // tileWidth
    graphicTilesHigh  = graphics.shape[0] // tileHeight
    reassembledHeight = indicesHeight * tileHeight
    reassembledWidth  = indicesWidth  * tileWidth
    pixelCountPerTile = tileWidth     * tileHeight

    reassembledGraphics = numpy.zeros(shape=[reassembledHeight, reassembledWidth], dtype=numpy.uint8)
    print(f"Reassembled graphics shape: {reassembledGraphics.dtype} {reassembledGraphics.shape}")

    # Remap the tile indices back to tile indices from their awkwardly split
    # pixel values. Each color channel stores 16 distinct values, multiplied
    # by 17 to span 0 through 255. So divide it back to 0 through 15.
    indices = indices // indicesScale

    for outputTileY in range(indicesHeight):
        for outputTileX in range(indicesWidth):
            indicesPixel = indices[outputTileY, outputTileX]
            # PIL loads the image as 0=B, 1=G, 2=R, 3=A
            inputTileX   = indicesPixel[0] * 16 + indicesPixel[3]
            inputTileY   = indicesPixel[2] * 16 + indicesPixel[1]
            inputTileY   = graphicTilesHigh - 1 - inputTileY  # The graphic tiles are stored upside down
            inputPixelX  = inputTileX * tileWidth
            inputPixelY  = inputTileY * tileHeight
            outputPixelX = outputTileX * tileWidth
            outputPixelY = outputTileY * tileHeight

            # Copy the 8x8 pixel tile from input to output.
            inputView = graphics[inputPixelY:(inputPixelY+8), inputPixelX:(inputPixelX+8)]
            if inputView.size == pixelCountPerTile: # Skip if somehow degenerate (shouldn't be, but in case data is bad)
                outputView = reassembledGraphics[outputPixelY:(outputPixelY+8), outputPixelX:(outputPixelX+8)]
                outputView[:] = inputView
            #endif
        #endfor outputTileX
    #endfor outputTileY

    # Convert back to image, and save the file.
    reassembledGraphicsImage = Image.fromarray(reassembledGraphics, mode="P")
    reassembledGraphicsImage.putpalette(palette, rawmode="RGBA")
    reassembledGraphicsImage.save(outputFilename)

#enddef ReassembleGraphics

ReassembleGraphics(sys.argv[1:]) # Ignore the script name, passing all the filenames.

```
