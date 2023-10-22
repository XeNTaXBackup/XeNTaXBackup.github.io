## Post #1
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2023-09-02T02:14:14+00:00
- Post Title: Zen Studios *.PXP fails to extract

Well the Zen Studios PXP script needs an update. It's been working on a lot of games I have, but not the following games/updates:

01.05 patch for Star Wars Pinball Vita, (detects chunk type 64 and 65, base game and update outside of patch_data dir works fine)
01.06 patch of Marvel Pinball PS3 (detects chunk type 64, base game and update outside of patch_data dir works fine)
01.05 patch of Star Wars Pinball PS3 (detects chunk type 64 and 65, base game and update outside of patch_data dir works fine)
All patches (aside from 0122) for Zen Pinball 2 PS3 (detect chunk type 64 and 65, base game and update outside of patch_data dir works fine)
1.22 patch of Zen Pinball 2 PS4
Wii U patch v1.4.0 of Zen Pinball 2 (detects chunk type 64, base game and update outside of patch_data dir works fine)
Version 2.1 of Zen Pinball Roller Coaster (iOS, comment out line 69 to fix at least for sfx.pxp, note the PXP format (v1) is slightly different as when a flag of an entry is 0, there's no compressed size value)
Zen Pinball 1 (PS3, base immediately crashes QuickBMS, DLC errors out with either a chunk error or incomplete file error)
Independence Day Battle Heroes main OBB (PXP) extracts fine than eventually returns the below (APK and patch extracts fine)

```
       Can't read 109760 bytes from offset 0594616a.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0    97%   90843550   93610346   . offset 0594616a

Last script line before the error or that produced the error:
  134 clog MEMORY_FILE OFFSET CHUNK_ZSIZE CHUNK_SIZE
- OFFSET       0x05934411
- ZSIZE        0x0002ca19
- SIZE         0x00040017
  coverage file 0    97%   90843550   93610346   . offset 0594616a
  coverage file -5   46%   70564      153104     . offset 00011bd8
  
```


Some sample files are attached (as of writing I'll upload the others later). As ZP2 on PS3 has many patches, only one's sample files will be provided, the same goes for the base of ZP1 on PS3, only providing a few basegame assets and one DLC as it's big. I have also documented a bit more on the PXP format here: [https://raw.githubusercontent.com/LolHa ... Package.bt](https://raw.githubusercontent.com/LolHacksRule/GameFileFormatsRE/main/ZenStudios/PX/PXPackage.bt)

Zen Pinball PS3 (+DLC 1): [https://workupload.com/archive/462KYvXrUH](https://workupload.com/archive/462KYvXrUH)
Zen Pinball PS4 Patch 1.22: [https://workupload.com/file/6myUTL4JKQW](https://workupload.com/file/6myUTL4JKQW)
Zen Pinball Wii U Patch 1.4.0 (only patch_data): [https://workupload.com/file/X4LqZW5dsgH](https://workupload.com/file/X4LqZW5dsgH)
Zen Pinball Rollercoaster v2.0: [https://workupload.com/file/KqZUFrNZrwD](https://workupload.com/file/KqZUFrNZrwD)
Independence Battle Heroes Android main OBB: [https://workupload.com/file/kQMCFPD3rwG](https://workupload.com/file/kQMCFPD3rwG)

Rebump from Zenhax
