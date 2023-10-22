## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-13T14:49:39+00:00
- Post Title: Files extractors scripting

a quick question: what are ALL the current available solutions for writing file extractors for simple formats through scripting?

an example of which I'm aware is the mexcom scripting but if I'm not in error it doesn't support things like zlib/deflate decompression and XORing (correct me if I'm wrong) but most important it works only with the registered version of multiex (correct me here too if needed) so it must be not considered.

the idea of creating file extractors on the fly with any text editor "stimulates" a lot my brain but obviously it's useless to reinvent the wheel if already exists a good solution.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-13T16:06:58+00:00
- Post Title: Files extractors scripting

I love your Idea of writing a file extractor that could be customized through some type of xml file or settings dialog.
This would not be easy to complete but would be very worth it in the end. 
The only ripper that I know of is jaedernaub but I do not know how to add file formats to it.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-04-13T21:00:42+00:00
- Post Title: Files extractors scripting

Well you can use MexCom scripts with GameExtractor.
I personally played around with Lua with added binary operations some time ago.
## Post #4
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-14T00:00:48+00:00
- Post Title: Files extractors scripting

Need command line extractor looks like ext.exe ,ext.ini. 
It is useful when need repack.
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-14T03:37:39+00:00
- Post Title: Files extractors scripting

I think not exists a perfact extractor now.
My idea is looks like this:

At first define some struct of file format.
For example

-------------------------------
Type 1
-------------------------------
Head
MagicNumber     XXX bytes
FileNumber      XXX bytes
For each
  FilePathName  XXX bytes 
  00        1   bytes

Body
                XXX bytes
-------------------------------
Type 2
-------------------------------
MagicNumber     XXX bytes
FileNumber      XXX bytes
For each
  FilePathName  XXX bytes 
  offset        4   bytes
  length        4   bytes

Body
                XXX bytes
-------------------------------
Type 3
-------------------------------
FileNumber      XXX bytes
For each
  FilePathName  XXX bytes 
  offset        4   bytes
  length        4   bytes

Body
                XXX bytes

and so on

In the ext.ini your just to define the value of every protities of "FilePathName","offse" and so on and the extract TYPE .
The main logic is in the ext.exe.
I wish the tool be made in command line because it can be used in a translation patch to unpacking and repacking.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-14T22:25:17+00:00
- Post Title: Files extractors scripting

"if" I will work on the tool it will be fore sure in double mode: command-line tool if launched from the console (cmd.exe), minimalistic GUI if launched with double-click on the executable.

in the meantime I need to find the best way/format for the script, for example the idea of simply declaring the fields of the file format (so not programming the tool through the script but simply the structure of the file) and then let the tool to do the rest seems something very interesting.

well, for the moment dreaming doesn't cost anything :)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-16T20:35:38+00:00
- Post Title: Files extractors scripting

well I have some good news.
yesterday and today I have worked on the script parser and the results are so good that my beta version already works.

I have made it compatible with the BMS scripting language so people don't need to learn 1000 languages and then it's a good language.
obviously the BMS support has been enhanced so it's possible to use XOR, rot13, zlib/deflate, lzo, lzss plus various new operator in the "math" command (and, or, xor, complement, not, shift and modulus) and some other things like choosing the desired endianness.
then the input BMS script no longer needs the semicolon ';' and the file number which are now optional.

