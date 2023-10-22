## Post #1
- Username: SillyWills
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 22, 2016 2:26 pm
- Post datetime: 2023-04-13T12:40:30+00:00
- Post Title: crossbeats REV. SUNRISE (AC) .arc files

Hey, there! I wasn't sure if I should post this here or in the compressed files section, so I'm just taking a shot in the dark here, lol. Anyway, I'm interested in ripping this game's music, but the audio (as well as most of the game's data in general) are contained in these .arc files. I was wondering if anyone could check them out and see if it's possible to extract the data, somehow? I've got a few sample files right [here.](https://drive.google.com/file/d/1q6eUnfT6Qri7Sje-j-lHOxWsrNF-rPvM/view?usp=sharing) Thanks in advance for any assistance!
## Post #2
- Username: AdventureT
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jun 22, 2019 2:46 pm
- Post datetime: 2023-04-13T20:19:32+00:00
- Post Title: crossbeats REV. SUNRISE (AC) .arc files

Very difficult archive format it seems... Thanks for the binary, it has RTTI, vftables and some member names which does help a bit. Compression/Encryption format is Blowfish.
I also found out the ARCC stands for ARC Compressed since the binary also refers to ARC\0 which is the uncompressed version.

Here is a desc of the archive format (Imhex pattern format):

```
// Version 1.0

#include <type/magic.pat>

struct ChunkInfo {
    u8 unk[0x50];
};


struct Header {
    type::Magic<"ARCC"> magic;
    u16 version;
    u16 chunkInfoCount;
    ChunkInfo infos[chunkInfoCount];
    padding[0x8000 - $];
};

Header header @ 0x0;
```


PS: In attachments there is a funny string a dev left in range of the decompress function (at address 006e6d00).
"mofumofu capcom (^-^)"
[Bild_2023-04-13_221155983.png](https://xentaxbackup.github.io/file/23660_Bild_2023-04-13_221155983.png)
## Post #3
- Username: AdventureT
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jun 22, 2019 2:46 pm
- Post datetime: 2023-04-13T20:29:49+00:00
- Post Title: crossbeats REV. SUNRISE (AC) .arc files

Ok just found out that there exists this: [https://gitlab.com/svanheulen/mhff/-/bl ... ds/arcc.py](https://gitlab.com/svanheulen/mhff/-/blob/master/n3ds/arcc.py)

Try extracting it with this tool and maybe the funny string is actually the key?! (Which would be even funnier)

Key: mofumofu capcom(^-^)
## Post #4
- Username: SillyWills
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 22, 2016 2:26 pm
- Post datetime: 2023-05-10T14:50:08+00:00
- Post Title: crossbeats REV. SUNRISE (AC) .arc files

^Sorry for the late reply! Anyway, I tried that script, but it didn't work for me, sadly. Still, thanks for your input! Hopefully, a solution to this format will come along, someday....
