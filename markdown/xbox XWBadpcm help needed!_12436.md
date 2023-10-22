## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-28T01:18:05+00:00
- Post Title: xbox XWB/adpcm help needed!

hello

i am interested in the audio from an old xbox game (circa 2001).

the audio data should be standard adpcm as the files follow various the specs exactly:

[http://wiki.xentax.com/index.php?title=XBOX_XWB3](http://wiki.xentax.com/index.php?title=XBOX_XWB3)
[http://quickandeasysoftware.net/readmes ... ormats.htm](http://quickandeasysoftware.net/readmes/PsychonautsExplorerHelp/index.html?audiofileformats.htm)

but using aluigi's player ([http://aluigi.altervista.org/papers/xbadpdec.zip](http://aluigi.altervista.org/papers/xbadpdec.zip)) produces nothing but static when i play it back. am i missing something simple?

here is a binary template i've written for the specs anyway:

```

FSeek(0);

struct
{
    char blockname[4];
    uint version;
    uint32 soHead1;
    int32 soHead2;
    uint32 detailsDir;
    uint32 detailsDirLength;
    uint32 filenameDir;
    uint32 filenameDirLen;
    uint32 fileOffset;
    uint32 unknown_0;
    uint16 unknown_1;
    uint16 unknown_2;
    
} hdr;

Assert(hdr.blockname == "WBND");

Printf("Filecheck ok...scanning for sound files\n");

uint NoEntries;

char name[16];
uint detEntry, fnEntry, alignment, unknown;


struct ENTRIES
{
    ushort Channels;
    ushort Formats;
    uint Values;
    uint offset, length;
    uint un1, un2;
} entries[NoEntries] <optimize=false>;

struct NAMES
{
    char filename[64];
} fnames[NoEntries];

local uint i=0;

while( i < NoEntries )
{
  FSeek( entries[i].offset + alignment );

struct {
  ubyte data[entries[i].length];
} data;

  ++i;
}


```


! help
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-28T01:27:00+00:00
- Post Title: xbox XWB/adpcm help needed!

solved

it can be played back using vgmstream -> [http://hcs64.com/vgmstream.html](http://hcs64.com/vgmstream.html)

more annoying it doesn't need converting - all vgmstream does it wrap the wav headers around the first entry........
