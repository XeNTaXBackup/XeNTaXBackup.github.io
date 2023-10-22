## Post #1
- Username: Nederlin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 26, 2005 10:11 am
- Post datetime: 2005-07-26T02:25:20+00:00
- Post Title: Arx Fatalis PAK files not working.

Hi all,

MultiEx 4.1.0 is not working on Arx Fatalis PAK files.   

I installed the program, i restarted the computer and when try to open an Arx Fatalis PAK file i get:

```
Attempt to read string > 256 bytes

```

debug.log

```
-----------------------------------------
mc32, C:\Archivos de programa\MultiEx Commander
4.1.0
-----------------------------------------
26/07/2005, 4:43:57
4:43:57 - ]-WebUpdate: user selected :3
4:43:57 - 4:43:57- Main : Opening MRF file
4:43:57 - -Main : Mex_FindPlugins
4:43:57 - -Main : Mex_FindPlugins->Searching
4:43:57 - -Main : Mex_FindPlugins->PGN at C:\Archivos de programa\MultiEx Commander\data\plugins\wad\Sacrifice.dll for Sacrifice
4:43:57 - -Main : RunAnalysis->Registering attempt of C:\Archivos de programa\MultiEx Commander\data\plugins\wad\Sacrifice.dll
4:43:57 - -Main : RunAnalysis->Progid to connect to Sacrifice.archive
4:43:57 - Sacrifice WAD Files Extractor
4:43:57 - -Main : Mex_FindPlugins->PGN at C:\Archivos de programa\MultiEx Commander\data\plugins\pak\Painkiller.dll for Painkiller
4:43:57 - -Main : RunAnalysis->Registering attempt of C:\Archivos de programa\MultiEx Commander\data\plugins\pak\Painkiller.dll
4:43:57 - -Main : RunAnalysis->Progid to connect to Painkiller.archive
4:43:57 - Painkiller PAK Files Extractor
4:43:57 - - Main : PlugIn Called: Painkiller PAK Files Extractor version 1.4, type (2), importation(1), varsreturned(5), restypespec(0), cancreate(1)
4:43:57 - - Main : Loading 
4:43:57 - - Main : Creating Panels 
4:43:57 - - Main : Setting Variables 
4:43:57 - - Main : Preparing Datafile List Columns 
4:43:57 - - Main : Setting Additional Variables
4:43:57 - - Main : Loading SupportForm
4:43:57 - - Main : Setting FileFilter
4:43:57 - - Main : Enabling All
4:43:57 - - Main : Creating New Instance
4:43:57 - - Main : Showing Program
4:43:57 - - Main : BASS Init called.
4:43:57 - - Main : DevIL Init called.
4:44:02 - -Main : RunAnalysis Started
4:44:02 - - Main : RunAnalysisProcess: Format=MEX3
4:44:02 - Main : RunAnalysisProcess->Running Mex3 on C:\Archivos de programa\MultiEx Commander\data\multiex.lst
4:44:04 - !!!!Main : MultiEx 3 could not process!->8
4:44:05 - Main: Saving Options
4:44:05 - Main: Closing DebugMode and open forms...
MultiEx Commander - Debug Mode - End
-----------------------------------------
26/07/2005, 4:44:05

```

or this one in some other files:

```
Get called with invalid datatype

```

debug.log

```
-----------------------------------------
mc32, C:\Archivos de programa\MultiEx Commander
4.1.0
-----------------------------------------
26/07/2005, 4:48:06
4:48:06 - ]-WebUpdate: user selected :3
4:48:06 - 4:48:06- Main : Opening MRF file
4:48:06 - -Main : Mex_FindPlugins
4:48:06 - -Main : Mex_FindPlugins->Searching
4:48:06 - -Main : Mex_FindPlugins->PGN at C:\Archivos de programa\MultiEx Commander\data\plugins\wad\Sacrifice.dll for Sacrifice
4:48:06 - -Main : RunAnalysis->Registering attempt of C:\Archivos de programa\MultiEx Commander\data\plugins\wad\Sacrifice.dll
4:48:06 - -Main : RunAnalysis->Progid to connect to Sacrifice.archive
4:48:06 - Sacrifice WAD Files Extractor
4:48:06 - -Main : Mex_FindPlugins->PGN at C:\Archivos de programa\MultiEx Commander\data\plugins\pak\Painkiller.dll for Painkiller
4:48:06 - -Main : RunAnalysis->Registering attempt of C:\Archivos de programa\MultiEx Commander\data\plugins\pak\Painkiller.dll
4:48:06 - -Main : RunAnalysis->Progid to connect to Painkiller.archive
4:48:06 - Painkiller PAK Files Extractor
4:48:06 - - Main : PlugIn Called: Painkiller PAK Files Extractor version 1.4, type (2), importation(1), varsreturned(5), restypespec(0), cancreate(1)
4:48:07 - - Main : Loading 
4:48:07 - - Main : Creating Panels 
4:48:07 - - Main : Setting Variables 
4:48:07 - - Main : Preparing Datafile List Columns 
4:48:07 - - Main : Setting Additional Variables
4:48:07 - - Main : Loading SupportForm
4:48:07 - - Main : Setting FileFilter
4:48:07 - - Main : Enabling All
4:48:07 - - Main : Creating New Instance
4:48:07 - - Main : Showing Program
4:48:07 - - Main : BASS Init called.
4:48:07 - - Main : DevIL Init called.
4:48:09 - -Main : RunAnalysis Started
4:48:09 - - Main : RunAnalysisProcess: Format=MEX3
4:48:09 - Main : RunAnalysisProcess->Running Mex3 on C:\Archivos de programa\MultiEx Commander\data\multiex.lst
4:48:10 - !!!!Main : MultiEx 3 could not process!->8
4:48:11 - Main: Saving Options
4:48:11 - Main: Closing DebugMode and open forms...
MultiEx Commander - Debug Mode - End
-----------------------------------------
26/07/2005, 4:48:11

```


