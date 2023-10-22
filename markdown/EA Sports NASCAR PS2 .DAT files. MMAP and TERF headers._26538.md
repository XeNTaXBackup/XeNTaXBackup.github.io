## Post #1
- Username: TheKingOfRockNRoll
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 05, 2023 8:34 am
- Post datetime: 2023-03-06T01:14:55+00:00
- Post Title: EA Sports NASCAR PS2 .DAT files. MMAP and TERF headers.

Well, guys...

In general, there are several topics on this forum dedicated to opening data files from PlayStation 2 NASCAR games from EA SPORTS. And unfortunately none of them seem to have been successful.

Briefly about everything. Game data files (Any. Whether it's NASCAR Thunder 2004 or 06 TTC) have the extension. DAT. When viewing these files in a hex editor, the following headers are output:

MMAP - game data?
TERF - game data?
DATA - again game data?
DIR1 - directory?
ADPCM - media (sounds, music, etc)

I tried using the madden_terf plugin from QuickBMS. Sounds, music and videos are fully readable in MPC.
It also unpacks a bunch of .tmf, .3ds and a few more files .dat files. I understand that tmf are textures and 3ds are models of machines, objects, and so on. Maybe...

BUT... no program reads them.

By the way, when viewing unpacked 3ds files in a hex editor, they will also have the MMAP header.

And the question is - is it possible to convert these extracted tmf, 3ds and dat files into something readable? And whether madden_terf it converts them correctly from .DAT archives?

On the wiki page write - game used EAGL engine various versions.
