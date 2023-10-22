## Post #1
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-09-18T15:21:28+00:00
- Post Title: Just Cause game .arc archives

I need to unpack/pack .arc archives from Just Cause game (c) Eidos
pc0.arc < this file is 510 MB
It is in demo too
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-18T15:36:09+00:00
- Post Title: Just Cause game .arc archives

Got any links to said demo?
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-18T17:21:02+00:00
- Post Title: Just Cause game .arc archives

> Reply from Slaii
>
> I need to unpack/pack .arc archives from Just Cause game (c) Eidos
pc0.arc < this file is 510 MB
It is in demo tooWhat console is this game for exactly?
Because the gamecube uses RARC compression (often called ARC), there archieves btw.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-18T21:21:33+00:00
- Post Title: Just Cause game .arc archives

About RARc compression:

> RARC archives
>
> =============
>
> 
>
> Version 1
>
> 
>
> 
>
> If you de-Yaz0 a Supermario Sunshine .szs file, you get a file starting with "RARC". This file is an archive file and contains several other files. This document describes the structure of these RARC files (note that I got all this information by staring at these files in a hex editor, so it may not be entirely accurate...it seems to work, though).
>
> 
>
> The file starts with an RarcHeader:
>
> 
>
> struct RarcHeader
>
> {
>
>   char type[4]; //'RARC'
>
>   u32 size; //size of the file
>
>   u32 unknown;
>
>   u32 dataStartOffset; //where does the actual data start? You have to add 0x20 to this value.
>
>   u32 unknown2[4];
>
> 
>
>   u32 numNodes;
>
>   u32 unknown3[2];
>
>   u32 fileEntriesOffset;
>
>   u32 unknown4;
>
>   u32 stringTableOffset; //where is the string table stored? You have to add 0x20 to this value.
>
>   u32 unknown5[2];
>
> };
>
> 
>
> Next are RarcHeader.numNodes Node structures:
>
> 
>
> struct Node
>
> {
>
>   char type[4];
>
>   u32 filenameOffset; //directory name, offset into string table
>
>   u16 unknown;
>
>   u16 numFileEntries; //how many files belong to this node?
>
>   u32 firstFileEntryOffset;
>
> };
>
> 
>
> Each RARC file contains at least one Node, the 'ROOT' node. For each subdirectory in the archive, there's another Node (so each Node represents a directory). Each Node contains files and directories, represented by FileEntry structures:
>
> 
>
> struct FileEntry
>
> {
>
>   u16 id; //file id. If this is 0xFFFF, then this entry is a subdirectory link
>
>   u16 unknown;
>
>   u16 unknown2;
>
>   u16 filenameOffset; //file/subdir name, offset into string table
>
>   u32 dataOffset; //offset to file data (for subdirs: index of Node representing the subdir)
>
>   u32 dataSize; //size of data
>
>   u32 zero; //seems to be always '0'
>
> };
>
> 
>
> To read the archive, you read the root node and its file entries. For each subdir in the root node's fileentries, you read the corresponding node and its file entries. For each file in the fileentries, you dump its data.
>
> 
>
> thakis (http://www.amnoid.de/gc/)
>
> 
>
> Changelog
>
> =========
>
> 
>
> 20050211: Initial release

Some links and programs 
[http://www.amnoid.de/gc/index.html](http://www.amnoid.de/gc/index.html) 

[http://www.amnoid.de/gc/szstools.zip](http://www.amnoid.de/gc/szstools.zip)
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-18T21:34:13+00:00
- Post Title: Just Cause game .arc archives

> Reply from pulposo
>
> About RARc compression:

RARC archives
=============

Version 1


If you de-Yaz0 a Supermario Sunshine .szs file, you get a file starting with "RARC". This file is an archive file and contains several other files. This document describes the structure of these RARC files (note that I got all this information by staring at these files in a hex editor, so it may not be entirely accurate...it seems to work, though).
http://www.amnoid.de/gc/index.html 

http://www.amnoid.de/gc/szstools.zip 
Ahh he he he   
I was correct then IT IS gamecube RARC.
This is some more info off the website.
I havent ahd a chance to read Pulpuso's post propperly yet so this may or may not be more detailed.
15.3  ARC (RARC Archive)
This file is an archive file and contains several other files. index 
15.3.1  Header
The file starts with an Rarc-Header: start end size description 
    4 type - 'RARC' 
    4 size, size of the file 
    4 unknown 
    4 dataStartOffset, where does the actual data start? You have to add 0x20 to this value. 
    16 unknown 
    4 numNodes 
    8 unknown 
    4 fileEntriesOffset 
    4 unknown 
    4 stringTableOffset, where is the string table stored? You have to add 0x20 to this value. 
    8 unknown 

index 
15.3.2  Nodes
Next are RarcHeader.numNodes Node structures: start end size description 
    4 type 
    4 filenameOffset, directory name, offset into string table 
    2 unknown 
    2 numFileEntries, how many files belong to this node? 
    4 firstFileEntryOffset 

Each RARC file contains at least one Node, the 'ROOT' node. For each subdirectory in the archive, there's another Node (so each Node represents a directory). Each Node contains files and directories, represented by FileEntry structures: index 
15.3.3  File Entries
start end size description 
    2 id, file id. If this is 0xFFFF, then this entry is a subdirectory link 
    2 unknown 
    2 unknown 
    2 filenameOffset, file/subdir name, offset into string table 
    4 dataOffset, offset to file data (for subdirs: index of Node representing the subdir) 
    4 dataSize, size of data 
    4 zero, seems to be always '0' 

To read the archive, you read the root node and its file entries. For each subdir in the root node's fileentries, you read the corresponding node and its file entries. For each file in the fileentries, you dump its data.
Hope it helps
## Post #6
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-09-19T14:58:05+00:00
- Post Title: Just Cause game .arc archives

Demo is available from gamershell:

```
http://www.gamershell.com/download_15145.shtml
```


or here:

```
http://hry2.sme.sk/just_cause_demo.exe
```


cca 540 MB

In attachment is header of pc0.arc file 
@lionheartuk thanx, but I think that is not right

game is for: [PC,PS2,Xbox] 

developer: Avalanche Studios
publisher: Eidos
2006
[just_124.jpg](https://xentaxbackup.github.io/file/862_just_124.jpg)
## Post #7
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-19T15:59:47+00:00
- Post Title: Just Cause game .arc archives

> Reply from Slaii
>
> 
In attachment is header of pc0.arc file 
@lionheartuk thanx, but I think that is not right
2006
JUst because the game is not FOR gamecube Doesnt mean that its not using a gamecube typoe method of encryption/compression.
Well I can say 1 thing.

Your image doesnt really help us much lol.
As it COULD be YAZ0R compression, though the sign of that its those 5 letters at the first 5 bytes.
BUT it could be an edit of that format.
THe best thing I think for you to do is use the FILE CUTTER to cut the file up, then upload it HERE or elsewhere and then we can see.
Few of us will actualy downlaod a file that over 500 meg JUST for a quick look, when we can get jsut as much info from a files Piece.

But it COULD be RARC still, But i cant tell at all until I look at a file Piece with a Hex editor myself.
But even then i cant PROMISE anything from it.
## Post #8
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-09-20T15:48:43+00:00
- Post Title: Just Cause game .arc archives

@lionheartuk: ok, now I know...

I cut small part of that .pc and pack it with 2 other files I found in the same dir as .pc

pclist.txt: there is list of files like

```
C:\finalbuilder\demo\Projects\JustCause\data\Levels\GlobalTerrainData_PC.dat
```


pc.tab: unknown

When I view .pc in hex I saw some UUU chars - I think, that there are packed .dds files...

Hope it help... if not I can send bigger piece of .pc to rapid*share
[justcause.rar](https://xentaxbackup.github.io/file/863_justcause.rar)
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-20T17:33:13+00:00
- Post Title: Just Cause game .arc archives

Can someone help me to find the "packed" data in this archive. i just
cannot find any. its not packed.

And yes. there are DDS textures in here. unpacked.
but without headers.
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-08T01:13:31+00:00
- Post Title: Just Cause game .arc archives

It's only in the first pack the compressed file, the other .arc's are uncompressed, there you can found a lot of DDS
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-08T10:46:04+00:00
- Post Title: Just Cause game .arc archives

It seems to me the txt file in the same dir as PC0 is the list of files in the PC0.ARC, and the .tab file gives information on where to find these files in the arc.
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-09T10:57:51+00:00
- Post Title: Just Cause game .arc archives

What I expected is indeed the case. I am still puzzled why the pclist.txt refers to more files then there are in the PC0.ARC file (based on findings in the pc.tab file). I am currently writing a plugin for MexCom to support extraction.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-10T07:38:37+00:00
- Post Title: Just Cause game .arc archives

See attached image. The plugin now detects all files in the ARC and links it with the correct filename. Need to build in actual extraction. More to follow.
[mexcom_justcause_arc.jpg](https://xentaxbackup.github.io/file/900_mexcom_justcause_arc.jpg)
## Post #14
- Username: srcs34k
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-10T14:38:05+00:00
- Post Title: Just Cause game .arc archives

Working Plugin for Just Cause (PC) .ARC files and SARC files. 

Download the attached zip file and extract the dll. Create a ARC folder in the plugin directory of MultiEx Commander and then copy the dll there. Done. 

This MexCom plugin will open and extract from .ARC files and SARC files. 

ARC files:

The .tab and .txt files that refer to the ARC file need to be in the same folder as the ARC file or it won't work. 

SARC files:
These are Smaller ARChives that are within the large ARC file. They usually have extensions like .bl and .nl at least, but there may be more. Just open some file with an Hex editor and if you see the word SARC starting from the 5th byte then presto, you have yourself a SARC file. 

I've attached some screens of MexCom with an open ARC file and an open SARC file. 

As to the format of the ARC file, the ARC file merely contains all the resources saved one by the other. However, they are padded up to blocks of whatever is specified in the .tab file. Padding is done by filling the remainder of the block up with "P", how aPProPriate. Padding...P...geddit? 

The .tab file and the pclist file need some further explaining. First the pclist.txt file. This had me puzzled because it listed more files then there actually were in the .ARC file, according to the .tab file. The answer, after a long session of logic and comparing extracted files with their possible names, was simple of course. Every file has a unique name, even though the folders they came from might differ. Every time this Eidos packer would encounter a file with the same name as one already stored in the .ARC file, it would SKIP IT! Furthermore, files that did not have an extension (like 4 or 5 entries in the pclist.txt) were also skipped! Possibly, because the packer regarded those as folders? I don't know. After sorting the list, all files in the ARC file matched thier names in chronological order from top of the list to bottom. 

Finally, the .tab file. This contains info about the location and the size of each resource in the .ARC archive. 

```
// Header

uint32 Version info?
uint32 BlockSize (for padding the .ARC file)
uint32 Version info?

// for each entry 

uint32  Unknown (increasing with each entry, rapidly)
uint32  Offset in blocks. To get the actual offset, multiply by the BlockSize
uint32  Size 


```

SARC Files:


```
// Header

uint32     Version?
byte {4} Magic word (SARC)
uint32     Size of file info block 

// For each entry (in the file info block)

uint32     Size of filename 
byte{}    Filename (string)
uint32     Offset 
uint32     Size

```


As said, there are a number of files listed in the pclist.txt file that are not saved in the .ARC file. When you start the plugin to open an .ARC file, it will create a dropped.txt file in the folder of the plugin. Those that were dropped form .ARC file you will find listed there. 

NOTE: To speed up comparison of filenames, I created a routine that hashes the filename strings first. I've achieved enough specificity to succesfully locate the duplicates etc and end up with the right list. I've worked with the demo, however, so I don't know about the retail version. 
Also note that you may have to be patient while the plugin does its work. 

Okido, thanks for tuning in, now view the screens and download the plugin. 
[Just_Cause_MexCom_PGN.zip](https://xentaxbackup.github.io/file/904_Just_Cause_MexCom_PGN.zip)

[mexcom_justcause_arc_1.jpg](https://xentaxbackup.github.io/file/903_mexcom_justcause_arc_1.jpg)

[mexcom_justcause_arc_2_bl.jpg](https://xentaxbackup.github.io/file/902_mexcom_justcause_arc_2_bl.jpg)
## Post #15
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-10-10T17:19:59+00:00
- Post Title: Just Cause game .arc archives

Hmmm
@Mr.Mouse:

It looks like your plugin is working, but when I try to open the .arc archive I only get error:
"PNG Archive not valid Path_to_my_directory_with Just_cause.dll"

I am using unregistered version
## Post #16
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-10-10T17:25:44+00:00
- Post Title: great!!!

Now it is working fine!

You would not believe me:
I had to install Mycrosoft Offyce 2000 to fix it.... (some error occured and then Mex asked me to install it...)

What a crazy day......

Btw: Mr.Mouse: you are great... thx
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-10T17:25:58+00:00
- Post Title: great!!!

> Reply from Slaii
>
> Hmmm
@Mr.Mouse:

It looks like your plugin is working, but when I try to open the .arc archive I only get error:
"PNG Archive not valid Path_to_my_directory_with Just_cause.dll"

I am using unregistered version

Are you sure the .tab and .txt files are in the folder with the .arc file?

Also, can you show what is in the folder with the.arc file? 

Are you using the retail version of Just Cause?
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-10T18:16:02+00:00
- Post Title: great!!!

> Reply from Slaii
>
> Now it is working fine!

You would not believe me:
I had to install Mycrosoft Offyce 2000 to fix it.... (some error occured and then Mex asked me to install it...)

What a crazy day......

Btw: Mr.Mouse: you are great... thx

Thanks. Glad it works now.
## Post #19
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-10-11T16:21:05+00:00
- Post Title: great!!!

you rock Mister Mouse!
## Post #20
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-13T22:04:21+00:00
- Post Title: great!!!

Hello I am new in this great Forum!

I need help! The Just Cause PLUGIN donÂ´t work on my PC i allways get the message PGN NOT VALID! And in the lower left corner stands, not a multiex commander plugin!

I hope someone can help me, i have try to reinstall my Microsoft Office but i doesnt help.

tom
## Post #21
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-13T23:17:47+00:00
- Post Title: great!!!

> Reply from thomasdxyz
>
> Hello I am new in this great Forum!

I need help! The Just Cause PLUGIN donÂ´t work on my PC i allways get the message PGN NOT VALID! And in the lower left corner stands, not a multiex commander plugin!

I hope someone can help me, i have try to reinstall my Microsoft Office but i doesnt help.

tom

All the others work? All the other plugins? You can see that in the plugin list in  Tools-->View detected plugins.
## Post #22
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-13T23:54:28+00:00
- Post Title: great!!!

> All the others work? All the other plugins? You can see that in the plugin list in  Tools-->View detected plugins.

I have tried Call of Duty 2, NFS Most Wanted, with this games it works fine. 

When i scan a *.arc file from Just Cause and i cancel it, then i can see some dds files and i can view it but when i want to open it normal i get this PGN error.

Could it be that it don`t work with the german full version of Just Cause.
## Post #23
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2006-10-14T07:08:40+00:00
- Post Title: great!!!

I get the same message when trying to open just cause .ARC files 


Pls help us  
[Image2.jpg](https://xentaxbackup.github.io/file/915_Image2.jpg)
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-14T07:16:24+00:00
- Post Title: great!!!

> Reply from thomasdxyz
>
> All the others work? All the other plugins? You can see that in the plugin list in  Tools-->View detected plugins.

I have tried Call of Duty 2, NFS Most Wanted, with this games it works fine. 

When i scan a *.arc file from Just Cause and i cancel it, then i can see some dds files and i can view it but when i want to open it normal i get this PGN error.

Could it be that it don`t work with the german full version of Just Cause.

Okay, can you upload/attach the debug log file of MexCom after you start it?

(CTRL+L) will show it. 

Also, it may be that the demo version is different than the full version. Are there any files like .txt and .tab in the same folder as the arc files? Please check this! If there are, please also attach those.

Next up, use the file cutter to cut the first and last part of the pc0.arc file. 

[http://www.xentax.com/downloads/tools/filecutter.zip](http://www.xentax.com/downloads/tools/filecutter.zip)
## Post #25
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2006-10-14T13:26:04+00:00
- Post Title: great!!!

Here's the files u asked for...  
I add Cut to the start of PC0.ARC

[http://rapidshare.de/files/36707218/Archives.zip.html](http://rapidshare.de/files/36707218/Archives.zip.html)

hope this helps...
## Post #26
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-14T15:38:39+00:00
- Post Title: great!!!

Here are the files you ask for. The files from the pc0.arc
[Just Cause.rar](https://xentaxbackup.github.io/file/917_Just Cause.rar)
## Post #27
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-14T15:45:46+00:00
- Post Title: great!!!

And the multiex start log file, pc.tab, pclist.txt
[log and tab.rar](https://xentaxbackup.github.io/file/918_log and tab.rar)
## Post #28
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-14T17:21:27+00:00
- Post Title: great!!!

> Reply from thomasdxyz
>
> And the multiex start log file, pc.tab, pclist.txt

I do not see the plugin for Just Cause in the list of detected plugins. Did you download the plugin and make a folder "arc" in the data/plugins folder of MultiEx Commander and copied the plugin there?
## Post #29
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-14T17:24:39+00:00
- Post Title: great!!!

Also, the file PCLIST.TXT is EMPTY. Is this the case normally? If so, then this will be the problem. The plugin needs the file to name the resources in the archive. If its empty, then the plugin will tell you the ARC was not valid.
## Post #30
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2006-10-14T17:41:13+00:00
- Post Title: great!!!

I still get the same error....
and have done all the above?
## Post #31
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-14T18:17:47+00:00
- Post Title: 

> Also, the file PCLIST.TXT is EMPTY. Is this the case normally? If so, then this will be the problem. The plugin needs the file to name the resources in the archive. If its empty, then the plugin will tell you the ARC was not valid.

yes, the pclist.txt is empty.  i forgot to install the plugin, here is the logfile with the installed plugin
[Multiex Log.rar](https://xentaxbackup.github.io/file/919_Multiex Log.rar)
## Post #32
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-14T20:30:48+00:00
- Post Title: 

> Reply from thomasdxyz
>
> Also, the file PCLIST.TXT is EMPTY. Is this the case normally? If so, then this will be the problem. The plugin needs the file to name the resources in the archive. If its empty, then the plugin will tell you the ARC was not valid. 

yes, the pclist.txt is empty.  i forgot to install the plugin, here is the logfile with the installed plugin

The log shows the plugin functions correctly as it responded to an info query. The problem probably lies in the empty pclist.txt file. Are there no other txt or tab files as the one you showed?
## Post #33
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-14T21:41:47+00:00
- Post Title: 

ther are no other pclist files there[/quote]
## Post #34
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2006-10-15T14:52:15+00:00
- Post Title: 

So what is suppost to be in the pclist.txt

and can someone pls post what its suppost to say thx..
## Post #35
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-15T15:38:11+00:00
- Post Title: 

> Reply from DRAVEN
>
> So what is suppost to be in the pclist.txt

and can someone pls post what its suppost to say thx..

In the demo version at least, the pclist.txt file is a list of file that are stored in the pc0.arc archive. Like "c:\foler\file.bl" etc. 

I can adapt the plugin to not care for actual filenames and just extract all of them with generic names.
## Post #36
- Username: hansdelord
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 15, 2006 11:19 pm
- Post datetime: 2006-10-15T15:42:11+00:00
- Post Title: 

the plugin doesnt work with the retail version of just cause (us-version).
it gives me an PGN vaild error.

also in archives folder it isnt a pclist.txt, only a pc.tab
## Post #37
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2006-10-15T19:35:35+00:00
- Post Title: 

Same as what I get... 
I have the UK version of the game
## Post #38
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-15T19:59:53+00:00
- Post Title: 

This plugin will extract from the pc0.arc files, using the .tab file only. It will not give actual filenames, but generic ones. I noticed someone said there's also other .arc files in there? That may pose a problem. 

Anyway, first try version 1.1 of the Just Cause MexCom plugin.
[Just_Cause_MexCom_PGN_1_1.zip](https://xentaxbackup.github.io/file/924_Just_Cause_MexCom_PGN_1_1.zip)
## Post #39
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-10-15T20:27:46+00:00
- Post Title: 

> Reply from thomasdxyz
>
> Hello I am new in this great Forum!

I need help! The Just Cause PLUGIN donÂ´t work on my PC i allways get the message PGN NOT VALID! And in the lower left corner stands, not a multiex commander plugin!

I hope someone can help me, i have try to reinstall my Microsoft Office but i doesnt help.

tom

Hi
I have the same problem:
always I tried to unpack Just Cause .arc files my Wyndows XP detect some problem and asked me to install Offyce (2000)
So I insert Offyce CD and install the missing part of... I do not know part of what)
Then I restart MEX and the plugin works fine....
## Post #40
- Username: hansdelord
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 15, 2006 11:19 pm
- Post datetime: 2006-10-16T18:02:45+00:00
- Post Title: 

version 1.1 works fine for me. thx goes to mr. mouse
## Post #41
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-16T18:19:49+00:00
- Post Title: 

know the plugin works! great work!

But what can i do with the *.mex files?
## Post #42
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-16T18:31:00+00:00
- Post Title: 

> Reply from thomasdxyz
>
> know the plugin works! great work!

But what can i do with the *.mex files?

That's up to you. As there are no filenames available, they have just generic names. *.mex just means that MexCom was used to extract them. You should now find out what they are. But that is entirely up to you and others that wish to help you out.
## Post #43
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-16T20:44:24+00:00
- Post Title: 

> That's up to you. As there are no filenames available, they have just generic names. *.mex just means that MexCom was used to extract them. You should now find out what they are. But that is entirely up to you and others that wish to help you out.

And how can i find this out which mex file stands for?
## Post #44
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-18T21:06:21+00:00
- Post Title: 

By exploring with a Hex editor. 

The other ARC files you can also open with the plugin, I've seen them and they are SARC files, which are supported . Those do have filenames.
## Post #45
- Username: thomasdxyz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 14, 2006 5:19 am
- Post datetime: 2006-10-20T18:51:18+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> By exploring with a Hex editor. 

The other ARC files you can also open with the plugin, I've seen them and they are SARC files, which are supported . Those do have filenames.

Hi,

Thank you for your help!!! But i have never worked with an hex editor. when i open a mex file with an hex editor how can i see what a file type it is? 

i just see many numbers   

please help me
## Post #46
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-20T19:02:54+00:00
- Post Title: 

Ah, yes, so this would be a great opportunity to read our Definitive Guide on Exploring File Formats first, before you use the Hex editor. The first chapters explain a lot for you then. Read it here:

[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF)
## Post #47
- Username: Infinity
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Sep 09, 2006 11:42 pm
- Post datetime: 2006-10-29T00:00:32+00:00
- Post Title: 

Mr.Mouse - What this    ( i test in full version game )
[JC.PNG](https://xentaxbackup.github.io/file/956_JC.PNG)
## Post #48
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-29T06:34:57+00:00
- Post Title: 

I have no idea. Are all of the files in the pc0.arc archive like that? Or only some. (I you wish,you can save the table of contents in File and attach it here)
## Post #49
- Username: Infinity
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Sep 09, 2006 11:42 pm
- Post datetime: 2006-10-30T20:57:59+00:00
- Post Title: 

Oke attached 
[pc.rar](https://xentaxbackup.github.io/file/960_pc.rar)
## Post #50
- Username: JagXIII
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 05, 2006 7:21 am
- Post datetime: 2006-11-04T23:57:54+00:00
- Post Title: 

Thanks Mr Mouse for your great plugin but it seems to me the reason they are all no name is because the UK/US retail pclist.txt is blank and like you said the names will not show. Must be just the demo pclist.txt that has info in it.
## Post #51
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-05T00:39:54+00:00
- Post Title: 

Yeah, that is correct, but I think he meant that those files all have the same offset and size in the archive (the ones in the picture he attached).

I need the Table Of Contents from within MultiEx Commander, Infinity! Not the tab file!
## Post #52
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-06T00:41:08+00:00
- Post Title: 

I didnÂ´t understand anithyng

IÂ´m brasilian and i want to extract the pc0.arc help me
## Post #53
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-06T00:55:57+00:00
- Post Title: 

I want to open a file "noname0.mex"
[just cause.JPG](https://xentaxbackup.github.io/file/962_just cause.JPG)
## Post #54
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-07T13:08:58+00:00
- Post Title: 

help me please
## Post #55
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-07T13:34:44+00:00
- Post Title: 

What's the problem? Extract the .mex file and open it in a Hex Editor (Like Hex Workshop). There are apparently no filenames saved in the pc0.arc archive, that's why they are called nonamexxx.mex. If you meant for us to have a look at the noname0.mex file then please zip it and attach it here. 

If you don't understand, perhaps Savage or Dinoguy can ask you in Spanish what you actually want.
## Post #56
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-07T14:00:16+00:00
- Post Title: 

I open with hex workshop but have many words there
## Post #57
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-07T14:34:35+00:00
- Post Title: 

Yes, the next step is to identify the file type this way. Perhaps someone can help you, just attach that .mex file here. I don't have the time to go around identifying each file type you extract from the.arc. My job is identifying resouce archive formats mostly.
## Post #58
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-07T14:40:01+00:00
- Post Title: 

nonam0.mex
[noname0.rar](https://xentaxbackup.github.io/file/963_noname0.rar)
## Post #59
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-07T21:22:55+00:00
- Post Title: 

can you help me mr.mouse
## Post #60
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-08T06:47:20+00:00
- Post Title: 

I've looked briefly at the file, can't identify it, sorry.
## Post #61
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-08T10:34:58+00:00
- Post Title: 

oh men, what i do??
## Post #62
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-08T10:40:12+00:00
- Post Title: 

i didnÂ´t download any file from here, only the Just_Cause.dll to open the ARC files.


I have to download the pc.tab????
I dontÂ´t have anything in my pclist.txt
## Post #63
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-09T13:15:08+00:00
- Post Title: 

i have just cause for PC help me
## Post #64
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-15T12:53:32+00:00
- Post Title: 

i have this files noname0
[PC0.arc (noname0).rar](https://xentaxbackup.github.io/file/983_PC0.arc (noname0).rar)
## Post #65
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-15T12:56:05+00:00
- Post Title: 

noname0
[PC1.arc (noname0).rar](https://xentaxbackup.github.io/file/984_PC1.arc (noname0).rar)
## Post #66
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-15T12:56:41+00:00
- Post Title: 

noname0.mex
[PC2.arc (noname0).rar](https://xentaxbackup.github.io/file/985_PC2.arc (noname0).rar)
## Post #67
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-15T12:57:15+00:00
- Post Title: 

noname0.mex
[PC3.arc (noname0).rar](https://xentaxbackup.github.io/file/986_PC3.arc (noname0).rar)
## Post #68
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-15T12:57:49+00:00
- Post Title: 

noname0.mex
[PC4.arc (noname0).rar](https://xentaxbackup.github.io/file/987_PC4.arc (noname0).rar)
## Post #69
- Username: guitutilo
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Nov 06, 2006 8:38 am
- Post datetime: 2006-11-15T12:58:41+00:00
- Post Title: 

I have many nonameÂ´s in may game in this noname files have a SARC, wath i do??
## Post #70
- Username: Ceej
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 30, 2007 5:58 am
- Post datetime: 2007-03-16T00:04:28+00:00
- Post Title: 

I am trying to extract the music in archive Just Cause\PC\SFX\Music\music.sab I get the "PGN Invalid" error.

There is no tab or text file... can someone help me out here with those text/tab files/whatever? I am a complete nubcake with no idea how to edit anything or hex anything or whatever.
## Post #71
- Username: flud
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 09, 2007 6:41 pm
- Post datetime: 2007-05-10T03:46:55+00:00
- Post Title: 

Plugin work ? or both
## Post #72
- Username: lmahesa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 13, 2007 10:06 pm
- Post datetime: 2007-08-14T18:42:26+00:00
- Post Title: 

Has anyone managed to get a full file listing for the arc files? I used filemon and the game looks for external files *IF* the .arc files aren't present, which means the game CAN be modded if the files can be extracted. Some of the unknown files are simple XML files, for example.
## Post #73
- Username: stinger
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 17, 2007 11:26 pm
- Post datetime: 2007-08-17T19:52:54+00:00
- Post Title: 

Hi,
I got idea. I have JC European version (oryginal) and file pclist.txt is empty. So maybe someone with US version could upload this file? Because I got only noname - files. And I want to find subtitles in that archives, but It seems that there are only game models, scripts and geometrics. Any ideas where are subtitles?

btw. Mr. Mouse you rock! But will you create an import function in your plugin? I think we all need that.
## Post #74
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T14:43:52+00:00
- Post Title: 

I have the same problem that everyone in the first few pages have been having. I get the invalid PGN error, I tried both versions of the plugins. Any ideas anyone?
## Post #75
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-29T06:01:15+00:00
- Post Title: 

THe plugin is almosrt 4 years old or so, so there's not much support for it. Anyway,. what OS are you using? Can you attach a debug.log file here? (press ctrl-d) and what version of the game are you using?
## Post #76
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-29T19:34:18+00:00
- Post Title: Re: Just Cause game .arc archives

> Reply from Mr.Mouse
>
> THe plugin is almosrt 4 years old or so, so there's not much support for it. Anyway,. what OS are you using? Can you attach a debug.log file here? (press ctrl-d) and what version of the game are you using?

Oh, it's 4 years old? Sorry if I'm bumping an old thread here. Anyways, I'm on Windows XP SP3. Here is the log:

```
-----------------------------------------
mc32, C:\Program Files\MultiEx Commander
4.3.1
-----------------------------------------
3/29/2010, 3:31:21 PM
3:31:21 PM[i]- Webupdate  User selected :0
3:31:22 PM[i]-  GetWebFile = 0
3:31:22 PM[i]-  C:\Program Files\MultiEx Commander\data\web.log
3:31:22 PM[i]- Check for update  0 new plugins, 0 new formats overall, and 56 formats removed.
3:31:22 PM[i]- MEX Open MRF  3:31:22 PM
3:31:22 PM[i]- MEX Open MRF  
3:31:23 PM[!]- RPM Parse FileInfo error 
3:31:23 PM[!]- RPM Parse FileInfo error 
3:31:23 PM[!]- RPM Parse FileInfo error 
3:31:23 PM[i]- RPM AddPlugins RPM at pluginmanager.dll for Beyond Good and Evil
3:31:23 PM[i]- RPM AddPlugins RPM at pluginmanager.dll for Prince of Persia
3:31:23 PM[i]- RPM AddPlugins RPM at pluginmanager.dll for Sid Meier's Pirates!
3:31:23 PM[i]- RPM AddPlugins RPM at pluginmanager.dll for Rahly's Test Archive
3:31:23 PM[i]- MexCom FindPlugins 
3:31:23 PM[i]- MexCom FindPlugins PGN at Just_Cause.dll for Just_Cause
3:31:23 PM[i]- PGN Register  Just_Cause.dll
3:31:23 PM[i]- PGN Connect  Just_Cause.archive
3:31:23 PM[i]- PGN Info  Just Cause .ARC and SARC Extractor,V:1.0,T:2,I:0,VR:3,RT:0,C:0
3:31:23 PM[i]- MexCom FindPlugins PGN at Snowy.dll for Snowy
3:31:23 PM[i]- PGN Register  Snowy.dll
3:31:23 PM[i]- PGN Connect  Snowy.archive
3:31:23 PM[i]- PGN Info  Snowy: Fish Frenzy ARF format Extractor,V:1.1,T:2,I:0,VR:3,RT:0,C:0
3:31:23 PM[i]- MexCom FindPlugins PGN at Age_Of_Empires_3.dll for Age_Of_Empires_3
3:31:23 PM[i]- PGN Register  Age_Of_Empires_3.dll
3:31:23 PM[i]- PGN Connect  Age_Of_Empires_3.archive
3:31:23 PM[i]- PGN Info  Age of Empires 3 BAR Files Extractor,V:0.9,T:2,I:0,VR:3,RT:0,C:0
3:31:23 PM[i]- MexCom FindPlugins PGN at Rayman3.dll for Rayman3
3:31:23 PM[i]- PGN Register  Rayman3.dll
3:31:23 PM[i]- PGN Connect  Rayman3.archive
3:31:23 PM[i]- PGN Info  Rayman 3 CNT Files Extractor,V:1.4,T:2,I:0,VR:3,RT:0,C:0
3:31:23 PM[i]- MexCom FindPlugins PGN at Commodore_64_disk_files.dll for Commodore_64_disk_files
3:31:23 PM[i]- PGN Register  Commodore_64_disk_files.dll
3:31:24 PM[i]- PGN Connect  Commodore_64_disk_files.archive
3:31:24 PM[i]- PGN Info  Commodore 64 D64 disk format Extractor,V:1.0,T:2,I:0,VR:3,RT:0,C:0
3:31:24 PM[i]- MexCom FindPlugins PGN at WWE.dll for WWE
3:31:24 PM[i]- PGN Register  WWE.dll
3:31:24 PM[i]- PGN Connect  WWE.archive
3:31:24 PM[i]- PGN Info  WWE Raw 2 FPK Files Extractor,V:1.0,T:2,I:1,VR:3,RT:0,C:0
3:31:24 PM[i]- MexCom FindPlugins PGN at Survival.dll for Survival
3:31:24 PM[i]- PGN Register  Survival.dll
3:31:24 PM[i]- PGN Connect  Survival.archive
3:31:24 PM[i]- PGN Info  Survival IDX/PAK format Extractor,V:1.0,T:2,I:0,VR:3,RT:0,C:0
3:31:24 PM[i]- MexCom FindPlugins PGN at TrainDriver2005.dll for TrainDriver2005
3:31:24 PM[i]- PGN Register  TrainDriver2005.dll
3:31:24 PM[i]- PGN Connect  TrainDriver2005.archive
3:31:24 PM[i]- PGN Info  Train Driver 2005 .JA Extractor by Rahly and Mr.Mouse,V:1.0,T:2,I:0,VR:3,RT:0,C:0
3:31:24 PM[i]- MexCom FindPlugins PGN at MXvsATVUnleashed.dll for MXvsATVUnleashed
3:31:24 PM[i]- PGN Register  MXvsATVUnleashed.dll
3:31:24 PM[i]- PGN Connect  MXvsATVUnleashed.archive
3:31:24 PM[i]- PGN Info  MX vs ATV Unleashed PAK format Extractor,V:1.7,T:2,I:1,VR:3,RT:0,C:1
3:31:24 PM[i]- MexCom FindPlugins PGN at Painkiller.dll for Painkiller
3:31:24 PM[i]- PGN Register  Painkiller.dll
3:31:24 PM[i]- PGN Connect  Painkiller.archive
3:31:24 PM[i]- PGN Info  Painkiller PAK Files Extractor,V:1.4,T:2,I:1,VR:5,RT:0,C:1
3:31:24 PM[i]- MexCom FindPlugins PGN at Sacrifice.dll for Sacrifice
3:31:24 PM[i]- PGN Register  Sacrifice.dll
3:31:24 PM[i]- PGN Connect  Sacrifice.archive
3:31:24 PM[i]- MEX Set language 
3:31:24 PM[i]-  - Main : Setting Variables 
3:31:24 PM[i]-  - Main : Preparing Datafile List Columns 
3:31:24 PM[i]-  - Main : Setting Additional Variables
3:31:24 PM[i]-  - Main : Loading SupportForm
3:31:24 PM[i]-  - Main : Setting FileFilter
3:31:24 PM[i]-  - Main : Enabling All
3:31:24 PM[i]-  - Main : Creating New Instance
3:31:24 PM[i]- Reinitializing MexCom  
3:31:24 PM[i]-  - Main : Showing Program
3:31:24 PM[i]-  - Main : BASS Init called.
3:31:25 PM[i]-  - Main : DevIL Init called.
3:31:51 PM[i]- Accessing archive 
3:31:51 PM[i]- Archive process format  PGN
3:31:51 PM[i]- PGN Calling 
3:31:51 PM[i]- PGN Register  C:\Program Files\MultiEx Commander\data\plugins\arc\Just_Cause.dll
3:31:51 PM[i]- PGN Connect  Just_Cause.archive
3:31:51 PM[i]- PGN Info  Just Cause .ARC and SARC Extractor version 1.0, type (2), importation(0), varsreturned(3), restypespec(0), cancreate(0)
3:31:53 PM[!]- PGN not valid  C:\Program Files\MultiEx Commander\data\plugins\arc\Just_Cause.dll
3:31:54 PM[i]- Reinitializing MexCom  

```


Unfortunately, there's only one version of the game. (1.0) It's disappointing they haven't patched it 

In terms of the error, perhaps you could try rebuilding the project in Visual Studio 2008? Maybe it's using some obsolete libraries. (That is if you even have the project anymore   )
