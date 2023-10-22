## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-18T14:25:20+00:00
- Post Title: Destiny (.pkg) XBOX360

I took a quick 5min look 

```
// File: .pkg (BIG Endian)
// Author: Cra0(Cra0kalo)
// Revision: 1
// Purpose: Research
//--------------------------------------

typedef struct
{ 
  uint32    magic;  //Always 00 18 00 03
  uint16    nElementCount; 
  uint16    version; 
  uint32    unknownA;
  uint32    unknownB;
  uint32    blankA;
  uint32    flagA;
  uint32    constValA; //doesnt change?
  uint32    constValB; //count maybe const
  byte      stampText[132];
} PK_Header; 



//File Attribute Table (FAT) ???
typedef struct
{ 
  uint32    unknownA;
  uint32    unknownB;
  uint32    unknownC;
  uint32    dataPointer; //points to data
  uint32    unkParA;
  uint32    unkParB;
  byte      chunk[20];
} PK_FATEntryA; 

typedef struct
{ 
  uint32    unknownA;
  uint32    dataPointer; //points to data
  byte      chunk[20];
} PK_FATEntryB; 


BigEndian();
PK_Header header;
PK_FATEntryA entry1;
PK_FATEntryB entry2;
PK_FATEntryB entry3;

```


Not encrypted prob compressed with lzx 

