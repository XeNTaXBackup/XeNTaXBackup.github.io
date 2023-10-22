## Post #1
- Username: tiniestmoterboat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 09, 2016 1:17 pm
- Post datetime: 2016-12-31T20:15:48+00:00
- Post Title: Sly 3's sly3.wad extraction?

Before anyone asks, yes I did do research to see if someone has found out how to extract the contents.
What I found:
[http://aluigi.altervista.org/bms/sly_wal.bms](http://aluigi.altervista.org/bms/sly_wal.bms)
[viewtopic.php?f=21&t=12300](http://forum.xentax.com/viewtopic.php?f=21&t=12300) (Contains decryption routine)

The problem:
Decryption routine/BMS script supports Sly 1, 2, and the Sly 3 E3 Demo, but not the retail. The sly series was one of my childhood favourites and I'd much like to see if I could find any hidden/unused/dev room stuff in the full retail version of the game if the devs left any in it, but since its been encrypted I unfortunately cannot.

I've already looked at the SCUS_974.64 under PS2Dis and IDA, I'll be honest, I have a tiny bit of knowledge of reverse engineering assembly code but most of the part I don't know what I am looking at. I can reverse file formats just fine, just not finding out how stuff is encrypted through ASM.
I did try to search for values like 0x01A3 near 0x181D in the disassembled code(Both big and little endian), even wrote a script to do it for me, no luck.

I'm not entirely sure what the limit of what I can link is. I have the retail disk ISO'd(legally, I own the disk, can take a picture if needed w/ timestamp) and mounted for poking/prodding. Obviously I cannot upload the whole ISO for legal reasons, but I have seen people "cut" files into like 0-256 chunks? Not sure how much that would be for a binary assembly, and even then I'm not entirely sure if it is permitted on the forum. If any long time members can tell me what is needed I can provide it if it is within the forum rules. Better yet if anyone owns a copy and has already done this before and minds sharing the techniques I would be most grateful.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-01-01T01:16:19+00:00
- Post Title: Sly 3's sly3.wad extraction?

Since Aluigi wrote the BMS script, your best bet would be to provide him the first 10MB of the .WAD on his forum Zenhax under the Game Archive section.

[Zenhax Forums](http://zenhax.com/index.php)
