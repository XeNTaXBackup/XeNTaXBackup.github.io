## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-14T11:11:56+00:00
- Post Title: What to do?

In options File Association the empty list.. Mr. Mouse how to correct this problem?
[scr.jpg](https://xentaxbackup.github.io/file/178_scr.jpg)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-14T11:43:34+00:00
- Post Title: What to do?

You already asked me this?  And I replied : what is your operating system, what is the configuration of your computer?
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-14T11:50:31+00:00
- Post Title: What to do?

> Reply from Mr.Mouse
>
> You already asked me this?  And I replied : what is your operating system, what is the configuration of your computer?

sorry

Windows XP SP 1
P4 2.8Mhz
1024MB RAM
128Mb Video
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-14T11:54:50+00:00
- Post Title: What to do?

Could you post the debug log here? CTRL+L in main window of MexCom.
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-14T11:56:01+00:00
- Post Title: What to do?

> Reply from Mr.Mouse
>
> Could you post the debug log here? CTRL+L in main window of MexCom.
Yes

MODMAIN: Initializing MC
INITMC: Loading Splash
INITMC: Getting mc32.exe path info
INITMC: Checking existence of MultiExDC
INITMC: MC_MRF = C:\Program Files\MultiEx Commander/data\config\mc.mrf
INITMC: Loading Connect Form
INITMC: Loading Options Form
INITMC: Getting Options 
INITMC: Checking Debug Mode
INITMC: Checking Online Start
.]-WebUpdate: user selected :3
.15:55:06- Main : Opening MRF file
INITMC: OpenMRF
INITMC: Mex_FindPlugins Starting
.-Main : Mex_FindPlugins
.-Main : Mex_FindPlugins->Searching
.-Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\wad\Sacrifice.dll for Sacrifice
.-Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\pak\Painkiller.dll for Painkiller
MAINMOD: Checking registry entry
MAINMOD: Loading Main Form
.- Main : Loading 
.- Main : Creating Panels 
.- Main : Setting Variables 
.- Main : Preparing Datafile List Columns 
.- Main : Setting Additional Variables
.- Main : Loading SupportForm
.- Main : Setting FileFilter
.- Main : Enabling All
.- Main : Creating New Instance
.- Main : Showing Program
.- Main : BASS Init called.
.- Main : DevIL Init called.
MAINMOD: Processing any command line pars
MAINMOD: Unloading Splash
.35603.Invalid key
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-14T12:03:40+00:00
- Post Title: What to do?

When do you get THIS log? Can you just start MultiEx Commander and press CTRL-L and copy the text you see exactly as shown? Or did you? Otherwise, please zip the mc32.exe file and attach it here!
## Post #7
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-14T12:12:10+00:00
- Post Title: What to do?

This log appears when I press Tools \File Association
[mc32.rar](https://xentaxbackup.github.io/file/179_mc32.rar)
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-14T12:15:50+00:00
- Post Title: What to do?

Your version is an old one (4.0.0.1) 

Please download the latest version first (4.1). 

[http://multiex.xentax.com](http://multiex.xentax.com)

Install it into a new directory, so you can always come back to the old one if you need it.
## Post #9
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-14T12:17:41+00:00
- Post Title: What to do?

> Reply from Mr.Mouse
>
> Your version is an old one (4.0.0.1) 

Please download the latest version first (4.1). 

http://multiex.xentax.com
I download 4.1.0 there too such problem
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-14T12:19:36+00:00
- Post Title: What to do?

Okay, but what is the log of the new version after you start MultiEx Commander?
## Post #11
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-14T12:20:54+00:00
- Post Title: What to do?

Lock this log

MultiEx Commander - Debug Mode - Log File
-----------------------------------------
mc32, C:\Program Files\MultiEx Commander
4.1.0
-----------------------------------------
14.04.2005, 16:18:40
16:18:40 - ]-WebUpdate: user selected :3
16:18:40 - 16:18:40- Main : Opening MRF file
16:18:40 - -Main : Mex_FindPlugins
16:18:40 - -Main : Mex_FindPlugins->Searching
16:18:40 - -Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\wad\Sacrifice.dll for Sacrifice
16:18:40 - -Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\wad\Sacrifice.dll
16:18:41 - -Main : RunAnalysis->Progid to connect to Sacrifice.archive
16:18:41 - Sacrifice WAD Files Extractor
16:18:41 - -Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\pak\Painkiller.dll for Painkiller
16:18:41 - -Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\pak\Painkiller.dll
16:18:41 - -Main : RunAnalysis->Progid to connect to Painkiller.archive
16:18:41 - Painkiller PAK Files Extractor
16:18:41 - - Main : PlugIn Called: Painkiller PAK Files Extractor version 1.4, type (2), importation(1), varsreturned(5), restypespec(0), cancreate(1)
16:18:42 - - Main : Loading 
16:18:42 - - Main : Creating Panels 
16:18:42 - - Main : Setting Variables 
16:18:42 - - Main : Preparing Datafile List Columns 
16:18:42 - - Main : Setting Additional Variables
16:18:42 - - Main : Loading SupportForm
16:18:42 - - Main : Setting FileFilter
16:18:42 - - Main : Enabling All
16:18:42 - - Main : Creating New Instance
16:18:42 - - Main : Showing Program
16:18:43 - - Main : BASS Init called.
16:18:43 - - Main : DevIL Init called.
.0.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-14T12:25:34+00:00
- Post Title: What to do?

Okay thanks, I will look into it when I have time. It may be that you have installed something that protects reading the windows registry. 

By the way, it's two hours later at your place then it is here!  (The Netherlands)
## Post #13
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-14T12:28:00+00:00
- Post Title: What to do?

> Reply from Mr.Mouse
>
> Okay thanks, I will look into it when I have time. It may be that you have installed something that protects reading the windows registry. 

By the way, it's two hours later at your place then it is here!  (The Netherlands)
  thx Mr.Mouse
## Post #14
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-14T12:37:51+00:00
- Post Title: What to do?

And what can protect windows?