Samples
[https://www.dropbox.com/sh/59pdrm5qn06l ... vlL4a?dl=0](https://www.dropbox.com/sh/59pdrm5qn06luw4/AADpGIcx3KC7o5n3Y2HTvlL4a?dl=0)

PM me for xex

010 editor script >


 Destiny_PKG.zip
(533 Bytes) Downloaded 83 times
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-09-19T13:29:41+00:00
- Post Title: Destiny (.pkg) XBOX360

Here is a list of external tools that Bungie used in the game 

[Havok](http://www.havok.com/)
[CRIWARE](http://www.cri-mw.com/)
[Speedtree](http://www.speedtree.com/)
[FaceFX](http://www.facefx.com/)
[Umbra3 Visibility Solution](http://www.umbrasoftware.com/en/umbra-3/)
[ZLIB Library](http://www.zlib.net/)
[Freetype project](http://www.freetype.org/)
[Granny Animation](http://www.radgametools.com/granny.html)
[Dolby Digital](http://www.dolby.com/us/en/technologies/dolby-digital.html)
[Audiokinetic Wwise](https://www.audiokinetic.com/)
[Oodle](http://www.radgametools.com/oodle.htm)
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-20T03:39:18+00:00
- Post Title: Destiny (.pkg) XBOX360

> Reply from brendan19
>
> Here is a list of external tools that Bungie used in the game 

Havok
CRIWARE
Speedtree
FaceFX
Umbra3 Visibility Solution
ZLIB Library
Freetype project
Granny Animation
Dolby Digital
Audiokinetic Wwise
Oodle

yep here is the string dump of the executable
[https://www.dropbox.com/s/h4ii6qpbfgsta ... p.zip?dl=0](https://www.dropbox.com/s/h4ii6qpbfgstala/Str_dump.zip?dl=0)
## Post #4
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2014-09-24T08:26:19+00:00
- Post Title: Destiny (.pkg) XBOX360

The files seem to be compressed using LZHLW from the Oodle Compression Library (by RAD Game Tools [[http://www.radgametools.com/oodle.htm](http://www.radgametools.com/oodle.htm)]).

The file entries are:

```
uint32_t FileOffset;
uint32_t CompressedFileSize;
uint32_t Flags; // 3rd byte tells the game whether the data is compressed
byte Sha1FileHash; // hash of the compressed or raw file data
};

```


The game also hashes the file tables and stores those hashes in the header as SHA-1's and the header is signed with SHA-256->RSA, and the signature is stored at 0x800.

If anyone has access to the Oodle SDK, I'm sure they can decompress them as there is no encryption on the data, just signed.

I'm not good with graphic formats or models, but this is an example of what a decompressed file looks like.
## Post #5
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-24T17:10:04+00:00
- Post Title: Destiny (.pkg) XBOX360

> Reply from Patriot
>
> The files seem to be compressed using LZHLW from the Oodle Compression Library (by RAD Game Tools [http://www.radgametools.com/oodle.htm]).

The file entries are:
Code: Select allstruct DestinyFileEntry {
uint32_t FileOffset;
uint32_t CompressedFileSize;
uint32_t Flags; // 3rd byte tells the game whether the data is compressed
byte Sha1FileHash; // hash of the compressed or raw file data
};


The game also hashes the file tables and stores those hashes in the header as SHA-1's and the header is signed with SHA-256->RSA, and the signature is stored at 0x800.

If anyone has access to the Oodle SDK, I'm sure they can decompress them as there is no encryption on the data, just signed.

I'm not good with graphic formats or models, but this is an example of what a decompressed file looks like.

great work ill look into it some more soon is there by any chance you can get some sample uncompressed files?
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-09-26T19:44:51+00:00
- Post Title: Destiny (.pkg) XBOX360

> Reply from cra0
>
> Patriot wrote:The files seem to be compressed using LZHLW from the Oodle Compression Library (by RAD Game Tools [http://www.radgametools.com/oodle.htm]).

The file entries are:
Code: Select allstruct DestinyFileEntry {
uint32_t FileOffset;
uint32_t CompressedFileSize;
uint32_t Flags; // 3rd byte tells the game whether the data is compressed
byte Sha1FileHash; // hash of the compressed or raw file data
};


The game also hashes the file tables and stores those hashes in the header as SHA-1's and the header is signed with SHA-256->RSA, and the signature is stored at 0x800.

If anyone has access to the Oodle SDK, I'm sure they can decompress them as there is no encryption on the data, just signed.

I'm not good with graphic formats or models, but this is an example of what a decompressed file looks like.


great work ill look into it some more soon is there by any chance you can get some sample uncompressed files?4

Oodle has five primary compression formats btw, LZA probably isnt the one choosen (since it was made reasonable speed-wise for games in july, so it's unlikely it was implemented into destiny) LZNib [http://cbloomrants.blogspot.com/2012/09 ... lznib.html](http://cbloomrants.blogspot.com/2012/09/09-13-12-lznib.html) is a possibility, other hints as to the structures are on this blog. he seems to be a dev for rad game tools. Also looks like alot of other next-gen games are picking up Oodle for use, The Order: 1886 is supposedly using it also (uncomfirmed, found through forum posts on gamedev.net by a programmer who works for ready at dawn studios)
## Post #7
- Username: TheLynx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 27, 2014 4:52 pm
- Post datetime: 2014-09-27T08:57:35+00:00
- Post Title: Destiny (.pkg) XBOX360

I'm willing to dedicate a lot of time to this project as I'm fairly invested in learning how to unpack game files. Is there anyways as a scrub that I can contribute, or should I just go learn elsewhere?
## Post #8
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-27T11:01:23+00:00
- Post Title: Destiny (.pkg) XBOX360

I tried legitimately to contact someone from [radgametools](http://www.radgametools.com) on getting my hands on the oodle package to evaluate however lets just say their licensing price is up there in the thousands.

Anyway


Crude as hell but here
[http://cra0kalo.com/public/DestinyPKGTool.zip](http://cra0kalo.com/public/DestinyPKGTool.zip)
## Post #9
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2014-09-27T15:04:07+00:00
- Post Title: Destiny (.pkg) XBOX360

> Reply from Pepper
>
> 4

Oodle has five primary compression formats btw, LZA probably isnt the one choosen (since it was made reasonable speed-wise for games in july, so it's unlikely it was implemented into destiny) LZNib http://cbloomrants.blogspot.com/2012/09 ... lznib.html is a possibility, other hints as to the structures are on this blog. he seems to be a dev for rad game tools. Also looks like alot of other next-gen games are picking up Oodle for use, The Order: 1886 is supposedly using it also (uncomfirmed, found through forum posts on gamedev.net by a programmer who works for ready at dawn studios)

I'm 99% (1% not sure since I don't have their SDK) certain it's LZHLW since that's what I found from looking at the function that decompresses the files in the game.

Also, I can make decompressed file dumps later this upcoming week. I have exams and after that I can create something to dump all files that run through the decompressor.
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-09-27T20:59:57+00:00
- Post Title: Destiny (.pkg) XBOX360

> Reply from Patriot
>
> Pepper wrote:4

Oodle has five primary compression formats btw, LZA probably isnt the one choosen (since it was made reasonable speed-wise for games in july, so it's unlikely it was implemented into destiny) LZNib http://cbloomrants.blogspot.com/2012/09 ... lznib.html is a possibility, other hints as to the structures are on this blog. he seems to be a dev for rad game tools. Also looks like alot of other next-gen games are picking up Oodle for use, The Order: 1886 is supposedly using it also (uncomfirmed, found through forum posts on gamedev.net by a programmer who works for ready at dawn studios)

I'm 99% (1% not sure since I don't have their SDK) certain it's LZHLW since that's what I found from looking at the function that decompresses the files in the game.

Also, I can make decompressed file dumps later this upcoming week. I have exams and after that I can create something to dump all files that run through the decompressor.

No problem, I didn't have any reason to suspect LZNib, I just wanted to give any information I could find online.
## Post #11
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2014-10-03T20:21:11+00:00
- Post Title: Destiny (.pkg) XBOX360

Here's the first file from "360_client_bootstrap_unpatchable_0.pkg". Will dump more in the weekend, trying to setup a tool to just feed the game any compressed file but I have to figure out the Oodle decompression function's parameters first.

I decided to upload this one since it's the first file that is decompressed.

This file contains the four compressed fragments in the above file and one "full" file, which is just the four fragments stitched together. The rest of the file is not compressed so you can just extract the binary data.

[http://www.mediafire.com/download/5nzicjr2s5zwwkl](http://www.mediafire.com/download/5nzicjr2s5zwwkl)


Update on research:

The resource entry table (offset of table is at 0xB8 in the pkg files) contains positions, sizes and indexes of the resources the game access. Each compressed file decompresses to 0x40000 bytes and all of the fragments decompressed make up a file.

The positions in each resource entry is relative to the start of the decompressed chunk. So for example, if accessing entry 0x1B0, the position value could be something like 0x00000040 instead of (0x1B0 * 0x40000) + 0x00000040.

Also, sound files don't seem to be compressed, you can extract them and they are in the XMA format, so to play them as .wav on pc, they need to be converted.


Update on files:

I can decompress any of the files now, if you want to do research on the files contact me through Private Message and we can work on them.
## Post #12
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-10-09T05:49:02+00:00
- Post Title: Destiny (.pkg) XBOX360

> Reply from Patriot
>
> Here's the first file from "360_client_bootstrap_unpatchable_0.pkg". Will dump more in the weekend, trying to setup a tool to just feed the game any compressed file but I have to figure out the Oodle decompression function's parameters first.

I decided to upload this one since it's the first file that is decompressed.

This file contains the four compressed fragments in the above file and one "full" file, which is just the four fragments stitched together. The rest of the file is not compressed so you can just extract the binary data.

http://www.mediafire.com/download/5nzicjr2s5zwwkl


Update on research:

The resource entry table (offset of table is at 0xB8 in the pkg files) contains positions, sizes and indexes of the resources the game access. Each compressed file decompresses to 0x40000 bytes and all of the fragments decompressed make up a file.

The positions in each resource entry is relative to the start of the decompressed chunk. So for example, if accessing entry 0x1B0, the position value could be something like 0x00000040 instead of (0x1B0 * 0x40000) + 0x00000040.

Also, sound files don't seem to be compressed, you can extract them and they are in the XMA format, so to play them as .wav on pc, they need to be converted.


Update on files:

I can decompress any of the files now, if you want to do research on the files contact me through Private Message and we can work on them.Hello, my friends, thank you very much for your great work, I want to like you, wanted to develop better tools to share with you, sharing happy, thank you
## Post #13
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-09T06:14:22+00:00
- Post Title: Destiny (.pkg) XBOX360

> Reply from Patriot
>
> Here's the first file from "360_client_bootstrap_unpatchable_0.pkg". Will dump more in the weekend, trying to setup a tool to just feed the game any compressed file but I have to figure out the Oodle decompression function's parameters first.

I decided to upload this one since it's the first file that is decompressed.

This file contains the four compressed fragments in the above file and one "full" file, which is just the four fragments stitched together. The rest of the file is not compressed so you can just extract the binary data.

http://www.mediafire.com/download/5nzicjr2s5zwwkl


Update on research:

The resource entry table (offset of table is at 0xB8 in the pkg files) contains positions, sizes and indexes of the resources the game access. Each compressed file decompresses to 0x40000 bytes and all of the fragments decompressed make up a file.

The positions in each resource entry is relative to the start of the decompressed chunk. So for example, if accessing entry 0x1B0, the position value could be something like 0x00000040 instead of (0x1B0 * 0x40000) + 0x00000040.

Also, sound files don't seem to be compressed, you can extract them and they are in the XMA format, so to play them as .wav on pc, they need to be converted.


Update on files:

I can decompress any of the files now, if you want to do research on the files contact me through Private Message and we can work on them.

Could you update this?
[https://github.com/cra0kalo/DestinyPKGT ... ool/PKG.cs](https://github.com/cra0kalo/DestinyPKGTool/blob/master/DestinyPKGTool/PKG.cs)
## Post #14
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2014-10-09T06:19:33+00:00
- Post Title: Destiny (.pkg) XBOX360

> Reply from cra0
>
> 

Could you update this?
https://github.com/cra0kalo/DestinyPKGT ... ool/PKG.cs

Yea, I'll try to fill in as much as I know.

Also, I was able to extract a texture:

[http://gyazo.com/f46ca672f9aeb9b40637c00d79231fb5](http://gyazo.com/f46ca672f9aeb9b40637c00d79231fb5)

 Still working on dealing with graphics formats, injection/editing is some time away.
## Post #15
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-10-09T12:35:17+00:00
- Post Title: Destiny (.pkg) XBOX360

Is there a way get the TOC from the PKG files so we can get some filenames going or are we going to be stuck with hashes?
## Post #16
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-10-09T17:37:37+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

Looking good.

XMA's when extracted can be converted with towav. 

Of course you'd need to add a proper header.
## Post #17
- Username: m4rx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 28, 2012 1:04 am
- Post datetime: 2014-10-10T20:56:57+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

> Reply from OrangeC
>
> Looking good.

XMA's when extracted can be converted with towav. 

Of course you'd need to add a proper header.

I only get .dat files when I extract, where are you finding the XMAs?
## Post #18
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-10-10T21:25:24+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

the RIFX headers should point to the XMA wavs. just use alphatwentythrees xma script to convert to a proper xma file, then convert with towav.

As for the .dat files they are just the data chunks without the filenames yet.
## Post #19
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2014-10-10T23:17:47+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

Are there any methods for ascertaining which filetypes each .dat file is? I'm asking in particular reference to model files over audio/texture. If I knew more I could begin to hammer on with the work myself.
## Post #20
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2014-10-10T23:31:12+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

> Reply from RosaWeyland
>
> Are there any methods for ascertaining which filetypes each .dat file is? I'm asking in particular reference to model files over audio/texture. If I knew more I could begin to hammer on with the work myself.

The .dat files you get using cra0's tool won't give you any models or texture data. That is stored inside the compressed files, which are what the .dat files are, compressed chunks of data. The audio files aren't compressed, which is why you can extract them (1 audio file can be spread over several .dat files if the audio is larger than 0x40000 bytes, which most seem to be). The resource entry table might have information about file types but the information the entries store needs to be figured out first (working on that right now).
## Post #21
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2014-10-11T23:40:36+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

Alrighty, understood. I'll have a poke myself.
## Post #22
- Username: no9
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 07, 2015 12:13 pm
- Post datetime: 2017-04-19T17:31:58+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

Didn't want to make another thread for Destiny as there was already 2 of them available, but Oodle has been RE'd.

[https://github.com/powzix/kraken](https://github.com/powzix/kraken)
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-04-19T17:58:19+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

Quick bms supports oodle
## Post #24
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-04-19T20:52:48+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

> Reply from no9
>
> Didn't want to make another thread for Destiny as there was already 2 of them available, but Oodle has been RE'd.

https://github.com/powzix/kraken

I'm not seeing Oodle in there.

Also, unfortunate Destiny still hasn't been extracted.
## Post #25
- Username: no9
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 07, 2015 12:13 pm
- Post datetime: 2017-04-20T00:05:28+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

> Reply from Gh0stBlade
>
> no9 wrote:Didn't want to make another thread for Destiny as there was already 2 of them available, but Oodle has been RE'd.

https://github.com/powzix/kraken

I'm not seeing Oodle in there.

Also, unfortunate Destiny still hasn't been extracted.

I mean last gen has been extracted, and the .pkg files have been extracted by cra0 as well.
## Post #26
- Username: Gins
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 09, 2004 6:05 am
- Post datetime: 2017-07-16T06:57:37+00:00
- Post Title: Re: Destiny (.pkg) XBOX360

is there any chance we can change the destiny pkg tool compatible with the destiny 2 beta?
