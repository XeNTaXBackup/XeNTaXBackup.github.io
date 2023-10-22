## Post #1
- Username: DemonS_HorizoN
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 14, 2004 2:21 am
- Post datetime: 2012-10-12T20:01:33+00:00
- Post Title: Darksiders 2 Savegame [PC]

I've done some research on Darksiders 2 DSAV-Files. Here is what I've found out so far:
4 Chars FF FF FF FF are often used as Seperators for different File-regions e.g. after Header-Region

Basic File-Structure:
[Header]
[Start Load Regions(MORE than ONE if DLC Campaign was played)]
[FF FF FF FF Seperator]
[Attribute Region]
[World States(Switches, Doors, Progress, Enemys)]
[unknown]
[ITEMS]
[unknown]
[Quests and Quest Targets]
[unknown(maybe statistics)]

Byte Order: Little Endian

Basic Datatypes:

```
BYTE   int8
WORD  int16
DWORD int32

struct STRING {
  WORD StringLength ;
  char String[StringLength] ;
}

struct START_REGION
{
  STRING World ;
  STRING Level ;
  STRING Start ;
}

enum DIFFICULTY {
  EASY		= 0,
  NORMAL		= 1,
  APOCALYPTIC	= 2,
  NIGHTMARE	= 3
}


```

Header:

```
WORD Version;
BYTE SignaturInformation[4] ;
DIFFICULTY Difficulty ;
BYTE NewGamePlus;
BYTE unknown ;
BYTE IsNullAtNewGameAfterDieingInNightmare ;
BYTE unknown ;
DWORD TimePlayedSeconds ;
/* 2 unknown DWORDs */
DWORD unknown[2] ;
DWORD CurentExperiencePoints ;
DWORD NextLevelExpererienceNeeded ;
DWORD LevelOfDeath ;
/* 8 unknown DWORDs */
DWORD unknown[8] ;

```

Start Load Region:

```
WORD StartLoadRegionLength ;
char StartLoadRegion[StartLoadRegionLength] ; 

```

Seperator: 4 times 0xFF 

Attribute Region:

```
DWORD GILD ;
DWORD boatmanCoins ;
DWORD CurrentHealth_No_Effect ;
DWORD unknown ;
DWORD unknown ;
DWORD SkillPoints ;
DWORD unknown[3] ;

```

World States:

```

```

Quests:

```
DWORD NumberOfQuestTargets ;
struct QuestTarget{
  STRING QuestTargetName ;
  BYTE QuestTargetStateUnknown ; // seems to be always 01 (maybe has to be done)
  BYTE QuestTargetStateVisible ; // 00 or 01
  BYTE QuestTargetStateActive ; // 01: active, 02: done
  // Hex: 01 01 02 - Objective done
}[NumberOfQuestTargets]

```
