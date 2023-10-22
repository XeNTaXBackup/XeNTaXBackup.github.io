## Post #1
- Username: johnz1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 09, 2019 8:38 am
- Post datetime: 2019-07-15T05:09:05+00:00
- Post Title: NBA Jam On Fire Edition - modifying roster update save file

I want to make roster and player ratings changes to NBA Jam On Fire Edition. I've released several roster update projects in the past 15 years for games like NFL Blitz 2003, NBA Street 2, Tecmo Super Bowl III, and Ken Griffey Jr Presents MLB. This is such a great game. It's a shame that there hasn't been an update to it in 6.5 years. I have found the data that needs to be changed - the problem is breaking the security. I haven't worked with any games as new as this one, so I'm hoping the answer is a no-brainer for the first person who reads this.

The downloadable roster update save 'NPUB305580200' contains three files:

- ICON0.PNG (save file image - not useful)
- PARAM.SFO (PS3 system file, contains system protections but not protection within the game - doesn't seem useful)
- SYS-DATA

'SYS-DATA' has two payloads (It has two "BGFA1.05" headers). The first is at 0x20 and contains XML files; the last XML file is the roster update file and the rest are Road Trip (campaign mode) matchup definitions. The second is at 0xb90a and contains graphics and other types of files (e.g. TEX, DIF). All files within are compressed with deflate/zlib. If the two payloads are split into separate files, they can be extracted with 'nbajamfire.bms' using QuickBMS.

'ROSTERUPDATE' is the XML roster update file. It defines changes made to the roster database. For testing, I'm simply changing one player rating. I've also tried modifying the "RC" files, as they can be successfully changed in the base game. The problem is that when the save file is modified, the game says that file is damaged and can't be loaded. The extraction/decompession/recompression process seems to work fine, as I can extract a file from SYS-DATA, decompress it, recompress it, and get the same CRC as the compressed file. The problem seems to be the security of 'SYS-DATA'.

There is at least one checksum in SYS-DATA, at 0x10. This is a CRC32 of 0x1c - EOF. There is also a promising 15 bytes near the beginning of SYS-DATA, just before the name of each XML file. Before each file name is 15 values, always starting with 11 and ending in 1A. The 11th value is interesting because starts at 01 and increases by one with about every other file listed. The 13th and 14th values seem to be a file size or length, as all the "RC" files (which are very small) range between "04 26" and "04 99" but "ROSTERUPDATE" (which is much bigger) is "0C E5". But the correlation doesn't seem to be direct or linear. It looks like there's another checksum immediately before the list of XML files, at 0x60-63 (D9 B6 E5 8F). I bet this is just for the first payload, but I haven't found anything yet that matches this. Other than this, I don't see anywhere else where the file could be protected.

Any help would be MUCH appreciated. Thanks for looking!


Here are the files: [https://mega.nz/#!zUk0WSQI!rfW6whpIKkNt ... RaylrcgJAc](https://mega.nz/#!zUk0WSQI!rfW6whpIKkNt2dwfzpotj4O8rQcaRk5W5RaylrcgJAc)
