## Post #1
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2016-01-11T22:46:32+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

Does anyone know what format the .T64 files from the Virtual Console releases of The Legend of Zelda Ocarina of Time and The Legend of Zelda Majora's Mask are in? The files for NTSC, JAP, and PAL are all the same except for the rom identifier at the start of the file and I'm looking for a tool that can convert them to .png or their n64 native formats.

Link to the files:
[https://www.mediafire.com/folder/1t463d ... elda_Files](https://www.mediafire.com/folder/1t463dit81hja/Zelda_Files)

Zoinkity also mentioned the format here, assuming it's the same for the Zelda VC titles:
[http://assemblergames.com/l/threads/sin ... ion.47187/](http://assemblergames.com/l/threads/sin-and-punishment-and-other-jap-only-titels-translation.47187/)
"Did take a look at the T64 files. It's odd, since they write in columns instead of rows and the palettes are argb. Still, the images are easy enough to extract, and since I have a handy-dandy table of everything might just be able to figure out how they know what to replace where ;*)"
## Post #2
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2016-03-25T05:15:49+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

Anyone? I just need to be able to export them to png.
## Post #3
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2017-01-18T01:07:45+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

> I've only looked at a small subset of t64 files, and they were all ci4 or ci8 images.  They're saved in block format (probably interlaced as well), which is pretty typical on the backend of PCs and PC programs (like GIMP).  I think (it has been a few years) the palettes are argb and not rgba.  That said, the format is roughly this (pretty sure I'm forgetting a checksums in here though):
>
> image file format:
>
> 0x0     4       VC64
>
> 0x4     4       4-byte cart ID string
>
> 0x8     4       
>
> 0xC     4       width
>
> 0x10    4       height
>
> 0x14    4       [1:i4]
>
> 0x18    4       [1:i4]
>
> 0x1C    4       [00002000: 10x20, i4]
>
> 0x20    4       [0:i4, 8:ci4]
>
> 0x24    4       [offset of some kind, probably rdram]
>
> 0x28    2       tile width      [computed as (width-1)*4]
>
> 0x2A    2       [0000]
>
> 0x2C    4       tile height     [computed as (height-1)*4]
>
> 0x2E    2       [0000]
>
> 0x30    4       [08000054: 10x20, i4]
>
> 0x34    4       [00010000: 10x20, i4]
>
> 0x38    4       #palette entries
>
>         0x20    16 color palette
>
> var     4       binary size
>
> var     var     image binary
>
> 
>
>   Reads the images in columns, reading a word per row.
>
>   So, 4bit samples write 8 pixels in a row, 8bit samples 4 pixels, 16bit samples 2 pixels, 32bit samples 1 pixel.
>
>   Annoying, since you basically have to straighten images before exporting.
>
> 
>
>   I wasn't interested in import at all.  Pretty sure to export them you'd use something like this to straighten out a ci4 image, but since I no longer have files to test against can't guarantee anything.
>
> 
>
> def straighten(data, height):
>
>      h = height << 2
>
>      c, d = 0, bytearray()
>
>      if isinstance(data, str): data = bytes.fromhex(data)
>
>      for i in range(height):
>
>          for j in range(c, len(data), h):
>
>              d.extend(data[j:j+4])
>
>          c+=4
>
>      return d

Can this get anyone in the right direction to decode these?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-18T03:42:07+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

looks like you've been waiting a year for a response, 
i would've just dumped the textures with an emulator by now
## Post #5
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2017-01-19T19:51:34+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

I would, except the Virtual Console version of Majora's Mask I'm trying to dump the textures from doesn't run in Dolphin (crashes at the N64 logo; or after pressing A for the Japanese release). I also don't know exactly which textures these replace, since I can't look at them.
## Post #6
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2017-03-18T16:53:29+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

Well it looks like now I have code samples (C/C++? I'm not sure), but it'd be great if someone could either convert these files or write a program to do it.

> I don't have the time to convert and verify the output of all of these, but it isn't terribly difficult to do--especially if you have a dump of the originals.
>
> 
>
> Using a couple samples in one of those files here's a sort of guide on how to interpret the data.
>
> http://imgur.com/a/AvrMA
>
> 
>
> 16bit color is stored argb, not the typical rgba. The row sorting algos are in the album, illustrating how they reorganize the data. Not sure if any images are interlaced or not--none of these were--but if they are that step would likely come before sorting and not after.

> This is a raw extract, reading the image as it is naturally stored. Color is stored argb16, not the typical rgba16 used in (most) N64.
>
> 
>
> 
>
> This is iterating the image so each sequential 32bit word is on the next line. That would be equivalent to:
>
> Code: Select alldef straighten(data, height):
>
>     h = height << 2
>
>     c, d = 0, bytearray()
>
>     if isinstance(data, str): data = bytes.fromhex(data)
>
>     for i in range(height):
>
>         for j in range(c, len(data), h):
>
>            d.extend(data[j:j+4])
>
>         c+=4
>
>     return d
>
> 
>
> This reorganizes those blocks into "natural" image order. Equivalent to:
>
> Code: Select alldef blkdivide(data, width, height=8):
>
>     h = height << 2
>
>     width >>= 3
>
>     width *= h
>
>     c, d = 0, bytearray()
>
>     if isinstance(data, str): data = bytes.fromhex(data)
>
>     while c < len(data):
>
>         for i in range(height):
>
>             for j in range(c, c+width, h):
>
>                 d.extend(data[j:j+4])
>
>             c += 4
>
>         c+= (width - h)
>
>     return d
>
> 
>
> What I'm assuming is an i4 image is read no differently than a ci4 image. Internally, the number of palette entries is 0 with no placeholder between that and the size of the image binary.
>
> 
>
> Likewise, ci8 images are not read any differently.  In "block" order these would be composed of 4x8 blocks, since only four pixels will fit in a single 32bit word.
>
> Example T64 images, converted raw, organized into blocks, and fully straightened.
## Post #7
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2017-03-22T04:39:00+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

Would it be possible for someone to take all this information and write a program to convert them or is there still information needed?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-22T15:34:39+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

> Reply from Aroenai
>
> Well it looks like now I have code samples (C/C++? I'm not sure), but it'd be great if someone could either convert these files or write a program to do it.
its python and looks like someone already has a working conversion script according to what you've posted so far,
maybe you could ask this guy to give you the rest of the script so you can use it.
## Post #9
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2017-03-23T00:25:26+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

If I could get more than a few unlabeled code samples from the guy, I wouldn't be asking here...
## Post #10
- Username: NicoDE
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 09, 2017 5:35 am
- Post datetime: 2017-06-08T21:56:22+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

It's a bit more complicated since the image files are stored in 8 different formats...
```
	uint8_t  magic[4];    // "VC64"
	uint8_t  game_id[4];  // "CZLE", "NZLP", "NZSE"
	uint32_t _0008;
	uint32_t width;
	uint32_t height;
	uint32_t _0014;       // 0, 1, 2
	uint32_t _0018;       // 0, 1, 2
	uint32_t _001C;       // 0x00002000
	uint32_t format;      // 0 (i4), 1 (i8), 2 (ia4), 3 (ia8), 5 (rgb5a3), 6 (rbga8), 8 (c4), 9 (c8)
	uint32_t _0024;
	uint32_t _0028;
	uint32_t _002C;
	uint32_t _0030;
	uint32_t _0034;
	uint32_t colors;           // 0, 16 (c4), 256 (c8) 
//  uint16_t palette[colors];  // rgb5a1 (MSB alwas set, rgb5a3?)
//  uint32_t texels;
//  T        image[texels];    // uint8_t (i4, i8, ia4, c4, c8), uint16_t (ia8, rgb5a3), uint32_t (rbga8)
};
```
I'm not sure about the pallette, since the MSB is always set.
Note that 'texels' is the length of the image buffer in image words (smallest unit), not bytes.

The decoding/unswizzle logic can be seen in the Dolphin project source code:
[https://github.com/dolphin-emu/dolphin/ ... eneric.cpp](https://github.com/dolphin-emu/dolphin/blob/master/Source/Core/VideoCommon/TextureDecoder_Generic.cpp)

Archives with the PNG images are attached...
(well, I might have added bugs in the converter, but the images look OK for me - reference images would have been nice )
[mm-ntsc-vc-t64_png.zip](https://xentaxbackup.github.io/file/12976_mm-ntsc-vc-t64_png.zip)
## Post #11
- Username: NicoDE
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 09, 2017 5:35 am
- Post datetime: 2017-06-08T21:57:34+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

Second attachment...
[oot-ntsc-vc-t64_png.zip](https://xentaxbackup.github.io/file/12977_oot-ntsc-vc-t64_png.zip)
## Post #12
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2017-06-09T05:02:34+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

Nico, once again you rock! Thanks for looking into this for me too.

I think they look correct, those Snowhead_Ent_Spike_0x ones look a little strange at the bottom but I wonder if it's related to something funky in the rom that they had to work around.
## Post #13
- Username: NicoDE
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 09, 2017 5:35 am
- Post datetime: 2017-06-09T05:26:38+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

> Reply from Aroenai
>
> [...] those Snowhead_Ent_Spike_0x ones look a little strange at the bottom [...]
Have seen it, yes. But all other rgb5a3 images (with and without alpha) look fine, so I classified it as data error/corruption.

ps: note that the US_doorway2.T64 is the only file that has the game id "NZLP" (instead of the expected "CZLE").
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-09T06:10:48+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

so is there a completed tool or full source to convert the images? 
i'm sure others will encounter this thread in the future and would appreciate a concrete solution.
## Post #15
- Username: NicoDE
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 09, 2017 5:35 am
- Post datetime: 2017-06-09T06:46:49+00:00
- Post Title: Virtual Console replacement (N64?) textures (*.T64)

> Reply from AceWell
>
> so is there a completed tool or full source to convert the images?
Not yet. I started the research ages ago with a [Lazarus](https://www.lazarus-ide.org/) project. Currently it's a huge block of Pascal code with hard-coded search paths and a lot of useless testing stuff 
But, as soon as I have some spare time, I will publish a converter with source code here.
In the meantime one could use the linked source code of the Dolphin project for the decoding (seems there are some endianness issues in the decoding routines, but most systems today are little-endian anyway ).

ps: example texel offset tables from my research notes:offsets are hexadecimal
0000 = uint8_t at offset 0
0000,0001 = uint16_t with LSB at offset 1 and MSB at offset 0 (big-endian)
0000,0001,0002,0003 = uint32_t with LSB at offset 3 and MSB at offset 0 (big-endian)
format names start with the least significant bits
BGR5X1/BGR4A3X1 = if the most significant bit is set BGR5, else BGR4A3
```
+---------------------------------------+---------------------------------------+---------------------------------------+
|0000 0000 0001 0001 0002 0002 0003 0003|0020 0020 0021 0021 0022 0022 0023 0023|0040 0040 0041 0041 0042 0042 0043 0043|
|0004 0004 0005 0005 0006 0006 0007 0007|0024 0024 0025 0025 0026 0026 0027 0027|0044 0044 0045 0045 0046 0046 0047 0047|
|0008 0008 0009 0009 000A 000A 000B 000B|0028 0028 0029 0029 002A 002A 002B 002B|0048 0048 0049 0049 004A 004A 004B 004B|
|000C 000C 000D 000D 000E 000E 000F 000F|002C 002C 002D 002D 002E 002E 002F 002F|004C 004C 004D 004D 004E 004E 004F 004F|
|0010 0010 0011 0011 0012 0012 0013 0013|0030 0030 0031 0031 0032 0032 0033 0033|0050 0050 0051 0051 0052 0052 0053 0053|
|0014 0014 0015 0015 0016 0016 0017 0017|0034 0034 0035 0035 0036 0036 0037 0037|0054 0054 0055 0055 0056 0056 0057 0057|
|0018 0018 0019 0019 001A 001A 001B 001B|0038 0038 0039 0039 003A 003A 003B 003B|0058 0058 0059 0059 005A 005A 005B 005B|
|001C 001C 001D 001D 001E 001E 001F 001F|003C 003C 003D 003D 003E 003E 003F 003F|005C 005C 005D 005D 005E 005E 005F 005F|
+---------------------------------------+---------------------------------------+---------------------------------------+
|0060 0060 0061 0061 0062 0062 0063 0063|0080 0080 0081 0081 0082 0082 0083 0083|00A0 00A0 00A1 00A1 00A2 00A2 00A3 00A3|
|0064 0064 0065 0065 0066 0066 0067 0067|0084 0084 0085 0085 0086 0086 0087 0087|00A4 00A4 00A5 00A5 00A6 00A6 00A7 00A7|
|0068 0068 0069 0069 006A 006A 006B 006B|0088 0088 0089 0089 008A 008A 008B 008B|00A8 00A8 00A9 00A9 00AA 00AA 00AB 00AB|
|006C 006C 006D 006D 006E 006E 006F 006F|008C 008C 008D 008D 008E 008E 008F 008F|00AC 00AC 00AD 00AD 00AE 00AE 00AF 00AF|
|0070 0070 0071 0071 0072 0072 0073 0073|0090 0090 0091 0091 0092 0092 0093 0093|00B0 00B0 00B1 00B1 00B2 00B2 00B3 00B3|
|0074 0074 0075 0075 0076 0076 0077 0077|0094 0094 0095 0095 0096 0096 0097 0097|00B4 00B4 00B5 00B5 00B6 00B6 00B7 00B7|
|0078 0078 0079 0079 007A 007A 007B 007B|0098 0098 0099 0099 009A 009A 009B 009B|00B8 00B8 00B9 00B9 00BA 00BA 00BB 00BB|
|007C 007C 007D 007D 007E 007E 007F 007F|009C 009C 009D 009D 009E 009E 009F 009F|00BC 00BC 00BD 00BD 00BE 00BE 00BF 00BF|
+---------------------------------------+---------------------------------------+---------------------------------------+
|00C0 00C0 00C1 00C1 00C2 00C2 00C3 00C3|00E0 00E0 00E1 00E1 00E2 00E2 00E3 00E3|0100 0100 0101 0101 0102 0102 0103 0103|
|00C4 00C4 00C5 00C5 00C6 00C6 00C7 00C7|00E4 00E4 00E5 00E5 00E6 00E6 00E7 00E7|0104 0104 0105 0105 0106 0106 0107 0107|
|00C8 00C8 00C9 00C9 00CA 00CA 00CB 00CB|00E8 00E8 00E9 00E9 00EA 00EA 00EB 00EB|0108 0108 0109 0109 010A 010A 010B 010B|
|00CC 00CC 00CD 00CD 00CE 00CE 00CF 00CF|00EC 00EC 00ED 00ED 00EE 00EE 00EF 00EF|010C 010C 010D 010D 010E 010E 010F 010F|
|00D0 00D0 00D1 00D1 00D2 00D2 00D3 00D3|00F0 00F0 00F1 00F1 00F2 00F2 00F3 00F3|0110 0110 0111 0111 0112 0112 0113 0113|
|00D4 00D4 00D5 00D5 00D6 00D6 00D7 00D7|00F4 00F4 00F5 00F5 00F6 00F6 00F7 00F7|0114 0114 0115 0115 0116 0116 0117 0117|
|00D8 00D8 00D9 00D9 00DA 00DA 00DB 00DB|00F8 00F8 00F9 00F9 00FA 00FA 00FB 00FB|0118 0118 0119 0119 011A 011A 011B 011B|
|00DC 00DC 00DD 00DD 00DE 00DE 00DF 00DF|00FC 00FC 00FD 00FD 00FE 00FE 00FF 00FF|011C 011C 011D 011D 011E 011E 011F 011F|
+---------------------------------------+---------------------------------------+---------------------------------------+
```

```
+---------------------------------------+---------------------------------------+---------------------------------------+
|0000 0001 0002 0003 0004 0005 0006 0007|0020 0021 0022 0023 0024 0025 0026 0027|0040 0041 0042 0043 0044 0045 0046 0047|
|0008 0009 000A 000B 000C 000D 000E 000F|0028 0029 002A 002B 002C 002D 002E 002F|0048 0049 004A 004B 004C 004D 004E 004F|
|0010 0011 0012 0013 0014 0015 0016 0017|0030 0031 0032 0033 0034 0035 0036 0037|0050 0051 0052 0053 0054 0055 0056 0057|
|0018 0019 001A 001B 001C 001D 001E 001F|0038 0039 003A 003B 003C 003D 003E 003F|0058 0059 005A 005B 005C 005D 005E 005F|
+---------------------------------------+---------------------------------------+---------------------------------------+
|0060 0061 0062 0063 0064 0065 0066 0067|0080 0081 0082 0083 0084 0085 0086 0087|00A0 00A1 00A2 00A3 00A4 00A5 00A6 00A7|
|0068 0069 006A 006B 006C 006D 006E 006F|0088 0089 008A 008B 008C 008D 008E 008F|00A8 00A9 00AA 00AB 00AC 00AD 00AE 00AF|
|0070 0071 0072 0073 0074 0075 0076 0077|0090 0091 0092 0093 0094 0095 0096 0097|00B0 00B1 00B2 00B3 00B4 00B5 00B6 00B7|
|0078 0079 007A 007B 007C 007D 007E 007F|0098 0099 009A 009B 009C 009D 009E 009F|00B8 00B9 00BA 00BB 00BC 00BD 00BE 00BF|
+---------------------------------------+---------------------------------------+---------------------------------------+
|00C0 00C1 00C2 00C3 00C4 00C5 00C6 00C7|00E0 00E1 00E2 00E3 00E4 00E5 00E6 00E7|0100 0101 0102 0103 0104 0105 0106 0107|
|00C8 00C9 00CA 00CB 00CC 00CD 00CE 00CF|00E8 00E9 00EA 00EB 00EC 00ED 00EE 00EF|0108 0109 010A 010B 010C 010D 010E 010F|
|00D0 00D1 00D2 00D3 00D4 00D5 00D6 00D7|00F0 00F1 00F2 00F3 00F4 00F5 00F6 00F7|0110 0111 0112 0113 0114 0115 0116 0117|
|00D8 00D9 00DA 00DB 00DC 00DD 00DE 00DF|00F8 00F9 00FA 00FB 00FC 00FD 00FE 00FF|0118 0119 011A 011B 011C 011D 011E 011F|
+---------------------------------------+---------------------------------------+---------------------------------------+
```

```
+---------------------------------------+---------------------------------------+---------------------------------------+
|0000,0001 0002,0003 0004,0005 0006,0007|0020,0021 0022,0023 0024,0025 0026,0027|0040,0041 0042,0043 0044,0045 0046,0047|
|0008,0009 000A,000B 000C,000D 000E,000F|0028,0029 002A,002B 002C,002D 002E,002F|0048,0049 004A,004B 004C,004D 004E,004F|
|0010,0011 0012,0013 0014,0015 0016,0017|0030,0031 0032,0033 0034,0035 0036,0037|0050,0051 0052,0053 0054,0055 0056,0057|
|0018,0019 001A,001B 001C,001D 001E,001F|0038,0039 003A,003B 003C,003D 003E,003F|0058,0059 005A,005B 005C,005D 005E,005F|
+---------------------------------------+---------------------------------------+---------------------------------------+
|0060,0061 0062,0063 0064,0065 0066,0067|0080,0081 0082,0083 0084,0085 0086,0087|00A0,00A1 00A2,00A3 00A4,00A5 00A6,00A7|
|0068,0069 006A,006B 006C,006D 006E,006F|0088,0089 008A,008B 008C,008D 008E,008F|00A8,00A9 00AA,00AB 00AC,00AD 00AE,00AF|
|0070,0071 0072,0073 0074,0075 0076,0077|0090,0091 0092,0093 0094,0095 0096,0097|00B0,00B1 00B2,00B3 00B4,00B5 00B6,00B7|
|0078,0079 007A,007B 007C,007D 007E,007F|0098,0099 009A,009B 009C,009D 009E,009F|00B8,00B9 00BA,00BB 00BC,00BD 00BE,00BF|
+---------------------------------------+---------------------------------------+---------------------------------------+
|00C0,00C1 00C2,00C3 00C4,00C5 00C6,00C7|00E0,00E1 00E2,00E3 00E4,00E5 00E6,00E7|0100,0101 0102,0103 0104,0105 0106,0107|
|00C8,00C9 00CA,00CB 00CC,00CD 00CE,00CF|00E8,00E9 00EA,00EB 00EC,00ED 00EE,00EF|0108,0109 010A,010B 010C,010D 010E,010F|
|00D0,00D1 00D2,00D3 00D4,00D5 00D6,00D7|00F0,00F1 00F2,00F3 00F4,00F5 00F6,00F7|0110,0111 0112,0113 0114,0115 0116,0117|
|00D8,00D9 00DA,00DB 00DC,00DD 00DE,00DF|00F8,00F9 00FA,00FB 00FC,00FD 00FE,00FF|0118,0119 011A,011B 011C,011D 011E,011F|
+---------------------------------------+---------------------------------------+---------------------------------------+
```

```
+-------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
|0000,0001,0020,0021 0002,0003,0022,0023 0004,0005,0024,0025 0006,0007,0026,0027|0040,0041,0060,0061 0042,0043,0062,0063 0044,0045,0064,0065 0046,0047,0066,0067|
|0008,0009,0028,0029 000A,000B,002A,002B 000C,000D,002C,002D 000E,000F,002E,002F|0048,0049,0068,0069 004A,004B,006A,006B 004C,004D,006C,006D 004E,004F,006E,006F|
|0010,0011,0030,0031 0012,0013,0032,0033 0014,0015,0034,0035 0016,0017,0036,0037|0050,0051,0070,0071 0052,0053,0072,0073 0054,0055,0074,0075 0056,0057,0076,0077|
|0018,0019,0038,0039 001A,001B,003A,003B 001C,001D,003C,003D 001E,001F,003E,003F|0058,0059,0078,0079 005A,005B,007A,007B 005C,005D,007C,007D 005E,005F,007E,007F|
+-------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
|0080,0081,00A0,00A1 0082,0083,00A2,00A3 0084,0085,00A4,00A5 0086,0087,00A6,00A7|00C0,00C1,00E0,00E1 00C2,00C3,00E2,00E3 00C4,00C5,00E4,00E5 00C6,00C7,00E6,00E7|
|0088,0089,00A8,00A9 008A,008B,00AA,00AB 008C,008D,00AC,00AD 008E,008F,00AE,00AF|00C8,00C9,00E8,00E9 00CA,00CB,00EA,00EB 00CC,00CD,00EC,00ED 00CE,00CF,00EE,00EF|
|0090,0091,00B0,00B1 0092,0093,00B2,00B3 0094,0095,00B4,00B5 0096,0097,00B6,00B7|00D0,00D1,00F0,00F1 00D2,00D3,00F2,00F3 00D4,00D5,00F4,00F5 00D6,00D7,00F6,00F7|
|0098,0099,00B8,00B9 009A,009B,00BA,00BB 009C,009D,00BC,00BD 009E,009F,00BE,00BF|00D8,00D9,00F8,00F9 00DA,00DB,00FA,00FB 00DC,00DD,00FC,00FD 00DE,00DF,00FE,00FF|
+-------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
|0100,0101,0120,0121 0102,0103,0122,0123 0104,0105,0124,0125 0106,0107,0126,0127|0140,0141,0160,0161 0142,0143,0162,0163 0144,0145,0164,0165 0146,0147,0166,0167|
|0108,0109,0128,0129 010A,010B,012A,012B 010C,010D,012C,012D 010E,010F,012E,012F|0148,0149,0168,0169 014A,014B,016A,016B 014C,014D,016C,016D 014E,014F,016E,016F|
|0110,0111,0130,0131 0112,0113,0132,0133 0114,0115,0134,0135 0116,0117,0136,0137|0150,0151,0170,0171 0152,0153,0172,0173 0154,0155,0174,0175 0156,0157,0176,0177|
|0118,0119,0138,0139 011A,011B,013A,013B 011C,011D,013C,013D 011E,011F,013E,013F|0158,0159,0178,0179 015A,015B,017A,017B 015C,015D,017C,017D 015E,015F,017E,017F|
+-------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
|0180,0181,01A0,01A1 0182,0183,01A2,01A3 0184,0185,01A4,01A5 0186,0187,01A6,01A7|01C0,01C1,01E0,01E1 01C2,01C3,01E2,01E3 01C4,01C5,01E4,01E5 01C6,01C7,01E6,01E7|
|0188,0189,01A8,01A9 018A,018B,01AA,01AB 018C,018D,01AC,01AD 018E,018F,01AE,01AF|01C8,01C9,01E8,01E9 01CA,01CB,01EA,01EB 01CC,01CD,01EC,01ED 01CE,01CF,01EE,01EF|
|0190,0191,01B0,01B1 0192,0193,01B2,01B3 0194,0195,01B4,01B5 0196,0197,01B6,01B7|01D0,01D1,01F0,01F1 01D2,01D3,01F2,01F3 01D4,01D5,01F4,01F5 01D6,01D7,01F6,01F7|
|0198,0199,01B8,01B9 019A,019B,01BA,01BB 019C,019D,01BC,01BD 019E,019F,01BE,01BF|01D8,01D9,01F8,01F9 01DA,01DB,01FA,01FB 01DC,01DD,01FC,01FD 01DE,01DF,01FE,01FF|
+-------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
```
