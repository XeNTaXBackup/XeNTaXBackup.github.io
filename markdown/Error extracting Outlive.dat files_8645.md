## Post #1
- Username: porongo51
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 27, 2012 10:22 am
- Post datetime: 2012-03-27T02:40:33+00:00
- Post Title: Error extracting "Outlive.dat" files

Hello.

I got this error when I try to extract any file Outlive.dat (Degub.txt)

The error, in my view, is in the extraction directory (D:\D:\). Am I Wrong?
Thanks for help...

MultiEx Commander - Debug Mode - Log File
-----------------------------------------
mc32, C:\Arquivos de programas\MultiEx Commander
4.0.0
-----------------------------------------
26/3/2012, 02:34:54
02:34:54 - ]-WebUpdate: user selected :3
02:34:54 - 02:34:54- Main : Opening MRF file
02:34:54 - -Main : Mex_FindPlugins
02:34:54 - -Main : Mex_FindPlugins->Searching
02:34:54 - -Main : Mex_FindPlugins->PGN at C:\Arquivos de programas\MultiEx Commander\data\plugins\pak\painkiller.dll for painkiller
02:34:54 - -Main : Mex_FindPlugins->PGN at C:\Arquivos de programas\MultiEx Commander\data\plugins\wad\sacrifice.dll for sacrifice
02:34:54 - - Main : Loading 
02:34:54 - - Main : Creating Panels 
02:34:54 - - Main : Setting Variables 
02:34:54 - - Main : Preparing Datafile List Columns 
02:34:54 - - Main : Setting Additional Variables
02:34:54 - - Main : Loading SupportForm
02:34:54 - - Main : Setting FileFilter
02:34:54 - - Main : Enabling All
02:34:54 - - Main : Creating New Instance
02:34:54 - - Main : Showing Program
02:34:54 - - Main : BASS Init called.
02:34:54 - - Main : DevIL Init called.
02:34:55 - -Main : RunAnalysis Started
02:34:55 - - Main : RunAnalysisProcess: Format=MEX3
02:34:55 - Main : RunAnalysisProcess->Running Mex3 on C:\Arquivos de programas\MultiEx Commander\data\multiex.lst
02:34:55 - Main : RunAnalysisProcess: Starting ProcessListFileMEX3
02:34:55 - Main: ProcessListFile: Analyzing Content
02:34:55 - Main: ProcessListFile: MEX3 : Opening List File C:\Arquivos de programas\MultiEx Commander\data\multiex.lst
02:34:55 - Main: ProcessListFile: List File : Log Entries 114
02:34:59 - Main - Starting Extract
02:34:59 - StartExtract>>Extracting: D:\D:\
02:34:59 - StartExtract>>Assinging buffer of size: 716743
02:34:59 - !!!!Error encountered: Number, Descr: 0, 
02:35:00 - Main: Saving Options
02:35:00 - Main: Closing DebugMode and open forms...
MultiEx Commander - Debug Mode - End
-----------------------------------------
26/3/2012, 02:35:00
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-03-27T20:21:06+00:00
- Post Title: Error extracting "Outlive.dat" files

Ah, the old 4.0.0. that was released on June 28th 2004....

Wait a minute... 2004? That's like .. nearly 8 years ago. I wasn't even married back then! Well, almost though, September that year, but that's beside the point. 

In any event, yes, it would seem that the extraction process came across a file that had a name like " D:\"  or so. Could be that I fixed that the past 8 years. In new releases. I think so. I would definitely assume so. Yes. Most definitely. I think. Outlive.dat eh? Hm.
## Post #3
- Username: porongo51
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 27, 2012 10:22 am
- Post datetime: 2012-03-27T22:13:13+00:00
- Post Title: Error extracting "Outlive.dat" files

Hum... My program does not update... When I check for a new version, I got this error:

> Run-Time error 62:
>
> Input past end of file

I want to extract Outlive.dat because I'll try to make a mod from this game. =D

Thanks for help...
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-03-28T05:32:47+00:00
- Post Title: Error extracting "Outlive.dat" files

Your program does not update, because it is 8 years old and no longer supported. The latest version is 4.5.0. [http://multiex.xentax.com](http://multiex.xentax.com) 

I could open Outlive.dat and extract its contents with that version.
