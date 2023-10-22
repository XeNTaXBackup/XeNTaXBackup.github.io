## Post #1
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2022-12-01T21:48:33+00:00
- Post Title: Entergram's LZSS variation ("LZLR" magic)

Games used in:
KonoSuba: Cursed Relic and the Perplexed Adventurers / この素晴らしい世界に祝福を！～呪いの遺物と惑いし冒険者たち～
Umineko: Golden Fantasia / Ougon Musou Kyoku / 黄金夢想曲

Looks like a LZSS variant with separated flags/data.
Something like this:
```
0x04: uint32 - uncompressed filesize
0x08: uint32 - dataStart
0x0C-dataStart: flags/codewords
dataStart-EOF: literals
```


Found some [very old](https://web.archive.org/web/20180611030249/https://github.com/polaris-/ougon) tool for Umineko but without the available source - the repo was deleted some time in/after 2018. After some scouring, I have found the binaries.

As I am extremely unskilled when it comes to debugging and disassembly - I ask You for Your help (explanation of flags/literals/codeword in this implementation), to port for using in a Noesis script for KonoSuba graphic files.
[Samples](https://files.catbox.moe/42eay1.7z) (compressed and decompressed) from the recent KonoSuba dungeon crawler/VN.
[seacat_fight_tools.7z](https://xentaxbackup.github.io/file/23095_seacat_fight_tools.7z)
