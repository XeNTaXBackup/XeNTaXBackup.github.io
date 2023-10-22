## Post #1
- Username: blenux
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 25, 2019 5:06 pm
- Post datetime: 2019-05-17T09:29:14+00:00
- Post Title: Rage 2 .arc .tab Archives

Hi all any chance of getting some Rage 2 scripts, files are .arc and .tab pretty sure they are different to the Rage 1 formats.

[File and Last files uploaded here in each folder. ](https://mega.nz/#F!NYcS1CTR!M4HVbSEVrEFnG0YqnK8-3A)
## Post #2
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2019-05-17T17:26:46+00:00
- Post Title: Rage 2 .arc .tab Archives

it's look 

[https://forum.xentax.com/viewtopic.php?f=10&t=19143](https://forum.xentax.com/viewtopic.php?f=10&t=19143)
## Post #3
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2019-05-17T21:14:21+00:00
- Post Title: Rage 2 .arc .tab Archives

[https://github.com/gibbed/Gibbed.JustCause4](https://github.com/gibbed/Gibbed.JustCause4) can apparently work with compressed JC4 arc/tab files perfectly, so it should be pretty easy to update it for Rage 2's files.. Maybe gibbed will push an update soon to support them, otherwise I'll try taking a look later.

EDIT: had a quick look through, seems they changed the header & file entry formats between JC4 and R2, header had a file entry count added to it (shifting some of the fields around), but that's easy to work around in gibbed's code.

Harder part is the file entry changes, seems they added 4 bytes to the start of the entry format but I'm not sure what those 4 bytes are for though, could be they extended the name-hash from 32 to 64bit, or maybe the 4 bytes is used as an XOR key or something (edit:nope)... still need to try some things out.

EDIT: with those changes files seem to extract fine! Haven't got any file-names associated with the extracted files yet though, so it's all files with names like 0D116543.unknown 

Hoping they haven't changed the name hashing algo too much, since I don't really want to go reversing the EXE itself... I'll try looking into it tomorrow, hopefully be able to post a fixed up tool soon.

EDIT: For anyone interested here's a 010 template for reading JC4 & RAGE2 .tab files, you can see the difference in the file entries here (TAB_ENTRY_V2 vs TAB_ENTRY_V3)

```
//--- 010 Editor v9.0.1 Binary Template
//
//      File: AvalancheTabFile.bt
//   Authors: infogram
//   Version: 1.0
// File Mask: *.tab
//  ID Bytes: 54 41 42 00
//
// Structs based on Gibbed.JustCause4, thanks to gibbed!
//
// TODO: other avalanche games (JC2/JC3/MadMax?)
//------------------------------------------------

// Split magic/version portion of header to its own struct
// That way we can decide what other part of the header to read based on version #...
typedef struct TAB_MAGIC
{
  DWORD Magic;
  WORD MajorVersion;
  WORD MinorVersion;
};

typedef struct TAB_HEADER_V2
{
  DWORD Alignment;
  DWORD Unknown0C;
  DWORD CompressedBlockSize;
  DWORD UncompressedBlockSize;
  DWORD CompressedBlockCount;
};

typedef struct TAB_ENTRY_V2 
{
  DWORD NameHash;
  DWORD Offset;
  DWORD CompressedSize;
  DWORD UncompressedSize;
  WORD CompressedBlockIdx;
  BYTE CompressionType; // 1 = Zlib, 4 = Oodle
  BYTE CompressionFlags;
};

typedef struct TAB_HEADER_V3
{
  DWORD Alignment;
  DWORD FileEntryCount;
  DWORD CompressedBlockCount;
  DWORD Unknown14;
  DWORD CompressedBlockSize;
  DWORD UncompressedBlockSize;
};

typedef struct TAB_ENTRY_V3
{
  DWORD NameHash; // Is this still the hash? or maybe Unknown04? or maybe both fields are a 64-bit hash?
  DWORD Unknown04;
  DWORD Offset;
  DWORD CompressedSize;
  DWORD UncompressedSize;
  WORD CompressedBlockIdx;
  BYTE CompressionType; // 1 = Zlib, 4 = Oodle
  BYTE CompressionFlags;
};

typedef struct TAB_COMPRESSED_BLOCK
{
  DWORD CompressedSize;
  DWORD UncompressedSize;
};

TAB_MAGIC Magic;
if(Magic.MajorVersion == 2 && Magic.MinorVersion == 1)
{
  // V2.1 == Just Cause 4
  
  TAB_HEADER_V2 Header;
  TAB_COMPRESSED_BLOCK CompressedBlocks[Header.CompressedBlockCount];
  
  // No file count in V2, so calc how many entries based on filesize
  local int numEntries = (FileSize() - FTell()) / 0x14;
  TAB_ENTRY_V2 FileEntries[numEntries];
}
else if(Magic.MajorVersion == 3 && Magic.MinorVersion == 1)
{
  // V3.1 == RAGE 2
  
  TAB_HEADER_V3 Header;
  TAB_COMPRESSED_BLOCK CompressedBlocks[Header.CompressedBlockCount];
  TAB_ENTRY_V3 FileEntries[Header.FileEntryCount];
}
else
{
  Printf("Unknown TAB version v%d.%d!", Magic.MajorVersion, Magic.MinorVersion);
}

```
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-05-19T14:39:08+00:00
- Post Title: Rage 2 .arc .tab Archives

This could be really useful as the OGG sound files in the game15.arch and game16.arc archives don't have names.
## Post #5
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2019-05-21T00:10:36+00:00
- Post Title: Rage 2 .arc .tab Archives

> Reply from infogram ↑Sat May 18, 2019 5:14 am at Sat May 18, 2019 5:14 am
>
> 
https://github.com/gibbed/Gibbed.JustCause4 can apparently work with compressed JC4 arc/tab files perfectly, so it should be pretty easy to update it for Rage 2's files.. Maybe gibbed will push an update soon to support them, otherwise I'll try taking a look later.

EDIT: had a quick look through, seems they changed the header & file entry formats between JC4 and R2, header had a file entry count added to it (shifting some of the fields around), but that's easy to work around in gibbed's code.

Harder part is the file entry changes, seems they added 4 bytes to the start of the entry format but I'm not sure what those 4 bytes are for though, could be they extended the name-hash from 32 to 64bit, or maybe the 4 bytes is used as an XOR key or something (edit:nope)... still need to try some things out.

EDIT: with those changes files seem to extract fine! Haven't got any file-names associated with the extracted files yet though, so it's all files with names like 0D116543.unknown 

Hoping they haven't changed the name hashing algo too much, since I don't really want to go reversing the EXE itself... I'll try looking into it tomorrow, hopefully be able to post a fixed up tool soon.

EDIT: For anyone interested here's a 010 template for reading JC4 & RAGE2 .tab files, you can see the difference in the file entries here (TAB_ENTRY_V2 vs TAB_ENTRY_V3)
Code: Select all//------------------------------------------------
//--- 010 Editor v9.0.1 Binary Template
//
//      File: AvalancheTabFile.bt
//   Authors: infogram
//   Version: 1.0
// File Mask: *.tab
//  ID Bytes: 54 41 42 00
//
// Structs based on Gibbed.JustCause4, thanks to gibbed!
//
// TODO: other avalanche games (JC2/JC3/MadMax?)
//------------------------------------------------

// Split magic/version portion of header to its own struct
// That way we can decide what other part of the header to read based on version #...
typedef struct TAB_MAGIC
{
  DWORD Magic;
  WORD MajorVersion;
  WORD MinorVersion;
};

typedef struct TAB_HEADER_V2
{
  DWORD Alignment;
  DWORD Unknown0C;
  DWORD CompressedBlockSize;
  DWORD UncompressedBlockSize;
  DWORD CompressedBlockCount;
};

typedef struct TAB_ENTRY_V2 
{
  DWORD NameHash;
  DWORD Offset;
  DWORD CompressedSize;
  DWORD UncompressedSize;
  WORD CompressedBlockIdx;
  BYTE CompressionType; // 1 = Zlib, 4 = Oodle
  BYTE CompressionFlags;
};

typedef struct TAB_HEADER_V3
{
  DWORD Alignment;
  DWORD FileEntryCount;
  DWORD CompressedBlockCount;
  DWORD Unknown14;
  DWORD CompressedBlockSize;
  DWORD UncompressedBlockSize;
};

typedef struct TAB_ENTRY_V3
{
  DWORD NameHash; // Is this still the hash? or maybe Unknown04? or maybe both fields are a 64-bit hash?
  DWORD Unknown04;
  DWORD Offset;
  DWORD CompressedSize;
  DWORD UncompressedSize;
  WORD CompressedBlockIdx;
  BYTE CompressionType; // 1 = Zlib, 4 = Oodle
  BYTE CompressionFlags;
};

typedef struct TAB_COMPRESSED_BLOCK
{
  DWORD CompressedSize;
  DWORD UncompressedSize;
};

TAB_MAGIC Magic;
if(Magic.MajorVersion == 2 && Magic.MinorVersion == 1)
{
  // V2.1 == Just Cause 4
  
  TAB_HEADER_V2 Header;
  TAB_COMPRESSED_BLOCK CompressedBlocks[Header.CompressedBlockCount];
  
  // No file count in V2, so calc how many entries based on filesize
  local int numEntries = (FileSize() - FTell()) / 0x14;
  TAB_ENTRY_V2 FileEntries[numEntries];
}
else if(Magic.MajorVersion == 3 && Magic.MinorVersion == 1)
{
  // V3.1 == RAGE 2
  
  TAB_HEADER_V3 Header;
  TAB_COMPRESSED_BLOCK CompressedBlocks[Header.CompressedBlockCount];
  TAB_ENTRY_V3 FileEntries[Header.FileEntryCount];
}
else
{
  Printf("Unknown TAB version v%d.%d!", Magic.MajorVersion, Magic.MinorVersion);
}

The game uses 64bit hash for names, and entries are sorted by the hash.
Hash of 
```
text/master_eng.stringlookup
```
 should be 
```
0x8453EE3581F31F39
```
.
I found the hash algorithm. It's MurmurHash3 128bit x64 version. The first 64bit is taken from the resulting 128bit.
I tried it [here](https://murmurhash.shorelabs.com/)
## Post #6
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2019-05-22T21:23:58+00:00
- Post Title: Rage 2 .arc .tab Archives

> Reply from rengareng ↑Tue May 21, 2019 8:10 am at Tue May 21, 2019 8:10 am
>
> 
The game uses 64bit hash for names, and entries are sorted by the hash.
Hash of Code: Select alltext/master_eng.stringlookup should be Code: Select all0x8453EE3581F31F39.
I found the hash algorithm. It's MurmurHash3 128bit x64 version. The first 64bit is taken from the resulting 128bit.
I tried it here

Holy crap, thanks a ton for finding that out! I was trying a bunch of things, like weird 64-bit versions of lookup3, searching the exe for hash algo patterns.. really wasn't having any luck with it though, huge thanks for figuring it out 

(wonder what made them change the hash algo, they do still use lookup3 in some string-related stuff, guess Murmur must be faster to calculate or something?)

Anyway I've updated gibbed's JustCause4 tool with the changed file format + Murmur3 algo, and it all seems to work great! Not really sure if we can repack at all though, maybe the game can load loose files if we're lucky.

Now I just need to test it against all of the archives and build a file-list to go with the hashes now (my friend Grinderkiller is working on that part), after that I'll post it up here (along with the changed source code of course), should be ready by tomorrow hopefully 

(edit: just heard from Grinderkiller that the game will load in loose files fine! It worked for the videos at least, haven't tested any other files yet afaik, but sounds good so far!)

Rage2Unpack Release

Rage2Unpack Download: [http://bit.ly/2HO6PRl](http://bit.ly/2HO6PRl)

Read the readme to learn how to use it, and download the latest filelist from [https://forum.xentax.com/viewtopic.php?p=153102#p153102](https://forum.xentax.com/viewtopic.php?p=153102#p153102) to extract more files!

Rage2Hook Release

Also made a DLL hook for dumping filenames from the game, it'll dump the filenames of any content that the game loads in.

If people could play through the game with this DLL enabled and post the rage2hook.log from it here, hopefully we can combine them all and cover more of the archives that way, like how people have been doing for RE2 Remake.

Rage2Hook Download: [http://bit.ly/2VZChpx](http://bit.ly/2VZChpx)
Just extract the dll file next to your RAGE2.exe, and now whenever you run the game all content filenames will be logged to rage2hook.log, thanks in advance to anyone that submits logs for us 

(this hook is made for the patch 1 Steam release, but might work fine with others, please let me know if you have any issues with your copy!)
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-05-23T21:58:10+00:00
- Post Title: Rage 2 .arc .tab Archives

Thanks for tool and the hook. with the hook enabled, does the names get dumped into its own log file or does it put inot a .txt file?
## Post #8
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2019-05-23T22:16:47+00:00
- Post Title: Rage 2 .arc .tab Archives

Got the the filelists up to 16% (49920/302871), just copied some translation/audio filenames and edited them for each of the different languages, and a few other small adds.
Seems it's mostly audio related stuff that's missing (probably story related stuff, since the filelist is mostly from early-game afaik), hopefully people can help fill those gaps with their logs 

Download filelists update 1: [http://bit.ly/2VIEksZ](http://bit.ly/2VIEksZ)
Just delete the projects directory from Rage2Unpack and extract the one from that zip in its place.

> Reply from OrangeC ↑Fri May 24, 2019 5:58 am at Fri May 24, 2019 5:58 am
>
> 
Thanks for tool and the hook. with the hook enabled, does the names get dumped into its own log file or does it put inot a .txt file?

They should get put in the rage2hook.log file next to RAGE2.exe, as long as the RAGE2 dir is writable at least (if it doesn't show up maybe run the RAGE2.exe as administrator, that should let the log be written no matter what)

(edit: the log is appended to the last log too, so don't worry about overwriting any older logs, it should always save to the end of any previous one)

After you've finished logging you can copy that rage2hook.log into "projects\RAGE 2\files\archives_win64", rename it as "new.filelist" and then run RebuildFileLists.exe, that should then check your new filelist for any missing files and add them to the right .filelist file for it, then you can check "projects\RAGE 2\files\status.txt" to see the new count of named files.
(if you want to submit your log you don't need to do this though, just post your .log file here and I'll manage the rest )
## Post #9
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2019-05-24T00:59:36+00:00
- Post Title: Rage 2 .arc .tab Archives

> Reply from infogram ↑Thu May 23, 2019 5:23 am at Thu May 23, 2019 5:23 am
>
> 
rengareng wrote: ↑Tue May 21, 2019 8:10 am
The game uses 64bit hash for names, and entries are sorted by the hash.
Hash of Code: Select alltext/master_eng.stringlookup should be Code: Select all0x8453EE3581F31F39.
I found the hash algorithm. It's MurmurHash3 128bit x64 version. The first 64bit is taken from the resulting 128bit.
I tried it here


Holy crap, thanks a ton for finding that out! I was trying a bunch of things, like weird 64-bit versions of lookup3, searching the exe for hash algo patterns.. really wasn't having any luck with it though, huge thanks for figuring it out 

(wonder what made them change the hash algo, they do still use lookup3 in some string-related stuff, guess Murmur must be faster to calculate or something?)

Anyway I've updated gibbed's JustCause4 tool with the changed file format + Murmur3 algo, and it all seems to work great! Not really sure if we can repack at all though, maybe the game can load loose files if we're lucky.

Now I just need to test it against all of the archives and build a file-list to go with the hashes now (my friend Grinderkiller is working on that part), after that I'll post it up here (along with the changed source code of course), should be ready by tomorrow hopefully 

(edit: just heard from Grinderkiller that the game will load in loose files fine! It worked for the videos at least, haven't tested any other files yet afaik, but sounds good so far!)

Rage2Unpack Release

So the tool seems to be working fine, and Grinderkiller got back to me about the filelists.
He collected them from the start of a new game, but so far only 5% of files are named (17901/302871).
It's a start at least, but seems there's still a lot more work to be done to get everything named...
(edit: latest filelist has 16% named, check my post below for updated filelists!)

What this means is that extracting the .tab files will mostly result in files being called stuff like "0C3247F95F5F301A.unknown" instead of being named something like "climate\zone_0\diffuse_textures_mid_0.ddsc", afaik it's mostly sounds that are unnamed, but there are some other filetypes too.

Anyway I don't want to keep people waiting anymore, so here's the tool:

Rage2Unpack Download: http://bit.ly/2HO6PRl
(edit: check my post below for updated filelists to use with rage2unpack!)

Rage2Hook Release

Also made a DLL hook for dumping filenames from the game, it'll dump the filenames of any content that the game loads in.

If people could play through the game with this DLL enabled and post the rage2hook.log from it here, hopefully we can combine them all and cover more of the archives that way, like how people have been doing for RE2 Remake.

Rage2Hook Download: http://bit.ly/2VZChpx

This hook is made for the patch 1 Steam release, but might work fine with others, let me know if you have any issues with your copy.

Can you share the source code for the hook? I used dinput8.dll for other games, it didn't work this game. 
I also found the hash function from the executable:

```
uint64_t MurmurHash3(const void * key, int64_t key_length, int32_t seed);

```
## Post #10
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2019-05-24T01:50:59+00:00
- Post Title: Rage 2 .arc .tab Archives

> Reply from rengareng ↑Fri May 24, 2019 8:59 am at Fri May 24, 2019 8:59 am
>
> 

Can you share the source code for the hook? I used dinput8.dll for other games, it didn't work this game. 
I also found the hash function from the executable:
Code: Select all// 0x107ABF0 is the relative virtual address (rva) for RAGE2.exe (update 1)
uint64_t MurmurHash3(const void * key, int64_t key_length, int32_t seed);

Yep that's the same function I hook, I think 0x107ABF0 is for the earlier update though, it moved to 0x107EF10 in the latest, unless I maybe got the updates confused... (I found it at those addresses in two different EXEs at least), but 0x107EF10 is the one Rage2Hook checks & hooks.

You can have the code for it sure, it's a little messy since I put it together pretty quick though: [https://pastebin.com/sfF0VFHg](https://pastebin.com/sfF0VFHg)
Once you build it rename the dll to xinput9_1_0.dll to load it into the game, proxy.cpp handles all the exports for that.

There's a few extra things in that source that isn't in the released Rage2Hook, eg. if you have the filelists in your Rage2 folder (SteamApps\RAGE 2\projects\RAGE 2\files\archives_win64\initial\...) it'll load them all and make sure rage2hook.log won't contain any already known filenames. It also now checks for extension in the hashed string to determine if it's a path that we should log (previously it just checked for "/" character).
I'll probably release a built DLL with all that tomorrow after I test some more, and some more filelist adds too, bit late here atm
## Post #11
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2019-05-24T02:58:09+00:00
- Post Title: Rage 2 .arc .tab Archives

> Reply from infogram ↑Fri May 24, 2019 9:50 am at Fri May 24, 2019 9:50 am
>
> 
rengareng wrote: ↑Fri May 24, 2019 8:59 am

Can you share the source code for the hook? I used dinput8.dll for other games, it didn't work this game. 
I also found the hash function from the executable:
Code: Select all// 0x107ABF0 is the relative virtual address (rva) for RAGE2.exe (update 1)
uint64_t MurmurHash3(const void * key, int64_t key_length, int32_t seed);



Yep that's the same function I hook, I think 0x107ABF0 is for the earlier update though, it moved to 0x107EF10 in the latest, unless I maybe got the updates confused... (I found it at those addresses in two different EXEs at least), but 0x107EF10 is the one Rage2Hook checks & hooks.

You can have the code for it sure, it's a little messy since I put it together pretty quick though: https://pastebin.com/sfF0VFHg
Once you build it rename the dll to xinput9_1_0.dll to load it into the game, proxy.cpp handles all the exports for that.

There's a few extra things in that source that isn't in the released Rage2Hook, eg. if you have the filelists in your Rage2 folder (SteamApps\RAGE 2\projects\RAGE 2\files\archives_win64\initial\...) it'll load them all and make sure rage2hook.log won't contain any already known filenames. It also now checks for extension in the hashed string to determine if it's a path that we should log (previously it just checked for "/" character).
I'll probably release a built DLL with all that tomorrow after I test some more, and some more filelist adds too, bit late here atm
It is unfortunate that they use this function for many different purposes. Only thing I can suggest for performance improvement is that using unordered_set instead of vector to lookup for a hash quickly.
## Post #12
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2019-05-24T06:38:22+00:00
- Post Title: Rage 2 .arc .tab Archives

Wow amazing genious !!  

audio look fsb5 header 
so we got probably the file uses encryption,

fsbext say  insert the needed keyword:
  type ? for viewing the hex dump of the first 176 bytes of the file because
  it's possible to see part of the plain-text password in the encrypted file!
## Post #13
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-24T08:12:32+00:00
- Post Title: Rage 2 .arc .tab Archives

That is awesome ,thanks for sharing with us infogram
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-05-24T12:03:20+00:00
- Post Title: Rage 2 .arc .tab Archives

Tried to rebuildfilenamelists tool but got install path not detected.
## Post #15
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2019-05-24T13:30:00+00:00
- Post Title: Rage 2 .arc .tab Archives

Hey all, just a small update for you guys... filelist is now 60% (182342/302871) complete 

With a lot of searching and some tricks I managed to get it up to there, there's still that 40% to go though, and now I really don't have any more tricks up my sleeve to pull... so I think the only way we'll get any further is from people posting Rage2Hook logs here, really hope you guys can help out  

Download filelist update 2: [http://bit.ly/2QkyHAk](http://bit.ly/2QkyHAk)
(delete the "projects" directory from Rage2Unpack and extract the one from this zip in its place.)

Small breakdown of the filelist: we have 89% (31712/35328) of the main non-translation-related files, and 56% (150630/267543) of the translation/voice related files.
I'm pretty sure the missing files are mostly quest/story related now though, hopefully in time we'll get those filled.

Enjoy 

> Reply from rengareng ↑Fri May 24, 2019 10:58 am at Fri May 24, 2019 10:58 am
>
> 
It is unfortunate that they use this function for many different purposes. Only thing I can suggest for performance improvement is that using unordered_set instead of vector to lookup for a hash quickly.
Yeah it's too bad the game uses it so much, was thinking of debugging it to try and narrow down which caller is actually responsible for paths, but I figured it's probably better to log the main Murmur func instead of limiting it to just one caller.

Thanks for the tip about unordered_set too, will add that into the next Rage2Hook release  

Also it really sucks they order by hash in the .tab file, in some other games that use hashes they sometimes leave it sorted alphabetical, which can give us clues about some missing files, no such luck here though 

edit: oh wow, turns out while .tab is ordered by hash, the data in the .arc is actually ordered alphabetically, so you can just sort the tab entries by the data offset to get an alphabetical listing of them! (as in, sorted alphabetically without needing to know the filename )

That makes working out missing items a lot easier.. for example see this pic: [https://i.imgur.com/68htpqc.png](https://i.imgur.com/68htpqc.png)
The pink ones are missing filenames, but now that it's sorted alphabetically next to the others, you can make a good guess for what the filename might be 

> Reply from kilik ↑Fri May 24, 2019 2:38 pm at Fri May 24, 2019 2:38 pm
>
> 
audio look fsb5 header 
so we got probably the file uses encryption,
Hmm, have you checked if there's any JC3/JC4 tools for them? If there's anything close maybe we can tweak it like we did with gibbed's tool.

> Reply from Ciprianno ↑Fri May 24, 2019 4:12 pm at Fri May 24, 2019 4:12 pm
>
> 
That is awesome ,thanks for sharing with us infogram
No problem, hope people find it useful!

> Reply from OrangeC ↑Fri May 24, 2019 8:03 pm at Fri May 24, 2019 8:03 pm
>
> 
Tried to rebuildfilenamelists tool but got install path not detected.
I had the same problem too, it's an issue with the original tool afaik.
Easy to fix though, open regedit, go to "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\", make a new key called "Steam App 548570", then make a string entry inside it called InstallLocation, and set to your RAGE 2 dir.

Here's a .reg file that will do all that, make sure to edit the install path and then save it into a .reg file, then run it and allow it to import etc: [https://pastebin.com/raw/KdyXYmLM](https://pastebin.com/raw/KdyXYmLM)
## Post #16
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2019-05-24T22:31:39+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Not sure if you are mapping .ogg files, but a lot of the UNKNOWNs are actually that  See game10.arc/.tab:



That we don't know their names, that's a different story. However you could do a look-up for "OggS" (first 4 bytes). Not sure how much of the "misses" will the "ogg" files cover, but you can give it a try
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-05-24T22:43:38+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Some ogg files have had their names, they are just not complete yet. I will play later today to capture more names with the hook,
## Post #18
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-24T23:11:34+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Any takes on ee,bl,fl,nl files?
They changed them from sarc/aaf into raw format. They now contains first 4 bytes what I believe is hash, and then files.
However there is no offset table, nor filenames, nothing. Just raw data.
My assumption was, that there should be some large file, with all informations, but I found none so far.

EDIT: 
My assumptions were correct, game loads file called sarc.0.gtoc. 
And of course I didn't extracted all archives, so it's no wonder that I couldn't find anything.
## Post #19
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-25T08:37:16+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Here is my rage2hook.log
[rage2hook.rar](https://xentaxbackup.github.io/file/16279_rage2hook.rar)
## Post #20
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-25T15:44:41+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Just released tool, that let's you extract, ee, fl, nl, bl files. 
Be sure to set correct settings. 
I was able to extract every one.
Tested textures too, without problems.

[https://github.com/PredatorCZ/ApexToolset](https://github.com/PredatorCZ/ApexToolset)
## Post #21
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2019-05-25T17:34:42+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Edit:
Rage2Hook 0.3
This adds support for the new RAGE 2 update to Rage2Hook, with this update all currently released RAGE 2 versions should be supported (well, the Steam versions at least), any future updates will still have to be added manually though... (maybe I'll add pattern matching stuff for it soon)

This also adds a small feature to Rage2Hook: if you have the Rage2Unpack filelists next to your RAGE2.exe, it'll load the filenames from them and then stop any already known filenames being output to the log file, useful to let you know what files you've found that are currently missing from the public filelist!

Rage2Hook 0.3 Download: [http://bit.ly/2Ma6mhK](http://bit.ly/2Ma6mhK)
(source code can be found here: [https://pastebin.com/4vYDRdLc](https://pastebin.com/4vYDRdLc))

Rage2Unpack filelist update 3
Another small update, bringing us up to 61% (185928/302871) of files, thanks to the log posted by Ciprianno and a few manual finds.
That's 3586 new filenames added to the list 

Filelist update 3 download: [http://bit.ly/2YTrr1r](http://bit.ly/2YTrr1r)
(delete the "projects" directory from Rage2Unpack and extract the one from this zip in its place)

> Reply from PredatorCZ ↑Sat May 25, 2019 11:44 pm at Sat May 25, 2019 11:44 pm
>
> 
Just released tool, that let's you extract, ee, fl, nl, bl files. 
Be sure to set correct settings. 
I was able to extract every one.
Tested textures too, without problems.

https://github.com/PredatorCZ/ApexToolset

Wow nice work! I had no idea ee/fl/nl/bl files were mini-archives, interesting.
I did look into the sarc.0.gtoc files to get some filenames for the list, but didn't really look into it any more than that.
So I guess that must mean if a ee/fl/nl/bl isn't defined in the sarc file then the game can't use it? I'm pretty sure I found a few of them that weren't though, weird, maybe unused content or something like that...

> Reply from sunbeam906 ↑Sat May 25, 2019 6:31 am at Sat May 25, 2019 6:31 am
>
> 
Not sure if you are mapping .ogg files, but a lot of the UNKNOWNs are actually that  See game10.arc/.tab:

That we don't know their names, that's a different story. However you could do a look-up for "OggS" (first 4 bytes). Not sure how much of the "misses" will the "ogg" files cover, but you can give it a try

Yeah like OrangeC said do we have some of them named, but theres still tons of them we haven't found yet.. especially in the languages archives too.
Luckily the languages all follow the same name structure, so finding the name for a sound in one language can let us find them in all the others (except for the sole "ara" language file, no idea what the name for that file is, but doubt the game even uses it so meh)

It's too bad theres no metadata in the Ogg to give us an idea of their filename, maybe if we're lucky we'll find a file somewhere that lists all the sounds used in the game or something.

> Reply from Ciprianno ↑Sat May 25, 2019 4:37 pm at Sat May 25, 2019 4:37 pm
>
> 
Here is my rage2hook.log
Thanks a lot! I'll post an updated filelist with it merged in soon. (edit: added the filelist above!)
## Post #22
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-25T19:43:14+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Here is my rage2hook.log with more ogg sound revealed , look at the bottom of the log file
[rage2hook.rar](https://xentaxbackup.github.io/file/16283_rage2hook.rar)
## Post #23
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2019-05-25T21:11:07+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

> Reply from Ciprianno ↑Sun May 26, 2019 3:43 am at Sun May 26, 2019 3:43 am
>
> 
Here is my rage2hook.log with more ogg sound revealed , look at the bottom of the log file

Good stuff, added that & a log I just made over the past few hours, we're now sitting at 63% (191961/302871) 

Filelist update 4 download (+6033 names): [http://bit.ly/30JtW8k](http://bit.ly/30JtW8k)
## Post #24
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-27T05:50:59+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

> Reply from infogram ↑Sun May 26, 2019 5:11 am at Sun May 26, 2019 5:11 am
>
> 
Ciprianno wrote: ↑Sun May 26, 2019 3:43 am
Here is my rage2hook.log with more ogg sound revealed , look at the bottom of the log file


Good stuff, added that & a log I just made over the past few hours, we're now sitting at 63% (191961/302871) 

Filelist update 4 download (+6033 names): http://bit.ly/30JtW8k
Here ..., another one
[rage2hook.rar](https://xentaxbackup.github.io/file/16294_rage2hook.rar)
## Post #25
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2019-05-27T09:08:05+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Updated filelist. Merged from all what infogram and rest post + me. 195966/302871 (64%)

```

```
## Post #26
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2019-05-27T15:10:17+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

EDIT:
Rage2Unpack 0.3a
Discovered a small bug where filenames that have capital letters wouldn't be processed correctly (would previously turn all filenames to lowercase, which I guess was fine for JC4, but RAGE2 seems to have some names that require capitals for hashes to match properly...)

Luckily was easy to fix, and I also figured out how to speed up RebuildFileLists.exe by a pretty big factor as well.

Found a few more filelist adds too, bringing us up to 201321/302871 (66%) 

Download Rage2Unpack 0.3a: [http://bit.ly/2JFIxfL](http://bit.ly/2JFIxfL)

Ideal setup is to extract the zip contents to your RAGE 2 base folder, next to RAGE2.exe.
This way if you use the [latest Rage2Hook DLL](https://forum.xentax.com/viewtopic.php?p=153102#p153102) it can read the filelists, and will then only output missing filenames to the rage2hook.log file.

If you have problems running RebuildFileLists.exe, I wrote about a quick fix for it at the bottom of this post here: [https://forum.xentax.com/viewtopic.php?p=153058#p153058](https://forum.xentax.com/viewtopic.php?p=153058#p153058)
## Post #27
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-28T21:58:41+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Last one
[rage2hook.rar](https://xentaxbackup.github.io/file/16299_rage2hook.rar)
## Post #28
- Username: blenux
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 25, 2019 5:06 pm
- Post datetime: 2019-05-30T09:24:47+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Hey guys, thanks for the info, so how does one use this exactly (I can be clueless at times sorry), I run the game and then just run the rage2unpack.exe ?
## Post #29
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2019-06-01T16:58:16+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

How to packing back the unpacked files to tab\arc?
## Post #30
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2019-06-02T07:40:59+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

> Reply from Zotya0330 ↑Sun Jun 02, 2019 12:58 am at Sun Jun 02, 2019 12:58 am
>
> 
How to packing back the unpacked files to tab\arc?
There is no need to pack them back to arc. Game loads unpacked files just fine.
Put unpacked files/folders to the main root next to the RAGE2.exe.
## Post #31
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2019-06-02T08:32:23+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

I tried, but game crashing
I was put the master_eng.stringlookup file to C:\Program Files (x86)\Steam\steamapps\common\RAGE 2\ nothing happend game still english
I tried C:\Program Files (x86)\Steam\steamapps\common\RAGE 2\text\master_eng.stringlookup game crashing
## Post #32
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2019-06-02T21:44:43+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Strange i put master_eng.striglookup to the D:\GAMES\Steam\steamapps\common\RAGE 2\text\master_eng.stringlookup
and game loads fine.
## Post #33
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2019-06-07T16:00:31+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

And you unpack, edit and pack back the master_eng.stringlookup file?
I edit and pack back then i put C:\Program Files (x86)\Steam\steamapps\common\RAGE 2\text\master_eng.stringlookup
And when i start the game the error reporting starts
## Post #34
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2019-06-08T10:52:43+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Here is my edited and repacked master_eng.stringlookup file:
[https://mega.nz/#!1YpkFYxS!zKUEBNi-7nzq ... bTtDInEAc4](https://mega.nz/#!1YpkFYxS!zKUEBNi-7nzqVze2TNB2fvaGljEJ20u4FbTtDInEAc4)
## Post #35
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2019-06-08T20:33:42+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

> Reply from Zotya0330 ↑Sat Jun 08, 2019 12:00 am at Sat Jun 08, 2019 12:00 am
>
> 
And you unpack, edit and pack back the master_eng.stringlookup file?
I edit and pack back then i put C:\Program Files (x86)\Steam\steamapps\common\RAGE 2\text\master_eng.stringlookup
And when i start the game the error reporting starts
You don't even say that before that you tried repack stringlookup file. Now i have clear. Don't expect nothing good if you using tools for JC.
## Post #36
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2019-06-08T21:28:25+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

I using Autoit Rage 2 export\import texttool, not JC.
## Post #37
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2019-06-19T18:54:57+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

sorry little lost fsbext.exe say password 

[https://forum.xentax.com/viewtopic.php? ... vc#p115091](https://forum.xentax.com/viewtopic.php?f=10&t=13598&p=115091&hilit=wavc#p115091)

so have extract fsb form wavc 

any idea for read fsb 

thank's
## Post #38
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2019-08-07T11:10:43+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

@infogram

Could you please re-upload the latest Rage 2 hook dll?
At the time i discovered that thread, even the first version was not online anymore.
Thank you!
## Post #39
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2019-08-07T20:33:42+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

*snip*

issue solved.
## Post #40
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2019-08-12T12:09:20+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

@infogram

would you consider, uploading a "xinput9_1_0.dll" which is compatible with the latest version please?
so we could collect the last filenames?

thank you!
## Post #41
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2019-09-03T13:08:55+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Hi
Found something that might be useful.
Start the game with this bat file and game will read all files from dropzone folder beside game exe.
You can monitor game and get all filenames that game reads in this way and mod the game   .
[StartGame.rar](https://xentaxbackup.github.io/file/16688_StartGame.rar)
## Post #42
- Username: Transletter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 06, 2019 9:33 pm
- Post datetime: 2019-10-06T13:38:26+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Hello friends. I want to translate this game but I need tool. Please give me tool for Rage 2. I looked but mixed. I'm waiting clean download link. Have a good day
## Post #43
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-10-20T21:19:51+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Hi Infogram, can you please upload your Rage2Unpack 0.3a somewhere else? I can't even download it from your current hosting site (it might be temporal though).
Also are filelists just 66% complete ATM? I'd be really thankful for this info too.
Later!
## Post #44
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2019-10-29T10:05:17+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

O.K guys i push the filelist upto 91%.

```
https://drive.google.com/open?id=19TrOgtILFuedN4nwUVrw8Nd3Yc6M14ZF
```

In attachment below is also infogram's unpacker for person above me. You must just copy "oo2core_7_win64.dll" from main game dir to the unpacker exe's.
[RAGE2_Unpack_by_infogram.7z](https://xentaxbackup.github.io/file/16963_RAGE2_Unpack_by_infogram.7z)
## Post #45
- Username: matthew425
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 03, 2015 6:15 am
- Post datetime: 2020-06-09T00:51:03+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

This discussion is probably dead, but i'll just do it anyway, really wish someone would tell me how to edit .wtunec files for Rage 2. Hope I don't have to do any hex editing since I have NO idea how to read information like that.
## Post #46
- Username: Mastertarnslator
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2020 2:22 am
- Post datetime: 2020-07-22T16:08:17+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

> Reply from Zotya0330 ↑Sun Jun 09, 2019 5:28 am at Sun Jun 09, 2019 5:28 am
>
> 
I using Autoit Rage 2 export\import texttool, not JC.

CAN YOU REUPLOAD TOOL FOR ME FRIEND? I WANT TO TRANSLATE THIS GAME SO BADLY. PLEASE HELP ME.
## Post #47
- Username: ZachFett
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 17, 2020 5:18 pm
- Post datetime: 2020-08-09T14:53:06+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

> Reply from GRiNDERKILLER ↑Tue Oct 29, 2019 6:05 pm at Tue Oct 29, 2019 6:05 pm
>
> 
O.K guys i push the filelist upto 91%.
Code: Select allhttps://drive.google.com/open?id=19TrOgtILFuedN4nwUVrw8Nd3Yc6M14ZF
In attachment below is also infogram's unpacker for person above me. You must just copy "oo2core_7_win64.dll" from main game dir to the unpacker exe's.

Is 91% still the most-finished file list out there? All the other filelist download links I've seen are dead.
## Post #48
- Username: sinnerclown
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Aug 22, 2020 5:49 am
- Post datetime: 2022-02-05T22:09:38+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Rage 2 import problem.Is there anyone who can help?
## Post #49
- Username: greydays
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 02, 2019 2:51 pm
- Post datetime: 2022-03-11T23:20:25+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Has anyone found a way to make the audio of voice clips etc playable?

Using the script, I can extract them all as .wavc files, but I've had no luck playing or converting these files. I know some people have figured out a way to play them, but clearly it requires an additional step. Any help would be appreciated!
## Post #50
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2022-06-12T21:06:35+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Anyone who still have the Rage2Hook and could share?
## Post #51
- Username: ZachFett
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 17, 2020 5:18 pm
- Post datetime: 2023-02-15T22:56:24+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

Here's the unpacker for anyone still looking for it, it includes the 91% filelist which, as far as I could ever find, was the most complete one.
[https://mega.nz/file/ZuhX1ALa#ujevXNdpS ... DPD5GPhPhw](https://mega.nz/file/ZuhX1ALa#ujevXNdpSLOYQe_8TMWLIOWB3fyPPAdvoDPD5GPhPhw)
This is from my own game install folder, I can't recall if it includes the Rage2Hook dlls or not. If it's not included there, does anyone remember what the filenames were for it so I can check if I have them elsewhere in my install folder?
## Post #52
- Username: greydays
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 02, 2019 2:51 pm
- Post datetime: 2023-04-16T14:38:26+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

> Reply from ZachFett ↑Thu Feb 16, 2023 6:56 am at Thu Feb 16, 2023 6:56 am
>
> 
Here's the unpacker for anyone still looking for it, it includes the 91% filelist which, as far as I could ever find, was the most complete one.
https://mega.nz/file/ZuhX1ALa#ujevXNdpS ... DPD5GPhPhw
This is from my own game install folder, I can't recall if it includes the Rage2Hook dlls or not. If it's not included there, does anyone remember what the filenames were for it so I can check if I have them elsewhere in my install folder?

Thanks for the unpacker, ZachFett. Unfortunately, no matter what file I try to extract, it results in the same error message:
Unhandled Exception: System.FormatException: One of the identified items was in an invalid format.
   at Gibbed.JustCase4.FileFormats.ArchiveTableFile.Deserialize(Stream input)
   at Gibbed.JustCause4.Unpack.Program.Main(String[] args)

I'd love to be able to get this to work... Any suggestions or fixes?
## Post #53
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2023-04-16T14:57:45+00:00
- Post Title: Re: Rage 2 .arc .tab Archives

> Reply from greydays ↑Sun Apr 16, 2023 10:38 pm at Sun Apr 16, 2023 10:38 pm
>
> 
ZachFett wrote: ↑Thu Feb 16, 2023 6:56 am
Here's the unpacker for anyone still looking for it, it includes the 91% filelist which, as far as I could ever find, was the most complete one.
https://mega.nz/file/ZuhX1ALa#ujevXNdpS ... DPD5GPhPhw
This is from my own game install folder, I can't recall if it includes the Rage2Hook dlls or not. If it's not included there, does anyone remember what the filenames were for it so I can check if I have them elsewhere in my install folder?


Thanks for the unpacker, ZachFett. Unfortunately, no matter what file I try to extract, it results in the same error message:
Unhandled Exception: System.FormatException: One of the identified items was in an invalid format.
   at Gibbed.JustCase4.FileFormats.ArchiveTableFile.Deserialize(Stream input)
   at Gibbed.JustCause4.Unpack.Program.Main(String[] args)

I'd love to be able to get this to work... Any suggestions or fixes?

You must unpack initial game9.tab (not dlc) or initial game10.tab (dlc). - sarc.0.gtoc

R2SmallArchive.config edit (example)
<?xml version="1.0"?>
<R2SmallArchive>
	<sarc0_gtoc_file_path>H:\RAGE.2\RAGE 2\archives_win64\initial\game10_unpack\sarc.0.gtoc</sarc0_gtoc_file_path>
	<expentities_gtoc_file_path>H:\RAGE.2\RAGE 2\archives_win64\initial\game10_unpack\resourcesets\expentities.gtoc</expentities_gtoc_file_path>
	<Generate_Log>true</Generate_Log>
</R2SmallArchive>
Then, using the R2SmallArchive.exe, unpack the archives ee, fl.
