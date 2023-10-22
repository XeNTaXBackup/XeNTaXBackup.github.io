## Post #1
- Username: lavers
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 25, 2009 12:58 pm
- Post datetime: 2009-10-25T07:56:25+00:00
- Post Title: LZH8 compression Wii Virtual Console

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-10-25T09:48:57+00:00
- Post Title: LZH8 compression Wii Virtual Console

Care to mention what game uses this?  I'd like to grab it and take a look at more examples, and maybe the binary, as I'm somewhat more adept at disassembly than compression.  Of course that assumes that this isn't some BIOS function...
## Post #3
- Username: lavers
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 25, 2009 12:58 pm
- Post datetime: 2009-10-25T21:59:26+00:00
- Post Title: LZH8 compression Wii Virtual Console

all snes virtual console games use this on the ROM file as well as emanual files, both of which are in the 00000005.app archive, not sure of the precise date they started using the compression, but i think it was around the time super punchout came out
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-10-26T04:42:56+00:00
- Post Title: LZH8 compression Wii Virtual Console

Update, and tip for anyone else hacking along, I'm looking at the VC binary that shipped with Uncharted Waters: New Horizons (US), and I think I've located the LZH8 decompression function at 0x800E77B8.  I located what seems like LZ77/LZSS at 0x800E73B8 by searching for 0x111 in the disassembly, and that's called from the sub at 0x8000BE3 which seems to be detecting things based on compression type bytes down around 0x8000BF44.
Will continue to hack at this until it looks right or wrong.

Looking good, here's lzh8_dec: [http://hcs64.com/files/lzh8_dec00.zip](http://hcs64.com/files/lzh8_dec00.zip)

Compression will be another story...
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-10-27T11:13:24+00:00
- Post Title: LZH8 compression Wii Virtual Console

Worked on compression tonight. I'm able to reproduce the LZSS behavior exactly (3 <= length <= (2^8 - 1 +3), 2 <= displacement <= (2^15-1)).  I'm nearly done with the Huffman coding but it isn't matching up with their tie-breaking algorithm yet.  Some analysis of the tree they store should allow some progress there, though if I don't figure it out soon I'll just leave it be, the total sizes will work out the same.
## Post #6
- Username: lavers
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 25, 2009 12:58 pm
- Post datetime: 2009-10-28T09:59:41+00:00
- Post Title: LZH8 compression Wii Virtual Console

wow, nice work hcs decompressor is working perfectly. I will try to catch you on irc, my nick is stev418. Ive got Bahumut Lagoon ready to try
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-10-29T11:57:57+00:00
- Post Title: LZH8 compression Wii Virtual Console

Well, this is probably as far as I'll come without a breakthrough (or cheating).
This is the latest version of the compressor and decompressor:
[http://hcs64.com/files/lzh8_cmpdec02.zip](http://hcs64.com/files/lzh8_cmpdec02.zip)
The compressor exactly duplicates the bitstream when recompressing, but something about the ordering of the tables at the beginning is different. That shouldn't matter to a decompressor, but it irritates me.

lavers tested the recompressed files and some patched compressed files, and it seems to work fine when injected back into the VC title (barring issues with VC ROM compatibility).
## Post #8
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-11-01T09:58:22+00:00
- Post Title: LZH8 compression Wii Virtual Console

Sorry to keep bumping this, should be the last time. I fixed a few bugs and finally got the table construction working exactly like the real thing.  Find it on my tools page: [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html) (rather than linking to a specific version).
## Post #9
- Username: lavers
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 25, 2009 12:58 pm
- Post datetime: 2009-11-01T21:27:28+00:00
- Post Title: LZH8 compression Wii Virtual Console

A job well done hcs, working brilliantly. Thanks for the time, i didnt think id ever get someone to get this done
