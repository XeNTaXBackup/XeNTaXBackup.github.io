## Post #1
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-10-22T03:29:49+00:00
- Post Title: Bioshock BSM unreal files

Attached is what game extractor says is a version 141 unreal file.  I was hoping to extract some of these, but game extractor doesn't like them very much, and can only look inside.  I am seeing models, sounds, animations, and alot more inside these.  the blk files only had larger textures.  I would like some guidance in extracting these.  it has the rest of the sounds that I've been looking for.  the entry file attached is the smallest one, most are larger than 50mb.  i've tried unrealed, unrealpackagetool, ucc, and game extractor, with the latest coming the closest to opening the files.

so anyone have any ideas how to get the .sound files out?  they open in goldwave like raw wav data from what i've been able to see.
[Entry.rar](https://xentaxbackup.github.io/file/1695_Entry.rar)
## Post #2
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-06-02T09:26:03+00:00
- Post Title: Bioshock BSM unreal files

Sorry for necroing this topic. I got no names in .blk/.bsm files. Are there programs that can decrypt/extract data from BioShock 1 and 2?



Samples:
[https://mega.nz/folder/1WZ0XBJK#gg8V3r9IhpOqKUQ25X3Wkw](https://mega.nz/folder/1WZ0XBJK#gg8V3r9IhpOqKUQ25X3Wkw)
## Post #3
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-06-05T11:23:40+00:00
- Post Title: Bioshock BSM unreal files

*.bsm package is compressed (Zlib)

```
{
    uint Tag;
    int PackageVersion;
    uint PackageFlags;
    int NamesCount;
    int NamesOffset;
    int ExportsCount;
    int ExportsOffset;
    int ImportsCount;
    int ImportsOffset;
  
    byte[] Guid; // [16]
  
    int GenerationsCount;
    for (int i = 0; i < GenerationsCount; i++)
    {
        int ExportCount;
        int NamesCount;
    }
  
    int NumberOfChunks;
    for (int i = 0; i < NumberOfChunks; i++)
    {
        int CompressedOffset;
    }
 }
 
 struct CompressedChunk
 {
     u32 CompressedSize;
     byte[] CompressedBlock; // [CompressedSize]
 }


```

1. Read package Header
2. Read compressed chunks offsets
3. Decompress all chunks to the same buffer
4. Continue reading the package using this decompressed buffer.
## Post #4
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-06-12T07:51:35+00:00
- Post Title: Bioshock BSM unreal files

And do you care for BLKs and catalog.bdc?
## Post #5
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-06-20T21:28:58+00:00
- Post Title: Bioshock BSM unreal files

catalog.bdc holds header (array of Filenames, Foldernames, Offsets etc.) for some.blk - the one you provided is for DynamicBulkFileTextures.blk
