## Post #1
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-06-25T17:51:15+00:00
- Post Title: Multiex.dll , ever wanted one?

Soon MultiEx Commander 3.9 will be released. 
Hopefully it will run on Win98/XP/2000. 

Anyway, with this release multiex.dll will be run. 
Yes, this is the main engine that runs on Binary MultiEx Script (BMS) files. 

=============================

DOWNLOAD MULTIEX.DLL (52 Kb)

=============================
This package includes BMS files for Multiex.dll to use, 69 in total. 
=============================



For any of you who'd like to implement multiex funtionality in your own programs, here's what the dllreadme.txt file will have to say.

> <==========================
>
> MultiEx 3 ActiveX DLL 
>
> ==========================>
>
> 
>
> Version    : 1.00
>
> COpyright  : XeNTaX 2003
>
> Author     : M.W.Zuurman (AKA Mr.Mouse)
>
> Website    : http://www.xentax.com
>
> 
>
> ---------------------------
>
> 
>
> Instructions for authors:
>
> 
>
> If you want to implement the MultiEx GameArchive Analysis
>
> Engine in your programs you must be aware of the following:
>
> 
>
> You must regsvr32.exe it. 
>
> 
>
> You must have Binary MultiEx Scripts (*.BMS) files that enable 
>
> processing of the archive you want to process! 
>
> (There are much included in the DLL package)
>
> 
>
> 
>
> The CLASS you want to address is AMex3GetFileInfoClass. 
>
> The CLASS AMex3GetFileInfoClass gives you access to 
>
> the function Mex3GetFileInfo. 
>
> 
>
> For example, assign a new AMex3GetFileInfoclass called RunMex and use
>
> it to call the function : ie "RunMex.Mex3GetFileInfo". 
>
> The Syntax is like this :
>
> 
>
> ------------------------------------------------
>
> Integer Mex3GetFileInfo (String PathToBMS, String PathToArchive, String ArgumentList)
>
> ------------------------------------------------
>
> 
>
> Arguments you may pass to the engine :
>
> 
>
> -l   : Log the process in a log file 
>
>        (it will be saved in the App.Path as mex3.log)
>
> -lst : by default the dll will create a file called multiex.lst 
>
>        that lists important variables on the archiveformat as well 
>
>        as the contents of the file. See "The List File"
>
>        With the argument -lst you tell the DLL to name it differently
>
>        USAGE : "-lst newname" 
>
> -pro : show a basic progress window during DLL operation
>
> -p   : Always show the Error MessageBox at the end of operation
>
> 
>
> The Return value is an integer and essentially the error code. 
>
> (0 = no errors)
>
> 
>
> -------------------------------------------------
>
> 
>
> The List File 
>
> -------------
>
> 
>
> Upon succesfull analysis of a gamearchive multiex.dll will 
>
> present you with a file called multiex.lst by default. 
>
> 
>
> The format has a header that gives :
>
> 
>
> Long	NumberOfFiles	: Number of files in the archive
>
> Long    Mex3ComType	: Compressiontype of the files in the archive (if any)
>
>                           0   = none
>
> 			  750 = ZLibCompression1
>
> Long    Mex3ImpType 	: Imporationtype that lets you know:
>
> 			  iStandard = 710
>
> 			  (both fileoffsets and filesizes are mentioned in the
>
> 			   archive)
>
> 			  iSFileOff = 711
>
> 		           (only fileoffsets are mentioned)
>
> 			  iSFileSize = 712
>
> 		           (only filesizes are mentioned)
>
> 			  iNone = 713
>
>  			  (for MultiEx Commander : no importing allowed)
>
> 			  iStandardTail = 714
>
> 			  (Standard but with a tailpointer at the beginning)
>
> 
>
> Byte	TailOffOffYes	: Is there an offset of a pointer to a tail?
>
> 			  0 = No
>
> 			  1 = Yes
>
> Long    TailOffOff	: The location of the offset of a pointer to a tail 
>
> 			  in the archive. 
>
> Byte    FileOffs_Rev	: The (long) variables depicting the Offsets of 
>
> 			  the different files in the archive are reversed in saved
>
> 			  format. So An offset of 12cd3400 would be written in the
>
> 			  archive as 00 34 cd 12. Low Byte->High Byte switched!
>
> 			  0 = No
>
> 			  1 = Yes
>
> Byte    FileSizes_Rev	: Like above, now for the size variables for each file 
>
> 			  in the archive
>
> 
>
> Then follows the body of information on each file in the archive
>
> (NumberOfFiles times!)
>
> 
>
> The record for a single entry looks like this:
>
> 
>
> String (preceded by VB depictor for a string) 	Name of the File in the archive
>
> Long   (preceded by VB depictor for a long) 	Offset of the file in the archive
>
> Long   (preceded by VB depictor for a long) 	Size of the file in the archive
>
> Long   (preceded by VB depictor for a long)	Offset of the Offset Variable 
>
> Long   (preceded by VB depictor for a long)	Offset of the Size Variable 
>
> NOTE : IF THE FILES ARE COMPRESSED THE FOLLOWING IS ADDED TO THE RECORD:
>
> Long   (preceded by VB depictor for a long)	The Original Size of the file 
>
> Long   (preceded by VB depictor for a long)	Offset of the Original Size Variable 
>
> 
>
> 
>
> There, that's it! Note that you may not need all the header variables for your 
>
> purpose at all. Then just ignore those values. 
>
> 
>
> -------------------------------------------------
>
> 
>
> For any additional help, visit the XeNTaX MultiEx Forums at 
>
> 
>
> http://forums.xentax.com
>
> 
>
> -------------------------------------------------
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-06-25T20:53:37+00:00
- Post Title: Multiex.dll , ever wanted one?

