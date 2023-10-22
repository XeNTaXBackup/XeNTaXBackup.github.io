## Post #1
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-06-09T13:18:26+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

I have an archive file (game0000.dat), that comes with some .mnf file (game.mnf). The files in .dat are simly following each other without any separator and can be unpacked without problems. They are compressed with zlib, so it's not a problem to get them. But I want to know their names and folders structure. So I'm sure, that .mnf file can help me with that. I think, that game.mnf is sort of a table with filenames, structures and maybe offsets for game0000.dat, but I can't open it and need your help with researching. I've uploaded the files [here](http://gfile.ru/aWLp).
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T13:19:17+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

what game is it?
## Post #3
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-06-09T13:22:53+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

> Reply from chrrox
>
> what game is it?
The Elder Scrolls Online.
## Post #4
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-06-09T14:39:52+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

could you pm me the launcher?
## Post #5
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2013-07-15T20:01:03+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

what's the status of your research? 

I did some research myself  and so far I've found offsets, sizes of packed and sizes of unpacked data blocks inside game0000.dat but still can't find filenames & directory structure  I suppose it should be something like EsoUI/Art/Achievements/achievements_points_legendary.dds

I also did some research on other dat/mnf files. They are a bit different/more complex, ie. another compression, more data0xxxx parts, etc. This time I've found sizes and offsets but no file parts ;/
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-16T10:40:24+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

Well trying make unpacker.

```
0x4 - szID (always MES2)
0x15 - unknown
0x4 - szFilesCount (endian BIG)
0x4 - szFilesCount (endian BIG)

0x4 - szBlockSize (endian BIG)
0x4 - szBlockZSize (endian BIG)
     [........Block........]

0x4 - szBlockSize (endian BIG)
0x4 - szBlockZSize (endian BIG)
     [........Block........]

0x4 - szBlockSize (endian BIG)
0x4 - szBlockZSize (endian BIG)
     [........Block........]
```


Blocks 1-2 unknown tables

```

0x4 - szFileSize
0x4 - szFileZSize
0x4 - szUnknown01
0x4 - szOffset
0x1 - szComType(0 - Not Compressed, 1 - Zlib, 2 - Snappy)
0x1 - szArchiveNum
0x2 - szUnknown02
```



I can not understand what's going on after func : sub_007522A0 (see attach) .. Seems func for generate sum (hash?) for file names. Passing 3 times with different paths: Example

```
EsoUI/PregameLocalization/LocalizePregameGeneratedStrings.lua

[2]
esoui/pregamelocalization/localizepregamegeneratedstrings.lua

[3]
/esoui/pregamelocalization/localizepregamegeneratedstrings.lua
```


I did a test project for gen sums, but output sums not found in the three tables.. Who will help deal? 
[MbHash.rar](https://xentaxbackup.github.io/file/6523_MbHash.rar)
## Post #7
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2013-07-16T19:01:47+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

thanks for file number hint - I was blind 

> 0x1 - szFlag (0 - Not Compressed, 1 - Compressed, 2 - Unknown (Compressed and Encrypted maybe))
I haven't tested it yet but imo 2 = compressed by snappy - [https://code.google.com/p/snappy/](https://code.google.com/p/snappy/)
I'm sure they use it becouse by using brute force attempt I was able to unpack a lot of files - textures, etc. (i.e. I've found over 400 ingame maps). It's also listed inside thirdparty.rtf file   

eso.mnf has extra data after 3rd zlibed block - do you know what's hidden there?
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-16T20:33:27+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

Currently I'm interested in file names.
## Post #9
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2013-07-16T22:59:16+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

I think that I have found "something" 
it's hidden inside files with ZOSFT header
inside that file you will find few zlib compressed blocks and then block of null-separated strings, i.e.

/esoui/app/app.txt 
/esoui/app/loadingscreen/loadingscreen.lua 
/esoui/app/loadingscreen/loadingscreen.xml 
/esoui/art/achievements/achievements_points_05.dds 
/esoui/art/achievements/achievements_points_10.dds 
/esoui/art/achievements/achievements_points_15.dds 
/esoui/art/achievements/achievements_points_50.dds 
/esoui/art/achievements/achievements_points_legendary.dds 
/esoui/art/actionbar/ability_keybindbg.dds 
/esoui/art/actionbar/ability_ultimate_framedecobg.dds 
...

how to link data from this file to mnf file is my next question/task ... but tomorrow 

hmm, there are more files then filenames
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-17T06:50:13+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

Hm i found only 1 ZOSFT in game0000.dat, in esoXXXX.dat not found also game0000.dat have only 2599 files, ZOSFT contain only 1574 records
## Post #11
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2013-07-17T07:38:42+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

same problem - not enough records 
I've found another ZOSFT file inside eso0002, offset 1394821 (my eso0002 size is 38006249)

5657125,2755862,2041805319,1394821,1,2,0 

but it has 50k records only and there are 200k+ files  :/

but maybe files without names are just obsolete junk?  it's beta but so many? :/
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-17T11:42:43+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

> Reply from Lord Vaako
>
> same problem - not enough records 
I've found another ZOSFT file inside eso0002, offset 1394821 (my eso0002 size is 38006249)

5657125,2755862,2041805319,1394821,1,2,0 

but it has 50k records only and there are 200k+ files  :/

but maybe files without names are just obsolete junk?  it's beta but so many? :/

60k...  Anyway need to find out for what used sums after Size and ZSize

```
0x4 - szUnknown01
```


btw : 3 ZOSFT ->

```
/animsfiletable.dat
/internalfiletable.dat
```
## Post #13
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2013-07-17T17:29:07+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

I had a tough day  so could you explain this? 

> btw : 3 ZOSFT ->
>
> Code: Select all/filetable.dat
>
> /animsfiletable.dat
>
> /internalfiletable.dat
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-17T17:53:03+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

> Reply from Lord Vaako
>
> I had a tough day  so could you explain this? 
btw : 3 ZOSFT ->
Code: Select all/filetable.dat
/animsfiletable.dat
/internalfiletable.dat
nvm
## Post #15
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2013-07-17T20:22:52+00:00
- Post Title: Researching of a .dat archive with a .mnf file.

I'm still trying to "link" mnf data and zosft data, so far no luck :/

i.e.

ZOSFT DATA: 04 00 00 00 69 00 00 00 E3 7E 19 4F 8E 72 19 6B
ZOSFT TEXT: /esoui/art/achievements/achievements_points_05.dds

MNF: 32896,6363,BBC31573,3310,1,0,0
## Post #16
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2013-07-18T18:26:10+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

have you found anything?
## Post #17
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-07-23T20:57:50+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Wow, I didn't know, that my topic has grown up  Anyway, I've found out all of this back in June. I have even linked data from zosft (Zenimax Online Studios File Table btw) file from game000.dat with some other files from game000.dat (~1500 files), but I still don't know, how to find other filenames. Also I don't know, how to find filenames of files from eso0xxx.dat, even with zosft file. I was too busy to research more at the last weeks, but I will try more in the future. Also look at zosft file - it contains a lot of zlibed blocks.
## Post #18
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2013-07-23T21:37:48+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

just an idea: maybe they use "human readable" filenames just for files used by lua scripts/interface/xml and "internal names/indexes" for other files?
## Post #19
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-07-24T06:11:30+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

> Reply from Lord Vaako
>
> just an idea: maybe they use "human readable" filenames just for files used by lua scripts/interface/xml and "internal names/indexes" for other files?
I don't think so. There is zosft file in eso0002.dat and it contains a lot of names of models and textures instead of scripts/xml.
## Post #20
- Username: kryptanon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 13, 2013 1:54 am
- Post datetime: 2013-08-12T20:00:37+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Ahh this thread seems dead   
I've been looking for weeks for someone smart enough to help me create a server emulation allowing the ability
to run ESO beta locally on a private server. I thought I was the only one pokin around in the dat files. IM NOT ALONE! 
Has anyone found anything related to server checks or anything? I would really like to get this up and running.
The issue I'm having is actually running the game ON the server. Your research as helped me so much! I wanna thank you for all your hard work guys
## Post #21
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-08-15T17:39:34+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

> Reply from kryptanon
>
> Ahh this thread seems dead   
I've been looking for weeks for someone smart enough to help me create a server emulation allowing the ability
to run ESO beta locally on a private server. I thought I was the only one pokin around in the dat files. IM NOT ALONE! 
Has anyone found anything related to server checks or anything? I would really like to get this up and running.
The issue I'm having is actually running the game ON the server. Your research as helped me so much! I wanna thank you for all your hard work guys
Well, I have unpacked encrypted launcher. Do you need it?
## Post #22
- Username: kryptanon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 13, 2013 1:54 am
- Post datetime: 2013-08-17T23:55:57+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Sure! I have eso.exe disassembled but not the launcher. Do you have any reverse-engineering experience or any coding experience? We could use some help if your interested!
## Post #23
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-08-19T11:06:17+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

I've been looking into this as well and have come to the same results: can't find the filenames. I have been manually extracting the files though, and even though I have enough coding experience to write an unpacker myself, I don't have the time lately. I noticed Ekey and perhaps others wrote one, so if anyone would be kind enough to post their unpacker here (source would be great too!) I would be really grateful. It would make doing research on this quite a lot easier ^^
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-19T18:23:12+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

> Reply from Lord Vaako
>
> I did some research myself  and so far I've found offsets, sizes of packed and sizes of unpacked data blocks inside game0000.dat but still can't find filenames & directory structure  I suppose it should be something like EsoUI/Art/Achievements/achievements_points_legendary.ddsMaybe I'm "off track" but this is what I found inside game0000.dat from offset 0x000E with aluigis comtype 1:

```
EsoUI\App\LoadingScreen\LoadingScreen.lua
EsoUI\App\LoadingScreen\LoadingScreen.xml
```


Succeeded by this data (lua-code?):

```

local SYSTEM_GRANULARITY = 100
local NUM_SYSTEMS = GetNumLoadingSubsystems()
local BAR_MAX = SYSTEM_GRANULARITY * NUM_SYSTEMS
local DEFAULT_TEXTURE = "EsoUI/Art/Screens/area_load.dds"

local g_loadStatus
local g_numSystemsRemaining = -1
local g_isReloadingUI

local TEXTURE_WIDTH = 1680
local TEXTURE_HEIGHT = 1050
local TEXTURE_ASPECT_RATIO = TEXTURE_WIDTH / TEXTURE_HEIGHT

local function SizeLoadingTexture()
[...]
function InitLoadScreen(self)
    LoadingScreenBar:SetMinMax(0, BAR_MAX)

    local r, g, b, a = GetInterfaceColor(INTERFACE_COLOR_TYPE_LOADING_SCREEN, LOADING_SCREEN_COLOR_BAR_START)
    local r1, g1, b1, a1 = GetInterfaceColor(INTERFACE_COLOR_TYPE_LOADING_SCREEN, LOADING_SCREEN_COLOR_BAR_END)
    LoadingScreenBar:SetGradientColors(r, g, b, a, r1, g1, b1, a1)
    
    EvtMgr:RegisterForEvent("LoadingScreen_AreaLoadStarted", EVENT_AREA_LOAD_STARTED, OnAreaLoadStarted)
    EvtMgr:RegisterForEvent("LoadingScreen_SizeLoadingTexture", EVENT_SCREEN_RESIZED, SizeLoadingTexture)
    EvtMgr:RegisterForEvent("LoadingScreen_OnReloadGui", EVENT_RELOAD_GUI, OnReloadGui)
    EvtMgr:RegisterForEvent("LoadingScreen_OnPrepareForJump", EVENT_PREPARE_FOR_JUMP, OnPrepareForJump)
    EvtMgr:RegisterForEvent("LoadingScreen_OnJumpFailed", EVENT_JUMP_FAILED, OnJumpFailed)

    local function OnSubsystemLoadComplete(eventCode, system)
        UpdateLoadingBar(system, 1.0)
        g_numSystemsRemaining = g_numSystemsRemaining - 1
        if g_numSystemsRemaining == 0 then
            OnLoadingCompleted()
        end
    end

    EvtMgr:RegisterForEvent("LoadingScreen_OnSubsystemLoadComplete", EVENT_SUBSYSTEM_LOAD_COMPLETE, OnSubsystemLoadComplete)

    SizeLoadingTexture()
end
```
## Post #25
- Username: kryptanon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 13, 2013 1:54 am
- Post datetime: 2013-08-19T18:32:07+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

> Reply from shakotay2
>
> Lord Vaako wrote:I did some research myself  and so far I've found offsets, sizes of packed and sizes of unpacked data blocks inside game0000.dat but still can't find filenames & directory structure  I suppose it should be something like EsoUI/Art/Achievements/achievements_points_legendary.ddsMaybe I'm "off track" but this is what I found inside game0000.dat from offset 0x000E with aluigis comtype 1:
Code: Select all; app UI files
EsoUI\App\LoadingScreen\LoadingScreen.lua
EsoUI\App\LoadingScreen\LoadingScreen.xml

Succeeded by this data (lua-code?):
Code: Select alllocal EvtMgr = GetEventManager()

local SYSTEM_GRANULARITY = 100
local NUM_SYSTEMS = GetNumLoadingSubsystems()
local BAR_MAX = SYSTEM_GRANULARITY * NUM_SYSTEMS
local DEFAULT_TEXTURE = "EsoUI/Art/Screens/area_load.dds"

local g_loadStatus
local g_numSystemsRemaining = -1
local g_isReloadingUI

local TEXTURE_WIDTH = 1680
local TEXTURE_HEIGHT = 1050
local TEXTURE_ASPECT_RATIO = TEXTURE_WIDTH / TEXTURE_HEIGHT

local function SizeLoadingTexture()
[...]
function InitLoadScreen(self)
    LoadingScreenBar:SetMinMax(0, BAR_MAX)

    local r, g, b, a = GetInterfaceColor(INTERFACE_COLOR_TYPE_LOADING_SCREEN, LOADING_SCREEN_COLOR_BAR_START)
    local r1, g1, b1, a1 = GetInterfaceColor(INTERFACE_COLOR_TYPE_LOADING_SCREEN, LOADING_SCREEN_COLOR_BAR_END)
    LoadingScreenBar:SetGradientColors(r, g, b, a, r1, g1, b1, a1)
    
    EvtMgr:RegisterForEvent("LoadingScreen_AreaLoadStarted", EVENT_AREA_LOAD_STARTED, OnAreaLoadStarted)
    EvtMgr:RegisterForEvent("LoadingScreen_SizeLoadingTexture", EVENT_SCREEN_RESIZED, SizeLoadingTexture)
    EvtMgr:RegisterForEvent("LoadingScreen_OnReloadGui", EVENT_RELOAD_GUI, OnReloadGui)
    EvtMgr:RegisterForEvent("LoadingScreen_OnPrepareForJump", EVENT_PREPARE_FOR_JUMP, OnPrepareForJump)
    EvtMgr:RegisterForEvent("LoadingScreen_OnJumpFailed", EVENT_JUMP_FAILED, OnJumpFailed)

    local function OnSubsystemLoadComplete(eventCode, system)
        UpdateLoadingBar(system, 1.0)
        g_numSystemsRemaining = g_numSystemsRemaining - 1
        if g_numSystemsRemaining == 0 then
            OnLoadingCompleted()
        end
    end

    EvtMgr:RegisterForEvent("LoadingScreen_OnSubsystemLoadComplete", EVENT_SUBSYSTEM_LOAD_COMPLETE, OnSubsystemLoadComplete)

    SizeLoadingTexture()
end


What did you use to unpack this?
## Post #26
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-08-19T18:41:30+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

> Reply from kryptanon
>
> Sure! I have eso.exe disassembled but not the launcher. Do you have any reverse-engineering experience or any coding experience? We could use some help if your interested!
[http://yadi.sk/d/4n_Ubuw085cTf](http://yadi.sk/d/4n_Ubuw085cTf) I have some coding experience (actually I have written almost working unpacker back in june), but don't have any reverse-engineering experience 

> Reply from kryptanon
>
> What did you use to unpack this?
It's just zlibed block from game0000.dat
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-19T18:46:56+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

quickbms

next file is

```
    <Controls>
        <TopLevelControl name="LoadingScreen" mouseEnabled="true" keyboardEnabled="true">
            <AnchorFill />
```


this is the bms:
set i long 1
comtype i

set NAME string "test.txt"
#clog NAME 0 ZSIZE SIZE
#set ZSIZE long 58
#set SIZE long 100
#clog NAME 0+14 ZSIZE SIZE

# lua file
#set ZSIZE long 1682
#set SIZE long 6984
#clog NAME 58+14 ZSIZE SIZE

# xml file
set ZSIZE long 1682
set SIZE long 6984
clog NAME 1740+14 ZSIZE SIZE

(I had the first 14 bytes cut from the original game0000.dat so you'll have to add them for clogs offset.)

edit: okay, too late...
## Post #28
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-08-19T18:50:18+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

```
EsoUI\App\LoadingScreen\LoadingScreen.lua
EsoUI\App\LoadingScreen\LoadingScreen.xml
```

It is file \esoui\app\app.txt

```

local SYSTEM_GRANULARITY = 100
local NUM_SYSTEMS = GetNumLoadingSubsystems()
local BAR_MAX = SYSTEM_GRANULARITY * NUM_SYSTEMS
local DEFAULT_TEXTURE = "EsoUI/Art/Screens/area_load.dds"

local g_loadStatus
local g_numSystemsRemaining = -1
local g_isReloadingUI

local TEXTURE_WIDTH = 1680
local TEXTURE_HEIGHT = 1050
local TEXTURE_ASPECT_RATIO = TEXTURE_WIDTH / TEXTURE_HEIGHT

local function SizeLoadingTexture()
[...]
function InitLoadScreen(self)
    LoadingScreenBar:SetMinMax(0, BAR_MAX)

    local r, g, b, a = GetInterfaceColor(INTERFACE_COLOR_TYPE_LOADING_SCREEN, LOADING_SCREEN_COLOR_BAR_START)
    local r1, g1, b1, a1 = GetInterfaceColor(INTERFACE_COLOR_TYPE_LOADING_SCREEN, LOADING_SCREEN_COLOR_BAR_END)
    LoadingScreenBar:SetGradientColors(r, g, b, a, r1, g1, b1, a1)
    
    EvtMgr:RegisterForEvent("LoadingScreen_AreaLoadStarted", EVENT_AREA_LOAD_STARTED, OnAreaLoadStarted)
    EvtMgr:RegisterForEvent("LoadingScreen_SizeLoadingTexture", EVENT_SCREEN_RESIZED, SizeLoadingTexture)
    EvtMgr:RegisterForEvent("LoadingScreen_OnReloadGui", EVENT_RELOAD_GUI, OnReloadGui)
    EvtMgr:RegisterForEvent("LoadingScreen_OnPrepareForJump", EVENT_PREPARE_FOR_JUMP, OnPrepareForJump)
    EvtMgr:RegisterForEvent("LoadingScreen_OnJumpFailed", EVENT_JUMP_FAILED, OnJumpFailed)

    local function OnSubsystemLoadComplete(eventCode, system)
        UpdateLoadingBar(system, 1.0)
        g_numSystemsRemaining = g_numSystemsRemaining - 1
        if g_numSystemsRemaining == 0 then
            OnLoadingCompleted()
        end
    end

    EvtMgr:RegisterForEvent("LoadingScreen_OnSubsystemLoadComplete", EVENT_SUBSYSTEM_LOAD_COMPLETE, OnSubsystemLoadComplete)

    SizeLoadingTexture()
end
```

And this one is \esoui\app\loadingscreen\loadingscreen.lua
## Post #29
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-08-19T19:05:07+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

[http://yadi.sk/d/k1X6Iieg85hVl](http://yadi.sk/d/k1X6Iieg85hVl) - unpacked game0000.dat (mostly with names)
## Post #30
- Username: kryptanon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 13, 2013 1:54 am
- Post datetime: 2013-08-19T19:18:37+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

You guys are awesome! You're really opening some doors on my research on building this thing!
I really thank you guys!


This may be a silly question. I'm no pro by any means but if I were to edit some of those .xml in game0000.dat how would I recompile that back into a .dat file? Is there any software that would do this for me?
## Post #31
- Username: Lugnut360
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 16, 2013 9:47 pm
- Post datetime: 2013-08-20T01:29:32+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Do you unpack the files from the .dat, then use a zlib decompression on them or do you somehow run zlib decompression on the entire eso0000.dat? 

I'm very new to computer programming/datamining and would appreciate any explanation of how you write the extraction script for this.

When I open up eso0000.dat in hex editor, I see:
Hex:           ASCII in parenthesis:
50 45 53 32 (PES2) 
01 00 00 00 (....) 
00 00 0E 00 (....)
00 00 78 9C (x..}) - zlib file header

I'm not sure how you write a BMS script from this. I assume something like:

idstring "PES2"
get UNK1
get FILES long
for i = 0 < FILES
getdstring NAME (????)
Not sure how to find OFFSET, ZSIZE, SIZE

Thanks TERAB1T for the unpacked file!
## Post #32
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-08-20T09:02:43+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

So does anyone know yet what's in the 21 unknown bytes at the beginning and the data after the 3rd zlib block of eso.mnf? Or what data the first two blocks contain? I'm pretty sure they'd have to at least keep references to the filetables there...
And I'm sure you have this already by now, but for those who don't, this QuickBMS script unpacks the 3 zlibbed blocks we know of from a *.mnf file:
*snip - you can find the script a few posts after this*
I would've used a loop but I'm planning to expand the script to get the data from the blocks too, that's why I always added the file number. 

EDIT -> Block 2 seems to contain data about the files as well: for every file just one field of 8 bytes, little endian. I have no idea what block 1 is.
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-20T09:46:14+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

The third block from MNF is the file table.

```
0x4 - szFileZSize
0x4 - szUnknown01
0x4 - szOffset
0x1 - szComType(0 - Not Compressed, 1 - Zlib, 2 - Snappy)
0x1 - szArchiveNum
0x2 - szUnknown02
```


Hash Function: Initialize hash by 0xA8396u

[http://rdf3x.googlecode.com/svn/trunk/i ... l/Hash.cpp](http://rdf3x.googlecode.com/svn/trunk/infra/util/Hash.cpp)
[http://rdf3x.googlecode.com/svn/trunk/i ... l/Hash.hpp](http://rdf3x.googlecode.com/svn/trunk/include/infra/util/Hash.hpp)
## Post #34
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-08-20T10:15:45+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Exactly, but it might not be linked with the filenames. What if block 1 or 2 (or the extra data after block 3) contains that link and block 3 just contains sizes and offsets?
## Post #35
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-20T10:18:04+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

In 3 block - 0x4 - szUnknown01 - it's seems filename hash (see my previous post)
## Post #36
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-08-20T12:51:58+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Yes, that will help a lot once we have found the complete list of filenames, but we still need to find that, right?

By the way, these are the 15 unknown bytes after the MES2 header:

```
FILENAME         [02 00] [XX] 00 00 00 00 [XX XX XX XX] 00 03 [00 00 00] 04 [XX XX XX XX]
eso.mnf:         [02 00] [D0] 00 00 00 00 [7B FB 4F 00] 00 03 [00 00 00] 04 [00 08 0C 01]
esoaudioen.mnf:  [02 00] [04] 00 00 00 00 [2B 09 1E 00] 00 03 [00 00 00] 04 [00 04 06 01]
game.mnf:        [02 00] [01] 00 00 00 00 [3A A2 00 00] 00 03 [00 00 00] 04 [00 00 10 19]

unknown1: This always has to be 2 for some reason. The files don't open otherwise.
num_dat_archives: number of DAT files
EOF_offset (little endian): After reading these 4 bytes, add EOF_offset to current offset to reach the end of the third block. This is EOF except for eso.mnf which has extra data.
unknown2 (big endian): This is 4120*(2^n)+1, with n ranging from 0 to 2. It seems n is also the number of the DAT archive containing the ZOSFT, but maybe this is just a coincidence.
```


EDIT -> I'm in the process of decompiling eso.exe. It's not going that well as expected but I fixed a few things in the description above.
## Post #37
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-10-04T09:31:58+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Bumping this topic.
About a month and a half has passed. I got stuck in the decompilation process.
Has anybody made any progress?

Here are my scripts so far. My code is a bit messy but then again, QuickBMS isn't that clean as a language.

eso_mnf_with_id.bms: extracts all files listed in the MNF file with a unique identification found in block 1.
eso_mnf_blocksonly.bms: extracts MNF zlibed blocks
eso_zosft_blocks.bms: extract ZOSFT zlibed blocks
eso_zosft_extract_names.bms: create a batch script to rename files extracted with eso_mnf_with_id.bms. The names aren't linked correctly, and I currently have no idea how I would fix that.

TERAB1T, it would be great if you could share how you linked the ZOSFT filenames to the files.
## Post #38
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-10-12T01:34:41+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

About game.mnf filenames:

There are three zlib-ed blocks in .mnf file. As you know, the last one contains filesizes, offsets etc (20 bytes for each file). And the second one contains indexes for some of filenames from zosft-file: 8 bytes for each file. Look at this screenshot:



If 'Unknown1 = 0' and 'Unknown3 = 128 (decimal)' index (Unknown0) will be valid.
And 'Unknown1 = 1' and 'Unknown3 = 128' is filetable (zosft).

Use valid indexes and link them with files at the end of filetable (after 9 zlibed blocks).

Also I figured out, that if you remove all the "00 00 00 00" parts from the first block in .mnf, you'll get unique ID for each file in archives (4 bytes for each file).
## Post #39
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-10-13T11:47:59+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Interesting - there are only 1768 valid indices in the MNF, although there are 1772 records in the ZOSFT file. It's not so hard to combine those indices with the ZOSFT without checking their validity though: they return in ZOSFT block 2.3 (that is, the third zlib block of the second big block, so it's the 6th zlib block), along with offsets for the corresponding filenames.
The indices are also unique in game.mnf, while they aren't in eso.mnf... quite strange indeed. I think that when combined with another number (which isn't necessary for game.mnf), they might be unique.

I had also found out that there are unique IDs for the files in the first MNF block (check the ZOSFT script in my previous post, it used them), and these IDs appear again in a few of the ZOSFT blocks, but they seem to be in the wrong order. The indices in block 2 seem to be the only link. I called that index file_number in my research notes which I made available here: [http://pastebin.com/rsgh1irr](http://pastebin.com/rsgh1irr)

I adapted my scripts so the filenames of game.zosft are correctly applied. 
eso_mnf_with_filenumber.bms: This extracts the files with file_number as filename. Some filetypes automatically receive the correct extension.
eso_zosft_extract_names_by_filenumber.bms: This creates a batch script to rename the files extracted with the previous script based on the names in the ZOSFT file.
## Post #40
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-11-24T09:00:06+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Hey guys, anyone succeeded at extracting the sounds ? eso0000.dat through eso0207.dat should contain sfx. And esoaudioen0000.dat through esoaudioen0003.dat got to be the container for the voices. 

I have attached a sample of the voice archive HERE. (1,09 gb) 
And also the esoaudioen.mnf, just in case. 

And the possible sfx HERE.

Anyone gets anything, let me know. Thanks!
## Post #41
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2013-11-27T19:16:26+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Extracting the audio is easy, you can do it with my QuickBMS scripts to extract everything using the MNF files. You'd better just extract all the archives in one go though, because the files the MNF file points to is divided over all of those DAT files.
Psst! If you know how to use Google, you can also find the soundtrack which I ripped and posted online some time ago...
## Post #42
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2014-01-09T15:33:40+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

I believe eso.mnf header has changed. Looking at this

> Reply from Droolie
>
>              unknown1  num_dat_archives       EOF_offset           dummy         unknown2
FILENAME         [02 00] [XX] 00 00 00 00 [XX XX XX XX] 00 03 [00 00 00] 04 [XX XX XX XX]
eso.mnf:         [02 00] [D0] 00 00 00 00 [7B FB 4F 00] 00 03 [00 00 00] 04 [00 08 0C 01]
esoaudioen.mnf:  [02 00] [04] 00 00 00 00 [2B 09 1E 00] 00 03 [00 00 00] 04 [00 04 06 01]
game.mnf:        [02 00] [01] 00 00 00 00 [3A A2 00 00] 00 03 [00 00 00] 04 [00 00 10 19]

I do not think bytes are in this order anymore. (there are extra bytes now and some are not all 00)
## Post #43
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2014-01-10T11:49:44+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

It seems that that unknown block of data at the end of eso.mnf you mentioned previously is now inserted after the first 22 bytes. I'll try and create a functioning bms script to compensate for this, but I'm a noob so ...
## Post #44
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2014-01-10T15:26:59+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

For the latest build things seem to have changed in eso.mnf. Block of dat that used to be after the third zlib block is now moved to 22nd byte. I modified Droolie's quickbms script to compensate for this change. I might have broken something else, but I did manage to extract a lot of DDS textures and gr2 models this way. WAVs seem to be broken (won't play in media players), but it might be something else.

There does not seem to be a ZOSFT file extracted with this script from eso*.dat files so I could not use the 2nd Droolie script to connect filenames with files. Any help is appreciated.
[eso_mnf_with_filenumber_stlj.zip](https://xentaxbackup.github.io/file/6914_eso_mnf_with_filenumber_stlj.zip)
## Post #45
- Username: fxfire
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 25, 2012 11:34 pm
- Post datetime: 2014-01-10T18:52:04+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Thanks for all the great work so far. Does anyone have a hint what type of packer/obfuscator was used for the current  stress test beta exo.exe ?
## Post #46
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2014-01-11T19:03:22+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

For whatever reason the quickbms script does not extract the zosft file from esodata files. I managed to find the file in eso0002.dat but it contains only a small portion of filenames (something like 30k as compared to over 250k present). It also seems that the quickbms script does not extract some additional files for whatever reason. I might be wrong though.
## Post #47
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2014-01-14T15:58:06+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

That bms script I posted several days ago will not properly unpack everything. Turns out it breaks when some of the empty archives are being called and eso0000.dat has files that are neither zlib nor snappy ( or something in the original bms script is not quite correct). Currently, I am skipping files that cause breaks in the script manually, but any help from the more experienced members would be welcome.
## Post #48
- Username: LennardF1989
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 31, 2010 7:54 am
- Post datetime: 2014-01-15T12:39:34+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Heya,

Never been active on this forum a lot, always lurking and messing around by myself. Let my extraction program run for a good half an hour yesterday , it would go through all archives, decompress the information, and check the header against a local file. I had to skip eso0000 and everything beyond eso0106, because there's stuff in there which I suspect is double compressed (so first Zlib then Snappy or other way around, because those files have multiple entries in the second block of the MNF with different "flags").

There aren't a lot of special files in there though: .xml, .lua, .dds, .gr2, some soundbanks, some audio files, a few custom files and thats about it.

Besides a single ZOSFT in all the scanned eso packages I also encountered a ANFT, which I suspect is some sort of internal filetable. Haven't been able to find another ZOSFT, but it could be its hidden away in side the packages I skipped.

However, as someone in this topic said before: It's not unlikely some files are only used interally.
## Post #49
- Username: LennardF1989
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 31, 2010 7:54 am
- Post datetime: 2014-01-15T18:08:22+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Attached is a rar with logs for all archives.

It's safe to say that Block 3 in the MNFs contains all entries into the DAT files as all bytes are consumed when going through them (except 8 bytes in archive 4 for some reason). The MNF for ESO also contains references to archive 0 which don't exist, so either its residual or it's used for whatever more is in the MNF (eg. the unknown block).

All archives beyond 203 are simply empty, they only have the first 14 bytes of the DAT header. However, the MNF contains over 50k entries into these files, so I guess the content is supposed to be there, but it's stripped/disabled for the beta.

Other than that, as said in my previous post, not a lot of interesting things going on in the files.

With these logs, you/I can check which files are in the ZOSFT to give them a name and which are most likely for internal use only.

EDIT: Logs.rar now also contains list of all filenames found in the ZOSFT, sorted by filename and extension. As you can see, a lot of the files you encounter in the other logs are not mentioned in the ZOSFT.
[logs.rar](https://xentaxbackup.github.io/file/6918_logs.rar)
## Post #50
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2014-01-16T12:38:08+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

I came to the same conclusions working with the bms scripts. There is one more thing I'd like to add though - file id is not unique. There are some files that have the same ID but are from diferent archives. So, for example, file with id 9 can be found in eso0000.dat and eso000x.dat and so on. I did not manage to find the correlation between archive_id, file_id and zosft so that I can determine which file from which archive is connected to which filename.
## Post #51
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-01-31T00:12:50+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

While follow this, it looks like ESO use a strong method to save their files.
## Post #52
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2014-02-06T13:20:52+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

After the latest update, it seems that as LennardF1989 said, eso0000.dat is compressed differently, or the MNF records are just wrong for that file. I haven't got the time to analyze it properly, so is anyone interested?

I'm currently using [this adapted script](http://pastebin.com/0h8mJz5f) to extract the audio and the ZOSFT only (since I'm only interested in those). You can easily adapt it (by using my older scripts) to extract all the files. It only extracts files in archives with 0 < archive number < 204. You can remove those restrictions to be able to extract files from MNFs other than eso.mnf.
## Post #53
- Username: LennardF1989
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 31, 2010 7:54 am
- Post datetime: 2014-02-07T19:44:22+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

I purposely waited for the next ESO weekend, because it seems it's not a mature format yet
## Post #54
- Username: Cagli
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 15, 2014 8:38 pm
- Post datetime: 2014-02-15T13:38:27+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

I've been lurking this post for a while, and I must say great work!
I'm only interested in the .dds files and have been succesfully getting plenty of those in the eso.mnf/eso00xxx.dat files.

But I don't seem to get the same result for the game.mnf one.
The topic started with the game.mnf file and shifted to the eso.mnf file.
Does anyone have a bms for the game.mnf one? I'm still pretty much a n00b when i comes to figuring it out.
I don't care about the file names, as long as the dds files are exported.
TERAB1T uploaded an exported one, but it seems to be missing a lot of files (perhaps due to not getting the right filenames)
Anyone that can help?
## Post #55
- Username: Ferugre
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 20, 2012 10:56 pm
- Post datetime: 2014-02-28T20:18:34+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

None of the QuickBMS scripts seem to work, they end up with xmalloc errors.  I think incorrect values are being used to extract files.  Anyone have working scripts still?
## Post #56
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2014-03-11T20:06:35+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Extracting main game archives is the first step but what about rev eng data/files inside? 
Was any of you able to find structure of any, non simple, files inside? 
There are maps (gfx & names), localized text (en/fr/de) containing quests data (titles, descriptions, objectives), lore books texts, npc names, items, names, etc. and even some ids, textures, sounds, ui scripts, etc.
But I'm still missing "connections" between those data - some kind of internal database, i.e. I know quest ids, names and descriptions but I'm missing quest level and category, or connection between quest and its objectives.
Or I'm not able to find connection between map gfx and map id - I know that for most of the zones its simple (just one map and gfx), but multi level zones (i.e the wailing prison) are the problem.

Have any of you found such kind of data?
## Post #57
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2014-03-15T17:20:20+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

None of that has been publicly reverse engineered. No one has yet delved into decrypting eso0000.dat and eso0001.dat, which contain a lot of files not in zosft files and are compressed with an unknown method (not zlib, not snappy). Looking at some websites out there I can see that probably noone reverese engineered the client and they are all sniffing packets or using in-game addons for data collection. I guess there is not enough interest by the pros to go deep into how zenimax encrypted their files.
## Post #58
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2014-03-17T10:47:22+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

I was snooping around eso0000 and offzip-ed it. Bunch of files with header 
```
fa fa eb eb
```
 or 
```
FB FB EC EC
```
 One of these have multiple zlibed blocks, while other seems to be and index of sorts. When I offzipped the one with zlib blocks I got thousands of new files. Some of them contain some strings and I believe this has something to do with map names and their IDs (possible map tiles?) and possible quest/NPC names (possible map locations?). I also found something strange which I am not able to decipher on my own yet. There are files that apparently have some sort of encrypted or compressed strings. From my crude analysis the files are composed of a header followed by the number of strings contained, followed by 8 byte (Id?), followed by 00, followed by str_length, followed by string, followed by 00.

Attached is one of those files. Does anyone recognize what this is compressed/encrypted with?
[000a4762.zip](https://xentaxbackup.github.io/file/7103_000a4762.zip)
## Post #59
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2014-03-21T01:12:28+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Shame, would be nice to see these models out.
## Post #60
- Username: Bungie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 19, 2014 3:09 am
- Post datetime: 2014-04-19T18:57:18+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

The Strings are encoded with somethink like Base64.

Here the first three links, decoded with Base64 and converted to hex.

```
047809043108273978044b496969391d64103d0f297b3f5d7a2f3e06480e480120035f01021820082a601055121a254405493040362f3f185e7662682224743d130c6f481b6c48010201064808475d234f
045d78636018050234674470471f471e5919076448123f241a6044474038115903043b443d07112e3c641f5c6040401e66611805581f3a386b

```
## Post #61
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-09-02T06:24:23+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

any updates on this?
## Post #62
- Username: Sparktank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 25, 2010 7:00 pm
- Post datetime: 2017-02-13T03:46:59+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

> Reply from Droolie
>
> After the latest update, it seems that as LennardF1989 said, eso0000.dat is compressed differently, or the MNF records are just wrong for that file. I haven't got the time to analyze it properly, so is anyone interested?

I'm currently using this adapted script to extract the audio and the ZOSFT only (since I'm only interested in those). You can easily adapt it (by using my older scripts) to extract all the files. It only extracts files in archives with 0 < archive number < 204. You can remove those restrictions to be able to extract files from MNFs other than eso.mnf.

Using the "updated script" for "audio only" to get wav's from the eso#####.dat files, I get WAV files with "junk" headers.

Googling the header takes me to a wiki for ESO where you can use a hex editor to change the first 64 bytes to make the WAV file playable in a media player.

[http://www.uesp.net/wiki/ESOMod:RIFF_File_Format](http://www.uesp.net/wiki/ESOMod:RIFF_File_Format)

I tried it on one of the largest files extracted using the updated BMS:
__409159448.26.65534.wav
Not sure which *.dat file that extract from.

But using the wiki to modify the header in HxD gives me a playable file.
Of wind sound effects.

SO that's a start at least 

My main question now:
Does anyone know of a way to batch process hex editing on all the extract WAV files?
Or even changing the BMS script to do that as it extracts?

From eso0000.dat -> eso0215.dat
It extracted over 7GB in over 25.5 thousand files.

I'd rather not sit here and do it manually for all the files. :s

EDIT:
It seems, only the first 60 bytes of the header are constant.
The next 4 bytes are random and create audible clipping/glitch noise if you replace only the first 60 bytes.

Replacing the first 64 bytes entirely with the 72 bytes indicated on the ESOMod wiki give a smooth playback without clipping/glitch.

It's not so much "search" and replace.
More like delete first 64 bytes, regardless, then insert new 72 bytes at start of file.

However, some WAV files produced include something about a playlist and do not play back properly if the header is changed as indicated in the ESOMod wiki.
## Post #63
- Username: jetaman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 07, 2017 1:39 am
- Post datetime: 2017-09-29T07:22:58+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Hey guys,
Is it possible to extract 3d models and animations from this game and import them in 3ds max?
Thanks
## Post #64
- Username: Sparktank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 25, 2010 7:00 pm
- Post datetime: 2018-03-20T17:33:14+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Any updates?

I can provide samples if needed (of latest game install).

Really hoping to get through to finding a sound file on the Dark Anchor, without using a youtube rip.
## Post #65
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2020-07-05T06:09:58+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

I found this
[https://www.esoui.com/downloads/info125 ... tData.html](https://www.esoui.com/downloads/info1258-EsoExtractData.html)
but somewhat I always get this error

Extra command parameter 'Elder' found!
Extra command parameter 'Scrolls' found!
Extra command parameter 'Online\game_mac\pubplayerclient\eso.app\Contents\Resourcesgame.mnf' found!
Invalid command line parameter received...aborting!
## Post #66
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-07-05T08:12:47+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Use "" around the path\whatever.mnf to prevent a pathname containing blanks being interpreted as separate parameters. As simple as this.
## Post #67
- Username: Sparktank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 25, 2010 7:00 pm
- Post datetime: 2020-07-05T15:56:09+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

The ESO tool extracts in .riff format without any names.
Converting the riff is easy.
But it'd be a lot better if we can get the names for all the files. 120GB of files without names just feels outdated.
## Post #68
- Username: IgnusT
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 10, 2022 9:34 am
- Post datetime: 2022-08-11T04:33:24+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

Sorry to resurrect a million year old thread, but I could use some help with something interesting I found while messing with the extracted ESO files.

Within the ESO gr2 model files, there's a set of properties that contain the full texture paths. So, for example, if you open 181235.gr2 you can see the following paths in the gr2 properties:

```
normalPath,C:\EsoGameData\EsoP4\Depot1039\client\Art\Fixture\Unique\ExteriorClutter\textures\UNI_EXC_NamiraStatue001_N.dds
detailPath,
diffuse2Path,
specularPath,C:\EsoGameData\EsoP4\Depot1039\client\Art\Fixture\Unique\ExteriorClutter\textures\uni_exc_namirastatue001_s.dds
tintmaskPath,

```


I was thinking that I might be able to generate the filehash in the mnf files using this information, but using the hash method and init value mentioned here [viewtopic.php?p=87434#p87434](https://forum.xentax.com/viewtopic.php?p=87434#p87434) hasn't led me anywhere, with any version of those filepaths, relative or otherwise.

If I can figure this out I can probably generate a table linking each mesh to each set of textures, or write an exporter that pulls the textures with the right filename, etc. 

If anyone has any ideas outside of brute force testing possible inputs to generate hashes, that'd help me a lot.
## Post #69
- Username: IgnusT
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 10, 2022 9:34 am
- Post datetime: 2022-08-17T21:42:46+00:00
- Post Title: Re: Researching of a .dat archive with a .mnf file.

An update on pairing gr2 filenames to their texture data, I've pulled what I believe is all of the filenames that are in the GR2 files. 

Link to file name exports: [https://drive.google.com/file/d/1DEjwPH ... sp=sharing](https://drive.google.com/file/d/1DEjwPH8cm9xXIexAFOueJh_3KtYcsdCc/view?usp=sharing)

filenames.txt contains a list of all the gr2 files and any texture paths I found within. 

fileset.txt contains all the paths stripped to the /art/ folder (when applicable) and lowercase, with no duplicate paths. Also includes texture names from the zosft files, giving us a total of 97241 texture names out of the 344851 textures that seem to exist.

Currently thinking that the rest of the texture names are probably packed up somewhere else, or only stored as references for meshes that can have multiple texture sets. 

Still looking for a way to properly pair the new texture names to their .mnf entries.
