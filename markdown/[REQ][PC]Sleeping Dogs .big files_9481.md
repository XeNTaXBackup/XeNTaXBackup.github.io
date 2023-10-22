## Post #1
- Username: Lennox775
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 15, 2012 11:37 am
- Post datetime: 2012-08-15T03:50:03+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

I've never seen any PC games created by this developer.
Perhaps it takes a long time to release unpack-repack tool.
I think .big is archive and .bix is its index.
## Post #2
- Username: onixer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 15, 2012 6:54 pm
- Post datetime: 2012-08-15T10:58:17+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

I have try extractor for DeadRising2, FinalBIG, Dragon UnPACKer -nothing does not help.
Maybe someone knows, how to  open these files, please!
## Post #3
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2012-08-15T12:30:04+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

This isn't my sort of thing at all, but it would appear that all BIG files have an empty header of 256 bytes, followed by the first 4 bytes of data being 50 4D 43 51 "PMCQ", which I guess signifies the file type. BIX files seem to all share the same first 4 bytes, A8 40 5C 2C. As Lennox775 suggested, they would appear to be some sort of index file.

My understanding is that the developers United Front Games made their own custom engine, so presumably the file format is custom as well.
## Post #4
- Username: onixer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 15, 2012 6:54 pm
- Post datetime: 2012-08-15T12:57:26+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

it's sad ((if we do not get access to files. we can not make mods for this game. 
Is there any way out?
## Post #5
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-08-15T19:34:24+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

*.bix is a simple format, but as always with Square Enix Games most of it uses hash's instead of real filenames,
i haven't found the function to calculate hashs yet, could take a while.

here the *.bix structure:

```
//--- 010 Editor v4.0.2 Binary Template
//
// File: Sleeping Dogs *.bix
// Author: Falo
// Revision: 1.0
//--------------------------------------
struct{
    ubyte magic1[4];        // A8 40 5C 2C
    int filesize1;
    int filesize2;
    int reserved1[4];
    uint checksum<format=hex>;
    int reserved2[2];
    ubyte magic2[4];        // F9 84 E7 2A
    char archive_name[36];
    int unk1[2];            // 2x -1
    int numFiles;
    int magic3;             // always 0x34
    byte junk[magic3-4];    // this is magic3 - 4 Byte junk data, contains archive name and sometimes "D:\UFG"

    struct ENTRY entry[numFiles]<optimize=false>;
}Header;

struct ENTRY{
    uint hash<format=hex>;
    int Offset;             // Offset *= 4
    int SizeEmpty:12;       // Offset += SizeEmpty
    int unk1:20;            // ???
    int CSize;              // Compressed Size, if 0 use USize
    int unk2;               // ???
    int USize;              // Uncompressed Size, if 0 it's a dummy file

    Printf("%08X;%08X;%08X;%08X\n",hash,(Offset*4)+SizeEmpty,CSize,USize);
};
```
## Post #6
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-08-16T12:43:11+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