Then i click the OK button and another window sais:

```

```


And when i go to Tools -> View detected plugins i get this window:

```
Could not find file pluginmanager.dll

```

debug.log

```
-----------------------------------------
mc32, C:\Archivos de programa\MultiEx Commander
4.1.0
-----------------------------------------
26/07/2005, 4:49:21
4:49:21 - ]-WebUpdate: user selected :3
4:49:21 - 4:49:21- Main : Opening MRF file
4:49:21 - -Main : Mex_FindPlugins
4:49:21 - -Main : Mex_FindPlugins->Searching
4:49:21 - -Main : Mex_FindPlugins->PGN at C:\Archivos de programa\MultiEx Commander\data\plugins\wad\Sacrifice.dll for Sacrifice
4:49:21 - -Main : RunAnalysis->Registering attempt of C:\Archivos de programa\MultiEx Commander\data\plugins\wad\Sacrifice.dll
4:49:21 - -Main : RunAnalysis->Progid to connect to Sacrifice.archive
4:49:21 - Sacrifice WAD Files Extractor
4:49:21 - -Main : Mex_FindPlugins->PGN at C:\Archivos de programa\MultiEx Commander\data\plugins\pak\Painkiller.dll for Painkiller
4:49:21 - -Main : RunAnalysis->Registering attempt of C:\Archivos de programa\MultiEx Commander\data\plugins\pak\Painkiller.dll
4:49:21 - -Main : RunAnalysis->Progid to connect to Painkiller.archive
4:49:21 - Painkiller PAK Files Extractor
4:49:21 - - Main : PlugIn Called: Painkiller PAK Files Extractor version 1.4, type (2), importation(1), varsreturned(5), restypespec(0), cancreate(1)
4:49:21 - - Main : Loading 
4:49:21 - - Main : Creating Panels 
4:49:21 - - Main : Setting Variables 
4:49:21 - - Main : Preparing Datafile List Columns 
4:49:21 - - Main : Setting Additional Variables
4:49:21 - - Main : Loading SupportForm
4:49:21 - - Main : Setting FileFilter
4:49:21 - - Main : Enabling All
4:49:21 - - Main : Creating New Instance
4:49:21 - - Main : Showing Program
4:49:21 - - Main : BASS Init called.
4:49:21 - - Main : DevIL Init called.

```


Then MultiEx crash and exit.

Thats all.

Any ideas 

Windows XP SP2
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-26T07:16:31+00:00
- Post Title: Arx Fatalis PAK files not working.

Yes, 

1. The plugin-manager you will get in the next version (it's a bug in this version, don't use it, all will be fixed in the new version). 

2. It seems the Arx Fatalis PAK format is different from the one MultiEx Commander expects. Possibly there are more formats for the PAK extension. 

If possible, do you have PAK files that are small enough to email, or do you know if there's a demo that contains files that give this error? Alternatively, you might use FileCutter to extract the front and back part of the PAK file that gives you this error and attach it here. FileCutter can be found at the Request link in my sig.
## Post #3
- Username: Nederlin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 26, 2005 10:11 am
- Post datetime: 2005-07-26T16:27:15+00:00
- Post Title: Arx Fatalis PAK files not working.

Well, in Arx Fatalis there are 5 PAK files:

- data.pak (232MB)
- data2.pak (2,11MB)
- LOC.pak (204KB)
- SFX.pak (43MB)
- SPEECH.pak (334MB)
[LOC.zip](https://xentaxbackup.github.io/file/382_LOC.zip)
## Post #4
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-06-20T07:36:57+00:00
- Post Title: Arx Fatalis PAK files not working.

Found a tool called ArxPak here:
[http://arx-fatalis.ifrance.com/arxpack_511.htm](http://arx-fatalis.ifrance.com/arxpack_511.htm)
It might be of use. It can be used as an editor (you can even debug scripts with it) and it seems it can repack the modified files back into the PAK file.
I would have attached v0.5.0.8 here for your convenience (and backup purposes), but it seems that the max. attachment size is 256k.
BTW: To have 0.5.0.8, you need to grab the ZIP and the EXE. (The ZIP has the old version plus the DLLs, while the EXE is the v0.5.0.8 release.)