To help you out, here's some C++ code to address the function:

Create a reftodll console application and write in reftodll.cpp

> #include "stdafx.h"
>
> // you may want to #include <basetsd.h> as well
>
> 
>
> int main(int argc, char* argv[])
>
> {
>
>   HRESULT  hr;
>
>   CLSID    clsid ;
>
> // Initialize an appointment
>
>   CoInitialize(NULL);					
>
> 
>
> //obtain the Class id 
>
>   CLSIDFromProgID(OLESTR("multiex.AMex3GetFileInfoClass"),&clsid); 
>
> 
>
> //Make RunMex the class of interest
>
>   _AMex3GetFileInfoClass *RunMex; 
>
> 
>
> // Create the Class instance, if failure show a message
>
>     if (CoCreateInstance(clsid, NULL, CLSCTX_INPROC_SERVER,__uuidof(_AMex3GetFileInfoClass), (void**) & RunMex) >= 0)
>
> 	{
>
> // succes, tell user to press ok to start running 
>
> 		MessageBox(0, "Ok to run MultiEx", "", MB_OK);
>
> // Run the Mex3GetFileInfo function, using the arguments
>
> // hr is the resulting error number, 0 = no error
>
> 		hr = RunMex->Mex3GetFileInfo("big.bms", "english.big", "-p -l -lst mylist.lst");						
>
> 		if (hr > 0 )
>
> 		{
>
> 			MessageBox(0, "MultiEx returned an error", "", MB_OK);
>
> 		}
>
> 	}
>
> 	else
>
> 	{
>
> 		MessageBox(0, "Failed to address the DLL!", "", MB_OK);		}
>
> // Destroy the appointment
>
> 	CoUninitialize();	
>
> 
>
> return 0;
>
> 
>
> }

In the StdAfx header you have write:

> #import "multiex.dll"
>
> using namespace multiex;
at the appropriate possition

There, that should do the trick. Compile everything and make sure you check the dependencies. 

The example expects multiex.dll in the project directory and a big.bms file 
for C&C: Generals BIG files , as well as the english.big file of the game in the app directory.
## Post #3
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-06-26T14:47:17+00:00
- Post Title: Multiex.dll , ever wanted one?

Hi!

  I hope I can work on this soon.   

  Since your mail I found how to use ActiveX in Delphi... almost as easy as in VB.   

  ByE!
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-06-26T15:14:49+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Elbereth
>
>   Since your mail I found how to use ActiveX in Delphi... almost as easy as in VB.
 Excellent, and hey, what's wrong with VB   (CHECK OUT MY COOL C++ code ABOVE!!   )

