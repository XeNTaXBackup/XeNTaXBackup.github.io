## Post #1
- Username: rerwarwar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 14, 2015 7:04 am
- Post datetime: 2015-06-14T00:50:55+00:00
- Post Title: Ratchet and Clank PS2 disc TOC (PAL)

Not sure if this was posted somewhere else, but for the Ratchet and Clank PAL disc, the cd/dvd filesystem only has the exectuable and config files in it. The actual data files are "Hidden" (not really). The actual files appear to be stored in some sort of sector table, LBA table would be appropriate but they aren't really blocks, or logical, just regular DVD sectors. Anyway, in the PAL version, the table starts at sector 1500 and has the format:

  u32 version; // maybe?
  u32 sizeinbytes; // ends at this offset from start
  struct sectlen wads[479]; //2eef00-0x2ee008
  u32 vags[240]; //2ef2c0-2eef00 // sectors, 0 is skipped?
  struct sectlen wads2[165]; //2ef7f8-2ef2c0
  struct sectlen video[90]; //2efab8-2ef7f8
  u32 vags2[900]; //2f08c8-2efab8 // sectors, 0 is skipped?
  struct sectlen leveldirs[38]; //2f0960-2f08c8 // levels?

where the struct sectlen is just 2 32 bit values, start sector and then a length in sectors or bytes. A length or sector of 0 means an entry is unused. The vags are normal ps2 adpcm and can be converted to wav with the vag2wav tool. The "wad" files are mostly files starting with the 3 byte signature "WAD" followed by the archive size, but there are other non-wad files there. The wads are stored with their lengths in sectors, videos are recorded with their length in bytes, vags don't have the length, but it's in their headers. The leveldirs seem to store the size of the contents of the directory in sectors. The leveldirs are a similar structure to this, they are:

struct lvlhead {
  u32 levelnumber; // increments with each level, 0-18.
  u32 sizeinbytes; // offset to end of dir
  struct extent parts[20*2]; // these are stored after the dir, different parts of the level file? The first one is large, probably the level geo or something
  // actually, there might only be 4 sections ever in this part, probably the 4 essential components of each level
  u32 vags[14]; // streamed level music, with intro and loop parts
  // wads[] up to file offset size
};

The vags and wads in the level dirs refer to a region of the disc (~670 MB) not referred to in the main TOC. I haven't been able to get the format of the "WAD" files, the ps23dformat website has some info on the model and texture formats:
[https://ps23dformat.wikispaces.com/Ratchet+%26+Clank](https://ps23dformat.wikispaces.com/Ratchet+%26+Clank)
[https://ps23dformat.wikispaces.com/Ratc ... g+Commando](https://ps23dformat.wikispaces.com/Ratchet+%26+Clank+Going+Commando) (assuming it's same as 1st)

As for directory structure, there are gaps (zero values) between sector entries in the main and level TOCs that would suggest the blocks of files are from different directories, but I think that might be an artifact from the flatenning process used to make the TOC, and no dir structure is stored? I couldn't find any file names for the entries, they might be encoded as not ASCII, but I think the game probably just uses sector numbers and indices into the TOC and level dirs to find it's data.

If you have a different disc version, the way I found the TOC was to run the game in PCSX2 and look at the disc debug info, which says what sectors it reads in. The first bunch are CdRead, which is the BIOS reading in the executable, then it changes to DvdRead, reads the config file to get the video mode, and then the next sector it reads should be the TOC (1500 for me). Version 9.8 gave the sectors 1 or 2 off (e.g. 1502) but 9.4 gave the right sectors.

Hope this is useful.
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-06-14T07:12:14+00:00
- Post Title: Ratchet and Clank PS2 disc TOC (PAL)

I think its easier if you just get the HD collection for the ps3 version the files are easy to retrieve and it has HD texturemaps. 

Good work though finding this information
