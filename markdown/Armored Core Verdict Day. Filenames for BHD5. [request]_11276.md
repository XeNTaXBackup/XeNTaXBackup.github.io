## Post #1
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-02T19:37:13+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

Hello.

I would like to offer the job: extracting a list of file names for the BHD container of game Armored Core: Verdict Day, developed by FromSoftware. I need a function that calculates the hash for filenames and full list of filenames.

If retrieving a complete list of names is a challenge, it will be enough just a function and examples of the names of two-three files from game archive with hashes.

You need decompile and research executable module of game for Xbox 360 or PS3.

I am willing to pay for this work. $100-200. Transfer through Paypal.

Script for parsing BHD file:

```
DWORD Endianess;
if(Endianess == 0)
    BigEndian();
    
DWORD Unknown1;
DWORD FileSize;
DWORD HashCount;
DWORD HashTableOffset <format=hex>;

struct HAT
{
    DWORD Size;
    DWORD Offset <format=hex>;
};

struct HashEntry
{
      DWORD NameHash<format=hex>;
      DWORD Size;
      QWORD Offset <format=hex>;
};

HAT Offsets[HashCount]; // 0 - 192

local int i;
for(i = 0; i < HashCount; i++)
{
    if(Offsets[i].Size)
    struct {
        HashEntry data[Offsets[i].Size];
    } hashEntry;
};

```

Files of this game are not uploaded, they are big (> 5Gb). You know where to get them.

Sorry for my bad English. I'm Russian.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-02T22:46:47+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

