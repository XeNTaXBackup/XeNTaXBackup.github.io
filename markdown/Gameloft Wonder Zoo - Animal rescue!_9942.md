## Post #1
- Username: Shockwave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2007 10:59 pm
- Post datetime: 2012-12-10T12:58:06+00:00
- Post Title: Gameloft Wonder Zoo - Animal rescue!

Greetings XeNTaX forum members. I have a problem with editing saves for this game. As far as I understand, game stores save file data in binary format and it is encrypted/packed in some way. I attached 2 files from the game with different amount of resources (gold) stored. 
1st file - 17868 gold
2nd file - 18288 gold
I compared these two files in a hex editor and they are completly different except for few first bytes. Example:
86 0B 01 00 2B 1A 00 00 2C 1A 00 00 01 87 3A EE
8E 0B 01 00 27 1A 00 00 28 1A 00 00 C3 98 1B 99

91 0B 01 00 28 1A 00 00 28 1A 00 00 4F 3C 88 C6 (same amount of gold as in a save No 2, just resaved game)

Maybe someone has already delt with this savegame format from Gameloft?
Your help would be greatly appreciated!   

Almost forgot to mention that this game also stores game data in a savegame.xml file, but changing values in this file doesn't affect game and all these values  are reseted after you load your game.

Game is available here for download: [https://play.google.com/store/apps/deta ... .GloftZRHM](https://play.google.com/store/apps/details?id=com.gameloft.android.ANMP.GloftZRHM)
[Savegame.rar](https://xentaxbackup.github.io/file/6077_Savegame.rar)
