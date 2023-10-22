## Post #1
- Username: drkevdog
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 24, 2008 8:25 am
- Post datetime: 2008-03-24T01:43:09+00:00
- Post Title: Help with Multiex Settings/Plugins?

Hello,

I paid the near million dollars    for this program and now I am frustrated because I cannot seem to get it to work. I am wanting to use it for F-22 TAW DAT file and I only get the error: "Zip failed to extract file from archive". I did follow all the activity on this board as TAW was being accepted and so I know you have the program. What are the settings and/or plugins to get Multiex to work on that DAT file?

Thanks
## Post #2
- Username: drkevdog
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 24, 2008 8:25 am
- Post datetime: 2008-03-24T14:31:19+00:00
- Post Title: Help with Multiex Settings/Plugins?

When I registered the program initially I recieved the keyed options. After I uninstalled and reinstalled the program (manually deleting the program files) The reinstall is listed as a registered version with no indication of the registration key additional functions being opened. Is that related?
Also on installing to Win98SE I have to "Ignore" 3 files in order to complete the install. Is that an issue?
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-24T19:33:37+00:00
- Post Title: Help with Multiex Settings/Plugins?

Yes, it remembers that you registered this version before, when you reinstall it. 

In any event, which files do you need to "ignore" when installing?
Also, please post the debug.log file (press CTRL-L) when multiex commander is running.
## Post #4
- Username: drkevdog
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 24, 2008 8:25 am
- Post datetime: 2008-03-25T02:20:09+00:00
- Post Title: Help with Multiex Settings/Plugins?

Mr. Mouse,

The 3 files are Oleaut32.dll, Stdole2.tlb and Olepro32.dll but I checked the system folder and they are all there and most likely not the problem.

