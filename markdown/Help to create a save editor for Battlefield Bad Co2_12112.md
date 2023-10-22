## Post #1
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2014-10-14T23:53:36+00:00
- Post Title: Help to create a save editor for Battlefield Bad Co2

Guys I have a problem, I'm actually trying to create a save editor to help the international scene. 
The game and the Battlefield Bad Company 2, with a hex editor, I tried to find the numbers of weapons ammo I'm using and found these codes.

Offset          0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
00019AD0                                                      4F 62 6A 65 63                     Objec
00019AE0   74 73 2F 57 65 61 70 6F  6E 73 2F 48 61 6E 64 68   ts/Weapons/Handh
00019AF0   65 6C 64 2F 55 53 5F 72  67 6C 5F 58 4D 38 2F 53   eld/US_rgl_XM8/S
00019B00   50 5F 72 67 6C 5F 58 4D  38 5F 53 63 6F 70 65 64   P_rgl_XM8_Scoped
00019B10   2F 36 41 30 36 36 41 32  44 2D 41 42 38 37 2D 34   /6A066A2D-AB87-4
00019B20   33 35 36 2D 41 46 41 34  2D 35 36 37 37 34 31 43   356-AFA4-567741C
00019B30   33 39 35 42 46 00 00 00  00 1E 00 00 00 B8 00 00   395BF........¸..
00019B40   00 00 00 00 00 00 00 01  01 01 4F 62 6A 65 63 74   ..........Object
00019B50   73 2F 57 65 61 70 6F 6E  73 2F 48 61 6E 64 68 65   s/Weapons/Handhe
00019B60   6C 64 2F 4D 45 43 5F 6C  6D 67 5F 51 4A 59 38 38   ld/MEC_lmg_QJY88
00019B70   2F 53 50 5F 6C 6D 67 5F  51 4A 59 38 38 2F 35 46   /SP_lmg_QJY88/5F
00019B80   39 30 44 39 37 41 2D 46  45 45 46 2D 34 38 45 38   90D97A-FEEF-48E8
00019B90   2D 42 31 45 43 2D 44 45  31 33 37 43 46 46 32 41   -B1EC-DE137CFF2A
00019BA0   36 41 00 00 00 00 C8 00  00 00 28 00 00 00 00 00   6A....È...(.....
00019BB0       00 00 00 00 01 01 01 4F  62 6A 65 63 74 73 2F 57   .......Objects/W
00019BC0   65 61 70 6F 6E 73 2F 48  61 6E 64 68 65 6C 64 2F   eapons/Handheld/
00019BD0   55 53 5F 72 67 6C 5F 58  4D 38 2F 53 50 5F 72 67   US_rgl_XM8/SP_rg
00019BE0   6C 5F 58 4D 33 32 30 5F  53 63 6F 70 65 64 2F 37   l_XM320_Scoped/7
00019BF0   39 46 32 43 42 35 38 2D  34 45 42 46 2D 34 41 39   9F2CB58-4EBF-4A9
00019C00   44 2D 38 34 32 35 2D 44  31 44 31 33 35 45 38 42   D-8425-D1D135E8B
00019C10   35 30 41 00 00 00 00 01 00 00 00 03 00 00 00 00   50A.............


Put to the test when making the changes do not appear ie remains as original, the Hex editor to review the changes and return to the default save 1mb increases in the original size, and that 1,05Mb. 

header this file
Offset      0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
00000000   4D 43 30 32 00 0F A0 24  00 00 00 08 00 0F A0 00   MC02.. $...... .
00000010   75 56 3A 8B 04 84 EA 3C  BB B6 F6 EC D1 DC FB 6F   uV:‹.„ê<»¶öìÑÜûo

I do not know what would be, I think is the compression used
File size, in case 1024036 Kb
I do not know what would. 
I do not know what would.
What could be so if anyone can help thank you very much. 

Abs.
[PROF_SAVE.zip](https://xentaxbackup.github.io/file/7946_PROF_SAVE.zip)
