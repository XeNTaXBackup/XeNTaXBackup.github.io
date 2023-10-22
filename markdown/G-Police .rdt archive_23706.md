## Post #1
- Username: WalterNEST
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 16, 2018 3:41 am
- Post datetime: 2021-04-07T18:36:07+00:00
- Post Title: G-Police .rdt archive

Recently I developed (with some help from DKDave on your Discord) a Noesis Python plugin that can import most of the models and tracks from Wipeout for Playstation. 
I am hoping to import models from a few other old games and the title highest on my list is G-Police. Another gem from Psygnosis with for the time stunning graphics. Major hurdle is that this game uses one large archive to store most of its files. I have only limited experience with handling archives and I currently can't figure out what do I need to do to get the files from it.
[https://drive.google.com/drive/folders/ ... LpO41v1gh1](https://drive.google.com/drive/folders/1wCXFeRRXZcCGtUlkiGd3_yLpO41v1gh1)
There are 3 files - res.rdt seems to be the actual archive. The files don't seem to be compressed as there are text briefings readable as plain text inside the archive. 
[http://wiki.xentax.com/index.php/Psygnosis_RDT](http://wiki.xentax.com/index.php/Psygnosis_RDT)
Your wiki has an entry for .rdt, but the file structure in my file does not match the entry. Is there anyone willing to help me with this? I am a quick learner and probably can do the actual work myself, but I need some pointers about what to do. Thanks in advance! 



wipeout_ship_lineup_render_by_walter_nest_dehbmmb-250t.jpg (11.75 KiB) Viewed 84 times
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-07T20:10:35+00:00
- Post Title: G-Police .rdt archive

I have checked your samples, but I couldn't figure out more than we have already described on the wiki regarding those archives, sorry.
Psygnosis is using some weird resource manager for G-Police and Overboard which is hard to crack without debugging the  game.

If the files are really not compressed, then the only option for making changes now is hex editing.
## Post #3
- Username: WalterNEST
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 16, 2018 3:41 am
- Post datetime: 2021-04-07T20:22:15+00:00
- Post Title: G-Police .rdt archive

I don't want to make changes. I was hoping to extract files - models in particular - from the archive and make a Noesis plugin that would read them.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-07T20:44:05+00:00
- Post Title: G-Police .rdt archive

Yeah, but it doesn't really change anything. Only solution left for now is manual extraction by hex editor (if you will be able to find model data in the archive).
## Post #5
- Username: WalterNEST
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 16, 2018 3:41 am
- Post datetime: 2021-04-07T21:40:43+00:00
- Post Title: G-Police .rdt archive

I was trying to explain that being to able to hex edit the files inside the archive is of no benefit for my purpose - it could be if I just wanted to do minor edits to the game.
Looking at the archive it seems it could be mostly files separated by padding of zeros. Unfortunately I don't know any file formats that the game uses so I could look for headers or familiar patterns. Is there some tool that would help me split the archive at the padding or something like that so I could try to sift through the resulting files and maybe find vertex positions, face indices or something else helpful?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-07T22:35:02+00:00
- Post Title: G-Police .rdt archive

You could try to write custom tool which is able to do one of the following:
1. Find padding areas endings and read data until next padding
2. Read hardcoded sizes and offsets and read data this way (but it requires putting those values in the tool first)
3. Recognize file signatures (if there are any) and read data until padding area

But I think I don't know any "standard" tools for that, only some general file rippers like this one [https://i.imgur.com/JW7ebl7.png](https://i.imgur.com/JW7ebl7.png)


So in my opinion the right approach would be do some debugging on this game and figure out how this resource manager work, but it will be hard and  time consuming, so I'm not sure if anyone will be able to help you with that.
## Post #7
- Username: WalterNEST
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 16, 2018 3:41 am
- Post datetime: 2021-04-07T23:14:43+00:00
- Post Title: G-Police .rdt archive

Maybe the models could be dumped from the game at runtime using some of the ripping programs. I tried it before with no luck as PC version of G-Police seems to run on DirectX 5, but I am no ripping expert. If there was way how to make that work, it should be much easier than debugging/reverse engineering the game, which would probably be too much effort for what it would bring. I want the models mostly for curiosity - most of them actually don't even look very good when compared to something like Wipeout. G-Police while not a bad looking game suffered from just about everything having this sort of dark grey vaguely metallic-looking concrete slab texture
## Post #8
- Username: Pollion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 07, 2021 7:36 am
- Post datetime: 2022-01-20T03:04:22+00:00
- Post Title: G-Police .rdt archive

I had a look at the RDT files RES.RDT, DISK1.RDT, DISK2.RDT and understood enough to parse through them. Here are some notes in pseudocode.

First, every data block in an RDT archive starts with this header:

```
    // chunkID = offset * 16 + archiveID
    // offset is of the SectionHeader itself, not the payload that follows
    uint32_t chunkID;
    uint32_t sizeInBytes;
    uint32_t u0;  // always 0?
    uint32_t u1;  // possibly two int16s, the second sometimes has an index-like value
    uint32_t numExtras;
    uint32_t extras[numExtras];  // unknown meaning
};

```


The archiveIDs for the three archives are 5, 9, 13 respectively. So, for example, a file in DISK1.RDT (archive ID = 9) at offset 0x14324 will have chunkID 0x143249. Because each file begins with a SectionHeader at offset 0, the chunkID of the first SectionHeader equals the archiveID. 

The RDT archive contains RDA2 subsections.

```
    char magic[8];  // "RDA2   \0"
    // Number of chunkIDs in the following fixed table actually used.
    uint32_t numChunkIDs;
    // The size of all chunks referenced in the RDA2Chunk, not including SectionHeaders.
    uint32_t totalPayload;
    uint32_t chunkIDs[20000];
};

```


Open an RDT and read the first SectionHeader. This will give the content size of the first RDA2 chunk, which follows immediately. Then you can read that and find all the payloads it references, then the next RDA2 chunk will follow, and so on. Note you must make a special case for reading the RDA2 chunk, because the SectionHeader only gives its contentful size, not including unused zero entries in the chunkIDs array.
## Post #9
- Username: Pollion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 07, 2021 7:36 am
- Post datetime: 2022-01-20T03:23:05+00:00
- Post Title: G-Police .rdt archive

Here is the format of RES.RDI. This file contains filenames. It may be possible to match these with the three RDT archives described above. There seems to be no reference to this RDI file in the executable, so it may be a dev file that somehow escaped into the release. The same may apply to RES.RDX.

```
    char magic[8];  // "RDI2   \0"
    uint32_t numFileNames;
    uint32_t numUnknownStrings;
};

```


The filenames are ASCIZ with the extension first and separated by a space.

```
    uint32_t alwaysZero;
    uint32_t index;
    char fileName[41];
};

```


```
    uint32_t alwaysZero;
    uint32_t index;
    char unknownString[37];
};

```


Here is an incomplete sample of existing extensions with frequencies:

TEX 3684
PAL 3684
BMP 3291
SHP 1469
WAV 776
VAG 773
RDA 116
SKN 74
MOT 52
FEB 48
STB 32

Note that I am looking at the PC version. One would expect WAV to be present and VAG to be omitted. In RES.RDT, we see examples of the sequence empty chunk, WAV, empty chunk, WAV, etc. In the filename list we also see an alternation of VAG, WAV, VAG, WAV, etc. This seems hopeful for matching up filenames sequentially.
## Post #10
- Username: Pollion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 07, 2021 7:36 am
- Post datetime: 2022-01-20T03:42:12+00:00
- Post Title: G-Police .rdt archive

RES.RDA has the same entry count as the file list in RES.RDI, and this format:

```
    char magic[8];  // "RDA2   \0"
    uint32_t numChunkIDs;
    uint32_t zero;
    uint32_t chunkIDs[numChunksIDs];
};

```


Almost all ChunkIDs in the file are 1, seeming to mean not an archive resource, as described in a previous post. Following the interesting ChunkIDs, they all seem to point to RDA2 chunks in the three RDTs.
## Post #11
- Username: Pollion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 07, 2021 7:36 am
- Post datetime: 2022-01-21T07:37:19+00:00
- Post Title: G-Police .rdt archive

I am attaching a small program showing how to process the RDT files and run tests on the data.
[rdt.7z](https://xentaxbackup.github.io/file/21656_rdt.7z)
