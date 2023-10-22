## Post #1
- Username: uly
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 03, 2007 7:29 am
- Post datetime: 2007-05-03T09:08:33+00:00
- Post Title: SpellForce 2 .cff files

Does anyone know what to use to extract the .cff files (and probably .sav files as well) for SpellForce 2?  I'm not talking about the .pak files, for which there is already an extractor released.

All of the .cff and .sav files starts with "12 DD 72 DD 03".  I thought I've seen this kind of header somewhere, but can't quite recall where...

Take a look at the attached file english.zip.  It's probably the localization file.  Please rename the extention to .cff.

TIA
[english.zip](https://xentaxbackup.github.io/file/1144_english.zip)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-03T09:11:46+00:00
- Post Title: SpellForce 2 .cff files

SAV files? Are they not saved games?
## Post #3
- Username: uly
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 03, 2007 7:29 am
- Post datetime: 2007-05-03T09:13:10+00:00
- Post Title: SpellForce 2 .cff files

Yeah, the .sav files are saved games.  But I'm really trying to get at the .cff files, just happens to notice that the .sav files have the same header.  They probably use the same compression.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-03T09:29:35+00:00
- Post Title: SpellForce 2 .cff files

Are you certain there is a compression or even usable data involved? Depending on the game it is often that in a saved game the stored data is unusable outside of the saved game file storeing information like current items held and position in the games as well as triggers, etc.

Anyways, the CFF files are a database file not an archive.
## Post #5
- Username: uly
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 03, 2007 7:29 am
- Post datetime: 2007-05-03T09:36:25+00:00
- Post Title: SpellForce 2 .cff files

Hmm, database files...  that would be quite logical.  Any idea which database program I can access these files with?
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-03T09:39:47+00:00
- Post Title: SpellForce 2 .cff files

Unfortunately no. Apparently it is incredibly difficult.
## Post #7
- Username: uly
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 03, 2007 7:29 am
- Post datetime: 2007-05-03T09:42:12+00:00
- Post Title: SpellForce 2 .cff files

Oh no!  Anything but the incredibly difficult!

Well, thanks for the quick replies.

Please help if anyone has an idea...
## Post #8
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2007-05-03T21:28:47+00:00
- Post Title: SpellForce 2 .cff files

Probably it's zlib compressed (see 36 hex offset).
Edit:
After decompression looks lik unicode text.
[](http://imageshack.us)
## Post #9
- Username: uly
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 03, 2007 7:29 am
- Post datetime: 2007-05-03T22:07:54+00:00
- Post Title: SpellForce 2 .cff files

Great!  So it is the file I'm looking for!

Sorry if it's a dumb question, but how do you decompress a zlib file?  I've looked on the board, got a command line tool but for some reason it didn't work.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-03T22:10:24+00:00
- Post Title: SpellForce 2 .cff files

Hm. That must be the English text. The Gamedata.cff contains the main script and as I read is very complicated. Perhaps why there is no editors for it yet. 

As for zlib... if the ZLIB used by Age of Empires I and II is the same as this you could use compr.exe and uncompr.exe inside a zlibnoh.rar package...

[http://aoe.heavengames.com/cgi-bin/aoec ... =5413&st=0](http://aoe.heavengames.com/cgi-bin/aoecgi/display.cgi?action=st&fn=1&tn=5413&st=0)

There. Maybe that would work.
## Post #11
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2007-05-04T08:56:11+00:00
- Post Title: SpellForce 2 .cff files

CFF file it's an archive of files zlib compressed.

```
4 - Archive Version? (3)
12 - null

// for each files
   4 - File ID?
   2 - (1)
   4 - Compressed size
   2 - (1)
   4 - Uncompressed size
   x - Data File (zlib compressed)

```


Bye
## Post #12
- Username: uly
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 03, 2007 7:29 am
- Post datetime: 2007-05-04T09:18:51+00:00
- Post Title: SpellForce 2 .cff files

I've tried both ZLIBnoh as suggested by Darkfox and ZLIBC that I found in the forum, but in both cases, the decompressed file is an empty 0 byte file.  baccello, can you tell me how you decompressed the file?
## Post #13
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2007-05-05T00:17:08+00:00
- Post Title: SpellForce 2 .cff files

Use this BMS script.

```
Set START Long 20 ;
GoTo START 0 ;
Do ;
Get ID Long 0 ;
Get FOO Int 0 ;
Get CS Long 0 ;
Get FOO Int 0 ;
Get US Long 0 ;
SavePos OFF 0 ;
If CS <> 0 ;
CLog "" OFF CS 0 0 US 0;
Math OFF += CS ;
GoTo OFF 0;
EndIf ;
While CS <> 0 ;

```
## Post #14
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2008-08-26T10:06:02+00:00
- Post Title: SpellForce 2 .cff files

I have one question, is there any way how to pack unpacked files back to the archive .cff??
(edit archive?). I know how to use hexaeditor, so i think with little help it could not be a problem.

Thank you for the answer.

Kramla

Edit: Now I know how to do it (I finaly found one working zlib packer...).
## Post #15
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2008-11-06T22:16:06+00:00
- Post Title: SpellForce 2 .cff files

Hi all,
is there a different way to extract said CFF file without the script above?
Thank you!
## Post #16
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2008-11-07T08:56:44+00:00
- Post Title: Re: SpellForce 2 .cff files

> Reply from Csimbi
>
> Hi all,
is there a different way to extract said CFF file without the script above?
Thank you!

You can do it, when you split the cff archive into files with hexaeditor (this files must only contains "data of files" from cff).
Then you can decompress it with zlibc (in this forum) by this instruction 
"zlibc -d C:\xxxx\xxx.dat C:\xxxx\uncompressedxxx.dat" (this instruction must be writen into cmd.exe - windows dos)
xxx.dat is name of compressed file and uncompressedxxx.dat is the result of decompression.
## Post #17
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2008-11-07T20:18:29+00:00
- Post Title: Re: SpellForce 2 .cff files

Hi kramla,
thanks for the detailed instructions and screen shots in your PM.
Based on those, I have created a template for the Sweetscape 010 Editor - it should be easy to save the zlib pieces one by one.

```
//--- 010 Editor v3.0.3 Binary Template
//
// File: Spellforce 2 CFF file template
// Author: Csimbi
// Revision: 1.0.0
// Purpose: Game hacking
//--------------------------------------
struct FILE
{
    struct HEADER
    {
        uint32 Header;         // ? =0x12DD72DD
        uint32 ArchiveVersion; // ? =3
        uint32 Padding[3];     // ? =0
    } header;
    do
    {
        struct RECORD
        {
            uint32 FileID;           // ?
            uint16 Unknown1;         // ? =1 or =2
            uint32 CompressedSize;
            uint16 Unknown2;         // ? =1, =2 or =4
            uint32 UnCompressedSize;
            char CompressedData [CompressedSize];
        } record;
    } while (!FEof() && record.CompressedSize != 0);
} file;

```
## Post #18
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2008-11-08T21:10:00+00:00
- Post Title: Re: SpellForce 2 .cff files

Here's a tool I just made to unpack the CFF files via command line - zlib decompression not included, so you will need another command line tool to do that.
Readme included, source code is available on request - just PM me. I used BCB6, but it should work with any C++ compiler.
[SF2CFFEX_10.rar](https://xentaxbackup.github.io/file/1731_SF2CFFEX_10.rar)
## Post #19
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2008-11-09T17:10:25+00:00
- Post Title: Re: SpellForce 2 .cff files

Hi all,
here's a command-line tool (an upgrade of the previous tool) that allows you to pack/unpack the CFF files. This one includes zlib (de)compression as needed.
Readme is included - though there is not much to read, the help will be dumped into the command-line window.
Source code is available on request - though I am not going to give you the source of my libraries and without those, it won't be worth much - PM me if you want it. I used BCB6, so you will need that, too.
[SF2CFFPK_10.rar](https://xentaxbackup.github.io/file/1733_SF2CFFPK_10.rar)
## Post #20
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-11-10T16:13:00+00:00
- Post Title: Re: SpellForce 2 .cff files

this might be a stupid question but what files will come out? Any 3d files i can use? Like .3ds or .obj?
## Post #21
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2008-11-10T19:24:42+00:00
- Post Title: Re: SpellForce 2 .cff files

> Reply from pixellegolas
>
> this might be a stupid question but what files will come out? Any 3d files i can use? Like .3ds or .obj?

From language files (like english.cff), you will get files with text, and from the others there are some scripts, databases etc.. Maybe there are some compressed objects in cff files. You must to try it.

Kramla
## Post #22
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2008-11-10T22:33:25+00:00
- Post Title: Re: SpellForce 2 .cff files

> Reply from pixellegolas
>
> this might be a stupid question but what files will come out? Any 3d files i can use? Like .3ds or .obj?

If you want to mod maps, scripts, models, textures, sounds, music, etc, you need to extract the contents of the PAK files (no need to repack them, if they are in the right path, the game will use them). Take a look there: [viewtopic.php?f=15&t=1902](http://forum.xentax.com/viewtopic.php?f=15&t=1902)

From gamedata.cff you get a bunch of index files that essentially make up the items/spells/buildings/units/heroes/NPCs (and generally all objects). I am working on decrypting them, though it is a slow process. If you want to edit items and other things, you need to mess with the chunks in gamedata.cff

From the localization files (such as English.cff) you get a bunch of string tables. Some are simple unicode strings, some are pairs of unicode and UTF8 strings, and some are complex tables. If you want to translate the game to another language, you will need to mess with these files because they include all strings from the game...

Here are some templates that I found out the formats for (they might not be correct, but they do work):
1. This applies to most files (see list of flie IDs inside):

```
//--- 010 Editor v3.0.3 Binary Template
//
// File: uncompressed data chunks of CFF files in Spellforce 2.
// Appropriate files IDs in base\English.cff and addon1\English.cff:
    // 9018 (1/1)
    // 9035 (1/1)
    // 9036 (1/1)
    // 9037 (1/1)
    // 9039 (1/1)
    // 9040 (1/1)
    // 9041 (1/1)
    // 9042 (1/1) (empty in \base and \addon1)
    // 9044 (1/1)
    // 9045 (1/1)
    // 9046 (1/1)
    // 9047 (1/1)
    // 9053 (1/1)
    // 9055 (1/1) (empty in \base)
    // 9057 (1/1) (empty in \base)
// Author: Csimbi
// Revision: 1.0.0
// Purpose: Game hacking
//--------------------------------------
struct FILE
{
    struct HEADER
    {
        uint32 RecordCount;
    } header;
    local int i=0;
    local char bMulti=0;
    if(header.RecordCount>0) do
    {
        struct RECORD
        {
            uint16 ItemID;        // See base\script\gds\definitions\gdsdbexport.lua
            uint16 Unknown1;
            uint16 Unknown2;
            if(Unknown2==0)
            {
                uint16 Unknown3;
                bMulti=0;
            }
            else
            {
                FSkip(-sizeof(uint16));
                bMulti=1;
            }
            uint32 StringLen;
            if(StringLen>0) char String [StringLen*2];
            if(bMulti==1)
            {
                uint32 StringLen2;
                if(StringLen2>0) char String2 [StringLen2*2];
            }
        } record;
        ++i;
    } while (!FEof() && i<header.RecordCount);
} file; 

```

2. This applies to only one file as well (see file ID inside):

```
//--- 010 Editor v3.0.3 Binary Template
//
// File: uncompressed data chunks of CFF files in Spellforce 2.
// Appropriate files IDs in base\English.cff and addon1\English.cff:
    // 9051 (1/1)
// Author: Csimbi
// Revision: 1.0.0
// Purpose: Game hacking
//--------------------------------------
struct FILE
{
    struct HEADER
    {
        uint32 RecordCount;
    } header;
    local int i=0;
    if(header.RecordCount>0) do
    {
        struct RECORD
        {
            uint16 ItemID;        // See base\script\gds\definitions\gdsdbexport.lua
            uint16 Unknown1; // =0;
            uint16 Unknown2;
            uint32 StringLen;
            if(StringLen>0) char String [StringLen*2];
        } record;
        ++i;
    } while (!FEof() && i<header.RecordCount);
} file; 

```

3. This applies to only one file as well (see file ID inside):

```
//--- 010 Editor v3.0.3 Binary Template
//
// File: uncompressed data chunks of CFF files in Spellforce 2.
// Appropriate files IDs in base\English.cff and addon1\English.cff:
    // 9052 (1/1) - item qualifiers
// Author: Csimbi
// Revision: 1.0.0
// Purpose: Game hacking
//--------------------------------------
struct FILE
{
    struct HEADER
    {
        uint32 RecordCount;
    } header;
    local int i=0;
    if(header.RecordCount>0) do
    {
        struct RECORD
        {
            uint16 ItemID;        // See base\script\gds\definitions\gdsdbexport.lua
            uint16 Unknown1; // =0;
            char Unknown2; // 2, 2, 1, 1, 3, 3
            char Unknown3; // 0, 1, 0, 1, 0, 1
            char Unknown4; // =0;
            uint32 StringLen;
            if(StringLen>0) char String [StringLen*2];
        } record;
        ++i;
    } while (!FEof() && i<header.RecordCount);
} file; 

```

4. This applies to two files (see list of flie IDs inside):

```
//--- 010 Editor v3.0.3 Binary Template
//
// File: uncompressed data chunks of CFF files in Spellforce 2.
// Appropriate files IDs in base\English.cff and addon1\English.cff:
    // 9003 (1/1)
    // 9050 (1/1)
// Author: Csimbi
// Revision: 1.0.0
// Purpose: Game hacking
//--------------------------------------
struct FILE
{
    struct HEADER
    {
        uint32 RecordCount;
    } header;
    local int i=0;
    local char bMulti=0;
    if(header.RecordCount>0) do
    {
        struct RECORD
        {
            char Unknown; // =1
            uint32 StringLen;
            if(StringLen>0) char String [StringLen];
            uint32 StringLen2;
            if(StringLen>0) char String2 [StringLen2*2];
        } record;
        ++i;
    } while (!FEof() && i<header.RecordCount);
} file; 

```
## Post #23
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-11-11T00:43:46+00:00
- Post Title: Re: SpellForce 2 .cff files

nah, i don\t want to mod as in putting in other models. I just want to have models separate to place in my engine and marvel at
## Post #24
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2008-11-21T06:03:36+00:00
- Post Title: Re: SpellForce 2 .cff files

I am trying to decode the item database. I am happy to report that I am half way through. Here is an example:
[http://spellforce.jowood.com/forum/show ... hp?t=51942](http://spellforce.jowood.com/forum/showthread.php?t=51942)
But. There are some structures that I could not decode yet. In order to create an item editor, I need to figure out the rest of the structures. PM me if you feel like helping.
Thanks.
## Post #25
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-06-25T22:57:01+00:00
- Post Title: Re: SpellForce 2 .cff files

Here's some quick descriptions of the files contained in the gamedata.cff from your UberEquip mod v1.1:
I thought I'd add some meaning to them.

0000-9038_1_1.dat	German texts
0001-9007_1_2.dat	building effects
0002-9008_1_4.dat	buildable objects
0003-9013_1_1.dat	heroes hair/head/body models
0004-9033_1_1.dat
0005-9001_1_4.dat	items (many bugged)
0006-9030_1_4.dat	items
0007-9031_1_1.dat	item categories
0008-9032_1_1.dat	item attribute types
0009-9034_1_1.dat	quest objects
0010-9056_1_1.dat	(empty?)
0011-9014_1_2.dat	objects
0012-9029_1_1.dat
0013-9025_1_1.dat	quests
0014-9004_1_1.dat
0015-9015_1_2.dat	sprites
0016-9027_1_2.dat	skill tree
0017-9002_1_2.dat	spells
0018-9026_1_1.dat	40-byte records
0019-9028_1_2.dat
0020-9049_1_1.dat	heroes
0021-9005_1_1.dat	enemy units
0022-9006_1_1.dat	units
0023-9000_1_1.dat
0024-9054_1_1.dat	(empty?)
0025-9020_1_1.dat
0026-9012_1_2.dat
