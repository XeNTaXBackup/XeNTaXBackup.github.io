## Post #1
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2014-01-27T15:59:59+00:00
- Post Title: Doubt to create a save editor

Staff would like if possible to take one doubt. 
I was creating a save editor for the game Rainbow Six Vegas for xbox360. 
Unable to identify the addresses to change. 

I made an editing directly in the file, adding more ammo for my weapons test. 
Only when loading the game, it's error, stating that the save is corrupted, or no save game.
I realized that any change, no matter how small the save does not work anymore. 

Only two games I saw this problem, and DuckTales was in Rainbow Six. 
How can I create a save editor in this case, and any changes I make the save does not work anymore. 
And the following information to help save.

MAP
Offset: 0xD0C3 = Beginning map shows which part of the map was recorded chackpoint
Offset: 0x D225 = Template indicates the map (I suppose that it would be the objects and weapons on this map there)

PRIMARY WEAPON
Offset: 0xD181 = Indicates the primary weapon. 
Offset: 0xD19C / 0xD19E = Amount of ammunition (I imagine it's maximum of 3 bytes)

SECONDARY WEAPON
Offset: 0xD15A = Indicates the secondary weapon 
Offset: 0xD171 / 0xD173 = Amount of ammunition (I imagine it's maximum of 3 bytes)

WEAPONS PISTOLS
Offset: 0xD1A7 = Indicates guns
Offset: 0xD1C6 / 0xD1C8 = Amount of ammunition (I imagine it's maximum of 3 bytes)

GRANADES
Offset:  0xD1D6 = Indicates the Granada 
Offset: 0xD1F8 / 0xD1F9 = Amount of ammunition (I imagine it's maximum of 2 bytes)
Offset: 0xD1FD = Smoke Grenades 
Offset: 0xD21C / 0x D21D = Amount of ammunition (I imagine it's maximum of 2 bytes)

```

0000D000   9A 44 A3 2F 00 00 00 0B  00 00 00 12 39 39 5F 48   šD£/........99_H
0000D010   65 6C 69 52 69 64 65 73  5F 30 31 49 6E 00 00 00   eliRides_01In...
0000D020   05 14 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
0000D030   00 00 00 00 00 04 00 00  00 0B 5A 6F 6E 65 49 6E   ..........ZoneIn
0000D040   66 6F 5F 30 00 00 00 00  00 00 00 00 15 52 36 43   fo_0.........R6C
0000D050   68 65 63 6B 70 6F 69 6E  74 56 6F 6C 75 6D 65 5F   heckpointVolume_
0000D060   30 00 00 00 00 02 00 00  00 15 52 36 43 68 65 63   0.........R6Chec
0000D070   6B 70 6F 69 6E 74 56 6F  6C 75 6D 65 5F 30 00 00   kpointVolume_0..
0000D080   00 00 03 00 00 00 15 52  36 43 68 65 63 6B 70 6F   .......R6Checkpo
0000D090   69 6E 74 56 6F 6C 75 6D  65 5F 30 00 00 00 00 04   intVolume_0.....
0000D0A0   00 00 00 15 52 36 43 68  65 63 6B 70 6F 69 6E 74   ....R6Checkpoint
0000D0B0   56 6F 6C 75 6D 65 5F 33  00 FF FF FF FF 00 00 00   Volume_3.ÿÿÿÿ...
0000D0C0   00 00 00 05 14 00 00 00  1E 4D 45 58 49 43 41 4E   .........MEXICAN
0000D0D0   20 42 4F 52 44 45 52 20  2D 20 49 4E 42 4F 55 4E    BORDER - INBOUN
0000D0E0   44 20 2D 20 30 34 00 01  FF FF FF FF 00 00 00 04   D - 04..ÿÿÿÿ....
0000D0F0   00 00 00 15 52 36 43 68  65 63 6B 70 6F 69 6E 74   ....R6Checkpoint
0000D100   56 6F 6C 75 6D 65 5F 33  00 00 00 00 03 00 00 00   Volume_3........
0000D110   29 52 53 35 52 61 69 6E  62 6F 77 2E 54 65 6D 70   )RS5Rainbow.Temp
0000D120   6C 61 74 65 2E 4C 6F 67  61 6E 5F 4D 65 78 69 63   late.Logan_Mexic
0000D130   6F 54 65 6D 70 6C 61 74  65 00 00 46 5D 18 00 C5   oTemplate..F]..Å
0000D140   19 A0 00 42 A9 84 F8 00  00 00 00 00 00 80 00 00   . .B©„ø......€..
0000D150   00 00 00 00 00 00 00 00  00 00 05 00 00 00 11 52   ...............R
0000D160   36 47 61 6D 65 2E 52 36  53 75 62 4D 50 35 4E 00   6Game.R6SubMP5N.
0000D170   00 00 00 F3 00 00 00 1F  00 00 00 00 01 00 00 00   ...ó............
0000D180   00 01 00 00 00 15 52 36  47 61 6D 65 2E 52 36 41   ......R6Game.R6A
0000D190   73 73 61 75 6C 74 41 4B  34 37 00 00 00 FF FF 00   ssaultAK47...ÿÿ.
0000D1A0   00 00 1F 00 00 00 00 01  00 00 00 00 00 00 00 00   ................
0000D1B0   14 52 36 47 61 6D 65 2E  52 36 50 69 73 74 6F 6C   .R6Game.R6Pistol
0000D1C0   4D 4B 32 33 00 00 00 00  FF 00 00 00 0D 03 00 00   MK23....ÿ.......
0000D1D0   00 00 00 00 00 00 01 00  00 00 1B 52 36 47 61 6D   ...........R6Gam
0000D1E0   65 2E 52 36 47 61 64 67  65 74 47 72 65 6E 61 64   e.R6GadgetGrenad
0000D1F0   65 46 72 61 67 00 00 00  00 52 00 00 00 1C 52 36   eFrag....R....R6
0000D200   47 61 6D 65 2E 52 36 47  61 64 67 65 74 47 72 65   Game.R6GadgetGre
0000D210   6E 61 64 65 53 6D 6F 6B  65 00 00 00 00 52 00 00   nadeSmoke....R..
0000D220   00 00 00 00 00 04 00 00  00 2D 52 53 35 52 61 69   .........-RS5Rai
0000D230   6E 62 6F 77 2E 54 65 6D  70 6C 61 74 65 2E 53 65   nbow.Template.Se
0000D240   62 61 73 74 69 65 6E 5F  4D 65 78 69 63 6F 54 65   bastien_MexicoTe
0000D250   6D 70 6C 61 74 65 00 03  46 5D 18 00 C5 23 00 00   mplate..F]..Å#..
0000D260   42 A7 05 BA 00 00 00 00  00 00 40 00 00 00 00 00   B§.º......@.....
0000D270   00 00 00 00 00 00 00 06  00 00 00 19 52 36 47 61   ............R6Ga
0000D280   6D 65 2E 52 36 41 73 73  61 75 6C 74 53 43 41 52   me.R6AssaultSCAR
0000D290   48 43 51 43 00 00 00 00  EF 00 00 00 1F 00 00 00   HCQC....ï.......
0000D2A0   00 00 00 00 00 00 01 00  00 00 12 52 36 47 61 6D   ...........R6Gam
0000D2B0   65 2E 52 36 53 75 62 4D  50 37 41 31 00 00 00 00   e.R6SubMP7A1....
0000D2C0   E5 00 00 00 29 00 00 00  00 01 00 00 00 00 01 00   å...)...........
0000D2D0   00 00 14 52 36 47 61 6D  65 2E 52 36 50 69 73 74   ...R6Game.R6Pist
0000D2E0   6F 6C 4D 4B 32 33 00 00  00 00 BB 00 00 00 0D 03   olMK23....».....
0000D2F0   00 00 00 00 00 00 00 00  01 00 00 00 20 52 36 47   ............ R6G
0000D300   61 6D 65 2E 52 36 47 61  64 67 65 74 47 72 65 6E   ame.R6GadgetGren
0000D310   61 64 65 46 6C 61 73 68  62 61 6E 67 00 00 00 00   adeFlashbang....
0000D320   03 00 00 00 1E 52 36 47  61 6D 65 2E 52 36 47 61   .....R6Game.R6Ga
0000D330   64 67 65 74 47 72 65 6E  61 64 65 54 65 61 72 47   dgetGrenadeTearG
0000D340   61 73 00 00 00 00 03 00  00 00 22 52 36 47 61 6D   as........"R6Gam
0000D350   65 2E 52 36 47 61 64 67  65 74 45 78 70 6C 6F 73   e.R6GadgetExplos
0000D360   69 76 65 42 72 65 61 63  68 69 6E 67 00 00 00 00   iveBreaching....
0000D370   03 00 00 00 00 FF FF FF  FF 00 00 00 27 52 53 35   .....ÿÿÿÿ...'RS5
0000D380   52 61 69 6E 62 6F 77 2E  54 65 6D 70 6C 61 74 65   Rainbow.Template
0000D390   2E 4B 61 6E 5F 4D 65 78  69 63 6F 54 65 6D 70 6C   .Kan_MexicoTempl
0000D3A0   61 74 65 00 04 46 5E A8  00 C5 23 00 00 42 40 00   ate..F^¨.Å#..B@.
0000D3B0   01 00 00 00 00 00 00 40  00 00 00 00 00 00 00 00   .......@........
0000D3C0   00 00 00 00 06 00 00 00  14 52 36 47 61 6D 65 2E   .........R6Game.
0000D3D0   52 36 4C 4D 47 4D 32 34  39 53 50 57 00 00 00 01   R6LMGM249SPW....
0000D3E0   90 00 00 00 4E 00 00 00  00 00 00 00 00 00 01 00   ....N...........
0000D3F0   00 00 12 52 36 47 61 6D  65 2E 52 36 53 75 62 4D   ...R6Game.R6SubM
0000D400   50 37 41 31 00 00 00 00  E5 00 00 00 29 00 00 00   P7A1....å...)...
0000D410   00 01 00 00 00 00 01 00  00 00 14 52 36 47 61 6D   ...........R6Gam
0000D420   65 2E 52 36 50 69 73 74  6F 6C 4D 4B 32 33 00 00   e.R6PistolMK23..
0000D430   00 00 BB 00 00 00 0D 03  00 00 00 00 00 00 00 00   ..».............
0000D440   01 00 00 00 1B 52 36 47  61 6D 65 2E 52 36 47 61   .....R6Game.R6Ga
0000D450   64 67 65 74 47 72 65 6E  61 64 65 46 72 61 67 00   dgetGrenadeFrag.
0000D460   00 00 00 03 00 00 00 1C  52 36 47 61 6D 65 2E 52   ........R6Game.R
0000D470   36 47 61 64 67 65 74 47  72 65 6E 61 64 65 53 6D   6GadgetGrenadeSm
0000D480   6F 6B 65 00 00 00 00 03  00 00 00 22 52 36 47 61   oke........"R6Ga
0000D490   6D 65 2E 52 36 47 61 64  67 65 74 45 78 70 6C 6F   me.R6GadgetExplo
0000D4A0   73 69 76 65 42 72 65 61  63 68 69 6E 67 00 00 00   siveBreaching...
0000D4B0   00 03 00 00 00 00 FF FF  FF FF 00                  ......ÿÿÿÿ.
```
[/code]
[R6_SaveCHECKPOINT.zip](https://xentaxbackup.github.io/file/6965_R6_SaveCHECKPOINT.zip)