Right, I just need to run a few more tests on the thing, and add some games. 

"This could be the beginning of a beautiful relationship!"  - MultiDragon sound nice?
## Post #5
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-06-26T18:03:42+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Mr.Mouse
>
>  Excellent, and hey, what's wrong with VB  
(CHECK OUT MY COOL C++ code ABOVE!!   )

 Nothing! I coded Dragon UnPACKer 4 in VB... 

> Reply from Mr.Mouse
>
> Right, I just need to run a few more tests on the
thing, and add some games.

  Ok! add as many games as you want! 

> Reply from Mr.Mouse
>
> "This could be the beginning of a beautiful
relationship!"  - MultiDragon sound nice?

  Hehe the plugin should be named MultiEx plugin for Dragon UnPACKer
or something like that.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-06-26T19:28:27+00:00
- Post Title: Multiex.dll , ever wanted one?

Hehe, well, we will have to see about the name    

One key function of MultiEx Commander though is that it enables the user to replace files in the game archive. Now, all that multiex.dll does is provide the user with the list file (as described above) that contains variables necessary for succesful file importation. It is MultiEx Commander that has the importation function. For succesful integration of multiex.dll function, I guess you will have to write such a function yourself, in Delphi, for your program to support it.  

We might even consider creating a new dll that takes care of this. However, then we will have to recreate and merge the two programs, because then it really is the combination of the two programs that makes the one tool to rule them all.   

MultiEx Commander has the WinZip-like GUI, Dragon UnPACK more like an Explorer interface.
## Post #7
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2003-07-24T14:44:07+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Mr.Mouse
>
> and hey, what's wrong with VB
you want a list?
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-07-24T14:48:30+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Captain
>
> you want a list?

No thanks, I already have my own.
## Post #9
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-12T18:43:33+00:00
- Post Title: Multiex.dll , ever wanted one?

Hi!

  I started coding a driver for Dragon UnPACKer 5 that use MultiEx DLL.
  I was able to generate a lst file for Doom2.wad (to test), but I still need to do the lst parsing.

  I have one question:
  Is it me (in my code) to detect the file format (and choosing the right BMS file) or do your DLL can do it ?
  Because it is quite confusing.

  ByE!
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-13T06:32:23+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Elbereth
>
> Hi!

  I started coding a driver for Dragon UnPACKer 5 that use MultiEx DLL.
  I was able to generate a lst file for Doom2.wad (to test), but I still need to do the lst parsing.

  I have one question:
  Is it me (in my code) to detect the file format (and choosing the right BMS file) or do your DLL can do it ?
  Because it is quite confusing.

  ByE!

No, as you also might have encountered, many formats do not have any ID tag anywhere in the file, other than the file extension. However, the file extension is not enough to identify a BMS file to use, because many games use archives with the same extension, but that are in fact totally different formats.   

Now, IF a given format does have a ID tag, and you would pass the wrong BMS file to MultiEx.DLL, the dll would abort process and notify that the ID tag is invalid in your achive. 

In MultiEx Commander the user selects the format prior to processing, because of the above mentioned reason. Then MultiEx Commander tells multiex.dll to use the BMS file that belongs to the user-chosen format. 

In essence, you will have to write some small code (at least its small in MC   ) to pass the right BMS file to MultiEx.DLL when appropriate.
## Post #11
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-13T08:50:45+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Mr.Mouse
>
> No, as you also might have encountered, many formats do not have any ID tag anywhere in the file, other than the file extension. However, the file extension is not enough to identify a BMS file to use, because many games use archives with the same extension, but that are in fact totally different formats.

   Yeah I know...

> Reply from Mr.Mouse
>
> Now, IF a given format does have a ID tag, and you would pass the wrong BMS file to MultiEx.DLL, the dll would abort process and notify that the ID tag is invalid in your achive.

  Hmm ok. And do I have a way to know from the BMS file is there is ID tag checking ?

> Reply from Mr.Mouse
>
> In MultiEx Commander the user selects the format prior to processing, because of the above mentioned reason. Then MultiEx Commander tells multiex.dll to use the BMS file that belongs to the user-chosen format.

  I should download your tool to see how it works. 