MultiEx Commander - Debug Mode - Log File
-----------------------------------------
MC32, C:\PROGRAM FILES\MULTIEX COMMANDER
4.3.0
-----------------------------------------
3/24/08, 9:06:00 PM
9:06:00 PM- MEX Open MRF  9:06:00 PM
9:06:04 PM-  GetWebFile = 0
9:06:04 PM-  C:\PROGRAM FILES\MULTIEX COMMANDER\data\web.log
9:06:04 PM- WIKI Succesful download of WIKI Resources 
9:06:04 PM- WIKI Succesful download of WIKI Resources 
9:06:04 PM[!]- RPM Parse FileInfo error 
9:06:04 PM[!]- RPM Parse FileInfo error 
9:06:04 PM[!]- RPM Parse FileInfo error 
9:06:04 PM- RPM AddPlugins RPM at pluginmanager.dll for Beyond Good and Evil
9:06:04 PM- RPM AddPlugins RPM at pluginmanager.dll for Prince of Persia
9:06:04 PM- RPM AddPlugins RPM at pluginmanager.dll for Sid Meier's Pirates!
9:06:04 PM- RPM AddPlugins RPM at pluginmanager.dll for Rahly's Test Archive
9:06:04 PM- MexCom FindPlugins 
9:06:04 PM[i]- MexCom FindPlugins PGN at Sacrifice.dll for Sacrifice
9:06:04 PM[i]- PGN Register  Sacrifice.dll
9:06:04 PM[i]- PGN Connect  Sacrifice.archive
9:06:05 PM[i]- MexCom FindPlugins PGN at MXvsATVUnleashed.dll for MXvsATVUnleashed
9:06:05 PM[i]- PGN Register  MXvsATVUnleashed.dll
9:06:05 PM[i]- PGN Connect  MXvsATVUnleashed.archive
9:06:05 PM[i]- PGN Info  MX vs ATV Unleashed PAK format Extractor,V:1.7,T:2,I:1,VR:3,RT:0,C:1
9:06:05 PM[i]- MexCom FindPlugins PGN at Painkiller.dll for Painkiller
9:06:05 PM[i]- PGN Register  Painkiller.dll
9:06:05 PM[i]- PGN Connect  Painkiller.archive
9:06:05 PM[i]- PGN Info  Painkiller PAK Files Extractor,V:1.4,T:2,I:1,VR:5,RT:0,C:1
9:06:05 PM[i]- MexCom FindPlugins PGN at Survival.dll for Survival
9:06:05 PM[i]- PGN Register  Survival.dll
9:06:05 PM[i]- PGN Connect  Survival.archive
9:06:05 PM[i]- PGN Info  Survival IDX/PAK format Extractor,V:1.0,T:2,I:0,VR:3,RT:0,C:0
9:06:05 PM[i]- MexCom FindPlugins PGN at WWE.dll for WWE
9:06:05 PM[i]- PGN Register  WWE.dll
9:06:05 PM[i]- PGN Connect  WWE.archive
9:06:05 PM[i]- PGN Info  WWE Raw 2 FPK Files Extractor,V:1.0,T:2,I:1,VR:3,RT:0,C:0
9:06:05 PM[i]- MexCom FindPlugins PGN at Commodore_64_disk_files.dll for Commodore_64_disk_files
9:06:05 PM[i]- PGN Register  Commodore_64_disk_files.dll
9:06:05 PM[i]- PGN Connect  Commodore_64_disk_files.archive
9:06:05 PM[i]- PGN Info  Commodore 64 D64 disk format Extractor,V:1.0,T:2,I:0,VR:3,RT:0,C:0
9:06:05 PM[i]- MexCom FindPlugins PGN at Age_Of_Empires_3.dll for Age_Of_Empires_3
9:06:05 PM[i]- PGN Register  Age_Of_Empires_3.dll
9:06:05 PM[i]- PGN Connect  Age_Of_Empires_3.archive
9:06:05 PM[i]- PGN Info  Age of Empires 3 BAR Files Extractor,V:0.9,T:2,I:0,VR:3,RT:0,C:0
9:06:05 PM[i]- MexCom FindPlugins PGN at Snowy.dll for Snowy
9:06:05 PM[i]- PGN Register  Snowy.dll
9:06:05 PM[i]- PGN Connect  Snowy.archive
9:06:05 PM[i]- PGN Info  Snowy: Fish Frenzy ARF format Extractor,V:1.1,T:2,I:0,VR:3,RT:0,C:0
9:06:05 PM[i]- MexCom FindPlugins PGN at Rayman3.dll for Rayman3
9:06:05 PM[i]- PGN Register  Rayman3.dll
9:06:05 PM[i]- PGN Connect  Rayman3.archive
9:06:05 PM[i]- PGN Info  Rayman 3 CNT Files Extractor,V:1.4,T:2,I:0,VR:3,RT:0,C:0
9:06:05 PM[i]- MexCom FindPlugins PGN at TrainDriver2005.dll for TrainDriver2005
9:06:05 PM[i]- PGN Register  TrainDriver2005.dll
9:06:05 PM[i]- PGN Connect  TrainDriver2005.archive
9:06:05 PM[i]- PGN Info  Train Driver 2005 .JA Extractor by Rahly and Mr.Mouse,V:1.0,T:2,I:0,VR:3,RT:0,C:0
9:06:05 PM[i]- MEX Set language 
9:06:05 PM[i]-  - Main : Setting Variables 
9:06:05 PM[i]-  - Main : Preparing Datafile List Columns 
9:06:05 PM[i]-  - Main : Setting Additional Variables
9:06:05 PM[i]-  - Main : Loading SupportForm
9:06:05 PM[i]-  - Main : Setting FileFilter
9:06:06 PM[i]-  - Main : Enabling All
9:06:06 PM[i]-  - Main : Creating New Instance
9:06:06 PM[i]- Reinitializing MexCom  
9:06:06 PM[i]-  - Main : Showing Program
9:06:06 PM[i]-  - Main : BASS Init called.
9:06:06 PM[i]-  - Main : DevIL Init called.
9:06:14 PM[i]-  d:\Program Files\Did\TAW\Program
9:06:14 PM[i]-  d:\Program Files\Did\TAW\Program
9:06:14 PM[i]-   >>F11 d:\Program Files\Did\TAW\Program\
9:06:29 PM[i]- Accessing archive 
9:06:29 PM[i]- Archive process format  ZIP
9:06:29 PM[!]- ZIP Failed to extract file from archive 
9:06:34 PM[i]- Reinitializing MexCom  
9:07:01 PM[i]-  Main: Saving Options
9:07:01 PM[i]-  Main: Closing DebugMode and open forms...
MultiEx Commander - Debug Mode - End
-----------------------------------------
3/24/08, 9:07:01 PM

I recieved a bms script, from a Multiex friend, to run TAW and it (bms script) initially unzipped and sort of autoran a Multiex download request of some type but I could not get the request processed out of basic ignorance of its function. Now all my Zip files have changed file type icons and I can't seem to get the re-downloaded bms file to automatically unzip or do anything.
