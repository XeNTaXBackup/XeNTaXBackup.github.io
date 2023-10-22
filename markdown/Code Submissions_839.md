## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-03T17:01:05+00:00
- Post Title: Code Submissions

Mr Mouse,

how do you feel about code submissions, or another programmer on the project?
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-03T23:50:33+00:00
- Post Title: Code Submissions

I think he would probably feel like any "free software" programmer - we will accept anything and everything. 

Definately, if it is code for opening another archive format (a MexScript) then it definately needs to be shared - mostly because everyone has different games, so it simply isn't possible for us to get copies of every game that people are likely to want. 

If it is code relating to the MexCom program - I guess Mr Mouse will have to answer that one. I personally don't have too much of a problem with accepting code for my programs, but I would typically re-write some or all of the code to my own implementation, so it fits in with my way of thinking etc. I'm sure he wouldn't mind the assistance.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-04T07:07:27+00:00
- Post Title: Code Submissions

> Reply from Anonymous
>
> Mr Mouse,

how do you feel about code submissions, or another programmer on the project?

I welcome other programmers. I don't regard myself as much of a programmer anyway, so I welcome other more professional coders. 
Why, are you interested in joinging the project?

And as WATTO said, if it's MexScript we are talking about, the main purpose I use that script approach is to enable others to easily add new support. So, yeah, that should definitely be shared. Mind you, I have noticed a stupid bug slipped in during 3.9.70 -> 4.0.0 programming: if you open an archive using a custom script you will see the contents nicely (showing succesful progress), but you can't actually work with the file and extract stuff (it CRASHES OH...MY...GOD...!). Have to fix that in the new release.
## Post #4
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-04T07:38:37+00:00
- Post Title: Code Submissions

Actually, I was wondering about adding formats.  Maybe a little more the interface itself.  Most of the time, when i do a new archival format, I make a command line tool first, if anything.  I was thinking about adding Diablo/Diablo2 formats,  Ultima7, Ultima7pt2, Ultima 8.  I'd really like to get the code into something like this, which supports multiple formats, rather than a bunch of my own tools.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-04T07:44:17+00:00
- Post Title: Code Submissions

Well, adding new formats is always needed. How would you propose to add new formats then? Using MexScript? Or fixing MultiEx Commander to use command-line driven plugins? This is a tricky thing, and depends on the language you use to write the tools. But if you have a solid win32 .exe that will cough up a list of archive contents, that might be possible. You could also write DLLs to plugin MultiEx Commander. See the help file in the new release for details on that.
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-04T12:14:13+00:00
- Post Title: Code Submissions

The easiest way for you would be to write plugins for MexCom, if you have a c++ or VB programming background. Otherwise, it would probably be better to write a format script, or even post information about those formats and hopefully Mr Mouse or someone else will be able to convert it over to a script.

I know the diablo series would be great to have in programs like MexCom, because I believe they are very complicated to interpret, and at this stage only a few single programs can handle them.

Let us know what you can do - we are always greatful for any assistance.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-04T18:10:20+00:00
- Post Title: Code Submissions

Yeah, right now i'm trying to get a plugin to work.  For some reason, it shows it being loaded in the debug log, but when i do a Tools->View Detected Plugins, it doesn't show up.  

The diablo files are a little complicated, similiar to FLX files used by origin.  The difference is that A) Its encoded via a password and they can be different per file.  And B) Filenames aren't stored in the archive, they are stored in the executable, but the index is stored in the archive.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-04T18:40:48+00:00
- Post Title: Code Submissions

Okay, you could send me the (preliminary) code, perhaps I can see what went wrong.
## Post #9
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-04T20:49:07+00:00
- Post Title: Code Submissions

I'll figure it out, VB is a bit picky about things.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-04T21:28:27+00:00
- Post Title: Code Submissions

Ok, but there's something missing from the help file , so I noticed. 
You will need to include a function that will list the contents of the archive it processes.  

Public Function iList(strPath As String, iType As Integer, iStdList() As String) As Long

So:
- you give the path to the archive in strPath, 
- you provide the type of list it needs to return in iStdList(). 1 will be mostly used. 
- you return the contents in a list of strings
  This depends on the type you specify. MultiEx will expect type 1 and ask for type 1:

List of contents Type 1 (iStdList):

An array of strings:

iStdList(0) = Number of files (in string-form, will need to be "File not supported" if the provided path can't be processed by the plug-in)
iStdList(1) = path to the archive
iStdList(2) = the name of the plug-in and its version number

Then follow the actual entries, in sequential order.
the first would be :
iStdList(3) = Name of the resource in the archive (e.g. "textures\me.tga")
iStdList(4) = Size of the resource in the archive (will be the COMPRESSED size in case the resources are compressed)
iStdList(5) = Offset of the resource in the archive
iStdList(6) = Uncompressed size of the resource (this is 0 if there's no compression)
OPTIONAL iStdList(7) = % compression (compressed size/uncompressed size*100) NOTE that this will not be so in case of uncompressed files. 
In case of uncompressed files the next entry will begin at iStdList(7), in case of compression the next entry will begin at iStdList(8 ). 

I hope this is clear to you .
## Post #11
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-05T00:17:29+00:00
- Post Title: Code Submissions

Yes I saw that, you are missing quite a few functions actually, cuz i didn't see the bsIdentify(String)  or is it the bnIdentify(String).  I can't remember your exact naming conventions at the moment.
## Post #12
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-05T06:06:21+00:00
- Post Title: Code Submissions

Also good to know, Doom 3 uses ZIP file format for its main file formats.  PK4.  If you force windows to open the file in winzip, works perfectly.  But if you use a free zipping program 7-zip you can right click and say extract.

```
0000010: f0bd 1402 0000 dc0d 0000 0b00 0000 6465  ..............de
0000020: 662f 6161 732e 6465 66ed 965d 6fda 3014  f/aas.def..]o.0.
0000030: 86af 41e2 3f58 beef ea18 939a db76 43d3  ..A.?X.......vC.
0000040: b46a d37a d14b e404 43ac e503 39ce 4834  .j.z.K..C...9.H4
0000050: edbf cf4e e260 88d5 7557 a512 d139 08bd  ...N.`..uW...9..
0000060: 2f3e f109 8f4e 3c9b f25c 09d5 7ce4 5bc0  />...N<..\..|.[.
0000070: 58b9 56cd 9e97 e0f7 6c3a 81e6 6b00 27ed  X.V.....l:..k.'.
0000080: 05b5 4728 b432 76e4 6538 c873 475e ef2a  ..G(.2v.e8.sG^.*
0000090: 2637 82e5 834b 5c37 6379 5c45 5539 b80b  &7...K\7cy\EU9..

```


thats a small hex dump of pak000.pk4.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T07:02:09+00:00
- Post Title: Code Submissions

Ah good. Just like they did with Quake 3. 

About that missing function bnIdentify, sorry for that.   I must have left my brains in my other pants when I wrote that HELP file. This is a function that you pass an archive to and the DLL should check if the archive is supported or not.
## Post #14
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-05T08:04:35+00:00
- Post Title: Code Submissions

yeah, i checked out the CVS, it seemed faster that way, although, i don't see where you defined bnPlugInfo in the class.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T08:05:59+00:00
- Post Title: Code Submissions

Forget about the current state of the CVS, the latest version is not up there yet. I have had very limited time lately to actually update that.
## Post #16
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-05T08:54:21+00:00
- Post Title: 

Actually, I can see a room for improvement in the plugins.  For example, if you have multiple types of the same file, like in Diablo/Diablo2 they have the same roughly the same format, and you can use a lot of the same code, it would be nice to be able to use one plugin for multiple formats or multiple games. Like


bnGetExtensions() to get a list of extensions or 
bnGetExtensionCount() to get a count of supported ectensions

then

bnGetExtensionInfo(Index) to get the info for each Extension (Game name/support flags)

then when you extract or list, you pass in that index into the other functions like iList

Also, you might wanna put in versioning.  For example a function

bnSupported(Version), where mexcom passes in the version and the plugin lets it know if it'll work with that version.  That way mexcom can "skip" plugins not supported on upgrade.  This doesn't have to be the version of the mexcom, it could a version of the dll interface methods, this could also help mexcom support older plugins as the future goes on.
## Post #17
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-05T08:57:27+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Forget about the current state of the CVS, the latest version is not up there yet. I have had very limited time lately to actually update that.

BAH!... well thats not good
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T09:00:06+00:00
- Post Title: 

Your ideas are very valid. 

Would you care to work on such an implementation? I will update the CVS to the latest then.
## Post #19
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-05T09:14:09+00:00
- Post Title: 

I could work on it, if you want, even though I havent worked with VB in years.  My strong suits, at least in windows, C/C++ and Delphi.  Also, I have the problem of not owning VB6.  The closest I have VB.NET.  But what I could do, is convert it to VB.NET (cuz you have to  ) and then submit a code changes to you directly.  Man, I should sign up on your forum.
## Post #20
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-05T09:18:33+00:00
- Post Title: 

Ahhh this is better.  I feel less..... naked.
## Post #21
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T09:18:36+00:00
- Post Title: 

> Reply from Guest
>
> Man, I should sign up on your forum.

LOL. Yeah, would be advisable. 

There are ways to overcome the problem of not owning VB though. But yeah, you could always send the implementations directly. Especially if we'd create a separate plugin-handling class + module. Changes in there would never interfere with the rest of the code, as its...well..separate.
## Post #22
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-05T09:42:23+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> There are ways to overcome the problem of not owning VB though. But yeah, you could always send the implementations directly. Especially if we'd create a separate plugin-handling class + module. Changes in there would never interfere with the rest of the code, as its...well..separate.

Right, in fact, i'm writing the plugin right now, in Delphi.  Once I get that done I could port it over C/C++, so other developers can have a sample in the language they prefer.

Also, i would like to build, at least along side Mexcom, a command line tool, that can utilize the same files as the gui, for 2 reasons

1) It would be nice to write a batch(script) file to do batches for certain games, and it would be nice for MODer to have build scripts for their MODs.

2) It would make it easily portable to a unix/linux environment, where some games are actually are.

Let me know your take on that.
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T10:23:46+00:00
- Post Title: 

Well, a command-line tool might be possible, you do know that the actual processing of the scripts (listing contents) is done by multiex.dll. MultiEx Commander just uses multiex.dll to list archive content. It is fed MexScripts. MultiEx.dll coudl be called by such a command-line tool, but that would be problematic cross-platform wise. 

I own Delphi as well, so I can test your code in there. If you have the plugin, with the added functions you mention, then I will update the code in MultiEx Commander to use it. 

Please also note that my life is pretty busy, and I will not always have the time to work on it. If it is speed you are after, I won't be able to help. But I don't think you will need speed in this case. And besides, as it might be turned into a mutual project you could always adapt pieces of code yourself after I send you the latest source.
## Post #24
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-05T10:39:17+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Well, a command-line tool might be possible, you do know that the actual processing of the scripts (listing contents) is done by multiex.dll. MultiEx Commander just uses multiex.dll to list archive content. It is fed MexScripts. MultiEx.dll coudl be called by such a command-line tool, but that would be problematic cross-platform wise.

It would if the dll was turned into a shared library.  Most platforms have a shared library format now.

> Reply from Mr.Mouse
>
> I own Delphi as well, so I can test your code in there. If you have the plugin, with the added functions you mention, then I will update the code in MultiEx Commander to use it.

First I have to get mexcom to SEE it as a plugin 

> Reply from Mr.Mouse
>
> Please also note that my life is pretty busy, and I will not always have the time to work on it. If it is speed you are after, I won't be able to help. But I don't think you will need speed in this case. And besides, as it might be turned into a mutual project you could always adapt pieces of code yourself after I send you the latest source.

Understandable, as I'm busy myself with my own projects as well as work, this includes my own coding web site.  But I was thinking of it as a port of sorts, and everyone knows ports of a software never come out the same time as the original .  The shared library could also be a port.  The worse thing here is the ActiveX Plugins, only cuz those aren't portable.  Everything else could be easily portable.
## Post #25
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-06T18:04:03+00:00
- Post Title: 

Yeah, I'd really like to see the code you use to check for a plugin.
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-06T20:12:42+00:00
- Post Title: 

If everything is well, I'm updating the CVS as we speak. 

For now, here is the clean source code:
[mc401source.zip](https://xentaxbackup.github.io/file/49_mc401source.zip)
## Post #27
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-06T23:19:30+00:00
- Post Title: 

You rule
## Post #28
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T00:22:00+00:00
- Post Title: 

Ok i think i found the problem, in Module1.bas.

1) There has to be at least one entry in the MRF file for that file extension (will not create new file extensions,  ie Making a XXG directory without adding a an entry into the MRF will be ignored.)

2) Problems if the file extension is less than 3 characters.  If I add the Extension  "XX" into the MRF file, and then make a directory called "XX" the system will never see it as a plugin because you pad out the extension in the MRF file, but not the subdirectory.  Hence "XX" <> "XX ".

Also good to note, a lot of newer games, are using more than 3 character extensions.  This system might want to be upgraded.

I found this out, by putting my module in the PAK directory, and it loaded just fine.
## Post #29
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T00:33:50+00:00
- Post Title: 

Further Analysis

I saw "If t <= ExtFormats + 1 Then" which means that it attempts to load it.

This attempts to load it past the end of the format list, but the ExtFormats variable is never updated.  The plugin definition is there (I think, i can't remember if VB auto redims an array when you try assign past its boundary).

This ExtFormats is used later, and when loop from 0 to ExtFormats -1, you never get to the NEW entries.
## Post #30
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T08:51:22+00:00
- Post Title: 

Please feel free to adapt and, improve on, the code. It would help a lot if we could work together on this matter, see also my reply in the Painkiller thread.
## Post #31
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-07T10:36:42+00:00
- Post Title: 

Ok, heres my opinions.  I love how you made the multiex.dll as an activex, although I don't think i would have installed it in the Windows\System directory.  It allows other programs to use it like a scripting language and doesn't require its path to be known by the calling process.  Now, I think the plugin files should be much simplier, like a standard DLL, your implementation is just like a dll with a wrapper around the functions into an activex.  Although, activex is pretty easy for  VB(it takes some of the hardness out, but is very limiting to what it can do), but its a little more difficult for other language, that have to design the activex interfaces as well as the classes.  Also, you were saying that most of the functionality is in the multiex.dll, if we do it the way i described, it would be better to put the plugin functionality into the multiex.dll, this way other programs can use it, and the plugins, without having to know about them (black box theory).

Ok now onto the good stuff

Please bear with me, i wrote this up in 15 mins in Delphi (a stronger language i'm familar with)

```
function mpGetVersion(var Major, Minor: Integer): Boolean; stdcall;

function mpGetFormatCount(): Integer; stdcall;

type
  TFormatInfo = packed record
    // DLL Format 1.0
    FileMask: PChar;
    GameName: PChar;
    Flags: Int64;  // used for testing for what the archive can do
  end;
  // This format can be expanded on and supported based

function mpGetFormatInfo(Index: Integer; var FormatInfo: TFormatInfo): Boolean;

function mpGetCreateOptions(var CreateOptions: PChar): Boolean;

// This replaces

function mpFindFileFirst(ArchiveHandle: Integer; FilePath: PChar; var FindData: TFileFindInfo): Boolean;

function mpFindFileNext(var FindData: TFileFindInfo): Boolean;

function mpFindClose(var FindData: TFileFindInfo): Boolean;

function mpIsArchive(Index: Integer; Filename: PChar): Boolean;

function mpOpenArchive(var ArchiveHandle: Integer; FormatIndex: Integer; Filename: PChar; Flags: Cardinal; CreateOptions: PChar): Boolean;

function mpExtractFileByName(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean;
function mpExtractFileByIndex(ArchiveHandle: Integer; Index: Integer; ExternalFile: PChar): Boolean;

function mpImportFileByName(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean;
function mpImportFileByIndex(ArchiveHandle: Integer; Index: Integer; ExternalFile: PChar): Boolean;

function mpCloseArchive(ArchiveHandle: Integer): Boolean;

```


mpOpenArchive does opening of read only archives as well as creating new archive files if supported new archive files.

Normally the plugin will implement ByName or ByIndex but not both, ByName is for files that contain filename, ByIndex is for files that don't contain filenames but rather on position in the file, 1 for the first file 2 for the 2nd.... so on so forth..... Also when you import a file by index and pass a -1 as the index, it will append the archive with the file.

Let me know what you think of the idea, cuz there is no point in starting to write it, if we both don't agree on it.
## Post #32
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T10:44:02+00:00
- Post Title: 

GRRRRRRRRRRRRRRR!
## Post #33
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T15:31:47+00:00
- Post Title: 

Ok, so what you are saying would also affect multiex.dll in a major way. Now multiex.dll is "fed" binary mex scripts to process a given archive and it will return the list (in file form). Basically the interface (the function any program would call multiex.dll with) should only need a bit of changing. Multiex.dll should then check a standard directory for any plugins. 

I can dig your approach. You would need the latest multiex.dll source files to do that. The existing plugins (Painkiller.dll and sacrifice.dll) can be rewritten to adapt to your interface. 

I will update the CVS (as it failed yesterday) and then you will have the latest files on multiex.dll and the scriptor (which should work with the latest multiex.dll always!). 

If you wish you can then adapt the code to your plan of the new plugin approach. If you do, I will officially add you as coworker on Sourceforge. 

[EDIT] I have updated the CVS. It should have the latest source files for multiex.dll and the scriptor.
## Post #34
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T15:58:46+00:00
- Post Title: 

Question

multiex.dll is just a compiler right now?... input source, output binary?  or does it do the executing of binary also?

If its just a compiler, there is no sense in modifying it.  Another approach would to make a new DLL, One that is "similar" to an active x control, BUT exports the same functions as a plugin.  This "plugin" will actually be a semi filter, to you it would look like a plugin, but in fact, it would process the MEX scripts(MRF File) and the other plugins.

EI.

mpOpenArchive(5) is actually a MEX script, and uses the MEX script to open and process the archive.

mpOpenArchive(6) is actually a plugin, and instead of processing, it just "reroutes" the call to the plugin, and returns the plugin values.

Also, GetFormatCount() should return a count of all formats, (MEX or otherwise)

To do it this way, will remove most of the processing out of the main application, thereby turning the main application into a gui "interface" to the archiving module.

MainGUI -> mexrun.dll -> MEXScript
MainGUI -> mexrun.dll -> Plugin

Also, I'd like to change ExtractFile so that instead of taking JUST a file name, it will take wildcards.

ExtractFile(ArchiveHandle, '*.tga', 'C:\MyTGAs\')  should extract all TGAs to the directory C:\MyTGAs

ExtractFile(ArchiveHandle, '*.bin', 'C:\MyTGAs\*.tga') should extract all bin files from the archive and save them as TGAs on the C drive.

ImportFile should work roughly the same way.

I'll just need the binary encoding of the MEX script.

Note: This will also allow us to build a "test" suite for the DLLs or Plugins, that help keep bugs down.
## Post #35
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T16:00:42+00:00
- Post Title: 

Just to let you know, the mp i tack onto the begining of function names stands for MultiEx Plugin.
## Post #36
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T16:09:28+00:00
- Post Title: 

Multiex.dll takes a script that was "compiled" by MexScriptor to an array of function codes and variables. It "runs" through this array and performs the functions that the codes resemble. If the script uses the command "Log" this will be result in an entry in a list file, with multiex.dll saving the filename, the offset of this filename, the size of this filename, the offset of the offsetpointer, the offset of teh sizepointer). At the end the script should stop at which point multiex.dll is done. 

There's a little info in the source files about how this works, and what the format of a .BMS file is (multiex script compiled to an array of functions and variables). 

The nice feature of the plugin system at this point is that the plugin can tell MultiEx Commander what variables it will return, so that MultiEx COmmander can assign the appropriate number of columns in the interface to the user. This should be kept I think. Also, the plugin can tell MultiEx Commander what questions to ask the user (i.e. what settings the user should specify) prior creation of a new archive (e.g. compression or no compression, filenames or indexes, or whatever the format should be able to handle).
## Post #37
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T16:38:22+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Multiex.dll takes a script that was "compiled" by MexScriptor to an array of function codes and variables. It "runs" through this array and performs the functions that the codes resemble. If the script uses the command "Log" this will be result in an entry in a list file, with multiex.dll saving the filename, the offset of this filename, the size of this filename, the offset of the offsetpointer, the offset of teh sizepointer). At the end the script should stop at which point multiex.dll is done.

Ok its the VM... I just though of an idea, this fliter plugin could call the multiex.dll when it needs to do script access.  This will leave the MEX scripts still completely in your hands, the only thing, The Gui won't call the multiex.dll directly, but instead call the filter plugin.

> Reply from Mr.Mouse
>
> There's a little info in the source files about how this works, and what the format of a .BMS file is (multiex script compiled to an array of functions and variables).

Gotcha, but if we do what i suggested, then I wouldn't need to know the formats of the MEX script files.

> Reply from Mr.Mouse
>
> The nice feature of the plugin system at this point is that the plugin can tell MultiEx Commander what variables it will return, so that MultiEx COmmander can assign the appropriate number of columns in the interface to the user. This should be kept I think. Also, the plugin can tell MultiEx Commander what questions to ask the user (i.e. what settings the user should specify) prior creation of a new archive (e.g. compression or no compression, filenames or indexes, or whatever the format should be able to handle).

The format of the plugins still has this. 

function mpGetCreateOptions(var CreateOptions: PChar): Boolean;

which instead of returning it as an array, its returns it all in one string. Now, the filter plugin would be able to parse this back into an array for you IF you want.

Format of the string will be 

'<VARIABLE>:<TYPE>=<DESCRIPTION>;<VARIABLE>:<TYPE>=<DESCRIPTION>'

then in the OpenArchive for the CreateParams you do something similar

'<VARIABLE>=<VALUE>'

<VARIABLE> is the Variable name for create archive
<TYPE> is the variable type(ie  Integer/Filename/String/etc)
<DESCRIPTION> is what the user interface should tell the user in a popup or a help message
<VALUE> is what to set the variable to

Well, for the first, i did see that, but i wanted a while to "think" about it.  How about this

Actually I was just going to suggest a field in the FormatInfo data, but I have a better Idea

function mpGetFormatFields(FormatIndex: Integer; LanguageId: Integer; var Data: PWChar): Boolean;

This will allow 2 things.  Allow the plugin to hold information per format, but also allow the plugin to hold multiple languages, and the current language ID can be grabbed from the Locale and passed in.

Format of the string would be 

'<FIELD NAME>=<DISPLAY NAME>;'

Then I can modify FindFirstFile to accept a string of Field names
'<FIELD NAME>;<FIELD NAME>'
## Post #38
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T16:52:35+00:00
- Post Title: 

Some very good ideas indeed. I like that. 

Yes, we should have a filter that handles the "legacy" multiex.dll (passes stuff to it), it will be easy to adapt the GUI to call the filter/wrapper. You need not concern yourself with multiex.dll then.  

I also say we can worry about the GUI later. 

Priority should be having a working new method of plugins and legacy script. I can then (re)write parts of MultiEx Commander to start to work with the new system. You can tell me what the GUI should do and not do with your plugin interface, and I will work it out. 

Thus, that makes you in full charge of the Plugin Interface & Plugin Implementation, if you want that, along with any other cool ideas ou may have of coure.    I shall give you your place in the project at Sourceforge. Have you already registered there?
## Post #39
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T17:19:11+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Some very good ideas indeed. I like that. 

Yes, we should have a filter that handles the "legacy" multiex.dll (passes stuff to it), it will be easy to adapt the GUI to call the filter/wrapper. You need not concern yourself with multiex.dll then.

or i could write the filter plugin too, not a big issue

> Reply from Mr.Mouse
>
> I also say we can worry about the GUI later. 

Priority should be having a working new method of plugins and legacy script. I can then (re)write parts of MultiEx Commander to start to work with the new system. You can tell me what the GUI should do and not do with your plugin interface, and I will work it out.

sounds good to me

> Reply from Mr.Mouse
>
> Thus, that makes you in full charge of the Plugin Interface & Plugin Implementation, if you want that, along with any other cool ideas ou may have of coure.    I shall give you your place in the project at Sourceforge. Have you already registered there?

I have a login, but its been so long since i used it.  I wonder if its still there.  Let me get the plugin system actually built with a test suite.  And I'll resign up or get my old password
## Post #40
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T17:27:17+00:00
- Post Title: 

Ok Here is my Semi sample for a delphi plugin with YOUR plugin interface

project1.dpr

```

uses
  ComServ,
  Project1_TLB in 'Project1_TLB.pas',
  Unit1 in 'Unit1.pas' {Archive: CoClass};

exports
  DllGetClassObject,
  DllCanUnloadNow,
  DllRegisterServer,
  DllUnregisterServer;

{$R *.TLB}

{$R *.RES}

begin
end.
```


Unit1.pas

```

{$WARN SYMBOL_PLATFORM OFF}

interface

uses
  Windows, ActiveX, Classes, ComObj, Project1_TLB, StdVcl, SysUtils, Direct3D9;

type
  Tarchive = class(TAutoObject, Iarchive)
  protected
    function bnPlugInfo(var Info: OleVariant): OleVariant; stdcall;
    function bnIdentify(Filename: OleVariant): WordBool; stdcall;
    {Declare Iarchive methods here}
  end;

implementation

uses ComServ, Variants;

function Tarchive.bnPlugInfo(var Info: OleVariant): OleVariant;
var
  Info2: OleVariant;
begin
  Info2 := VarArrayCreate([0, 10], varOleStr);
  Info2[0] := 'This is my New Game';
  Info2[1] := '2';
  Info2[2] := '1.0';
  Info2[3] := '0';
  Info2[4] := '1';
  Info2[5] := '0';
  Info2[6] := '0';
  Info2[7] := '0';
  Info2[8] := '0';
  Info2[9] := '0';
  Info2[10] := 'Filename';
  Info := Info2;
end;

function Tarchive.bnIdentify(Filename: OleVariant): WordBool;
begin
  Result := False;
end;

initialization
  TAutoObjectFactory.Create(ComServer, Tarchive, Class_archive,
    ciMultiInstance, tmApartment);
end.
```


Project1_TLB.pas

```

// ************************************************************************ //
// WARNING                                                                    
// -------                                                                    
// The types declared in this file were generated from data read from a       
// Type Library. If this type library is explicitly or indirectly (via        
// another type library referring to this type library) re-imported, or the   
// 'Refresh' command of the Type Library Editor activated while editing the   
// Type Library, the contents of this file will be regenerated and all        
// manual modifications will be lost.                                         
// ************************************************************************ //

// PASTLWTR : 1.2
// File generated on 8/7/2004 11:19:04 AM from Type Library described below.

// ************************************************************************  //
// Type Lib: C:\Program Files\Borland\Delphi7\Projects\Auto\Project1.tlb (1)
// LIBID: {218D0DCD-767C-487E-8B97-CD9785F39F63}
// LCID: 0
// Helpfile: 
// HelpString: Project1 Library
// DepndLst: 
//   (1) v2.0 stdole, (C:\WINDOWS\System32\STDOLE2.TLB)
// ************************************************************************ //
{$TYPEDADDRESS OFF} // Unit must be compiled without type-checked pointers. 
{$WARN SYMBOL_PLATFORM OFF}
{$WRITEABLECONST ON}
{$VARPROPSETTER ON}
interface

uses Windows, ActiveX, Classes, Graphics, StdVCL, Variants;
  

// *********************************************************************//
// GUIDS declared in the TypeLibrary. Following prefixes are used:        
//   Type Libraries     : LIBID_xxxx                                      
//   CoClasses          : CLASS_xxxx                                      
//   DISPInterfaces     : DIID_xxxx                                       
//   Non-DISP interfaces: IID_xxxx                                        
// *********************************************************************//
const
  // TypeLibrary Major and minor versions
  Project1MajorVersion = 1;
  Project1MinorVersion = 0;

  LIBID_Project1: TGUID = '{218D0DCD-767C-487E-8B97-CD9785F39F63}';

  IID_IArchive: TGUID = '{174CFDA1-86D5-467B-BCE1-88D525FF0795}';
  CLASS_Archive: TGUID = '{4A61A49C-6659-49A3-8C4D-4E3F1BF72430}';
type

// *********************************************************************//
// Forward declaration of types defined in TypeLibrary                    
// *********************************************************************//
  IArchive = interface;

// *********************************************************************//
// Declaration of CoClasses defined in Type Library                       
// (NOTE: Here we map each CoClass to its Default Interface)              
// *********************************************************************//
  Archive = IArchive;


// *********************************************************************//
// Declaration of structures, unions and aliases.                         
// *********************************************************************//
  POleVariant1 = ^OleVariant; {*}
  PHResult1 = ^HResult; {*}


// *********************************************************************//
// Interface: IArchive
// Flags:     (4352) OleAutomation Dispatchable
// GUID:      {174CFDA1-86D5-467B-BCE1-88D525FF0795}
// *********************************************************************//
  IArchive = interface(IDispatch)
    ['{174CFDA1-86D5-467B-BCE1-88D525FF0795}']
    function bnPlugInfo(var Info: OleVariant): OleVariant; stdcall;
    function bnIdentify(Filename: OleVariant): WordBool; stdcall;
  end;

// *********************************************************************//
// The Class CoArchive provides a Create and CreateRemote method to          
// create instances of the default interface IArchive exposed by              
// the CoClass Archive. The functions are intended to be used by             
// clients wishing to automate the CoClass objects exposed by the         
// server of this typelibrary.                                            
// *********************************************************************//
  CoArchive = class
    class function Create: IArchive;
    class function CreateRemote(const MachineName: string): IArchive;
  end;

implementation

uses ComObj;

class function CoArchive.Create: IArchive;
begin
  Result := CreateComObject(CLASS_Archive) as IArchive;
end;

class function CoArchive.CreateRemote(const MachineName: string): IArchive;
begin
  Result := CreateRemoteComObject(MachineName, CLASS_Archive) as IArchive;
end;

end.
```


Although, this isn't a very USABLE plugin, it will be seen by MultiEx Commander and executed properly.
## Post #41
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T17:36:18+00:00
- Post Title: 

Bug fix for the current plugin system

```
Dim LD, t, t2, SubFolder, File
Dim f As Folder
Dim D, E
Dim handle
'f.path
DebugLog "-Main : Mex_FindPlugins"


Set D = New FileSystemObject
Set E = New FileSystemObject
On Error Resume Next
Set f = D.GetFolder(MainPath)
Set f = D.GetFolder(MainPath & "\" & MultiExPlugInPath)
On Error GoTo 0

If f.path <> MainPath Then

DebugLog "-Main : Mex_FindPlugins->Searching"

LD = 1
While LD <= f.SubFolders.Count

t = 0
For Each SubFolder In f.SubFolders
Dim ts, nu
ts = SubFolder.Name

'RAHLY 3 Lines
If Len(ts) < 3 then
  ts = Pad(ts,3)
End If

t = 0
While formats(t).Extension <> UCase(ts) And t <= ExtFormats
t = t + 1
Wend
If t <= ExtFormats + 1 Then
nu = formats(t).Number

nu = nu + SubFolder.Files.Count

ReDim Preserve formats(t).Games(nu)

formats(t).Number = nu
t2 = 1
For Each File In SubFolder.Files
formats(t).Games(nu - t2).Execute = "PGN"
formats(t).Games(nu - t2).FPath = File.path
formats(t).Games(nu - t2).GameName = E.GetBaseName(File.Name)
'handle = LoadLibrary(formats(t).Games(nu - t2).FPath)
DebugLog "-Main : Mex_FindPlugins->" & _
formats(t).Games(nu - t2).Execute & " at " & _
RTrim(formats(t).Games(nu - t2).FPath) & " for " & _
RTrim(formats(t).Games(nu - t2).GameName)
TotalForm = TotalForm + 1

' Rahly 3 Lines  Note: This will only work if VB6 doesn't need to
'   ReDim the "formats" variable
If T > ExtFormats then
  ExtFormats = ExtFormats + 1
End If

'ReDim Preserve Extfilter



'Dim FP

'FP = GetProcAddress(handle, "DllGetClassObject")
t2 = t2 + 1
Next
End If



t = t + 1
Next

LD = LD + 1
Wend
ReDim Preserve FExt(TotalForm)
ReDim Preserve FilterExt(TotalForm)
Else
DebugLog "-Main : Mex_FindPlugins->None found"
End If
'End If



End Function
```


Look for Rahly in the code, for code changes, and make sure they are in the newest version
## Post #42
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T18:44:52+00:00
- Post Title: 

Also, I'd like to request a change, it may have some problems with your currently implemented system, but hear me out.

Instead of the plugin registering an extension, I was thinking of registering as a "file mask"

Instead of saying "EXT"  you would say "*.arch" or "*.PK?" meaning any file with an extentions of arch or... any extension with a PK<something>.

This would almost infinitely expand setting a file extension to a game. or if you think thats a little too much

"arch"  and "PK?"  without the beginning *., but still allow wildcards in the extension.
## Post #43
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T19:02:53+00:00
- Post Title: 

Yes, we need that. 

One thing though, you are working NOT with the latest code, apparently, because you made changes in my old plugin detection code. 

Here is the current code for it, I think it does not have that problem you described earlier. 

> Public Function Mex_FindPlugIns() As Long
>
> Dim LD, t, t2, SubFolder, File
>
> 'Dim f As Folder
>
> Dim handle
>
> Dim cFiles As New colFiles
>
> 
>
> DebugLog "-Main : Mex_FindPlugins"
>
> 
>
> 
>
> 
>
> On Error Resume Next
>
> 
>
> cFiles.Clear
>
> cFiles.LoadFiles MainPath & "\" & MultiExPlugInPath & "*.dll", True
>
> On Error GoTo 0
>
> 
>
> If cFiles.Count > 0 Then
>
> 
>
> DebugLog "-Main : Mex_FindPlugins->Searching"
>
> 
>
> 'LD = 1
>
> 'While LD <= f.SubFolders.Count
>
> Dim t3, D
>
> t = 0
>
> 
>
> For t3 = 1 To cFiles.Count
>
> Dim ts, nu
>
> D = Len(MainPath & "\" & MultiExPlugInPath)
>
> ts = Right(cFiles.Item(t3).sFilename, Len(cFiles.Item(t3).sFilename) - (D))
>
> ts = MexGetParentFolderName(ts)
>
> 
>
> t = 0
>
> While formats(t).Extension <> UCase(ts) And t <= ExtFormats
>
> t = t + 1
>
> Wend
>
> If t <= ExtFormats + 1 Then
>
> nu = formats(t).Number
>
> 
>
> nu = nu + 1
>
> 
>
> ReDim Preserve formats(t).Games(nu - 1)
>
> 
>
> formats(t).Number = nu
>
> t2 = 1
>
> 
>
> 'If MexGetExtensionName(cFiles.Item(t3).sFilename) = "dll" Then
>
> 
>
> 
>
> formats(t).Games(nu - t2).Execute = "PGN"
>
> formats(t).Games(nu - t2).FPath = cFiles.Item(t3).sFilename
>
> formats(t).Games(nu - t2).GameName = MexGetBaseName(cFiles.Item(t3).sFilename)
>
> 'handle = LoadLibrary(formats(t).Games(nu - t2).FPath)
>
> DebugLog "-Main : Mex_FindPlugins->" & _
>
> formats(t).Games(nu - t2).Execute & " at " & _
>
> RTrim(formats(t).Games(nu - t2).FPath) & " for " & _
>
> RTrim(formats(t).Games(nu - t2).GameName)
>
> TotalForm = TotalForm + 1
>
> 
>
> 'End If
>
> 
>
> End If
>
> 
>
> 
>
> 
>
> t = t + 1
>
> Next t3
>
> 
>
> 'LD = LD + 1
>
> 'Wend
>
> ReDim Preserve FExt(TotalForm)
>
> ReDim Preserve FilterExt(TotalForm)
>
> Else
>
> DebugLog "-Main : Mex_FindPlugins->None found"
>
> End If
>
> 'End If
>
> 
>
> 
>
> 
>
> End Function
## Post #44
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T19:14:16+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Yes, we need that. 

One thing though, you are working NOT with the latest code, apparently, because you made changes in my old plugin detection code. 

Here is the current code for it, I think it does not have that problem you described earlier. 
Code: Select allPublic Function Mex_FindPlugIns() As Long
Dim LD, t, t2, SubFolder, File
'Dim f As Folder
Dim handle
Dim cFiles As New colFiles

DebugLog "-Main : Mex_FindPlugins"



On Error Resume Next

cFiles.Clear
cFiles.LoadFiles MainPath & "" & MultiExPlugInPath & "*.dll", True
On Error GoTo 0

If cFiles.Count > 0 Then

DebugLog "-Main : Mex_FindPlugins->Searching"

'LD = 1
'While LD <= f.SubFolders.Count
Dim t3, D
t = 0

For t3 = 1 To cFiles.Count
Dim ts, nu

'This might be fixed
D = Len(MainPath & "" & MultiExPlugInPath)
ts = Right(cFiles.Item(t3).sFilename, Len(cFiles.Item(t3).sFilename) - (D))
ts = MexGetParentFolderName(ts)

t = 0
While formats(t).Extension <> UCase(ts) And t <= ExtFormats
t = t + 1
Wend
'Still not fixed here
If t <= ExtFormats + 1 Then
nu = formats(t).Number

nu = nu + 1

ReDim Preserve formats(t).Games(nu - 1)

formats(t).Number = nu
t2 = 1

'If MexGetExtensionName(cFiles.Item(t3).sFilename) = "dll" Then


formats(t).Games(nu - t2).Execute = "PGN"
formats(t).Games(nu - t2).FPath = cFiles.Item(t3).sFilename
formats(t).Games(nu - t2).GameName = MexGetBaseName(cFiles.Item(t3).sFilename)
'handle = LoadLibrary(formats(t).Games(nu - t2).FPath)
DebugLog "-Main : Mex_FindPlugins->" & _
formats(t).Games(nu - t2).Execute & " at " & _
RTrim(formats(t).Games(nu - t2).FPath) & " for " & _
RTrim(formats(t).Games(nu - t2).GameName)
TotalForm = TotalForm + 1

' Rahly 3 Lines  Note: This will only work if VB6 doesn't need to 
'   ReDim the "formats" variable 
If T > ExtFormats then 
  ExtFormats = ExtFormats + 1 
End If 


'End If

End If



t = t + 1
Next t3

'LD = LD + 1
'Wend
ReDim Preserve FExt(TotalForm)
ReDim Preserve FilterExt(TotalForm)
Else
DebugLog "-Main : Mex_FindPlugins->None found"
End If
'End If



End Function

There were 2 problems, and they are both present in the version of MultiEx that i have, 4.0.1 ? Look at "TotalForm = TotalForm + 1"

And About the FileMask, I didn't know what was involved in the MEX scripts. So I wanted to ask.
## Post #45
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T19:23:43+00:00
- Post Title: 

Good, I used that last code bit and it ran. 
I will take a look at it in the future. 

As for the filemasks, yes, I think we should do that. I will see that I fix the system in the Commander so that it will regiter as that. I think I will need a new way of handling the different formats supported, perhaps. Or at least just for the plugins anyway. I think it won't be too much trouble. 

I don't readily see the benefit of "*.arch?" over "arch?", so I think the "arch?" approach will do nicely for the plugins. Perhaps I need to fix that stuff also for the script-processed formats, but that will require a bit more work, as the ScriptBinder (MexBinder) needs to be fixed for that as well.
## Post #46
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T19:28:50+00:00
- Post Title: 

Bloody hell, I see what you mean. If the plugin would support an extension that is not yet supported, it would not register it. SILLY SILLY ME!!!!! OMG I'm so STUPID sometimes.   

I clearly used the if statement for the purpose of CREATING a new extension if it was not supported yet, I must have simply forgotten after I tested some code. "Ah it works, let's move on to a new, more important function" Damn.  

[EDIT]Okay, I will fix that, the way you proposed would be nice, but it won't work like that. I will do it immediately after it turns out that an extension is not yet in the current base of the Commander.
## Post #47
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T19:37:53+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> I don't readily see the benefit of "*.arch?" over "arch?", so I think the "arch?" approach will do nicely for the plugins. Perhaps I need to fix that stuff also for the script-processed formats, but that will require a bit more work, as the ScriptBinder (MexBinder) needs to be fixed for that as well.

The benefit is for something in the future, like ntfs supports.

"*.gfx.arch?" "*.script.arch?" may be the same type of archive, but you might wanna add support for preview. or maybe "*.gfx.arch?" isn't compressed but the "*.script.arch?" is compressed, but there are no "flags" in the file to indicate it, so you have to treat them as seperate archives.

Sorry, prolly not the BEST of examples, but an example, nonetheless.
## Post #48
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T19:41:03+00:00
- Post Title: 

> Reply from Rahly
>
> Mr.Mouse wrote:I don't readily see the benefit of "*.arch?" over "arch?", so I think the "arch?" approach will do nicely for the plugins. Perhaps I need to fix that stuff also for the script-processed formats, but that will require a bit more work, as the ScriptBinder (MexBinder) needs to be fixed for that as well.

The benefit is for something in the future, like ntfs supports.

"*.gfx.arch?" "*.script.arch?" may be the same type of archive, but you might wanna add support for preview. or maybe "*.gfx.arch?" isn't compressed but the "*.script.arch?" is compressed, but there are no "flags" in the file to indicate it, so you have to treat them as seperate archives.

Sorry, prolly not the BEST of examples, but an example, nonetheless.

Ok point taken.
## Post #49
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T19:43:45+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Okay, I will fix that, the way you proposed would be nice, but it won't work like that. I will do it immediately after it turns out that an extension is not yet in the current base of the Commander.

So you do have to redim it  I thought so, i wasnt sure if they changed that since my VB4 days.

[EDIT]There are too many languages that DO work that way now, perl and php are just 2 examples.  I still do a lot of work in perl.
## Post #50
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-08T09:12:14+00:00
- Post Title: 

Ok, removed mpGetCreateOptions() function and replaced it with

mpGetOptions(FormatIndex: Integer; OptionType: Integer; Options: PChar): Boolean;

This allows plugins to provide Export/Import options as well, like, if they wanna convert one of the files in it, from a proprietary format, to a more standard format, or one that works with an application.
## Post #51
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-08T21:49:10+00:00
- Post Title: 

Okay, but the plugin will also need to convert them back to the one the format uses when they import, else the game will mostlikely fail to use the (new) resource. 

On another note, also directed to WATTO, I'm working at the background (in free, free time) on a little app that will focus on identifying parts of formats in newly encountered archives. The most easy example would be, say, WAV files. Suppose an archive contains Microsoft Wave files, then you would find a string like "RIFF", exposing the beginning of the file in the archive. This offset might be found somewhere else in the file (as part of a header or tail). Now, you could also specify that the FileID entry has also a size variable (whcih the RIFFs have for instance) at at what distance from the start of the file it can be found, what type it is etc. ). That way you could also possibly find a Size variable somewhere in the archive in a header or tail. You see where this leads, and I think it is just an expansion what your basic Ripper would do, however, it would also try to MAP a header or tail. The possibilities are there I think to create a custom extractor, that users could try and run on an archive they encountered, and if the analysis of the tool would be succesful, they could at least extract stuff from it. The tool could create a text file that users might want to send to us, so we can have already some idea of the format before we delve into it with a hex editor. But most of all, it would help out users that want to get something out of non-supported formats. 
What do you think?
## Post #52
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-09T00:30:36+00:00
- Post Title: 

> On another note, also directed to WATTO, I'm working at the background (in free, free time) on a little app that will focus on identifying parts of formats in newly encountered archives. The most easy example would be, say, WAV files. Suppose an archive contains Microsoft Wave files, then you would find a string like "RIFF", exposing the beginning of the file in the archive. This offset might be found somewhere else in the file (as part of a header or tail). Now, you could also specify that the FileID entry has also a size variable (whcih the RIFFs have for instance) at at what distance from the start of the file it can be found, what type it is etc. ). That way you could also possibly find a Size variable somewhere in the archive in a header or tail. You see where this leads, and I think it is just an expansion what your basic Ripper would do, however, it would also try to MAP a header or tail. The possibilities are there I think to create a custom extractor, that users could try and run on an archive they encountered, and if the analysis of the tool would be succesful, they could at least extract stuff from it. The tool could create a text file that users might want to send to us, so we can have already some idea of the format before we delve into it with a hex editor. But most of all, it would help out users that want to get something out of non-supported formats. 
>
> What do you think?

Mr Mouse,

Yes, this sounds like a good idea, and I myself have contemplated creating a program like this before, however i think it would be quite painful to accomplish.

Firstly, we would need to fully understand that the program is developed for non-experienced users - not us programmers - because face it, we already know how to read archives . With this in mind, we would have to cram as much as possible into the program, but still keep it rather simple to use.

Secondly, we would need to program it to recognise as many different archive formats as possible

Thirdly, we would need to have the program recognise as many different header types as possible, so we may need to research this alittle.

I think this is a great idea, but alot of work. I would be happy to help out with the program, assuming it is in Java, VB, or to a lesser degree, .Net/C#/J# etc.

Sorry for sounding alittle down about it, I do think it would be a great tool to have!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #53
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T05:48:52+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Okay, but the plugin will also need to convert them back to the one the format uses when they import, else the game will mostlikely fail to use the (new) resource.

Thats up to the plugin designer.

> Reply from Mr.Mouse
>
> On another note, also directed to WATTO, I'm working at the background (in free, free time) on a little app that will focus on identifying parts of formats in newly encountered archives. The most easy example would be, say, WAV files. Suppose an archive contains Microsoft Wave files, then you would find a string like "RIFF", exposing the beginning of the file in the archive. This offset might be found somewhere else in the file (as part of a header or tail). Now, you could also specify that the FileID entry has also a size variable (whcih the RIFFs have for instance) at at what distance from the start of the file it can be found, what type it is etc. ). That way you could also possibly find a Size variable somewhere in the archive in a header or tail. You see where this leads, and I think it is just an expansion what your basic Ripper would do, however, it would also try to MAP a header or tail. The possibilities are there I think to create a custom extractor, that users could try and run on an archive they encountered, and if the analysis of the tool would be succesful, they could at least extract stuff from it. The tool could create a text file that users might want to send to us, so we can have already some idea of the format before we delve into it with a hex editor. But most of all, it would help out users that want to get something out of non-supported formats. 
What do you think?

Sorry, I know you were talking to Watto, but..... 

It sounds like a great idea, as long as file is still in raw format (not encrypted/compressed).  It sounds almost like your trying to recreate the unix command "file".  The only difference, is file, only works on the original file position, you want it to go through the entire file. ie  "file bob.avi" -> "RIFF Video File"   "file bob.wav" -> "Riff Audio Wave PCM file"
## Post #54
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-09T06:43:17+00:00
- Post Title: 

> Reply from friendsofwatto
>
> 
Firstly, we would need to fully understand that the program is developed for non-experienced users - not us programmers - because face it, we already know how to read archives . With this in mind, we would have to cram as much as possible into the program, but still keep it rather simple to use.

Yes. It should have a Wizardish kind of feel. 

> Secondly, we would need to program it to recognise as many different archive formats as possible
>
> 
>
> Thirdly, we would need to have the program recognise as many different header types as possible, so we may need to research this alittle.

Yes, we need to do research on this. Not in the least, we should define a way the program would need to be coded, and how we should be able to easily "Feed" it new formats/header types/fileids etc. 

As an example, and a very early prototype, here's my Mexscan I talked about:
[http://www.xentax.com/downloads/oldcode ... exscan.zip](http://www.xentax.com/downloads/oldcode/mr.mouse/Mexscan.zip)
This little dos app takes script commands to do some of the work our new program should also be able to do. Please read it's docs for more. 

> I think this is a great idea, but alot of work. I would be happy to help out with the program, assuming it is in Java, VB, or to a lesser degree, .Net/C#/J# etc.

That would be great! We could even start a whole new open source project for it. I already have a new name for it: Eureka, although that may sound a little corny...  

> Sorry for sounding alittle down about it, I do think it would be a great tool to have!

I don't think you are sounding down about it! 
Before we decide who codes what in what we'd best define first how the program should operate in my opinion. Gives us a proper way to start. 

> Reply from Rahly
>
> 
Sorry, I know you were talking to Watto, but..... 

It sounds like a great idea, as long as file is still in raw format (not encrypted/compressed). It sounds almost like your trying to recreate the unix command "file". The only difference, is file, only works on the original file position, you want it to go through the entire file. ie "file bob.avi" -> "RIFF Video File" "file bob.wav" -> "Riff Audio Wave PCM file"

I was talking also to you!   

Anyway, yes, compressed/encrypted resources in an archive might be problematic, but if you have identified a header or tail to belong to a specific type of format (one that you know uses a certain compression) you would not need to identify the compression from the compressed file. Even the latter may be accomplished for some compression formats. 

I want it to go through the file, looking for a match of header patterns, meanwhile looking for file signatures etc, as part of Phase 1. In Phase 2, when it has not identified the archive yet, it should go through the whole archive again and try to find somewhere the offsets and sizes (as variables) of the found signatures, i.e. Phase 2 would be the actual mapping of regions where directory structures reside.
## Post #55
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T07:15:11+00:00
- Post Title: 

Well, since we are working on the plugin system to MultiEx.  I had another thought, this would make plugins even more generic, and possible to use in your new program.

Instead of passing filenames for the plugin to use, i was thinking of passing IStream's to it, this way, IStreams can point to a file, memory, or even a TCP/IP socket.  This will allow the plugins to be used in multiple a variety of projects.

```

function mpIsArchive(MyStream: IStream): boolean;
```


mpIsArchive tests for archive validity.  RIFF files could be a plugin also, since its an archive of "streams".  Also, with the new plugin system, you can define weither or not it can be tested, so you could say "riff" files can't extract, can't import, but can be tested for (has mpIsArchive).  Then only use the plugins that have the option of "SUPPORTFLAG_CANTESTFOR".

[EDIT] [http://msdn.microsoft.com/library/defau ... stream.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/stg/stg/istream.asp) [/EDIT]
## Post #56
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-09T09:11:59+00:00
- Post Title: 

> Reply from Rahly
>
> Well, since we are working on the plugin system to MultiEx.  I had another thought, this would make plugins even more generic, and possible to use in your new program.

Instead of passing filenames for the plugin to use, i was thinking of passing IStream's to it, this way, IStreams can point to a file, memory, or even a TCP/IP socket.  This will allow the plugins to be used in multiple a variety of projects.
Code: Select allfunction mpOpenArchiveBindStream(var ArchiveHandle: Integer; MyStream: IStream): Boolean;

function mpIsArchive(MyStream: IStream): boolean;

mpIsArchive tests for archive validity.  RIFF files could be a plugin also, since its an archive of "streams".  Also, with the new plugin system, you can define weither or not it can be tested, so you could say "riff" files can't extract, can't import, but can be tested for (has mpIsArchive).  Then only use the plugins that have the option of "SUPPORTFLAG_CANTESTFOR".

[EDIT] http://msdn.microsoft.com/library/defau ... stream.asp [/EDIT]

I can see you clearly have a good way of thinking! You must do this stuff for some time now! Professionally maybe? What do you do for a living?

These Istreams would have to be declared in MultiEx Commander as well then. How would this work out? Suppose I wish to open an archive (say .MyArch) and retrieve a resource from it (say MyFile.res), how would the commander procede?
## Post #57
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T09:41:47+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> I can see you clearly have a good way of thinking! You must do this stuff for some time now! Professionally maybe? What do you do for a living?

Coding and Electrical Engineering, I like to think i have good logical skills as well as good problem solving skills.  Unfortunately, having developed these skills, leaves me lacking in creativity skills(art, drawing, design).  My last job was solely creating development tools for the developers .

> Reply from Mr.Mouse
>
> These Istreams would have to be declared in MultiEx Commander as well then. How would this work out? Suppose I wish to open an archive (say .MyArch) and retrieve a resource from it (say MyFile.res), how would the commander procede?

It does HAVE to have it, only if it plans to use these functions.  The way I had it planed out is, that I'll have One activex Plugin tool that you call, and it will handle the calls to all the other plugins for you.  I have since found out VB cannot call functions out of normal dlls , at least dynamically.  Statically, YES, but dynamically, no, you have to use a com/activex object.  So I'll write an activex plugin manager, so that you can import that into. And Since, multiex commander won't call those functions (it will use the original methods (send filename)), it doesn't need to define IStream, but is available if we do plan to change multiex commander later.  But your "scan" program would have to define it, look at the MS web site i posted, maybe you can gleam info on it from there.  I'm DEFINATELY not familiar with importing Interfaces into VB.

This IStream GUID is {0000000C-0000-0000-C000-000000000046} if you need it.  Fortunately Delphi already has it defined in the ActiveX module.  I like to think of Delphi as "VB with power" as the syntax is as easy and nice as VB, but you get the power of C++.  Just a personal preference, but unfortunately not a lot of companies use it, because its not marketed like MS markets tools.   One of my projects is a new compiler plugin for Delphi, to add some features I would like it to have. MACROs  also some new function types "constinconstout" and "compiletime".  constinconstout tells the compiler that if constants are passed in, constants are passed out, and if the compiler sees that function with all constants, it executes it at compile time, and returns it as a constant, which if it can, can be further parsed down.  Also, allowing for PIC (Position Independant Code) so that when you import a unit and you only use one function, you only import that function(and anything it uses).  Also a couple of nuisances that piss me off when coding .

I really want macros to do something like this

```
{$MACRO AllocateMem(s) Track_GetMem(s, __FILE__, __LINE__)};
{$ELSE}
{$MACRO AllocateMem(s) GetMem(s)}
{$ENDIF}
```


this way a programmer can type   AllocateMem and whereever it does that the compiler will insert the filename and the line number.  That way when you, say debug your memory, and there was a place you didn't free the memory, you can find out the File and line number that you created the memory, but didn't free it.

You know, simple things like that, that people need. Right now, you'd have to pass the filename and line number everytime you did it, which is kind of a pain for a programmer.

[EDIT]what i'd really like to do is. is make the activex plugin manager, export functions as well as an activex control, this way, you can use either.[/EDIT]
## Post #58
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-09T10:17:17+00:00
- Post Title: 

Rahly, you got me all excited.   Love this stuff. Yeah, you can't use function from non-ActiveX dlls in VB, a TRUE and UTTER pain. you have to declare them statically, which limits you no end.   

Another stupid thing (among may in VB) is the lack of unsigned variables, the lack of simple things like bitwise shift-left etc. and the lack of using some inline assembly whenever wanted.   of course it has advantages, one being simplicity, but I have had to do a lot of additional coding in C++ for other VB projects, writing a support-program that could actually do stuff that was impossible in VB. 

Rewriting all of the Commander in Delphi/C++ would be too much of a pain, so I appreciate you creating an ActiveX plugin-interface. 

Even Pascal could handle inline assembly, come to think of it. And Commodore 64 BASIC let you load up assembly routines at certain memory locations, by letting you POKE DATA at these locations.
## Post #59
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T16:10:34+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Rahly, you got me all excited.   Love this stuff. Yeah, you can't use function from non-ActiveX dlls in VB, a TRUE and UTTER pain. you have to declare them statically, which limits you no end.

LOL, i got you.. excited.  ~wonders if he should be scared~

> Reply from Mr.Mouse
>
> Another stupid thing (among may in VB) is the lack of unsigned variables, the lack of simple things like bitwise shift-left etc. and the lack of using some inline assembly whenever wanted.   of course it has advantages, one being simplicity, but I have had to do a lot of additional coding in C++ for other VB projects, writing a support-program that could actually do stuff that was impossible in VB. 

Rewriting all of the Commander in Delphi/C++ would be too much of a pain, so I appreciate you creating an ActiveX plugin-interface.

Actually it would be a "hybred" providing the original interface, which makes it easy for C++/Delphi to use.  Come to think of it, I don't HAVE to make it an activex plugin interface, because you CAN link to static functions, which WILL be in the plugin interface, although, I might just make it an activex just for simplicity sakes.  But its best we get all these ideas out NOW, that way we can be really fullied featured for the first version.  Now, here is how the plugin system I think will work.  Let me know if you think anything is out of order, or something.

Ok, multiex commander includes the MultiexPluginManager DLL, either through static methods or an activex control.  After this connects, the DLL will go through the plugin directory (either a cfg file, or a registry entry) and attempt to load each plugin.  First it attempts to loads the plugin dll as a C++/Delphi with static functions WINAPI standard calling convention.  If valid (adds it to the list of valid plugins).  If not valid, checks for the DLLGetClassObject, if its there it will attempt to register it if needed, and then try to load it at an activex object. (the purpose of this is, so you can write easy C++/Delphi(Static function) plugins and easy VB(activex) plugins.  So we are not limiting anyone from making plugins, although, i think VB.NET can make proper dlls.

Also, a suggesting, I was thinking of renaming dlls to a different extension, i'm thinking of maybe  "MXP" for MultieX Plugin.

I think I'll have a version of the static plugin up here in a few hours.  So let me know what you think, i'll have to include the IStream idea in though.

> Reply from Mr.Mouse
>
> Even Pascal could handle inline assembly, come to think of it. And Commodore 64 BASIC let you load up assembly routines at certain memory locations, by letting you POKE DATA at these locations.

Yeah I remember that, it took me a whole year after I loaded this one program to figure out what "00010 SYS 8510" meant.  Course, I was 9 at the time.  My first real program was a single player RPG typing game when i was 8 .  Written in C64 Basic.  And then it wasn't till i was 11 that i found the almight book C64 6510 Programming Reference.  I never really liked the C128.  I had an Amiga 2000 at one time, and i was so geeked about 4096 colors.  ~drooled~  The only thing i wanted more was the Video Toaster.  It took forever for the PC market to get more than 256.  One of the things I did love, was that all of Babylon 5's graphics were done on an Amiga.  When I read that, i was like .... hell yeah... amiga was soooo ahead of its time.... too bad it had such poor marketing.  I think it would have been more popular than the PC, and would have soared.

[EDIT]I have some "fair" ability in debuging programs with no source ~cough~  [/EDIT]
## Post #60
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T16:55:41+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Another stupid thing (among may in VB) is the lack of unsigned variables, the lack of simple things like bitwise shift-left etc. and the lack of using some inline assembly whenever wanted.

Actually, if you declare the variable as a long or an integer type

doing

X := X * 2  (converts to a shl 1)
X := X / 2  (converts to a shr 1)

if you do

X := X * (2^A) (converts to a shl A)
X := X / (2^A) (converts to a shr A)

at least, delphi is smart enough to do that.

Although, i donno what VB does for this.
## Post #61
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-09T21:23:13+00:00
- Post Title: 

> Reply from Rahly
>
> Ok, multiex commander includes the MultiexPluginManager DLL, either through static methods or an activex control.  After this connects, the DLL will go through the plugin directory (either a cfg file, or a registry entry) and attempt to load each plugin.  First it attempts to loads the plugin dll as a C++/Delphi with static functions WINAPI standard calling convention.  If valid (adds it to the list of valid plugins).  If not valid, checks for the DLLGetClassObject, if its there it will attempt to register it if needed, and then try to load it at an activex object. (the purpose of this is, so you can write easy C++/Delphi(Static function) plugins and easy VB(activex) plugins.  So we are not limiting anyone from making plugins, although, i think VB.NET can make proper dlls.

Also, a suggesting, I was thinking of renaming dlls to a different extension, i'm thinking of maybe  "MXP" for MultieX Plugin.

Okay, I got it. Sounds like the way too go, you obviously have much more experience in the coding department (I'm just a molecular geneticist), but I can follow it and like it. 

About the renaming of the dlls, MXP it is then. 


> Reply from Rahly
>
> And then it wasn't till i was 11 that i found the almight book C64 6510 Programming Reference.  I never really liked the C128.  I had an Amiga 2000 at one time, and i was so geeked about 4096 colors.  ~drooled~  The only thing i wanted more was the Video Toaster.  It took forever for the PC market to get more than 256.  One of the things I did love, was that all of Babylon 5's graphics were done on an Amiga.  When I read that, i was like .... hell yeah... amiga was soooo ahead of its time.... too bad it had such poor marketing.  I think it would have been more popular than the PC, and would have soared.

The C64 Programming Reference Guide is the bible, and a only spoken aloud with utter respect. 

Indeed, the video toaster wat the thing! I was so proud to be able to tell my mates this Babylon 5 they were watching was rendered with "my" Amiga, instead of their lame, still Prince of Persia running PC's.   
Although I had a hard time convincing my friends in the Commodore c64 scene, they would (and still do, some of them) mostly refer to that machine as the L'Amiga.   

> Reply from Rahly
>
> if you do 

X := X * (2^A) (converts to a shl A) 
X := X / (2^A) (converts to a shr A) 

at least, delphi is smart enough to do that. 

Although, i donno what VB does for this.

Yes, that would be the way, only it does not work like that. I'm telling you, there's only signed variables in there!
## Post #62
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T22:04:09+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> The C64 Programming Reference Guide is the bible, and a only spoken aloud with utter respect. 

Indeed, the video toaster wat the thing! I was so proud to be able to tell my mates this Babylon 5 they were watching was rendered with "my" Amiga, instead of their lame, still Prince of Persia running PC's.   
Although I had a hard time convincing my friends in the Commodore c64 scene, they would (and still do, some of them) mostly refer to that machine as the L'Amiga.

Yeah, the only thing is, i didn't know what the render time was for scenes/frames in it.  The amiga was a marvel, the first multitasking processor, too.  To bad commodore bought it, and just sat on it.  Although, I heard somewhere, that they might be bringing it back.

> Reply from Mr.Mouse
>
> Yes, that would be the way, only it does not work like that. I'm telling you, there's only signed variables in there!

So it compiles down to an SAL/SAR instead of an SHL/SHR.  Fortunately SHL and SAL do the same thing, even the Intel/AMD documentation say the same thing.  But SAR/SHR aren't the same.

Of course, I wouldn't know unless you make a program that did performed this function like

DIM A As Long
LET A = 500
MsgBox A (or however its done
LET A = A / 2
MsgBox A

Then I could look at the assembly generated.
## Post #63
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T07:41:28+00:00
- Post Title: 

Sample Plugin


PluginSystem.pas

```

interface

uses
  Common,  // Common structures and constants, need to make a common.h and maybe a common.bas
  ActiveX; // For imported the global IStream interface

function mpGetInterfaceVersion(var Major, Minor: Integer): Boolean; stdcall;
function mpGetVersion(var Major, Minor: Integer): Boolean; stdcall;
function mpGetFormatCount(): LongWord; stdcall;
function mpGetFormatInfo(FormatIndex: Integer; var FormatInfo: TFormatInfo): Boolean; stdcall;
function mpGetOptions(FormatIndex: Integer; OptionType: Integer; var Options: PChar): Boolean; stdcall;
function mpOpenArchive(var ArchiveHandle: Integer; FormatIndex: Integer; ArchiveName: PChar; Flags: Cardinal; CreateOptions: PChar): Boolean; stdcall;
function mpOpenArchiveBindStream(var ArchiveHandle: Integer; FormatIndex: Integer; Stream: IStream; Flags: Cardinal; CreateOptions: PChar): Boolean; stdcall;
function mpCloseArchive(ArchiveHandle: Integer): Boolean; stdcall;
function mpIndexCount(ArchiveHandle: Integer): Integer; stdcall;
function mpFindFirstFile(ArchiveHandle: Integer; FileMask: PChar; FieldList: PChar; var FindData: TFileFindInfo): Boolean; stdcall;
function mpFindNextFile(var FindData: TFileFindInfo): Boolean; stdcall;
function mpFindClose(var FindData: TFileFindInfo): Boolean; stdcall;
function mpIsArchive(FormatIndex: Integer; Filename: PChar): Boolean; stdcall;
function mpExportFileByNameToFile(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean; stdcall;
function mpExportFileByIndexToFile(ArchiveHandle: Integer; FileIndex: Integer; ExternalFile: PChar): Boolean; stdcall;
function mpExportFileByNameToStream(ArchiveHandle: Integer; ArchiveFile: PChar; Stream: IStream): Boolean; stdcall;
function mpExportFileByIndexToStream(ArchiveHandle: Integer; FileIndex: Integer; Stream: IStream): Boolean; stdcall;
function mpImportFileByNameFromFile(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean; stdcall;
function mpImportFileByIndexFromFile(ArchiveHandle: Integer; FileIndex: Integer; ExternalFile: PChar): Boolean; stdcall;
function mpImportFileByNameFromStream(ArchiveHandle: Integer; ArchiveFile: PChar; Stream: IStream): Boolean; stdcall;
function mpImportFileByIndexFromStream(ArchiveHandle: Integer; FileIndex: Integer; Stream: IStream): Boolean; stdcall;

implementation

uses
  SysUtils,  // For system functions like "FileExists"
  Match,     // Homebrewn matching object to match files with wildcards
  BigFile,   // Object for processing BF(aka BIG) files
  Classes,   // Standard Stream Classes
  AxCtrls;   // Import TOleStream class for converting IStream into a Delphi Stream class                              

// Internal Structures and Constants

const
  MyFormats: Array[0..1] of TFormatInfo =
    (
      ( FileMask: '*.bf'; GameName: 'Beyond Good and Evil';
        Flags: SUPPORTFLAG_EXPORT or SUPPORTFLAG_BYINDEX or SUPPORTFLAG_BYNAME ),
      ( FileMask: '*.bf'; GameName: 'Prince of Persia';
        Flags: SUPPORTFLAG_EXPORT or SUPPORTFLAG_BYINDEX or SUPPORTFLAG_BYNAME )
    );

type
  TArchiveHandles = record
    Used: Boolean;
    Filename: String;
    BigFile: TBigFile;
    MyStream: TStream;
  end;

  PMyFindInfo = ^TMyFindInfo;
  TMyFindInfo = record
    MyMatcher: TMatchObject;
    LastIndex: Integer;
  end;

var
  ActiveHandles: Array of TArchiveHandles;

// Exported Functions

function mpGetInterfaceVersion(var Major, Minor: Integer): Boolean;
begin
  Major := InterfaceVersionMajor;
  Minor := InterfaceVersionMinor;
  Result := True;
end;

function mpGetVersion(var Major, Minor: Integer): Boolean;
begin
  Major := 1;
  Minor := 0;
  Result := True;
end;

function mpGetFormatCount(): LongWord;
begin
  Result := Length(MyFormats);
end;

function mpGetFormatInfo(FormatIndex: Integer; var FormatInfo: TFormatInfo): Boolean; stdcall;
begin
  Result := False;
  if( (FormatIndex >= 0) and (FormatIndex < Length(MyFormats)) and
      (FormatInfo.Size >= SizeOf(TFormatInfo)) ) then
    begin
    FormatInfo.FileMask := MyFormats[FormatIndex].FileMask;
    FormatInfo.GameName := MyFormats[FormatIndex].GameName;
    FormatInfo.Flags    := MyFormats[FormatIndex].Flags;
    Result := True;
    end;
end;

function mpGetOptions(FormatIndex: Integer; OptionType: Integer; var Options: PChar): Boolean;
begin
  Result := False;
  case OptionType of
    OPTIONTYPE_EXPORT:
      begin
      Options := 'MSADPCMTOPCM';
      Result := True;
      end;
  end;
end;

function mpOpenArchive(var ArchiveHandle: Integer; FormatIndex: Integer; ArchiveName: PChar; Flags: Cardinal; CreateOptions: PChar): Boolean;
var
  Count: Integer;
begin
  Result := False;
  if (FormatIndex >= 0) and (FormatIndex < Length(MyFormats)) and (Flags = 0) and
    FileExists(ArchiveName) then
    begin

    Count := 0;
    while (Count < Length(ActiveHandles)) and ActiveHandles[Count].Used do
      Inc(Count);
    if Count >= Length(ActiveHandles) then
      begin
      SetLength(ActiveHandles,Length(ActiveHandles)+1);
      end;

    try
      case FormatIndex of
        0:
          ActiveHandles[Count].BigFile := TBIGFile.Create(String(Archivename),$22);
        1:
          ActiveHandles[Count].BigFile := TBIGFile.Create(String(Archivename),$25);
      end;
      ActiveHandles[Count].Used := True;
      ActiveHandles[Count].Filename := String(Archivename);
      Result := True;
    except
      ActiveHandles[Count].Used := False;
      Result := False;
    end;

    end;
end;

function mpOpenArchiveBindStream(var ArchiveHandle: Integer; FormatIndex: Integer; Stream: IStream; Flags: Cardinal; CreateOptions: PChar): Boolean;
var
  Count: Integer;
begin
  Result := False;
  if (FormatIndex >= 0) and (FormatIndex < Length(MyFormats)) and (Flags = 0) then
    begin

    Count := 0;
    while (Count < Length(ActiveHandles)) and ActiveHandles[Count].Used do
      Inc(Count);
    if Count >= Length(ActiveHandles) then
      begin
      SetLength(ActiveHandles,Length(ActiveHandles)+1);
      end;

    try
      ActiveHandles[Count].MyStream := TOleStream.Create(Stream);
      case FormatIndex of
        0:
          ActiveHandles[Count].BigFile := TBIGFile.Create(ActiveHandles[Count].MyStream,$22);
        1:
          ActiveHandles[Count].BigFile := TBIGFile.Create(ActiveHandles[Count].MyStream,$25);
      end;
      ActiveHandles[Count].Used := True;
      ActiveHandles[Count].Filename := '';
      Result := True;
    except
      ActiveHandles[Count].Used := False;
      Result := False;
    end;
    end;
end;

function mpCloseArchive(ArchiveHandle: Integer): Boolean;
begin
  Result := False;
  if (ArchiveHandle >= 0) and (ArchiveHandle < Length(ActiveHandles)) and
     ActiveHandles[ArchiveHandle].Used then
    begin
    ActiveHandles[ArchiveHandle].Used := False;
    ActiveHandles[ArchiveHandle].Filename := '';
    FreeAndNil(ActiveHandles[ArchiveHandle].BigFile);
    end;
end;

function mpIndexCount(ArchiveHandle: Integer): Integer;
begin
  Result := 0;
  if (ArchiveHandle >= 0) and ( ArchiveHandle < Length(ActiveHandles)) and
     (ActiveHandles[ArchiveHandle].Used) then
    Result := ActiveHandles[ArchiveHandle].BigFile.FileCount;
end;

function mpFindFirstFile(ArchiveHandle: Integer; FileMask: PChar; FieldList: PChar; var FindData: TFileFindInfo): Boolean;
var
  MyData: PMyFindInfo;
  Found: Boolean;
begin
  Result := False;
  if (ArchiveHandle >= 0) and (ArchiveHandle < Length(ActiveHandles)) and
     ActiveHandles[ArchiveHandle].Used then
    begin
    New(MyData);
    MyData^.MyMatcher := TMatchObject.Create(String(FileMask));
    FindData.FileMask := FileMask;
    FindData.ArchiveHandle := ArchiveHandle;
    FindData.FieldList := FieldList;
    FindData.InternalFindInfo := MyData;
    if ActiveHandles[ArchiveHandle].BigFile.FileCount > 0 then
      begin
      ActiveHandles[ArchiveHandle].BigFile.FileNumber := 0;
      Found := MyData^.MyMatcher.DoesTextMatch(ActiveHandles[ArchiveHandle].BigFile.FileInfo.Filename);
      while( Not(Found) and ActiveHandles[ArchiveHandle].BigFile.NextFile ) do
        begin
        Found := MyData^.MyMatcher.DoesTextMatch(ActiveHandles[ArchiveHandle].BigFile.FileInfo.Filename);
        end;
      if Found then
        begin
        FindData.Filename := PChar(ActiveHandles[ArchiveHandle].BigFile.FileInfo.Filename);
        // Process Field List to Create Field Data
        FindData.FieldData := '';
        MyData^.LastIndex := ActiveHandles[ArchiveHandle].BigFile.FileNumber;
        Result := True;
        end;
      end;
    end;
end;

function mpFindNextFile(var FindData: TFileFindInfo): Boolean;
var
  ArchiveHandle: Integer;
  MyData: PMyFindInfo;
  Found: Boolean;
begin
  Result := False;
  ArchiveHandle := FindData.ArchiveHandle;
  if (ArchiveHandle >= 0) and (ArchiveHandle < Length(ActiveHandles)) and
     ActiveHandles[ArchiveHandle].Used then
    begin
    MyData := FindData.InternalFindInfo;
    if (ActiveHandles[ArchiveHandle].BigFile.FileCount > 0) and
       (MyData^.LastIndex < ActiveHandles[ArchiveHandle].BigFile.FileCount ) then
      begin
      ActiveHandles[ArchiveHandle].BigFile.FileNumber := MyData^.LastIndex + 1;
      Found := MyData^.MyMatcher.DoesTextMatch(ActiveHandles[ArchiveHandle].BigFile.FileInfo.Filename);
      while( Not(Found) and ActiveHandles[ArchiveHandle].BigFile.NextFile ) do
        begin
        Found := MyData^.MyMatcher.DoesTextMatch(ActiveHandles[ArchiveHandle].BigFile.FileInfo.Filename);
        end;
      if Found then
        begin
        FindData.Filename := PChar(ActiveHandles[ArchiveHandle].BigFile.FileInfo.Filename);
        // Process Field List to Create Field Data
        FindData.FieldData := '';
        MyData^.LastIndex := ActiveHandles[ArchiveHandle].BigFile.FileNumber;
        Result := True;
        end
      else
        MyData^.LastIndex := MaxInt;
      end;
    end;
end;

function mpFindClose(var FindData: TFileFindInfo): Boolean;
begin
  Dispose(FindData.InternalFindInfo);
  Result := True;
end;


function mpIsArchive(FormatIndex: Integer; Filename: PChar): Boolean;
var
  MyFile: TBigFile;
begin
  Result := False;
  try
    case FormatIndex of
      $0:
        begin
        MyFile := TBigFile.Create(Filename, $22);
        MyFile.Free;
        Result := True;
        end;
      $1:
        begin
        MyFile := TBigFile.Create(Filename, $25);
        MyFile.Free;
        Result := True;
        end;
    end;
  except
    Result := False;
  end;
end;

function mpExportFileByNameToFile(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean;
var
  ToName: String;
  FromName: String;
  FindData: TFileFindInfo;
begin
  Result := False;
  FromName := String(ArchiveFile);
  ToName := String(ExternalFile);
  if ( Pos(FromName, '*')>0 ) or ( Pos(FromName, '?') > 0 ) then
    begin
    ToName := IncludeTrailingPathDelimiter(ToName);
    if ForceDirectories(ToName) then
      begin
      if mpFindFirstFile(ArchiveHandle, ArchiveFile, nil, FindData) then
        begin
        repeat
          with ActiveHandles[ArchiveHandle] do
            BigFile.ExtractToFile(ToName + BigFile.FileInfo.Filename);
        until Not(mpFindNextFile(FindData));
        Result := True;
        end;
      mpFindClose(FindData);
      end;
    end
  else
    begin
    if mpFindFirstFile(ArchiveHandle, ArchiveFile, nil, FindData) then
      begin
      with ActiveHandles[ArchiveHandle] do
        if (Length(ToName) > 0) and (ToName[Length(ToName)] = '\') then
          BigFile.ExtractToFile(ToName + BigFile.FileInfo.Filename)
        else
          BigFile.ExtractToFile(ToName);
      Result := True;
      end;
    mpFindClose(FindData);
    end;
end;

function mpExportFileByIndexToFile(ArchiveHandle: Integer; FileIndex: Integer; ExternalFile: PChar): Boolean;
var
  ToName: String;
begin
  ToName := String(ExternalFile);
  Result := False;
  if (ArchiveHandle >= 0) and (ArchiveHandle < Length(ActiveHandles)) then
    begin
    ActiveHandles[ArchiveHandle].BigFile.FileNumber := FileIndex;
    if ActiveHandles[ArchiveHandle].BigFile.FileNumber = FileIndex then
      begin
      with ActiveHandles[ArchiveHandle] do
        if (Length(ToName) > 0) and (ToName[Length(ToName)] = '\') then
          BigFile.ExtractToFile(ToName + BigFile.FileInfo.Filename)
        else
          BigFile.ExtractToFile(ToName);
      Result := True;
      end;
    end;
end;

function mpExportFileByNameToStream(ArchiveHandle: Integer; ArchiveFile: PChar; Stream: IStream): Boolean;
var
  FromName: String;
  FindData: TFileFindInfo;
  MyStream: TOleStream;
begin
  Result := False;
  FromName := String(ArchiveFile);
  MyStream := TOleStream.Create(Stream);
  if ( Pos(FromName, '*')=0 ) and ( Pos(FromName, '?') = 0 ) then
    begin
    if mpFindFirstFile(ArchiveHandle, ArchiveFile, nil, FindData) then
      begin
      with ActiveHandles[ArchiveHandle] do
        BigFile.ExtractToStream(MyStream);
      Result := True;
      end;
    mpFindClose(FindData);
    end;
  MyStream.Free;
end;

function mpExportFileByIndexToStream(ArchiveHandle: Integer; FileIndex: Integer; Stream: IStream): Boolean;
var
  MyStream: TOleStream;
begin
  Result := False;
  MyStream := TOleStream.Create(Stream);
  if (ArchiveHandle >= 0) and (ArchiveHandle < Length(ActiveHandles)) then
    begin
    ActiveHandles[ArchiveHandle].BigFile.FileNumber := FileIndex;
    if ActiveHandles[ArchiveHandle].BigFile.FileNumber = FileIndex then
      begin
      with ActiveHandles[ArchiveHandle] do
        BigFile.ExtractToStream(MyStream);
      Result := True;
      end;
    end;
  MyStream.Free;
end;

function mpImportFileByNameFromFile(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean;
begin
  // Not Supported
  Result := False;
end;

function mpImportFileByIndexFromFile(ArchiveHandle: Integer; FileIndex: Integer; ExternalFile: PChar): Boolean;
begin
  // Not Supported
  Result := False;
end;

function mpImportFileByNameFromStream(ArchiveHandle: Integer; ArchiveFile: PChar; Stream: IStream): Boolean; 
begin
  // Not Supported
  Result := False;
end;

function mpImportFileByIndexFromStream(ArchiveHandle: Integer; FileIndex: Integer; Stream: IStream): Boolean;
begin
  // Not Supported
  Result := False;
end;

end.
```


Common.pas

```

interface

type
  TFormatInfo = packed record
    // Version 1.0
    Size: Integer;
    FileMask: PChar; // This is better than an "Interface
    GameName: PChar; // This is the name of the game it supports
    Flags: Int64;    // Support flags
  end;

  TFileFindInfo = packed record
    Filename: PChar;
    FieldData: PChar;
    FileMask: PChar;
    ArchiveHandle: Integer;
    FieldList: PChar;
    InternalFindInfo: Pointer;
  end;

const
  SUPPORTFLAG_CREATE = $0000000000000001;
  SUPPORTFLAG_IMPORT = $0000000000000002;
  SUPPORTFLAG_EXPORT = $0000000000000004;
  SUPPORTFLAG_DELETE = $0000000000000008;
  SUPPORTFLAG_REPLACE= $0000000000000010;
  SUPPORTFLAG_ADD    = $0000000000000020;
  SUPPORTFLAG_BYINDEX= $0000000000000040;
  SUPPORTFLAG_BYNAME = $0000000000000080;

  OPTIONTYPE_CREATE  = $00000001;
  OPTIONTYPE_EXPORT  = $00000002;
  OPTIONTYPE_IMPORT  = $00000003;

  OPENFLAG_CREATENEW      = $00000001;
  OPENFLAG_CREATEEXISTING = $00000002;

  InterfaceVersionMajor = 1;
  InterfaceVersionMinor = 0;

implementation

end.
```


plug_bf.dpr

```

uses
  SysUtils,
  Classes,
  PluginSystem in 'PluginSystem.pas',
  Common in 'Common.pas';

{$R *.res}

{$EXTENSION mxp}

exports
  mpGetInterfaceVersion,
  mpGetVersion,
  mpGetFormatCount,
  mpGetFormatInfo,
  mpGetOptions,
  mpOpenArchive,
  mpOpenArchiveBindStream,
  mpCloseArchive,
  mpIndexCount,
  mpFindFirstFile,
  mpFindNextFile,
  mpFindClose,
  mpIsArchive,
  mpExportFileByNameToFile,
  mpExportFileByIndexToFile,
  mpExportFileByNameToStream,
  mpExportFileByIndexToStream,
  mpImportFileByNameFromFile,
  mpImportFileByIndexFromFile,
  mpImportFileByNameFromStream,
  mpImportFileByIndexFromStream;


begin
end.
```


Creates a plug_bf.mxp.
## Post #64
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T08:03:00+00:00
- Post Title: 

Ok, now working on the Plugin Manager.
## Post #65
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T08:30:30+00:00
- Post Title: 

Found some changes already 

added some new constants

```
  SUPPORTFLAG_HANDLEFILE    = $0000000000000200;
  SUPPORTFLAG_TESTARCHIVE   = $0000000000000400;
```


to the common.pas

and change

mpIsArchive into 2 functions

```
function mpIsStreamAnArchive(FormatIndex: Integer; Stream: IStream): Boolean; stdcall;
```
## Post #66
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-10T08:57:02+00:00
- Post Title: 

Lol! You do know that you can attach files here? Saves cutting and pasting.
## Post #67
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T08:59:54+00:00
- Post Title: 

Yeah, but this is easier to read, i haven't given you the whole plugin YET, i wanna get the manager done first.  Just wanted to show you what i had done
## Post #68
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-10T09:05:10+00:00
- Post Title: 

Ok  By the way, do you have a registration at Sourceforge yet? You've done so much now, would be best to put you in the list of programmers. 

Where are you from, gives me an inidication of the times you will be online (over here in The Netherlands it's 11:00 AM at the moment, for instance).
## Post #69
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T09:24:07+00:00
- Post Title: 

Michigan, USA, its 5 am here, let me go register.  Ok Done.
## Post #70
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-10T10:35:05+00:00
- Post Title: 

Yes, well, what is your username there?
## Post #71
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T10:36:39+00:00
- Post Title: 

oh... opps,   dl748   "DL748" but as lowercase, i think sourceforge is case sensitive.
## Post #72
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-10T11:08:55+00:00
- Post Title: 

Added!
## Post #73
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T11:43:21+00:00
- Post Title: 

you use wincvs?
## Post #74
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-10T11:43:59+00:00
- Post Title: 

No, TortoiseCVS
## Post #75
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T12:43:17+00:00
- Post Title: 

I looked at my plugin dll that was generated and it was 386K in size, so i went through it and found adding the unit AxCtrls, changed it back down to 118K, but I couldn't use TOleStream.  So I ended up copying the class to a seperate unit, and using that, and it went to 119K.  Which is not a bad size.
## Post #76
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T12:47:08+00:00
- Post Title: 

i don't have permission to import, can you make a module/directory called mexplug
## Post #77
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-10T13:44:27+00:00
- Post Title: 

You don't have that? Strange. 
Let me see. By the way, don't you ever sleep? Las ttime you said it was 5:00 AM.
## Post #78
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-10T13:47:25+00:00
- Post Title: 

"Project developers (and admins) must use :ext: authentication with SSH in order to obtain write access to the repository. Non-developers must use anonymous pserver-based authentication to access the repository. " The settings are all okay? You should have access to the mexcom module.

[EDIT]I checked again and you really should have read/write access to the CVS[/EDIT]
## Post #79
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-10T15:04:15+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> You don't have that? Strange. 
Let me see. By the way, don't you ever sleep? Las ttime you said it was 5:00 AM.

Sleep? Whats that?
## Post #80
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-10T15:05:10+00:00
- Post Title: 

LOL Damn timeouts