> Reply from Mr.Mouse
>
> In essence, you will have to write some small code (at least its small in MC   ) to pass the right BMS file to MultiEx.DLL when appropriate.

  That's what I though. You see in Dragon UnPACKer 5 the plugins have two exported functions IsFormat and ReadFormat. The IsFormat tells from the extension if it can read the file (or using ID tags if the Deeper argument is TRUE) and then Dragon UnPACKer 5 run all the drivers that answered TRUE to IsFormat with ReadFormat, if no driver could read the file then I display and error. So I was thinking in making a table to associate BMS files with extensions in my driver (which the user could change).

  Another note:
  What OCX and DLLs do your MultiEx.DLL needs ?
  (because I was forced to install the VB6 runtime to get it to work on my computer)
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-13T09:37:53+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Elbereth
>
> 
  Hmm ok. And do I have a way to know from the BMS file is there is ID tag checking ?

Well, at the moment the only two ways to see wether there is ID tag checking is to open the BMS in Mex3Scriptor (that comes with the MultiEx Commander package) and examine the script. If there's a command :
IDString "somestring" 
then yes. You might also open the BMS file with a hex editor and examine its tail, to see if there's some kind of ID tag string in the tail. 

> Reply from Elbereth
>
> I should download your tool to see how it works. 

  

> Reply from Elbereth
>
> That's what I though. You see in Dragon UnPACKer 5 the plugins have two exported functions IsFormat and ReadFormat. The IsFormat tells from the extension if it can read the file (or using ID tags if the Deeper argument is TRUE) and then Dragon UnPACKer 5 run all the drivers that answered TRUE to IsFormat with ReadFormat, if no driver could read the file then I display and error. So I was thinking in making a table to associate BMS files with extensions in my driver (which the user could change).

Yes, that seems a good idea.   

> Reply from Elbereth
>
>  Another note:
  What OCX and DLLs do your MultiEx.DLL needs ?
  (because I was forced to install the VB6 runtime to get it to work on my computer)

Really? That's kind of strange. Was there some kind of error? If so, what error did it display? It may be that the "progress" window needs some OCX/DLL. Please tell me the error you encountered. so I can fix any bugs or dependencies.
## Post #13
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-13T13:45:59+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Mr.Mouse
>
> Really? That's kind of strange. Was there some kind of error? If so, what error did it display? It may be that the "progress" window needs some OCX/DLL. Please tell me the error you encountered. so I can fix any bugs or dependencies.

  The error was with MSCOMCTL.OCX that wasn't registered, I installed the VB6 runtime because I knew this file was registered during the install.
After installing the VB6RT all was ok so there is maybe other OCX dependencies.

  By the way MultiEx Commander 3.8b crash sometimes here, everytime I do some kind of action. The first time it just crashed everytime I pressed something on the interface.

  Now when I run MultiEx it search for some stuff on internet and then the main window appear. Now if I press Info > Supporting formats (Allowing import) I got the following error (same error everytime it crashed even when doing something else):

   Erreur d'exécution '35603': Clé non valide.
   (which means something like Runtime error '35603': Invalid key)

  If I press OK the program just close.

  I am running under Windows XP Pro Corporate with SP1 and all Windows Update patches until today.
## Post #14
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-13T15:47:17+00:00
- Post Title: Multiex.dll , ever wanted one?

In the readme you write:

```
                          0   = none
			  750 = ZLibCompression1
```