[http://svn.gib.me/public/darksouls/trun ... Helpers.cs](http://svn.gib.me/public/darksouls/trunk/Gibbed.DarkSouls.FileFormats/StringHelpers.cs)
## Post #3
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-03T03:38:15+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

I saw this function. It is for Dark Souls. Non for Armored Core: Verdict Day. I would not have asked here if it were so simple.

For example. XEX module (after decryption) contains string "image:/system/WorldTopHelp_Offline_$(Platform)_NA.tpf.dcx". String "$(Platform)" after formating equals "ps3" (for PS3 port). We have a string "image:/system/WorldTopHelp_Offline_ps3_NA.tpf.dcx". It points to a file at offset 0x07996216 with hash 0x6EEB4743. It's DCX-file contains TPF-file contains WorldTopHelp_Offline_ps3_NA.dds texture. I checked it.

```
StringHelpers.HashFileName("image:\\system\\WorldTopHelp_Offline_ps3_NA.tpf.dcx") == 0x93839980
StringHelpers.HashFileName("\\system\\WorldTopHelp_Offline_ps3_NA.tpf.dcx") == 0x94AA8BCB
StringHelpers.HashFileName("/system/WorldTopHelp_Offline_ps3_NA.tpf.dcx") == 0xB25F5FED
```

But must be 0x6EEB4743.

Armored Core: Verdict Day has another function. Sadly.
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-03-03T17:48:14+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

> Reply from destrator
>
> Armored Core: Verdict Day has another function. Sadly.The hash function is most certainly the same. image:/ is a virtual device, you need to figure out what image:/ points to, and for each virtual device, until you get dvdroot:/ (IIRC, this might be a slightly different name). Having the relative path alone will not give you the correct hash.
## Post #5
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-03T18:50:14+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

OK. It is file acv2.ini from dvdbnd_layer0.bdt. PATH section:

```
$(Lang)           		= jp
$(VoiceLang)           	= jp
$(Pub)            		= UBI
$(TrialTitleRes)        = Trial_Title
$(RatingSystem)			= ESRB
$(Data)           		= game_bind:
$(Common)         		= $(Data)
$(FontData)       		= $(Data)\font
$(ModelData)      		= $(Data)\model
$(MapModelData)   		= $(ModelData)\map
$(ObjModelData)   		= $(ModelData)\obj
$(EneModelData)   		= $(ModelData)\ene
$(PartsData)      		= $(Common)\Param\AcParts.bin
$(MissionData)      		= $(Common)\Lang\$(Lang)\Param\MissionInfo.bin
$(AIResource)	  		= $(Data)\AiResource
$(AIParam_mission)		= $(Data)\AiResource\Mission
$(Viewer)         		= $(Common)\Viewer
$(Effect)         		= $(Data)\Effect
$(MapViewerDefaultMap)	= $(Data)\mission\mission_0000.xml
$(CoOpDefaultMapID)		= 410
$(VersusDefaultMap)   	= $(Data)\mission\BattleFeild_5000.xml
$(TutorialMap)          = $(MapModelData)\m710\m710.msb
$(AcTestMap)            = $(MapModelData)\m720\m720.msb
$(EventStdLoadScript) 	= $(Common)\Event\Include\inc.lua
$(AIStdLoadScript)		= $(AIScript)\include\include.lua
$(AIScript)	  	  		= aiscript:
$(MissionEventScript) 	= $(Common)\Event\Mission
$(ObjectEventScript) 	= $(Common)\Event\Mission
$(NavGraph)	  			= $(Data)\AiResource\NavGraph
$(BriefingCAP)			= $(Data)\cap\briefing
$(MissionCAP)			= $(Data)\cap\mission
$(MissionDefaultCAP)	= $(MissionCAP)\MissionDefault.cap
$(TutorialCAP)			= $(Data)\cap\Tutorial
$(Movie)				= movie:\jp
$(Bind)					= $(Data)\bind\$(Lang)
$(Shader)				= $(Data)\Shader

$(LocalizeTarget) 		= $(Data)\Lang\$(Lang)
$(MenuTextDir)			= $(LocalizeTarget)\Text\Menu
$(TutorialMsg)			= $(LocalizeTarget)\Text\Tutorial\Tutorial.fmg
$(MissionMsgDir)		= $(LocalizeTarget)\Text\Mission
$(VersusMsgDir)			= $(LocalizeTarget)\Text\Versus
$(MissionDefMsgFile)	= MissionDefault
$(MissionDefaultMsg)	= $(LocalizeTarget)\Text\Mission\MissionDefault.fmg
$(KeyGuideDir)			= $(LocalizeTarget)\System
$(Ac4MenuResource)   	= $(Data)\Lang\JP\menu\Ac4
$(MenuResource)   		= $(Data)\Lang\$(Lang)\menu
$(BriefingResource)		= $(LocalizeTarget)\Briefing
$(PartsNameFmg)			= $(LocalizeTarget)\Text\PartsName_$(Lang).fmg
$(PartsExplainFmg)		= $(LocalizeTarget)\Text\PartsExplain_$(Lang).fmg
$(BindEmblemTexBase)	= Lang\jp
$(NowloadTexBase)		= $(Data)\Lang\$(Lang)\nowload\tex
$(EmblemPreparedRoot)	= $(Data)\Lang\jp\model\image\im0000\tex
$(MissionSaveData)		= /app_home/N:\ACV\data\game\common\msave
$(AutorunTest)			= /app_home/N:\ACV\data\game\common\test\AutoRun
$(RegionData)			= $(Data)\Region\$(Region)
```


Apparently the root is "game_bind:". Environment variable "$(Data)". We'll take a string from default.xex with "game_bind:".

```
game_bind:\param\colorpalette.bin
```

Computing...

```
StringHelpers.HashFileName("game_bind:/param/colorpalette.bin") == 0xF05576D8
```


But the files dvdbnd5_layer0.bhd and dvdbnd5_layer1.bhd does not contain these values​​. I checked the values ​​in big and little endian.
## Post #6
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-03-03T18:53:40+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

> Reply from destrator
>
> Code: Select allgame_bind:\param\colorpalette.bin
Computing...
Code: Select allStringHelpers.HashFileName("game_bind:\\param\\colorpalette.bin") == 0x1F1CEDDA
StringHelpers.HashFileName("game_bind:/param/colorpalette.bin") == 0xF05576D8

But the files dvdbnd5_layer0.bhd and dvdbnd5_layer1.bhd does not contain these values​​. I checked the values ​​in big and little endian.Don't include the device name. Use /param/colorpalette.bin.
## Post #7
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-03T19:06:49+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

> Reply from Rick
>
> Don't include the device name. Use /param/colorpalette.bin.

It's works! Thanks.

I promised to pay for help. I need your Paypal account.
## Post #8
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-03-03T19:32:18+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

> Reply from destrator
>
> It's works! Thanks.

I promised to pay for help. I need your Paypal account.I've sent you a PM.
## Post #9
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-03T20:20:56+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

Oh, one more little question. How this function will look like in C++?

My C# is very bad too
## Post #10
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-03-05T09:11:09+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

> Reply from destrator
>
> Oh, one more little question. How this function will look like in C++?

My C# is very bad too
```
{
    if (input == NULL || *input == '\0')
    {
      return 0;
    }
    
    uint32_t hash = 0;
    for (const char* p = input; *p != '\0'; ++p)
    {
        hash *= 37;
        hash += tolower(*p);
    }
    return hash;
}
```
Should work, though I wrote that out without testing it at all.
## Post #11
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-06T08:40:51+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

Yes, I have already found a solution.

Now I restore list of files. I have strange results. For example file StoryMission.drb.dcx is represented as: $(MenuResource)\StoryMission.drb.dcx or $(Data)\Lang\$(Lang)\menu\StoryMission.drb.dcx. We have the following:

```
/Lang/FR/menu/StoryMission.drb.dcx
/Lang/GE/menu/StoryMission.drb.dcx
/Lang/IT/menu/StoryMission.drb.dcx
/Lang/JP/menu/StoryMission.drb.dcx
/Lang/SP/menu/StoryMission.drb.dcx
```

However, hash sum is valid only for:

```
/Lang/JP/menu/StoryMission.drb.dcx
```


I need figure out more.
## Post #12
- Username: Odinv6
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 22, 2023 2:14 am
- Post datetime: 2023-08-25T14:48:46+00:00
- Post Title: Armored Core: Verdict Day. Filenames for BHD5. [request]

When will we be able to get a file name list posted.
