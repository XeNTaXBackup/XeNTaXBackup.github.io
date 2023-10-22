## Post #1
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-05-23T12:00:53+00:00
- Post Title: Watch_Dogs fat and dat archives

This game's file structure is similar to Far Cry series with fat and dat archives, but a bit different. Here is an example, can anyone take a look into this. Hope someone can make a unpacker/packer for it, like Rick's tools. Thanks in advanced.



```
https://www.firedrive.com/file/BA315D54DDCE56FC
```
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-23T12:16:37+00:00
- Post Title: Watch_Dogs fat and dat archives

```
{
	DWORD	dwID; // 3TAF
	DWORD	dwVersion; // Always = 8
	DWORD	dwUnknown;
	DWORD	dwTotalFiles;
};
```


```
{
	DWORD	dwHash;
	DWORD	dwSize;
	DWORD	dwZSize;
	DWORD	dwOffset;
};
```

PC > XMem
PS3 > Deflate
Xbox > XMem

PS: Edited info > thx Haoose
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-23T15:20:23+00:00
- Post Title: Watch_Dogs fat and dat archives

can you upload that common dat file?
## Post #4
- Username: HAIDER6222354
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Jul 04, 2012 12:19 pm
- Post datetime: 2014-05-23T15:29:08+00:00
- Post Title: Watch_Dogs fat and dat archives

> Reply from cra0
>
> can you upload that common dat file?
this common dat and fat for ps3 version

