## Post #1
- Username: emrekumas61
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 02, 2012 2:46 am
- Post datetime: 2014-01-18T13:27:03+00:00
- Post Title: Matrix Game Files (.ftx and .btx_28)

Hi. I want to edit The Matrix: Path of Neo. I want to know how to open these files.

The .btx_28 files are the localization files of the game. I can open them in a hex editor and edit them as I like. I also can add more characters and the game shows them perfectly with no error.

The .ftx files are the font files of the game. I tried to open these with too many programs but none of them opened. Please help me to open these font files.
[Matrix.rar](https://xentaxbackup.github.io/file/6925_Matrix.rar)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-01-20T00:37:00+00:00
- Post Title: Matrix Game Files (.ftx and .btx_28)

I guess you'll have to write your own ex-/importer for these files.
The good news is, the file format is pretty simple. I'll post the format here soon.

Here are some characters from the file (just to proof that I'm not bullshitting you):



output.bmp (7.8 KiB) Viewed 221 times
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-01-22T00:02:14+00:00
- Post Title: Matrix Game Files (.ftx and .btx_28)

Here are my findings on the file format:

0x44 and 0x48 is probably the global height of each character block

0x158-0x447 (length: 0x2F0)
here we have the character information (8 bytes per character)

struct char_info {
  uint8 char_offset;
  unit8 unknown0; // always 0x00
  uint16 block_offset;
  uint8 char_width;
  uint8 char_height;
  uint8 unknown1; // most times 0x00, sometimes 0xFF
  uint8 unknown2; // most times equals to width
};

add 0x850 to each block_offset to get the correct address of the block.
byte char_block[char_height*256]

each byte represents one pixel
I don't know how the font looks in-game but I think that this block is the alpha channel.
So 0x00 is fully transparent, 0xFF is opaque and every value in between is partly transparent.

Each block is a bitmap which is 256 pixels wide, the height is always 0x1B.
Inside this block the char_offset tells us where the actual character starts.

Here's the full character set:



MATRIX.FTX.bmp (55.05 KiB) Viewed 169 times
