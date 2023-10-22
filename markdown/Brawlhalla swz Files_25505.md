## Post #1
- Username: yayababa55
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2022 4:31 am
- Post datetime: 2022-06-07T20:41:41+00:00
- Post Title: Brawlhalla swz Files

So there's this "Flash" game on Steam called Brawlhalla with quite a lively playerbase, complete with a million-dollar eSports scene. The meat of what affects gameplay is stored in these so called "swz" files. From what I know, they're some type of encrypted XML file. My main goal in accessing these is changing the balance state of the game. Stuff like damage, knockback, recovery time and start-up. 

If this works out, I could perhaps host tournaments on my own server and/or a LAN tournament with prize pools, but custom gameplay mechanics. This could attract quite a large audience. But you will also be able to change core modules of the engine itself, not just balance values, enabling you to create neat mods.

 There is a small number of people with access to these files, so it is definitely possible, but they are unwilling to disclose their means of unlocking and decrypting the swz files.

If anyone could help me out, I would be very thankful
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-10T22:10:28+00:00
- Post Title: Brawlhalla swz Files

Can you upload a few SWZ files?
## Post #3
- Username: yayababa55
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2022 4:31 am
- Post datetime: 2022-06-13T15:49:05+00:00
- Post Title: Brawlhalla swz Files

Sure. 

Here's one of them, Dynamic.swz.There is also Engine.swz, Game.swz and Init.swz. Couldn't upload them all because of the file size limit. Note this is for game version 6.07.
[SWZs.zip](https://xentaxbackup.github.io/file/22361_SWZs.zip)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-06-13T18:57:56+00:00
- Post Title: Brawlhalla swz Files

Completely encrypted.
## Post #5
- Username: yayababa55
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2022 4:31 am
- Post datetime: 2022-06-14T15:30:56+00:00
- Post Title: Brawlhalla swz Files

What about this one? Any easier?
[18swz.zip](https://xentaxbackup.github.io/file/22368_18swz.zip)
## Post #6
- Username: RawlhallFan1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 19, 2022 3:01 am
- Post datetime: 2022-07-18T19:08:19+00:00
- Post Title: Brawlhalla swz Files

Looks like there is a decryption routine in one of the ANE extension DLLs. I am sure if you can disassemble the correct subroutines you will crack the files very easily. It might be hard getting behind it though, since you need to jump between the action script source and the DLL itself. 

Sincerely 
One of the dudes who got behind it and omit any info xoxo
## Post #7
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-07-24T11:50:26+00:00
- Post Title: Brawlhalla swz Files

These files store a number of string objects which are all zlib compressed and encrypted. The format uses an XOR Cipher combined with the [WELL512](https://en.wikipedia.org/wiki/Well_equidistributed_long-period_linear) pseudo-random number generator algorithm providing a random key for each operation. Each file uses the below structure and reads StringEntries until compressedSize exceeds the end of the file. 

All of the encryption is handled by RawData.dll which is an Adobe Native Extension that is invoked by BrawlhallaAir.swf. This extension contains 3 methods:

- bool RawData_Init(uint seed) : which defines a global encryption key. At of time of writing patch 6.08 uses 119026080
- bool RawData_SetData(byte[] fileContents) : which initialises and mixes the WELL512 algorithm. The seed is (header.Seed ^ globalEncryptionKey)
- string RawData_GetData() : which decrypts and decompresses a string object

```
{
  uint32_BE Checksum;
  uint32_BE Seed;      // XOR with EncryptionKey
  StringEntry Entries[x];
}

struct StringEntry
{
  uint32_BE EncodedCompressedSize   // XOR'd
  uint32_BE EncodedDecompressedSize // XOR'd
  uint32_BE Checksum;

  //  zlib compressed then XOR'd
  byte EncodedZlibCompressedData[decodedCompressedSize];
}

```


Do note, as WELL512 is an LFSR, all calls to NextUInt must be honored - even if it seems unnecessary such as with checksum validation - otherwise the state will be invalid and decryption will fail.

A C# example can be found [here](https://gist.github.com/barncastle/a21b62df945445b38daf91ede021a3ec).
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-13T12:08:36+00:00
- Post Title: Brawlhalla swz Files

Here's the article for reference
[http://wiki.xentax.com/index.php/Brawlhalla_SWZ](http://wiki.xentax.com/index.php/Brawlhalla_SWZ)

Thanks for sharing, barncastle
## Post #9
- Username: yayababa55
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2022 4:31 am
- Post datetime: 2022-10-05T12:52:22+00:00
- Post Title: Brawlhalla swz Files

> Reply from barncastle ↑Sun Jul 24, 2022 7:50 pm at Sun Jul 24, 2022 7:50 pm
>
> 
These files store a number of string objects which are all zlib compressed and encrypted. The format uses an XOR Cipher combined with the WELL512 pseudo-random number generator algorithm providing a random key for each operation. Each file uses the below structure and reads StringEntries until compressedSize exceeds the end of the file. 

All of the encryption is handled by RawData.dll which is an Adobe Native Extension that is invoked by BrawlhallaAir.swf. This extension contains 3 methods:

- bool RawData_Init(uint seed) : which defines a global encryption key. At of time of writing patch 6.08 uses 119026080
- bool RawData_SetData(byte[] fileContents) : which initialises and mixes the WELL512 algorithm. The seed is (header.Seed ^ globalEncryptionKey)
- string RawData_GetData() : which decrypts and decompresses a string object
Code: Select allstruct Header
{
  uint32_BE Checksum;
  uint32_BE Seed;      // XOR with EncryptionKey
  StringEntry Entries[x];
}

struct StringEntry
{
  uint32_BE EncodedCompressedSize   // XOR'd
  uint32_BE EncodedDecompressedSize // XOR'd
  uint32_BE Checksum;

  //  zlib compressed then XOR'd
  byte EncodedZlibCompressedData[decodedCompressedSize];
}


Do note, as WELL512 is an LFSR, all calls to NextUInt must be honored - even if it seems unnecessary such as with checksum validation - otherwise the state will be invalid and decryption will fail.

A C# example can be found here.

Thank you so much! Good work
## Post #10
- Username: yayababa55
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2022 4:31 am
- Post datetime: 2022-10-08T13:58:53+00:00
- Post Title: Brawlhalla swz Files

Someone else asked for help on another forum and a kind user made a tool for encrypting the SWZs. As such, I'm now able to make changes to the game, but there is one last problem. The game checks for modified files and throws a "File loading error" if it detects anything (which it doesn't always, but it limits my ability to make any interesting changes). Definitely possible to bypass, but again, I'm no programmer so this is my final request. Thank you 

Forum thread with download link: [https://www.unknowncheats.me/forum/gene ... files.html](https://www.unknowncheats.me/forum/general-programming-and-reversing/517876-repacking-brawlhallas-swz-files.html)
