## Post #1
- Username: kelisidian
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 15, 2010 5:47 am
- Post datetime: 2011-03-11T20:49:54+00:00
- Post Title: Persona 3 FES font (*.FNT)

Hello everyone. I am a member of a translation team that wants to translate Persona 3 FES to spanish. We have everything to do it: the text, the graphics, the desire; except for the font. We cannot manage to edit it, no matter what.

What we have discovered, is that there is a folder called "FONT" containing two types of files: *.TMX and *.FNT 
In fact, we thought the font was in the *.TMX files, and thanks to the tool "TMX Explorer" we manage to edit... but we realized that nothing changed, we replaced all the characters to "0" (for testing), but as I say nothing changed.

So logically and by discarding, the font is on the *.FNT files. But we want to know if the font is really in there. That's we are asking for help.

The problem is, we do not know much about graphic editing. And we need guidance, we are walking blind.

So, We are asking a big favor: if you can help us to edit it, or at least guide us.

Thank you very much in advance.

PD: I attached the TMX files supposed to be the font, and the FNT files.
[FONT.rar](https://xentaxbackup.github.io/file/4046_FONT.rar)
## Post #2
- Username: RikuKH3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 26, 2012 7:37 am
- Post datetime: 2015-09-11T09:20:34+00:00
- Post Title: Persona 3 FES font (*.FNT)

Hello everyone!   After starting reversing PS2 PERSONA games font format I came here asking for help. I wrote font decompressor by simulating mips instructions and it works flawlessly with both PERSONA3 FES and PERSONA4. Output format is: 0x0-0x40 is 4-byte-per-color palette, 0x40-file_end is 4bpp 32x32 tiled bitmap.


Program itself:
[http://rghost.net/6ZYVkMHKm](http://rghost.net/6ZYVkMHKm)

Now I need to reverse process to make compressor. The thing is I'm not very good with math and whole process kinda hurts my brain.  :'( Is there any skilled programmers who can take a look at my findings and decompressor source code and help to write backward compressor? I'm really interested in modding game fonts.

Anyway, here's some format explanations based on FONT0.FNT from US version of Persona 4:

```
  0x0-0x4 header size
  0xE-0x10 total glyph count
  0x10-0x14 tile size, two word values
0x20-0x60 4-byte-per-color palette
0x60-0x3F0 font width table
  0x60-0x64 block size
  0x64-0x3F0 metrics, two 1 byte values for every glyph (left cut and right cut)
0x3F0-0xC38 unused reserved font map, 4-byte-per-glyph
0xC38-0xF4B2 compressed font area
  0xC38-0xC58 header
    0xC38-0xC3C header size
    0xC3C-0xC40 compression dictionary block size
    0xC40-0xC44 last block size
    0xC50-0xC54 glyph position table block size
    0xC54-0xC58 uncompressed font size (number-of-glyphs*512 in this case, since each is 32x32 4bpp)
  0xC58-0x17A4 compression dictionary block
    0xC58-0xC5A number of entries
    0xC5A-0xC5C number of entries subtract 1
    0xC5C-0xC5E number of dictionary entries dedicated for storing uncompressed byte values
    0xC5E-0x17A4 dictionary entries, number-of-entries * 6
      0xC5E-0xC64 dictionary entry. consists of 3 word values. first value is a entry count.
  0x17A4-0x1F88 compressed glyph position table, 4-byte-per-glyph, unused for whole decompression, required for recompression. processed by shifting value right to $4 (Rsh), shifting left to $1 (Lsh), adding last block start position.
  0x1F88-0xF4B2 compressed last block data
```
