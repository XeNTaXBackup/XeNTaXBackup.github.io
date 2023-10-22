## Post #1
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-13T17:49:51+00:00
- Post Title: Xenoblade (Wii)

here a bms script to extract Xenoblade (Wii) *.pkb & *.pkh files

all *.pkb (PakBinary?) files are in the root of the DVD, 
all *.pkh (PakHeader?) files are in static.arc, use a U8 tool to extract them

extracted files have no name, my script uses the Hash (or FileID, don't know) + .dat as filename

the game uses common Wii/GC file formats (*.brres, *.brmdl, *.arc, *.brlyt, *.tpl)
some files are in *.kyp, when this is the case, you can get the real filename

here a sample Model: (en090701.brmdl)
[http://www.imagebanana.com/view/kf9tx3m7/en090701.jpg](http://www.imagebanana.com/view/kf9tx3m7/en090701.jpg)

```
# by Falo - 2010
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
#
# usage :
#
# use WiiScrubber to extract all *.pkb files
# use any u8 tool (arc extractor) to extract static.arc
# you should then have *.pkb and *.pkh files
# use this script on *.pkb

endian big

Open FDDE PKH 1

get Temp long 1 # always 0x00FE1200
get Temp long 1
get ofsHashTable long 1  # not sure, HashTable or FileIDTable
get FileSize long 1
get numFiles long 1

set ofsSizeTable numFiles
set ofsOffsetTable numFiles

math ofsSizeTable *= 8
math ofsOffsetTable *= 2

math ofsSizeTable += ofsHashTable
math ofsOffsetTable += ofsSizeTable

for i = 0 < numFiles
   goto ofsHashTable 1
   get Hash long 1 # not sure, Hash or FileID
   get Temp long 1 # always 0x0
   goto ofsSizeTable 1
   get Size short 1
   goto ofsOffsetTable 1
   get Offset long 1

   math Size *= 2048
   math Offset *= 2048

   # use hash/fileid as filename
   set Name Hash
   set FileExt ".dat"

   # get FileExt
   goto Offset
   get FileID long

   if FileID = 1437218861 # Nintendo ARC (U8)
      set FileExt ".arc"
   endif
   if FileID = 1651664243 # Nintendo BRRES
      set FileExt ".brres"
   endif
   if FileID = 2142000 # Nintendo TPL
      set FileExt ".tpl"
   endif
   if FileID = 1264144384 # Xenoblade KYP -> BRRES Archive
      set FileExt ".kyp"
   endif
   if FileID = 1835229440 # Xenoblade MCA
      set FileExt ".mca"
   endif
   if FileID = 1145131057 # Xenoblade DAP1
      set FileExt ".dap"
   endif
   if FileID = 1280263241 # Xenoblade LODI
      set FileExt ".lod"
   endif

   string Name += FileExt

   log Name Offset Size

   # next file, increase all offsets
   math ofsHashTable += 8
   math ofsSizeTable += 2
   math ofsOffsetTable += 4
next i

CleanExit
```


//Edit1: Script Version 1.1
- added FileEXT support

//Edit2: Script Version 1.2
- added *.dap and *.lod
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-06-16T11:58:35+00:00
- Post Title: Xenoblade (Wii)

[re-edit] Ok, my fault again...the arc extractor I was using was a shit...

[re-re-edit]I'm stubborn  your script works like a charm but in some files they have the same ID/Hash so i made a little change. On line 41 instead of

set Name Hash

i wrote

set Name i
## Post #3
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-16T18:02:21+00:00
- Post Title: Xenoblade (Wii)

I updated the script, it can now read the FileID to get the real file extension,
this works for *.arc, *.brres, *.tpl, *.kyp, *.mca,
it does not work for some dummy files and BDAT files.

I'm working on a menu translation of Xenoblade,
here my thread on gamefaqs: [http://www.gamefaqs.com/boards/960564-x ... e/55197852](http://www.gamefaqs.com/boards/960564-xenoblade/55197852)

Every text is inside of BDAT files, this means all files in Common.pkb and static.arc/dvddata/jp/bdat.bin

here a script to extract BDAT files:
it will extract all bdat with {filename}_{offset}.bdat

```
# by Falo - 2010
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big

get numFiles long
get Filesize long

SavePos ftemp

for i = 1 to numFiles
   goto ftemp
   get Offset long
   SavePos ftemp
   get Offset2 long

   if i = numFiles
      set Size Filesize
   else
      set Size Offset2
   endif
   math Size -= Offset

   goto Offset
   get FileID long
   get ofsName long

   math ofsName += Offset
   goto ofsName

   get Name string
   string Name += "_"
   string Name += Offset
   string Name += ".bdat"

log Name Offset Size

next i
```


i'm not sure how bdat works:

```
     char FileID[4];
     int ofsTableHeaders;
     short sizeStructText;
     short ofsTextOffsetTable;
     short numTexts;
}header;
```


- FileID 
will always be "BDAT"

- ofsTableHeaders 
brings you to an excel style Table Header, 
i don't know how they work, 
but the first entry is the bdat filename

- ofsTextOffsetTable
brings you to the table entry structure

- sizeStructText 
this is how big 1 Table entry is, this goes from 4 byte up to 68 byte
every structure is different, the format depends on the Table Headers

i need to write for every structure a new script (010 editor) 
but it's easy to figure them out

most follow this:

```
byte unk1[sizeStructText-2];
```

or

```
short ofsText2;
byte unk1[sizeStructText-4];
```


If someone could figure out how the Table Headers works, i could write a real text editor.
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-06-16T19:00:45+00:00
- Post Title: Xenoblade (Wii)

I'd like to study the game in prevision of a non-localization except for english. I could help if you want.
## Post #5
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-18T17:08:24+00:00
- Post Title: Xenoblade (Wii)

have you just try to open your pkg files directly with kentilan viewer ?
normally it may load all brres and related ^supported files ^^
## Post #6
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-19T17:12:44+00:00
- Post Title: Xenoblade (Wii)

> I'd like to study the game in prevision of a non-localization except for english. I could help if you want.
i think i know now how to read it, my new 010 editor script works on any bdat ^^

except for the "struct TableHeaders" this does not work, the problem is not all entrys follow the structure only some,

2 Byte = unknown value, first entry starts with 0x20, it increases with every entry by 4
2 Byte = 0x0000
X Byte = 0x00 terminated TableName

but some entrys have a 1 byte 0x00 after the TableName's 0x00 terminator and i don't know what triggers it.

```
//--- 010 Editor v3.1.2 Binary Template
//
// File: Xenoblade *.bdat
// Author: Falo
// Revision:
// Purpose:
//--------------------------------------
BigEndian();
local int i,j,numTables;

struct{
    char FileID[4];
    int ofsTableHeaders;
    short sizeTableStruct;
    short ofsTable;
    short numEntrys;
    short unk1;
    short unk2;
    short unk3;
}Header;

numTables = (Header.ofsTableHeaders - 0x20) / 4;

FSeek(0x20);
struct{
    for(i=0;i<numTables;i++)
    {
        struct{
            byte unk1;
            byte type;
            short idx;
        }Data;
    }
}TypeTable;

FSeek(Header.ofsTableHeaders);
struct{
    char BDATName[];
    for(i=0;i<numTables;i++)
    {
        struct{
            ushort dat1;
            if (dat1 == 0) 
            {
                ubyte dat1_1;
            }
            ushort dat2;
            char Name[];
            Printf("Table %03d: %s\n",i,Name);
        }THeader;
    }
}TableHeaders;

struct{
    for(i=0;i<Header.numEntrys;i++)
    {
        FSeek(Header.ofsTable + (i * Header.sizeTableStruct));
        j = 0;
        struct{
            do
            {
                switch(TypeTable.Data[j].type)
                {
                    case 1:
                        ubyte data_ubyte;
                        break;
                    case 2:
                        ushort data_ushort;
                        break;
                    case 4:
                        ubyte data_ubyte2;
                        break;
                    case 5:
                        ushort data_ushort2;
                        break;
                    case 7:
                        ushort data_string_offset;
                        break;
                    default:
                        byte unk1;
                        break;
                }
                j++;
            }
            while(j != numTables);
        }Entry;
    }
}Tables;
```


> Reply from shadowmoy
>
> have you just try to open your pkg files directly with kentilan viewer ?
normally it may load all brres and related ^supported files ^^

this should work, but you can't load textures with this methode, you need to extract them, kentilian's viewer tries to find only a valid MDL0 header.

and i know now for sure, the FileID is a hash, because main.dol loads the real filename (example: "/common/jp/bdat_qs0000.bin")


//Edit 
010 Editor script updated, 
- it now supports the Table Header and Prints it to Output Window
- added Case 4 & 5

here a new bms script, for unpacking Xenoblade dap (map) files
with this script map files (brres) and dialog text are now ripable:

Colony 9:
[http://www.imagebanana.com/view/j1xllrfo/Colony9.jpg](http://www.imagebanana.com/view/j1xllrfo/Colony9.jpg)

```
# by Falo - 2010
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big

get FileID long
get numFiles long

SavePos ftemp

for i = 1 to numFiles
goto ftemp

GetDString Name 8
get Offset long
get CSize long
get USize long
get unk1 short
get unk2 short
SavePos ftemp

goto Offset

GetDString FileExt 3
get unk3 byte
get USize2 long

math Offset += 8
string Name += "."
string Name += FileExt

ComType zlib

clog Name Offset CSize USize

next i

CleanExit
```
## Post #7
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-01-27T17:44:59+00:00
- Post Title: Xenoblade (Wii)

Since there's still no news of localization, I've decided to write my own text extractor/inserter and if it goes well, search for a translator. Thanks for documenting the bdat file format, you saved me a lot of time.

Did you ever get to start translating the menu? All google has yielded me was an italian translation (although he took the easy way out by not bothering with remapping the text pointers and just using the available space)
Just asking to make sure.

And to stay on topic (although I'm fairly late):

> but some entrys have a 1 byte 0x00 after the TableName's 0x00 terminator and i don't know what triggers it.

There's extra 0's because the strings are 2-byte aligned. I.e. to solve the problem:

```
if (curr_file_pos % 2 != 0) curr_file_pos++;
```


Also, "unk1" in Header is the offset of the last tablename's end.
## Post #8
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-01-30T16:28:00+00:00
- Post Title: Xenoblade (Wii)

Since there's some space issues which I can't quite fix, I'll just post what I have:
Edit: see below posts for link

What you need: static.arc and darchD.exe
1. 
static.arc can be extracted from the iso via WiiScrubber. 
darchD.exe is a *.arc packer/unpacker that comes with the Wii SDK. Use google. 
(You can use any other, but I haven't had any good experiences with any other tool; and you'll have to edit both *.bats I provide)

2. Download the XBSE.rar and unpack it somewhere. Put both the static.arc and darchD.exe into the same folder.

3. Run "extractEverything.bat" and you'll get 3 new folders: static_arc, bdats and xls

4. Edit the text by editting the xls files

5. Run "compileEverything.bat" and your static.arc will be updated, put it into your iso with WiiScrubber again.

There is no theoretical limit on your string size (the pointers are remapped properly), but in some cases, the game will only parse the first x characters (e.g. 9 for battle arts, 11 for monster names, 4-8 for stats) and since I can't get the Dolphin debugger working properly, I have no idea how to fix this.

Screenshots:



The xls files I used for the above pics (replace the xls folder after running extractEverything.bat):
[http://forte.spacequadrat.de/upload/xls.rar](http://forte.spacequadrat.de/upload/xls.rar)
## Post #9
- Username: redyoshi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 31, 2011 11:41 pm
- Post datetime: 2011-01-31T16:12:44+00:00
- Post Title: Xenoblade (Wii)

forte, the package has only xbse.exe and pack.exe ,has no
extracteverything and compileeverything and xbse.exe is corromped.
I'm trying to translate Portuguese Brazil.
## Post #10
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-01-31T16:16:04+00:00
- Post Title: Xenoblade (Wii)

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: redyoshi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 31, 2011 11:41 pm
- Post datetime: 2011-01-31T18:29:41+00:00
- Post Title: Xenoblade (Wii)

thaks forte!   the package is ok.
edit:I run the self-extracting file but xls folder came empty.....this is right?
i run the compile xls in static file and replace in iso, i try run in wii but reboot wii.
## Post #12
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-02-02T19:09:15+00:00
- Post Title: Xenoblade (Wii)

> Reply from Forte
>
> 
There is no theoretical limit on your string size (the pointers are remapped properly), but in some cases, the game will only parse the first x characters (e.g. 9 for battle arts, 11 for monster names, 4-8 for stats) and since I can't get the Dolphin debugger working properly, I have no idea how to fix this.
If you get the dolphin-debugger to work properly could you post how do you did it since I tried to use it once but without success. I wasnt able to find a site that describes the features or anything related to the debugger.
After the DonkeyKongClassic Classiccontroler hack came out, Crediar spoke about how he did it: [http://www.rvlution.net/forums/viewtopi ... t=30#p5179](http://www.rvlution.net/forums/viewtopic.php?f=4&t=585&start=30#p5179) He was "just" looking at the disassembled code in IDA and used WiiRD besides that. I'm curious about these methods too and maybe they would be helpful for you too. 

Maybe I should have posted this in the Tutorials-section...
## Post #13
- Username: HisshouBuraiKen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 06, 2011 4:25 am
- Post datetime: 2011-02-05T20:26:50+00:00
- Post Title: Xenoblade (Wii)

Just thought I would chime in, I'm doing/leading the translations so if you guys wanna join in on the hacking side and figure out how to get around the character parsing limits, let me know!  I'd definitely love to work with you
## Post #14
- Username: Heroine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 27, 2010 4:13 pm
- Post datetime: 2011-08-01T13:19:12+00:00
- Post Title: Xenoblade (Wii)

Hello,I knew that the EU and US version of Xenoblade would be released recently,but I still want to working on the translation for another launage.

I have trouble with displaying those two 1.21m fonts generated by your tools,so could anyone tell me how to do it?
## Post #15
- Username: robotortoise
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 20, 2015 9:06 am
- Post datetime: 2015-09-29T22:50:38+00:00
- Post Title: Xenoblade (Wii)

Sorry to bump this.

I can easily extract Xenoblade's ".pkh" archive format using this QuickBMS script above made by Falo. My question is...how can I extract a pkh, edit some files, and then make it a working .pkh file again?

I tried using QuickBMS's "repack" tool, but no dice with the bms script I used before. It seems like the script has to be modified to repack the pkh.

I'm trying to replace cutscenes, but I first have to figure out how to replace character models, as that's much easier.

Anyone got any ideas?

-Robotortoise

EDIT: Nevermind, figured it out.Use this guide I made. 

[https://tcrf.net/Notes:Xenoblade_Chroni ... an_archive](https://tcrf.net/Notes:Xenoblade_Chronicles#How_to_repack_an_archive)
## Post #16
- Username: heraldo1980
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 21, 2021 11:18 am
- Post datetime: 2021-06-23T00:11:55+00:00
- Post Title: Re: Xenoblade (Wii)

your, script quick bms to extract the pkb files, it is not working, always give error
