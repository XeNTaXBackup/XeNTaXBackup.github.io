## Post #1
- Username: EratoTiaTuatha
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 18, 2018 7:33 am
- Post datetime: 2023-01-25T09:33:31+00:00
- Post Title: Forspoken earc archive - Luminous Engine

Forspoken uses the same archive format as Final Fantasy XV. The only notable difference seems to be that there is a new file flag that is applied to all non-reference entries.

Speculation suggests this flag denotes a new encryption algorithm that was created specifically for Forspoken to prevent people easily extracting the files right away.

The file flags from FFXV are as follows:
1: Autoload
2: Compressed
4: Reference
8: NoEarc
16: Patched
32: PatchedDeleted
64: Encrypted
128: MaskProtected

The flags used for the Forspoken assets are 1342177282, or Compressed | 1342177280. My guess is that the data is encrypted after compression, as ZLib is unable to decompress the data as-is the way it would with FFXV. This jump in flags number seems odd, but perhaps they just started at a much higher number for Forspoken related stuff to differentiate.

Due to the similarities, the modding suite Flagrum for FFXV can also be used with Forspoken. By pointing Flagrum to the Forspoken exe, the archives will be indexed much in the same way as they are with FFXV, and then the assets can be browsed directly without extraction. As this tool is open-source and the developer is more than happy to incorporate such changes into Flagrum, if someone were to solve this new flag, Flagrum could potentially be extended to work as an Asset Explorer and Mod Manager for Forspoken as well.

Flagrum-indexed file structure:



Forspoken internal file structure, as indexed with Flagrum forspoken-indexed.png (24.49 KiB) Viewed 132 times



Flagrum github: [https://github.com/Kizari/Flagrum](https://github.com/Kizari/Flagrum)
Links to the Exineris discord as well, which you should join if you have questions or contributions.



UPDATE: compression changes have been solved and files can now be extracted successfully. Follow work on the textures: viewtopic.php?t=26322
