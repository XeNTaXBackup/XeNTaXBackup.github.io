## Post #1
- Username: Mortisanti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue May 31, 2016 2:35 pm
- Post datetime: 2018-09-19T05:39:52+00:00
- Post Title: ERROR: 7-Out of memory

MexCom was working for me just a few days ago. I recently installed some Windows Updates - I also recently decided to check out Cheat Engine and messed with the tutorial, I only mention this because I'm curious if MexCom corrupts itself if it knows CE exists on the PC - and now I'm getting an error on launch. I've uninstalled, deleted the install directory, and reinstalled; I've also tried running as admin and set the compatibility mode to Windows XP SP2 (among others) and it continues to throw the same error. I also noticed "RPM Parse FileInfo" errors after the "MEX Open MRF" line. What could be causing this issue?

System
Win7 Home Premium 64-bit SP1, 16GB RAM

Updates installed
[*]KB4457144
[*]KB3177467
[*]KB4457918 (Security/Quality Rollup for .NET Framework 3.5.1 - 4.7.2)

Log

```
INITMC: Loading Connect Form
[!]  GetWebFile = 0
[!]  C:\Program Files (x86)\MultiEx Commander\data\web.log
INITMC: Checking Online Start
[!]  GetWebFile = 0
[!]  C:\Program Files (x86)\MultiEx Commander\data\web.log
[!] Check for update  0 new plugins, 0 new formats overall, and  formats removed.
[!] Check for update  Executable is up to date.
MODMAIN: Initializing MC
INITMC: Loading Splash
[!] PGN Register  FileSignature.dll
[!] PGN Connect  FileSignature.clsFileSignature
[!]  1.0.0
INITMC: Checking existence of MultiExDC
INITMC: MC_MRF = C:\Program Files (x86)\MultiEx Commander\data\config\mc.mrf
INITMC: Loading Options Form
[!] MEX Load language:  C:\Program Files (x86)\MultiEx Commander\data\languages\English.txt
[!] MEX Open MRF  1:31:10 AM
INITMC: OpenMRF
[!] MEX Open MRF  
[!] RPM Parse FileInfo error 
[!] RPM Parse FileInfo error 
[!] RPM Parse FileInfo error 
[!] MexCom FindPlugins 
[!] MexCom FindPlugins PGN at Just_Cause.dll for Just_Cause
[!] PGN Register  Just_Cause.dll
[!] PGN Connect  Just_Cause.archive
[!] PGN Info  Just Cause .ARC and SARC Extractor,V:1.0,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at Snowy.dll for Snowy
[!] PGN Register  Snowy.dll
[!] PGN Connect  Snowy.archive
[!] PGN Info  Snowy: Fish Frenzy ARF format Extractor,V:1.1,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at Age_Of_Empires_3.dll for Age_Of_Empires_3
[!] PGN Register  Age_Of_Empires_3.dll
[!] PGN Connect  Age_Of_Empires_3.archive
[!] PGN Info  Age of Empires 3 BAR Files Extractor,V:0.9,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at Rayman3.dll for Rayman3
[!] PGN Register  Rayman3.dll
[!] PGN Connect  Rayman3.archive
[!] PGN Info  Rayman 3 CNT Files Extractor,V:1.4,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at Commodore_64_disk_files.dll for Commodore_64_disk_files
[!] PGN Register  Commodore_64_disk_files.dll
[!] PGN Connect  Commodore_64_disk_files.archive
[!] PGN Info  Commodore 64 D64 disk format Extractor,V:1.0,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at RobotWarsPSP.dll for RobotWarsPSP
[!] PGN Register  RobotWarsPSP.dll
[!] PGN Connect  RobotWarsPSP.archive
[!] PGN Info  Robot Wars *.DAT files (PSP),V:1.0,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at WWE.dll for WWE
[!] PGN Register  WWE.dll
[!] PGN Connect  WWE.archive
[!] PGN Info  WWE Raw 2 FPK Files Extractor,V:1.0,T:2,I:1,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at Survival.dll for Survival
[!] PGN Register  Survival.dll
[!] PGN Connect  Survival.archive
[!] PGN Info  Survival IDX/PAK format Extractor,V:1.0,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at TrainDriver2005.dll for TrainDriver2005
[!] PGN Register  TrainDriver2005.dll
[!] PGN Connect  TrainDriver2005.archive
[!] PGN Info  Train Driver 2005 .JA Extractor by Rahly and Mr.Mouse,V:1.0,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at MXvsATVUnleashed.dll for MXvsATVUnleashed
[!] PGN Register  MXvsATVUnleashed.dll
[!] PGN Connect  MXvsATVUnleashed.archive
[!] PGN Info  MX vs ATV Unleashed PAK format Extractor,V:1.7,T:2,I:1,VR:3,RT:0,C:1
[!] MexCom FindPlugins PGN at Painkiller.dll for Painkiller
[!] PGN Register  Painkiller.dll
[!] PGN Connect  Painkiller.archive
[!] PGN Info  Painkiller PAK Files Extractor,V:1.4,T:2,I:1,VR:5,RT:0,C:1
[!] MexCom FindPlugins PGN at PuzzleQuestPSP.dll for PuzzleQuestPSP
[!] PGN Register  PuzzleQuestPSP.dll
[!] PGN Connect  PuzzleQuestPSP.archive
[!] PGN Info  MexCom plugin for Puzzle Quest *.PAK files (PSP),V:1.0,T:2,I:0,VR:3,RT:0,C:0
[!] MexCom FindPlugins PGN at Sacrifice.dll for Sacrifice
[!] PGN Register  Sacrifice.dll
[!] PGN Connect  Sacrifice.archive
MAINMOD: Checking registry entry
MAINMOD: Loading Main Form
ERROR: 7-Out of memory

```
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2019-02-22T22:49:40+00:00
- Post Title: ERROR: 7-Out of memory

Very odd. Did you manage to get it working again?
