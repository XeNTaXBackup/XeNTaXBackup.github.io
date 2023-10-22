## Post #1
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-28T09:49:39+00:00
- Post Title: TRE Class VB6 Source Code released!

[As promised](http://forum.xentax.com/viewtopic.php?t=519), the VB6 Source code of the TRE Object Class.   

[**EDIT**] THIS WAS UPDATED ON THE 11TH OF JANUARY 2004
THE NEW VERSION CODE (0.7.16) IS RELEASED THAT FIXES A PROBLEM WITH NON-COMPRESSED RESOURCES! [/**EDIT**]

First the Class_readme.txt :


> Reply from Class_readme
>
> 
*****************************************
 TRE ARCHIVER VISUAL BASIC 6 SOURCE CODE
        CREATED IN DECEMBER 2003
          BY MIKE W. ZUURMAN
         ALSO KNOWN AS MR.MOUSE
      XENTAX http://www.xentax.com
-----------------------------------------

TREOBJECT.CLASS - manual

-----------------------------------------

This class represents a *.TRE Archive
TRE Archives are shipped with the PC game
Star Wars : Galaxies, and contain the
resources of the game, such as sounds,
textures and game settings. Contact the producer
of the game before you alter their game and ask
for permission!
Resources in TRE Archives may be compressed
using NORMAL Zlib compression. Thus, using
the "create" funtion you can create archives of
your own, as an alternative to PKZip.
THE TRECLASS REQUIRES THE DYNAMIC LIBRARY

 ZLIB.DLL (at least version 1.1.2.0)
 -----------------------------------

 available at http://www.zlib.net
The TREClass Code is not very optimized
and comments may be scarce.
As long as you credit the author, you can
do with it as you please, there are no
copyrights on this file.


****************************************
The CLASS PROPERTIES (syntax + description)
****************************************

------------------------------------------------
TREObject.DebugLog(strLog As String)

If this is set, only THEN the log will be
kept, so you can use it to turn ON the logging
------------------------------------------------
TREObject.SetReplaceNames(repnames As Byte)

Turn on(>0)/Off(0) the replacing of filenames
in the filenamestail

------------------------------------------------
TREObject.SetReplaceOld(repold As Byte)

overwrite the old TRE Archive if
-chosen the same savename as the old one

------------------------------------------------
TREObject.ProgressStatus() As Double

Get the current status of any process
------------------------------------------------
TREObject.ItemCount() As Long

Get the number of items in the TRE Archive
------------------------------------------------
TREObject.ItemSize(Index As Long) As Long

Get the size of the item with index Index
in the TRE Archive
------------------------------------------------
TREObject.ItemOffset(Index As Long) As Long

Get the offset of the item with index Index
in the TRE Archive
------------------------------------------------
TREObject.ItemFilename(Index As Long) As String

Get the filename of the item with index Index
in the TRE Archive
------------------------------------------------
TREObject.ItemCompressionMethod(Index As Long) As Long

Get the compressionmethod of the item with index Index
in the TRE Archive
------------------------------------------------
TREObject.ItemOriginalSize(Index As Long) As Long

Get the originalsize of the item with index Index
in the TRE Archive
------------------------------------------------


****************************************
PUBLIC FUNCTIONS AND SUBS (syntax + description)
****************************************

------------------------------------------------
TREObject.Extract(AsBuffer As Byte, ByRef TheData() As Byte, Optional strPath As String, Optional strName As String, Optional Index As Long)  As Long

Extracts a specified item to the path provided

AsBuffer : Do(>0)/Do not(0) save, but return the (extracted) item as a buffer
TheData() : will contain the extracted file if AsBuffer > 0
strPath : the path to save the item to (optional)
strName : the name of the item (optional)
Index : the index of the item in the TRE Archive (optional)

Note : strName OR Index must be given to identify
the item in the list


------------------------------------------------
TREObject.Replace(Activate As Byte, Optional strReplacePath As String, Optional SaveTREPath As String, Optional strName as string, Optional Index As Long) As Long

Targets an item for replacement in the TRE Archive
Depending on the Activate variable
actual Replacement and creation of a new
TRE Archive will follow

Syntax:
Activate : Target(0) the item and follow with (1) actual replacement
strReplacePath : (optional) The path to the file that should replace the item in the TRE Archive
strSaveTREPath : (Optional) The path that should become the new TRE Archive after replacement
strName : (optional) the name of the item in the TRE Archive
Index : (optional) the index of the item in the TRE Archive

Note : strName OR Index must be given to identify
the item in the list
------------------------------------------------

TREObject.OpenTRE(strFile As String) As Long

Opens a specified TRE Archive

Syntax:
strFile: The path to the TRE Archive to open

Note : This will clear all previous items in this
TREObject and reset it to the new TRE Archive
------------------------------------------------

TREObject.Clear()

Clear the TRE Object

Note : This will clear all previous items in this
TREObject. It will be reset to a default state
------------------------------------------------

TREObject.Create(strFilename As String, strList As String)

Create a new TRE Archive

Syntax:
strFilename: The path to the TRE Archive to create
strList : A string containing a list of space-delimited filenames to inlude in the archive
   Note to list : the first entry needs to be the parent folder of all the
                  items following in the list
                  Example : "c:\folder file1.fil file2.fil file3.fil"

Note : This will clear all previous items in this
TREObject and reset it to the new TRE Archive

------------------------------------------------

Download the 

[TRE_Class_Source_Code](http://www.xentax.com/downloads/tools/TRE_Class_VB6Source_0716.zip) (11Kb)

Or the complete 

[TRE Archiver Source code](http://www.xentax.com/downloads/tools/TRE_Archiver_Source_0716.zip) (48Kb)

Executables :

[viewtopic.php?t=519](http://forum.xentax.com/viewtopic.php?t=519)

Report comments, questions and suggestions here!
