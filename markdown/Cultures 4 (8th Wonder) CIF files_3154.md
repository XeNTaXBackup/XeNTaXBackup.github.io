## Post #1
- Username: uly
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 03, 2007 7:29 am
- Post datetime: 2008-09-12T02:30:56+00:00
- Post Title: Cultures 4 (8th Wonder) CIF files

Hello guys, I'm looking for a way to extract the .CIF files in the game "8th Wonder of the World" (or Cultures 4, or Das Achte Weltwunder).  These files are stored in the .LIB file, which itself is an archive file, probably uncompressed.  The .LIB files are unsupported by MEX but supported by Game Extractor.

The .CIF files seem to be compressed or encrypted, since they contain all kinds of data (from strings to map files, etc.), but looking at the hex code does not give any indication of the content.  The files start with the hex header
FD 03 00 00 00 00 00 00 01 00 00 00...

Any help would be appreciated.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-12T16:29:03+00:00
- Post Title: Cultures 4 (8th Wonder) CIF files

In which folder do they reside (inside the .lib)?
## Post #3
- Username: uly
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 03, 2007 7:29 am
- Post datetime: 2008-09-13T01:07:01+00:00
- Post Title: Cultures 4 (8th Wonder) CIF files

The CIF files are present in almost all of the subfolders in the .\DataX\Libs\data0001.lib, which is the main data archive.  Anywhere from data\engine2d\inis\soundfx\soundfx.cif to data\maps\campaign_03_01\text\eng\strings.cif.  The fact that it seems to contain all kinds of data is what lead me to conclude that the CIF themselves are file archives.