Now when I open Doom 2 WAD file (this is the first file I found on my harddisk) this field value is 99. What does that mean ? (because for me Doom 2 IWAD file isn't compressed)

So this also leads to some problem because you write:

```
Long   (preceded by VB depictor for a long)	The Original Size of the file 
Long   (preceded by VB depictor for a long)	Offset of the Original Size Variable
```


  So I coded it that way:
  If Mex3ComType is not 0 then read 2 long values and then next entry
  If it is 0 then next entry

  The problem is for the Doom 2 IWAD this doesn't work because the 2 long values do not exist...

  I just tried with Shadow Warrior GRP file (which I also know is uncompressed) and the Mex3ComType is still 99.

  One last question:
  How do I know where the LST file is saved ?
  Sometimes it is saved in the multiex.dll directory and sometimes in the same directory as the source file. I would really appreciate to give him the full path to the LST file to create.
  I tried giving a path after the -lst parameter but it doesn't work.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-13T19:58:52+00:00
- Post Title: Multiex.dll , ever wanted one?

> Reply from Elbereth
>
> In the readme you write:
Code: Select allLong    Mex3ComType	: Compressiontype of the files in the archive (if any)
                          0   = none
			  750 = ZLibCompression1

Now when I open Doom 2 WAD file (this is the first file I found on my harddisk) this field value is 99. What does that mean ? (because for me Doom 2 IWAD file isn't compressed)

So this also leads to some problem because you write:
Code: Select allNOTE : IF THE FILES ARE COMPRESSED THE FOLLOWING IS ADDED TO THE RECORD:
Long   (preceded by VB depictor for a long)	The Original Size of the file 
Long   (preceded by VB depictor for a long)	Offset of the Original Size Variable

  So I coded it that way:
  If Mex3ComType is not 0 then read 2 long values and then next entry
  If it is 0 then next entry

  The problem is for the Doom 2 IWAD this doesn't work because the 2 long values do not exist...

  I just tried with Shadow Warrior GRP file (which I also know is uncompressed) and the Mex3ComType is still 99.
 You are quite right, I wrote the readme.txt with air in my head instead of brains. The value = 99 = No Compression. Not 0. So , you read 99 and that means no compression and no elongation of the entries. Sorry for that. 

> Reply from Elbereth
>
>   One last question:
  How do I know where the LST file is saved ?
  Sometimes it is saved in the multiex.dll directory and sometimes in the same directory as the source file. I would really appreciate to give him the full path to the LST file to create.
  I tried giving a path after the -lst parameter but it doesn't work.

Well, it takes full paths in my book!

For example : "F:\Code\VISUAL~1\MC39ME~1\data\multiex.lst"

It simply takes a string and uses that as a Path...it really should work the way you want to.
## Post #16
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-13T20:38:04+00:00
- Post Title: Re: some other questions about MultiEx DLL

> Reply from Mr.Mouse
>
>   You are quite right, I wrote the readme.txt with air in my head instead of brains. The value = 99 = No Compression. Not 0. So , you read 99 and that means no compression and no elongation of the entries. Sorry for that.

 Fine! np 

> Reply from Mr.Mouse
>
> Well, it takes full paths in my book!

For example : "F:\Code\VISUAL~1\MC39ME~1\data\multiex.lst"

It simply takes a string and uses that as a Path...it really should work the way you want to.

  Hmm do I need to use small 8.3 names like in your exemple ?
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-14T08:17:27+00:00
- Post Title: Re: some other questions about MultiEx DLL

Hmm....you could try to use small names. See if that helps. That would be strange though, but you never know. The ways of programming languages are sometimes mysterious:  you never know what code you end up with. Still, it saves programming in assembly, which is a hassle, although very accurate and mostly you know exactly what happens.
## Post #18
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-14T11:29:55+00:00
- Post Title: Re: some other questions about MultiEx DLL

> Reply from Mr.Mouse
>
> Hmm....you could try to use small names. See if that helps. That would be strange though, but you never know.

   It worked with SFN... I would bet it is because of the spaces in the path.

   Now the driver works! 
   Yes MultiEx.DLL works in Dragon UnPACKer 5. Hehe!!

   But I still have some things to do.
   And so here is questions (again.. hehe):

1. Which file format do have Zlib compressed files in it ?
    For testing purposes. Yeah I am a lazy guy I don't want to search by myself 

2. In the header of the LST file do I need to care about FileOffs_Rev and FileSizes_Rev if I don't use importation ?
   (in fact does the LST file entries always have normal (non-rev) offsets/sizes)

   That's all. After that it will be ready and I will release a test version.
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-14T11:44:01+00:00
- Post Title: Re: some other questions about MultiEx DLL

Damn. Oh well, I will have a look-see in the future version of the DLL to get rid of that stupid space-bug.  

> Reply from Elbereth
>
> Now the driver works! 
   Yes MultiEx.DLL works in Dragon UnPACKer 5. Hehe!!

   But I still have some things to do.
   And so here is questions (again.. hehe):

1. Which file format do have Zlib compressed files in it ?
    For testing purposes. Yeah I am a lazy guy I don't want to search by myself 

2. In the header of the LST file do I need to care about FileOffs_Rev and FileSizes_Rev if I don't use importation ?
   (in fact does the LST file entries always have normal (non-rev) offsets/sizes)

   That's all. After that it will be ready and I will release a test version.

1. Hmm, well, I'm lazy too, so I haven't got a clue which have that. most of them don't though. I will see if I can trace them. 
2. No

Anyway, cool! I will download your testversion as soon as you've got it running !
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-14T14:05:36+00:00
- Post Title: Re: some other questions about MultiEx DLL

Ok : 

Arcanum is the only one that has ZLib1 compression, if I'm correct.
## Post #21
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-14T14:51:37+00:00
- Post Title: Re: some other questions about MultiEx DLL

> Reply from Mr.Mouse
>
> Arcanum is the only one that has ZLib1 compression, if I'm correct.

   Argh. I don't have this game. :/

   I noticed something with your DLL it is creating a log file but I don't have the -l argument set (only -lst).

   I am almost done for the test version. My drvier use early binding to attach to MultiEx.DLL. The problem is that if your ActiveX DLL isn't registered when running Dragon UnPACKer then it will hang on startup. :/ I will have to investigate the late binding to avoid this problem.
## Post #22
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-14T15:50:22+00:00
- Post Title: Re: some other questions about MultiEx DLL

Ok!

Here is the first test version, hope it works.
It is a 7Z file so you will need [7-Zip v2.30](http://www.7-zip.com) to decompress it.

Dragon UnPACKer v5.0.0 RC2-WIP4 or later is REQUIRED
(You can get it from: [http://www.elberethzone.net/index.php?page=dup5dev](http://www.elberethzone.net/index.php?page=dup5dev))

[Mr.Mouse's MultiEx DLL wrapper v1.0.0 Alpha 1](http://download.elberethzone.net/dup5/drv/multiex/multiex100alpha1.7z) (185KB)
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-14T16:03:01+00:00
- Post Title: Re: some other questions about MultiEx DLL

IT LOADS! Now how do I use it? To test ?
## Post #24
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-14T16:36:12+00:00
- Post Title: Re: some other questions about MultiEx DLL

The drv_multiex.ini I provided use only 4 BMS scripts, I was lazy to add other BMS, so try opening one of those 4 extensions. Just edit the INI file as stated in the README.txt to add other BMS scripts.

FIFA 1999 (*.ABG)
FIFA 2000 (*.ABG)
FIFA 2001 (*.ABG)
FIFA 2002 (*.ABG)
Age of Mythology (*.BAR)
Doom (*.WAD)
Doom 2 (*.WAD)
Hexen (*.WAD)
Heretic (*.WAD)
Duke Nukem 3D (*.GRP)
Shadow Warrior (*.GRP)

Remove all other drivers to be sure it is the MultiEx one used. Because drv_default can open BAR and GRP for ex. And I think it will have priority (but not sure).
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-14T19:03:27+00:00
- Post Title: Re: some other questions about MultiEx DLL

Well, it seems to work okay. ABG should be BIG files though. 
I added SadComLtdat files (*.SAD) and something went wrong with the parsing. The filenames are saved in the list in the format  "\mc\docs\readme.txt" , and so your program doesn't know how to handle a "\" directory (blanc) and then no filenames were written. 

Do you delete the lst and log file afterwards?
Can you add something like "MultiEx.DLL (C) 2003 XeNTaX" before the "you can get MultiEx Commander from", thanks!

Well, it seems to function okay, the only thing is the regsvr32 upon program install. Perhaps you can also run the batch you created in the background after install. Or check the registry for its existence. 

You should add the other BMS files in your INI as well, of course...
## Post #26
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-14T19:24:37+00:00
- Post Title: Re: some other questions about MultiEx DLL

> Reply from Mr.Mouse
>
> ABG should be BIG files though.

  Oh.. ok, I don't have those games so I don't know, I will look in your MultiEx Commander for the right extensions. 

> Reply from Mr.Mouse
>
> I added SadComLtdat files (*.SAD) and something went wrong with the parsing. The filenames are saved in the list in the format  "\mc\docs\readme.txt" , and so your program doesn't know how to handle a "" directory (blanc) and then no filenames were written.

  Yeah this might be because of the directory detection, I will remove the starting \ or / when they exist that should fix the problem.

> Reply from Mr.Mouse
>
> Do you delete the lst and log file afterwards?

  I delete the LST file just after parsing it.

> Reply from Mr.Mouse
>
> Can you add something like "MultiEx.DLL (C) 2003 XeNTaX" before the "you can get MultiEx Commander from", thanks!

  Of course!

> Reply from Mr.Mouse
>
> Well, it seems to function okay, the only thing is the regsvr32 upon program install. Perhaps you can also run the batch you created in the background after install. Or check the registry for its existence.

  I don't know how I will distribute this plugin, but with Inno Setup I might be able to do all the installation steps automatically. Or maybe I will modify my D5P tools to be able to register a dll. One thing for sure I cannot release it until I release the v5.0.0 RC2. That means I have some time yet to decide how to do it 

> Reply from Mr.Mouse
>
> You should add the other BMS files in your INI as well, of course...

  Yeah when I get some time
## Post #27
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-14T19:29:46+00:00
- Post Title: Re: some other questions about MultiEx DLL

> Reply from Elbereth
>
> Mr.Mouse wrote:Do you delete the lst and log file afterwards?

  I delete the LST file just after parsing it.

Ah, so I assume it doesn't create a log file anymore when you don't want to?
## Post #28
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-14T19:42:25+00:00
- Post Title: Re: some other questions about MultiEx DLL

> Reply from Mr.Mouse
>
> Ah, so I assume it doesn't create a log file anymore when you don't want to?

   It seems so... I might have dreamed last time. Ahahaha.
## Post #29
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-14T19:54:00+00:00
- Post Title: Re: some other questions about MultiEx DLL

> Reply from Elbereth
>
> Mr.Mouse wrote:Ah, so I assume it doesn't create a log file anymore when you don't want to?

   It seems so... I might have dreamed last time. Ahahaha.
## Post #30
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-14T20:46:57+00:00
- Post Title: Re: some other questions about MultiEx DLL

Here is the second test version, I tried to fix/add all you talked about. Still no automatic install. I have removed all BMS scripts that my program can handle already. All the included BMS are in the INI now.

[Mr.Mouse's MultiEx DLL wrapper v1.0.0 Alpha 2](http://download.elberethzone.net/dup5/drv/multiex/multiex100alpha2.7z) (186KB)
## Post #31
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-14T21:56:43+00:00
- Post Title: 

Not bad...    Transport Tycoon Deluxe BMS (*.CAT, actually only one CAT file, sample.cat) is a RIFF (wave) searcher. Dragon reports an error when it uses that.
## Post #32
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-15T07:16:39+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Not bad...    Transport Tycoon Deluxe BMS (*.CAT, actually only one CAT file, sample.cat) is a RIFF (wave) searcher. Dragon reports an error when it uses that.

  Ohh. I will remove it then because the HyperRipper can do that already.
  But it should work no?
  I will have to get my transport tycoon deluxe cd back to test.
## Post #33
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-15T13:55:50+00:00
- Post Title: 

I have modified my D5P tools so ActiveX DLLs can be registered and installation seems to work fine.

I cannot release the D5P installation version of the plugin because Duppi (the tool to install D5P) released along with 5.0.0 RC1 isn't compatible (obviously) with those options. But automatic installation works.
## Post #34
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-15T15:12:17+00:00
- Post Title: 

No problem, you can just release it with the new version of DUP. 

By the way, this version 3.8 of MultiEx Commander 
might be better for your platform XP.

[http://www.xentax.com/downloads/multiex ... up_vsi.zip](http://www.xentax.com/downloads/multiex/mc32setup_vsi.zip)

I installed it on different XP systems and it worked fine.   

Read the readme_now first as always.

EDIT : UPLOADED FULLY
## Post #35
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-15T17:40:12+00:00
- Post Title: 

Or perhaps even better : The Inno Setup version: 

[http://www.xentax.com/downloads/multiex ... tup_XP.exe](http://www.xentax.com/downloads/multiex/mc32setup_XP.exe) (2.3Mb)



Alpha
## Post #36
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-17T09:34:47+00:00
- Post Title: 

By the way, Elbereth, the link at your site to 
[http://download.elberethzone.net/dup5/d ... 0alpha2.7z](http://download.elberethzone.net/dup5/drv/multiex100alpha2.7z)
doesn't work.
## Post #37
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2003-08-17T09:38:02+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> By the way, Elbereth, the link at your site to 
http://download.elberethzone.net/dup5/d ... 0alpha2.7z
doesn't work.
 Oops! Fixed.
## Post #38
- Username: XL_R Cmndr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 02, 2003 2:37 am
- Post datetime: 2003-09-01T18:47:51+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> To help you out, here's some C++ code to address the function:

Create a reftodll console application and write in reftodll.cpp


#include "stdafx.h"
// you may want to #include <basetsd.h> as well

int main(int argc, char* argv[])
{
  HRESULT  hr;
  CLSID    clsid ;
// Initialize an appointment
  CoInitialize(NULL);					

//obtain the Class id 
  CLSIDFromProgID(OLESTR("multiex.AMex3GetFileInfoClass"),&clsid); 

//Make RunMex the class of interest
  _AMex3GetFileInfoClass *RunMex; 

// Create the Class instance, if failure show a message
    if (CoCreateInstance(clsid, NULL, CLSCTX_INPROC_SERVER,__uuidof(_AMex3GetFileInfoClass), (void**) & RunMex) >= 0)
	{
// succes, tell user to press ok to start running 
		MessageBox(0, "Ok to run MultiEx", "", MB_OK);
// Run the Mex3GetFileInfo function, using the arguments
// hr is the resulting error number, 0 = no error
		hr = RunMex->Mex3GetFileInfo("big.bms", "english.big", "-p -l -lst mylist.lst");						
		if (hr > 0 )
		{
			MessageBox(0, "MultiEx returned an error", "", MB_OK);
		}
	}
	else
	{
		MessageBox(0, "Failed to address the DLL!", "", MB_OK);		}
// Destroy the appointment
	CoUninitialize();	

return 0;

}

In the StdAfx header you have write:
#import "multiex.dll"
using namespace multiex;

at the appropriate possition

There, that should do the trick. Compile everything and make sure you check the dependencies. 

The example expects multiex.dll in the project directory and a big.bms file 
for C&C: Generals BIG files , as well as the english.big file of the game in the app directory.

hi can this be used on any type of game and not just the games in your list?
cause I want to use this for AVP2 and PrimalHunt.
and I tryed to edit your code you posted on here to use it for avp2 and primalhunt.
and both those games use REZ files for the lithtech.exe server to register packets by.
and to generate edited version of the games modles and say if you wanted to added in all the weapons by using the avp2l.rez file you can and change the ammo as well for a modified rez file for multiplayer and single player modes.
but for multiplayer modes the other party has to have the same rez file as you to join a hosted server.
and avp2 and primalhunt due run of .dlls as well.
so it is sort like no one lives for ever games then again no one lives for ever game was created by lithtech company..
and I tryed using your MultiEx Commander and Mex3Scriptor too.
but when I tryed to get it to import the rez file avp2l.rez file it came up with an error and would not finish the process.
so I was wondering if you can help me with this or make the transcript for avp2 and primalhunt games??
and I did fallow your instruction for the dll to be in the directorie for the script I tryed to edit to use for avp2 and primalhunt and I added in the rest too.
and I got at least 32 errors.
## Post #39
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-09-02T17:55:43+00:00
- Post Title: 

Arjan zegt:
just reply:
"as you can see in [http://www.xentax.com/html/gameslist.html](http://www.xentax.com/html/gameslist.html) MultiEx only support NOLF extraction, not importation. Sorry d00d"

Edit:
Arjan zegt:
just reply:
"importation in NOLF (or related) games is not possible with MultiEx."
Arjan zegt:
*unfortunately not possible
Arjan zegt:
"as for extraction, it is only possible to extract wav files"