[https://www.firedrive.com/file/7769DA947BE2EA60](https://www.firedrive.com/file/7769DA947BE2EA60)
## Post #5
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-05-23T16:12:38+00:00
- Post Title: Watch_Dogs fat and dat archives

this is from pc version

```
https://www.firedrive.com/file/B7B191D4E38EA190
```
## Post #6
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-25T11:50:38+00:00
- Post Title: Watch_Dogs fat and dat archives

> Reply from namquang93
>
> this is from pc version
Code: Select allhttps://www.firedrive.com/file/B7B191D4E38EA190

yep I got the pc version will take a look soon
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-25T15:53:21+00:00
- Post Title: Watch_Dogs fat and dat archives

It's just a modifed Xmem i think... well for pc at least I can see the magic header, here is a 010 editor script anyway for the fat files using what ekey found

```
//--- 010 Editor v5.0 Binary Template
//
// File: common.fat
// Author: EKey/Cra0kalo
// Revision: 1
// Purpose: WatchDogs
// ByteFormat - Little Endian
//--------------------------------------


typedef  float vec3[3];
typedef  float quat4[4];
typedef  string asciiz;

struct
{
   DWORD   dwID; // 3TAF
   DWORD   dwVersion; // Always = 8
   DWORD   dwUnknown;
   DWORD   dwTotalFiles;
}FATHeader;

//DWORD UnknownA;

local int i;
for(i = 0; i < FATHeader.dwTotalFiles; i++ )
{
struct
{
   DWORD   dwHash;
   DWORD   dwSize;
   DWORD   dwZSize;
   DWORD   dwOffset;
}FATEntry;


}

```


As for Xmem we can see the usual 0x0F 0xF5 0x12 0xEE magic identifier in the dat



Another script of a standard header it's obviously different but yeah I'm about to head to sleep will take a look tomorrow

```
//--- XCOMPRESS
//--- Watch Dogs 2014
//--------------------------------------
long Identifier; // # XCOMPRESS_FILE_IDENTIFIER_LZXNATIVE
long ContextFlags;
long Flags;
long WindowSize;
long CompressionPartitionSize;
long UncompressedSizeHigh;
long UncompressedSizeLow;
long CompressedSizeHigh;
long CompressedSizeLow;
long UncompressedBlockSize;
long CompressedBlockSizeMax;

```

[xcompress.h](http://pastie.org/pastes/1261481#248)
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-25T16:38:09+00:00
- Post Title: Watch_Dogs fat and dat archives

PS3 compressed data header 

```
{
   SHORT   wChunksCount;
   SHORT   wUnknown; //xFF\x0F

  for(i = 0; i < DataHeader.wChunksCount; i++ )
  {
    Read(wChunksSizes, 2);
  }
};
```
## Post #9
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2014-05-26T18:14:30+00:00
- Post Title: Watch_Dogs fat and dat archives

Thanks to you guys I was able to extract the XCompress using quickbms , but there is a little modification to the file struct.

All big endian

```
//--- XCOMPRESS
//--- Watch Dogs 2014
//--------------------------------------
long Identifier; // # XCOMPRESS_FILE_IDENTIFIER_LZXNATIVE
long ContextFlags;
short Version;
short Reserved;
long Flags;
long WindowSize;
long CompressionPartitionSize;
long UncompressedSizeHigh;
long UncompressedSizeLow;
long CompressedSizeHigh;
long CompressedSizeLow;
long UncompressedBlockSize;
long CompressedBlockSizeMax;
long CompressedBlockSize;

```



I'll try to post the script , btw :I'm not good in writing scripts
## Post #10
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-05-26T19:18:48+00:00
- Post Title: Watch_Dogs fat and dat archives

How did you uncompress it? Does the game still work with uncompressed .dat files?
Might help with some performance issue many users have with the game.
## Post #11
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-26T19:45:41+00:00
- Post Title: Watch_Dogs fat and dat archives

> Reply from Gruselgurke
>
> Does the game still work with uncompressed .dat files?
No. Need modified EXE-file for it
## Post #12
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-27T06:15:31+00:00
- Post Title: Watch_Dogs fat and dat archives

> Reply from Haoose
>
> Gruselgurke wrote:Does the game still work with uncompressed .dat files?
No. Need modified EXE-file for itNot sure why that would be the case, the archive format supports uncompressed data just fine.
## Post #13
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-05-27T06:51:09+00:00
- Post Title: Watch_Dogs fat and dat archives

> Reply from Rick
>
> Haoose wrote:Gruselgurke wrote:Does the game still work with uncompressed .dat files?
No. Need modified EXE-file for itNot sure why that would be the case, the archive format supports uncompressed data just fine.

hello, will you work on this game ? I really love the way you did with Far Cry 3.
## Post #14
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-27T07:42:48+00:00
- Post Title: Watch_Dogs fat and dat archives

When I have the time.
## Post #15
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-05-27T11:57:16+00:00
- Post Title: Watch_Dogs fat and dat archives

Cool to see some progress! For me im wondering and am curious about the scripts, and if we are able to change them up depending on the code
## Post #16
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-27T17:03:22+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from killerpepo
>
> Thanks to you guys I was able to extract the XCompress using quickbms , but there is a little modification to the file struct.

All big endian
Code: Select all//--------------------------------------
//--- XCOMPRESS
//--- Watch Dogs 2014
//--------------------------------------
long Identifier; // # XCOMPRESS_FILE_IDENTIFIER_LZXNATIVE
long ContextFlags;
short Version;
short Reserved;
long Flags;
long WindowSize;
long CompressionPartitionSize;
long UncompressedSizeHigh;
long UncompressedSizeLow;
long CompressedSizeHigh;
long CompressedSizeLow;
long UncompressedBlockSize;
long CompressedBlockSizeMax;
long CompressedBlockSize;


I'll try to post the script , btw :I'm not good in writing scripts
Yep figured that out on the bus lol 


Ok heres the extractor




 wd_extractor.zip
(115.14 KiB) Downloaded 355 times


Please don't share this outside of this forum thankyou
## Post #17
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-27T18:16:40+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Hmm seems textures are normal dds with custom header anyway post your findings im off to sleep
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-27T18:53:19+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Well it's only for Xbox right?
## Post #19
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-05-27T19:12:05+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Thanks a lot for the tool cra0! Is it also possible to reverse the process?
Will have a look I find anything interesting the chunk files.

@EKey
It worked fine with PC .fat files. Though I don't know if this is actually usable data.
## Post #20
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-05-27T19:25:47+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> Haoose wrote:Gruselgurke wrote:Does the game still work with uncompressed .dat files?
No. Need modified EXE-file for itNot sure why that would be the case, the archive format supports uncompressed data just fine.

Nice, would be cool to see a plain decompressor without any file extraction then. Looks like cra0's tool is essentially doing that in a way?
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-27T19:33:52+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Gruselgurke
>
> @EKey
It worked fine with PC .fat files. Though I don't know if this is actually usable data.
Oh pc version using xmem compression too also xbox.
## Post #22
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2014-05-27T19:42:33+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

it's possible to get tut's for sound please thank's :)
## Post #23
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-05-27T20:02:35+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

output file size computation is wrong. all are 0x8000 while this is the window size for decompressor. some files are interrupt, some are appended with zeroes. I suppose each unpacked file might be made out of several compressed blocks, please refine the tool respective.
## Post #24
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-27T22:31:03+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> Haoose wrote:Gruselgurke wrote:Does the game still work with uncompressed .dat files?
No. Need modified EXE-file for itNot sure why that would be the case, the archive format supports uncompressed data just fine.
Sorry, I thought about the unpacked archives

cra0. Thx for unpacker
It's work on XBOX and PC (not PS3)
But it is not complete files. =(
## Post #25
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-05-28T02:12:35+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

hopefully someone can crack this son of a b and mod the b jeesus out of it to justify purchasing.
## Post #26
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-05-28T03:22:02+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Currently dont works with sound.fat (PC, Xbox360).
## Post #27
- Username: filu23
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Feb 03, 2014 8:30 pm
- Post datetime: 2014-05-28T04:11:02+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

sound.dat not work
## Post #28
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-28T04:19:39+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

[http://svn.gib.me/public/disrupt/trunk](http://svn.gib.me/public/disrupt/trunk)
[http://svn.gib.me/builds/disrupt](http://svn.gib.me/builds/disrupt)
## Post #29
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-28T04:50:35+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> http://svn.gib.me/public/disrupt/trunk
http://svn.gib.me/builds/disrupt
Nice work!
## Post #30
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-05-28T05:00:56+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

rick delivers with the quickness. 

i don't have the game yet, so to those with the game, to what extent can we expect to modify the game?

i assume uplay will have to be hacked off( i can live with that)
## Post #31
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-28T05:01:26+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from odrin
>
> rick delivers with the quickness. 

i don't have the game yet, so to those with the game, to what extent can we expect to modify the game?

i assume uplay will have to be hacked off( i can live with that)Formats largely same as Far Cry 3. Disrupt engine (Watch_Dogs) largely based on Dunia 2 (Far Cry 3).
## Post #32
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-28T05:12:42+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Additional note: game will load patch.fat/patch.dat if it is present and override content as expected, just like Far Cry 3, even though it's not used yet.
## Post #33
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-28T05:14:42+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> http://svn.gib.me/public/disrupt/trunk
http://svn.gib.me/builds/disrupt

Rick does it also work with X360 version pls ?
## Post #34
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-28T05:18:37+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from michalss
>
> Rick does it also work with X360 version pls ?I don't see any reason for it not to work but I haven't done any testing as I don't own the 360 version.
## Post #35
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-28T05:24:22+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> Additional note: game will load patch.fat/patch.dat if it is present and override content as expected, just like Far Cry 3, even though it's not used yet.
did you write a geom and xbt parser for farcry3watchdogs if not i can write a quick one for testing or contribute to the svn
## Post #36
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-28T05:30:44+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from cra0
>
> did you write a geom and xbt parser for farcry3watchdogs if not i can write a quick one for testing or contribute to the svnNo for both. GEOM format is actually new to Disrupt, Dunia 2 had a different format (or version). XBT is same but it's simple enough that I never wrote tools for it.
## Post #37
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-28T05:33:09+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> cra0 wrote:did you write a geom and xbt parser for farcry3watchdogs if not i can write a quick one for testing or contribute to the svnNo for both. GEOM format is actually new to Disrupt, Dunia 2 had a different format (or version). XBT is same but it's simple enough that I never wrote tools for it.
alright ill write something quick in c# you may add to the svn if you wish.
-EDIT-
ok here xbt2dds



Download


 xbt2dds.zip
(19.59 KiB) Downloaded 121 times


[https://github.com/cra0kalo/xbt2dds](https://github.com/cra0kalo/xbt2dds)
[http://cra0kalo.com/public/xbt2dds.zip](http://cra0kalo.com/public/xbt2dds.zip)
I'll do geom tomorrow or weekend prob when I have time
## Post #38
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2014-05-28T10:03:54+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Wow that's very very nice , Excellent work guys

I was about to finish a quickbms script , but never mind your tools are perfect 

@Rick
I've a problem while unpacking files says :

```
could not find an acceptable version of XnaNative installed to use
```


Command I'm using 

```
Gibbed.Disrupt.Unpack.exe shaders.fat 1
```


So what's the problem exactly ? Thanks again
## Post #39
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-05-28T10:13:27+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Install XNA framework:
[http://www.microsoft.com/en-us/download ... x?id=20914](http://www.microsoft.com/en-us/download/details.aspx?id=20914)

Has anyone found textures of Aiden?
## Post #40
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2014-05-28T10:18:37+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from erik945
>
> Install XNA framework:
http://www.microsoft.com/en-us/download ... x?id=20914

Has anyone found textures of Aiden?

Thank you it works fine now
## Post #41
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-05-28T10:28:53+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

game seems crashed with the rebuilt windy_city.dat/fat
## Post #42
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-28T11:53:55+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from namquang93
>
> game seems crashed with the rebuilt windy_city.dat/fatSo don't rebuild the absurdly large archives? Why would you do that?

Edit: I did just fix a bug with packing though, that probably caused your issue. Really though, you shouldn't be repacking that archive.
## Post #43
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-28T12:34:07+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Rick
Thx for Tools
10006/310337 (3%)
## Post #44
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-05-28T12:45:13+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Rick did you planed update filelist? A lot of files in  __UNKNOWN\unknown  directory.
## Post #45
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-28T12:50:42+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from erik945
>
> Rick did you planed update filelist? A lot of files in  __UNKNOWN\unknown  directory.Yes? It's not as if I can pull all of the filenames out of my own ass.
## Post #46
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-05-28T14:36:02+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> namquang93 wrote:game seems crashed with the rebuilt windy_city.dat/fat  So don't rebuild the absurdly large archives? Why would you do that?

Edit: I did just fix a bug with packing though, that probably caused your issue. Really though, you shouldn't be repacking that archive.

I just want to decompress it   the game loads other uncompressed archives fine but not for this one. I tried the new disrupt-r14 but it still crashes on Continue Game    it's strange that no matter does game load the rebuilt file or not, the unpacker still be able to extract that file so I think that issue is caused by the game
## Post #47
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-05-28T14:38:15+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Rick, I get

```

   at XCompression.XnaNative.Load(BaseContext context)
   at XCompression.BaseContext..ctor()
   at XCompression.DecompressionContext..ctor(UInt32 windowSize, UInt32 chunkSize)
   at Gibbed.Disrupt.FileFormats.Big.EntryDecompression.DecompressXMemCompress(Entry entry, Stream input, Stream output)

   at Gibbed.Disrupt.FileFormats.Big.EntryDecompression.Decompress(Entry entry, Stream input, Stream output)
   at Gibbed.Disrupt.Unpack.Program.Main(String[] args)

```

how can I fix this? I've tried to copy fat+dat into "bin" folder and extract right there, but get the same exception.
## Post #48
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-28T14:40:28+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Oleg
>
> Rick, I get
how can I fix this? I've tried to copy fat+dat into "bin" folder and extract right there, but get the same exception.

> Reply from erik945
>
> Install XNA framework:
http://www.microsoft.com/en-us/download ... x?id=20914
## Post #49
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-28T14:41:48+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

@Oleg see below. Are you gonna try to make a ZM filter?

> Reply from erik945
>
> Install XNA framework:
http://www.microsoft.com/en-us/download ... x?id=20914
## Post #50
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-28T14:47:09+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Here my updated list's > 28140/310006 (9%)
[wd_filelist_r15.7z](https://xentaxbackup.github.io/file/7390_wd_filelist_r15.7z)
## Post #51
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-05-28T14:49:02+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Thanks. Sorry, the extra pages of comments was posted while I was trying to run Rick's tools and kept the forum page opened for reply. 

Works fine now.

@Chipicao, yes.
## Post #52
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-05-28T15:05:03+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Ekey how you created it?
## Post #53
- Username: kalleoskar
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-28T15:12:51+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Here my updated list's > 28410/310337 (9%)


 files-28410-310337-(9%).7z
(142.15 KiB) Downloaded 72 times
## Post #54
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-05-28T15:37:04+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I think the main point is to get the game works with modified archives
## Post #55
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-28T15:38:39+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Haoose
>
> Here my updated list's > 28410/310337 (9%)
files-28410-310337-(9%).7zName you added to shadersobj is invalid, otherwise. Good work!

28445/310351 (9%)
## Post #56
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-28T15:48:41+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

lol yeah good job
## Post #57
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-28T15:49:49+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> Update file lists (with contributions from Haoose). 28445/310351 (9%)
And from Ekey!
## Post #58
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-28T19:02:53+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

49568/310351 (15%)
[wd_filelist_r15_v2.7z](https://xentaxbackup.github.io/file/7393_wd_filelist_r15_v2.7z)
## Post #59
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-05-28T20:02:40+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

How do you do it?

I modify Watch Dogs.xml:

```
	<action type="path">D:\Watch_Dogs</action>
</install_location>
```


run RebuildFileLists.exe and generated files (28133/310337 (9%))
What next? How I can upgrade this result?
## Post #60
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-05-28T20:49:25+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> erik945 wrote:Rick did you planed update filelist? A lot of files in  __UNKNOWN\unknown  directory.Yes? It's not as if I can pull all of the filenames out of my own ass.
Lmfao!
## Post #61
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-28T20:53:12+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from erik945
>
> How do you do it?

I modify Watch Dogs.xml:
Code: Select all<install_location>
	<action type="path">D:\Watch_Dogs</action>
</install_location>

run RebuildFileLists.exe and generated files (28133/310337 (9%))
What next? How I can upgrade this result?
Create file projects\Watch Dogs\files\newfilenames.filelist with new filenames(!) and run RebuildFileLists.exe
## Post #62
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-28T20:59:30+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Gh0stBlade
>
> Rick wrote:erik945 wrote:Rick did you planed update filelist? A lot of files in  __UNKNOWN\unknown  directory.Yes? It's not as if I can pull all of the filenames out of my own ass.
Lmfao!
Best Reply 2014
## Post #63
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-05-28T21:15:29+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Haoose
>
> erik945 wrote:How do you do it?
Create file projects\Watch Dogs\files\newfilenames.filelist with new filenames(!) and run RebuildFileLists.exe

Ok, thank you! 
what is new filenames? Names of files found RebuildFileLists.exe at the previous iteration, names of files found in hex-editor, or else?
Is there a manual?
## Post #64
- Username: Gruselgurke
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-28T21:17:25+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Update filelist from Ekey
Credits: Ekey

50058/310337 (16%)


 files-50058-310337 (16%).7z
(224.36 KiB) Downloaded 83 times


erik945
names of files found in hex-editor, or a manual, or ... in game-files =)
## Post #65
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-05-28T21:24:01+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from cra0
>
> 
Best Reply 2014

Yes I agree   

---------------

Anywho, looks like the meshes are stored in .XBG (Xbox Geometry) format looks fairly straight forward from a quick glance...
## Post #66
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-05-29T00:01:38+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

edit: nvm should have looked into the source first
## Post #67
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-05-29T03:58:09+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

after the filelist is built, is it then possible to do straight model replacements?
## Post #68
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-29T06:34:39+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

74342/310351 (23%) - Download - See below.
## Post #69
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-29T06:59:10+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Gh0stBlade
>
> Anywho, looks like the meshes are stored in .XBG (Xbox Geometry) format looks fairly straight forward from a quick glance...
Where did you see this?
I already have an import script for xbg (Far Cry 3), but in Watch_Dogs I couldn't find any .xbg files, only .geom which are different.
## Post #70
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-29T07:24:24+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Chipicao
>
> Gh0stBlade wrote:Anywho, looks like the meshes are stored in .XBG (Xbox Geometry) format looks fairly straight forward from a quick glance...
Where did you see this?
I already have an import script for xbg (Far Cry 3), but in Watch_Dogs I couldn't find any .xbg files, only .geom which are different.
for example - graphics\buildings\_interior\auctionhouse\ah_building_ext.xbg
## Post #71
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-29T07:47:21+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Ekey
>
> for example - graphics\buildings\_interior\auctionhouse\ah_building_ext.xbg
Thanks, but it's still completely different compared to FC3 xbg.
Rick's tool saves unknown filenames in .geom and known in .xbg, correct? That would explain why I didn't see it before.

Yesterday I started working on a maxscript for the new GEOM format and I'm making good progress.
## Post #72
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-29T07:51:52+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Yup .geom it's .xbg
## Post #73
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-05-29T07:55:25+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Anybody  can  write a step by step manual to generation newfilenames.filelist?
## Post #74
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-29T08:42:34+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Chipicao
>
> Ekey wrote:for example - graphics\buildings\_interior\auctionhouse\ah_building_ext.xbg
Thanks, but it's still completely different compared to FC3 xbg.
Rick's tool saves unknown filenames in .geom and known in .xbg, correct? That would explain why I didn't see it before.

Yesterday I started working on a maxscript for the new GEOM format and I'm making good progress.
yep it seems pretty straight forward
## Post #75
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-29T11:33:19+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

86165/310351 (27%) - Download - See below
## Post #76
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2014-05-29T11:37:06+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Thank you very much for all your hard work guys 

May I ask if there is a way to unpack and repack .loc files yet?
## Post #77
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-29T14:50:27+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

```
  <Resource Class="CTextureResource" SourceExt=".png;.dds" TargetExt=".xbt" /> 
  <Resource Class="CAnimationResource" SourceExt=".mac" TargetExt=".mab" CompileDependency=".markup" /> 
  <Resource Class="CSkeletonResource" SourceExt=".skel.xml" TargetExt=".skeleton" /> 
  <Resource Class="CPhysResource" SourceExt=".hkr" TargetExt=".hkx" /> 
  <Resource Class="CRealtreeResource" SourceExt=".rta" TargetExt=".rtx" /> 
  <Resource Class="CFrankensteinPoseResource" SourceExt=".frank" TargetExt=".apm" /> 
  <Resource Class="CStateMachineResource" SourceExt=".gosm.xml" TargetExt=".gosm.xml" /> 
  <Resource Class="CMaterialResource" SourceExt=".material.xml" TargetExt=".material.bin" /> 
  <Resource Class="CSectorResource" SourceExt=".gsdat" TargetExt=".sdat" /> 
  <Resource Class="CSectorResourceLowRes" SourceExt=".gsdlr" TargetExt=".sdlr" /> 
  <Resource Class="CSectorResourceHiRes" SourceExt=".gsdhr" TargetExt=".sdhr" /> 
  <Resource Class="CBinkResource" SourceExt=".bik" TargetExt=".bik" /> 
  <Resource Class="CAIWorkspaceResource" SourceExt=".ai.xml" TargetExt=".ai.rml" /> 
  <Resource Class="CTrafficPatternCollectionResource" SourceExt=".tpc" TargetExt=".tpc" /> 
  <Resource Class="CLoftShapeResource" SourceExt=".lft" TargetExt=".xlf" /> 
  <Resource Class="CSequenceResource" SourceExt=".seq" TargetExt=".cseq" CompileDependency=".naseq;.liseq;.auseq;.fxseq;.prseq" /> 
  <Resource Class="CWorldLoadingUnitResource" SourceExt=".data.fcb" TargetExt=".dat" /> 
  <Resource Class="CAnimationTrackCollectionResource" SourceExt=".animtrackcol.xml" TargetExt=".animtrackcol.rml" /> 
  <Resource Class="CRoadResource" SourceExt=".groad" TargetExt=".road" /> 
  <Resource Class="CSplineLoftLowResGfxResource" SourceExt=".glgfx" TargetExt=".lgfx" /> 
  <Resource Class="CSplineLoftHiResGfxResource" SourceExt=".ghgfx" TargetExt=".hgfx" /> 
  <Resource Class="CSplineLoftPhysicsResource" SourceExt=".gphys" TargetExt=".phys" /> 
  <Resource Class="CPoseAnimationResource" SourceExt=".dpas;.animset" TargetExt=".dpax" /> 
  <Resource Class="CPoseDefinitionResource" SourceExt=".dpds" TargetExt=".dpdx" /> 
  <Resource Class="CMoveResource" SourceExt=".move.xml" TargetExt=".move.bin" /> 
  <Resource Class="CBatchResource" SourceExt=".batch" TargetExt=".cbatch" /> 
```
## Post #78
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-05-29T16:24:12+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

-c, -pv, -pt command for Gibbed.Disrupt.Pack.exe seems not working yet.
## Post #79
- Username: Boulotaur2024
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 04, 2011 1:12 am
- Post datetime: 2014-05-29T16:28:11+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from namquang93
>
> I think the main point is to get the game works with modified archives
Did anyone have success with that ?
I just slightly modified a shader, repacked it with Rick's tool into a new 'shaders.dat' archive, the resulting archive is much bigger than the original... I havent tried to launch the game yet... but I have the feeling it won't work
## Post #80
- Username: SWORDS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 07, 2011 4:04 pm
- Post datetime: 2014-05-29T16:45:38+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Boulotaur2024
>
> namquang93 wrote:I think the main point is to get the game works with modified archives  
Did anyone have success with that ?
I just slightly modified a shader, repacked it with Rick's tool into a new 'shaders.dat' archive, the resulting archive is much bigger than the original... I havent tried to launch the game yet... but I have the feeling it won't work

With feeling modding is limited...

Launching the game without to recompress is still possible?
I've not already installed the Rick's tools and waiting for the completion of the filelist.

I know with waiting modding is limited too...

All in all I appreciate the wonderful work!
## Post #81
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2014-05-29T16:48:14+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Boulotaur2024
>
> namquang93 wrote:I think the main point is to get the game works with modified archives  
Did anyone have success with that ?
I just slightly modified a shader, repacked it with Rick's tool into a new 'shaders.dat' archive, the resulting archive is much bigger than the original... I havent tried to launch the game yet... but I have the feeling it won't work

It works without any problems, have been tinkering around with a bunch of xmls and could see the changes in game without recompression just by using the pack command.
## Post #82
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-05-29T16:55:58+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

yes, I have tested, all the files, except windy_city.dat/fat, could be read by the game.
## Post #83
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-05-29T17:02:29+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I tried some basic changes to game config from common.fat, works now  Really nice effort all you involved!
## Post #84
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-05-29T17:43:09+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Indeed, common.fat seems to be working fine to some degree but I doubt it's stable with so many unknow files still there. Or does pack.exe put these unkown files back to the right place in the archive?
## Post #85
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-05-29T17:47:28+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from eycaramba
>
> Boulotaur2024 wrote:namquang93 wrote:I think the main point is to get the game works with modified archives  
Did anyone have success with that ?
I just slightly modified a shader, repacked it with Rick's tool into a new 'shaders.dat' archive, the resulting archive is much bigger than the original... I havent tried to launch the game yet... but I have the feeling it won't work 

It works without any problems, have been tinkering around with a bunch of xmls and could see the changes in game without recompression just by using the pack command.

what changes have you made? would you say replacement of character models is possible at any point in the future?
## Post #86
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-05-29T18:15:22+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Im trying to find the handling lua file haha, so great work done so fast you guys
## Post #87
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-29T18:38:25+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

If you mean handling for vehicles, that won't be in lua scripts.
## Post #88
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-05-29T18:42:58+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> If you mean handling for vehicles, that won't be in lua scripts.
Good to know!
## Post #89
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-29T20:09:39+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

100546/310351 (32%) - [Download](http://www.sendspace.com/file/ewg7wp)
## Post #90
- Username: Boulotaur2024
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 04, 2011 1:12 am
- Post datetime: 2014-05-29T20:51:48+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from eycaramba
>
> It works without any problems, have been tinkering around with a bunch of xmls and could see the changes in game without recompression just by using the pack command.Well it most certainly depends on which file you modified, I guess. For me I tried to modify many many .fx shaders files originally in shaders.dat, even the xml ones... then repacked into a new shaders.dat... but the game is consistently ignoring my changes 

I guess it is because -as someone said- that the Pack tool doesn't put everything back in its right place ?
## Post #91
- Username: hilohi
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-29T22:46:45+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

100745/310351 (32%) - [Download](http://www.sendspace.com/file/5tihhb)
Credits: Ekey
## Post #92
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-05-29T22:50:52+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Anyway I can help with finding file names? Or do I answer the question myself by asking it?
## Post #93
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-05-30T06:00:12+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Boulotaur2024
>
> For me I tried to modify many many .fx shaders files originally in shaders.dat, even the xml ones... then repacked into a new shaders.dat... but the game is consistently ignoring my changes

I guess the game uses pre-compiled binary shaders code, so your changes have no effect.
## Post #94
- Username: Boulotaur2024
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 04, 2011 1:12 am
- Post datetime: 2014-05-30T06:55:38+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Oleg
>
> I guess the game uses pre-compiled binary shaders code, so your changes have no effect.I think you're right. Thats what the .cso, .gso, .pso files in \shadersobj_unpack\engine\shaders\obj are for... Some of them even include 'Microsoft (R) HLSL Shader Compiler 9.29.952.3111' in the header... So yeah the shaders are pre-compiled (thats the standard procedure nowadays anyways) but they did include the HLSL .fx source files as well... That's weird :/
## Post #95
- Username: Lennox775
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 15, 2012 11:37 am
- Post datetime: 2014-05-30T10:38:15+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Anybody researching binaryclass of "vehiclespawninfo" and "trafficconfig"?
It'll allow to change vehicles spawn settings
## Post #96
- Username: dontera
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 28, 2014 9:52 pm
- Post datetime: 2014-05-30T13:58:03+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Hey guys, new to the forum as of Watch Dogs, but I've been unpacking and poking around in game data since I was tiny.

About Watch_Dogs, I was wondering if anyone has tried modifying the ActionMapping xml, copying the Aim and Shoot actions from passenger to driver. I wonder what the results would be..
## Post #97
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-05-30T14:48:37+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from dontera
>
> Hey guys, new to the forum as of Watch Dogs, but I've been unpacking and poking around in game data since I was tiny.

About Watch_Dogs, I was wondering if anyone has tried modifying the ActionMapping xml, copying the Aim and Shoot actions from passenger to driver. I wonder what the results would be..

Why ask and not just try it yourself and let us know about the results?
## Post #98
- Username: dontera
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 28, 2014 9:52 pm
- Post datetime: 2014-05-30T17:07:46+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Gruselgurke
>
> dontera wrote:Hey guys, new to the forum as of Watch Dogs, but I've been unpacking and poking around in game data since I was tiny.

About Watch_Dogs, I was wondering if anyone has tried modifying the ActionMapping xml, copying the Aim and Shoot actions from passenger to driver. I wonder what the results would be..

Why ask and not just try it yourself and let us know about the results?

That's an entirely reasonable suggestion. I do/did intend to, but haven't found the time. Just wanted to share my idea and see if anyone else had thought of it.
## Post #99
- Username: filu23
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Feb 03, 2014 8:30 pm
- Post datetime: 2014-06-01T12:46:35+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Hi guys. How to open "sbao" files?
## Post #100
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-06-01T20:49:45+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

i suppose modding ability of this game is doa, like far cry 3.

moving on
## Post #101
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-06-01T21:39:03+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from odrin
>
> i suppose modding ability of this game is doa, like far cry 3.

moving on

How would you come to that conclusion? You can already modify a great deal. Even more once the filelist is completed by Ekey and Haoose.
## Post #102
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-06-02T04:17:52+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

It's been five days since release.
## Post #103
- Username: filu23
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Feb 03, 2014 8:30 pm
- Post datetime: 2014-06-02T07:16:56+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

SBAO (ogg) files converter.

```
http://www70.zippyshare.com/v/67065938/file.html
```


Edit two files: sbao converter to mp3.bat and sbao converter to wav.bat

Enjoy
## Post #104
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2014-06-02T08:19:02+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

not only would I hope to get the van with a sumbero out of the game but if it does turn out to be modable that I might actually pick up the pc edition off steam or wherever.  I have many cars I've made for other games that would be fun to take for a ride in this games map.
## Post #105
- Username: nurullah390
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 27, 2014 2:23 am
- Post datetime: 2014-06-02T11:39:16+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Hi. How to open .loc files? I need help.
## Post #106
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-02T14:34:50+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from octaviousrex
>
> not only would I hope to get the van with a sumbero out of the game but if it does turn out to be modable that I might actually pick up the pc edition off steam or wherever.  I have many cars I've made for other games that would be fun to take for a ride in this games map.
Myself, Chipicao and many others are working on it
## Post #107
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-06-02T15:15:26+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

GHreat to see the game getting support here =) I doubt we will se any "offical" mod tools so everthing you doing here is great work indeed
## Post #108
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-06-03T15:27:29+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from cra0
>
> Myself, Chipicao and many others are working on it
me too.
## Post #109
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-04T05:02:14+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Oleg
>
> cra0 wrote:Myself, Chipicao and many others are working on it
me too.
 lets make a list


btw
## Post #110
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-06-04T06:54:53+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

cool! Is this a vehicle replacement mod? I've got the game, but can't run it on my HD4830 card)))) Once I upgrade my video, I'll be able to see what I'm actually dealing with, as to the moment I keep guessing what is what
## Post #111
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-04T09:22:26+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Oleg
>
> cool! Is this a vehicle replacement mod? I've got the game, but can't run it on my HD4830 card)))) Once I upgrade my video, I'll be able to see what I'm actually dealing with, as to the moment I keep guessing what is what
I for one am only planning on an import script, no exportign. I've already researched about 90% of the file structure so it won't be long now.
## Post #112
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-04T09:36:15+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Oleg
>
> cool! Is this a vehicle replacement mod? I've got the game, but can't run it on my HD4830 card)))) Once I upgrade my video, I'll be able to see what I'm actually dealing with, as to the moment I keep guessing what is what
Making a modelviewer/exporter tool for XBG/XBT to FBX/SMD/OBJ/IQM/DAE etc
## Post #113
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-04T09:51:23+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

