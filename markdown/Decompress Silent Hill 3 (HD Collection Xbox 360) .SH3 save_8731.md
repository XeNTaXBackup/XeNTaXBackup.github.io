## Post #1
- Username: thatguy!
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 09, 2012 7:08 pm
- Post datetime: 2012-04-09T12:12:36+00:00
- Post Title: Decompress Silent Hill 3 (HD Collection Xbox 360) .SH3 save

First of all, I hope this is the right section for my request. I know there is a seperate gamesave subforum, but my request is (hopefully) "just" about compression and not checksums etc.

I'm trying to decompress the save file of Silent Hill 3 on the Silent Hill HD Collection (.SH3). Silent Hill 2 on the same Collection is not compressed or encrypted at all.
I've tryed offzip with all possible window values, no avail. Then I tried comtype_scan2 and looked through the dumps for 2 hours, but I guess I'm to inexperienced to distinguish what result is plausible.

So please, could anybody take a quick look at those save files?
I'm attaching 2 saves. The first one has 31 handgun bullets (00 1F), the second one 28 (00 1C). Both have 10 shots loaded in the handgun, 4 beef jerkys, 5 health drinks and 1 ampoulle.

Maybe this could be the length of the compressed block (just a guess in the wild):


There's also some uncompressed text that is shown at the loading/saving screen at the end of the file:


I've also included a Silent Hill 2 save file in the attachment (.SH2)
The inventory begins at offset 563 (hex): 11 health drinks (00 0B), 5 Medikits (00 05), 00 00, 10 Shots in Pistol (00 0A), 180 handgun bullets (00 B4).

A big thanks for anyone who tries to help me out 
[upload.zip](https://xentaxbackup.github.io/file/5284_upload.zip)
## Post #2
- Username: thatguy!
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 09, 2012 7:08 pm
- Post datetime: 2012-04-10T06:48:22+00:00
- Post Title: Decompress Silent Hill 3 (HD Collection Xbox 360) .SH3 save

Just let me know if you need any more samples or other files (the .xex for example).
## Post #3
- Username: thatguy!
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 09, 2012 7:08 pm
- Post datetime: 2012-04-12T09:13:14+00:00
- Post Title: Decompress Silent Hill 3 (HD Collection Xbox 360) .SH3 save

Only 1 download so far? (+ 1 by me to test it).
Come one guys, please 

I'm thankful for any piece of advice.
## Post #4
- Username: thatguy!
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 09, 2012 7:08 pm
- Post datetime: 2012-04-19T14:06:28+00:00
- Post Title: Decompress Silent Hill 3 (HD Collection Xbox 360) .SH3 save

My 010 Editor binary template so far, it's not much 

```
//--- 010 Editor v3.2.2 Binary Template
//
// File: SH3 Savegame
// Author:
// Revision:
// Purpose:
//--------------------------------------
struct FILE {
    struct HEADER {
	    byte padding[4];
        int unknown1; // = 52
        int unknown2; // = 64 (maybe key? blocksize?)
        int size; // = 5408 (constant across saves)
        byte unknown3; // = 1A..constant?
        byte unknown4[3]; // checksum?
        byte padding2[4];
        int unknown5; // = 2000, constant?
        int unknown6; // = 1044 
        int unknown7; // = 63078, constant?
        byte unknown8[4]; // 01 00 00 0E, constant?
        int unknown9; // = 4
        int unknown10; // = 1, constant?
        int unknown11; // = 2, constant?
        byte padding3[12];
        byte unknown12[21]; // maybe a key?
    } header <bgcolor=cLtGray>;

    struct DATA {
        byte encryptedData[5387];
    } data;

} file;
```
## Post #5
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2012-12-14T18:32:48+00:00
- Post Title: Decompress Silent Hill 3 (HD Collection Xbox 360) .SH3 save

This place is pretty much dead. Can barely get help from anyone. Good luck
