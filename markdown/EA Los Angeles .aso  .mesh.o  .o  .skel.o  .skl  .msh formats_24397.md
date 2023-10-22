## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-25T19:42:16+00:00
- Post Title: EA Los Angeles .aso / .mesh.o / .o / .skel.o / .skl / .msh formats

I'm looking for a way to convert these formats (.aso / .mesh.o / .o / .skel.o / .skl / .msh) from the following games:

2002 Medal of Honor: Frontline (.msh / .skl) — [SAMPLE](https://drive.google.com/open?id=1UkMdAu20oj_Ubz0B6l7xEVe84702pUa2) ([.msh hex preview](https://drive.google.com/open?id=1F_NZLEQ7st65kKqDmR1F7eHOgAwmYEZY))
2003 Medal of Honor: Rising Sun (.aso / .msh / .mesh.o / .skel.o) — [SAMPLE](https://drive.google.com/open?id=1td3-BHToYJ8DYnbhXGympKN7f8bW9-4P) ([.mesh.o hex preview](https://drive.google.com/open?id=1qotxXqU0PPVtw-CrcsJPx4ENfTNAaqy8))
2004 Golden Eye: Rogue Agent (.aso / .msh / .mesh.o / .skel.o) — [SAMPLE](https://drive.google.com/open?id=1SSmuE6DI4AEcfxrKX4FhmV1kZkNwuDry) ([.skel.o hex preview](https://drive.google.com/open?id=1Al3w2G59Hj7J7rSvQiwY3OJ-Q2PE_7Fu), [.mesh.o hex preview](https://drive.google.com/open?id=1GLSs7NCDjcnysRPKol-ER1uvQSJLrWeS))

2005 Medal of Honor: European Assault — couldn't find any models, since not all archive formats can be unpacked yet
2007 Medal of Honor: Vanguard — couldn't find any models, since not all archive formats can be unpacked yet

```
.mesh.o		- model (2003-2004)
.o		- model (2003-2004)
.skel.o		- skeleton (2003-2004)
.skl		- skeleton (2002)
.msh		- models? (2002) - can contain SHPS string, possible texture container?
```


This is the closest tool I could find for the formats. But unfortunately it work with PC files only:
[viewtopic.php?f=16&t=21675](https://forum.xentax.com/viewtopic.php?f=16&t=21675)

p.s.: texture .ssh research: [viewtopic.php?f=18&t=24396](https://forum.xentax.com/viewtopic.php?f=18&t=24396)
archive .cpt / .rtc / .str / .cdb research: [viewtopic.php?f=10&t=24395](https://forum.xentax.com/viewtopic.php?f=10&t=24395)
## Post #2
- Username: santiagogustavo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 12, 2023 12:33 pm
- Post datetime: 2023-07-17T00:31:52+00:00
- Post Title: EA Los Angeles .aso / .mesh.o / .o / .skel.o / .skl / .msh formats

Hi friend!

Passing by to thank you for the .ssh textures plugin for Noesis. I've also been very interested in ripping the files from Goldeneye Rogue Agent because I'm enthusiastic of game development and I wanted to try out a "pc port" of sorts.

My experience in reverse engineering is very short, but I was able to rip some .elf files and a .o that looks like a file structure declaration at the root of the PS2 ISO. I could also unpack the .viv files and check the textures using your plugin. Due to my lack of understanding of hex decryption I uploaded those files here for you to check out: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/15Fije0uM6olxGStHZQngNjejM2AW5-As?usp=sharing)

I've also ran 
```
readelf -a GE2RDVD.ELF
```
 from a Linux terminal, here's the following results:

```
  Magic:   7f 45 4c 46 01 01 01 00 00 00 00 00 00 00 00 00
  Class:                             ELF32
  Data:                              2's complement, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  ABI Version:                       0
  Type:                              EXEC (Executable file)
  Machine:                           MIPS R3000
  Version:                           0x1
  Entry point address:               0x106608
  Start of program headers:          52 (bytes into file)
  Start of section headers:          5847180 (bytes into file)
  Flags:                             0x20924001, noreorder, 5900, eabi64, mips3
  Size of this header:               52 (bytes)
  Size of program headers:           32 (bytes)
  Number of program headers:         1
  Size of section headers:           40 (bytes)
  Number of section headers:         22
  Section header string table index: 21

Section Headers:
  [Nr] Name              Type            Addr     Off    Size   ES Flg Lk Inf Al
  [ 0]                   NULL            00000000 000000 000000 00      0   0  0
  [ 1] .text             PROGBITS        00106600 000080 493c08 00  AX  0   0 64
  [ 2] .reginfo          MIPS_REGINFO    00000000 5900e8 000018 01      0   0  4
  [ 3] .DVP.ovlytab      LOPROC+0xffff42 00000000 590100 000060 0c   W  4   0  4
  [ 4] .DVP.ovlystrtab   STRTAB          00000000 590160 000127 00      0   0  1
  [ 5] .DVP.overlay..0x0 LOPROC+0xffff42 00000000 590287 000800 00  WX  0   0  1
  [ 6] .DVP.overlay..0x8 LOPROC+0xffff42 00000000 590a87 000800 00  WX  0   0  1
  [ 7] .DVP.overlay..0x1 LOPROC+0xffff42 00000000 591287 000800 00  WX  0   0  1
  [ 8] .DVP.overlay..0x1 LOPROC+0xffff42 00000000 591a87 000800 00  WX  0   0  1
  [ 9] .DVP.overlay..0x2 LOPROC+0xffff42 00000000 592287 000800 00  WX  0   0  1
  [10] .DVP.overlay..0x2 LOPROC+0xffff42 00000000 592a87 000208 00  WX  0   0  1
  [11] .DVP.overlay..0x0 LOPROC+0xffff42 00000000 592c8f 000800 00  WX  0   0  1
  [12] .DVP.overlay..unk LOPROC+0xffff42 00000000 59348f 000250 00  WX  0   0  1
  [13] .data             PROGBITS        0059a280 493d00 03e5d0 00  WA  0   0 128
  [14] .vutext           PROGBITS        005d8880 4d2300 003560 00  AX  0   0 16
  [15] .rodata           PROGBITS        005dbe00 4d5880 0af4fc 00   A  0   0 16
  [16] .gcc_except_table PROGBITS        0068b300 584d80 00005c 00  WA  0   0  4
  [17] .sdata            PROGBITS        0068b380 584e00 00b25c 00 WAp  0   0  8
  [18] .sbss             NOBITS          00696600 590080 000a18 00 WAp  0   0 64
  [19] .bss              NOBITS          00697080 5900e8 108d9c 00  WA  0   0 128
  [20] .vubss            NOBITS          0079fe1c 5900e8 000000 00  WA  0   0  1
  [21] .shstrtab         STRTAB          00000000 5936df 0001ad 00      0   0  1
Key to Flags:
  W (write), A (alloc), X (execute), M (merge), S (strings), I (info),
  L (link order), O (extra OS processing required), G (group), T (TLS),
  C (compressed), x (unknown), o (OS specific), E (exclude),
  p (processor specific)

There are no section groups in this file.

Program Headers:
  Type           Offset   VirtAddr   PhysAddr   FileSiz MemSiz  Flg Align
  LOAD           0x000080 0x00106600 0x00106600 0x58ffdc 0x69981c RWE 0x80

 Section to Segment mapping:
  Segment Sections...
   00     .text .data .vutext .rodata .gcc_except_table .sdata .sbss .bss

There is no dynamic section in this file.

There are no relocations in this file.

The decoding of unwind sections for machine type MIPS R3000 is not currently supported.

No version information found in this file.

```
## Post #3
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2023-07-17T01:18:16+00:00
- Post Title: EA Los Angeles .aso / .mesh.o / .o / .skel.o / .skl / .msh formats

If I recall correctly Need for Speed: Hot Pursuit 2 also used .o models. There are plugins for that game. Might be worth tracking down any research they have in that community. Pretty sure it was also used in the Def Jam games of that era too
## Post #4
- Username: santiagogustavo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 12, 2023 12:33 pm
- Post datetime: 2023-07-18T01:21:34+00:00
- Post Title: EA Los Angeles .aso / .mesh.o / .o / .skel.o / .skl / .msh formats

Unfortunately, none of the threads I found led to model research. The .ssh textures are accessible, but that's pretty much it.
However, I got some progress using OTools: it actually ran a dump of the EAGLRM.o file I attached previously.
You can open it using any text editor: [https://drive.google.com/file/d/1Fvk7QK ... sp=sharing](https://drive.google.com/file/d/1Fvk7QKH_yPpmZJ5M8sMPT8AVrrmS1-ce/view?usp=sharing)
