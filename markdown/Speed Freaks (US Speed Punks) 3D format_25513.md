## Post #1
- Username: petitcoq
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 09, 2022 5:35 am
- Post datetime: 2022-06-09T14:45:37+00:00
- Post Title: Speed Freaks (US: Speed Punks) 3D format

Hello everyone,

I'm trying to extract 3D models and tracks from the video game Speed Freaks, and I'm posting my findings here to know if anyone have any additional information on the matter that could keep me going.

First of all, aside from the executable, a dummy filler, and two BIN files, the game disc only contains GDF files.

GDF files are uncompressed and unencrypted archives that contains all the files needed for a scene: Title screen (TITLE.GDF), menus (MENU.GDF, MENU2.GDF, etc.), tracks (LEAGUE1/L1T1D1.GDF, etc), end race podium (PODIUM.GDF), bosses(challenges?) (CHL1.GDF, CHL2.GDF, etc.).

The header of GDF files is defined as follows

```
  char magic_string[8]; // Identified for GDF files, always "0FDG XSP"
  uint32_t header_end; // Hexadecimal offset of the end of the header<
  uint32_t number_of_items; // Can be shorter than the actual number of items
  item items[number_of_items];
}
  
struct item {
  char extension[4];
  uint32_t unknown;
  uint32_t position;
  uint32_t size;
}

```


GDF archives can contain files with the following extensions: MARV, MARS, MARD, PMET, MROF, LVO, COLR.

MARV files starts with the magic string "VXSP", and seems to contain uncompressed textures with an indexed palette, among other unidentified information.
MARD files have no magic string, and seems to contain 3D information. Possible models, judging from the text strings inside. Possibly animation information, and maybe, judging by the size of some, the track itself.
MARS files starts with the magic string "HBAV". Unknown data. Possibly sounds effects. Encrypted?
MROF files starts with the magic string "MROF". Unknown data.
PMET files maybe have a magic string, but there's only one instance of the same file duplicated in some archives.
LVO files have no magic string. Unknown data. Encrypted?
COLR files starts with the magic string "COLR". Possibly a bit COLoR palette, or a COLlision file?

I've check the files of the other racing games developed by FunCom around the same era. Namely:

 Championship Motocross 2001 Featuring Ricky Carmichael (2001)
 Championship Motocross Featuring Ricky Carmichael (1999)
 Impact Racing (1996)


but none of them seems to share the same file formats. Quite the opposite, they seems to all have their own file formats.

If anyone have any information regarding Speed Freaks, of any experienced tinkerer wants to dive in, I'll be all to happy to read any additional information.

Best regards.
## Post #2
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2022-06-24T17:49:52+00:00
- Post Title: Speed Freaks (US: Speed Punks) 3D format

it's funny i'm looking at those right now.
read chunk headers backwards and you'll get the answer, VRAM, DRAM, SRAM, FORM

PSX GDF0 - format signature apparently
vram - textures
dram - must be level mesh data, or anything actually.
sram - sound banks, VAB is psx sound format, VABh is vab header iirc
ovr - overlay, chunk of executable code that can be loaded dynamically
form - dunno, maybe something for menus
colr looks like color indeed, rloc doesnt make any sense right away. however, considering it's a list of some incrementing values, i'll take a wild guess it's same as in ctr - file offsets that should be turned into ram pointers.

kaitai struct spec for gdf
[https://gist.github.com/DCxDemo/9e6aa8d ... 592528ac2d](https://gist.github.com/DCxDemo/9e6aa8dda5c74bf13c13a0592528ac2d)

the unknown value for dram is some slot number i guess, it's unique for every dram entry.
on vram it probably denotes top and bottom half of vram

dram slot 1 seems to store level data
rest is used for characters

simple extractor


 gdf.zip
(2.95 KiB) Downloaded 15 times
## Post #3
- Username: petitcoq
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 09, 2022 5:35 am
- Post datetime: 2022-06-25T15:10:17+00:00
- Post Title: Speed Freaks (US: Speed Punks) 3D format

Hello DCxDemo,

Thank you very much for your information and tool. I've wrote an extraction tool myself, but forgot to publish it. It can be downloaded here : [https://pastebin.com/a9LEASaD](https://pastebin.com/a9LEASaD)

I'm using Linux, and I haven't tried compiling it under Windows.

We both extract the exact same data, so that's a good step!
