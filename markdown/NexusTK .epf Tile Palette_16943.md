## Post #1
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-08-30T02:12:25+00:00
- Post Title: NexusTK .epf Tile Palette

Hi all,

I actually stumbled onto this forum trying to figure out this format from this post: [viewtopic.php?f=11&t=1726​](http://forum.xentax.com/viewtopic.php?f=11&t=1726%E2%80%8B)  

NexusTK is a 2D MMORPG.

There is a Map Editor for the game:
[http://www.mediafire.com/file/zxsuz45jv ... Editor.zip](http://www.mediafire.com/file/zxsuz45jv9g72k4/NexusTK-Map_Editor.zip)

This editor will use the provided /Data/ to allow a user to create .MAP files

I am interested in converting the EPF/PAL/TBL format to some sort of spritesheet.
I wanted to use graphics from a game I use to play years ago for a hobby project 2D game   

I believe that the relevant files are:

```
TileA1.pal
TileA2.pal
TileA3.pal
TileA4.pal
TileA5.pal
TileA6.pal
TileA7.pal
TileA.epf
TileA.tbl
```


In the other thread (link above), Omnilord suggested the following for each image type:

> .tbl - describes the structure 
>
> .pal - describes the pallette 
>
> .epf - stores tile data as described in the .tbl and .pal files.

Tiles are 24x24 (in the editor program)

I am assuming the actual data for the images is stored in the EPF files, which gets the colors from the PAL (palette file)
I further presume that the variants of TileA{0-9} is the "shades" of lightness/darkness as the game goes from night to day.
Maybe all that is needed is: 1 PAL file, 1 EPF file, and 1 TBL file (TileA0.pal, TileA.epf, TileA.tbl) -- further simplifying my end goal (I only need the brightest version, 0 or 9).

Diffing hex versions of: TileA0.pal and TileA1.pal show very small differences, so maybe it's variations of itself (shades).
Diffing hex versions of: TileA.epf and TileB.epf shows many differences, which smells like the actual data.

I'm uncertain how the TBL file fits into all of this though.
"describes the structure". I would think that the EPF file was doing the description of how to present the PAL colors, but that doesn't include the TBL file.

Any help would be appreciated, thanks!!
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2017-08-30T21:13:57+00:00
- Post Title: NexusTK .epf Tile Palette

This should be the file format (In C-like syntax).
Convert the files to bmp shouldn't be a big deal but I don't have the time for this right now.
Maybe someone else can work with this information.


Tile*.tbl:

```
int numbPalettes;
byte[3] unknown;
short[numTiles] paletteIndex;
```

Tile*.pal:

```
color[256] palette;

typedef struct {
  byte blue;
  byte green;
  byte red;
  byte padding; // usually 0x04
} color;
```

Tile*.epf:

```
short width;
short height;
short unknown; // always 0
int pixelDataLength;
byte[pixelDataLength] pixelData;
tableEntry[numTiles] table;

typedef struct {
  int unknown;
  short width;
  short height;
  int offsetPixelData;
  int offsetUnknown;
} tableEntry;

// additional info about the pixelData:
typedef struct {
  byte[width * height] paletteIndex;
  byte[height] unknown; // usually 0x98
} tile;
```


I haven't figured out what's going on in SObj.tbl. Apparently the tiles from TileC are put together to bigger objects in this file.
## Post #3
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-08-30T23:15:57+00:00
- Post Title: NexusTK .epf Tile Palette

Thank you so much herbert3000 for taking the time to look into this!!

I should be able to piece together the headers in a script to create the bmps, no worries there   

I am extremely curious on your process here..

What tools did you use to analyze these files? Was it file extension knowledge, or was something obvious in the hex that gave the structure away?

Thank you again!
## Post #4
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-08-30T23:21:24+00:00
- Post Title: NexusTK .epf Tile Palette

Also, I'll post a Python viewer/bmp exporter when I finish it up
## Post #5
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-08-31T16:27:21+00:00
- Post Title: NexusTK .epf Tile Palette

TileA*.pal Format:

```
color[256] palette;

typedef struct {
  byte blue;
  byte green;
  byte red;
  byte padding; // usually 0x04
} color;
```


The header for the PAL files may be byte[32] (or byte[0x20]).

This adds up to the files size:

4 bytes * 256 colors + 32 bytes = 1056

$ du -b TileA0.pal
>> 1056

The TBL syntax should be correct though (I wrote a Python class to store it for now)
## Post #6
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-02T06:15:11+00:00
- Post Title: NexusTK .epf Tile Palette

Success!

I'm gonna write a simple PyQt5 interface to export individual tiles (or all tiles - bulk).
## Post #7
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-04T02:04:08+00:00
- Post Title: NexusTK .epf Tile Palette

It's rough, but it's functional: [https://github.com/DizzyThermal/EPFViewer](https://github.com/DizzyThermal/EPFViewer)

Cheers!
## Post #8
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-05T20:56:43+00:00
- Post Title: NexusTK .epf Tile Palette

I added MAP file handling to the EPFViewer Github repo as well. I am starting to understand how the SObj.tbl incorporates. This appears to be "Static Objects", where groups of 10 Tiles are arranged vertically.

MAPHandler is not complete. MAP files appear to have full integers dedicated to storing an ID (short -- bytes). The other short appeared to be unused, but I am now beginning to think Tile C are for the other 2 bytes (short). This allows walls to "mix/blend" with ground tiles
## Post #9
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-14T20:27:57+00:00
- Post Title: NexusTK .epf Tile Palette

I am getting really close. I also have incorporated much of the SObj.tbl (grouping TileC tiles).

What I'm struggling with is the alpha layer, and it appears that there may be compression some sort of cipher to mix pixels around?

Anyone have any ideas?:

left: Map Maker (no source available) | right: EPFViewer

Thanks in advance!
## Post #10
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-14T23:45:53+00:00
- Post Title: NexusTK .epf Tile Palette

Counting the pixel padding (top and left) of alpha layer, I'm recognizing a pattern:

08 00 06 00 18 00 18 00 00 00 00 00 20 01 00 00

Using our structure for a tile_entry:

```
  int unknown
  short width
  short height
  int pixel_data_offset
  int unknown_offset
} tile_entry
```


I think the first unknown int is the "top" and "left" pad for alpha

08 00 and 06 00 (8-top, 6-left):


This is usually 00 00 00 00 for TileA and TileB, but those don't appear to have alpha layers.

Getting closer!
## Post #11
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-15T01:33:58+00:00
- Post Title: NexusTK .epf Tile Palette

Added some logic to put the cropped images in 24x24 blocks for rendering. Looking better:



The 10th block in doesn't look right, but its tile_entry is:

[08 00] [00 00] [18 00] [0E 00] [EA 11 00 00] [CA 12 00 00]

pad_top = 0x08
pad_left = 0x00
width = 0x18 (24 pixels)
height = 0x0E (14 pixels)



Looks like the assumed height and width are swapped 

Here's another odd one:

[13 00] [00 00] [18 00] [03 00] [16 E8 01 00] [25 E8 01 00]

pad_top = 0x13 (19 pixels)
pad_left = 0x00
width = 0x18 (24 pixels)
height = 0x03 (3 pixels)



Appears to check out..
## Post #12
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-15T02:08:43+00:00
- Post Title: NexusTK .epf Tile Palette

[Fixed and commited!](https://github.com/DizzyThermal/EPFViewer)
## Post #13
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-16T22:44:10+00:00
- Post Title: NexusTK .epf Tile Palette

Figured out the "Static Objects" (SObj.tbl) file and incorporated a viewer scroll area for it as well:


This is to mimic the Map Editor functionality:


Roadmap:

* Add functionality to read in *.MAP files and view/export to BMP
* EPF tile injection/deletion
* Map creator? X-by-Y maps
## Post #14
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-19T21:55:41+00:00
- Post Title: NexusTK .epf Tile Palette

Added MAP Viewer functionality (Open > Map File (*.map)).

This reads in and displays MAP files made with the Map Editor Program (not EPF Viewer).

Map Editor


EPF Viewer


[https://github.com/DizzyThermal/EPFViewer](https://github.com/DizzyThermal/EPFViewer)

Cheers!
## Post #15
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-20T15:57:49+00:00
- Post Title: NexusTK .epf Tile Palette

Github's [@DDeokk](https://github.com/DDeokk) generously provided more information pertaining to EPF and PAL file structures in the [EPFViewer Issues section](https://github.com/DizzyThermal/EPFViewer/issues).

Planning on implementing soon - stay tuned
## Post #16
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2017-10-07T12:31:53+00:00
- Post Title: Re: NexusTK .epf Tile Palette

Hi Dizzy,

Not sure if you need any of this information for your tool, or even if you want your tool to work with other images in the game, but here is some additional information about the following archives...
arrow, body, bow, coat, emotion, face, facedec, fan, hair, hairdec, helmet, mantle, neck, shield, shoes, spear, sword

These archives all have 2 corresponding entries in the file char.dat with the extensions PAL and DSC. The PAL one is the format you describe on your GitHub, but the DSC one is different. It kinda takes the place of the TBL file used by the tiles.

This is the DSC format, to the best of my knowledge so far...

```
  7 - null
  1 - Unknown (1)
  4 - Number of Parts
  
  // for each part (610 bytes per part)
    4 - Part ID (incremental from 0)
    4 - Palette ID Number
    4 - First Tile Number for this Part
    4 - Number of Tiles for this Part
    1 - Unknown (2)
    4 - Unknown
    1 - Unknown (4)
    4 - Unknown
    4 - Unknown
    4 - Number of Chunks (12)
  
    // for each chunk
      4 - Unknown ID
      4 - Unknown (-1/0)
      4 - Number of Blocks (4x4, then 4x2, then 4x6, to make the total of 12 blocks)
    
      // for each block
        1 - Unknown ID
        4 - null
        4 - Unknown (-1)

```


On order to read the images from the EPF files and map them to the correct PAL palette, you need to use the following fields above...

```
    4 - First Tile Number for this Part
    4 - Number of Tiles for this Part

```


For each Part, you can read the 3 fields above. The first one gives the palette ID for all images in the Part. The "First Tile Number" is the ID of the first image in the EPF file that belongs to this Part, and the "Number of Tiles" tells you the number of images in the Part.

For an example, the first entry in the DSC file might have "First Tile Number" = 0 and "Number of Tiles" = 20. In this case, all the images from 0-19 in the EPF file belong to this Part, and all use the same Palette. The second DSC entry might have "First Tile Number" = 20 and "Number of Tiles" = 8. In this case, images 20-27 belong to the Part.

The EPF file is basically the same as you wrote on GitHub, but I needed to work out the width of the image data in the EPF file as "Width = Width + (0-X Position)" and similarly for the height of the image data.

As for the Chunks and the Blocks - I have no idea what they represent, and I haven't really looked further in to them, as it isn't needed for reading the images. That said, I assume it's either something to do with the animation of the images, or placement of the images relative to other images, something like that I guess.

Hope this helps.
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2017-10-09T11:28:28+00:00
- Post Title: Re: NexusTK .epf Tile Palette

And for the remaining archives...

Effects (efx.dat)...

```
  4 - Number of Tiles
  
  // for each tile
    4 - Color Palette Number

```


Very simple. Seemed to be 40 images short of the number listed in the FRM file, but the images looked ok when I applied the palettes to them, so not sure what's going on there.


Monsters (mon.dat)...

```
  4 - Number of Monsters
  
  // for each monster...
    4 - First Image ID
    1 - Number of Blocks
    1 - Unknown
    2 - Palette Number
    
    // for each Block
      2 - Number of Chunks
      
      // for each chunk
        2 - Unknown ID
        2 - Unknown ID
        2 - Unknown (-1)
        2 - null
        1 - null

```


Pretty sure the chunks represent the direction that the "monster" image is facing, and things like that. Haven't really explored in to it though.


For the EFX and MON, they both have EPF and PAL files as well, which are the same as all the others.

Hope this helps you, if you're so interested.
## Post #18
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-10-10T17:22:17+00:00
- Post Title: Re: NexusTK .epf Tile Palette

friendsofwatto, thank you for the information, I appreciate it!

The file_reader module is intended to handle all TK file formats, so these are great additions!

As for where/how to present all the different image formats/types in the QT5 GUI is another question. I'm open to suggestions on GUI/layout structure as this is not my forte
## Post #19
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2018-02-01T22:41:43+00:00
- Post Title: Re: NexusTK .epf Tile Palette

friendsofwatto,

I got more time to look into the other file types. I am trying to read a Shield:

Shield0.epf
Shield.dsc
Shield.pal

Shield.pal expands into multiple palettes, which I handle, but when I try to read the EPF similar to the tiles (w/TBL) I get back negative numbers.

Here is how I am reading the DSC file:

```
class DSCHandler(FileHandler):
    _PART_COUNT_POS = 23

    def __init__(self, *args):
        super(DSCHandler, self).__init__(*args)
        self.seek(self._PART_COUNT_POS)
        self.part_count = self.read('int')
        self.parts = []
        for i in range(self.part_count):
            part = {}
            part['id'] = self.read('int')
            part['palette_id'] = self.read('int')
            part['frame_index'] = self.read('int')
            part['frame_count'] = self.read('int')
            self.seek(14, whence=1)
            part['chunk_count'] = self.read('int')
            part['chunks'] = []
            for j in range(part['chunk_count']):
                chunk = {}
                chunk['id'] = self.read('int')
                chunk['unk'] = self.read('int')
                chunk['block_count'] = self.read('int')
                chunk['blocks'] = []
                for k in range(chunk['block_count']):
                    block = {}
                    block['id'] = self.read('byte')
                    self.seek(4, whence=1)
                    block['unk'] = self.read('int')
                    chunk['blocks'].append(block)
                part['chunks'].append(chunk)
            self.parts.append(part)
```


I then wrote this script to try to save the first 20 frames of the first part:

```

import binascii
import io
import os
import signal
import sys

from file_reader import DSCHandler
from file_reader import EPFHandler
from file_reader import PALHandler
from file_reader import MAPHandler
from file_reader import SObjTBLHandler
from file_reader import TBLHandler

from PIL import Image

_VERBOSE = False

pal_handler = PALHandler('./Shield.pal')
print('PAL Count: {}'.format(pal_handler.pal_count))
dsc_handler = DSCHandler('./Shield.dsc')
print('Part Count: {}'.format(dsc_handler.part_count))
epf_handler = EPFHandler('./Shield0.epf', pals=pal_handler.pals, dsc=dsc_handler)
for i in range(1):
    print('  [{}] Part ID: {}'.format(i+1, dsc_handler.parts[i]['id']))
    print('  [{}] Palette ID: {}'.format(i+1, dsc_handler.parts[i]['palette_id']))
    print('  [{}] Frame Index: {}'.format(i+1, dsc_handler.parts[i]['frame_index']))
    print('  [{}] Frame Count: {}'.format(i+1, dsc_handler.parts[i]['frame_count']))
    if _VERBOSE:
        print('')
        print('  [{}] Chunk Count: {}'.format(i+1, dsc_handler.parts[i]['chunk_count']))
        for j in range(dsc_handler.parts[i]['chunk_count']):
            print('    [{}] Chunk ID: {}'.format(i+1, dsc_handler.parts[i]['chunks'][j]['id']))
            print('    [{}] Unknown: {}'.format(i+1, dsc_handler.parts[i]['chunks'][j]['unk']))
            print('    [{}] Block Count: {}'.format(i+1, dsc_handler.parts[i]['chunks'][j]['block_count']))
            for k in range(dsc_handler.parts[i]['chunks'][j]['block_count']):
                print('      [{}] Block ID: {}'.format(i+1, dsc_handler.parts[i]['chunks'][j]['blocks'][k]['id']))
                print('      [{}] Unknown: {}'.format(i+1, dsc_handler.parts[i]['chunks'][j]['blocks'][k]['unk']))


    alpha_rgb=(0, 0, 0)
    background_color='black'
    
    for i in range(dsc_handler.parts[0]['frame_count']):
        p1_first_frame = dsc_handler.parts[0]['frame_index']
        frame = epf_handler.frames[p1_first_frame+i]
        width = frame['width']
        height = frame['height']

        pixel_data_offset = frame['pixel_data_offset']
        stencil_data_offset = frame['stencil_data_offset']

        pixel_data = epf_handler.pixel_data[pixel_data_offset:pixel_data_offset+(width*height)]

        if not epf_handler.dsc:
            palette_index = 0
        else:
            palette_index = epf_handler.dsc.parts[0]['palette_id']

        pixel_bytes = []
        for j in range(height * width):
            pixel_byte = (epf_handler.pals[palette_index]['colors'][pixel_data[j]]['rgb'])
            if pixel_byte in epf_handler._ALPHA_COLORS:
                pixel_byte = alpha_rgb

            pixel_bytes.append(pixel_byte)

        if frame['top'] or frame['left'] or (height != 24 or width != 24):
            sub_image = Image.new('RGBA', (width, height), background_color)
            sub_image.putdata(pixel_bytes)

            image = Image.new('RGBA', (24, 24), background_color)
            image.paste(sub_image, (frame['left'], frame['top']))
        else:
            image = Image.new('RGBA', (width, height))
            image.putdata(pixel_bytes)

        image.save('C:\\Shield\\frame{}.bmp'.format(i))
```


I get the following error when I try to run it:

```
Part Count: 56
  [1] Part ID: 0
  [1] Palette ID: 0
  [1] Frame Index: 0
  [1] Frame Count: 20
Traceback (most recent call last):
  File "C:\Users\Stephen\Git\TKViewer\test.py", line 70, in <module>
    sub_image = Image.new('RGBA', (width, height), background_color)
  File "C:\Users\Stephen\AppData\Local\Programs\Python\Python36-32\lib\site-packages\PIL\Image.py", line 2282, in new
    _check_size(size)
  File "C:\Users\Stephen\AppData\Local\Programs\Python\Python36-32\lib\site-packages\PIL\Image.py", line 2261, in _check_size
    raise ValueError("Width and height must be >= 0")
ValueError: Width and height must be >= 0
```


Here is my File structure description:

```
byte[7] null                 (7 bytes)
byte unknown1                (1 byte)
int part_count               (4 bytes)
part[part_count] parts       (27 + (part_count * part_size) bytes)

typedef struct {
  int id                     (4 bytes)
  int palette_id             (4 bytes)
  int frame_index            (4 bytes)
  int frame_count            (4 bytes)
  byte unknown2              (1 byte)
  int unknown3               (4 bytes)
  byte unknown4              (1 byte)
  int unknown5               (4 bytes)
  int unknown6               (4 bytes)
  int chunk_count            (4 bytes)
  chunk[chunk_count] chunks  (34 + (chunk_count * chunk_size) bytes)
} part

typedef struct {
  int id                     (4 bytes)
  int unknown                (4 bytes)
  int block_count            (4 bytes)
  block[block_count] blocks  (16 + (block_count * block_size) bytes)
} chunk

typedef struct {
  byte id                    (1 byte)
  int null                   (4 bytes)
  int unknown                (4 bytes)
} block                      (9 bytes)
```


Anything wrong with my interpretation of your DSC post?

Thanks!
## Post #20
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2018-02-02T02:54:00+00:00
- Post Title: Re: NexusTK .epf Tile Palette

I think the blocks are where I'm misreading:

```
4 - Number of Blocks (4x4, then 4x2, then 4x6, to make the total of 12 blocks)
```


I started working out the file and the blocks stopped making sense:

```
# 00 00 00 00 00 00 00 01                      | (08) Null[7], Unknown[1]
# 38 00 00 00                                  | (04) Part Count (56)
# 00 00 00 00                                  | (04)   1st Part ID
# 00 00 00 00                                  | (04)   1st Palette ID
# 00 00 00 00                                  | (04)   1st Frame Index
# 14 00 00 00                                  | (04)   1st Frame Count (20)
# 02 00 00 00 00 04 00 00 00 00 00 00 00 00    | (14)   Unknown[1,4,1,4,4]
# 14 00 00 00                                  | (04)   Chunk Count (20)
# 00 00 00 00                                  | (04)     1st Chunk ID
# FF FF FF FF                                  | (04)     1st Chunk Unknown
# 04 00 00 00                                  | (04)     Block Count (4)
# ================================================================================#
# 00                                           | (01)       1st Block ID
# 00 00 00 00                                  | (04)       1st Block Null
# FF FF FF FF                                  | (04)       1st Block Unknown
# ================================================================================#
# 01                                           | (01)       2nd Block ID
# 00 00 00 00                                  | (04)       2nd Block Null
# FF FF FF FF                                  | (04)       2nd Block Unknown
# ================================================================================#
# 00                                           | (01)       3rd Block ID
# 00 00 00 00                                  | (04)       3rd Block Null
# FF FF FF FF                                  | (04)       3rd Block Unknown
# ================================================================================#
# 02                                           | (01)       4th Block ID
# 00 00 00 00                                  | (04)       4th Block Null
# FF FF FF FF                                  | (04)       4th Block Unknown
# ================================================================================#
# 01                                           | (01)       ?th Block ID
# 00 00 00 00                                  | (04)       ?th Block Null
# FF FF FF FF                                  | (04)       ?th Block Unknown
# ================================================================================#
# 04                                           | (01)       ?th Block ID
# 00 00 00 00                                  | (04)       ?th Block Null
# FF FF FF FF                                  | (04)       ?th Block Unknown
# ================================================================================#
# 00 00 00 03
# 00 00 00 00
# FF FF FF FF
# 04
# 00 00 00 00
# FF FF FF FF
```


I'm sure it's due to the block offset being wrong
## Post #21
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2018-02-03T21:14:57+00:00
- Post Title: Re: NexusTK .epf Tile Palette

Updating this a bit with some calculations:

```
Length of Header: 0x1B
Number of Parts: 0x38

(0xE94B - 0x1B) / 0x38 = 0x42A || 1066 bytes
```

Part Size is 0x42A (1066) bytes

I could parse the file by part boundary and ignore chunk/block data, but I'd like to figure out how to properly read it
## Post #22
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2018-02-06T00:54:49+00:00
- Post Title: Re: NexusTK .epf Tile Palette

Figured out my issue.

The issue was that in the EPF File's frames, the top, right, bottom, left - shorts are suppose to be signed, not unsigned.
## Post #23
- Username: JeremiahHix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 16, 2023 11:16 am
- Post datetime: 2023-09-16T04:12:53+00:00
- Post Title: Re: NexusTK .epf Tile Palette

> Reply from DizzyThermal ↑Sat Sep 02, 2017 2:15 pm at Sat Sep 02, 2017 2:15 pm
>
> 

how do i do this? i downloaded and compiled your github thing. i can't get the tiles to display. all it brings up is a viewer of items and stuff but no tiles.
