## Post #1
- Username: rerwarwar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 14, 2015 7:04 am
- Post datetime: 2015-06-21T04:16:36+00:00
- Post Title: Jak and Daxter [PS2] music

On the Jak and Daxter disc there is a folder called MUS, with files ending in .mus. These are combinations of a soundfont and midi data. The header is like

```
  uint32_t version; // 1 version?
  uint32_t subversion; // 3 subversion?
  uint32_t minorversion; // 32 minor version?
  uint32_t oSomething; // points to start of soundbank data, -32? or is it SBv2 struct data size?
  uint32_t oBank; // this points to the start of the soundbank sample data
  uint32_t sBank; // size of sound bank
  uint32_t oMID; // pointer to sequenced music data
  uint32_t s3;
} __attribute__((packed));

E.g.: Version 1.3.32, oSomething 704, Bank offset 736 B, Bank Size 534256 B, MID offset 534992, ? 22772

```


The sounds are at offset oBank, and are ps2 adpcm. There are pointers into this data in the SBv2 structure, which looks like

```
  char signature[4]; // "SBv2"
  uint32_t version;
  uint32_t hversion;
  char name[4]; //eg "V1RA" or "BOSS"
  uint32_t a; // 0xa
  uint16_t b; //1
  uint16_t nMap;
  uint16_t nSMap;
  uint16_t nSample; // same as nMap? no it can be different...
  uint32_t f; //0x34 another offset, to end of extname from start of SBv2?
  uint32_t oInstrument; // from start of SBv2
  uint32_t oRegions; // from start of SBv2
  uint32_t i; //0x5040
  uint32_t sizeofsamples; // same as in file header
  uint32_t k; //0
  uint32_t l; //4 or 5?
  char extname[12]; // e.g. "V1RAV1RAV1RA"
  uint16_t m;
  uint16_t n;
  uint16_t o;
  uint16_t p;
  uint32_t q;
} __attribute__((packed));

```


After this are the instrument definitions, which are what are selected when there is a midi program change event:

```
  uint8_t nRegion; // usually 1
  uint8_t volume; // ? maybe... like 7f is 1.0?
  uint16_t something; // always 0
  uint32_t oRegion; // relative to start of SBv2 block I think, points to the first region for instrument
} __attribute__((packed));

```


The instrument regions look like

```
  uint8_t type; //? always 0
  uint8_t marker1; // usually 7f, not always, maybe another volume?
  uint8_t a; // not same for same sample data
  uint8_t b; // not same for same sample data
  int16_t c; // signed in range +/- 64? Tuning? intruments with 2 regions seem to have these in a plus minus couple, maybe panorama?
  uint32_t keymap; //? LSB is only set for programs with multiple entries?
  uint16_t marker2; // 0x80ff, bt sometimes LSB is dX
  uint8_t type2; // in range c9 - d1? can be different for same sample data
  uint8_t marker3; // always 9f, or 0x80 | 0x1f?
  uint16_t version; //? 1 or 0, maybe looped flag? not same sample data
  uint32_t oSample; // offset to sample from start of sample bank
  uint32_t sampleID; // I think it's the index in the sample bank...
} __attribute__((packed));

```


And that is all for the sound font stuff. The sequence data comes afterwards, starting with

```
  u32 version; // 2
  u32 subversion; // 1
  u32 number; // 16
  u32 size; // Size of sequence data following this struct
} __attribute__((packed));

```


Then after this there is either a "MMID" or "MID " block, for multiple or single track midi. The MMID block looks like

```
  char signature[4]; // "MMID"
  u16 type; //?
  u8 a; //?
  u8 nTrack; // maybe... it's always 3 lol
  char name[4]; // e.g. "V1RA"
  u32 blank; //?
} __attribute__((packed));

```


And after this is a an array of u32 offsets to the individual MID tracks, relative to the start of the sequence data. The MID tracks look like

```
  char signature[4]; // "MID "
  u16 a;
  u16 b;
  u32 c;
  u32 d;
  char name[4]; // e.g. "V1RA"
  u32 e;
  u32 f; // offset from start of struct to midi data
  u32 g;
  u32 tempo; // microseconds per quarter note?
  u32 division; // or not...
  u16 unknown;
  u8 iTrack; // track index 0 - 2
  u8 nTrack; // number of tracks (3)
} __attribute__((packed));

```


So for now, I don't know what most of the fields mean, I have a lot of guesses but haven't really tried them out. Some examples of the instrument entries from village1.mus:

```
1: 01 7F 0000 60010000
2: 01 7F 0000 78010000

```


and then some regions

```
1: 00 7F B4 42 0000 3E460000 FF80 C9 9F 0100 30070500 13000000
2: 00 7F C2 42 0000 007F0000 FF80 D2 9F 0000 80220700 19000000
3: 00 7F BC 7C 0000 007F0000 FF80 C9 9F 0000 10AD0400 10000000

```


So instrument 1 maps to 2 regions, starting at region 0, using samples 0x12 and 0x13 for the 2 parts (small bongo drum sounds?)
instruments 2 and 3 map to the next 2 (big reverberating drum and er, muted beep?). I probably don't have the splitting correct for some of the fields... A similar layout is used in the sound banks for the sound effects (SBK), so maybe I could figure out more looking there...

As for the actual sequence data, most of the music has 3 tracks, but some (DANGER, FISHGAME, OGREBOSS) only have a single track. For the multitrack ones, the first track just has a single SysEx event and no end of stream marker, the message for VILLAGE1.MUS looks like:  750f00010001010101020e02030f02030204040305050405050506060606060707070808080908080a08080b09090c0a0a0d0a0a
Others are shorter (this is the longest I think).

Then the 2nd track is the main part of the song. The 3rd track seems to have lots of overlapping layers, and I think the SysEx message in track 1 groups blocks of channels together to overlay from the 3rd track onto the 2nd for different areas. The 3rd track has lots of SysEx 751000 or 7510001009 etc, probably related to the overlay. There are no pan or pitch bends or anything in the midi.

Oh and the NoteOff event is Dx instead of 8x like normal midi, and takes no velocity. I made a bunch of hacky code when I was trying to figure out the formats, it's up on bitbucket: [https://bitbucket.org/rerwarwar/gamestuff/src](https://bitbucket.org/rerwarwar/gamestuff/src), in JAD folder. Er, if you clone it on linux (I should maybe use multiple instead of folders...), you should be able to just run make to build all the stuff. There's mus2samples for dumping samples to wav, mus2midi for attempting to make a midi file output (terrible), and mus2wav for making a max 1 minute wav from the sample e.g. "mus2wav VILLAGE1.MUS 1" should give an approximation of sandover beach, in seq.wav. I tried to make mus2dls but sort of gave up half way... And the mountain pass klaww music was missing when I looked through, maybe I deleted the file accidentally, or it could be embedded in the level data.

Hopefully this helps anyone else trying to figure out the sequenced music format of this game or others like it (I think the Sly Cooper games used same format?).
## Post #2
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-07-20T17:10:25+00:00
- Post Title: Jak and Daxter [PS2] music

Edit: Yeeeaaah I probably should've checked the SND989.IRX driver...
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-26T01:56:56+00:00
- Post Title: Jak and Daxter [PS2] music

It's great to see someone working on this again