note that the BMS guide available on [http://wiki.xentax.com/index.php/BMS](http://wiki.xentax.com/index.php/BMS) doesn't report some additional fields which instead already exists like the GetCT, ComType and ReverseLong or some internals variables like EXTRCNT so I have tried to find and add also these ones.

about the new commands, the following is an example of BMS script for the game Outcry (you can call it outcry.bms or outcry.txt or as you want):

```
get FILES long

savepos NAMES_OFFSET
for i = 1 to FILES
    get FNAMESZ long
    getdstring  FNAME FNAMESZ
    get OFFSET  long
    get SIZE    long
next i

savepos FILES_OFFSET
goto NAMES_OFFSET
for i = 1 to FILES
    get FNAMESZ long
    getdstring  FNAME FNAMESZ
    get OFFSET  long
    get SIZE    long
    math OFFSET += FILES_OFFSET

    filexor 0xcc
    log FNAME OFFSET SIZE 0 0
    filexor 0
next i
```
as visible it's files are XORed with the byte 0xcc.

now the link to the beta version:

[http://aluigi.org/papers/quickbms.zip](http://aluigi.org/papers/quickbms.zip)

obviously it needs to be tested more because 2 days are not enough for a project like this which is not so basic so anyone is invited to test it and suggest new features.

P.S.: the usage is very simple and the following are some examples:
listing the files in the archive common.spk of outcry: 
```
quickbms -l outcry.bms c:\common.spk .
```

extracting the files in c:\folder: 
```
quickbms outcry.bms c:\common.spk c:\folder
```

extracing or listing only the dds files: 
```
quickbms -f "*.dds" outcry.bms c:\common.spk c:\folder
```
## Post #8
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-16T22:16:40+00:00
- Post Title: Files extractors scripting

Wow,it is a real good news!
If repacking is possible, it will be amazing.
I　will  think more fearure for it.
## Post #9
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-16T23:56:04+00:00
- Post Title: Files extractors scripting

Does it works when the file name table at the end of the file?
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-17T00:40:27+00:00
- Post Title: Files extractors scripting

if you know the size of the structure or where is located the particular value you are searching (for example some file formats have a 32bit number in the last 4 bytes which has the offset where are located the other file structures) you could use something like the following:

```
math OFFSET -= 4
goto OFFSET
get OFFSET long
goto OFFSET
...
```
"asize" is not available in the BMS guide but is supported by both multiex and my tool, it contains the total size of the file.
anyway tell me a file format which has the file name table at the end, it's good to make various exercises for testing the BMS language and where is possible to enhance it.

oh and about the "repacking" question, no it will be not supported

*EDIT*: updated version to 0.1.1 and attached 3 examples of BMS files which show different operations or different types for doing the same thing (7x7m.bms and 7x7m_special.bms)
[testbms.zip](https://xentaxbackup.github.io/file/1965_testbms.zip)
## Post #11
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-17T03:39:30+00:00
- Post Title: Files extractors scripting

File Format for test:
(Can you make a script for it?)

game name :
Evil Days of Luckless John

web:
[http://www.centauriproduction.com/raide ... casino.php](http://www.centauriproduction.com/raiders-of-the-lost-casino.php)

Version : 
Centauri Production Resource File 3.00 (not 3.01)

File Format: 
Header 
string Header; // "Centauri Production Resource File 3.00\n\n\0" 
int FilesCount; 
int TOCOffset; 

ToC 
string FileName; 
long FileTime; 
int isPacked; 
int Offset; 
int UnpackedSize; 
int PackedSize; 
int unk1; // Could be crc or something else.
## Post #12
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-17T03:49:36+00:00
- Post Title: Files extractors scripting

Another test file :
Dracula Origin

[viewtopic.php?f=10&t=3061&start=0&st=0& ... ula+Origin](http://forum.xentax.com/viewtopic.php?f=10&t=3061&start=0&st=0&sk=t&sd=a&hilit=Dracula+Origin)

Can you test your tool with this file and make a script sample?
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-17T13:24:28+00:00
- Post Title: Files extractors scripting

the script for Centauri is attached although I have tested it only with the gooka2 game (the only one for which there is a demo available on the centauri websites).

important note: don't use "int" as size specifier in the examples because in the BMS scripts "int" is used for the 16 bit fields while here you meant a 32 bit one. I tell you because this can create confusion (indeed my tool supports various aliases for these size identifiers like u32, u32, short, u16, 16, u8, 8 and so on).

no luck with the dracula origin format because the structure with the filenames is not clear and I guess it's the compressed block at the end of file. unfortunately at the moment there are no ways (in the BMS format) to parse formats which have the filename table compressed so maybe in future I will find an alternative solution/command if necessary.
[centauri.zip](https://xentaxbackup.github.io/file/1966_centauri.zip)
## Post #14
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-17T15:07:14+00:00
- Post Title: Files extractors scripting

Very thanks.

Some advice.
1. I think will have many updates for this tool,so can you add a -ver option to show the tool's version?

2. If the archive have 2 files ,one is index ,one is data,looks like abc.idx, abc.dat.
   Can this tool extract this kind of archive ?
  (For example:  So Blonde )
## Post #15
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-17T15:08:57+00:00
- Post Title: Files extractors scripting

For  test :

This game's file name table is at the end of the game.
Under cover: Operation Wintersun
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-17T15:30:31+00:00
- Post Title: Re: Files extractors scripting

the version is displayed when you launche the tool just after its name, for example:
"QuickBMS generic files extractor 0.1.2"

for the question about the index and data file the BMS language allows to use the "Open" command. basicly the first file that you must open is "ever" the data one (because the log and clog commands don't have a "filenumber" specifier) and then using "Open" to open the index file using the filenumber 1 and specifying it all the times you need to load data from it.

for the other 2 games now I take a look to them and I will let you know if they can be handled through the BMS language.
## Post #17
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2009-04-17T16:50:16+00:00
- Post Title: Re: Files extractors scripting

I'd be cautious about adding new features to MexScript, there's another forum member working on a [new version](http://forum.xentax.com/viewtopic.php?f=13&t=2208) of it.
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-17T16:52:35+00:00
- Post Title: Re: Files extractors scripting

the "so blonde" archive has been very useful because has allowed me to test the Open function and correcting some other bugs, the scripts for both the games are attached.
[bms.zip](https://xentaxbackup.github.io/file/1968_bms.zip)
## Post #19
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-18T00:27:59+00:00
- Post Title: Re: Files extractors scripting

How about the archive be compressed twice?
I means the archive has been compressed and the sub file is compressed too.
For example ,after extracing still life 2 Sl2fnt.dat ,i get a ARIAL 64.RU.
This file with string id XCPK ,so i think this file be compressed too.

Can you take a look it ?
[EXTDATASFONT.rar](https://xentaxbackup.github.io/file/1969_EXTDATASFONT.rar)
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-18T01:25:11+00:00
- Post Title: Re: Files extractors scripting

@Dinoguy1000:
uhmmm I have taken a quick look at that thread but it's stopped from years and then there are some things which are not so useful:
- 64 bit fields: handling a script already takes lot of cycles if compared to a native extraction program and handling 64 bit numbers on native 32 bit operating systems (the majority) takes a lot of more cycles and then the file formats which use 64 bit numbers are very very rare
- endianess on the number: uhmm doesn't look useful, the games use the same endianess for all the fields of the file so it's useless to specify each time the type of endianes to use
- 1000 fields: too chaotic
- complex Set+Math command: could be good in some occasions, thumb half up :)

@stevenx:
I don't have idea of the format used by those 2 files
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-18T02:30:30+00:00
- Post Title: Re: Files extractors scripting

> Reply from stevenx
>
> How about the archive be compressed twice?
I means the archive has been compressed and the sub file is compressed too.
For example ,after extracing still life 2 Sl2fnt.dat ,i get a ARIAL 64.RU.
This file with string id XCPK ,so i think this file be compressed too.

Can you take a look it ?

I did not try this but this may open your files.
[http://gbatemp.net/index.php?showtopic=109433](http://gbatemp.net/index.php?showtopic=109433)
## Post #22
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-18T03:00:33+00:00
- Post Title: Re: Files extractors scripting

Another test.

Posted to wrong thread.
[viewtopic.php?f=10&t=1476&p=28887#p28887](http://forum.xentax.com/viewtopic.php?f=10&t=1476&p=28887#p28887)
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-19T07:12:32+00:00
- Post Title: Re: Files extractors scripting

I personally think it's a great idea to 'fork' away from my original BMS script. I know that some people have implemented BMS as a way to increase the number of supported games (e.g. Watto has build in a nice BMS editor in his Java-built Game Extractor and there are also some linux implementations). Indeed, we as Xentax have at some point created OpenMex (Craptain did) in Python that also used the BMS language. At this time, Rahly is working on a new version of the language and when he finishes it, this will effectively replace my own BMS interpreter (multiex.dll) in MexCom. Nevertheless, I applaud you building on it, as there are many features to add (the original BMS is rather limited). 

Your QuickBMS tool looks a lot like my own 16-bit multiex.exe (Dos) that was the first implementation of BMS ever.  1997. LOL. 

By the way, ZLib IS supported. You can specify ComType ZLib1 in BMS. Then you must use the CLog instead of the Log command in MexScript to tell a little bit more about uncompressed size and compressed size and so on.

```

   Specify the compression type
   ZLib1 : Standard Zlib compression
   ComType <ComType>

    * CLog 

   when you have specified a compression type you MUST use
   this log event instead of 'Log'
   CLog <var name> <var offset> <var size> <var/num 
   offoff> <var/num sizeoff> 
   <var/num OrSize> <var/num OrSizeOff>

```
## Post #24
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-19T11:18:14+00:00
- Post Title: Re: Files extractors scripting

uhmmm my idea was not that of creating a fork (like a new derived language) but only an enhancement of the original BMS language otherwise there is the risk of having 1000 different and incompatible languages.
indeed the current BMS language is not bad because it can be used for all those file formats (the majority as visible in these threads) which are enough basic to avoid to write boring stand-alone extractors, so imho it's already good.

so the enhancements about I talk are mainly those in the BMS syntax for making it simpler to read like:
- avoiding the final semicolon
- optional filenumber (in the 90% of the cases it's ever 0)
- micro enhancements of some commands, for example a negative "pos" in "GoTo" could be used to specify a SEEK_END offset or making more clear the "substract" operation in the "String" command

for the rest I see only the need to implement some new commands for the usual operations which we have seen in the recent times for handling the so called "obfuscations" implemented by the games (like xor) and some new compressions (the first one is the standard deflate, which is zlib initialized with windowbits set to -15).

do you know where are visible (other than in the old thread linked by dinoguy) the improvements that rahly wants to add or is adding?
## Post #25
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2009-04-21T16:32:58+00:00
- Post Title: Re: Files extractors scripting

On the topic of semicolons, Mr.Mouse actually added the requirement for them at one point IIRC. He had originally planned the MexScript language to have support for multiple commands per line, but never did anything with it, so in one of the recent versions, he cleaned up the formatting related to it. IMHO, it actually feels far cleaner with terminating semicolons than without.
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-21T21:22:48+00:00
- Post Title: Re: Files extractors scripting

Can anyone show me how to write a script for this file. I have figured out the format I am just not good with the script. I would like to add scripts here if someone can show me this example. Thanks in advance.
I had to xor this file to get it in readable form how would I specify a fixed size to xor only that part?
The format details are in the lazeska thread.
[Character1.rar](https://xentaxbackup.github.io/file/1979_Character1.rar)
## Post #27
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-21T23:43:06+00:00
- Post Title: Re: Files extractors scripting

I have attached a script example.
note that handling that type of folder is not that easy so I have tried to use at least the last directory name found in the archive
I have also released a new beta of [QuickBMS](http://aluigi.org/papers/quickbms.zip)
[lazeska.zip](https://xentaxbackup.github.io/file/1980_lazeska.zip)
## Post #28
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-22T00:22:44+00:00
- Post Title: Re: Files extractors scripting

just for fun I have attached the script for listing and extracting the files from the ZIP archives, maybe it's a good example to learn how to use the scripts
[zip.zip](https://xentaxbackup.github.io/file/1981_zip.zip)
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-22T02:28:44+00:00
- Post Title: Re: Files extractors scripting

Thanks  the folder creation worked great and it seems to of extracted everything.
## Post #30
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-23T22:47:16+00:00
- Post Title: Re: Files extractors scripting

Is there a way to specify how long the xor operation will last in an archive. I manually xored the file table I posted then pasted it back into the original file and commented out the xor operation and your script worked perfectly. can I make the xor operation only apply to the file table, or when it reads a certain string it stops, or at a certain offset the xor stops? Thanks in advance for all your great work  any of these 3 methods would work for lazeska archive to stop the xor command.
## Post #31
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-24T08:20:54+00:00
- Post Title: Re: Files extractors scripting

the xor operation is like an interrupt: on or off.
it's applied to the read operations so if you use something like:
```
get NUM1 long
filexor ""
get NUM2 long
```
NUM1 will be read from the file and XORed with 0xaa while NUM2 is read as is

now imagine if lazeska had only the filename table XORed, in this case you needed to specify "filexor 0xaa" before "get FILEID long" and then "filexor """ ("" disable the xoring because it's an empty string of numbers) after "getdstring FILENAME 52"

exists also another idea, using the virtual MEMORY_FILE to pre-load the filename table (in this case you need to know its full size first) and then using it as an external file, the result is the same and avoids the continuous on/off of filexor

I will post more examples later, just yesterday I have added some feature which allowed me to replicate the spike girls files decoder using custom math operations applied to each single byte of the file
## Post #32
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-24T09:11:16+00:00
- Post Title: Re: Files extractors scripting

I like the XOR feature. It's simple yet effective. If you go on like this, I'll have to update my own multiex.dll !!
## Post #33
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-24T09:33:22+00:00
- Post Title: Re: Files extractors scripting

the only "limitation" I have seen in this interrupt-like solution is with nametables xored with multiple xor bytes.
for example if the name table is xored with 0x12 0x34 0x56 there is no problem to handle it but when we disable the xoring to dump the file (filexor "") we loose the current position inside the xor string (uhmm practically if the last position was at byte 0x34 when we will re-activate the xor it will start from 0x12).

so the only way at the moment for avoiding this problem is using the memory_file feature like in the following example:
```
log MEMORY_FILE NAMETABLE_OFFSET NAMETABLE_SIZE
filexor ""

get OFFSET long MEMORY_FILE
get SIZE long MEMORY_FILE
get NAME string MEMORY_FILE
...
```
I'm looking for other possible arguments to avoid this problem because obviously the same happens if the files are xored with multiple bytes and the nametable is clear or xored with another sequence
## Post #34
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-24T09:56:39+00:00
- Post Title: Re: Files extractors scripting

ok for solving the above issue I have specified the string of numbers as a sequence of fixes bytes while previously I declared it as a variable (it was useful in case of dynamic xor values but in the real world a similar obfuscation is not much used by the games) so the position is automatically handled inside the tool.
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-25T03:37:24+00:00
- Post Title: Re: Files extractors scripting

The contents of this post was deleted because of possible forum rules violation.
## Post #36
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-25T07:34:39+00:00
- Post Title: Re: Files extractors scripting

These are UNICODE strings.
## Post #37
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-25T10:04:07+00:00
- Post Title: Re: Files extractors scripting

```
# By Mr.Mouse 2009
IDString 0 "BPFS" ;
Get U1 Long 0 ;
Get LastOffset Long 0 ;
Get U2 Long 0 ;
Set Start Long 140 ;
GoTo Start 0 ;
Do ;
Get Dummy Long 0 ;
Get Dummy Long 0 ;
SavePos FOO 0 ;
Get Offset Long 0 ;
SavePos FSO 0 ;
Get Size Long 0 ;
Get FNSize Long 0 ;
Set Name String "" ;
For T = 1 to FNSize ;
GetDString A 1 0 ;
Get Dummy Byte 0 ;
String Name += A ;
Next T ;
Get U3 Long 0 ;
Get Date1 Long 0 ;
Get Date2 Long 0 ;
Get Date1 Long 0 ;
Get Date2 Long 0 ;
Get U4 Long 0 ;
Log Name Offset Size FOO FSO ;
Math Offset += Size ;
Set Start Long Offset ;
GoTo Start 0 ;
While Start <= LastOffset ;

```


This is my MexScript (BMS means actually "Binary MultiEx Script", which is the compilation of MexScript into a numeric format that legacy versions of multiex.dll could process. The current multiex.dll can also handle MexScript, but simply by parsing it into BMS. 

Anyway, the above script works and logs the correct filenames. 

Here's a few examples I could get out of them: 

data\gfx\char\musher_mari\ani\mari_anim.h

```
// animations stored in the associated KFM file. Include this file in your
// final application to easily refer to animation sequences.

#ifndef MARI_ANIM_H__
#define MARI_ANIM_H__

namespace mari_Anim
{
    enum
    {
        EAT_FOOD                = 330,
        EMOTION_ANGER001        = 540,
        EMOTION_FAIL001         = 510,
        EMOTION_GIGGLE001       = 530,
        EMOTION_GLAD001         = 500,
        EMOTION_HI001           = 520,
        IDLE_CONTAINER001       = 321,
        IDLE_FOR_WEBSITE        = 1020,
        IDLE_GESTR001           = 240,
        IDLE001                 = 230,
        IDLE002                 = 234,
        IDLE003                 = 235,
        OPEN_CONTAINER          = 320,
        PROLG_CROUCH_IDLE       = 1030,
        RETIRED                 = 270,
        RETIRED_IDLE            = 271,
        RUN                     = 231,
        RUN_LOOKBACK            = 233,
        SHIVERING               = 820,
        SLED_BRAKE              = 253,
        SLED_BRAKE_TO_IDLE      = 254,
        SLED_GETOFF             = 251,
        SLED_GETON              = 250,
        SLED_HIGHSPD            = 221,
        SLED_HIGHSPD_JUMP       = 131,
        SLED_HIGHSPD_LEFT       = 223,
        SLED_HIGHSPD_RIGHT      = 222,
        SLED_IDLE               = 11,
        SLED_IDLE_GESTR001      = 12,
        SLED_IDLE_GESTR002      = 13,
        SLED_IDLE_TO_NOMALSPD   = 1,
        SLED_IDLE_TO_TURNLEFT_END = 22,
        SLED_IDLE_TO_TURNLEFT_HOLD = 21,
        SLED_IDLE_TO_TURNLEFT_START = 20,
        SLED_IDLE_TO_TURNRIGHT_END = 25,
        SLED_IDLE_TO_TURNRIGHT_HOLD = 24,
        SLED_IDLE_TO_TURNRIGHT_START = 23,
        SLED_LOWSPD             = 201,
        SLED_LOWSPD_JUMP        = 111,
        SLED_LOWSPD_LEFT        = 203,
        SLED_LOWSPD_RIGHT       = 202,
        SLED_LOWSPD_TO_IDLE     = 2,
        SLED_NORMALSPD          = 211,
        SLED_NORMALSPD_JUMP     = 121,
        SLED_NORMALSPD_LEFT     = 213,
        SLED_NORMALSPD_RIGHT    = 212,
        SLED_NORMALSPD_TO_BRAKE = 252,
        SLED_PEDALING           = 200,
        SLED_RETIRED            = 260,
        SLED_RETIRED_IDLE       = 261,
        SLED_SHIVERING          = 810,
        SLED_USE_CAMERA         = 341,
        TALK_GESTR001           = 400,
        USE_CAMERA              = 340,
        USE_PICKAXE             = 300,
        USE_SHOVEL              = 310,
        WALK                    = 232
    };
}

#endif  // #ifndef MARI_ANIM_H__

```


Cursors from the data.016.pak:



cursors_extracted.JPG (25.37 KiB) Viewed 1097 times
## Post #38
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-25T10:38:19+00:00
- Post Title: Re: Files extractors scripting

the 8 bytes are not at the end of the file block but at its beginning (so before Get Offset Long), indeed the last file is not catched.
## Post #39
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-25T11:19:57+00:00
- Post Title: Re: Files extractors scripting

> Reply from Bugtest
>
> the 8 bytes are not at the end of the file block but at its beginning (so before Get Offset Long), indeed the last file is not catched.

Ah yes, I had forgotten that they were at the beginning of the file. I've adapted the above script accordingly. The last file WAS catched, by the way, but not correctly  The 
```
While Start <= LastOffset ; 
```
 made sure the while loop stopped after processing the last file.
## Post #40
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-25T13:58:32+00:00
- Post Title: Re: Files extractors scripting

That looks perfect Mr.Mouse thanks for the help with this file format
## Post #41
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-25T16:02:36+00:00
- Post Title: Re: Files extractors scripting

finally I have released [QuickBMS](http://aluigi.org/papers.htm#quickbms) to public so it's no longer in the beta stage.
I have also added the support for unicode strings (UTF-16 in both little and big endian form) in "Get" and for unicode->string conversion in "Set".

so the Husky Express script can be also like [this example](http://aluigi.org/papers/bms/husky_express.bms)
## Post #42
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-26T11:55:15+00:00
- Post Title: Re: Files extractors scripting

Thanks Bugtest this script worked great now I can try to compare the 2 scripts and hopefully learn how to convert them between each other.
## Post #43
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-26T12:54:52+00:00
- Post Title: Re: Files extractors scripting

Well, apart from the UNICODE string handling, the scripts are comparible. My script loads up a few more variables from the archive (I do this so I remember what I thought the format was like at the time I worked on it). Bugtest's script is straight to the point of extracting.
## Post #44
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-29T19:25:19+00:00
- Post Title: Re: Files extractors scripting

well, finally a new [version](http://aluigi.org/papers.htm#quickbms) :)
other than the usual corrections I have added support for the PKWare Data Compression Library (also known as explode), lzma and gzip.
indeed all these 3 compressions or file formats (like in the case of gzip which is just deflate) are used in some games so was necessary to implement them, an example is [Assaurl Heroes](http://aluigi.org/papers/bms/assault_heroes.bms).

if someone is aware of other libraries commonly used in game and non-game archives they are welcome.
it's important that they are well used libraries because algorithms like lzw are totally useless due to the existence of 1000 variants.

just for remaining in theme of libraries, is someone aware of games/archives which use [UCL/NRV](http://www.oberhumer.com/opensource/ucl/)?
it's used to compress the executables through the UPX tool but I have never heard of it used in other fields.
## Post #45
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-29T23:18:54+00:00
- Post Title: Re: Files extractors scripting

is it possible to support this SLZ compression?
Here someone documented the format specifications.
[http://www.romhacking.net/forum/index.p ... 790.0.html](http://www.romhacking.net/forum/index.php/topic,7790.0.html)
This is used in all the games from that publisher and it would be great to get at those archives.
I can post archives from these if you think it will not be to much trouble to implement / if you want to add support.
Just let me know and Ill post some archives.
## Post #46
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-30T17:33:54+00:00
- Post Title: Re: Files extractors scripting

LZSS is already implemented in QuickBMS because it's an enough standard algorithm where the only possible variants are some settings in it but I guess nobody modifies them.

while the LZSS+RLE specified in that post doesn't sound much "standard".
## Post #47
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-30T23:36:57+00:00
- Post Title: Re: Files extractors scripting

The contents of this post was deleted because of possible forum rules violation.
## Post #48
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-30T23:59:39+00:00
- Post Title: Re: Files extractors scripting

it's a big endian archive so it's enough to specify "endian big" at the beginning and any numeric "Get" operation will be automatically performed with the needed endianess :)

```
idstring "\0CRA"    # "ARC\0" big endian
get VERSION short
get FILES short

for i = 0 < FILES
    getdstring NAME 64
    get TIMESTAMP long
    get ZSIZE long
    get SIZE long
    get OFFSET long

    clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #49
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-01T02:16:07+00:00
- Post Title: Re: Files extractors scripting

Ah thanks very much 
I was wondering what this archive type was called.
The script works great.
## Post #50
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-04T01:11:02+00:00
- Post Title: Re: Files extractors scripting

I made a script for this game

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "2CCPPACK"
    get FILES long
    math FILES -= 1

for i = 0 < FILES
getdstring NAME 32
get ZSIZE long
get COMPRESSED long #either a 0 or 1 seems to always be 1
get SIZE long
get OFFSET long
get NULL long # always 00000000

    if COMPRESSED == 0
        log FULLNAME OFFSET SIZE
    else
        clog FULLNAME OFFSET ZSIZE SIZE
    endif
next i
```


game website
[http://www.2ccp.com/dysnomia/top.html](http://www.2ccp.com/dysnomia/top.html)

Is it possible to do byte swapping in quickbms?
what i mean is take AB CD EF and make it BA DC FE
thanks in advance for any help
## Post #51
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-04T09:44:54+00:00
- Post Title: Re: Files extractors scripting

uhmmm the example you showed is not byte swapping.
byte swapping is when you have a 32/24/16 bit number and you reverse the order of its bytes while in your case it's a 4 bit swapping.
anyway that type of swapping can be done with:

```
math TMP &= 0x0f
math BYTE &= 0xf0
math BYTE ^= TMP
```
so if this type of obfuscation is implemented on each file you must save each file in the memory buffer, performing these operations and then saving it on the disk like the following example:

```
for j = 0 < SIZE
    getvarchr BYTE MEMORY_FILE j
    set TMP BYTE
    math TMP &= 0x0f
    math BYTE &= 0xf0
    math BYTE ^= TMP
    putvarchr MEMORY_FILE j BYTE
next j
log "myfilename.dat" 0 SIZE MEMORY_FILE
```
## Post #52
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-04T19:05:52+00:00
- Post Title: Re: Files extractors scripting

I got a request for an extractor for this game from Kataah
The google translation of the title is
The three question marks - the cursed castle (PC)
here is the website
[http://www.usm.de/produkte/cd-rom-dvd-r ... hloss.html](http://www.usm.de/produkte/cd-rom-dvd-rom/kinder-jugend/spiel/single-spiel/product/neuheiten/die-drei-das-verfluchte-schloss.html)
the file is just a zip file xored with 0x55

bms script

```
ComType deflate
for i = 0 to 0x7FFFFFF
    idstring "PK\x03\x04"
    # get sign long
    # if sign != 0x04034b50
    #     cleanexit
    # endif

    get ver         short
    get flag        short
    get method      short
    get timedate    long
    get crc         long
    get comp_size   long
    get uncomp_size long
    get name_len    short
    get extra_len   short
    getdstring name     name_len
    getdstring extra    extra_len

    savepos offset
    CLog name offset comp_size uncomp_size
    math offset += comp_size
    goto offset
next i

```
## Post #53
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-05-04T19:34:04+00:00
- Post Title: Re: Files extractors scripting

thx chrrox
## Post #54
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-05T00:30:13+00:00
- Post Title: Re: Files extractors scripting

I am trying to extract the game WFFM Online I know what I want quick bms to do but I do not know how to write the script.
here is what I have so far.

```
#getdstring FILES 3
#getdstring POSITION 3
#math POSITION += 30
#goto - POSITION
goto 16416
getdstring DUMMY 10
for i = 0 < 50
get NULL long
get OFFSET long
get SIZE long
get VAR short
getdstring NAME 15

log NAME OFFSET SIZE
next i

```

from what I have gathered from the archive is there is a header file and a storage file.
the .tbl is the storage and the .data is the container of the uncompressed data.
in the table file it starts with DIR then there are 3 bits not bytes that I think might be the total number of files in an archive it could be a little later on in the header also I am not sure yet.
then I know the next 3 bits represent the start of the file table from the end of the file and then add 30 to that.
so we go to the end of the file and go back bye that string and then we add 30 to that string to get the offset of the file table.
next there is a dummy 10 bytes called dummy.txt\0
then it is a fairly strait forward file structure until it comes to the names the names are always 14 or 20 bytes in length
what I need to do is if it reads the dstring and it is greater than 14 set the length to 20.
I hope this makes sense.

here are some sample files.
[http://www.MegaShare.com/854351](http://www.MegaShare.com/854351)

thanks in advance for anyone who can help me.
## Post #55
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-05T09:49:22+00:00
- Post Title: Re: Files extractors scripting

test the following:

```
open FDDE DATA 0

idstring 1 "DIR\x1a"
get TOTAL_SIZE long 1
get OFFSET long 1   # not sure
get FILES long 1

math OFFSET += 0x4000
goto OFFSET 1
get DUMMY long 1

for i = 0 < FILES
    get DUMMY long 1    # don't know, the file doesn't seem compressed
    get OFFSET long 1
    get SIZE long 1
    get NAME string 1
    padding 4 1

    log NAME OFFSET SIZE
next i
```
## Post #56
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-05T22:09:14+00:00
- Post Title: Re: Files extractors scripting

That worked great thanks a million 
here is a link to the game wffm online
[http://wffm.mgame.com/?mainMX=wffm](http://wffm.mgame.com/?mainMX=wffm)

I found another game from the same company with almost an identical format this is what I have
the game is Holic 2 Online
[http://holic2.mgame.com/?mainMX=holic2](http://holic2.mgame.com/?mainMX=holic2)

```
goto 4
get NULL long
get UNK1 long
get FILEEND long
get FTBLOFF long
get FTBLLENGTH long
get FILEEND2 long
get FILES long

math FTBLOFF += 4100
goto FTBLOFF

for i = 0 < FILES
get OFFSET long
get SIZE long
getdstring NAME 18 # i need it to pick up all 18 bytes then dump the 0's and keep the offset from the last 0

log NAME OFFSET SIZE
next i

```


The only thing I am stuck on is the names they are always 18 bytes reserved for the name but there is a varying amount of trailing 0's after the name ends.
Here is a sample archive.
[http://www.MegaShare.com/860055](http://www.MegaShare.com/860055)
## Post #57
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-05T23:50:01+00:00
- Post Title: Re: Files extractors scripting

here it's used also a sort of "relative padding" which wasn't used (at least not in the files you provided) in the other game... mah very strange, luckily I noticed it:

```
goto 12
get TOTAL_SIZE long
get INFO_OFFSET long
get TOTAL_SIZE long
get DUMMY long
get FILES long

math INFO_OFFSET += 0x1000
goto INFO_OFFSET

for i = 0 < FILES
    get DUMMY long
    get OFFSET long
    get SIZE long
    get NAME string

    savepos TMP_OFFSET  # horrible relative padding
    math TMP_OFFSET -= INFO_OFFSET
    math TMP_OFFSET %= 4;
    if TMP_OFFSET > 0
        set TMPSZ long 4
        math TMPSZ -= TMP_OFFSET
        getdstring DUMMY TMPSZ
    endif

    log NAME OFFSET SIZE
next i
```
## Post #58
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-06T00:40:33+00:00
- Post Title: Re: Files extractors scripting

Thanks so much  I think I figured out the texture format in this game they are dds files with their header removed I have pasted valid header files on them and they show up fine.
I think the models may also be direct x files missing their headers I will post anything more I learn from these files.
## Post #59
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-06T09:47:12+00:00
- Post Title: Re: Files extractors scripting

Very Interesting Scripts! I just wonder what is the "padding" in BMS means!

```
    padding 4 1
```


I can understandard in your second script, you can use the math method to jump over the variable padding

```
    math TMP_OFFSET -= INFO_OFFSET
    math TMP_OFFSET %= 4;
    if TMP_OFFSET > 0
        set TMPSZ long 4
        math TMPSZ -= TMP_OFFSET
        getdstring DUMMY TMPSZ
    endif
```


If "padding" do the same things as the above maths method, it will be a lot fool friendly them !
## Post #60
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-06T15:54:08+00:00
- Post Title: Re: Files extractors scripting

the Padding command does a very simple job, gets the current offset of the specified file (the second argument, 1 in that script) and checks if it's correctly padded to the size specified in the first argument.
so, for example, if the current offset is 23 and we choose a "padding 16" the current offset will become 32.

in the latest script is not possible to use the Padding command because the offsets are relative to the offset where are located the files informations, this is the first time I see a relative padding used in a file format so it's a very rare event
## Post #61
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T15:37:14+00:00
- Post Title: Re: Files extractors scripting

if someone follows this thread, I have just released a major version of [QuickBMS](http://aluigi.org/papers.htm#quickbms). hope you like it
## Post #62
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-09T18:25:09+00:00
- Post Title: Re: Files extractors scripting

The contents of this post was deleted because of possible forum rules violation.
[6D10AC88.rar](https://xentaxbackup.github.io/file/2018_6D10AC88.rar)
## Post #63
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T19:56:25+00:00
- Post Title: Re: Files extractors scripting

why "math FILES -= 1"?
the FILES value is correct as is because there are 2 files in the archive.
## Post #64
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-09T20:03:33+00:00
- Post Title: Re: Files extractors scripting

If I take that out it tries to read 3 files for some reason. It must be something I am doing wrong.
## Post #65
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T20:58:08+00:00
- Post Title: Re: Files extractors scripting

here it gets 2 files correctly.
then I saw you linked another game (VivaFighter) but I don't see the relationship with the GP4 files
## Post #66
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-09T21:25:40+00:00
- Post Title: Re: Files extractors scripting

when I run this command this is what I get

```

QuickBMS generic files extractor 0.1.3
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open G:\Viva\Resource\6D10AC88.gp4
- open G:\Viva\VIVA.bms

  offset   filesize   filename
------------------------------
  00000046 315        skeleton_die_effect.cfg
  00000181 101993     skeleton_die_effect.mb

- 2 files found

F:\Program Files\Audition>quickbms.exe -l G:\Viva\VIVA.bms G:\Viva\Resource\6D10AC88.gp4 .

QuickBMS generic files extractor 0.1.3
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open G:\Viva\Resource\6D10AC88.gp4
- open G:\Viva\VIVA.bms

  offset   filesize   filename
------------------------------
  00000046 315        skeleton_die_effect.cfg
  00000181 101993     skeleton_die_effect.mb
  6946696e 1866687852 SkillInfo]
ID = skeleton_die_effect
Kind = -1
SkillImpType = Model
A

- 3 files found

```

1st result is with the -= 1 the second is with that commented out.

The gp4 files are from viva fighter.
## Post #67
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T21:34:28+00:00
- Post Title: Re: Files extractors scripting

"QuickBMS generic files extractor 0.1.3"... the latest one is 0.2!!!
## Post #68
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-09T22:01:24+00:00
- Post Title: Re: Files extractors scripting

I am sorry I must of had an older copy on my hard drive. Thanks for clearing things up for me
## Post #69
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-11T13:02:58+00:00
- Post Title: Re: Files extractors scripting

The contents of this post was deleted because of possible forum rules violation.
## Post #70
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-13T02:41:49+00:00
- Post Title: Re: Files extractors scripting

I found a game with almost identical compression of Shaolin Plus Online.
The game is called Zodiac Online.
I almost have it figured out based on the Shaolin script but I am missing something.

> # Zodiac Online
>
> # script for QuickBMS http://aluigi.org/papers.htm#quickbms
>
> 
>
> goto 0x14
>
> get NSIZE long
>
> filexor 0x99
>
> getdstring NAME NSIZE
>
> filexor ""
>
> get ZSIZE long
>
> get SIZE long
>
> getdstring DUMMY 12
>
> savepos OFFSET
>
> #get ZSIZE asize
>
> #math ZSIZE += OFFSET
>
> 
>
> comtype LZO1X
>
> clog NAME OFFSET ZSIZE SIZE
here is a file attached.
[Magic_C03.rar](https://xentaxbackup.github.io/file/2031_Magic_C03.rar)
## Post #71
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-13T09:51:26+00:00
- Post Title: Re: Files extractors scripting

Hi Chrrox, there is nothing wrong with your extracted file in Magic_C03.tg_ actually!
It just missing header! If you add a classic TGA header then It will be fine.
And I guess the value @0x2D (04) will be bytes-per-color!!

```
00000010   20 00                                               
```


By the way, how do you know it's LZO compressed? (I am always interested in LZO) 

PS: bugtest, Is is possible to add data(like tga header above) in QuickBMS?
[Magic_C03.jpg](https://xentaxbackup.github.io/file/2032_Magic_C03.jpg)
## Post #72
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-13T13:21:13+00:00
- Post Title: Re: Files extractors scripting

uhmmm at the moment don't exist ways (or easy ways) to put custom data inside the output file because the BMS language doesn't have rules for editing memory.
so the only easy way is creating a file containing the header you want to add (for example the bytes you specified in your post) and then:

```
open FDSE "header_file.dat" 1
get HEADER_FILE_SIZE asize 1
...
    log NAME 0 HEADER_FILE_SIZE 1
    log NAME OFFSET SIZE
...
```

if you copy the content of "header_file.dat" in a MEMORY_FILE you can also edit it (for example if you want to add a RIFF header you need to modify at least the 2 fields containing the size of the data and riff blocks) but at the moment GetVarChr and PutVarChr works only on single bytes so it's boring to handle 32bit fields like in the RIFF example.

so in the next version I will add two things for doing this job on the fly:
- adding the possibility of filling the MEMORY_FILE with custom data directly inside the BMS script (for example "Set MEMORY_FILE binary "\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x01\x20\x00")
- adding a datatype value in Get/PutVarChr for being able to handle any 8, 16, 32bit and string value making it complete
## Post #73
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-14T21:48:54+00:00
- Post Title: Re: Files extractors scripting

Here is a game called astro ranger
[http://astroranger.com/](http://astroranger.com/)
it is like ddr meets power rangers I guess but I wrote an extractor for this game to see what was in there.
where else can you find a game that has the original Japanese sailor moon theme song in it lol.

```
get VERSION long
get FILES long
get NULL long

for i = 0 < FILES
getdstring NAME 0x80
get SIZE long
get ZSIZE long
get OFFSET long

clog NAME OFFSET ZSIZE SIZE

next i

```


client [http://astro.nefficient.co.kr/astrorang ... client.exe](http://astro.nefficient.co.kr/astroranger/patchdb/astrorangerclient.exe)


edit
The only reason I knew it was that compression was bugtest had showed me a script for shaolin plus online that uses that compression and it seemed very familiar so I had a strong feeling it was that compression.
[npc_anchor_jolie_body.rar](https://xentaxbackup.github.io/file/2036_npc_anchor_jolie_body.rar)
## Post #74
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-15T01:23:40+00:00
- Post Title: Re: Files extractors scripting

Here is a script for ghostx online
[http://ghostx.gamengame.com/main.jce](http://ghostx.gamengame.com/main.jce)
this game is in english and uses custom smd models and normal png textures.

```

get VERSION long
goto 0x18
get FILES long

for i = 0 < FILES
get NLENGTH long
get OFFSET long
get SIZE long
get DUMMY long
getdstring NAME NLENGTH

savepos LOCATION

log NAME OFFSET SIZE

math LOCATION += SIZE
goto LOCATION

next i

```


[ext.rar](https://xentaxbackup.github.io/file/2039_ext.rar)
## Post #75
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-16T23:25:55+00:00
- Post Title: Re: Files extractors scripting

I am stuck on the game Love Beat Online. [http://lovebeat.plaync.co.kr/](http://lovebeat.plaync.co.kr/)

I have figured out most of it and I get the files to be listed correctly but I can not extract the files.
Here is what I have so far.

```
get VERSION long
get FILES long
goto 0x15
math OFFSET += 0x208
math OFFSET *= FILES
math OFFSET += 0x15
for i = 0 < FILES

getdstring NAME 0x200
get ZSIZE long
get SIZE long
comtype LZO1X
clog NAME OFFSET ZSIZE SIZE
math OFFSET += ZSIZE

next i

```

Here are some sample archives.
[sample1.rar](https://xentaxbackup.github.io/file/2042_sample1.rar)
## Post #76
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-17T00:36:26+00:00
- Post Title: Re: Files extractors scripting

the files are not compressed indeed it's enough the following script for extracting them:

```
goto 10
get FILES long
goto 0x15
for i = 0 < FILES
    getdstring NAME 0x200
    get SIZE long
    get OFFSET long
    log NAME OFFSET SIZE
next i
```
the problem is that the DDS files have the first 508 bytes (skipping the first 2) encrypted with a non "visibly recognizable" algorithm
## Post #77
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2009-05-20T08:12:24+00:00
- Post Title: Re: Files extractors scripting

Wombat (available at [http://www.szevvy.com](http://www.szevvy.com)) lets you do some basic operations on data through the script:

```
	folder: "Background Tiles"
	[16] (
		encryptedData SecretAgentXOR[8064] (

			data(3) unknown

			image EGA(
				width: 16
				height: 16
				dataSize: 8061
				tilesAcross: 4
			)
		)
	)
)

XORData: values (
	0x43, 0x6F, 0x70, 0x79, 0x72, 0x69, 0x67, 0x68, 0x74, 0x20, 0x31, 0x39, 0x39, 0x31,
        0x20, 0x50, 0x65, 0x64, 0x65, 0x72, 0x20, 0x4A, 0x75, 0x6E, 0x67, 0x63, 0x6B, 0x00)

script SecretAgentXOR (
	counter: 0

	[all] (

        read unsigned8 encryptedByte        

        #reverse the byte
        set encryptedByte: ((encryptedByte & 0x0F) << 4) | ((encryptedByte & 0xF0) >> 4)
        set encryptedByte: ((encryptedByte & 0x33) << 2) | ((encryptedByte & 0xCC) >> 2)
        set encryptedByte: ((encryptedByte & 0x55) << 1) | ((encryptedByte & 0xAA) >> 1)

        write unsigned8: encryptedByte ^ XORData[counter % 28]

        set counter: counter + 1
	)
)
```


This is for Secret Agent - decrypts and draws the tiles.  It also lets you do packed file extraction and so forth:

```
	files [size > 0] (
		FixedString(12) name
		unsigned32 offset
		unsigned32 size
	)
)
```


will list all files in a Duke Nukem 2 archive.
## Post #78
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-20T11:15:25+00:00
- Post Title: Re: Files extractors scripting

> Reply from Bugtest
>
> the problem is that the DDS files have the first 508 bytes (skipping the first 2) encrypted with a non "visibly recognizable" algorithm
Still wondering how that visual recognization works.
## Post #79
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-20T13:09:15+00:00
- Post Title: Re: Files extractors scripting

yeah I don't know to what I was thinking in that moment :)
I guess I referred to the usual xor and rot13 checks
## Post #80
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-20T13:40:10+00:00
- Post Title: Re: Files extractors scripting

Yeah but I can't imagine how to find out an encryption just by looking at the scrambled code
## Post #81
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-20T14:02:31+00:00
- Post Title: Re: Files extractors scripting

usually the archive files have often 00 bytes (or a most used byte) inside them so if you see a sequence of b8 b8 b8 in various zones of the examined block you can guess it's a xor or rot13 which involves the byte 0xb8 (or -0x48 in the case of rot13 decryption).

if you see a pattern of 8 bytes which is used in at least 2 zones it can be an ECB algorithm like blowfish where the same sequence of bytes (which fits the block size of the algorithm, like 8 for blowfish) gives ever the same result.
obviously you can't retrieve the key but at least you can have an idea of the encryption used on that file.

while if it's used an ivec (a sequence of bytes used to xor the resulted block and updated at each cycle) there is nothing visually recognizable.

so, yes, it's possible to figure an algorithm (completely or partially) only using the eyes and a dose of luck :)
## Post #82
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-20T14:48:16+00:00
- Post Title: Re: Files extractors scripting

> Reply from Bugtest
>
> while if it's used an ivec (a sequence of bytes used to xor the resulted block and updated at each cycle) there is nothing visually recognizable.
I like those ones 
[viewtopic.php?p=21276#p21276](http://forum.xentax.com/viewtopic.php?p=21276#p21276)
## Post #83
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-22T01:05:25+00:00
- Post Title: Re: Files extractors scripting

I can not figure out what I am doing wrong. The game is Dragon Nest Online.
I have extracted a single file no problem when I start before the first file and have it just extract that file but I can not figure out how to continue the pattern.
I set the files to 10 just for testing it should just go to the end of the file.
here is what I have.

```
#get FILES long
math FILES += 11
goto 0xC
for i = 0 < FILES
get ZIP long
getdstring NAME 0x100
get ZSIZE long
get SIZE long
getdstring NULL 0x14
savepos OFFSET
if ZIP == 1
clog NAME OFFSET ZSIZE SIZE
math OFF += ZSIZE
goto OFF
next i
else
log NAME OFFSET SIZE
goto OFFSET
next i

```

here is the header and footer of the archive.
[http://www.MegaShare.com/936627](http://www.MegaShare.com/936627)
Thanks in advance for any help
## Post #84
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-22T02:59:30+00:00
- Post Title: Re: Files extractors scripting

the format of the archive is enough clear, it's practically like the "binary" version of a recursing directory scanning (including "." and "..").
the problem is that it's a job for a recursive function because the bms scripts can't support it.

... anyway the attached script although looks horrible seems to do the job correctly :)

*edit* updated script in the next post
## Post #85
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-22T03:31:57+00:00
- Post Title: Re: Files extractors scripting

You sir are amazing.
It goes very far in the script but then I get this error.

```
  1b5e64a7 57368      Mapdata\Grid\Z_Test\Resource\Sound\Prop\Tile\Water\Trigger\Action\Condition\Ev
ent\Resource\Camera\Char\Monster\Basilisk\basilisk_shell\Bat\Beholder\Beholder_eye\BlackDragon\Broo\
Cerberos\Darkelf\Evil Roots\Gargoyle\Ghoul\Goblin\Goblin.msh
  1b5eadc9 174904     Mapdata\Grid\Z_Test\Resource\Sound\Prop\Tile\Water\Trigger\Action\Condition\Ev
ent\Resource\Camera\Char\Monster\Basilisk\basilisk_shell\Bat\Beholder\Beholder_eye\BlackDragon\Broo\
Cerberos\Darkelf\Evil Roots\Gargoyle\Ghoul\Goblin\Goblin01.dds
  1b609c8f 174904     Mapdata\Grid\Z_Test\Resource\Sound\Prop\Tile\Water\Trigger\Action\Condition\Ev
ent\Resource\Camera\Char\Monster\Basilisk\basilisk_shell\Bat\Beholder\Beholder_eye\BlackDragon\Broo\
Cerberos\Darkelf\Evil Roots\Gargoyle\Ghoul\Goblin\Goblin_Black.dds

- error in src\quickbms.c line 3053: dumpa()
Error: No such file or directory

```

I think this company liked folders a bit to much lol.
or is that error from name too long?
here is a section from where is stopped.
[http://www.MegaShare.com/936988](http://www.MegaShare.com/936988)
if you need a different section let me know and I can upload it did the program get stuck in the Z_test folder?

I put the extraction destination to a folder called 1 on the root of my drive and it got this far.

```
Cerberos\Darkelf\Evil Roots\Gargoyle\Ghoul\Goblin\GoldDragon\DG_Gold.msh
  1b8f6b8e 12484      Mapdata\Grid\Z_Test\Resource\Sound\Prop\Tile\Water\Trigger\Action\Condition\Ev
ent\Resource\Camera\Char\Monster\Basilisk\basilisk_shell\Bat\Beholder\Beholder_eye\BlackDragon\Broo\
Cerberos\Darkelf\Evil Roots\Gargoyle\Ghoul\Goblin\GoldDragon\DG_Gold.skn
  1b8f6d9d 2796368    Mapdata\Grid\Z_Test\Resource\Sound\Prop\Tile\Water\Trigger\Action\Condition\Ev
ent\Resource\Camera\Char\Monster\Basilisk\basilisk_shell\Bat\Beholder\Beholder_eye\BlackDragon\Broo\
Cerberos\Darkelf\Evil Roots\Gargoyle\Ghoul\Goblin\GoldDragon\gold.dds
  1ba17fae 92881      Mapdata\Grid\Z_Test\Resource\Sound\Prop\Tile\Water\Trigger\Action\Condition\Ev
ent\Resource\Camera\Char\Monster\Basilisk\basilisk_shell\Bat\Beholder\Beholder_eye\BlackDragon\Broo\
Cerberos\Darkelf\Evil Roots\Gargoyle\Ghoul\Goblin\GoldDragon\Golem\Golem.act

- error in src\quickbms.c line 3053: dumpa()
Error: No such file or directory

```


Edit2 Here is the section where I think it is different it is attached
[part.rar](https://xentaxbackup.github.io/file/2051_part.rar)
## Post #86
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-22T15:15:36+00:00
- Post Title: Re: Files extractors scripting

I guess I have understood what's the problem (probably), I used max 8 subfolders in the script while seems that the game use more subfolders so now I have set them to 20.
I don't know if this solves the problem but I guess that any file in the archive should be extracted correctly.
so test the attached new version
[dragon_nest_blah.zip](https://xentaxbackup.github.io/file/2052_dragon_nest_blah.zip)
## Post #87
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-22T20:08:48+00:00
- Post Title: Re: Files extractors scripting

The script did go further this time 
I think I see a pattern I believe when get NEXT_FOLDER long is == 0000 it goes backwards 2 directories
here is one part of the folder
F:\2\Mapdata\Grid\Z_Test\Resource\Sound\Prop\Tile\Water\Trigger\Event\Resource\Char\Monster\Wraith\NPC\Npc_Woman_Trader_May\Player\Archer\Parts\Cleric\Parts\
I think it should be
-----Mapdata
---Grid
--Z_Test
-----Resource
---Sound
--Prop
---Tile
--Water
---Trigger
--Event
-----Resource
---Char
--Monster
-Wraith
--NPC
-Npc_Woman_Trader_May
--Player
-Archer
Parts
-Cleric
Parts

There are other folders besides these in each directory and based on those folders and looking at some of the pattern I think this may be the case.
I have attached a section that should contain a few of these double back directories. I can upload the whole archive if need be just let me know.
Thanks again for all of your work 
[http://www.MegaShare.com/940686](http://www.MegaShare.com/940686)
## Post #88
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-23T23:04:44+00:00
- Post Title: Re: Files extractors scripting

Here is a file extractor for the game cars online.
I am not used to working with separate header files so I
pasted the header file on top of the main file to write this script.

```
math FILES += 0x28bc
for i = 0 < FILES
getdstring HASH 0x8
get OFFSET long
get SIZE long
math OFFSET += 0x28BD4
log NAME OFFSET SIZE
math NAME += 1
next i

```

This does not extract the file names as I can not figure out how they are stored. It appears they are stored every so many files in big edian format.
I will attach the header file and an index file if anyone is interested. the main file is called client.dat
website [http://cars.wasabii.com.tw](http://cars.wasabii.com.tw)
client link [http://dlcars.wasabii.com.tw/Cars_1.0.322.exe](http://dlcars.wasabii.com.tw/Cars_1.0.322.exe)
sample file
[http://upload.megashare.com/upload_succ ... 6388689087](http://upload.megashare.com/upload_success.php?tmp_sid=a49ca14c723beb3a2d5e3792b1d60b24&up_dir=336388689087)
## Post #89
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-26T21:58:19+00:00
- Post Title: Re: Files extractors scripting

Hi Bugtest,

A little problem here, I have a archive with some data in it. But there is no index-table. So what I have to do is to export the resources in between Headers!

I use "findloc" to search for each header and it works fine!
The only problem is the last resource! Because I can find the header anymore!

According to BMS wiki(I know its a bit different). 
If using "findloc" to search for a sting and can't find any. It will return 0
But QuickBMS just exit without any error!

I attached a example to make myself clear, sorry for my bad English!

In Fatduck.dat, there should have 3 resource! The header is "FatduckFile"
1 @ 0x0 length: 296
2 @ 0x128 length: 519
3 @ 0x32F length: 209 (failed to export this one)

The test.bms can only export the first two resource only!
No error, clean exit!
[findloc_sample.rar](https://xentaxbackup.github.io/file/2065_findloc_sample.rar)
## Post #90
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-26T23:38:00+00:00
- Post Title: Re: Files extractors scripting

I understand, practically you use the location of the next "FatduckFile" to calculate the size of the previous one... uhmmm yeah without knowing if there is another FatduckFile is available you can do nothing.

anyway the action in case findloc doesn't find the searched string is the termination, this has been confirmed in [this thread](http://forum.xentax.com/viewtopic.php?f=14&p=29395).

basicly now we have "FindLoc <var> <datatype> <text/number> [filenumber]" so it's needed to specify somewhere something which says to the script engine "hey don't terminate if you don't find this string".
adding another option parameter after filenumber sux so it must be excluded, the other arguments can't be touched and by default findloc must exit.
now get these parameters and if you solve this rubik cube I implement it in quickbms on the fly :)
## Post #91
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-27T00:33:52+00:00
- Post Title: Re: Files extractors scripting

can you go to end of file and add x bytes to the end like "fatduck"
and then process the file like normal?
not another - option just something in bms script like what fatduck did with the end of file only adding some bytes to the end so it will recognize it as a file.
## Post #92
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-27T00:53:06+00:00
- Post Title: Re: Files extractors scripting

for the previous post of chrrox: uhmmm simple solution but it's not logical (because at that returned offset is not located the searched string) and still incompatible with the current findloc standard behaviour.

while for the current one: modifying the input file manually is definitely not a good solution (it's just not a solution at all, it can be defined a work-around)
## Post #93
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-27T07:04:00+00:00
- Post Title: Re: Files extractors scripting

Is it possible to return a negative value rather then exit? eg: return -1 to the variable but not terminated the script! So we can at least do something to check and continue!

Another minor problem:

```
for i = 1 to 20
    set RES_NAME FName
    ...
    string RES_NAME += i
    log RES_NAME RES_START RES_OFFSET
next i

```


The i value is in Hexadecimal format! So the RES_NAME become:
File_1
File_2
...
File_9
File_0xa
File_0xb
File_0xc
...

Is it possible to export a decimal number?
## Post #94
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-27T12:28:22+00:00
- Post Title: Re: Files extractors scripting

the value that I would assign to the destination variable is not found is "" so that it's enough to use the following example:

```
if OFFSET == ""
    cleanexit # or anything else you want to do when the end of the file is reached
endif
```
but the problem is that the standard BMS language says that FindLoc must exit if the string is not found so the problem is differentiating the behavioiur of FindLoc keeping the compatibility with the standard command.
and idea could be a new command like FindLocX which returns "" instead of exiting but I don't know if it's a good idea to introduce a new custom command only for this thing.
## Post #95
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-27T15:02:25+00:00
- Post Title: Re: Files extractors scripting

about FindLoc I have opted for the additional argument after the file number.
practically if you specify -1 after the filenumber that value will be assigned to the variable if the string is not found, example:

```
if OFFSET == "bad_luck_man"
    cleanexit
endif
```
well it's a good compromise, so this is the solution available in the next version of quickbms
## Post #96
- Username: deve
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 22, 2009 4:56 pm
- Post datetime: 2009-05-27T22:05:49+00:00
- Post Title: Re: Files extractors scripting

is it possible to make quickbms also for packing back ?
## Post #97
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-28T02:48:25+00:00
- Post Title: Re: Files extractors scripting

Here is an extractor for FEZ (fantasy earth Zero)

```
get UNK long
for i = 0 < FILES
get NSIZE short
getdstring NAME NSIZE
get OFFSET long
get SIZE long

log NAME OFFSET SIZE
next i

```

this is a great archive format for som one to learn bms scripting from.
I attached a sample.
website [http://tw.fez.gamania.com/](http://tw.fez.gamania.com/)
installer [http://tw.dl.gamania.com/fez/FEZ_1103.exe](http://tw.dl.gamania.com/fez/FEZ_1103.exe)
this game uses textures with wrong headers mainly dds and some tga and some kind of .mdl format.
[Etc.rar](https://xentaxbackup.github.io/file/2069_Etc.rar)
## Post #98
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-28T17:13:19+00:00
- Post Title: Re: Files extractors scripting

The new version work great! Thank you Bugtest!

How about decimal output as I said a few post above?
## Post #99
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-28T17:27:46+00:00
- Post Title: Re: Files extractors scripting

ops I forgot that :)
uhmmm I could add an option for that (an option and not a command for not creating too much custom commands outside the BMS language).
practically internally quickbms converts all the numbers in 0xhexadecimal because it's more useful during scripts debugging so, yes, if necessary I can add an option which forces the myitoa() function to use the decimal notation.

oh I take the time also to say that I implemented some ways to add custom bytes (read "header") to the output files.
obviously it's not the most easy thing of the world just because it's not the job of the tool (something like a car which prepares the coffee) but works :)
the following is an example which builds a riff wave header in real time, like a raw_pcm to wav converter: [http://aluigi.org/papers/bms/raw2wav.bms](http://aluigi.org/papers/bms/raw2wav.bms)
## Post #100
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-05-31T09:59:59+00:00
- Post Title: Re: Files extractors scripting

Any clue/bms for Indiana Jones lego?   
[viewtopic.php?f=21&t=3068](http://forum.xentax.com/viewtopic.php?f=21&t=3068)
## Post #101
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-31T13:08:26+00:00
- Post Title: Re: Files extractors scripting

> Reply from Savage
>
> Any clue/bms for Indiana Jones lego?   
viewtopic.php?f=21&t=3068

Here is an exe scan of the game. I am not familiar with this algorithm / compression.

```

Signsrch 0.1.4
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
  optimized search function from Andrew http://www.team5150.com/~andrew/

- open file "F:\Program Files\LEGO Indiana Jones\Indiana_Jones_GameExplorerHelper.dll"
- 111912 bytes allocated
- load signatures
- open file C:\signsrch\signsrch.sig
- 1294834 bytes allocated for the signatures
- 1869 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  0001a076 188  SSH RSA id-sha1 OBJ.ID. oiw(14) secsig(3) algorithms(2) 26 [..15]
  00013daa 1784 anti-debug: IsDebuggerPresent [..17]

- 2 signatures found in the file

C:\signsrch>signsrch.exe "F:\Program Files\LEGO Indiana Jones\LEGOIndyDEMO.exe"

Signsrch 0.1.4
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
  optimized search function from Andrew http://www.team5150.com/~andrew/

- open file "F:\Program Files\LEGO Indiana Jones\LEGOIndyDEMO.exe"
- 7488808 bytes allocated
- load signatures
- open file C:\signsrch\signsrch.sig
- 1294834 bytes allocated for the signatures
- 1869 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  00723076 188  SSH RSA id-sha1 OBJ.ID. oiw(14) secsig(3) algorithms(2) 26 [..15]
  00504e52 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]
  00317ead 567  classical random incrementer 0x343FD 0x269EC3 [32.le.8&]
  00432c48 862  Generic bitmask table [32.le.128]
  005300e0 1188 Vorbis FLOOR1_fromdB_LOOKUP [float.le.1024]
  00136b19 1783 anti-debug: Dongle protection [..3]
  0058e68a 1784 anti-debug: IsDebuggerPresent [..17]
  00432c4c 1827 bitmask [32.le.128]

- 8 signatures found in the file
```
## Post #102
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-31T16:36:42+00:00
- Post Title: Re: Files extractors scripting

the archive of that game is horrible, it's composed by various chunks but the PNTR one is not like the others... blah
## Post #103
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-06T04:26:56+00:00
- Post Title: Re: Files extractors scripting

Fighters Club Online
This game uses nif files so you can view all the models and their animations.
website
fc.kog.co.kr/main.aspx
client
[http://download.kog.co.kr/FC_Install/Fi ... lubCB1.exe](http://download.kog.co.kr/FC_Install/FightersClubCB1.exe)

quickbms script.

```
get FILES long
get UNK long
math LENGTH += 0x10c
math LENGTH *= FILES
MATH LENGTH += 0x3C

for i = 0 < FILES
getdstring NAME 0x100
get SIZE long
get ZSIZE long
get OFFSET long
math OFFSET += LENGTH

clog NAME OFFSET ZSIZE SIZE

next i

```
## Post #104
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-07T21:17:57+00:00
- Post Title: Re: Files extractors scripting

@fatduck
I have just added the -D option which uses the decimal notation internally in quickbms so your doubt problem be solved.
## Post #105
- Username: Gocha
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-05T15:31:59+00:00
- Post Title: Re: Files extractors scripting

9th Company: Roots of Terror


```
#QuickBMS Script
idstring "SMA\ 2\ 0"
get files long
get FTABLEEND long
for i = 0 < files
get NSIZE byte
getdstring NAME NSIZE
get SIZE long
get ZSIZE long
get offset long
clog NAME OFFSET ZSIZE SIZE
next i 
```
## Post #106
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-11T02:17:04+00:00
- Post Title: Re: Files extractors scripting

Wind Fantasy Online
I am lazy so you must paste the index file at the end of the archive to extract the file but then it works. I will work on learning how to work with memory files better.
[http://ago.gameflier.com/](http://ago.gameflier.com/)
This game uses an unknown "to me" image format and 3d model format.


```
math FILES += 470
comtype inflate
for i = 0 < FILES
getdstring UNK 0x14
get ZSIZE long
get SIZE long
get NSIZE long
getdstring UNK2 0xA
get OFFSET long
getdstring NAME NSIZE
clog NAME OFFSET ZSIZE SIZE
next i

```
## Post #107
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-11T03:24:52+00:00
- Post Title: Re: Files extractors scripting

Final Quest Online
[http://fq.space.co.kr/](http://fq.space.co.kr/)


```
goto 0x200
get UNK1 long
get SIZE long
get ZSIZE long
get UNK2 long
savepos OFFSET
get NAME filename
string NAME -= 4
set EXT STRING ".png" 
string NAME += EXT
clog NAME OFFSET ZSIZE SIZE
next i

```
## Post #108
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-11T03:32:10+00:00
- Post Title: Re: Files extractors scripting

Cars Online
[http://cars.wasabii.com.tw/](http://cars.wasabii.com.tw/)


```
math FILES += 0x28bc
for i = 0 < FILES
getdstring NULL 0x8
get OFFSET long
get SIZE long
math OFFSET += 0x28BD4
log NAME OFFSET SIZE
math NAME += 1
next i

```

sorry no names for these files.
mainly dds files and some model files.
## Post #109
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-16T13:47:31+00:00
- Post Title: Re: Files extractors scripting

Lost Eden Texture Extractor and converter.
[http://losteden.jp/start](http://losteden.jp/start)
[http://download.losteden.jp/losteden/cl ... taller.exe](http://download.losteden.jp/losteden/client/LEInstaller.exe)

```
set DDS string ".dds"
for i = 0 < FILES
get NAME filename
STRING NAME -= 4
math COUNTER += 1
string NAME += COUNTER
string NAME += DDS
get SIZE long
get ZSIZE long
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE SIZE
append
math SIZE -= 0x1e
log NAME 0x1e SIZE MEMORY_FILE
append
math OFFSET += ZSIZE
goto OFFSET
next i

```

[monster2.JPG](https://xentaxbackup.github.io/file/2284_monster2.JPG)
## Post #110
- Username: Zerox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-16T14:22:50+00:00
- Post Title: Re: Files extractors scripting

Luna Online pak extractor
[http://luna.gpotato.com/](http://luna.gpotato.com/)
[http://luna.gpotato.com/?m=download](http://luna.gpotato.com/?m=download)

```
get FILES long
goto 0x5c
for i = 0 < FILES
get UNK1 long
get SIZE long
get NSIZE long
math NSIZE += 1
get UNK2 long
getdstring NULL 0x10
getdstring NAME NSIZE
savepos OFFSET
log NAME OFFSET SIZE
math OFFSET += SIZE
goto OFFSET
next i

```

[Luna.Online3 (Custom).jpg](https://xentaxbackup.github.io/file/2285_Luna.Online3 (Custom).jpg)
## Post #111
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-18T03:06:36+00:00
- Post Title: Re: Files extractors scripting

City Of Heroes .pigg extractor
ill create some more extractors converters for this game but I don't want to make one script to big.
[http://www.cityofheroes.com/trial/index.html](http://www.cityofheroes.com/trial/index.html)

```
get FILES long
math OFFSET2 += FILES
math OFFSET2 *= 0x30
math OFFSET2 += 0x1c
savepos TABLE1
for i = 0 < FILES
get V4 long
get FILENUMBER long
get SIZE long
get UNK2 long
get OFFSET long
get NULL2 long
get FFFFFFFF long
get UNK3 long
get UNK4 long
get UNK5 long
get UNK6 long
get ZSIZE long
savepos TABLE1
goto OFFSET2
get NSIZE long
getdstring NAME NSIZE
clog NAME OFFSET ZSIZE SIZE
savepos OFFSET2
goto TABLE1
next i


```

why do they compress their data 2x lol.
sample file
[http://www.MegaShare.com/1337914](http://www.MegaShare.com/1337914)
[dress.JPG](https://xentaxbackup.github.io/file/2293_dress.JPG)
## Post #112
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-19T04:29:22+00:00
- Post Title: Re: Files extractors scripting

Heva Online Quick bms script.
Client Download
[http://windybeta.xcdnplus.co.kr/windyde ... VO_CBT.exe](http://windybeta.xcdnplus.co.kr/windydev/client/Heva/HVO_CBT.exe)
Website
[http://windybeta.xcdnplus.co.kr](http://windybeta.xcdnplus.co.kr)

```
get UNK1 short
math FILES += 0xFFFF
for i = 0 < FILES
get NSIZE long
get UNK2 long
get UNK3 long
get ZSIZE long
get SIZE long
get ZSIZE2 long
get UNK4 long
getdstring NAME NSIZE
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE
math OFFSET += ZSIZE
goto OFFSET
next i

```

[](http://img11.imageshack.us/i/screenshot1249737825248.jpg/)
I attached some sample models that should be simple to decode.
[BBox.rar](https://xentaxbackup.github.io/file/2296_BBox.rar)
## Post #113
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-31T02:56:38+00:00
- Post Title: Re: Files extractors scripting

The contents of this post was deleted because of possible forum rules violation.
## Post #114
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-26T20:28:12+00:00
- Post Title: Re: Files extractors scripting

Here is a extractor script fot NAYA online
纳雅外传OL
[http://nywz.hitogame.com/Index.aspx](http://nywz.hitogame.com/Index.aspx)
[http://download1.hitogame.com/Naya_Setup_0.2.0.0.exe](http://download1.hitogame.com/Naya_Setup_0.2.0.0.exe)

```
math FILES += 0xFFFFFF
get NULL1 long
get FTABLE long
get FTABLESIZE long
goto FTABLE
for i = 0 < files
get NSIZE long
getdstring NAME NSIZE
get ZIP byte
get OFFSET long
get ZSIZE long
get SIZE long
if ZIP == 1
clog NAME OFFSET ZSIZE SIZE
else
log NAME OFFSET ZSIZE
endif
math COUNTER += 1
print "%COUNTER%"
next i

```

The model format is Open Scene Graph for models and animations but I can not find a windows viewer or a compiled version of open scene graph.
[vs05.JPG](https://xentaxbackup.github.io/file/2376_vs05.JPG)
## Post #115
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-12T19:40:48+00:00
- Post Title: Re: Files extractors scripting

@any developer
well, the development of QuickBMS continues with new enhancements and support to other useful and less useful stuff (and yes, the usual bugfixes).
for example in the new version I have decided to use the OpenSSL library that through its EVP interface allows to use any encryption algorithm supported by this great library (included any ecb, cbc, ofb and other modes) using the same function! :)

regarding the various algorithms I guess that for the moment there is nothing else to add natively, after all if the algorithms used by the games are not standards like zlib or lzo there is not much to do.
anyway I have added the possibility to choose the parameters of the lzss algorithm, so for example for a game like The Settlers II would be enough to specify 'comtype lzss "10 4 2 0"' for supporting its compression with non-default parameters.

and the following is a small funny/crazy/mad/stupid thing I have created in a couple of minutes, it's a conversion in BMS scripting of the LZSS algorithm to prove that the custom compression algorithms can be implemented even in the scripting language... obviously the performances are not excellents (22 seconds for decompressing 20 megabytes) but it works and is a good demonstration:

```
# remember that QuickBMS supports the LZSS algorithm natively so this one
# is only a funny demonstration of a script-only function

set NAME string "unpacked.dat"
get ZSIZE asize
math SIZE = ZSIZE
math SIZE *= 10
log MEMORY_FILE 0 ZSIZE
callfunction LZSS_BMS_DUMP

# you must set: MEMORY_FILE (input), ZSIZE (input size), MEMORY_FILE2 (output), SIZE (max size)
startfunction LZSS_BMS_DUMP
    set EI long 12
    set EJ long 4
    set P long 2
    set rless long P
    set init_chr long 0x20

    set N long 1
    math N <<= EI
    set F long 1
    math F <<= EJ

    # pre-allocate memory for faster performances
    putvarchr MEMORY_FILE3 N 0
    for i = 0 < N
        putvarchr MEMORY_FILE3 i init_chr
    next i
    putvarchr MEMORY_FILE2 SIZE 0

    math r = N
    math r -= F
    math r -= rless
    math N -= 1
    math F -= 1

    math src = 0
    math dst = 0
    math srcend = ZSIZE
    math dstend = SIZE

    math flags = 0
    for src = 0 < srcend
        if flags & 0x100
        else
            getvarchr flags MEMORY_FILE src
            math src += 1
            math flags |= 0xff00
        endif
        if flags & 1
            getvarchr c MEMORY_FILE src
            math src += 1
            putvarchr MEMORY_FILE2 dst c
            math dst += 1
            putvarchr MEMORY_FILE3 r c
            math r += 1
            math r &= N
        else
            getvarchr i MEMORY_FILE src
            math src += 1
            getvarchr j MEMORY_FILE src
            math src += 1
            math TMP = j
            math TMP >>= EJ
            math TMP <<= 8
            math i |= TMP
            math j &= F
            math j += P
            for k = 0 <= j
                math TMP = i
                math TMP += k
                math TMP &= N
                getvarchr c  MEMORY_FILE3 TMP
                putvarchr MEMORY_FILE2 dst c
                math dst += 1
                putvarchr MEMORY_FILE3 r c
                math r += 1
                math r &= N
            next k
        endif
        math flags >>= 1
    next
    math SIZE = dst
    log NAME 0 SIZE MEMORY_FILE2
endfunction
```
hope you like the idea and in case of doubts about the scripting language or what is possible or not possible to do with it remember to read quickbms.txt or to contact me or to watch the various existent bms scripts.
## Post #116
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-10-14T12:43:14+00:00
- Post Title: Re: Files extractors scripting

aluigi, I don't know if this is where we can request for you to add something to QuickBMS, but I was wondering if you could possibly add BPE (Byte Pair Encoding) to the program?  Thanks.
## Post #117
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-14T13:19:44+00:00
- Post Title: Re: Files extractors scripting

bpe has been added just in this version, the function comes from the known bpd.c code.
and yes, any new idea or discussion can be made in this thread, the only requirement is that any new algorithm to implement natively in quickbms must be a standard (like zlib, lzo, lzma, any library) or at least used in more than one game.
## Post #118
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-15T23:58:42+00:00
- Post Title: Re: Files extractors scripting

Here is the new format for the dragon nest archives they got rid of the recursive archive format.

> Math Files += 0xFFFFFF
>
> findloc RES_START string "mapdata"
>
> goto RES_START
>
> savepos RES_START
>
> math RES_START -= 1
>
> goto RES_START
>
> for i = 0 < FILES
>
> getdstring NAME 0x100
>
> get UNK1 long
>
> get SIZE long
>
> get ZSIZE long
>
> get OFFSET long
>
> get UNK3 long
>
> getdstring NULL1 0x28
>
> clog NAME OFFSET ZSIZE SIZE
>
> next i
client [http://dragonnest.nefficient.co.kr/Rele ... onNest.cab](http://dragonnest.nefficient.co.kr/ReleaseBuild/Install/DragonNest.cab)
[harpy_blue.JPG](https://xentaxbackup.github.io/file/2448_harpy_blue.JPG)
## Post #119
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-17T17:04:52+00:00
- Post Title: Re: Files extractors scripting

well, I have just finished to add a new function that in my opinion could be very useful in some cases and I don't talk only about the simple extraction but moreover to who encounters a custom algorithm and must choice if it's more convenient to spend time trying to reverse it or trying to use it directly in its binary form.

practically it's the ability of importing and using an external function from an executable or a dll or even a raw file, like the dumped content of a function.

the particularity of this CallDLL command is that it's highly customizable, for example is possible to choose not only the name of the function to import (if it's an exported function) but even to choose the offset where is located (useful for internal/non-exported functions) and the calling convention: stdcall or cdecl.

it's important to note that there is a technical obstacle to avoid the usage of functions from executables where are used fixed/static variables.
in short words if the executable cannot be loaded at the same address for which it has been designed (image base) then is not possible to access these variables or only in some cases when the memory is allocated there but with possible corruptions.

for example by default any executable is designed to use the image base 00400000 but that zone of the memory is already occupied, and no I don't talk about our program (the caller) where it's enough to change its image base to bypass the problem but I talk about the memory (stack/heap) allocated there since the starting of our program (you can verify it with ollydbg).

and obviously loading the imported executable in a different address (for example 00f20000) means that the static variable which was located (for example) at offset 006c5000 is no longer accessible because the whole range allocated by the exe has been moved.
wow, I hope someone is following me :)

obviously there are no problems for those functions that don't use static fields and for the dlls, so be happy.

in conclusion this little command should help the testing of custom binary-only algorithms without reversing them and maybe even using them directly in the extraction code like I did in my internal tests for the lz2k algorithm.

oh, naturally it's ever possible to use the command for importing plugins, for example a dll written by us with the custom decryption code necessary to decrypt the data of a game and that will avoid to force its implementation in bms-language saving a lot of performances.
## Post #120
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-20T00:00:14+00:00
- Post Title: Re: Files extractors scripting

Culpa Innata
[http://store.steampowered.com/app/12310/](http://store.steampowered.com/app/12310/)
This game uses nif file format so you can import fully rigged models and animations into your favorite program that supports nif.
[](http://img21.imageshack.us/i/00000034721024x768.jpg/)

```
idstring "SFS1"
get FILES short
for i = 0 < FILES
get NSIZE short
getdstring NAME NSIZE
get OFFSET long
savepos NTABLE
goto OFFSET
get SIZE long
savepos OFFSET
log NAME OFFSET SIZE
goto NTABLE
next i

```
## Post #121
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-10-20T16:14:42+00:00
- Post Title: Re: Files extractors scripting

aluigi, thanks for adding the BPE decoding support, however I am still having some troubles making it work.  Perhaps the Smackdown games are using some sort of variation on BPE.  Could you PLEASE look at these two sample bpe files and see if you can get them to extract properly?  I have tried every setting I can think of.  The compressed size of the data is the LONG or SHORT at 0x008, with the data starting at 0x010, but the value at 0x00C, either LONG or SHORT, is not the uncompressed value, and that value is the same in both files too, so not sure if it would be pertaining to the size anyway.  The closest I can come is if I say the uncompressed size of the first file is 1000000, then it extracts, but it has repeating data at the end for a long time, and doesn't really decompress properly.  I have had a hard time getting anything to work even close on the second file.  Thanks for any help you can give, and if it helps, I can give you the PAC files that these two file were taken from, just didn't want to give a big file, unless necessary.
[test.rar](https://xentaxbackup.github.io/file/2467_test.rar)
## Post #122
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-10-20T16:18:15+00:00
- Post Title: Re: Files extractors scripting

I will just go ahead and post the PAC file that they came from, it isn't much bigger than those two files by themseleves.  Thank you, if you can help, I appreciate it.   
[DLC.rar](https://xentaxbackup.github.io/file/2468_DLC.rar)
## Post #123
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T16:55:15+00:00
- Post Title: Re: Files extractors scripting

I have tried to test all the algorithms supported by quickbms but nothing.
that's the max I can do
## Post #124
- Username: Gocha
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-29T03:11:05+00:00
- Post Title: Re: Files extractors scripting

Dragon Age Origins.

```
get FILES long
get UNK1 long
get UNK2 long
get UNK3 long
for i = 0 < FILES
getdstring UNAME 0x40
set NAME unicode UNAME
get OFFSET long
get SIZE long
log NAME OFFSET SIZE
next i

```
 
this extracts all the main data types from this game the audio is fsb which is supported with [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)
except the gui sounds they seem to be a newer version
## Post #125
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-29T18:04:03+00:00
- Post Title: Re: Files extractors scripting

if needed I have other examples of bms scripts that I created the other day in some minutes:
[Gorky17](http://aluigi.org/papers/bms/gorky17.bms)
[Razor Shadow Unit](http://aluigi.org/papers/bms/razorsu.bms)
[games developed by Rebellion with the Asura Engine (ASR,PC)](http://aluigi.org/papers/bms/asura.bms)
[games of 49games](http://aluigi.org/papers/bms/49games.bms)
[RFA files used in the DICE's Refractor2 engine (like the Battlefield series)](http://aluigi.org/papers/bms/rfa.bms)
[ShellShock NAM67](http://aluigi.org/papers/bms/shellshock67.bms)
[Red Faction](http://aluigi.org/papers/bms/redfaction.bms)
[Massive Assault Network](http://aluigi.org/papers/bms/massive_assault.bms)
[Sacrifice](http://aluigi.org/papers/bms/sacrifice.bms)
[SÖLDNER - Secret Wars (simplified folders tree)](http://aluigi.org/papers/bms/soldner.bms)
[Soldier of Fortune 1](http://aluigi.org/papers/bms/sof1.bms)
[Panzer Elite Action](http://aluigi.org/papers/bms/panzer_elite_action.bms)
[MAS files of ANY game that uses the ISI Gmotor2 engine (cool)](http://aluigi.org/papers/bms/mas.bms)

what I did was simply searching some of the bigger files in my hard-disk and I found these games and so I decided to see how much time was needed to make the work.
it was mainly a test to see how simple and fast was to create the scripts.

if someone has some requests about non-recent games or games for which already exist extractors (so for seeing the difference with a bms script) please let me know.
## Post #126
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2009-10-29T19:05:39+00:00
- Post Title: Re: Files extractors scripting

hi aluigi!
i don't know if .dat mk trilogy psx files are a valid request   
if it is then i posted a sample file and some info here: [viewtopic.php?f=18&t=3811](http://forum.xentax.com/viewtopic.php?f=18&t=3811)

thanx in advance
## Post #127
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-29T19:26:42+00:00
- Post Title: Re: Files extractors scripting

rapidshare is impossible to use as usual, but judging the size of that file it's to be excluded that it's an archive.
so not stuff for me
## Post #128
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2009-10-29T19:31:04+00:00
- Post Title: Re: Files extractors scripting

the file is a .dat from a stage of mkt containing graphics.
characters are stored in the same kind of files.
so, now luck, right?

thanx anyway.
## Post #129
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-10T13:50:37+00:00
- Post Title: Re: Files extractors scripting

I have implemented a feature in quickbms 0.3.8 that I guess could be useful to some advanced users.

as many of you know, the main problem when handling a compressed file is figuring the algorithm used for compressing it.
in some cases it's simple like for the zlib data which starts with 0x78 or with the deflate algorithm in general where it's enough to use tools like offzip to recognize it, in other cases is less easy but still possible like the lzma data which has a 5 bytes header with some zeroes in it or with lzss that is used often and the plain-text data in it is enough visible or with xmemdecompress that seems used in many x360 games but usually it's hard or not possible to figure them on the fly.

so recently after an obsession (really!) in the searching of various algorithms to implement in quickbms I thought that wouldn't be bad to use this vast collection of algorithms in sequence for knowing if and what algorithm was used or at least having an idea of what of them has a result closer to the original uncompressed file.

the following is a simple example of quickbms script for doing this "scan job":
[http://aluigi.org/papers/bms/comtype_scan.bms](http://aluigi.org/papers/bms/comtype_scan.bms)

it's job is very simple, it reads the input file and performs a decompression using any of the available algorithms and each output will be placed in an output file named with a sequential number which is the same one used internally by quickbms to index the algorithm.
the number associated to the algorithm is visible in the source code of quickbms.c where I have numbered them in steps of 5 like:

```
    COMP_LZO1,
    COMP_LZO1A,
    COMP_LZO1B,     // scan 5
    COMP_LZO1C,
    COMP_LZO1F,
    COMP_LZO1X,
    COMP_LZO1Y,
    COMP_LZO1Z,     // scan 10
    COMP_LZO2A,
    ...
```

so it's clear that the input file must be the direct raw compressed data block without headers and other useless stuff, or in any case it must have the format supported by quickbms (this is valid only for those algorithms that don't have a standard like quad, balz, paq6, ppmd and so on).

unfortunately, although I have tried to fix some of them a bit, the algorithms implemented come from third parties and so are not written correctly for supporting invalid data, the consequence is that a file compressed with zlib will cause the crash of quickbms when the script is scanning the XMemDecompress algorithm and the same will happen with other non-well-written algorithms.

so IN ANY CASE is needed the hand of the user (you) for removing the crashed algorithms from the bms script.
that means that in the case of the previous example we need to substituite

```
    #elif i == 22    # XmemDecompress
```
with
```
    elif i == 22    # XmemDecompress
```
for skipping that algorithm which causes the crash and continuing with the others and doing the same (uncommenting or adding them) with any other crashed algorithm.

and now a practical example:
a couple of days ago chrrox had a doubt about the algorithm used in that Rumble Rose game so I dumped the compresse data from the files he provided (you can see it some bytes after the "BPE" signature) and I launched quickbms -o comtype_scan.bms data.dat z:\ and I noticed that the generated file with name "55" (the bpe algorithm) had a perfectly comprehensible data in it.
ok then I noticed that only the first 0x400 compressed bytes gave this perfect result but that scan of some seconds was enough to guess the correct algorithm without having that game or without spending time to do the manual check on each algorithm.

well I hope it helps and let me know any doubt or idea.
oh and as I have said before this stuff is intended only for advanced users!
## Post #130
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-11-11T08:51:38+00:00
- Post Title: Re: Files extractors scripting

i am not advanced 
i discoverd if we set a random value larger than real value in (uncompressed size variable) used in CLOG command has no issue !
just remaind the offset and zsize , but if we set them incorrect QBMS will crash by error !
please if it is possible gift an ability to QBMS that can sweep in a defined range for offset or zsize without 
error prompt untill it dump the file !
excuse me for greed ! because i accustomed to QBMS   
acclaim , Luigi Auriemma
## Post #131
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-11T11:41:18+00:00
- Post Title: Re: Files extractors scripting

scanning both offset and zsize is not a problem (although doing it for zsize is useless, use the whole zsize and you are ok) but remains ever the problem of the bad algorithms that crash with invalid data.

for example in zlib and deflate there is absolutely no problem, the result will be exactly like offzip but I guess that lzo could start to give some troubles with some types of data and the same happens to almost all the others.

oh, the offset scanning can be implemented directly in the bms script, so nothing to add to quickbms.
## Post #132
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-25T18:22:23+00:00
- Post Title: Re: Files extractors scripting

regarding the guessing of the compression algorithms I have released another version of comtype_scan that now avoids the need of editing it everytime one of the supported algorithms crashes.

needed files:
[http://aluigi.org/papers/bms/comtype_scan2.bat](http://aluigi.org/papers/bms/comtype_scan2.bat)
[http://aluigi.org/papers/bms/comtype_scan2.bms](http://aluigi.org/papers/bms/comtype_scan2.bms)

the bat file launches quickbms 200 times in sequence so that if an algorithm crashes it's enough to close the Windows dialog message that reports the error and if an algorithm doesn't terminate just press CTRL-C and type 'n' for continuing with the next algorithm.

example:
comtype_scan2.bat c:\comtype_scan2.bms c:\dump.dat c:\output_folder

if the needed 3 arguments are missing then the bat will show a runtime help.
note that is necessary [QuickBMS 0.3.13](http://aluigi.org/papers.htm#quickbms)

now there are no excuses for having doubts about an unknown algorithm :)
and obviously if you are aware of other algorithms that you would like to see implemented in quickbms, just tell me
## Post #133
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-23T17:41:55+00:00
- Post Title: Re: Files extractors scripting

oh well it's already passed one year from the first idea of QuickBMS (read the first posts of this thread) and within 2 days there will be the first "birthday" from the date of the public version ih ih ih :)

so I have decided to retake this thread only to show some of the recent updates, indeed today I have released another version: [0.4.1](http://aluigi.org/quickbms)

support for the WCX packer plugins of Total commander
so now GAUP and any other TC plugin can be used directly from QuickBMS
automatic extensions if you use an empty filename in your scrypts like: log "" OFFSET SIZE
abnourmous number of new encryptions and compressions that can be applied even to the variables (String command)
various hash and crc (fully customizable) through the Encryption command
improved the CallDll command like support for dlls inside the scripts and any known x86 calling convention
lot of bugfixes and enhancements

the downside of all this stuff is that now the size of the executable is over 2 megabytes, wow the first version was about 200 kilobytes :)

as usual let me know if you have new ideas or bug reports for QuickBMS or the scripts created by me.

for example I have already thought to the idea of adding support for other external plugins (I mean plugins written for other programs) but except Total Commander I have seen no other software that has a so good "park of plugins" and it's easy to implement to deserve the support in QuickBMS.
## Post #134
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-24T19:39:55+00:00
- Post Title: Re: Files extractors scripting

I have not look at a recent release, but would it be possible for a number to string conversion function be added? Eg, instead of always treating as signed number, you could do unsigned (%u), or in hex (%X/%08X), etc.

I didn't see anything for this in the documentation I looked at, but this was a week or two ago when I last looked.
## Post #135
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-24T20:00:12+00:00
- Post Title: Re: Files extractors scripting

for the visualization with the Print command you could use the -x option of quickbms that shows the numbers in hex mode so "print %123%" will show 0x7b instead of 123
while for the unsigned thing no, there is no way.

personally I use a lot -x when I debug a format with the usage of the Print instruction just for this reason (offsets and sizes).
while if I need to know the unsigned version of a number (99% not needed because if it's so big it's probably only a crc) I convert it with my calculator simply copying and pasting the number in the console.
## Post #136
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-24T20:03:45+00:00
- Post Title: Re: Files extractors scripting

I was thinking more in the line for filenames where the name is a hash of some sort -- signed numbers don't really work well for that.
## Post #137
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-24T20:18:47+00:00
- Post Title: Re: Files extractors scripting

uhmmm depends by what you want to do and "how" you do because I have already worked with various hashes without problems but I guess you refer to something else, so show me an example.
## Post #138
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-24T20:24:43+00:00
- Post Title: Re: Files extractors scripting

It's cumbersome to work with filenames that were made into signed numbers from a hash value, that's all. I'd rather they were in hex for sorting purposes.
## Post #139
- Username: Bringbackfez
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 04, 2014 12:22 am
- Post datetime: 2014-09-04T18:40:14+00:00
- Post Title: Re: Files extractors scripting

Looking for the Fantasy Earth Zero server files if anyone has any info pleae contact us at [https://www.facebook.com/BringBackFantasyEarthZero](https://www.facebook.com/BringBackFantasyEarthZero) or message me on forum. Gamepot USA (doesn't exist) no longer has rights to the NA version & the gamania is open for atking so we want to start our own server.