I don't think the hashes are calculated from the actual file names.
Here's a list of a few of the hashes from the Game.bix, they're far too incremental to be calculated from a filename (unless they're all very similar file names but even then the algorithm must be pretty bad to produce hashes that similar)
## Post #7
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-08-16T14:09:21+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

> Reply from twisted
>
> I don't think the hashes are calculated from the actual file names.
Here's a list of a few of the hashes from the Game.bix, they're far too incremental to be calculated from a filename (unless they're all very similar file names but even then the algorithm must be pretty bad to produce hashes that similar)

No this is always the case for Square Enix Games, the hashes are sorted to be incremental, it's not sorted after the offsets.
I have seen this in KH1, KH2, KHBBS, Just Cause 2, it is correct.

i found some filenames in HKShip.exe, but not the function

```
Data\UI\loading_generic4_tp.perm.bin
Data\UI\loading_generic7.tp.perm.bin

Data\UI\Icons_Weapon_QSZ92_TP.perm.bin
Data\UI\Icons_Weapon_45CAL_TP.perm.bin
Data\UI\Icons_Weapon_45CAL02_TP.perm.bin
Data\UI\Icons_Weapon_ACT02_TP.perm.bin
Data\UI\Icons_Weapon_ACT_TP.perm.bin
Data\UI\Icons_Weapon_ARGL_TP.perm.bin
Data\UI\Icons_Weapon_PUMPS_TP.perm.bin
Data\UI\Icons_Weapon_SMG_TP.perm.bin
Data\UI\Icons_Weapon_GOLD50_TP.perm.bin
Data\UI\Icons_Weapon_BATON_TP.perm.bin
Data\UI\Icons_Weapon_BROOM_TP.perm.bin
Data\UI\Icons_Weapon_CLEAVER_TP.perm.bin
Data\UI\Icons_Weapon_KNIFE_TP.perm.bin
Data\UI\Icons_Weapon_CROWBAR_TP.perm.bin
Data\UI\Icons_Weapon_STICK_TP.perm.bin
Data\UI\Icons_Weapon_SHOVEL_TP.perm.bin
Data\UI\Icons_Weapon_BRIEFCASE_TP.perm.bin
Data\UI\Icons_Weapon_HAMMER_TP.perm.bin
Data\UI\Icons_Weapon_CANEWALKING_TP.perm.bin
Data\UI\Icons_Weapon_HANDGRINDER_TP.perm.bin
Data\UI\Icons_Weapon_FISHWRAPPED_TP.perm.bin
Data\UI\Icons_Weapon_WOK.perm.bin
Data\UI\Icons_Weapon_FIREEXTINGUISHER.perm.bin
Data\UI\Icons_Weapon_COOKINGPAN.perm.bin
Data\UI\Icons_Weapon_SHOPPINGBAG.perm.bin
Data\UI\Icons_Weapon_DUFFLEBAG.perm.bin
Data\UI\Icons_Weapon_GROCERYBAG.perm.bin

Data\UI\SpyPC_texturepack.perm.bin
Data\UI\casecomplete_texturepack.perm.bin
Data\UI\unlockables_texturepack.perm.bin
Data\UI\garage_texturepack.perm.bin
Data\UI\gametracker_texturepack.perm.bin
Data\UI\camera_texturepack.perm.bin
Data\UI\camera_cctv_texturepack.perm.bin
Data\UI\options_common_texturepack.perm.bin
Data\UI\options_controllers_TexturePack.perm.bin
Data\UI\options_common_texturepack.perm.bin

data\world\game\dlc\%s\dlc%d.perm.bin
%s\Row_%d\TexturePack_%d_%d%s.perm.bin
```
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T14:22:30+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

do you have a sample archive?
I want to test the following script:
*edit* updated script

```

    ubyte magic1[4]        // A8 40 5C 2C
    int filesize1
    int filesize2
    int reserved1[4]
    uint checksum           // <format=hex>
    int reserved2[2]
    ubyte magic2[4]        // F9 84 E7 2A
    char archive_name[36]
    int unk1[2]            // 2x -1
    int numFiles
    int magic3              // always 0x34
    math magic3 -= 4
    byte junk[magic3]

for i = 0 < numFiles
    uint hash               // <format=hex>
    int Offset             // Offset *= 4
    int SizeEmpty:12       // Offset += SizeEmpty
    int unk1:20            // ???
    int CSize              // Compressed Size, if 0 use USize
    int unk2               // ???
    int USize              // Uncompressed Size, if 0 it's a dummy file

    math Offset *= 4
    math Offset += SizeEmpty
    if CSize == 0
        log "" Offset USize 1
    else
        #clog "" Offset CSize USize 1
        log "" Offset CSize 1
    endif
next i
```
yeah quickbms accepts C structures and bits too :)
## Post #9
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-08-16T14:42:50+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

global .big and .bix

[https://dl.dropbox.com/u/9950356/global.rar](https://dl.dropbox.com/u/9950356/global.rar)
## Post #10
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2012-08-16T17:32:12+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

- open input file I:\-=TEMP=-\QuickBMS\Global.bix
- open script SD_BIX.txt
- c_structs: "ubyte" "magic1[4];"
- c_structs: "int" "filesize1"
- c_structs: "int" "filesize2"
- c_structs: "int" "reserved1[4]"
- c_structs: "uint" "checksum"
- c_structs: "int" "reserved2[2]"
- c_structs: "ubyte" "magic2[4];"
- c_structs: "char" "archive_name[36]"
- c_structs: "int" "unk1[2];"
- c_structs: "int" "numFiles"
- c_structs: "int" "magic3;"
- c_structs: "byte" "junk[magic3]"
- c_structs: "uint" "hash"
- c_structs: "int" "Offset;"
- c_structs: "int" "SizeEmpty:12;"
- c_structs: "int" "unk1:20;"
- c_structs: "int" "CSize;"
- c_structs: "int" "unk2;"
- c_structs: "int" "USize;"
- set output folder OUTPUT

  offset   filesize   filename
------------------------------

Error: the requested amount of bytes to allocate is negative (-3)
## Post #11
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-08-16T19:25:12+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

yes because the script is wrong ^^
the bigfile is *.big, the fileindex is *.bix, the script reads files only from *.bix which is wrong, here the correct script:

```
open FDDE bix 1
goto 0x58 1
get numFiles long 1
goto 0x90 1

for i = 0 < numFiles
    get hash long 1
    get Offset long 1
    get unk1 long 1
    get CSize long 1
    get unk2 long 1
    get USize long 1
	
    set SizeEmpty unk1
    math SizeEmpty &= 0xFFF
    math Offset *= 4
    math Offset += SizeEmpty
	
    if CSize == 0
        log hash Offset USize
    else
        //clog hash Offset CSize USize
		log hash Offset CSize
    endif
next i
```


Compressed files have a PMCQ Header, in that header is the uncompressed size at 0x18, there are 3 functions in HKShip.exe that uses PMCQ, one of this should be the decompression:

```

.text:0095E679                 mov     dword ptr [edi], 'QCMP'

.text:00ABFFA7                 cmp     eax, 'QCMP'
.text:00ABFFAC                 jz      short loc_ABFFB5
.text:00ABFFAE                 cmp     eax, 'PMCQ'
.text:00ABFFB3                 jnz     short loc_AC0023
```

is it legal to post the steam protected exe ?
## Post #12
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-08-16T21:05:28+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

File name hash is modified CRC32, will have code up in repository later.
## Post #13
- Username: onixer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 15, 2012 6:54 pm
- Post datetime: 2012-08-16T21:23:07+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

sorry guys I'm in this business just a kid, but I see you're a pro. 
please tell me, is it possible to open these .big files?
## Post #14
- Username: Lennox775
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 15, 2012 11:37 am
- Post datetime: 2012-08-17T09:02:15+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

> Reply from onixer
>
> sorry guys I'm in this business just a kid, but I see you're a pro. 
please tell me, is it possible to open these .big files?
Researching and creating tools cannot be done in just a few days. (especially from scratch)
In case of JustCause2 it took two or three weeks to release extract/repack tools. 
Be patient please.
## Post #15
- Username: Gishank
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 11, 2011 5:58 pm
- Post datetime: 2012-08-19T09:18:15+00:00
- Post Title: [REQ][PC]Sleeping Dogs .big files

Well, least there is the advantage that the devs won't be blocking modding with patches, etc, unlike some other companies. lol
## Post #16
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2012-08-19T12:04:57+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

nothing official yet
[http://forums.sleepingdogs.net/viewforum.php?f=11](http://forums.sleepingdogs.net/viewforum.php?f=11)
## Post #17
- Username: onixer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 15, 2012 6:54 pm
- Post datetime: 2012-08-20T12:47:42+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

the story was over?
## Post #18
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-08-23T12:34:24+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

so no news on a script release for quickbms
## Post #19
- Username: Gishank
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 11, 2011 5:58 pm
- Post datetime: 2012-08-23T18:14:07+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

As a general note, people who want modding tools for Sleeping Dogs should chceck out the thread I made on the official forums ([here](http://forums.sleepingdogs.net/viewtopic.php?f=11&t=2094)), and add your opinion/vote on the poll. Assuming it gets enough support the devs may consider making official tools.
## Post #20
- Username: H1Vltg3
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 31, 2012 1:46 am
- Post datetime: 2012-08-25T08:26:25+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I know I personally cannot wait to get access to this games files. Please don't give up on this!
## Post #21
- Username: Herf
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Mar 02, 2012 2:47 pm
- Post datetime: 2012-08-28T21:02:40+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I'm sorry if this is offtopic but I'm interested in ripping the music from the game.
I extracted the data from .pck files (using the script from Assassin's Creed topic) and found audio streams there (wwise), but ww2ogg tool tells about 'unknown header' or stuff like that (forgot what it exactly said, beat the game already, but can reinstall and provide some stuff, if needed).
If someone managed to successfully extract and convert this stuff, please, give some instructions.
Thanks in advance.
## Post #22
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-09-01T16:20:42+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hello everyone, I just dropped by to say that I'm also expecting some progress from the very talented people here at Xentax.
I'm not a coder myself so I won't be contributing in terms of technical development but I will give those tools some usage since I'm interested in translating and modding this game. Anyway, keep motivated and take your time. Everyone appreciates your hard work.
## Post #23
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-09-12T15:01:21+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Any progress?
## Post #24
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-09-12T15:14:42+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from JonhOliver
>
> Any progress?

I was contacted by a forum member that took a peek at a .big and .bix sample files (thanks again, friend!) but his reply didn't bring good news:

> sorry, this format has far too many unknowns
>
> there are some compressed zlib chunks in the .big file but there is no string table for locale - just names of various textures and some references to flash or lua packages
## Post #25
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-12T18:12:00+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

the main problem is that both original and cracked executables are protected so it's not even that easy to run an ASM check on the algos
## Post #26
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-09-12T18:15:53+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Vash
>
> the main problem is that both original and cracked executables are protected so it's not even that easy to run an ASM check on the algos
I didn't know that, but makes perfect sense.
A highly knowledgeable reverse engineer is needed to make some progress. Unfortunately I'm neither.
## Post #27
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-09-13T22:06:02+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Wow, this is an amazing piece of work, thank you.
At least we got a working unpacker which, for the moment, is more than enough for the modders out there to start peeking into the game resources and get to know it better. That being said, I am aware that our friend wasn't able to get the repacker working on such short notice but I'm positive that either him or someone else will be able to sum up the knowledge acquired so far to make some progress towards that goal. Anyway, thanks to everyone involved on this.  

P.S.: Out of curiosity, what did you mean by this:

> Reply from h1210591
>
> First of all, I'm just using this account temporarily to post this, with the consent of the account holder. Sorry guys, I won't pay 5EUR to be able to share the results of the research I did on my free time.
## Post #28
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-09-13T22:52:54+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Could you explain how to extract the texts?
## Post #29
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-09-14T09:31:29+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from h1210591
>
> ner0 wrote:P.S.: Out of curiosity, what did you mean by this:
h1210591 wrote:First of all, I'm just using this account temporarily to post this, with the consent of the account holder. Sorry guys, I won't pay 5EUR to be able to share the results of the research I did on my free time.

I would have liked to register my own account normally here, but the registration page demands a 5 Euro "donation" in order to create a new account. I didn't feel fair that after spending a significant amount of my free time to research this stuff, I need to spend some money to share my results. So I found an alternate way to post here without paying the donation.
I'm sorry, I was not aware of [this](http://i.imgur.com/vKRxU.png). When I registered at Xentax one year ago this was not the case.
Although I understand that maintaining the community has it's costs, I do not agree that registrations should have mandatory donations.
In the end, I think this will hurt the community more than it will help. Anyway, this is just my opinion and this is also not the place for discussing it. Sorry about that.
## Post #30
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2012-09-15T08:15:52+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Awesome work. SD modding is back!
I installed Python3 and tried to extract with it, but always said "Invalid magic number; file may not be an IDX file at all".
Am i doing something wrong? Or scripts are under WIP?
## Post #31
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2012-09-15T12:34:37+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

It works perfectly. Thanks a lot  

Unfortunately extracted files are all encrypted...
## Post #32
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-09-15T16:42:40+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from h1210591
>
> I don't believe they are encrypted (at least the XBOX version of the files don't seem to be), but they all have their own binary formats, which need to be examined and reverse-engineered on their own.

In other words, it obviously needs further research before anything meaningful can be changed in the BIG file. I probably won't do any of that research myself, but hopefully the extractor code allows others to get further results.

The problem was never extracting the files, 2 extractors scripts are on the first page and i coded a standalone .NET extractor, there were only 2 problems,
the hash algo and the compression, i didn't continue the work on the tool yet, because the hash functions does not work, i posted some filenames on the first page, but i can't find a matching hash with your algo in UI.bix.

Maybe my translated code is wrong or you reversed the wrong checksum, there are 3 crc32 & 3 crc32b precalculated tables in the exe.

```
        Dim vector As Integer = -1
        Dim idx As Byte = 0

        For i As Integer = 0 To Name.Length - 1
            idx = Val(Name(i)) Xor (vector >> 24)
            vector = cksum2_magic(idx) Xor (vector << 8) 
        Next i

        Return vector
    End Function
```


```
	Referenced at 00D7B9B4, 00D7BA4D, 00D7BA75, 
	00D7BA9C, 00D7BAC4, 00D7BAEC, 00D7BB13,
	00D7BB3B, 00D7BB63, 00D7BB9F, 00D7BC18, 
	00D7BC94, 00D7BCED, 00D7BD47, 00D7BD9F, 
	00D7BDF8, 00D7BE52, 00D7BEAA, 00D7BF03, 
	00D7BF70, 00D7BFA6
CRC32 :: 00E57F78 :: 01258B78
	Referenced at 00D84F88, 00D84FA1, 00D84FBA, 
	00D84FDC, 00D84FED, 00D84FFE, 00D8500F, 
	00D85027, 00D85038, 00D85049, 00D8505D, 
	00D8508F, 00D850A8, 00D850C1, 00D850D6, 
	00D850E7, 00D850F8, 00D8510C, 00D85129, 
	00D85142, 00D8515B
CRC32 :: 00E77288 :: 01277E88
	Referenced at 00E3E93D, 00E3E989, 00E3E9BE, 
	00E3E9F3, 00E3EA28, 00E3EA5D, 00E3EA92, 
	00E3EACB, 00E3EB00, 00E3EB4D, 00E3EB78
CRC32b :: 00DD15F0 :: 011D21F0
	Referenced at 00416BED, 00716EF8, 00A1E33D
CRC32b :: 00FA2598 :: 013A3598
	Referenced at 004915FA, 0052BF60, 006CC10A, 00B0F1DD
CRC32b :: 00FC7090 :: 013C8090
	Referenced at 00A87D28, 00CC060F
```
## Post #33
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-09-16T10:51:03+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from h1210591
>
> Your translated code might be wrong, though. I don't know much about VB, but you seem to be using signed arithmetic while the checksum code should do everything unsigned. The string "testing" yields a 32-bit checksum of 0xdec270b7 and a 64-bit checksum of 0xfa9517a51a2f814b. If your translated code gives the same results, it's very likely to be correct.

I had an error, but it was not the signed arithmetic, somehow "Val(Name(i))" results always in 0x00, dunno why, it should return the integer value, but it works with "Asc(Name(i))", the 32-bit value is correct, the 64-bit not, maybe another small bug, but right know i only need the 32-bit name checksum.

signed or unsigned doesn't matter in calculations like this, it's only xor.
## Post #34
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2012-09-19T22:48:57+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Falo
>
> twisted wrote:I don't think the hashes are calculated from the actual file names.
Here's a list of a few of the hashes from the Game.bix, they're far too incremental to be calculated from a filename (unless they're all very similar file names but even then the algorithm must be pretty bad to produce hashes that similar)

No this is always the case for Square Enix Games, the hashes are sorted to be incremental, it's not sorted after the offsets.
I have seen this in KH1, KH2, KHBBS, Just Cause 2, it is correct.

i found some filenames in HKShip.exe, but not the function
Code: Select allData\UI\loading_generic3_tp.perm.bin
Data\UI\loading_generic4_tp.perm.bin
Data\UI\loading_generic7.tp.perm.bin

Data\UI\Icons_Weapon_QSZ92_TP.perm.bin
Data\UI\Icons_Weapon_45CAL_TP.perm.bin
Data\UI\Icons_Weapon_45CAL02_TP.perm.bin
Data\UI\Icons_Weapon_ACT02_TP.perm.bin
Data\UI\Icons_Weapon_ACT_TP.perm.bin
Data\UI\Icons_Weapon_ARGL_TP.perm.bin
Data\UI\Icons_Weapon_PUMPS_TP.perm.bin
Data\UI\Icons_Weapon_SMG_TP.perm.bin
Data\UI\Icons_Weapon_GOLD50_TP.perm.bin
Data\UI\Icons_Weapon_BATON_TP.perm.bin
Data\UI\Icons_Weapon_BROOM_TP.perm.bin
Data\UI\Icons_Weapon_CLEAVER_TP.perm.bin
Data\UI\Icons_Weapon_KNIFE_TP.perm.bin
Data\UI\Icons_Weapon_CROWBAR_TP.perm.bin
Data\UI\Icons_Weapon_STICK_TP.perm.bin
Data\UI\Icons_Weapon_SHOVEL_TP.perm.bin
Data\UI\Icons_Weapon_BRIEFCASE_TP.perm.bin
Data\UI\Icons_Weapon_HAMMER_TP.perm.bin
Data\UI\Icons_Weapon_CANEWALKING_TP.perm.bin
Data\UI\Icons_Weapon_HANDGRINDER_TP.perm.bin
Data\UI\Icons_Weapon_FISHWRAPPED_TP.perm.bin
Data\UI\Icons_Weapon_WOK.perm.bin
Data\UI\Icons_Weapon_FIREEXTINGUISHER.perm.bin
Data\UI\Icons_Weapon_COOKINGPAN.perm.bin
Data\UI\Icons_Weapon_SHOPPINGBAG.perm.bin
Data\UI\Icons_Weapon_DUFFLEBAG.perm.bin
Data\UI\Icons_Weapon_GROCERYBAG.perm.bin

Data\UI\SpyPC_texturepack.perm.bin
Data\UI\casecomplete_texturepack.perm.bin
Data\UI\unlockables_texturepack.perm.bin
Data\UI\garage_texturepack.perm.bin
Data\UI\gametracker_texturepack.perm.bin
Data\UI\camera_texturepack.perm.bin
Data\UI\camera_cctv_texturepack.perm.bin
Data\UI\options_common_texturepack.perm.bin
Data\UI\options_controllers_TexturePack.perm.bin
Data\UI\options_common_texturepack.perm.bin

data\world\game\dlc\%s\dlc%d.perm.bin
%s\Row_%d\TexturePack_%d_%d%s.perm.bin

Hello, what program you use to find these codes structure
## Post #35
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-09-20T04:40:36+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Falo
>
> h1210591 wrote:Your translated code might be wrong, though. I don't know much about VB, but you seem to be using signed arithmetic while the checksum code should do everything unsigned. The string "testing" yields a 32-bit checksum of 0xdec270b7 and a 64-bit checksum of 0xfa9517a51a2f814b. If your translated code gives the same results, it's very likely to be correct.

I had an error, but it was not the signed arithmetic, somehow "Val(Name(i))" results always in 0x00, dunno why, it should return the integer value, but it works with "Asc(Name(i))", the 32-bit value is correct, the 64-bit not, maybe another small bug, but right know i only need the 32-bit name checksum.

signed or unsigned doesn't matter in calculations like this, it's only xor.

Hi Falo,

are you planning to do also repacker for X360 please ?
## Post #36
- Username: onixer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 15, 2012 6:54 pm
- Post datetime: 2012-09-20T13:30:19+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Soory im not programer, please tell me..is it posible to extract *.big file ? if yes please tell me how, in detail!
THANKS!
## Post #37
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-09-23T07:26:05+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

So no one has got the files extracted? in working order
## Post #38
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2012-09-23T10:00:09+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hmm... I think the progress will very slow untill UFG releases official tools or Rick works on it.
But It seems he's busy with Dark Souls's working
## Post #39
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-09-24T05:04:51+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from neburas
>
> Hmm... I think the progress will very slow untill UFG releases official tools or Rick works on it.
But It seems he's busy with Dark Souls's workingAnd Borderlands 2, too many games!
## Post #40
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-09-24T05:20:46+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Rick
>
> neburas wrote:Hmm... I think the progress will very slow untill UFG releases official tools or Rick works on it.
But It seems he's busy with Dark Souls's working And Borderlands 2, too many games!

I'm looking forward to rick's bl2 save editor and profile editor.
## Post #41
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-10-05T12:49:44+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

any news?
## Post #42
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-10-29T23:06:17+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Progresss? Or are we really waiting for ufg to release tools of their own. Also, I tried 3d ripper dx and it didn't work, i dont see a ready to capture text, and i tried forcing sleeping dogs to direct x 9 to force it, but it just doesnt launch. lol
## Post #43
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-30T18:33:14+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

As Rick told there the modified CRC32. Function used also in the scripts for hashing ID's and ect.

Here modified table

```
0x00000000, 0x04C11DB7, 0x09823B6E, 0x0D4326D9, 0x130476DC,
0x17C56B6B, 0x1A864DB2, 0x1E475005, 0x2608EDB8, 0x22C9F00F,
0x2F8AD6D6, 0x2B4BCB61, 0x350C9B64, 0x31CD86D3, 0x3C8EA00A,
0x384FBDBD, 0x4C11DB70, 0x48D0C6C7, 0x4593E01E, 0x4152FDA9,
0x5F15ADAC, 0x5BD4B01B, 0x569796C2, 0x52568B75, 0x6A1936C8,
0x6ED82B7F, 0x639B0DA6, 0x675A1011, 0x791D4014, 0x7DDC5DA3,
0x709F7B7A, 0x745E66CD, 0x9823B6E0, 0x9CE2AB57, 0x91A18D8E,
0x95609039, 0x8B27C03C, 0x8FE6DD8B, 0x82A5FB52, 0x8664E6E5,
0xBE2B5B58, 0xBAEA46EF, 0xB7A96036, 0xB3687D81, 0xAD2F2D84,
0xA9EE3033, 0xA4AD16EA, 0xA06C0B5D, 0xD4326D90, 0xD0F37027,
0xDDB056FE, 0xD9714B49, 0xC7361B4C, 0xC3F706FB, 0xCEB42022,
0xCA753D95, 0xF23A8028, 0xF6FB9D9F, 0xFBB8BB46, 0xFF79A6F1,
0xE13EF6F4, 0xE5FFEB43, 0xE8BCCD9A, 0xEC7DD02D, 0x34867077,
0x30476DC0, 0x3D044B19, 0x39C556AE, 0x278206AB, 0x23431B1C,
0x2E003DC5, 0x2AC12072, 0x128E9DCF, 0x164F8078, 0x1B0CA6A1,
0x1FCDBB16, 0x018AEB13, 0x054BF6A4, 0x0808D07D, 0x0CC9CDCA,
0x7897AB07, 0x7C56B6B0, 0x71159069, 0x75D48DDE, 0x6B93DDDB,
0x6F52C06C, 0x6211E6B5, 0x66D0FB02, 0x5E9F46BF, 0x5A5E5B08,
0x571D7DD1, 0x53DC6066, 0x4D9B3063, 0x495A2DD4, 0x44190B0D,
0x40D816BA, 0xACA5C697, 0xA864DB20, 0xA527FDF9, 0xA1E6E04E,
0xBFA1B04B, 0xBB60ADFC, 0xB6238B25, 0xB2E29692, 0x8AAD2B2F,
0x8E6C3698, 0x832F1041, 0x87EE0DF6, 0x99A95DF3, 0x9D684044,
0x902B669D, 0x94EA7B2A, 0xE0B41DE7, 0xE4750050, 0xE9362689,
0xEDF73B3E, 0xF3B06B3B, 0xF771768C, 0xFA325055, 0xFEF34DE2,
0xC6BCF05F, 0xC27DEDE8, 0xCF3ECB31, 0xCBFFD686, 0xD5B88683,
0xD1799B34, 0xDC3ABDED, 0xD8FBA05A, 0x690CE0EE, 0x6DCDFD59,
0x608EDB80, 0x644FC637, 0x7A089632, 0x7EC98B85, 0x738AAD5C,
0x774BB0EB, 0x4F040D56, 0x4BC510E1, 0x46863638, 0x42472B8F,
0x5C007B8A, 0x58C1663D, 0x558240E4, 0x51435D53, 0x251D3B9E,
0x21DC2629, 0x2C9F00F0, 0x285E1D47, 0x36194D42, 0x32D850F5,
0x3F9B762C, 0x3B5A6B9B, 0x0315D626, 0x07D4CB91, 0x0A97ED48,
0x0E56F0FF, 0x1011A0FA, 0x14D0BD4D, 0x19939B94, 0x1D528623,
0xF12F560E, 0xF5EE4BB9, 0xF8AD6D60, 0xFC6C70D7, 0xE22B20D2,
0xE6EA3D65, 0xEBA91BBC, 0xEF68060B, 0xD727BBB6, 0xD3E6A601,
0xDEA580D8, 0xDA649D6F, 0xC423CD6A, 0xC0E2D0DD, 0xCDA1F604,
0xC960EBB3, 0xBD3E8D7E, 0xB9FF90C9, 0xB4BCB610, 0xB07DABA7,
0xAE3AFBA2, 0xAAFBE615, 0xA7B8C0CC, 0xA379DD7B, 0x9B3660C6,
0x9FF77D71, 0x92B45BA8, 0x9675461F, 0x8832161A, 0x8CF30BAD,
0x81B02D74, 0x857130C3, 0x5D8A9099, 0x594B8D2E, 0x5408ABF7,
0x50C9B640, 0x4E8EE645, 0x4A4FFBF2, 0x470CDD2B, 0x43CDC09C,
0x7B827D21, 0x7F436096, 0x7200464F, 0x76C15BF8, 0x68860BFD,
0x6C47164A, 0x61043093, 0x65C52D24, 0x119B4BE9, 0x155A565E,
0x18197087, 0x1CD86D30, 0x029F3D35, 0x065E2082, 0x0B1D065B,
0x0FDC1BEC, 0x3793A651, 0x3352BBE6, 0x3E119D3F, 0x3AD08088,
0x2497D08D, 0x2056CD3A, 0x2D15EBE3, 0x29D4F654, 0xC5A92679,
0xC1683BCE, 0xCC2B1D17, 0xC8EA00A0, 0xD6AD50A5, 0xD26C4D12,
0xDF2F6BCB, 0xDBEE767C, 0xE3A1CBC1, 0xE760D676, 0xEA23F0AF,
0xEEE2ED18, 0xF0A5BD1D, 0xF464A0AA, 0xF9278673, 0xFDE69BC4,
0x89B8FD09, 0x8D79E0BE, 0x803AC667, 0x84FBDBD0, 0x9ABC8BD5,
0x9E7D9662, 0x933EB0BB, 0x97FFAD0C, 0xAFB010B1, 0xAB710D06,
0xA6322BDF, 0xA2F33668, 0xBCB4666D, 0xB8757BDA, 0xB5365D03,
0xB1F740B4}; 
```


Script with new formatting hash ID

```
goto 0x58 1
get numFiles long 1
goto 0x90 1

for i = 0 < numFiles
    get hash long 1
    get Offset long 1
    get unk1 long 1
    get CSize long 1
    get unk2 long 1
    get USize long 1
   
    set SizeEmpty unk1
    math SizeEmpty &= 0xFFF
    math Offset *= 4
    math Offset += SizeEmpty

    string NAME p= "%08X" hash
   
    if CSize == 0
      log NAME Offset USize
    else
      log NAME Offset CSize
    endif
next i
```


I write tool for generate hash, maybe useful for someone 

```
        SDHasher <Mode> <Text>

[Modes]
        f - Generate Hash for FileName
        s - Generate Hash for Scripts Labels, ID ect.

[Examples]
        SDHasher -f Data\UI\loading_generic3_tp.perm.bin
        SDHasher -s TransformNodeComponent::sIdentifyNode
```

[Here Example](http://img41.imageshack.us/img41/4691/sdhasher.png)

GL in ripping (some founded filenames you can found on Rick's SVN [here](http://svn.gib.me/public/sleepingdogs/trunk/bin/projects/Sleeping%20Dogs/files/)) 

PS: Hate you all because had to install Win7 
[SDHasher_0.1.rar](https://xentaxbackup.github.io/file/5945_SDHasher_0.1.rar)
## Post #44
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-30T23:08:03+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Decompress function (sub_8B1760 - example used by game)
[PMCQ_Decompress.rar](https://xentaxbackup.github.io/file/5946_PMCQ_Decompress.rar)
## Post #45
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-11-03T03:25:16+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Lol. I'm kind a noob at this, but I have no idea what to do with these programs. I'll see what happens, one seems like a list of the models and one seems to be a converter?
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-04T12:34:25+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

No, it is only of developments info.



Currently i work on decompression function.
## Post #47
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-11-04T15:09:33+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Thanks for your work Ekey.
## Post #48
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-04T19:55:57+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Well here extractor. Decompression dont work (In progress).

Filelists:

Animation - 1026/1040
AnimationNIS - 16/450
Characters - 457/4133
CharactersHD - 20/376
Game - 110/5633
GameHD - 0/5584
GameHD2 - 0/46
Global - 1163/1245
UI - 3174/3928
Vehicles - 107/1144

Download: See [below](http://forum.xentax.com/viewtopic.php?p=83035#p83035)
## Post #49
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-11-04T23:11:57+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Ekey is it also for X360 please ?
## Post #50
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-04T23:42:03+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from michalss
>
> Ekey is it also for X360 please ?
I dont have XBOX version. Send me small BIG and BIX. Global or UI

PS: Updated Filelist's

Animation - 1026/1040
AnimationNIS - 16/450
Characters - 1082/4133
CharactersHD - 32/376
Game - 5585/5633
GameHD - 0/5584
GameHD2 - 0/46
Global - 1164/1245
UI - 3302/3928
Vehicles - 117/1144
[Projects_0.2b.rar](https://xentaxbackup.github.io/file/5963_Projects_0.2b.rar)
## Post #51
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-11-05T06:39:43+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Thank you going to send it now  Thx for help Are you also planning repack ?
## Post #52
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-05T11:52:39+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from michalss
>
> Are you also planning repack ?
Dunno.

Unpacker for XBOX and PS3 -> [>>Here<<](http://www.mediafire.com/?cxg1886r73rjio3)

PS: Decompression algo finally fully reversed and worked [Result](http://img84.imageshack.us/img84/1705/70496175.png) 
[01FA1F04_Test.rar](https://xentaxbackup.github.io/file/5965_01FA1F04_Test.rar)
## Post #53
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-11-05T16:56:56+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Pleas Ekey make also repack funtion  We can translate this game into our langs  Thx
## Post #54
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-05T22:22:40+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Well decompressor for test [>>Here<<](http://www.sendspace.com/file/45hr7v)

Known issues: On Win7 output file can be size 0. I dont know why <- (Tested on Win7 Home) -> (on XP work fine).
## Post #55
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-05T22:23:24+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from michalss
>
> Pleas Ekey make also repack funtion  We can translate this game into our langs  Thx

 
Us 2, I'm waiting on this fantastic tool.
## Post #56
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-05T22:30:07+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Currently no plans for packing.

Note: XML_CacheList.bin and XML_CacheList_MetaData.bin it's archives, contained compressed XML's.

New filenames found for Game.big

```
Data\World\Game\Section\SD\Cell_409__HotShot\Cell_409__HotShotDET.temp.bin
Data\World\Game\Section\SD\Cell_409__HotShot\Cell_409__HotShotLOD.perm.bin
Data\World\Game\Section\SD\Cell_409__HotShot\Cell_409__HotShotLOD.temp.bin
Data\World\Game\Section\SD\Cell_409__HotShot\Cell_409__HotShotSTD.perm.bin
Data\World\Game\Section\SD\Cell_409__HotShot\Cell_409__HotShotSTD.temp.bin
Data\World\Game\Section\SD\Cell_409__HotShot\Cell_409__HotShotXXX.perm.bin
Data\World\Game\Section\SD\Cell_409__HotShot\Cell_409__HotShotXXX.temp.bin
```


Total 40 unknowns
## Post #57
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-06T14:41:51+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

[>>Here<<](http://www.sendspace.com/file/oeq0zp) updated decompressor. Fixed bug with alignment in output file.
## Post #58
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-11-06T23:53:07+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> >>Here<< updated decompressor. Fixed bug with alignment in output file.

Yay! Finally some progress. I hope this works :p thank you
## Post #59
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-07T12:48:52+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from soulslayerzx
>
> Ekey wrote:>>Here<< updated decompressor. Fixed bug with alignment in output file.

Yay! Finally some progress. I hope this works :p thank you
I dont know how about on Win7 (Home Edition - output files with size 0) on WinXP work fine.
## Post #60
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-09T19:30:56+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hello friends, I want to translate this game for PS3, can anyone help me?

someone already figured out how to do and the repaker. BIK

edit. bin that contains the texts?

Hugs.
## Post #61
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-11T10:12:32+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from timartinelli
>
> someone already figured out how to do and the repaker. BIK
You mean tool for BIG ? I don't know but maybe Rick plans to make the packer.

> Reply from timartinelli
>
> edit. bin that contains the texts?
Almost all of the text compressed. I do not know, whether game works if add in BIG changed localization files without compression. We have only algo for decompression.

PS: Updated Vehicles list. 626/1144
[Vehicles_list.rar](https://xentaxbackup.github.io/file/5977_Vehicles_list.rar)
## Post #62
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-11-18T23:31:05+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

So can models/textures be extracted from the game now?
## Post #63
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-19T13:20:10+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from soulslayerzx
>
> So can models/textures be extracted from the game now?
You can extract but they same compressed.
## Post #64
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-11-19T18:14:54+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

so are there obj's or model files now? I really just need wei shen
## Post #65
- Username: onixer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 15, 2012 6:54 pm
- Post datetime: 2012-11-19T19:10:20+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> soulslayerzx wrote:So can models/textures be extracted from the game now?
You can extract but they same compressed.
Thanks!!!!!Please tell how it psible to extract ?  Do you have extractor?
## Post #66
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-21T18:47:02+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Extractor [here](http://forum.xentax.com/viewtopic.php?p=83035#p83035)
## Post #67
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-22T00:34:04+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> Extractor here
 

Good work man will try it out soon
## Post #68
- Username: guilhermearra
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 28, 2012 9:31 am
- Post datetime: 2013-01-01T23:25:23+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Anyone had any progress with the decompress code?

Thanks guys.
## Post #69
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-01-02T00:57:42+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from guilhermearra
>
> Anyone had any progress with the decompress code?

Thanks guys.
Infelizmente não...
## Post #70
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-02T12:15:49+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Decompressor already writed -> [here](http://forum.xentax.com/viewtopic.php?p=80679#p80679)
## Post #71
- Username: guilhermearra
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 28, 2012 9:31 am
- Post datetime: 2013-01-06T17:33:28+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> Decompressor already writed -> here

And Extractor? =(
## Post #72
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-07T11:11:23+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from guilhermearra
>
> And Extractor? =(

> Reply from Ekey
>
> Extractor here

Too lazy to read?
## Post #73
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-01-07T11:49:54+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

It doesn't actually work dude says 
SDDecompressor.exe has stopped working
## Post #74
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-14T14:36:03+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Ok guys here updated unpacker. Now decompression work on Win7 (Thanks to Asmodean for help!)

Download: See [below](http://forum.xentax.com/viewtopic.php?p=83044#p83044)
## Post #75
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-14T21:38:40+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Fixed: Bug with unpack archive > 2gb (GameHD.big) IO / 131
Updated: Filelists AnimationNIS, Game, GameHD, GameHD2

```
AnimationNIS - 434/471
Characters - 1148/4384
CharactersHD - 32/391
Game - 5689/5748
GameHD - 2840/2840
GameHD2 - 2839/2905
Global - 1164/1332
UI - 3302/3960
Vehicles - 626/1187
```


huh seems all work fine. GL in creating mods  

PS: If you found new file names post here please.

Download: See [below](http://forum.xentax.com/viewtopic.php?p=83102#p83102)
## Post #76
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2013-02-15T16:25:50+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

So Ekey ala h4x0r, game loaded unpacked files? Otherwise BIG thanks for hard work.
## Post #77
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-15T16:41:28+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from GRiNDERKILLER
>
> So Ekey ala h4x0r, game loaded unpacked files? Otherwise BIG thanks for hard work.
Seems yes because i found infoticker.perm.bin and infoticker.temp.bin files not in BIG

```
c:\Games\Sleeping Dogs - Limited Edition\Data\global\infoticker.temp.bin
```


PS: Not tested.

Updated filelists :

```
AnimationNIS - 471/471
Characters - 1104/4384
CharactersHD - 296/391
Game - 5649/5748
GameHD - 2840/2840
GameHD2 - 2839/2905
Global - 1164/1332
UI - 3302/3960
Vehicles - 626/1187
```


Download: See [below](http://forum.xentax.com/viewtopic.php?p=83092#p83092)
## Post #78
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-15T17:55:38+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Language files are in a simple format 



Edited: Now can dectect Label names
## Post #79
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-02-15T20:36:28+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

great job ekey keep it going ^_^

i have 2 questions will this work with the 360 version and are you able to repack?
## Post #80
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-15T20:53:39+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Dunno because i dont have XBOX version
## Post #81
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2013-02-16T10:04:05+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Ekey, how compression is used in bin files? Thanks in advance. Because i see the mess inside archive and see too texture data.
And one thing, after unpack UI is missing data in font.temp "0 MB", font.perm is O.K. have "33 Kb" Any idea?
## Post #82
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-16T12:14:04+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

It's normal
## Post #83
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-02-17T01:50:00+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> 
Code: Select allAnimation - 1056/1058
AnimationNIS - 471/471
Characters - 1104/4384
CharactersHD - 296/391
Game - 5649/5748
GameHD - 2840/2840
GameHD2 - 2839/2905
Global - 1164/1332
UI - 3302/3960
Vehicles - 626/1187
Rick found 7 files more in UI: 3309
Maybe can be useful:[http://svn.gib.me/public/sleepingdogs/t ... entorylist](http://svn.gib.me/public/sleepingdogs/trunk/bin/projects/Sleeping%20Dogs/files/ui.biginventorylist)
## Post #84
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-17T02:19:24+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from delutto
>
> Rick found 7 files more in UI: 3309
Maybe can be useful:http://svn.gib.me/public/sleepingdogs/t ... entorylist
My old list 

Updated:

```
AnimationNIS - 471/471
Characters - 3942/4384
CharactersHD - 390/390
Game - 5649/5748
GameHD - 2840/2840
GameHD2 - 2839/2905
Global - 1165/1332
UI - 3433/3960
Vehicles - 1186/1186
```


Download: See [below](http://forum.xentax.com/viewtopic.php?p=83110#p83110)
## Post #85
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-02-17T04:54:50+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

yea it doesnt work with the xbox version ^_^
## Post #86
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-17T12:36:34+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Updated: Supported PS3 and XBOX version (decompression doesnt work (trying resolve it))

Download: See [below](http://forum.xentax.com/viewtopic.php?p=83162#p83162)
## Post #87
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-17T19:12:25+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Last update

```
AnimationNIS  - FULL
Characters    - 4310/4384
CharactersHD  - FULL
Game          - 5649/5748
GameHD        - FULL
GameHD2       - 2839/2905
Global        - 1165/1332
UI            - 3433/3960
Vehicles      - FULL
```


Download: See [below](http://forum.xentax.com/viewtopic.php?p=83162#p83162)
## Post #88
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-17T20:56:33+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

what is the compress method used Ekey ? For X360 it should be LZX is it ?
## Post #89
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-17T21:40:14+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

nope it's same compression from PC -> PMCQ but it seems need to swap bytes in decompression cycle for PS3/XBOX
## Post #90
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-18T06:52:15+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> nope it's same compression from PC -> PMCQ but it seems need to swap bytes in decompression cycle for PS3/XBOX

Yes X360,PS3 are from 98% Big Endian . Did you also pls consider to make repacker without compression? Or can you please share exact struct and Standalone decompressor for PC/X360/PS3 ? I could write it on my own(i guess) . Just need decompresor... Thx
## Post #91
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-18T12:32:23+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from michalss
>
> Ekey wrote:nope it's same compression from PC -> PMCQ but it seems need to swap bytes in decompression cycle for PS3/XBOX

Yes X360,PS3 are from 98% Big Endian . Did you also pls consider to make repacker without compression? Or can you please share exact struct and Standalone decompressor for PC/X360/PS3 ? I could write it on my own(i guess) . Just need decompresor... Thx

Well decompression algo you can found on [this post](http://forum.xentax.com/viewtopic.php?p=80436#p80436). About Repacker honestly do not want to mess
## Post #92
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-18T12:36:53+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> michalss wrote:Ekey wrote:nope it's same compression from PC -> PMCQ but it seems need to swap bytes in decompression cycle for PS3/XBOX

Yes X360,PS3 are from 98% Big Endian . Did you also pls consider to make repacker without compression? Or can you please share exact struct and Standalone decompressor for PC/X360/PS3 ? I could write it on my own(i guess) . Just need decompresor... Thx

Well decompression algo you can found on this post. About Repacker honestly do not want to mess

Gr8 does it work for X360 pls ? I mean decompressor. Files are compress as 1 piece or it is on chunks pls ?
## Post #93
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-18T13:12:13+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Decompress algo from PC on PS3/XBOX dont work. Output buffer just nulled. Btw calculating size for files inside archive different from PC
## Post #94
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2013-02-18T20:43:28+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

So, Ekey, there's no chance that the files containing the text for the original game can be decrypted?
## Post #95
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-19T11:53:56+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Sartr0n
>
> So, Ekey, there's no chance that the files containing the text for the original game can be decrypted?
Files not encrypted, just compressed. If you mean text for PS3/XBOX i'm work on decompress func for console version. For PC text parsed.

XML Unpacker Incoming soon  .. Thanks to Rick for explaining about format.
## Post #96
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-19T12:06:28+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

would be gr8 to do some kind of localization tools  Thx Ekey
## Post #97
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-19T17:33:38+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Can someone send me next files: Global (BIG/BIX) and UI (BIG/BIX) from XBOX ?
## Post #98
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-19T18:35:39+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> Can someone send me next files: Global (BIG/BIX) and UI (BIG/BIX) from XBOX ?

I have to download it again damn... I need some hours for this pls wait a bit
## Post #99
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2013-02-19T22:40:59+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I was talkin' for PC, Ekey.
## Post #100
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-19T23:05:00+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Sartr0n
>
> I was talkin' for PC, Ekey.
Well for PC we can parse text. Results you can see on [this post](http://forum.xentax.com/viewtopic.php?p=83061#p83061)
## Post #101
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-20T15:35:10+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

For PS3 we have the next situation: I checked Global and UI big archives. Files inside not compressed although there is a record about compressed size.
For Xbox check it later.

So here updated unpacker: Now you can unpack XMLCache (PC/PS3/XBOX). 

And also filelists updated:

```
GameHD2       - 2858/2905
Global        - 1321/1332
UI            - 3454/3960
```


Huh. Can't attach. Reached Max Size  Download [here](http://www.sendspace.com/file/vtisdf)

Enjoy
## Post #102
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-02-21T16:56:30+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

damn you you just keep poping out new things for this game lol (love it)
and the extractor work prefect for the xbox files if you need any files i will send them your way i really hope to see a repacker

and i hope to see a xml unpcker for the xbox/ps3 
here are the files for the 360 the .bin files that are in the global/ui/vehicles
[http://www.mediafire.com/?svzl49ps598gxkv](http://www.mediafire.com/?svzl49ps598gxkv)
## Post #103
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-21T17:26:36+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from lllccc
>
> and i hope to see a xml unpcker for the xbox/ps3

XMLUnpacker work on PC/PS3/XBOX

> Reply from lllccc
>
> here are the files for the 360 the .bin files that are in the global/ui/vehicles
http://www.mediafire.com/?svzl49ps598gxkv
Files not comrpessed
## Post #104
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-02-21T18:01:40+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

hmm i cant find the link on here for that besides the sdbig unpacker and the .bin/xml unpacker on the program doesn't find the .bin files
## Post #105
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-21T18:34:29+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Download updated version.

> Reply from Ekey
>
> Huh. Can't attach. Reached Max Size  Download here

If you have already updated version File -> Unpack XML.
## Post #106
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-02-21T18:37:12+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> Ekey wrote:Huh. Can't attach. Reached Max Size  Download here

yea thats the one i downloaded but when i go to open any .bin files it shows nothing in the folder  but there are alot
of.bin files extracted from the .bix/.big files and the only 2 files in the global folder
## Post #107
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-21T18:47:05+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

You can unpack only XMLCache. Other bins not supported. This is all that I can do.
## Post #108
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-22T11:30:44+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Well trying redesign interface. Looks sweet
## Post #109
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-02-22T17:14:59+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hello

Thank you for the great work eKey friend who has been doing and helping everyone.

I got some time off and I lost a bit of the theme topic, already have some test files with the repaker.'s BIG PS3?

Hugs.
## Post #110
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-23T10:32:00+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

[Official Modding Tools request/petition](http://forums.sleepingdogs.net/viewtopic.php?f=11&t=2094)
## Post #111
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-18T20:07:36+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Textures unpacking incomming

PC


PS3/XBOX


'll share tool later when I resolve problem of convertation textures for ps3/xbox
## Post #112
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-05-14T11:48:34+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hi Ekey,

Can you please describe current status of your tools? Is it posible to repack big files and textures ? Asking coz of locatizations ? I could maybe help...
## Post #113
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-05-15T06:10:36+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I'm not interested anymore.
## Post #114
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-20T14:48:27+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> I'm not interested anymore.

Do i need packager to translate a game?
## Post #115
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-07-27T20:05:01+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Has anyone tried to run the game unpacked?

I'm aware not all filenames are known at this point, but I was thinking maybe those known might work.
So I extracted the vehicles archive, placed the resulting folders (Vehicles and Vehicles_New) in \SleepingDogs\Data\ and then I deleted vehicles.bix and vehicles.bin.

The game starts and most cars seem to work, but some don't and the game crashes when it attempts to load them.
Could there be a problem with filenames or maybe decompression on some files?
## Post #116
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-28T17:15:27+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Game does not work without archives.
## Post #117
- Username: Moo
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Jul 25, 2012 7:04 am
- Post datetime: 2014-03-18T22:34:21+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> I'm not interested anymore.
Not going to release what you have so far?
Maybe even source, so someone else can continue with it?
## Post #118
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-18T23:35:05+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I will share updated version later > Improved detect filenames and support for unpack textures (Thanks to howfie)
## Post #119
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2014-03-30T12:30:21+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Any chance to repack files?
## Post #120
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-04-20T08:13:47+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Sorry for the dig, but is there any chance you're still interested in this? 

> Reply from ZerOHearth
>
> Any chance to repack files?
Repacking isn't necessary, simply extract the files to ".../SleepingDogs/Data/" and if the game can't find the BIG file then it'll load those instead. HUGE thanks to Chipicao for figuring that out.
However, the game crashes instantly with all of them except for CharactersHD and Animation since the unpacker doesn't assign names to vital files. If Ekey updates those unknown files then we could create mods for normal characters too!


Also, Howfie already created a texture extractor a long time ago. It's a standalone .exe though, maybe you could incorporate his code into your program to make the process more streamlined.

EDIT: Reading over this thread, it saddens me to see how much support there was for this earlier, and now absolutely nobody cares.
## Post #121
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-06-07T00:00:23+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Say, does anyone know how people create the filelists for unpackers? 

I've been trying to figure this out myself but no amount of messing around in the .BIGs or the .exe turned up the names of those missing files. How did he do it in the first place?
## Post #122
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-06-14T18:30:11+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Animation     - FULL
>
> AnimationNIS  - FULL
>
> Characters    - 4310/4384
>
> CharactersHD  - FULL
>
> Game          - 5700/5748
>
> GameHD        - FULL
>
> GameHD2       - 2858/2905
>
> Global        - 1165/1332
>
> UI            - 3454/3960
>
> Vehicles      - FULL
Hm, according to info.txt there's 74 unknown files in Characters.big. One of those must be vital to the game function since it crashes without it.

> Data\Characters\CharacterRigs.bin
>
> Data\Characters_New\18k_B_100.perm.bin
>
> Data\Characters_New\18k_B_100.temp.bin
>
> Data\Characters_New\18k_B_100_TS0.perm.bin
>
> Data\Characters_New\18k_B_100_TS0.temp.bin
>
> ...
And in Character.list there's a giant list of filenames, I assume the unpacker takes the names from here. 

So I just need to locate the names of those 74 missing files and add them to here. Question is, how the heck am I supposed to find those names? There's nothing in the exe, and the .bix file is filled with gibberish.

EDIT: 



Well, here's one of them. 



I went to the labeled offset in the .big file, but that's not very helpful either. This is clearly a texture.perm.bin. But where's that dang filename?

EDIT: 

> Reply from Falo
>
> *.bix is a simple format, but as always with Square Enix Games most of it uses hash's instead of real filenames,
Welp, there goes that. I really wish I didn't have the intelligence of a potato when it comes to these things.
## Post #123
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-06-15T09:28:12+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Okay, I'm stupid. Ignore my entire previous post, cra0 was nice enough to explain this process to me.

For everyone else, Ekey made a [convenient hash calculator](http://forum.xentax.com/viewtopic.php?p=80428#p80428). That's what they used, and I'll use it too. I swear to god I WILL find those 74 file names, even if it takes me all year!
## Post #124
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-06-30T04:08:44+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Um, okay. I've been having some real trouble with this as always, and then I found something interesting. 
All the files have some clue inside as to their filenames, but no matter what I tried I couldn't seem to match up the generated hash to the original.

Then I tried a file that already had a filename assigned. 



The unpacker assigned this file the name 18k_BrawlerA01_Glasses.perm.bin, which more or less matches up with the name inside.

Yet the hash for that name is completely different.



Well no wonder I was having so much difficulty. Either I'm misunderstanding the point of this program or it's simply outdated/not meant for this purpose.


Also, cra0 recommend I try dumping the exe, but that did nothing. The dumped exe was almost identical to the original. Anyone know any other methods?

EDIT: Oh, who am I kidding, I'm the only one who reads this thread. Maybe when November rolls around the HD remake of the game will attract some people.
## Post #125
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2014-06-30T08:06:25+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> Um, okay. I've been having some real trouble with this as always, and then I found something interesting. 
All the files have some clue inside as to their filenames, but no matter what I tried I couldn't seem to match up the generated hash to the original.

Then I tried a file that already had a filename assigned. 



The unpacker assigned this file the name 18k_BrawlerA01_Glasses.perm.bin, which more or less matches up with the name inside.

Yet the hash for that name is completely different.



Well no wonder I was having so much difficulty. Either I'm misunderstanding the point of this program or it's simply outdated/not meant for this purpose.


Also, cra0 recommend I try dumping the exe, but that did nothing. The dumped exe was almost identical to the original. Anyone know any other methods?

EDIT: Oh, who am I kidding, I'm the only one who reads this thread. Maybe when November rolls around the HD remake of the game will attract some people.

I don't have much to add to your question... but I'll propose another question, even though it may make no sense and be totally wrong. Is it possible that the "hash" is an offset address for fat packed file?
## Post #126
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-06-30T08:27:59+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I don't really know. From what I've gathered hash refers to that random string of numbers and letters, and that's what the archive stores the file names as. The offset is a separate thing. 




Wait, fat archives? [You're probably thinking of this instead](http://forum.xentax.com/viewtopic.php?f=10&t=11534).
## Post #127
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2014-06-30T08:35:41+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> I don't really know. From what I've gathered hash refers to that random string of numbers and letters, and that's what the archive stores the file names as. The offset is a separate thing. 




Wait, fat archives? You're probably thinking of this instead.
lol, yes... my bad, wrong thread.
## Post #128
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-06-30T08:37:24+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I figured there would be confusion eventually. Too many dogs at once!

In any case, I think I'll just not bother with the hashes and throw filenames into the list willy nilly. It's bound to work eventually right?
## Post #129
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-01T19:52:52+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> EDIT: Oh, who am I kidding, I'm the only one who reads this thread. Maybe when November rolls around the HD remake of the game will attract some people.I'm still following 
However, I'm don't think it will work. As I've said in a previous post, even extracting only one archive with 100% known names will crash the game.

They're doing a HD remake?? PC too or just nex-gen consoles?
## Post #130
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T02:37:01+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Wait, you are? I thought you quit with this a long time ago. 

> Reply from Chipicao
>
> They're doing a HD remake?? PC too or just nex-gen consoles?
[http://forums.sleepingdogs.net/viewtopic.php?f=2&t=4983](http://forums.sleepingdogs.net/viewtopic.php?f=2&t=4983)

It's pretty much just a rumor right now, but I really hope it happens. The textures need improvement desperately.

> Reply from Chipicao
>
> However, I'm don't think it will work. As I've said in a previous post, even extracting only one archive with 100% known names will crash the game.
Not necessarily. I've unpacked Animation, AnimationNIS and CharacterHD simultaneously and it works perfectly. Simply unpack it, rename or delete the big/bix files, then merge the two Data folders.

With Vehicles the game runs and loads, but crashes at seemingly random points. Interestingly the actual vehicles work, but they [seem to have corrupted textures](http://puu.sh/9T4mG/f3860a7523.jpg).

If you unpack Characters the game runs, but crashes as soon as it tries to load the world. I just don't understand that, from what I've seen the only missing files are just models and textures. 
If a model file is missing from CharactersHD, [it'll simply be not there, and the rest of the game will work fine](http://puu.sh/6H9iu.jpg). Yet if a model file is missing from Characters it will crash the whole thing. I just don't get it.
## Post #131
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-02T05:46:53+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

The crashes are not really random, it only crashes when certain vehicles are loaded. The randomness is only in the vehicle spawning.
This suggests that the game can load some unpacked files, but fails to load others.

I assume the same thing happens with Characters, but it crashes every time probably because it's Wei Shen's files that fail to load.

As for Animation, AnimationNIS and CharacterHD, have you considered that maybe you just haven't encountered a situation which required one of the missing files? Or perhaps the game simply ignores it?

It all comes down to how the game handles such errors internally.
In case of textures that are missing or fail to load, it simply won't display them, as you've pointed out with characters and vehicles.
But for other files, such as 3D data, it will crash.

So the behavior actually makes sense. The question is why does it fail to load some but not all files. Is there an error in the extracted paths or filenames? Or maybe there's a limit to the number of files it can load simultaneously? Or what?
## Post #132
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T05:54:09+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Wei's files are all there. The stuff that's unknown is just a bunch of random props like those glasses and DLC stuff like the golden cleaver.

> Reply from Chipicao
>
> The crashes are not really random, it only crashes when certain vehicles are loaded. The randomness is only in the vehicle spawning.
This suggests that the game can load some unpacked files, but fails to load others.
True. There's obviously more issues with the unpacker than expected.

> Reply from Chipicao
>
> As for Animation, AnimationNIS and CharacterHD, have you considered that maybe you just haven't encountered a situation which required one of the missing files? Or perhaps the game simply ignores it?
No, those three have no unknown files, those are all good. 

But that's the thing. I'm assuming it crashes because it can't load some vital file, but then we have this odd behavior. 
Animation, AnimationNIS, CharacterHD, and Vehicles all have no unknown files. The first three work perfectly but Vehicles doesn't. Why do vehicle files cause crashes but character models and animations don't? I just don't understand.

EDIT:

> Animation - FULL
>
> AnimationNIS - FULL
>
> Characters - 4310/4384
>
> CharactersHD - FULL
>
> Game - 5700/5748
>
> GameHD - FULL
>
> GameHD2 - 2858/2905
>
> Global - 1165/1332
>
> UI - 3454/3960
>
> Vehicles - FULL
Also, GameHD has no unknown files as well. I tired unpacking that, everything ran smoothly. I drove all over the city, no errors or crashes.

Then I tried Animation, AnimationNIS, CharacterHD and GameHD, all at once, everything worked just fine. That's nearly 4800 unpacked files it had to load, and I did notice it took slightly longer to launch.
## Post #133
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-02T06:44:01+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

No, you don't understand.

What I'm saying is that even though we supposedly have the names for Wei's files, the game still fails to load them.
The same goes for Animation, AnimationNIS, CharacterHD, and Vehicles. Having the correct filenames doesn't necessarily mean they will also work.

Define "work perfectly". Have you tested every single animation available for every single character in-game? There must be hundreds, maybe thousands.
Just because the game doesn't crash doesn't mean it manages to load all of the unpacked files. The proof is in those missing textures you posted yourself. It's easy to see a missing texture, not so easy to see a missing animation.
## Post #134
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T07:05:22+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Chipicao
>
> What I'm saying is that even though we supposedly have the names for Wei's files, the game still fails to load them.
The same goes for Animation, AnimationNIS, CharacterHD, and Vehicles. Having the correct filenames doesn't necessarily mean they will also work.
I get what you're saying here. I sort of assumed the filenames were all correct, but of course just because it works for one doesn't mean it'll work for the rest. Explains the funkiness with Vehicles.

> Reply from Chipicao
>
> Define "work perfectly". Have you tested every single animation available for every single character in-game? There must be hundreds, maybe thousands.
Just because the game doesn't crash doesn't mean it manages to load all of the unpacked files. The proof is in those missing textures you posted yourself. It's easy to see a missing texture, not so easy to see a missing animation.
I've been playing the game for quite some time this way. Completed most of the missions and sat through all the cutscenes, I didn't see anything wrong. 

Only time I saw errors is where I deliberately removed files. The image of Wei's missing head was caused by me manually removing his head file from CharactersHD. Here's another [resulting from a manual removal of animations](http://puu.sh/9TiRQ/3e0e64db2b.jpg).
Heck, you could create a cheatmod by removing the attack animations from enemies.

Although you're right, I still haven't completed every last one. 
I've been meaning to sit down and do a full playthrough on the PC for a while now, this way I can do that and make sure it runs properly at the same time. If I come across a crash or an error it'll be easy to tell which file is causing it.
## Post #135
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-02T08:24:31+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

For find new names you need dump some memory regions not exe
## Post #136
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T09:24:58+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> For find new names you need dump some memory regions not exe
Well that would've been nice to know. 

Snarkiness aside, I genuinely appreciate the tip. I need every scrap of info I can get my hands on. 

Although it seems we're getting into the heavy technical stuff here, all of which I have absolutely no clue on how any of it works. I'll not press you since you've most likely already said everything you wanted to. 
Cra0 comes back in a few days, I can ask him for specifics on the memory thing.
## Post #137
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-02T10:00:15+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

It's not to be hard. Use WinHex for example. While playing open WinHex > Tools > Open RAM. Search HKShip.exe and you can see named regions like > Primary and Entrie memory. Open them and save on disk. After use any Hex Editor and search filenames which begin > Data\ . Usually for that writting simple logger but game have anti-debugging system
## Post #138
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T10:15:36+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Oh yeah, I heard about that. Is it really that bad? 

Anyway, thanks man. Even if I have to do everything manually it still helps a lot.
## Post #139
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-02T14:20:33+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

In an attempt to figure out what's going on when the game reads these unpacked files, I decided to log disk activity with Process Monitor.
First of all I fired up the game packed, to get a baseline of some sort.
It was very interesting to see that even when packed, the game tried to read files from \SleepingDogs\Data\Animation and AnimationNIS, which didn't exist. Even more strange is that the folders and files it was trying to read were "switched".
For example, \Data\AnimationNIS\Zodiac_Into.bin is not in AnimationNIS.big but in Animation.big.
And \Data\Animation\NIS_GAME_INTRO_OPENING.bin is actually in AnimationNIS.big. Maybe this is due to broken code that got left in the game.

Other than this it keeps to bix and big files as expected.
[](http://www.imagebam.com/image/fb2411336344333) 

Then I unpacked vehicles and started the game. It crashed immediately because my save is currently in a crowded area. The best place to test this is in that home with a driveway.
According to the log, it only tried to read Vehicles.bix once, failed, and then started reading unpacked files. Coincidence or not, it only reads files from Vehicles_New.
The strange part is that there are no failed read attempts logged for vehicle files. It simply crashes and begins to write a memory dump. No read failures prior to the crash either.
[](http://www.imagebam.com/image/035171336344337) 

@Ekey If you don't mind me asking, what's with those 0byte vehicle files? Are you sure there aren't any problems with the extractor?

Another interesting thing is that the game tries to read a bunch of hashed .bix files that don't exist. Could we create these files and use them as patches for mods? 
[](http://www.imagebam.com/image/272ff6336344334)
[Logfile.zip](https://xentaxbackup.github.io/file/7540_Logfile.zip)
## Post #140
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-02T15:48:56+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I did a second test, this time at the house I was talking about.

First I loaded a car I knew would work, the 600 Coupe S. In the attached log you can see the game reading 600CoupeS04_ts001 files @18:13:35. I drove a bit in the garage without any issues.

Then I tried loading the Terre GT and it crashed immediately after I pressed the drive button. @18:16:10 you'll see the game read some Guide01 files, which I believe are for the car selection menu. But after that there is no attempt to read any Terre01 files. It simply crashes and starts writing the dump file.
[600CoupeS_TerreGT.zip](https://xentaxbackup.github.io/file/7541_600CoupeS_TerreGT.zip)
## Post #141
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-02T17:28:53+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Chipicao
>
> @Ekey If you don't mind me asking, what's with those 0byte vehicle files? Are you sure there aren't any problems with the extractor?
It's normal because SIZE and ZSIZE just equal 0 in entry table.

> Reply from Chipicao
>
> Another interesting thing is that the game tries to read a bunch of hashed .bix files that don't exist. Could we create these files and use them as patches for mods?
Game try search DLCxxxx.bix packages where xxxx ID of DLC. How it works:

1) Searching - printf("DLC%d.xml", i);
2) Name is - DLC1.xml
3) Get hash from this file - BCF931BB
4) Add extension - dat
5) Name is - BCF931BB.dat
6) Try to read this file
7) If found game try search BIG package of this DLC adding other extension - BIX  -> BCF931BB.bix

This repeated 1 to 100
## Post #142
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T20:59:12+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Chipicao
>
> @18:16:10 you'll see the game read some Guide01 files, which I believe are for the car selection menu. But after that there is no attempt to read any Terre01 files. It simply crashes and starts writing the dump file.
Guide01 is actually just another normal vehicle. 

> Reply from Chipicao
>
> even when packed, the game tried to read files from \SleepingDogs\Data\Animation and AnimationNIS, which didn't exist.
Wait, hold on. Is this only for the two animation folders, or for all of them? Which does it try to load first, the folders or the big files?

If it loads the folders first, couldn't you theoretically place files in the folders, have them load, then any missing files are loaded from the big? Or do the packed files override the loose ones? I recall trying something like this earlier.

> Reply from Chipicao
>
> Another interesting thing is that the game tries to read a bunch of hashed .bix files that don't exist. Could we create these files and use them as patches for mods?
Also, in regards to this. I noticed in 600CoupeS_TerreGT.csv at 10:59.0 there is a call to a nonexistent file "SleepingDogs\EF1246F9.pck". There is F3ABACA0.pck in that folder however. Is it the same system Ekey said?
## Post #143
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-02T21:55:27+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

@Ekey Thanks for clarifying

> Reply from SergeantJoe
>
> Guide01 is actually just another normal vehicle.Any idea which one it is?

> Reply from SergeantJoe
>
> Wait, hold on. Is this only for the two animation folders, or for all of them? Which does it try to load first, the folders or the big files?Only for animation; big files are read first. I think the game only looks for extracted files when it can't find them in archives.
Actually, here's what's probably happening:
- there's  a piece of broken code in the game that has the animation files mixed up;
- so it tries to read AnimationNIS files inside Animation.big and vice verse, but obviously it can't because it has the wrong archive names;
- when it fails it tries to read them unpacked as you would expect, again with the switched path error;
- in the end the error is most likely ignored and it doesn't affect the game.

> Reply from SergeantJoe
>
> Also, in regards to this. I noticed in 600CoupeS_TerreGT.csv at 10:59.0 there is a call to a nonexistent file "SleepingDogs\EF1246F9.pck". There is F3ABACA0.pck in that folder however. Is it the same system Ekey said?No idea. I have all DLCs but I don't see any F3ABACA0 files
## Post #144
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T22:15:48+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Chipicao
>
> Any idea which one it is?
[Pretty sure it's this one.](http://puu.sh/9UdTh/025dcdbd30.jpg)

> Reply from Chipicao
>
> No idea. I have all DLCs but I don't see any F3ABACA0 files
Well that's weird. Must've been included with something I downloaded. The thing is, that file contains sounds from Year of the Snake and Zodiac Tournament, yet so does the main one.
## Post #145
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-02T22:26:22+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Sorry, I misread. I have F3ABACA0.pck, but no EF1246F9.
## Post #146
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T23:08:06+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

That's what I was saying, maybe you were onto something there. Or it could be just a DLC loading method like Ekey explained, only for sounds instead of models.
## Post #147
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-29T03:22:43+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

1 down, 73 to go! 

Big thanks to Ekey for pointing me in the right direction and cra0 for more detailed info.


EDIT: Although I can't help but think there's got to be an easier way to do this. Right now I'm finding the file in-game, making a memory dump, then manually matching the name to the file contents. 
It works, but it'll take a while.
## Post #148
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2014-08-24T14:10:02+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Anyone know where is fonts ?
## Post #149
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-08-25T18:04:39+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Font files are located in UI.BIG/Data/UI/Fonts.perm.bin

Although you can't really do anything with them, since there are no tools for .bin files and nobody cares enough to make some. Hopefully that will change in October when Definitive Edition is released.
## Post #150
- Username: GhostSpy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 14, 2014 9:47 pm
- Post datetime: 2014-09-14T23:19:54+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

how to repack
 bin files to big, bix

Please help
## Post #151
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-09-16T09:16:34+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from GhostSpy
>
> how to repack
 bin files to big, bix

Please help
Ekey made a script for that, but it's useless because the game simply freezes indefinitely upon loading the repacked files.

But like I said, 

> Reply from SergeantJoe
>
> Repacking isn't necessary, simply extract the files to ".../SleepingDogs/Data/" and if the game can't find the BIG file then it'll load those instead. HUGE thanks to Chipicao for figuring that out.
However, the game crashes instantly with all of them except for CharactersHD and Animation since the unpacker doesn't assign names to vital files.
## Post #152
- Username: burc ugur
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 06, 2014 3:14 am
- Post datetime: 2014-10-05T19:24:59+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hello @Ekey , im translate game but your program not give download link here.

Ekey , please re-upload download link please help me..

Sleeping Dogs Language Parser v1.0.0.2



Good days..
## Post #153
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-09T23:29:22+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Unpacker only for Sleeping Dogs: Definitive Edition

PS: Lang parser outdated and not supported.

Download: See below.
## Post #154
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-09T23:29:38+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

EDIT: Oh! Well then, that was unexpected. Thanks a ton Ekey!
## Post #155
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-10T12:56:57+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

ROFL they shipped the exe with debug symbols               


Holy fucken shit Joe you are in luck!
## Post #156
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-10-10T13:47:38+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

So I take it the localization isn't possible at the moment? I translated Sleeping Dogs a while back to Hungarian. It would be great if I could port it to the Definitive Edition.
## Post #157
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-10T17:08:49+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Nope
## Post #158
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-11T05:36:03+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Luck indeed!

I don't know how much there already is but I'm going to leave this here just in case.

```
enum UFG::BIGFileIndex::State
{
  STATE_DISABLED = 0x0,
  STATE_ENABLED = 0x1,
  STATE_PATCH = 0x2,
  STATE_PATCH2 = 0x3,
  STATE_OVERRIDING = 0x4,
};

/* 14542 */
struct UFG::BIGFileSize
{
  unsigned int load_offset;
  unsigned int compressed_size;
  unsigned int compressed_extra;
  unsigned int uncompressed_size;
};

/* 14544 */
struct UFG::BIGFileIndex::Entry
{
  unsigned int uid;
  unsigned int offset_div_4;
  UFG::BIGFileSize size;
};

/* 14563 */
struct __cppobj __declspec(align(8)) UFG::BIGFileIndex : UFG::qResourceData
{
  __int64 mSortKey;
  unsigned int mEntryCount;
  UFG::qOffset64<UFG::BIGFileIndex::Entry *> mEntries;
  UFG::qFile *mpFile;
  unsigned __int16 mState;
  unsigned __int16 mMountIndex;
  unsigned int mPadding0;
  unsigned int mPadding1;
  char mBigFileName[32];
};
```
## Post #159
- Username: burc ugur
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 06, 2014 3:14 am
- Post datetime: 2014-10-11T09:08:03+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> Unpacker only for Sleeping Dogs: Definitive Edition

PS: Lang parser outdated and not supported.

Ekey , SDDEUnpacker open language file and edit strings?

You remake a sleeping dogs lang parser?
## Post #160
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-11T16:29:14+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

No
## Post #161
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-10-11T17:51:06+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

The tool does not work.

Game: Sleeping Dogs.v 2.0 + 24 DLC

[](http://www.radikal.ru)
[](http://www.radikal.ru)

Ekey может я туплю но программа не открывает файлы.
## Post #162
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-10-11T18:21:38+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

We already know.
## Post #163
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-11T22:35:25+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Also, thanks for updating the filelists!

I copied the filenames from the DE unpacker into the SD unpacker, and now Characters.BIG has only 5 unknown files instead of 70+!

Problem is they're all empty. This means that there are several model.perm.bins that are missing their their .temp.bin files, and the game still crashes trying to load them. I'll have to go through the list and check every one.
## Post #164
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-12T22:30:45+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Updated unpacker for DE -> [Download](https://www.sendspace.com/file/dds3bk)

> Reply from makcar
>
> The tool does not work.

Game: Sleeping Dogs.v 2.0 + 24 DLC

Ekey может я туплю но программа не открывает файлы.
Кажется это не последняя версия распаковщика для 1.0 - 2.0
## Post #165
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-13T11:36:44+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

In order to avoid spam in PM's here my logger. Before use create backup > sdhdship.exe.. Copy next files in game folder:

```
Injector_x64.exe
SDLogger.dll
sdhdship.exe
```


Warning: You need also disable ASLR!
PS: For disable run ASLR_Disable.reg and reboot.

Run game by > Injector_x64.bat

If you did everything correctly you get next message and inside game folder you can see file with log -> qSH32_Log.txt

```

  AllocationBase:       0x0000000001880000
  EntryPoint:           0x0000000001882C08
  SizeOfImage:          0x0000000000018000
  CheckSum:             0x0000000000012CBD
  ExitCodeThread:       0x0000000001880000
```

Don't use on original sdhdship.exe!

Download: [here](https://www.sendspace.com/file/35t39q)
[ASLR.rar](https://xentaxbackup.github.io/file/7927_ASLR.rar)
## Post #166
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-19T15:55:41+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from cra0
>
> ROFL they shipped the exe with debug symbols
Yeah they include pdb base, but after Update 1 deleted. Also they include in XML_Cache project file for WWise
## Post #167
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-19T19:05:00+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> Yeah they include pdb base, but after Update 1 deleted.
Luckily I saved a backup.

> Reply from Ekey
>
> Also they include in XML_Cache project file for WWise
Holy... You serious? Could we theoretically repack PCK files with that? I thought it was impossible!
## Post #168
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-19T19:15:14+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> 
Holy... You serious? Could we theoretically repack PCK files with that? I thought it was impossible!
yup
## Post #169
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2014-10-20T00:48:23+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

So i was looking through the forum and I was hoping someone could teach me how to extract the models from the definitive edition?
## Post #170
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-20T06:23:34+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from MisterNatal
>
> how to extract the models from the definitive edition?
You can't. [We have to wait until someone fixes the Blender script.](http://forum.xentax.com/viewtopic.php?f=16&t=12082)
## Post #171
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-26T02:08:35+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Ekey
>
> http://oi62.tinypic.com/f591zp.jpg
Say, do you have a link to that program? I've been searching for a while but I can't find anything.

Also, I thought of something. When you unpack a PCK file, all the names are lost. Will that affect anything? 
Probably will, since I assume that file is only the project and doesn't hold any of the actual wav files. 

This means it'll be impossible to repack SFX.pck, but the files from English(US).pck have the names imbedded in the file, which we can extract.
## Post #172
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-26T16:59:13+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

[http://www.audiokinetic.com/download/](http://www.audiokinetic.com/download/)
## Post #173
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-26T23:20:29+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Oh, well then. I was under the assumption that the official tools were limited to 200 items. 

But now whenever I attempt to open the file it says "Object reference not set to an instance of an object". 

You know what, the heck with it. Like I said, the project is not very useful without the named wav files. (is it?)


EDIT: Hold the phone.

```
	<ShortName>mus_licensed_final\01_HKLUB\mus_lic_01_nwang_mystory.wav</ShortName>
	<Path>sfx\mus_licensed_final\01_hklub\mus_lic_01_nwang_mystory_19be004f.wem</Path>
</File>
```

63805603 is the name of one of the unpacked wav files. I opened it and sure enough, it contains the song "My Story".

If someone creates a program that matches the wav name to it's ID and gives it the real name and path, this could be possible after all.

I don't know anything about file formats, but I do know a microscopic amount of Java, maybe I can make the renamer program myself.
## Post #174
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-26T23:51:54+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

They used FNV1a as hash algo but for BNK files x32 for other files seems x64 with convert to x32
## Post #175
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-29T02:12:16+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I'm not quite sure what that means, but I was able to do this!

> Reading input/2001420.wav
>
> Writing output/bigfu_pain_03.wav
>
> 
>
> Reading input/1752987.wav
>
> Writing output/dialogue/_fsr/d_tags/thug_sporty_full_set_low/selects/winded/thug_sporty_20_winded_03.wav
>
> 
>
> Reading input/2029353.wav
>
> Writing output/ui/_new/ui_upgrade.wav
>
> 
>
> Reading input/1863799.wav
>
> Writing output/collisions/cinder_block/deb_cinder_med03.wav
>
> 
>
> Reading input/1464505.wav
>
> Writing output/fighting/hand-to-hand/hard_smack_punches_AB/HI_Smack_Punch_05.wav
----------------Before-------------------------------------------------------After

----------


[http://www.mediafire.com/download/na7qq ... enamer.jar](http://www.mediafire.com/download/na7qqkevuaul85v/SD_Renamer.jar)
[http://www.mediafire.com/download/7c8jx ... namer.java](http://www.mediafire.com/download/7c8jxgdkrrpa0fj/SD_File_Renamer.java)

Unfortunately I'm only a first-year student, so I don't know any advanced functionality or even a better language.


But still, if I ever manage to open the Wwise project we could very well unpack and successfully repack the PCK file! Has anyone even done that before?

EDIT: Alright, I got the project opened, however, repacking is still a long ways off.

I did manage to rename most of the source WAV files, however it seems to reference .BNK files as well. Question is, does it require premade .bnk files or does it make them itself?

Also, there's this:

```
<ExternalSourcesOutputRoot>D:\UFG\MadScience\Project\SDHD\SDHD_PC\Data\Audio\SD2\wwise\SD2\GeneratedSoundBanks\Windows\Externals\</ExternalSourcesOutputRoot>
```

What the heck's a .wsources file? I doubt it'd be possible to replicate. Will it still pack without it?


Point is, there's still a huge mess to sort out. Would it better to make a separate thread?
## Post #176
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-29T06:39:38+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I don't know about wsources but packer works without them.
## Post #177
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2014-10-29T12:38:08+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

This may not be the perfect place to ask, but does anyone know whether there's a deeper level script/config which determines graphics settings?
I assume there would be something inside the archives, as the DisplaySettings.xml which you get right off the bat is pathetic and i doubt that they would just hardcode such tight set of options.
## Post #178
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-29T16:12:38+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I'm pretty sure DisplaySettings.xml is all there is. Maybe if you poke around Global.big you'll find something, but even if you do it wont be very helpful since we can't run that particular archive unpacked.
## Post #179
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-30T02:20:22+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Using Process Monitor I manged to spot the last four unknown files in CharactersHD.big!

```
Data\Characters_New\Wei_HeadNoBones_HD.temp.bin
Data\Characters_New\Wei_HeadNoBones_HD_TS00.perm.bin
Data\Characters_New\Wei_HeadNoBones_HD_TS00.temp.bin
```


EDIT: And the last four in Vehicles.big!

```
Data\Vehicles_New\Heli01.temp.bin
Data\Vehicles_New\Heli01_ts001.perm.bin
Data\Vehicles_New\Heli01_ts001.temp.bin
```


EDIT:

```
Data\Characters_New\Wei_HeadNoBones.temp.bin
Data\Characters_New\Wei_HeadNoBones_TS00.perm.bin
Data\Characters_New\Wei_HeadNoBones_TS00.temp.bin
Data\Characters_New\AS_H_VendorDLC.perm.bin
Data\Characters_New\AS_H_VendorDLC.temp.bin
Data\Characters_New\AS_B_VendorDLC.perm.bin
Data\Characters_New\AS_B_VendorDLC.temp.bin
Data\Props_New\HandcuffsHQ001.perm.bin
Data\Props_New\HandcuffsHQ001.temp.bin
Data\Props_New\HandcuffsHQ001_ts001.perm.bin
Data\Props_New\HandcuffsHQ001_ts001.temp.bin
Data\Props_New\TinyPhysicsObject.perm.bin
Data\Props_New\TinyPhysicsObject.temp.bin
Data\Props_New\TinyPhysicsObject_ts001.perm.bin
Data\Props_New\TinyPhysicsObject_ts001.temp.bin
```


That's all I could get with this method though, I'll have to check out Ekey's logger after this PCK mess is sorted out.
## Post #180
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-11-09T03:36:48+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> But still, if I ever manage to open the Wwise project we could very well unpack and successfully repack the PCK file! Has anyone even done that before?

EDIT: Alright, I got the project opened, however, repacking is still a long ways off.

I did manage to rename most of the source WAV files, however it seems to reference .BNK files as well. Question is, does it require premade .bnk files or does it make them itself?
I poked around a bit more, and it does in fact require the original BNK files, but luckily those are easy to get. 

However it turns out you can't just stick raw WAV files in there and make it pack, it requires the corresponding WEM files as well, which is some sort of Wwise proprietary format. I knew it couldn't be that easy.
## Post #181
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-11-14T20:39:51+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Anyone managed to get the localization texts out of UI.BIG/BIX yet?
## Post #182
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-11-14T22:15:30+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

The texts are located in "UI.BIG/Data/UI/Localization/". Problem is, you can't actually do anything with them.
## Post #183
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-11-15T10:29:09+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> The texts are located in "UI.BIG/Data/UI/Localization/". Problem is, you can't actually do anything with them.
Yeah, I know that, because I translated the original Sleeping Dogs to Hungarian a while back, but in Definitive Edition a lot of files were changed and Ekey's program doesn't support it anymore. That's why I asked
## Post #184
- Username: tarique
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 20, 2014 12:03 am
- Post datetime: 2015-05-06T11:25:43+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from lostprophet
>
> SergeantJoe wrote:The texts are located in "UI.BIG/Data/UI/Localization/". Problem is, you can't actually do anything with them.
Yeah, I know that, because I translated the original Sleeping Dogs to Hungarian a while back, but in Definitive Edition a lot of files were changed and Ekey's program doesn't support it anymore. That's why I asked
can you help me?
I unpacked the ui.big file. and there are text files in localization file that it has got .bin extension. end unpacker dont see them. 
[http://prntscr.com/724xxp](http://prntscr.com/724xxp)
## Post #185
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-10T00:08:37+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

The .bin unpacker only works for XML .bin files.

You need to edit the files with Notepad.
## Post #186
- Username: tarique
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 20, 2014 12:03 am
- Post datetime: 2015-05-10T13:53:36+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> The .bin unpacker only works for XML .bin files.

You need to edit the files with Notepad.

thank you sir, it works.
and one more question? how can I repack them to the UI.big file?

I saw language parser by ekey but there is no link?
## Post #187
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-10T20:38:19+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I'm pretty sure ekey never released it, and repacking big files is impossible.

Yup, this is the kind of frustration everyone has to deal with. No wonder nobody wants to mod the game.
## Post #188
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-18T14:59:49+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Reuploaded unpacker for Definitive Edition [here](https://www.sendspace.com/file/965jt1)
## Post #189
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-11-24T16:43:36+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Woah, that was unexpected! Thanks man!

Just out of curiousity, were there any changes made? I notice the version number is different.
## Post #190
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-24T17:39:45+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> Just out of curiousity, were there any changes made? I notice the version number is different.
Nothing special. I did some changes for work with BIG files on different platforms. Also some functions moved from library in main executable.

Note: If someone preserved my old logger, re-upload it please.
## Post #191
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-11-24T18:34:33+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

[I got it right here.](http://www.mediafire.com/download/aiujwe0qgtz5vq2/SDDE_Logger_0.0.1_x64.7z) [And here's the ASLR thingy.](http://www.mediafire.com/download/2szon1ga4mq9q3k/ASLR.rar)


And also, do you think it would be possible to look into the 5 unknown files unpacked from Characters.big? If those are fixed/identified we'll finally be able to make real mods! 
I've tried many times myself but to no avail.
## Post #192
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-24T18:45:21+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> I got it right here. I also have the ASLR thingy if you need that too.
Thanks! It's not for me, just for public because links are dead.

> Reply from SergeantJoe
>
> And also, do you think it would be possible to look into the 5 unknown files unpacked from Characters.big? If those are fixed/identified we'll finally be able to make real mods! 
I've tried many times myself but to no avail.
I'll be home in a week to check it out
## Post #193
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-11-25T03:57:47+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Alrighty, I updated my post above with a second link. And once again, huge thanks.
## Post #194
- Username: felisthecat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 10, 2016 9:41 pm
- Post datetime: 2016-02-10T13:46:22+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hello.
Can I do subtitle fonts bigger using mod tools?
## Post #195
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-02-11T14:33:28+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

There are no actual mod tools. And there never will be any because I don't know anything about file formats and other people don't care.
## Post #196
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2016-05-19T22:42:12+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Sorry if I resume this old thread but recently I've noticed an error in official Italian translation of SD (std edition):

[](http://postimg.org/image/ju96e1s3l/)

As you can see, because of a pair of typos in UI.big the game doesn't display framerate correctly. Instead of "%3.1f" they wrote "%3,1f" and this is the result...
So I came in this thread but found no tool to correct the bug. Someone can help me please and maybe have a copy of the original tools to edit game strings?
I'm not interested in modding textures or other things, just wanted to fix the Advanced Video Options text bugs
## Post #197
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-05-26T13:26:12+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

There is no tool to edit the strings. Unpack UI.big, look in "Data/UI/Localization/" and edit the .bin files with Notepad.
## Post #198
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2016-05-26T17:43:48+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from SergeantJoe
>
> There is no tool to edit the strings. Unpack UI.big, look in "Data/UI/Localization/" and edit the .bin files with Notepad.
I tried that but the game hangs on startup when I remove the UI.big file and leave the unpacked version in DATA\UI...

Please, can you explain in detail how to run the game with modified files?
UI is unpacked as:

```
├───Data
│   └───UI <-- I moved this
│       ├───Localization
│       ├───Minimap
│       │   ├───Row_0
│       │   ├───Row_1024
│       │   ├───Row_1280
│       │   ├───Row_1536
│       │   ├───Row_256
│       │   ├───Row_512
│       │   └───Row_768
│       └───Screens
└───__Unknown

```

...so I edited and moved UI branch under <Steam_game_path>\Data\ but the game hangs on startup.

EDIT: fixed the problem of broken FPS counter in Italian in another way... see on Steam my guide.
## Post #199
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-05-27T05:29:16+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

I've never done it myself, so I don't know how he did it, but that's the method for editing most things. It hangs because it's missing those unknown files.
## Post #200
- Username: Marusero
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jan 15, 2012 4:12 am
- Post datetime: 2016-12-12T23:09:16+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hello.
Does anyone still have a PS3 version?
## Post #201
- Username: Jacob
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 15, 2017 8:59 pm
- Post datetime: 2017-12-15T13:02:43+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Hi, 
I have a quick questions about animations. I unpacked Big file and I have a lot of bin animations files in the folder.
Is it possible to read those files? Can I unpack those animations to any 3d format so i can view it in 3dsmax or other programs?

Thanks!
## Post #202
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-12-29T07:36:13+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from Jacob
>
> Hi, 
I have a quick questions about animations. I unpacked Big file and I have a lot of bin animations files in the folder.
Is it possible to read those files? Can I unpack those animations to any 3d format so i can view it in 3dsmax or other programs?!
For the past FIVE YEARS I've been trying to get useable animations. I've tried tons of different tools, I've asked many people, but nothing worked and nobody could figure it out.

Here's the rundown:
This game uses the Havok animation system. Each bin file contains multiple binary Havok hkx animations, you can separate them pretty easily.

It is possible to convert binary hkx to plaintext xml hkx using AssetCC from official Havok SDK, and load it into HavokStandaloneTool to view the animation.

However, there's no way to convert the hkx data to a useable format like fbx. And it looks like there never will be because nobody is able to help.
## Post #203
- Username: Jacob
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 15, 2017 8:59 pm
- Post datetime: 2018-01-02T15:58:02+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> For the past FIVE YEARS I've been trying to get useable animations. I've tried tons of different tools, I've asked many people, but nothing worked and nobody could figure it out.
>
> 
>
> Here's the rundown:
>
> This game uses the Havok animation system. Each bin file contains multiple binary Havok hkx animations, you can separate them pretty easily.
>
> 
>
> It is possible to convert binary hkx to plaintext xml hkx using AssetCC from official Havok SDK, and load it into HavokStandaloneTool to view the animation.
>
> 
>
> However, there's no way to convert the hkx data to a useable format like fbx. And it looks like there never will be because nobody is able to help.

Thanks for answer  , shame that it ended up this way.
## Post #204
- Username: iwl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 03, 2018 11:58 am
- Post datetime: 2018-01-03T04:01:59+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Could someone re-upload the most recent unpacker for Definitive Edition? The one from Wed Nov 18, 2015 2:59 pm has invalid file.
## Post #205
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2018-01-03T08:12:48+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from iwl
>
> Could someone re-upload the most recent unpacker for Definitive Edition? The one from Wed Nov 18, 2015 2:59 pm has invalid file.
[Here you go.](https://www.mediafire.com/folder/bcik5bwvi4z0l/SD)
## Post #206
- Username: iwl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 03, 2018 11:58 am
- Post datetime: 2018-01-03T12:16:54+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Thanks man!
## Post #207
- Username: mcc26
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 15, 2017 1:23 am
- Post datetime: 2018-10-07T19:59:59+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

Is there new news about Compressor or Repack BIG files ???
## Post #208
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2018-10-08T06:37:31+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from mcc26
>
> Is there new news about Compressor or Repack BIG files ???
Sorry, man you're 6 years too late. There is no news, and there never will be, because nobody knows that this game exists.
## Post #209
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2018-10-08T07:16:36+00:00
- Post Title: Re: [REQ][PC]Sleeping Dogs .big files

> Reply from mcc26
>
> Is there new news about Compressor or Repack BIG files ???
Unfortunately game hacking forums like this are mostly focused on extracting and ripping/stealing assets from games… and just a few games have also a repacker (useful for translators etc.), sigh…
