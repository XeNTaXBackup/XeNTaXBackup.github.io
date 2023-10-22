## Post #1
- Username: Corak
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 13, 2014 9:34 am
- Post datetime: 2015-11-04T08:22:39+00:00
- Post Title: [Request] Kingdom Under Fire (.RES)

Hi! Please help making extractor script (QuickBMS or else) for .RES format - game resource files in "Kingdom Under Fire" 
The game perfectly works with extracted resource files, so it's better to make them separated, to easly compare with translated and patched versions. Nobody still done extractor for this .res files.
Game is a little known korean Realtime-Strategy (Warcraft2/Starcraft clone) + RPG (Diablo-clone).

Examples:
[http://files.leraux.ru/Corak/Games/Stra ... /res11.res](http://files.leraux.ru/Corak/Games/Strateg/Kingdom_Under_Fire/KUF/res11.res) (Item stats)
[http://files.leraux.ru/Corak/Games/Stra ... F/res9.rar](http://files.leraux.ru/Corak/Games/Strateg/Kingdom_Under_Fire/KUF/res9.rar) (WAV's, sounds, unit speeches)

Format specification:
START:
1. start header=EFB KUF Resource File
2. 0x00 zeroes data
3. at 0x48 - files counter of index (4bytes)
4. at 0x4C - index base address location (4bytes) = 

INDEX (located at the end of file, and starting with:
1. filename size - (4bytes)
2. filename (size in 4bytes before). example - Terrain16.kti
3. folders/dirs name size - (4bytes)
4. all folders/dirs name (size in 4bytes before). example = res\MapData | res\Sound\Voice .. etc
5. ???checksum or date maybe?? (4bytes)
6. file address in resources (4bytes)
7. Filesize (4bytes)
8. ???FileType/Compressed??? (4bytes). example 0x21000000 or 0x20000000

1. ... Index for next file.