@Rick how does your tool work, does it just require valid path\filenames?

I reckon I could use my script to parse all geom files and get material filenames + .xbgmip files which usually have corresponding .xbg with the same name.
Is there any way to check if a filename is valid?
## Post #114
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-06-04T13:30:05+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I'm more wondering if we indeed need all filenames to have a game that won't crash or if unknown files just get put back where they came from and we simply don't know their filename and filetype without trial and error.
I'm not getting much out of the source code that I understand.
## Post #115
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-04T14:10:30+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

At this point it's unknown if the game will even run unpacked without a modified exe.
## Post #116
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-06-04T14:14:10+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Put modified files in clean patch.fat/dat, why is this hard?

> Reply from Chipicao
>
> @Rick how does your tool work, does it just require valid path\filenames?

I reckon I could use my script to parse all geom files and get material filenames + .xbgmip files which usually have corresponding .xbg with the same name.
Is there any way to check if a filename is valid?If its hash is present in a .fat, then it's valid. Look at RebuildFileLists.
## Post #117
- Username: Lennox775
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 15, 2012 11:37 am
- Post datetime: 2014-06-04T14:16:25+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Almost xml values remains in hash ID but I'm trying to modding them.
Here are a sample; police vehicles spawn as traffic 
You can see more police vehicles and steal safely.
## Post #118
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-06-04T14:17:52+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

