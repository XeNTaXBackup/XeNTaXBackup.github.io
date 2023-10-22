## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-29T08:31:14+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

For archival purposes I thought to upload by old (final) DOS version of MultiEx Commander and multiex.exe.

The installation files:


 mcsetup23r.zip
MultiEx Commander 2.3 DOS (373.58 KiB) Downloaded 110 times



Some source code:


 MexCom_DOS_Source_1997_1999.zip
Some old source code from a version of MultiEx Commander (OSGOD) plus some other stuff. (27.75 KiB) Downloaded 46 times




 MultiEx_DOS_SourceCode_2000.zip
Some old source code from a version of MultiEx plus some other stuff. (28.46 KiB) Downloaded 46 times


Screenshots: 
[viewtopic.php?f=22&t=3450&p=29057#p29057](http://forum.xentax.com/viewtopic.php?f=22&t=3450&p=29057#p29057)

MexScript v1 manual:
[viewtopic.php?f=22&t=3450&p=29055#p29055](http://forum.xentax.com/viewtopic.php?f=22&t=3450&p=29055#p29055)

Here's some text from the release:

```

MULTIEX COMMANDER INSTALLATION!!

For CORRECT Installation do the following:

1. Make sure you have these setup-files in a directory
(anywhere)

2. Make sure you do not have an Environment Path 
   (e.g. SET PATH=c:\windows;c:\bc5;c:\mc;...etc...etc)
   of more than 256 bytes. Unfortunately MULTIEX.EXE
   can't find its INI files otherwise. 

3. RUN SETUP.EXE and give a installation path, BUT:
   SETUP will create a MC directory, do NOT use "MC" in your
   installation path. (if you do, it won't work!)

->Now you are ready to install...

4. Most important as well is that you create a shortcut in Win98 
   to MC.BAT (or change the "properties" of mc.bat directly)
   that has at least 4 (4096KB) MB of Initial Environment Memory, and 
   4 MB Expanded Memory. To do that, go to Explorer, go to the MC directory,
   click on MC.BAT with your right mouse button, select "properties" and switch 
   to "Memory". 


->...and run!

```


MC.INI (automatically created)

```
ROOT=d:\mc\
MAINVIEWER=d:\mc\BREAD.EXE
FILEFILE=d:\mc\FILE.MKD
EXT=TXT -> d:\mc\TREAD.EXE
EXT=INI -> d:\mc\TREAD.EXE
EXT=DOC -> d:\mc\TREAD.EXE
EXT=WAV -> d:\mc\PLANY.EXE
EXT=SND -> d:\mc\PLANY.EXE
EXT=VOC -> d:\mc\PLANY.EXE
EXT=AU  -> d:\mc\PLANY.EXE
EXT=IFF -> d:\mc\PLANY.EXE
EXT=BMP -> d:\mc\PICTVIEW.EXE
EXT=PCX -> d:\mc\PICTVIEW.EXE
EXT=JPG -> d:\mc\PICTVIEW.EXE
EXT=GIF -> d:\mc\PICTVIEW.EXE
EXT=TGA -> d:\mc\PICTVIEW.EXE
EXT=TIF -> d:\mc\PICTVIEW.EXE

```


multiex.ini

```
MULTIEXDIR=d:\mc\

```


Example of mcdebug.txt (debug log of multiex.exe)

```
* Called Routine : Init MC
--------------------------
- debug --> Reading INI File: D:\MC\mc.ini
- debug --> Created Windows
- debug --> Opened selectlist/editorial: d:\mc\selected.mkd and d:\mc\editor.mct
-- debug -> Long: ''D:\MC\..'', Short:  ''D:\MC\..''
* Return (Init)
-- debug -> Long: ''D:\MC\CONFIG'', Short:  ''D:\MC\CONFIG''
-- debug -> Long: ''D:\MC\DOCS'', Short:  ''D:\MC\DOCS''
-- debug -> Long: ''D:\MC\BREAD.EXE'', Short:  ''D:\MC\BREAD.EXE''
-- debug -> Long: ''D:\MC\EDITOR.MCT'', Short:  ''D:\MC\EDITOR.MCT''
-- debug -> Long: ''D:\MC\FILE.MKD'', Short:  ''D:\MC\FILE.MKD''
-- debug -> Long: ''D:\MC\LFE.EXE'', Short:  ''D:\MC\LFE.EXE''
-- debug -> Long: ''D:\MC\MC.BAT'', Short:  ''D:\MC\MC.BAT''
-- debug -> Long: ''D:\MC\..'', Short:  ''D:\MC\..''
-- debug -> Long: ''D:\MC\CONFIG'', Short:  ''D:\MC\CONFIG''
-- debug -> Long: ''D:\MC\DOCS'', Short:  ''D:\MC\DOCS''
-- debug -> Long: ''D:\MC\CONFIG'', Short:  ''D:\MC\CONFIG''
-- debug -> Long: ''D:\MC\..'', Short:  ''D:\MC\..''
-- debug -> Long: ''D:\DOWNLO~1'', Short:  ''D:\DOWNLO~1''
-- debug -> Long: ''D:\MC'', Short:  ''D:\MC''
-- debug -> Long: ''D:\SAMSUN~1'', Short:  ''D:\SAMSUN~1''
-- debug -> Long: ''D:\WII'', Short:  ''D:\WII''
-- debug -> Long: ''D:\MYSAD.SAD'', Short:  ''D:\MYSAD.SAD''
ERROR: Unable Read File

```


Example INI file (in MexScript 1!): 100.INI

```

ID=NONE

EVENTS
PROMPTUSER
SET DUMMYL NUMBER 0
SET FILECNTL NUMBER 8
MULTIPLY FILECNTL VAR FILECNTL NUMBER 220
ADD FILECNTL NUMBER 5


LOOP
SavePos FILESTART
GetNullString 40 FILENAME
ADD FILESTART NUMBER 13
GoTo FILESTART
GetLong FILESIZE
ExtractFILE ONE
ENDLOOP EXTRCNT FILECNTL

```


LIB.INI

```
;LIB Files

ID=EALIB

EVENTS
PROMPTUSER
GetInt FILECNTL
SavePos FILESTART

LOOP
GoTo FILESTART
GetString 12 FILENAME
GetInt DUMMYL
GetLong FILEOFF
ADD FILEOFF NUMBER 5
SavePos FILESTART
SavePos DUMMYL
ADD DUMMYL NUMBER 12
GoTo DUMMYL
GetInt DUMMYL
GetLong FILESIZE

SUBST FILESIZE VAR FILEOFF
ExtractFILE ONE
ENDLOOP EXTRCNT FILECNTL
```


docs\error.txt

```

#define ErrorInMainINI 1
#define ErrorInExINI   2
#define OpenMainINI    3
#define OpenExINI      4
#define OpenDatFile    5
#define IllegalFormat  6
#define NoDATFile      7
#define UnableListFile 8
#define UnableCreateEx 9
#define IllegalSwitch  10
#define ErrorInWriting 11
#define ImpFileNotExis 12
#define FIleNotFound   13
#define NotEnoughFree  14
#define EndOfFile      15
#define NoPathVar      16
#define UnableFindFID  17
#define IllegalFOff    18
#define NoSepHeader    19
#define NormalExit     99

```


docs/whatsnew.txt

```
-------------------------------

*During 1998-1999 a lot changed

*April 28, 1999
---------------
I added a sorting routine for the files in the directory.
A rather quick one it is. Sadly, it had only a limited capacity.
(Between 2000-8000, depending on the amount of available mem)
Hey, who wants more than 4000 files in a directory anyway!

*April 29, 1999
---------------
That sorting routine turned out to be low capacity (not even 250 files).
This was because MC.EXE used a small memory scheme. I rebuild it with a 
large one. Now it should do the trick quite nicely. Whenever there are
to many files to sort in memory, the files will be left unsorted.
I am NOT going to write a routine which does it IN FILE, because that would
slow things down too much, and is very boring to code too.;-)

*May 2, 1999
------------

Added the MultiEx command FlipLong which reverses the byte order in a long.
This was necessary to support formats like Thunder Hawk(view the INI).

*May-Juli 1999
--------------
V1.9 of Multiex now uses much less memory space than before, due to more
logical use of it. I completed Multiex Commander more or less. It should work
on any computer now using the SETUP.EXE I wrote for it. 
But WINDOWS is giving me trouble with running MC correctly... A memory problem, 
but MC works fine in full DOS mode. Why bother with DOS? I haven't got any
Windows-Builder for C... But hey, MC works fine, fuck windslow anyhow.
When you look at the speed of the "graphical amusements" in MC, when running
during windows, they are sloooooow. Sorry for that. In DOS they're fine.

*August	1999
------------

Rewrote MC. It now supports long filenames, and asks to create paths, 
if none exist. This makes it fully Windows compatible, 
but less DOS. Also added some effect (timer interrupt) for fun. 
Oh and it is possible to select all files at once. And limitless too.
MultiEx also uses long filenames now. But it does not create paths. 

Removed a stupid bug in the SADCom datafile format which you can create with 
MC. It created a header allright, but calculated a wrong size, so the offsets 
of the individual files were wrong. DUH!

Added two commands for MEX to be programmed: 
-GetDString (Get a string of variable lenght):
 GetDString <VAR> FILENAME
-SeperateHeader <EXTENSION>
 SepearteHeader CNT
 (for example!)
Because Hidden and Dangerous uses the DTA files as the main file, 
but the file info (offsets, sizes and names) are in the *.CNT header files.
Like H&D.CNT (the header) and H&D.DTA (the datafile)

V2.0 of MultiEx now complete. 
I added another command for MultiEx to use: 
-StrCReplace FILENAME <char1> <char2> (in numbers)
This replaces all char1 found in FILENAME to char2
It was necessary in order for PAK files, where the dirstructure is saved 
as duh/troep/ah.wav instead of usable (in DOS/WIN) duh\troep\ah.wav.
Oh and I added the "Create ALL Dirs" function in MC. 
So whenever MC encounters a dir that does not exist, it will ask to create
it and you can now answer "ALL". Saves a lot of hassle, don't you think?

9th of Nov 1999
---------------

DAMN!!!!!! MY HARD DRIVE FUCKED UP!!!!! ALL LATEST SOURCE CODE IS GONE!!!!!!!
DAAAAAAAAAMMMNNNNNNNNNNN!!!!!!!!!!!!!!!
AAAAAARGGHHHHHHHH!

9th of Feb 2000
---------------
So, I am not going to rewrite all of MC. This also means that the bugs that are in there, are in there forgood. I'll just add more and more formats for MC to support. 
That's it. No more coding on MC. Perhaps in the future I will do a totally new Windows-based Multiex. Anyone care to cooperate?

10th of June 2000
-----------------

I added a little prog that handles extensions that are alike between different formats. 
No no-one has to rename files. Whenever people try to open Quake's pak files, they will be
given a choice between the different PAK formats (e.g. Dune 2, Quake etc. and Daikatana)


15th of June 2000
-----------------

I added	TREAD.EXE BREAD.EXE and created a new, fully automatic SETUP.EXE
Also, I saw that the MEX-command CASE had not been added in MultiEx.DOC
Read it to see what it does, and read the README.1ST in the MC dir for more on the
new release. 

17th of June 2000
-----------------

Removed a bug in TREAD and made MULTIAD use path strings of 256. 

10th of December 2000
---------------------

Work has started on a Win32 version. A new XeNTaX member "Mage" has taken up the workload.

5th of February 2001
--------------------

Rebuild the MultiEx website. 
Added more games. 


6th of February 2001
--------------------

I added the program from Bill Neisius (bill@solaria.hac.com) called PLANY.EXE to play
.AU.VOC.SND.IFF and .WAV files, using the Soundblaster variable. Now when the user extracts any of these, 
he will be able to hear them from within the MultiEx Commander shell. 


23rd of February 2001
---------------------
I added more games. 

I added the program from Jan Patera called PICTVIEW which MultiEx Commander will call whenever you set the cursor on a picture file. Then it will show you that picture. 
Some info about PICTVIEW:
Author  : Jan Patera, Czech Republic
Internet: support@pictview.com, patera@km1.fjfi.cvut.cz
http://www.pictview.com
http://pascal.fjfi.cvut.cz/~patera/pictview
http://www.geocities.com/SiliconValley/Pines/9994

Picture files it supports (their extensions):
[BMI] [BMP] [DIB] [RLE] [CAL] [MIL] [CDR] [CDT] [PAT] [CEL CMX] [CUT]
[DCX] [GIF] [ICN] [CUR] [ICO] [IFF/LBM/HAM] [IMG-Soft. set] [IMG-GEM]
[IMG-Vivid] [JMX] [JIF] [JPE] [JPG] [MAC] [MSP] [OFX] [PAN] [PBM]
[PGM] [PPM] [PNM] [PC2] [PCD] [PCT] [PCX] [PIC-PC Paint] [PIC-Dr.Halo]
[PNG] [PSD] [PYX] [QFX] [RAS] [RLE-Intergraph] [RLE-Utah RLE] [SAM]
[SCx] [SGI] [BW] [RGB] [RLE] [TGA] [TIFF] [SEP] [CPT] [ST UDI] [WPG]
[ZBR] 

Great program ! :) Full credits to Jan!
```


docs/latest.txt

```
--------------------------------

Entry Date: 23rd of February 2001
--------------------------------
- Blood 1 (RFF)
- Blood 2 (REZ) - RIFF WAV Sound extraction
- Call To Power 2 (ZFS) -> it works, but a bit buggy
- No One Lives Forever - RIFF WAV sound extraction  (REZ)
- Outlaws (LAB) 
- Suddenstrike (RUS) sound file


Entry Date: 5th of February 2001
--------------------------------

- Colin McRae Rally 2 (BFL)
- Cultures (LIB)
- Escape From Monkey Island (M4B)
- Heroes Chronicles - Clash of The Dragons (SND)
- Heroes Chronicles - Clash of The Dragons (LOD)
- Hitman (BIN)
- Micro Machines 2 (SFX)


Entry Date: 10th of December 2000
---------------------------------

- Blair Witch Project (POD)
- Dark Reign 2 (ZWP)
- Delta Force: Land Warrior (PFF)
- Delta Force: Land Warrior (PWF) <-- these you extract from PFF files
- FIFA 2001 (BIG)
- Nascar Heat (RES)


Entry date: 15th of June 2000

- Final Fantasy (LGP)

Entry date: 3rd of June 2000
----------------------------
- Betrayal at Krondor (001)
- Conflict (Descent): Freespace (VP)
- Daikatana (PAK)
- Planescape: Torment (BIF)


Entry date: 20th of May 2000
----------------------------
- Counter-Strike (HALF LIFE MOD)  (*.PAK)
- Counter-Strike (HALF LIFE MOD)  (*.WAD) 
- Lemmings Revolution huge file (*.BOX)
- StarLancer (.HOG) files. 
- Total Annihilation (*.ZRB). Just extracting packed files.
 

Entry date: 20th of Feb 2000
----------------------------
- Abomination: The Nemesis Project Sounds (.AWF) 
- Abomination: The Nemesis Project Files  (.CLT) 
- Close Combat 4 (.AZP)
- Close Combat 4 Pictures (.PIX) 
- Close Combat 4 (.SFX) 
- FIFA 2000 .BIG files. (sfx, in .bnk format)
- Master of Magic LBX files (Thanks again Roger!)
- Master of Orion 1 LBX files
- Sim Theme Park Sound data (.SDT files) (MP2 format)
- Sim Theme Park WAD files (though im not sure!) 

 
Entry date: 9th of Feb 2000
---------------------------
- Age of Empires 2 .DRS files
- Homeworld VCE file
- Mortyr .HAL files

```


docs/addons.txt

```
==============================

Info about some datafiles
-------------------------

;Format for Blood 1 RFF files 
; sounds in sound.rff are 8 bit mono 11025 hz and unsigned



Now following are add-ons, formats I figured out but haven't got round to 
implement in MEX, either because of lack of time or because 
it is a kind of format MEX-functions can't support yet.
Er, some have been implemented... So these notes are just info.


Quake3 PAK Format:
------------------

These are actually PKZIP files. Rename them into .zip and
use WinZip or something to open them.


Thief 2 .CRF Format:
--------------------

As with Quake 3:

These are actually PKZIP files. Rename them into .zip and
use WinZip or something to open them.


--------------------------
pak format Jack Orlando :

header:

begin
-start of data

further
-offset
-size
-filename [13]

until start found --> number of files found --> start extract

----------------------------

wd format earth2140

-first filenumb(long)
then :
-offset file a (long)
-3 unknown longs
-offset file b (long) etc...

file a size: offset file b - offset file a

after this come nullterminated filenames (filenumb times)
then extraction can begin.

-----------------------------
Theme Hospital 
(sound file .dat)

Here: go to back of file, get the long there which points to the end of the tail, 
then get some dummy longs until you get a good one which should direct you 
towards the Start of the TAIL. There you should get some longs until you get a 
long which is the FILECNT. Get a dummy int and start getting the filename
(about 16 chars), the fileoffset and the filesize.
There's a catch however, ignore the NULL.WAVs they are excluded by the
FILECNT as well. Or you could just use the ME2.INI which uses the RIFFlenghts
to extract the files, until end of file.
----------------------------- 

HEROES of might and magic 2 (3?)
(heroes.agg)

FILECNT (int)

unknown     (int)  --}
FILE OFFSET (long)   |
FILE SIZE   (long)   |  FILECNT TIMES
FILE SIZE   (long) --}

then after you know the LAST offset + size, the FILENAMES come, 12 long, 
byte 13 a null and an unknown int, totalling it 15. FILECNT times.

-----------------------------

Hidden and Dangerous

These .DTA files have a spearate file-header: *.CTL files. 
Ya get some ID stuff in these files, then:

-Long 	: The offset in the DTA file
-Long 	: The size of the file
-Int    : string length
-String : The name of the file (including dirs)
          Actually, dirs come first, then the files.
          Dirs are in capitals. The strings do not have a fixed size,
          it depends on the their name. The int that come before them
          gives away their size.
------------------------------

```
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2009-04-29T16:29:00+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

Cool. Are you going to archive other old versions of MexCom as well?
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-29T17:29:59+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

docs/BUGS!.txt

```
-----------------------------------------------

- Environment Path (e.g. SET PATH=c:\windows;c:\bc5;c:\mc;...etc...etc...)
  may NOT be longer than 256 bytes. Or else multiex.exe can't find the ini file(s)
  it needs to function correctly. This bug may be stupid, yes, but at the moment 
  there's nothing I can do about it. Sorry. But hey, if you just work with Win98
  anyhow, you run setup from Explorer, and you put a default shortcut to MC.BAT somewhere,    with a small path, then who cares, it will work fine. 

- The setup routine may be faulty when no install path is given by user

- At a filename lenght of exactly 38 the routine that handles the printing of the correct   path at the top of the screen fucks ups and crashed the program. No idea why.


- users MUST enter a "open" path when extracting:
  e.g. : d:\temp\data  --> wrong! error!
  MUST : d:\temp\data\ --> extracts fine

- also, a path must have a valid name, no strange characters or else error!

- when such an error occurs, the extraction progress window is NOT closed...@#$@#!

- whenever you'd enter the windows dir, and try to set the cursor on win386
  boom! multiex system error message! (you hear your a: drive make noise too!)

- On some computers the whole DRIVE selection (with ALT-1/ALT-2) fucks up
  I have yet no idea why.

- People MUST provide the NOFILENAMES command in the INI script when there are no filenames 
  in a data file, because MEX does not check whether it has gotten a filename when it
  starts to extract. This causes string errors.

- it is not yet possible to try and see if a format fits your new game without MC exiting    when it fails. 

- not really a bug but PLANY (the sound player) will only work with soundblaster compatible

```


docs/supported.txt

```
------------------------------------

Latest entry : 22nd of February 2001

*The table below shows you what the file extension is of the
 datafile of your interest.  

Program                                     Extension           
*SadCom DAT Files (create with MC)	    SAD			

Abomination: The Nemesis Project            AWF                 
Abomination: The Nemesis Project            CLT                 
Actua Soccer 1 audio files  		    MAD
Actua Soccer 2 audio files		    MAD
Actua Soccer 3 audio files                  MAD                 
Age of Empires 2			    DRS			
Apache LongBow Files                        BLK                 
Ascendancy Files                            COB                 
Baldur's Gate				    BIF			
Betrayal at Krondor			    001                 
Blair Witch Project			    POD
Blood 1					    RFF
Blood 2					    REZ
Call To Power 2				    ZFS
Close Combat 4				    AZP			
Close Combat 4				    PIX			
Close Combat 4 Sound			    SFX			
Colin McRae Rally 2 (sound files)	    BFL
Conflict (Descent): Freespace		    VP                  
Counter-Strike (HALF LIFE MOD) 		    PAK			
Counter-Strike (HALF LIFE MOD)	            WAD			
Crusader, No remorse FLX files              FLX                 
Cultures				    LIB
Daikatana				    PAK                 
Dark Reign 2				    ZWP
Delta Force: Land Warrior		    PFF
Delta Force: Land Warrior		    PWF
Descent 3				    HOG			
Destruction Derby SOUND files               BIN                 
Doom 1                                      WAD                 
Doom 2 					    WAD
Duke Nukem 3D                               GRP                 
Duke Nukem 3D                               RTS                 
Dune 2 *.PAK files                          PAK                 
Empire 2, DIGSND.DAT                        DAT                 
Escape From Monkey Island		    M4B
FIFA 2000 				    BIG			
FIFA 2001				    BIG
Final Fantasy series			    LGP	
Half Life 				    PAK			
Half Life 				    WAD			
Heretic 1                                   WAD                 
Heroes of might and magic 1 (heroes.agg)    AGG                 
Heroes of might and magic 3                 LOD                 
Heroes of might and magic 3 sound file      SND                 
Heroes Chronicles Clash of the Dragons      LOD                 
Heroes Chronicles Clash of the Dragons      SND                 
Hexen 1                                     WAD                 
Hidden and Dangerous			    DTA  		
Hitman (sound files)			    BIN
Homeworld				    VCE			
Imperialism II RSR Files                    RSR                 
Kingdom O Magic                             DAT                 
Lemmings Revolution			    BOX			
Master of Magic 			    LBX			
Master of Orion Files                       LBX                 
Master of Orion 2 Files                     LBX                 
Micro Machines 2			    SFX
Mortyr					    HAL	
Nascar Heat 				    RES
No One Lives Forever (RIFF EXTRACTION)      REZ
Outlaws					    LAB
Planescape: Torment            		    BIF                 
Populous 3				    SDT			
Quake 1                                     PAK                 
Quake 2 				    PAK
Rage Of Mages 2 RES filez		    RES			
Shadow Warrior                              GRP                 
Shadow Warrior                              RTS                 
Sim Theme Park Sound Files                  SDT                 
StarLancer				    HOG			
Star Trek: BOTF				    SND			
Suddenstrike 				    RUS
Terminator Future Shock BSA files           BSA                 
Theme Hospital Sound (sound-0.DAT)          DAT                 
Thunder Hawk, *.WAD Filez                   WAD                 
Tomb Raider 3 Sound File (main.sfx)         SFX                 
Tomb Raider 3 WAD (cdaudio.wad)             WAD                 
Total Annihilation (just packed files)      ZRB			
Transport Tycoon Deluxe; extract RIFFs!     CAT                 
Twilight CD Bundled RAR filez	 	    001			
Unknown (I can't remember)                  DAT                 
US Navy Fighters		 	    LIB			
WarCraft 2 Files                            SUD                 
WarCraft 2 Sound Files (including briefs)   WAR                 
Worms 1 SFX files                           SFX                 


Total number of programs: 80+
```
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-29T17:31:48+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

docs/multiex.doc (manual for multiex.exe and MexScript)

```

                     M U L T I E X   V 1 . 8 0
                               b y  
                   X e N T a X / S A D C O M  L t d.

                      coded by MrMouse 1998 

   ---------------------------------------------------------------------
			CONTENTS:
	
			1.  Introduction
			2.  How to create an INI file
			2.1 COMMANDS FOR INIFILE
			2.2 VARIABLES FOR INIFILE
			2.3 MULTIEX ERRORS
			2.4 EXAMPLE OF 3.1
			3.  Command line pars
 			4.  Additional remarks
			5.  Supported FORMATS
   ---------------------------------------------------------------------










		        1. Introduction
			---=========---

-First of all, what is MULTIEX?

It is a tool for anyone of you wanting to extract from and import files
into socalled datafiles, which come with numerous of programs...
You all will remember for instance that DOOM had *.WAD files, in which
all data was contained. And take a look at Quake2 for example, this
game has the *.PAK files in which all data is contained.

-What can you do with MULTIEX?

With MULTIEX you can extract/import files from practicaly any datafile,
providing you create your own INI-file for the format.
MULTIEX reads preset formatfiles (see for example PAK.INI and WAD.INI in
the config directory), and then is readily able to extract files from
it. In other words, YOU tell MULTIEX what the format of the datafile of
interest is like and save it in a INI-format.
After that is done, you are ready to extract and import files!
(BUT ONLY IMPORT WHEN THE FILENAMES IN THE DATAFILE ARE NO LONGER
THAN 8 BYTES, EXCLUDING THE EXTENSION)
So all in all MULTIEX was meant to be a programmable file extractor/importer.

-DISCLAIMER:
 
 MULTIEX is a shareware program, so feel free to give it to anyone, on
 one condition: give them the same zip file you got yourself.
 By doing this you make sure they get the MULTIEX.DOC file, which is
 very important. If you fail to provide others with the MULTIEX.DOC
 file, you are responsible what happens if they use it. 
 It is illegal to SELL this program to others!
 Furthermore, the author is in no way responsible for any damage 
 MULTIEX may do to your programs and/or system. 
 By using MULTIEX you agree on these terms.


---------------------------------------------------------------------
			2. How to create an INI file.
			---=======================---

What you should begin with, is trying to figure out what kind of format
the datafile you wish to implement is using.

For example, does it have a header?
If so you should be able to see it, like filenames together with some
constants, which should give fileoffsets and filesizes...
Some formats have a tail, which means that the fileinfo (name, size,
offset) is at the BACK of the datafile. These mostly start with a
pointer to the beginning of the tail. Once there, you can read the info.

A very common format is this one:

-ID
 (a string giving the fileid)
-FILENUMBER
 (an int (2 bytes), or a long (4 bytes) giving the number of files in
 the datafile.)
-FILEINFO
 Like:
 FILENAME
 (a string of preset length)
 FILESIZE
 (a long giving the filesize)
 FILEOFFSET
 (a long giving the position of the file in the datafile)

 This then ofcourse is repeated FILENUMBER times; for every one of the
 FILENUMBER files.
-DATA
 (all the files put after eachother)

Now how would you tell multiex that this is the format he should use?
First, here are all the commands you can use in the INI-file:

----------------------------------------------------------------------

			2.1 COMMANDS FOR INIFILE
			---==================---

ID={identifier}     :
---------------------

NONE let's multiex know that the format has no
ID.
Else, give the found ID.


EVENTS :
--------

Always use this comment after ID and when you start programming the format!


NOFILENAMES         :
---------------------

Let's multiex know that there are no filenames,
so that when extracting occurs, multiex will
create n.MEX files.

GetLong   {variable}:
---------------------

Gets a long from the file and preserves it in
a certain variable you specify, see below for all
the variables you may use!

FlipLong {variable}:
--------------------

this will reverse the order of the bytes in the long. 
(e.g 00 00 05 4c will become 4c 05 00 00, which is a totally different 
number of course) Normal longs are read starting from low-byte to high byte.
(e.g. left to right). Some datafiles use the idiot method of reversing them,
when they store them. Why? No-one knows. 

GetInt    {variable}:
---------------------

Gets an int from the file.

WriteLong {variable}:
---------------------

Writes a long to the file (DON'T USE IT THOUGH!)

GetString (lenght) {variable}:
------------------------------

Gets a string of length into the given variable.

GetDString {variable1} {variable2}
--------------------------------

Gets a string of {variable1} size and stores it in {variable2}


GetNullString (length) {variable}:
----------------------------------

Gets a null-terminated string of max (length). This means that THE FILE
POINTER stops after the NULL of the string is found!
And NOT as with GetString after (length) bytes. Very useful. 

StrCReplace {variable} (char1) (char2):
---------------------------------------

Replaces all (char1)'s in {variable} to (char2).


StrEResizeC {character(in numbers)} {variable}: 
-----------------------------------------------

Resizes a given string ({variable}), starting from the 
end of the string, till a given character is reached.

LOOP:
-----

Starts a loop session.

ENDLOOP {variable1} {variable2}:
--------------------------------

Ends the loop when the condition {variable1}={variable2} is true.
If you specify the first var as EXTREOF, multiex will continue the loop
until it reaches the end of file. Very useful. 

SavePos {variable}:
-------------------

Saves the current fileposition into a given variable.

GoTo {variable}:
----------------

Jumps to a fileposition in the datafile specified by {variable}.

SET {variable} {specifier} {variable/number}:
---------------------------------------------

Sets a given variable to a certain amount. The {specifier} can be
NUMBER (which says that a number follows) or VAR (which says that
a variable follows).

SETFILECNT {0/variable}:
------------------------

You can either set the FILECNT 0 or a variable.

SETBYTESREAD {0/variable}:
--------------------------

BYTESREAD is used sometimes as a condition in a loop, so you must be
able to initialize it by setting it to 0 or a variable.
Whenever a read function is performed BYTESREAD is upped, so remember
that.

ADD {variable} {specifier} {number/variable}:
---------------------------------------------

To add a variable or a number to a variable.
see SET for specifiers.

SUBST {variable} {specifier} {number/variable}:
-----------------------------------------------

As ADD, only substraction.

MULTIPLY {variable} {specifier} {numb/var} {specifier} {numb/var}:
------------------------------------------------------------------

First give the variable that must contain the mutiplication.
Then specify the first (VAR/NUMBER), give it, and the second as well.
These will be mutiplied into the very first variable.

DIVIDE {variable} {specifier} {numb/var} {specifier} {numb/var}:
------------------------------------------------------------------

As MULTIPLY, just a divison occurs now, instead of MULTIPLY


UP {variable}:
-------------- 

Ups variable with 1.

DOWN {variable}:
----------------

Decreases variable with 1.

PROMPTUSER:
-----------

When you think the format has reached a certain point where
enough is known about the file so that it is ready to extract,
this will prompt the user for input on whether or not to extract
the file. I need to update this stupid command. Just use it always.

ExtractFILE ONE:
----------------

You can only use ONE as specification. I had implemented ALL as well,
but for importfunctions it was best to cut that and force everyone
to use a grand loop in the INI-formats.

SEPPATH:
--------

When you use SEPPATH (as a single command) a gotten filename which contains
path info (e.g. "\gifs\new\001.gif") will be separated from the info to 
obtain "001.gif", this is the file that will be saved. MultiEx does not
support path names (yet ;-))

FindFileID <string> <variable>:
-------------------------------

This command searches the file from the current fileposition for a 
<string> of max 40 length and saves the position (when found) in 
<variable>. This way, if you know that a datafile contains only
a certain type of file with a set ID you can get the OFFSET of this 
file that way. Just search for the ID and let MEX save its pos in FILEOFF.


Case <variable> {specifier} <Numb/Var> EXIT :
---------------------------------------------

When it is the CASE that the first <variable> matches the second
(which can be a number OR a variable> MULTIEX finishes (EXIT).

SeperateHeader <string>:
------------------------

Tells MEX to use a seperate header file, the same name, but the extension
<string>. This will only create a LST and IMP file. Use MC to extract things.

---------------------------------------------------------------------

			2.2 VARIABLES FOR INIFILE
			---===================---

VARIABLE	  TYPE		COMMENTS  
----------------+--------------+-------------------------------------
	   	|	       | 	 
FILESTART	| long	       | 
TAILOFF		| long         | anytime this is loaded the pos.
		|	       | of this long in the file is rec. 	 	
TAILSIZEB       | long         |
BYTESREAD	| long 	       | this is increased whenever bytes are
		|	       | read from the datafile.
DUMMYL		| long         | use for your own purpose.
FILECNTL        | long         | 
EXTRCNT         | long         | this is increased whenever a file
	        |	       | in the datafile is extracted or passed.
FILEOFF		| long         | whenever this is loaded and multiex is
		|	       | in import mode, the position
		| 	       | of the long in the file is recorded.					        	
FILESIZE        | long         | see FILEOFF.		 	 	
FILEJMP         | long         | see FILEOFF and furthermore, 
		|	       | when in importmode and the file has been 
	        |	       | imported, at the previously recorded
                |              | position the FILEJMP will be written.
		|	       | see the GRP.INI for the reason why.
FILENAME        | string       | maxlength is 80.
----------------+--------------+-------------------------------------

			3.3 MULTIEX ERRORS
			---============---

CODE	 TEXT			  	 EXPLANATION
--------+-------------------------------+----------------------------
1	| Error in MainINI		| you probably made a syntax
	|				| error in the MULTIEX.INI
2	| Error in ExINI		| you probably made a syntax
	|				| error in the format INI's
3	| Cannot Open MainINI		| MULTIEX.INI not found
4	| Cannot Open ExINI		| you have specified a format
	|				| INI which could not be found
5	| Cannot Open DATFile 		| you gave a datafilename at 
	|				| the commandline which could
	|				| not be found
6	| Illegal Format		| the ID given in the INI-
	|				| format does not correspond
	|				| with the datafile given at
	|				| commandline
7	| No DataFile			| the datafile given at command
	|				| line is not supported
8	| Unable to Create ListFile     | doserror, check name etc
9       | Unable to Create ExtractFile  | doserror, check name etc
10	| Illegal Switch 		| well?
11      | Error in Writing		| doserror, check name etc
12	| File To Import Not Found      | the file you gave at the 
	|				| commandline does not exist
	|				| in the specified datafile
13      | File Not Found		| duh?
--------+-------------------------------+----------------------------

			3.4 EXAMPLE OF 3.1
			---============---

Now, we are ready to create an INI file for the named example format in
2.1.
First we create a textfile in the CONFIG directory named after the 
extension the datafile of interest has, let's say DAT.INI.
Let's also assume the datafile has the ID "multiex".
Then the complete DAT.INI would look like:

;format file for DAT format
;comments you add with ;!

;ID is casesensitive

ID=multiex  			

;the filepointer is now 0+length of "multiex" (7)

;Now we tell MULTIEX that the format is up next:
EVENTS
	 
;We save the long at pos 7, which is the number of files in the datafile.
GetLong 	FILECNTL
;Then we save the filepointer which is now 7+4 = 12
SavePos		FILESTART

;Now we create a loop

LOOP
;We jump to the saved position
GoTo		FILESTART

;We get the file info FILESIZE, FILEOFF and FILENAME
GetLong		FILESIZE
GetLong		FILEOFF

;Let's assume the filenames are all 13 in length
GetString	13	FILENAME

;In order to be able to come back to the following file we
SavePos		FILESTART

;We prompt the user for the file to extract and Extract it
PROMPTUSER
ExtractFILE ONE

;Then we end the loop, saying that it should end when extracted=filenumber
ENDLOOP EXTRCNT FILECNTL

;This is the end of it, now you are ready to use this DAT.INI!


TO BE ABLE TO USE THE CREATED INI YOU MUST CREATE A DIR WITH THE NAME OF THE
DATAFILE EXTENSION IN THE CONFIG IF THIS IS NOT ALREADY THERE
AND PUT THE INI FILE (DAT.INI) IN THAT DIRECTORY. IMPORTANLY: IF THERE
ARE MORE FILES IN THAT DIR CREATE AND ADDITIONAL DAT.TXT (IN THIS CASE DAT)
AND MAKE IT A FILE WITH A SMALL NAME FROM THE GAME YOU MADE IT FOR
(FOR INSTANCE "Half Dead") NOW, WHEN MC ENCOUNTERS YOUR FILE IT WILL ASK FOR
YOU TO CHOOSE BETWEEN THE OTHER AND THE NEW ONE. 
TO TEST IT HOWEVER WITH MULTIEX DO THIS AT THE COMMAND LINE
e.g. MULTIEX HDEAD.DAT -debug 
BUT MAKE SURE YOU ALSO LEAVE A COPY OF THE DAT.INI IN THE CONFIG DIRECTORY!!



And now you are ready to rock!

--------------------------------------------------------------------

			4. Command line pars
			---==============---

The syntax is:

	multiex [datafile] [extractiondir] [switches]

If you do not specify an extraction dir the current dir will be used
to save the extracted files.

Switches:

-l		:	generates a listfile of all the files found
			in the datafile.
			The format of the listfile is :
			FILENAME FILESIZE FILEOFFSET.
-debug		:	when making your own format use this to follow
			multiex step by step.
-f[filename]	:	with this you can specify which file(s) to 
			extract.
			you can use the full name, or wildcard the name
			or the extension(for example *.WAV or SOUND.*)
-i[filename]	:	use this to import a file into your datafile.
			You must use a file with the same name as the one
			you want to replace in your datafile.
			MULTIEX does the following when importing:
			
			When YOUR file is shorter than or equal in length
			to the ORIGINAL it just puts the new file in, 
			and does not shorten the datafile.

			When YOUR file is longer than the ORIGINAL
			the difference in length can be two types:
			<= 50000: no temp file will be created
			>  50000: a temp file of <difference> long
				  will be created containing the info
				  from End-difference to End of the datfile.

       		        This info will be appended to the DATAFILE.
			Then all info which comes after the end
			of the ORIGINAL file to End-diff is moved
			<difference> bytes to the back of the
			datafile.
			Multiex performs a check if you have enough
			space when creating a temp file. 					 

-savetemp	:	Normally, after importing a file, multiex will 
			delete the created TEMP.MEX file again.
			With this switch you can preserve the created
			TEMP.MEX. (THIS FUNCTION IS DISABLED)
-all		:	extracts all files, without prompting.
 
--------------------------------------------------------------------

			5. Additional remarks
			---===============---

-> Sometimes when you import files, like sound files, the program which
   uses this datafile, does not sound the files you import.
   This is most likely due to the fact that the original files have 
   something build in the files. Be sure to import sound files of
   the same format and then check the original files for a catch.

-> When you extract files and specify some, remember that it is 
   case sensitive, which means you must use the right name!

-> When you import files, you CHANGE the original file!
   If possible make a copy of it before you alter it and possibly
   corrupt it too!
   Of course when everything is programmed correctly, no corruptions
   should occur. However, if you import a file and replace the original
   it is possible that that file is of utmost inportance to the program
   that uses the datafile. Be certain that you KNOW what you are doing.

---------------------------------------------------------------------

			6. Supported FORMATS
			---==============---

View the added SUPPORT.TXT for currently available formats.

--------------------------------------------------------------------

For comments or any questions send email to:

michael@xs4all.nl
mr.mouse@home.nl

Have fun using this program!

MrMouse/SadCom Ltd.

```
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-29T18:44:13+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

docs/mc.doc (MultiEx Commander manual)

```
Platform: DOS/WIN98 (Long Filenames) NOT WINDOWS 95.

-----------------------------------------------------------

General:
--------

I have provided TREAD and BREAD as default FILEVIEWERS.
With MC.INI you can alternatively use your own favourite text editor 
for any file you like,just read the instructions in the INI. Also, you can make MC start up, say,a music player when the cursor is on a *.MOD file and you press enter. 
It is quite easy. I use it of course! ;-)

Besides extracting and (be careful!) importing files with MC, you can also
create a datafile with the SadCom Ltd Format (name them *.SAD). 
Just select the files you wish to add when not in Extract Mode, and press
F1 to start creating the SAD(!) file. It saves full path names so keeping the 
directory structure intact.

IMPORTANT: 
if something is not functioning correctly 
(either when you have created ini's of your own, my own sloppy code is 
responsible) you can start up MC with MCMAIN -db, this enables some logging
of functions. You should find yourself with a MCDEBUG.TXT file in your MC
directory. If you please, send this file to me so I can work on it (the bug).

Keys:
-----
Quite frankly, it is as simple as any other file handlers.
you start it up and use the following keys:

<CURSOR>        :   all directions in your current window

<ENTER>         :   there are some possibilities:
                    Either you have given a program to call when
                    you press enter on a file with a given extension,
                    or MultiEx is called. If MultiEx does not recognize
                    the extension, you will be returned to MC,
                    if it does, you will switch to Extract Mode and
                    the contents of the datafile will be shown.

<ESC>           :   Extract Mode -> Switch to Normal Mode
                    Normal Mode -> Exit Program
		    Input mode -> abandon input		    
	
<INSERT>        :   Extract Mode -> select internal file
                    Normal Mode => select file in directory

<TAB>           :   switch between file and selection window, or Docs
                    (this is of course only possible when you have
                     indeed selected files)
<DELETE>        :   delete selected files, so, switch to the
                    selection window first!

<F1>            :   depending on the mode (Normal/Extract)
                    and if you selected files or not
                    you can start creating your own FILE.SAD

<F2>            :   RUNS BREAD with the file under the cursor
                    (when in Normal mode)
                    If you happen to be in Extract Mode MCVIEW is called
		    BREAD ADN TREAD HAVE AS KEYS: PAGEUP, PAGEDOWN AND ESCAPE.

<F3>		:   Select All Files


<F4>		:   Clear selectlist


<F5>            :   Delete the files in your selection window (Normal)


<F6>		:   MOVE - NOT IMPLEMENTED


<F7>            :   Extract the files in your selection window (Extract)
                    (you will be prompted to specify an extraction dir,
                     just press enter if you wish to use the current
                     dir)

<F8>		:   Import the selected files into a DAT file of your 
		    choice. As with MEX, be sure the filenames in the
		    datafile and of those you wish to import are identical.


<ALT>+1		:   Change DISK (e.g. C:\, D:\ etc) UP

<ALT>+2		:   Change DISK Down

```
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-29T19:24:51+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

Finally some screenshots



mc.PNG (21.6 KiB) Viewed 630 times





openarchive.PNG (17.77 KiB) Viewed 631 times





extract.PNG (15.04 KiB) Viewed 627 times





creation.PNG (22.42 KiB) Viewed 626 times





mcview.PNG (38.88 KiB) Viewed 626 times





tread.PNG (17.68 KiB) Viewed 624 times





multiex_debug.PNG (12.91 KiB) Viewed 621 times
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-29T19:28:34+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

> Reply from Dinoguy1000
>
> Cool. Are you going to archive other old versions of MexCom as well?

Maybe I will  See where I got the stuff
## Post #8
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-05-08T08:48:51+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

Sweet, now I feel so nostalgic 

Very funny app, when I run that it shows me:

> Frankly, the program shouldn't have reached this far!

Noo  I'm just joking, I just checked source codes... thats why I feel nostalgic, C without oop and lot of global variables... hh

Thanks for showing that to us!
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-08T09:05:19+00:00
- Post Title: Oldie: MultiEx Commander 2.3 DOS ;-)

Yeah