@Chipicao
No I mean not unpacked but the repacked files.
The game runs with a repacked common.dat (and doesn't without a common.dat), though there were only about 30% of all files found in the common.dat when I tried this, so I'm wondering if the game just didn't need the unknown files in the first level of the game or if the pack.exe is putting the unknown files into the correct position in the archive for the engine to find them or if the engine doesn't even care about position and just need this hash filename that the unknown file names have to find the the file in the archive and the archives don't have a folder structure all.

Edit: @Rick
ah ok, so all that is needed is the valid hash for the file and the pack will have all valid files?
## Post #119
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-06-04T14:25:41+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Gruselgurke
>
> @Chipicao
No I mean not unpacked but the repacked files.
The game runs with a repacked common.dat (and doesn't without a common.dat), though there were only about 30% of all files found in the common.dat when I tried this, so I'm wondering if the game just didn't need the unknown files in the first level of the game or if the pack.exe is putting the unknown files into the correct position in the archive for the engine to find them or if the engine doesn't even care about position and just need this hash filename that the unknown file names have to find the the file in the archive and the archives don't have a folder structure all.

Edit: @Rick
ah ok, so all that is needed is the valid hash for the file and the pack will have all valid files?Pack tool can pack unknown files via the __UNKNOWN directory structure.

 Please stop repacking game archives!  You don't need to do that. Put modified files into a new patch.fat/dat archive.
## Post #120
- Username: Gnampf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 05, 2014 8:03 am
- Post datetime: 2014-06-05T12:46:37+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Did someone know, where I can find the game music, like the radio tracks und mission tracks (e.g. Blume Bunker on act 2) ? I gonne love that music and wanna hear it more than one time 

Thx for answer
## Post #121
- Username: Fox
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 05, 2014 12:19 am
- Post datetime: 2014-06-05T21:37:39+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Haoose
>
> 100745/310351 (32%) - Download
Credits: Ekey

Anyone manage to get it more complete than that yet?  

And gents, thank you so much.
## Post #122
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-06-05T21:45:56+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Fox
>
> Anyone manage to get it more complete than that yet?
[http://svn.gib.me/builds/disrupt/](http://svn.gib.me/builds/disrupt/)
disrupt-r43_b31.zip
187164/310351 (60%)
## Post #123
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-06-06T04:29:09+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Where file sound_russian.filelist?

[](http://www.radikal.ru)
## Post #124
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-06-06T10:24:48+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from makcar
>
> Where file sound_russian.filelist?I don't have access to Russian or Japanese copy of the game. It's OK though, the lists should contain the same file names as the Russian and Japanese copies.
## Post #125
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-06-06T11:02:30+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from makcar
>
> Where file sound_russian.filelist?
Просто запусти RebuildFileLists.exe и он появится

Rick
sound_russian.fat - [http://rghost.ru/56208136](http://rghost.ru/56208136)
windy_city_russian.fat - [http://rghost.ru/56208183](http://rghost.ru/56208183)
common.fat (russian version) - [http://rghost.ru/56208200](http://rghost.ru/56208200)
## Post #126
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-06T14:35:03+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

XBG WIP still a lot of work but here is something

Credits: Chipicao/Myself
## Post #127
- Username: hilohi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 05, 2012 5:32 am
- Post datetime: 2014-06-06T19:13:32+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Keep going thats amazing work so far!
## Post #128
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-06-06T20:48:26+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> Gruselgurke wrote:@Chipicao
No I mean not unpacked but the repacked files.
The game runs with a repacked common.dat (and doesn't without a common.dat), though there were only about 30% of all files found in the common.dat when I tried this, so I'm wondering if the game just didn't need the unknown files in the first level of the game or if the pack.exe is putting the unknown files into the correct position in the archive for the engine to find them or if the engine doesn't even care about position and just need this hash filename that the unknown file names have to find the the file in the archive and the archives don't have a folder structure all.

Edit: @Rick
ah ok, so all that is needed is the valid hash for the file and the pack will have all valid files?Pack tool can pack unknown files via the __UNKNOWN directory structure.

 Please stop repacking game archives!  You don't need to do that. Put modified files into a new patch.fat/dat archive.

I absolutely understand. I'm just interested in the performance difference as the game seems to stream a lot of resources from the disk.
## Post #129
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-07T05:06:33+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

The problem now is figuring out how the shader scales the UVs because it seems to scale differently per model.
## Post #130
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2014-06-07T05:51:41+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I guess Ubisoft likes to obfuscate their models to prevent people from ripping them.

At least the models don't end up looking like this:



Keep it up guys! This is excellent progress!
## Post #131
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-06-07T06:45:53+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

What? Don't mistake proprietary formats with obfuscation.
## Post #132
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2014-06-07T11:02:51+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> What? Don't mistake proprietary formats with obfuscation.

From my understanding, Watch_Dogs relies on shaders to finalize the "look and feel" of the model. This basically means you can achieve something similar to that of obfuscation by requiring the shader to perform the necessary operations to get the model looking correct. If I'm not mistaken, 3d rippers cannot properly extract these models due to the lack of shaders being applied.

In my case, the models are scaled very strangely, and are correctly scaled via their shaders. Is that not what's going on in cra0's image? I apologize for the misunderstanding if so.
## Post #133
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-06-07T12:09:18+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

the geometry itself is not obfuscated. the scaling does seem to be applied to entire model:


cra0 was talking about UV data scaling, as it's need to be applied for texture to appear correctly on certain mesh fragments.
## Post #134
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-06-07T13:38:32+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from CarLuver69
>
> Rick wrote:What? Don't mistake proprietary formats with obfuscation. 

From my understanding, Watch_Dogs relies on shaders to finalize the "look and feel" of the model. This basically means you can achieve something similar to that of obfuscation by requiring the shader to perform the necessary operations to get the model looking correct. If I'm not mistaken, 3d rippers cannot properly extract these models due to the lack of shaders being applied.

In my case, the models are scaled very strangely, and are correctly scaled via their shaders. Is that not what's going on in cra0's image? I apologize for the misunderstanding if so.Assets in games are commonly baked in a way that optimizes their use (such as loading and rendering) in a game, this includes custom vertex formats, rendering via shaders, etc. Calling this obfuscation just because it made it harder for you to export into a usable format is really very silly.
## Post #135
- Username: cenkzenk
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 01, 2009 8:15 pm
- Post datetime: 2014-06-10T19:35:34+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Thanks to everyone

How to open  "main english.loc" Aluigi Help plz "53 4C 01 00" does not open

get NAME basename
idstring SL
get TYPE byte
get DUMMY long
if DUMMY & 0xff
    endian little
else
    endian big
endif
get ZSIZE long
get SIZE long
get DUMMY long
get DUMMY long
savepos OFFSET
if TYPE == 0
    string NAME += ".unslz"
    log NAME OFFSET ZSIZE
elif TYPE == 4
    string NAME += ".xcompress"
    log NAME OFFSET ZSIZE
else
    print "Error: unsupported type, contact me"
    cleanexit
endif
[main_english.rar](https://xentaxbackup.github.io/file/7467_main_english.rar)
## Post #136
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-06-12T07:33:46+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

awesome work so far! 
I'm mainly interested in the 3d models, so in the xbg conversion tool, if I correctly understood the only big problem left to fix is the uv scaling, right?
## Post #137
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-12T11:44:05+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Not really, cra0 and I have determined that most models use a scale of 2 or 3. We'll have to do more tests when the tool is ready, but worst case scenario you'll have to input a scaling factor manually.
## Post #138
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-06-12T12:22:56+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Ok. Thanks for the explanation!
Let me know if I can do something useful !
## Post #139
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-06-13T00:32:25+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

[out]
## Post #140
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-13T03:31:24+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Wobble
>
> Which .DAT file are these models found?  I looked at common, shaders, and shadersobj, and found nothing.
You obviously are blind -_-
## Post #141
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-13T09:43:45+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Wobble
>
> Which .DAT file are these models found?  I looked at common, shaders, and shadersobj, and found nothing.
windy_city and windy_city_cache
## Post #142
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-06-13T17:14:06+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

[out]
## Post #143
- Username: hqqttjiang
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 19, 2012 10:27 am
- Post datetime: 2014-06-14T04:04:46+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

it seems not work with the videos.fat/videos.dat    who can help me ？
[无标题.png](https://xentaxbackup.github.io/file/7474_无标题.png)
## Post #144
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2014-06-14T19:53:33+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Gnampf
>
> Did someone know, where I can find the game music, like the radio tracks und mission tracks (e.g. Blume Bunker on act 2) ? I gonne love that music and wanna hear it more than one time 

Thx for answer
This is also something I was looking for but came short of finding.
I mean, I think the radio stations/music tracks are packed inside sound.dat like most/all of the generic sounds used by the game. But probably the problem is the conversion process from SBAO to OGG, which fails for a lot of those files. For example, 00114db4.sbao file is (Chicago - Wake Up Sunshine) one of the musics that are played in vehicles, but I came short of getting others.
Can anyone else chime in on this?

Anyway, great work everyone!  

P.S: As far as the missions soundtrack goes: [http://bit.ly/1pYbws6](http://bit.ly/1pYbws6)
## Post #145
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-06-15T20:04:29+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I've changed few bytes in unpacked graphics/vehicles_nexus/land/muscle/muscle_03/ files and packed them back into patch.fat and patch.dat. Put them both into data_win64 folder and run the game. but I see no changes on respective models. Looks like modified file is ignored. 

May be I've missed some point? I've packed with Gibbed.Disrupt.Pack.exe with no extra options, just as:

Pack patch.fat graphics
## Post #146
- Username: Snake Plissken
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 6:35 am
- Post datetime: 2014-06-15T22:27:24+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

ill pay alot of bitcoins if someone could make a working first person view on foot mod. havent been able to unpack commen.dat myself yet.
## Post #147
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-06-16T00:42:01+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Oleg
>
> I've changed few bytes in unpacked graphics/vehicles_nexus/land/muscle/muscle_03/ files and packed them back into patch.fat and patch.dat. Put them both into data_win64 folder and run the game. but I see no changes on respective models. Looks like modified file is ignored. 

May be I've missed some point? I've packed with Gibbed.Disrupt.Pack.exe with no extra options, just as:

Pack patch.fat graphicsYou need to pack the containing directory. The root directory given to Pack is not included as part of the data path used in the archives.
## Post #148
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-06-16T07:38:37+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Snake Plissken
>
> ill pay alot of bitcoins if someone could make a working first person view on foot mod. havent been able to unpack commen.dat myself yet.

lol bitcoins. why not just tell people you'll pay them in metro tokens.
## Post #149
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2014-06-16T08:11:16+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from odrin
>
> Snake Plissken wrote:ill pay alot of bitcoins if someone could make a working first person view on foot mod. havent been able to unpack commen.dat myself yet.

lol bitcoins. why not just tell people you'll pay them in metro tokens.
I reckon Bottle Caps are way more comfortable to trade and suffer less fluctuation overall.
## Post #150
- Username: Gnampf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 05, 2014 8:03 am
- Post datetime: 2014-06-16T12:48:47+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from ner0
>
> Gnampf wrote:Did someone know, where I can find the game music, like the radio tracks und mission tracks (e.g. Blume Bunker on act 2) ? I gonne love that music and wanna hear it more than one time 

Thx for answer
This is also something I was looking for but came short of finding.
I mean, I think the radio stations/music tracks are packed inside sound.dat like most/all of the generic sounds used by the game. But probably the problem is the conversion process from SBAO to OGG, which fails for a lot of those files. For example, 00114db4.sbao file is (Chicago - Wake Up Sunshine) one of the musics that are played in vehicles, but I came short of getting others.
Can anyone else chime in on this?

Anyway, great work everyone!  

P.S: As far as the missions soundtrack goes: http://bit.ly/1pYbws6

Yeah, i've got unpacked that archive an same problems with converting the sbao's. The soundtrack OST is the original Soundtrack CD, but there isn't that backgroundmusic of the bunker mission. Hope they can fix the sbao converter or something. In my oppinion, I think there some sbao files missing in that archive.
## Post #151
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-06-16T22:01:55+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

apparently this was found in the code:


[http://forums.guru3d.com/showpost.php?p ... count=1283](http://forums.guru3d.com/showpost.php?p=4843210&postcount=1283)

ah the joys of cross platform development
## Post #152
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2014-06-16T22:30:13+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from odrin
>
> apparently this was found in the code:


http://forums.guru3d.com/showpost.php?p ... count=1283

ah the joys of cross platform development
At first I found it funny but then I felt a bit insulted, not having a console and all...   
Anyway for the sake of continuity, and in case that post is no more, here is the piece of code with comment from deferredambient.inc.fx in shaders.dat:

```
	float3 upperColor = tex3Dlod(BigProbeVolumeTextureUpperColor3D,finalUVW4).xyz;
#endif
#else
	// This is PC only, who cares.
	float3 upperColor = DefaultProbeUpperColor;
#endif
```
## Post #153
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-06-20T10:19:22+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

@Rick, can we have a tool or a code for converting "FCbn" files? I guess this is a binary XML files. To the moment, the /graphics/vehicle/*.. */(vehicle-name)_ref.skeleton looks like a single FCbn file. I've checked your tools for FC3, but they seem to deal with .fcb files which looks to include multiple "FCbn" entries. I mean the _ref.skeleton starts straight from nbCF bytes. Can you have a look at these?

The code might be preferable, as some xbg files seem to contain very similar data inside (most of high-detailed ped models seems to store _ref.skeleton inside xbg).
## Post #154
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-06-22T05:45:20+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Any plans on importing custom models back ingame? Format seems simple enough from what I heard, so I'd be more than glad to shove in new cars and characters in WD.
## Post #155
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-22T08:04:38+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Nearly there 
[http://www.youtube.com/watch?v=NovaLL1j7sg](http://www.youtube.com/watch?v=NovaLL1j7sg)
## Post #156
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-06-22T08:48:10+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Simply amazing!
Can't wait for the release of the tool!
## Post #157
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-06-22T09:55:26+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Wow damn that's amazing ;_; Great work!
## Post #158
- Username: hilohi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 05, 2012 5:32 am
- Post datetime: 2014-06-22T21:00:16+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

cra0 Feel free to raid the cookie jar when your done. Keep going!!
## Post #159
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-06-25T13:40:52+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I'm thinking of either ripping Aiden's phone/profiler and shoving it to some other game, or importing a Galaxy S5 to WD for good measure.  Anyone else here planning on doing something similar?
## Post #160
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-07-04T04:37:48+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Sorry for the bump, but anything new in regards to the formats?
## Post #161
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-07-05T16:50:09+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Any new filename update for sound.dat?

EDIT: how does one get new filenames from?
## Post #162
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-07-11T08:18:22+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Haoose
>
> Fox wrote:Anyone manage to get it more complete than that yet?  
http://svn.gib.me/builds/disrupt/
disrupt-r43_b31.zip
187164/310351 (60%)

Sorry but I've to know if there are any more updates after the one I quoted!
I noticed that with the r43 some character's textures are still missing.
## Post #163
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-07-11T11:26:24+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from loriscangini
>
> Haoose wrote:Fox wrote:Anyone manage to get it more complete than that yet?  
http://svn.gib.me/builds/disrupt/
disrupt-r43_b31.zip
187164/310351 (60%)

Sorry but I've to know if there are any more updates after the one I quoted!
I noticed that with the r43 some character's textures are still missing.

What character textures do you mean?
If it's arms, eyes, eyelashes and on some characters also clothing then they are in the 'kit' folders. The game uses general textures for the random citizens and some of those textures are also used by main characters. The game adjusts the correct skin tones and eye colors of those in shaders i suppose =)
## Post #164
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-07-11T12:16:07+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

No, I mean that some maps are missing, for example the alpha map of Clara's hairs, there is one but I think that something is still missing.
## Post #165
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2014-07-13T19:18:56+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

HI all,

is there any plan to support dat/fat files from ps3. I've read on some pages that on ps3 format is deflated. (I'll try to use offzip on this files but I don't get any results)

I've upload common.dat/fat for ps3 here:

[http://www46.zippyshare.com/v/94165371/file.html](http://www46.zippyshare.com/v/94165371/file.html)

Someone could tell me that is other structure file format diferent from pc?

Thanks
## Post #166
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-07-14T11:06:41+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from loriscangini
>
> No, I mean that some maps are missing, for example the alpha map of Clara's hairs, there is one but I think that something is still missing.

No that one is actually the correct one^^ I think the models use two UV channels for hairs because Clara isn't the only one with hair issues. The game Deus Ex: Human Revolution had different UV sets for models on hair aswell and Watch Dogs seems to do it the same way. (If you look at the normal map of the hair you can see that it uses the same UV layout as the alpha texture.
## Post #167
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-07-15T03:31:16+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

How exactly are filenames found?
## Post #168
- Username: Gnampf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 05, 2014 8:03 am
- Post datetime: 2014-07-30T14:21:05+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Did someone found the Music of the bunker mission? Or is it now possible to unpack and convert the hole music files?
## Post #169
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-11T18:07:36+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Filenames base update to > 192362/310356 (61%) - [here](https://www.sendspace.com/file/w20h9j)
## Post #170
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-08-13T06:43:36+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Does anybody looked at .loc files?
## Post #171
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-13T10:06:27+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

They compressed or encrypted.
## Post #172
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-08-14T03:27:48+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Is it possible debug exe to find compression/encryption code like in Sleeping Dogs?
## Post #173
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-09-04T09:37:07+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from o0Crofty0o
>
> loriscangini wrote:No, I mean that some maps are missing, for example the alpha map of Clara's hairs, there is one but I think that something is still missing.

No that one is actually the correct one^^ I think the models use two UV channels for hairs because Clara isn't the only one with hair issues. The game Deus Ex: Human Revolution had different UV sets for models on hair aswell and Watch Dogs seems to do it the same way. (If you look at the normal map of the hair you can see that it uses the same UV layout as the alpha texture.

I think you are right, but I haven't figured out how to do to make them look ok, do you know how to do?

For example I tried with Jordi, the diffuse texture is ok and fits with the UV maps, the alpha one doesn't
## Post #174
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-09-19T19:15:43+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I've created several batchfiles for 2 reasons: do some reconverting to reduce the game size for backup purposes, and allow me to do these processes in batch form (to see some level of progress). The tools are there, but either use a GUI or are file-per-file based.
Obviously, all credits go to the appropriate contributors/authors of said tools/info.
p

ps1: some remarks/input
Currently, it does not seem possible to reimport ONLY those files one has changed (like one is - sometimes - able to do with Quickbms: "-r -w" parameters).
Technically, this should be possible as long as the new file is '=<' the original file (the original position and size seem to be known, which I conclude from other tools I've tried out)
Repacking larger dat-files causes Watch Dogs to crash (either directly through its original DAT/FAT file or via Patch.dat).
There is a Quickbms script that allows one to export a "flat" file-list with hex-named files. Unfortunately, this script does not allow to reimport...

It would be great though if one could simply play the game with extracted folder structures. This would probably also give a performance boost on some machines as well. But that does not seem to be possible right now (unless through the use of a modified EXE)... (apparently, I read somewhere that it is possible on the Xbox?!)

It seems that the sound files (.sbao) are also 'trailed' with an additional header of 55 bytes long. The author of [xbt2dds] could easily extend its functionality by either adding this option, or - more generically - allow a "start ~ end" byte position. (Trunc only allows an end-position).
One could use [Sox] to convert these files into many different formats, such as MP3 and WAV (or reconvert in OGG). For Ogg-conversion, make sure to use v14.4 and "sndfile" library for better results.

ps2: U had to remove most EXE-files to keep the rar_size small, but these can easily be found/downloaded. Most batchfiles will tell you if a file is missing...
[WD_Repack.7z](https://xentaxbackup.github.io/file/7840_WD_Repack.7z)
## Post #175
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-20T03:16:46+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Paul44
>
> The author of [xbt2dds] could easily extend its functionality by either adding this option, or - more generically - allow a "start ~ end" byte position. (Trunc only allows an end-position).
[https://github.com/cra0kalo/xbt2dds](https://github.com/cra0kalo/xbt2dds) 
Source is there
## Post #176
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-09-20T08:40:25+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I use packing into patch.fat/.dat files for testing, but Uplay uses to replace the patch with the downloaded one after each restart of PC. Does this tool resolve this problem for modding? I guess it changes files straight in *_world.fat/.dat files, correct?
## Post #177
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-09-20T10:56:06+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

@cra0
Believe me, if I could, I would already have done that.
Programming is not (no longer) my forte. The last time I did some serious programming was with Clipper and LotusScripting, back in "ye old days".
p
## Post #178
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-09-21T19:49:01+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I've spent my sunday afternoon figuring this one out, and got it pretty close after lots of experimenting. I've explained all this in a PDF doc. But since one is limited in upload file size, you'll get a link to that file.
([http://www.4shared.com/office/JzvidBwLb ... mport.html](http://www.4shared.com/office/JzvidBwLba/WD_FIle_Import.html))

I hope this work will "tantalize" somebody to get me going on the long run 
p
## Post #179
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-09-26T09:03:13+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I identified some additional 'filelist' names. And have added the batchfile I've used to create the appropriate DDS files (which can easily be extended for other 'header-included' file formats). (also Swiss File Knife not incl)
p

ps:@ Rick. Quickbms EXE makes a distinction for files <> 4 GB. maybe something to consider for packed files larger then 4GB (like windy_city). I've reduced videos.dat to 2 GB, and the game has not yet crashed sofar...
[Windy_City_new DDS filenames.rar](https://xentaxbackup.github.io/file/7854_Windy_City_new DDS filenames.rar)
## Post #180
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-09-26T14:40:32+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Can't edit/attach additional files, so...
(missed writing down the 1st file, hence ???)
p

ps:No idea how to add those to the filelist, since I could not find a clear explanation. Dito for a way to find those names.
[WD_DDS_Newnames2.rar](https://xentaxbackup.github.io/file/7856_WD_DDS_Newnames2.rar)
## Post #181
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-09-30T12:42:03+00:00
- Post Title: XBcompress

After some more reading and experimenting: the tools xbcompress and xbdecompress allows you to (de)compress the files in the dat-files. As a sidenote: not all files within a dat-file seemed to be compressed.
(I'm using Swiss File Knife here)

If you run following on windy_city: > sfk172 hexfind windy_city.dat -bin "/0FF512EE010300000000000000000000/"
(1st 16 bytes of any compressed file)
you'll get a lot of hits (131.210  vs  162.504 Files unpacked). I assume that the remaining files are uncompressed?!

windy_city.dat : hit at offset 0x31040FE
>5B43415C 7CA877C2 9C838B9D 71E26F40< [CA\|.w.....q.o@ 031040DE
>3DBE24F9 43E5A249 10003400 00000000< =.$.C..I..4..... 031040EE
>0FF512EE 01030000 00000000 00000000< ................ 031040FE
>00008000 00008000 00000000 00002744< ..............'D 0310410E
>00000000 00000B5C 00008000 00000B5C< .......\.......\ 0310411E
>00000B5C FF27440B 52022049 74954D00< ...\.'D.R. It.M. 0310412E
windy_city.dat : hit at offset 0x3104C8E
>F37F3C87 E5F7ADFB AFFA3678 F0D36AE5< ..<.......6x..j. 03104C6E
>B5AAE9EA F6F8F276 F7D81700 00000000< .......v........ 03104C7E
>0FF512EE 01030000 00000000 00000000< ................ 03104C8E
>00008000 00008000 00000000 00000440< ...............@ 03104C9E
>00000000 0000029E 00008000 0000029E< ................ 03104CAE
>0000029E FF044002 9400200A 44950C00< ......@... .D... 03104CBE

If you then extract one of those hits (e.g. between: 0x31040FE - 0x3104C8E) using this command:
> sfk172 partcopy windy_city.dat 0x31040FE 0x3104C8E WD_WindyCity_Extr0x31040FE.compr -yes

and then run xbdecompress, this way:
> xbdecompress WD_WindyCity_Extr0x31040FE.compr WD_WindyCity_Extr0x31040FE.decompr

you'll get a decompressed (unpacked) file. Open this file in a hexeditor to find out what type it is...

My problem now: how to "xbcompress" it back to its original compressed size? Anyone knows the correct param_setting for this?

I already found out that one needs to use /N: to get the correct header sequence, but no luck from thereon sofar...
p
## Post #182
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-02T09:18:13+00:00
- Post Title: XBcompress

I've found the way to recompress the files, using xbcompress. The difference between the original compressed file and recompressed file is 3 or 4 bytes. Have been testing this on 10 random files, and it always give me the exact same byte locations/differences. Which means that I probably need to use an additional parameter setting to get it 100% right.
The good news: the filesizes are exactly the same, and - once imported back - the game recognizes the file (does not crash). Even more, I changed the DDS (filetype I have been working with), recompressed it (giving me a smaller value), reimported it (using SFK) and it shows without any problems! 
And of course: reimporting is instant, and [Windy_City.dat] does not change in size...

If have tested this on Windy_City.dat, and the adv shown on papabs_pawnshop (close to the Owl Motel).
[papabs_pawnshop_decal_01_d.xbt]
p

as stated earlier, some of the files in Windy_City.dat are not compressed at all (even some of the DDS files, like the adv at the Owl Motel). If one recompresses such an example, and reimport it, the game will not crash, but you will not see the advertisement either...!
## Post #183
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-10-02T09:24:34+00:00
- Post Title: XBcompress

does the game detect changes in .dat file (may be checksum)? I mean, when you close and restart UPlay, does it redownload the latest patch or it behaves correctly and ready-to-go?
## Post #184
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-03T09:03:27+00:00
- Post Title: XBcompress

> Reply from Oleg
>
> does the game detect changes in .dat file (may be checksum)? I mean, when you close and restart UPlay, does it redownload the latest patch or it behaves correctly and ready-to-go?
I deduce from your question that you want to play with a modded version (which can only be merged within patch.dat). I guess that won't work since those mods probably (?) use their proper (non-basic) files. Iow you won't find them in any of the .dat files... Not to mention the fact that - if they do use existing files - they will surely be different/larger in size then the original files?!

If I assume wrong: I never play games online... not ever. But if you want to test it, then I'll upload the "Papa Bs" example for you to import into Windy_city.
p

ps1: if the mod does use original files, then probably the only way to get this working is, if the packed/uncompressed windy_city.dat vs would not crash... (assuming that this is not detected, as you suggested)

ps2: if your patch.dat gets overwritten during start up of the game, then try to a) start up while disconnected, and once in menu connect b) start connected with original patch.dat and once in menu, 'change' to modded version...
## Post #185
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-10-03T09:49:16+00:00
- Post Title: XBcompress

my inquiry is generally about offline mods. wish some user install several mods, how would he do this? Currently, he has to pack them all into a single patch .fat/.dat, backup this file, start UPlay, let the game download "correct" patch, replace it with modded patch and finally start the game. So, I'm wondering whether it would be possible to find a simple solution.

yet the GTA was modded that way, buy replacing files in original archives, but GTA uses 2 files per vehicle (model + textures pack). WD uses for one vehicle: model + high lod + reference skeleton + physics + dozen of materials + dozen of textures.
## Post #186
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-03T15:27:57+00:00
- Post Title: XBcompress

Some more names found. Did test with the Rebuilder, but apparently only .fcb filenames are added?!
p

@Oleg: like I said, either option ps1 (like you do now apparently) or option ps2 (depends on Rick).
I've checked some files in the TheWorse mod: they use also game-existing filenames, but several of them are bigger in size. So, no go.

ps: if anyone is interested, I made an overview of all file_extensions found sofar in windy_city (either in the unpacked folders, or from the Unknown files)
[newfilenames.rar](https://xentaxbackup.github.io/file/7877_newfilenames.rar)
## Post #187
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-10-03T18:25:45+00:00
- Post Title: XBcompress

How to get the rest of the filenames for sound.dat?
## Post #188
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-05T13:15:04+00:00
- Post Title: XBcompress

> Reply from OrangeC
>
> How to get the rest of the filenames for sound.dat?
are you saying now that you are happy with the current [sound.filelist]? In my filelist, those are just as meaningless then the Unknow ones... Anyway, you should ask Ekey about them; he's the one who provided the list, if I'm not mistaken.

I can provide a batchfile which extracts the compressed files from windy_city, based on the header "stamp" (see at beginning of this topic). You can decompress all those files (about 160.000 of them), and then run another batchfile which search for strings such as 'graphics', 'worlds', etc (ie the main folders). That's how I got those additional names. I did see more names appearing but I only concentrated on the "first_hit". And obviously, the batchfiles can easily be adapted for other dat/fat files.
But open some of the sbao-files, and you'll notice quickly that no path_info is found within them. So other files/programs must be refering to them, I guess...
p
## Post #189
- Username: lapius
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 23, 2014 4:23 am
- Post datetime: 2014-10-22T20:59:04+00:00
- Post Title: XBcompress

Hi, I am new here and I came to ask your help. While I was playing, I saw Aiden answering the phone in one mission, but I couldnt take picture. I want to mane similar UI to my android phone, so if someone can help me find...

Ok, So I got some textures to look.
[https://www.youtube.com/watch?v=fu51RBr ... e=youtu.be](https://www.youtube.com/watch?v=fu51RBrJeH0&feature=youtu.be)
## Post #190
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2014-11-16T06:43:19+00:00
- Post Title: XBcompress

Quick question. has anyone figured how to convert the yellow normal map into a blue regular normal map?
## Post #191
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-11-16T10:35:50+00:00
- Post Title: XBcompress

these are green-alpha normal displacement maps with green been displacement on X/U and alpha on Y/V. You can move alpha channel to red and save this normal map as GR16 (green 16 bit, red 16 bit). then load it in any directX-compatible editor as bump map and the "Z" (blue) will be automatically computed.

I don't know the whole chain on conversion, this is just the guideline. I mess directly with green-alpha textures as they are.
## Post #192
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-11-17T18:49:55+00:00
- Post Title: XBcompress

[out]
## Post #193
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-11-23T07:29:29+00:00
- Post Title: XBcompress

time to move on, guys. this is an unmoddable pile of shit
## Post #194
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-11-23T12:56:10+00:00
- Post Title: XBcompress

I would not agree, I think it's moddable, we just don't put much effort into it.
## Post #195
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2014-12-06T00:39:36+00:00
- Post Title: XBcompress

hello everyone, can any of you help me how to re-compress the common & patch dat / fat for PS3 version??

basically, i just want to swap controls because aim & fire with L2 & R2 is a bit unsettling for me. so i want to change it into L1 & R1 (in-game option doesn't let us swap the button).

thanks!
## Post #196
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2015-01-06T22:49:37+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I'll quote myself here, if anyone interested: [viewtopic.php?p=102661#p102661](http://forum.xentax.com/viewtopic.php?p=102661#p102661)
## Post #197
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-01-13T23:33:03+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Rick
>
> http://svn.gib.me/public/disrupt/trunk
http://svn.gib.me/builds/disruptIs there an updated version on this? I can't extract the sound.dat/fat from the Xbox 360 version. The extractor just crashes. I'm sorry, I haven't read the whole thread. Found it quicker to just ask.
## Post #198
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-02-03T05:56:54+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Я вот никак не могу понять?

Будет ли НОРМАЛЬНЫЙ способ по извлечению моделей из игры Watch Dogs?
## Post #199
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-02-03T08:31:24+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

А чем существующий не угодил? Геометрия есть, развертка есть, даже кости есть.
## Post #200
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2015-02-03T09:36:56+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

[www.zmodeler3.com](http://www.zmodeler3.com)
## Post #201
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-02-03T10:06:48+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

English pls, this is English forum, i wont tolerate any gibberish in here. I hope you understand.
## Post #202
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-02-03T10:07:50+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from AlphaTwentyThree
>
> Rick wrote:http://svn.gib.me/public/disrupt/trunk
http://svn.gib.me/builds/disruptIs there an updated version on this? I can't extract the sound.dat/fat from the Xbox 360 version. The extractor just crashes. I'm sorry, I haven't read the whole thread. Found it quicker to just ask.

Also would like to see extraction of X360 files
## Post #203
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-02-05T05:37:08+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from erik945
>
> А чем существующий не угодил? Геометрия есть, развертка есть, даже кости есть.

Проблемная точнее геморойная активация Zmodeler3 - если бы был бы импортер/экспортер для blender или 3ds max, то было бы в разы проще вытаскивать текстуры и модели из этой игры!

Я не лентяй, просто экстрактирование моделей из это игры не должно быть такой архи-сложной задачей! Я никак не могу понять, зачем чтобы экспортировать одну модель в формат .fbx, я должен мучатся и пыхтеть над активацией этой программы, у которой регистрация привязана к железу компьютера и слетает спустя 15 дней?

Вот какие модель я хотел бы вытащить из этой игры:

Джорди Чин
[http://ru.watchdogs.wikia.com/wiki/Джорди_Чин](http://ru.watchdogs.wikia.com/wiki/%D0%94%D0%B6%D0%BE%D1%80%D0%B4%D0%B8_%D0%A7%D0%B8%D0%BD)

Делфорд Уэйд
[http://ru.watchdogs.wikia.com/wiki/Делфорд_Уэйд](http://ru.watchdogs.wikia.com/wiki/%D0%94%D0%B5%D0%BB%D1%84%D0%BE%D1%80%D0%B4_%D0%A3%D1%8D%D0%B9%D0%B4)

Джексон Пирс
[http://ru.watchdogs.wikia.com/wiki/Джексон_Пирс](http://ru.watchdogs.wikia.com/wiki/%D0%94%D0%B6%D0%B5%D0%BA%D1%81%D0%BE%D0%BD_%D0%9F%D0%B8%D1%80%D1%81)

Лена Пирс
[http://ru.watchdogs.wikia.com/wiki/Лена_Пирс](http://ru.watchdogs.wikia.com/wiki/%D0%9B%D0%B5%D0%BD%D0%B0_%D0%9F%D0%B8%D1%80%D1%81)

Шарлотта Гарднер
[http://i.playground.ru/i/43/82/20/00/wi ... j14i57.png](http://i.playground.ru/i/43/82/20/00/wiki/content/qvj14i57.png)

Донован Рашмор
[http://i.playground.ru/i/71/33/20/00/wi ... m7n19f.png](http://i.playground.ru/i/71/33/20/00/wiki/content/zwm7n19f.png)

Роуз Вашингтон
[http://i.playground.ru/i/81/33/20/00/wi ... tif2sx.jpg](http://i.playground.ru/i/81/33/20/00/wiki/content/2ytif2sx.jpg)

Брэд Кезеловски
[http://ru.watchdogs.wikia.com/wiki/Брэд_Кезеловски](http://ru.watchdogs.wikia.com/wiki/%D0%91%D1%80%D1%8D%D0%B4_%D0%9A%D0%B5%D0%B7%D0%B5%D0%BB%D0%BE%D0%B2%D1%81%D0%BA%D0%B8)

Костюм: «Чикагский гангстер»
[http://ru.watchdogs.wikia.com/wiki/Файл:Costume_02.png](http://ru.watchdogs.wikia.com/wiki/%D0%A4%D0%B0%D0%B9%D0%BB:Costume_02.png)

Костюм: «Киберпанк»
[http://ru.watchdogs.wikia.com/wiki/Файл:Costume_03.png](http://ru.watchdogs.wikia.com/wiki/%D0%A4%D0%B0%D0%B9%D0%BB:Costume_03.png)

Вот всё что я хочу вытащить из этой игры, остальные "персонажи" меня не интересуют.
## Post #204
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-02-05T05:40:39+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from michalss
>
> English pls, this is English forum, i wont tolerate any gibberish in here. I hope you understand.

Sorry.

Но увы - Google-переводчик искажает то что я хочу написать, можете мне не верить.

Это ваше дело!
## Post #205
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2016-05-09T09:05:21+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Ekey
>
> Filenames base update to > 192362/310356 (61%) - here

Hi Ekey! Sorry about bringing up the thread. How exactly do you find all those filenames? Hope you were still there!
## Post #206
- Username: fahad00
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 19, 2016 3:36 am
- Post datetime: 2016-11-19T09:03:40+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from cra0
>
> killerpepo wrote:Thanks to you guys I was able to extract the XCompress using quickbms , but there is a little modification to the file struct.

All big endian
Code: Select all//--------------------------------------
//--- XCOMPRESS
//--- Watch Dogs 2014
//--------------------------------------
long Identifier; // # XCOMPRESS_FILE_IDENTIFIER_LZXNATIVE
long ContextFlags;
short Version;
short Reserved;
long Flags;
long WindowSize;
long CompressionPartitionSize;
long UncompressedSizeHigh;
long UncompressedSizeLow;
long CompressedSizeHigh;
long CompressedSizeLow;
long UncompressedBlockSize;
long CompressedBlockSizeMax;
long CompressedBlockSize;


I'll try to post the script , btw :I'm not good in writing scripts 
Yep figured that out on the bus lol 


Ok heres the extractor


wd_extractor.zip
Please don't share this outside of this forum thankyou
Does anyone please tell me how to extract and repack import files of watch dogs please help me
## Post #207
- Username: maxtheduke
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 01, 2016 2:44 am
- Post datetime: 2016-11-30T19:38:20+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

YOU GUYS ROCK! THANKS!!!!!
## Post #208
- Username: Maoky
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 02, 2017 8:17 am
- Post datetime: 2017-08-02T01:24:29+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Guys I can't understand how to extract sound effects from the game Watch Dogs 2, can you help me out? I tried everything, read all the conversations, used programs, watched tutorial, nothing works.

Here the link, just an example: [https://mega.nz/#!YihzxAbI!_kUc2V5TkNuB ... Hd6HenB-Co](https://mega.nz/#!YihzxAbI!_kUc2V5TkNuB256vW3RoDe9fmxNEak6wbHd6HenB-Co)

Is there someone who I can talk to by facebook or vk maybe? It's really really really important, I'm begging you.
## Post #209
- Username: CryptoCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 20, 2021 6:26 am
- Post datetime: 2021-05-29T04:08:57+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

Sorry for the bump. Has anyone figured out how to view .xbgmip file? Not sure if they exist in Watch Dogs, but they do in the second game, Watch Dogs 2
## Post #210
- Username: CryptoCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 20, 2021 6:26 am
- Post datetime: 2021-05-29T08:14:14+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

> Reply from Maoky ↑Wed Aug 02, 2017 9:24 am at Wed Aug 02, 2017 9:24 am
>
> 
Guys I can't understand how to extract sound effects from the game Watch Dogs 2, can you help me out? I tried everything, read all the conversations, used programs, watched tutorial, nothing works.

Here the link, just an example: https://mega.nz/#!YihzxAbI!_kUc2V5TkNuB ... Hd6HenB-Co

Is there someone who I can talk to by facebook or vk maybe? It's really really really important, I'm begging you.

Your mega.nz link is down. I think the sounds are in sound.dat/fat and in san_francisco_sound.dat/fat.
Are you able to extract any files from the dat/fat archive? You might have several files starting from 0xA, if that is the case then those are your audio files. You just have to check with hex editor what is the header and change file extension appropriately. I can help with that if needed
## Post #211
- Username: Mca23
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 12, 2021 1:48 am
- Post datetime: 2021-07-11T17:54:35+00:00
- Post Title: Re: Watch_Dogs fat and dat archives

I tried to extract Watch dogs 2 dat and fat files and couldn't extract any of the files, I used disrupt and it gave me errors like (bad magic) I wanted to change the music in the game can anyone help me?
