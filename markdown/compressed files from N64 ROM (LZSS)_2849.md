## Post #1
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-20T12:24:00+00:00
- Post Title: compressed files from N64 ROM (LZSS)

Hi,

I've been collecting missions for the game Command & Conquer, and after I found out that the N64 version of the game had a few original new missions in it, I've been trying to extract them. However, I've had some problems...

In the ROM, all bytes seemed to be switched in pairs. So for example, instead of "01 02 03 04 05 06" it said "02 01 04 03 06 05"
This didn't really pose a problem though. I just wrote a small program that converted the entire rom file.
In the converted file I found a neat index of files and their sizes, and I can extract all files from it (with some more work, but that's not the problem). However, here's my real problem... all of the separate files seem to be compressed.

It looks like a rather basic case of replacing a string that has been used before by some sort of reference to the first occurence. The beginning of the (text) file is still quite readable, but after that it becomes a mess.

I really don't know much about data compression though.

For my research I've taken one of the compressed files from the N64 ROM that is NOT new to the N64 version, so it can be compared to the original file, taken straight from my CD.

When compressing the original file with some small lzss compressor I had lying around, the result seemed similar to the compressed file from the ROM, but uncompressing the ROM's file with that same lzss proggie didn't give anything readable. Not that I really expected it to, but hey, it was worth a try.

Note: the compressed file has some trailing zeroes that I'm pretty sure are just left over from the archiving, and will probably need to be cut off.

I can probably upload more examples after I've written the file extractor.


[edit]

After some more research, the data in the file archive's index table might be necessary...

This is the data in the index for that file:

"SCB01EA.INI" 63 6B 1C 00 00 12 13 22 00 07 BE

The last 2 bytes, 07BE, are the compressed file size (bytes are not switched) The 6th and 7th byte, "1213" is the uncompressed file size. I've checked this with several other of my original files.
This uncompressed file size might just be there to cut off these trailing zeroes.

The rest, I have no idea. I attached the index file; the actual file archive (without the index header) is 9964728 bytes long.
[SCB01EA.zip](https://xentaxbackup.github.io/file/1395_SCB01EA.zip)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T12:40:41+00:00
- Post Title: compressed files from N64 ROM (LZSS)

Could indeed be LZSS. There is no generic LZSS decompressor cause there are many variations. Will have a deeper look at it when I come back.
## Post #3
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-20T12:52:21+00:00
- Post Title: compressed files from N64 ROM (LZSS)

Thank you 

[edit]

Yes, seems like my lzss proggie uses blocks of 8 bytes, with 1 byte in between, while this uses blocks of 16 bytes, with 2 in between. My proggie also seems to have FF as default empty value for the bytes in between, where the ROM file has 00 00

Still haven't fully figured out LZSS itself, but from what I've read about it so far, it does seem to be what I'm dealing with here.

Also, I think my original compressed file was extracted incorrectly... it should have 2 zero-bytes before it as first lzss indicator, and 2 less behind it. I re-uploaded it.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T15:46:43+00:00
- Post Title: compressed files from N64 ROM (LZSS)

> Reply from Nyerguds
>
> Yes, seems like my lzss proggie uses blocks of 8 bytes, with 1 byte in between, while this uses blocks of 16 bytes, with 2 in between.
Yeah, two flag bytes.

> My proggie also seems to have FF as default empty value for the bytes in between, where the ROM file has 00 00
Yes, the semantics are inverted here.

> Also, I think my original compressed file was extracted incorrectly... it should have 2 zero-bytes before it as first lzss indicator, and 2 less behind it. I re-uploaded it.
Already changed that.

You "just" have to find out how they encode the offset and length.
## Post #5
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-20T15:49:25+00:00
- Post Title: compressed files from N64 ROM (LZSS)

> Reply from Rheini
>
> You "just" have to find out how they encode the offset and length.
And that's exactly the part I can't figure out 


[edit]
what I got so far: 

To get the indexes, reverse the bits on each byte and paste the 2 bytes together.
Each reference is 2 bytes long, but is seen as a single location in the index. The byte after the 2-byte reference will simply be seen as the next location in the index.


example: offset 36 in the file

```
= 00000010 00000000

  01234567 89ABCDEF
= 01000000 00000000

```

References are:
-location 1

2-byte data at location 1: C3 9E (1100 0011 1001 1110)

[edit]

Wrong part removed, my bad X_x
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T20:53:55+00:00
- Post Title: compressed files from N64 ROM (LZSS)

I don't understand your explanations.
That C3 9E must stand for 0D 0A 0D 0A 5B 54
So the length must be 6 and the offset must be 0x26.
But I can't find those values in C39E.
## Post #7
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-21T05:05:51+00:00
- Post Title: compressed files from N64 ROM (LZSS)

Agh, sorry, you're absolutely right, I confused the first and second one because I was working on both, and the string referenced in the second is actually located before the string referenced in the first one.

At offset 0x49 you get 00 08, which becomes 00000000 00010000, and at that location (0x56) it has "60 1D". THIS is the reference to "for". ("reinforce.")

String "for":
-byte 5 in the cluster 1 (second cluster)
-hex address in undecoded file: 19
-hex address in decoded first part: 15
-length: 3
(I THINK I only need these last two)

Still doesn't look like anything identifyable...
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-11-21T13:11:06+00:00
- Post Title: compressed files from N64 ROM (LZSS)

Somebody rang? 

At least the length value is not hard to see: Take into account that no sequence of characters that is shorter than three bytes will ever be compressed, then you can offset every length value by 3. Thus, search for the value 3 instead of 6. The last four bits of the little-endian reference word should do nicely:

```
000111010110 0000     0 +3 =  3 ("for")
100001111111 0011     3 +3 =  6 ("BadGuy")
011100111110 0010     2 +3 =  5 ("<CR><LF>rnf")
100110010010 1110    14 +3 = 17 ("=Time,Reinforce.,")
```


I currently do not see how the offsets work, though. They neither seem to be direct absolute nor relative values -- but I'm probably missing something.

[Edit: It seems, however, that identical "offset" parts refer to the beginning of the same character sequence. I'm beginning to wonder if a data structure different from a simple buffer has been used.]
## Post #9
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-21T15:00:11+00:00
- Post Title: compressed files from N64 ROM (LZSS)

Hmm... it seems we're getting somewhere 

Thanks for the info, I didn't think about the minimum of 3 thing.


lol, this probably means the index blocks are little-endian too, and then completely reversed.
## Post #10
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-11-21T16:31:44+00:00
- Post Title: compressed files from N64 ROM (LZSS)

> Reply from Nyerguds
>
> lol, this probably means the index blocks are little-endian too, and then completely reversed.
Correct. 

I still don't see where the references lead us to, though. They look very irregular to me ...
## Post #11
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-22T05:35:10+00:00
- Post Title: compressed files from N64 ROM (LZSS)

Well actually they're not even reversed.. the lowest bits are simply used for the lowest index number, but meh.

I've looked into the offsets some more, and I see what you meant with the identical offsets pointing to identical locations, yes... still can't figure out how it's coded though.

[edit]

Hmm... apparently this port was done by Looking Glass Studios (Thief, System Shock). I might want to look into their other PC games and see if they have used the same file archive system in one of them.

[edit]
"Thief" just uses renamed ZIP files. Bummer. Looking into any other games now, specifically closer to 1999 (when the Command & Conquer ROM was released)

[edit again]

System shock 1 has two special data formats (.DAT & .RES), but neither looks anything like this file archive, or even compressed 
The game's from '93 though.

[edit yet again]

System shock 2 (1999) uses... renamed ZIP files
## Post #12
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-25T15:04:05+00:00
- Post Title: compressed files from N64 ROM (LZSS)

(can somebody explain why you can attach a .CSS file to the forum, but NOT plain .TXT? And why stuff between CODE tags still creates smileys? That's "8D", btw.)

---

I made a list of the reference codes (minus the length part) and what they reference to for the first part of the file (until the line "X=21" in the [MAP] ini section)

```
1D6 = 0x15
87F = 0x1F
13F = 0x2B
F0F = 0x30
9EC = 0x31
66D = 0x3B
73E = 0x40
992 = 0x46
4E3 = 0x4B
CAF = 0x4F
097 = 0x58 *
097 = 0x58 *
82F = 0x59
8F4 = 0x63
E8D = 0x64 * ! (0x8A)
E8D = 0x64 * ! (0x8A)
716 = 0x65
E8D = 0x8A   !
5D5 = 0x92 *
5D5 = 0X92 *
7E2 = 0x93
15F = 0xA4
AE4 = 0xA8 !!
AD4 = 0xA8 !!
51B = 0xAB
F35 = 0xB5
56B = 0xD1
0DC = 0x101
1AD = 0x11B
774 = 0x18E

```


*: indicates duplicates. The referenced strings don't always have the same length, which would indicate that the reference code itself is unrelated to the length.

!: The code E8D references a string (",0<CR><LF>") that is first found at 0x64. For some reason they don't use that occurence, but rather one that comes later, at 0x8A. The third time the code E8D is used it references a longer string, which shows which string it is really about.

!!: the code AE4 (",0,None,") and AD4 (",0,") both SEEM to reference the string at 0xA8 (first occurence of ",0,None,"). Most probably they reference different strings with the identical beginning ",0,", but I can't imagine why they wouldn't take the first occurence.
This is especially strange since the code AD4 is later used to reference a string ",0,None", which is the same string referenced by AE4 but without the last comma.
It also shows that this is not done to somehow only reference to the longest occurence of a string (which might indicate indexing of strings), like the E8D case could indicate.
[decode.rar](https://xentaxbackup.github.io/file/1402_decode.rar)
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-11-26T00:21:31+00:00
- Post Title: compressed files from N64 ROM (LZSS)

That's a very thorough analysis, good work!

> Reply from Nyerguds
>
> Most probably they reference different strings with the identical beginning ",0,", but I can't imagine why they wouldn't take the first occurence.
That might have to do with the string search method used. Depending on the implementation, the algorithm may not guarantee finding the first occurrence of the given substring (which is not an important property in this case).

> Reply from Nyerguds
>
> This is especially strange since the code AD4 is later used to reference a string ",0,None", which is the same string referenced by AE4 but without the last comma.
It also shows that this is not done to somehow only reference to the longest occurence of a string (which might indicate indexing of strings), like the E8D case could indicate.
I'm not sure about that. The longer I look at the data, the more I get the feeling that some sort of hashing or indexing has been used. (That feeling, however, is more or less based on the fact that I fail to make out any meaningful pattern.)
## Post #14
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-26T07:48:32+00:00
- Post Title: compressed files from N64 ROM (LZSS)

Yeah, I also think it might be some sort of indexing... it's just that those small abnormalities are weird.
## Post #15
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-11-27T09:10:16+00:00
- Post Title: compressed files from N64 ROM (LZSS)

I wonder if it's a coincidence that these 2 codes (AE4 & AD4) that seem to reference to the same string  ",0,None," have a difference of exactly 0x10... might give some hint to how the indexing is done.
## Post #16
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-12-02T22:52:42+00:00
- Post Title: 

Possible, but difficult to say. If it was a piece of PC software, I'd suggest disassembling, but currently I'm out of ideas here ...
## Post #17
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-12-03T22:04:58+00:00
- Post Title: 

I had a look at it, too. It looks like the offsets are encoded in some way. Usually there's 2 bits of some kind of command followed by 4 bits. If you combine the 2x4 bits you sometimes end up with the correct offset. It's probably some way to increase the dictionary size to more than 4kb while still only using 12 bits for the offset, or something like that.
## Post #18
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2007-12-12T13:03:00+00:00
- Post Title: 

Well, in the end I noticed that there was one single file that could be found uncompressed in the memory dump (quick save) of the emulator.

This file, which contained the mission objectives for all missions in the game, was mentioned in one single place in the ROM file (except for the file archive of course).

So all I needed to do was replace that filename string in the ROM by the filename of the file I wanted to extract, launch the game, start a mission and go to options menu to read my mission objectives.

The actual mission objective text is blank after replacing the file, but it doesn't crash, and if I save the game at that point I can get the complete uncompressed file from the mem dump.

It's still a pity I didn't get through the compression algorythm, but I got the files I need now, so I'm going to leave it at that.


Either way, thanks for all the help I got here. And yes, it DID help me in some way:

See, C&C missions are 2 files, one binary file with raw terrain data, and one INI file with the stuff on the map (units, structures, trees, mission programming...)
The INI files of the N64 ROM are perfectly compatible with the PC version, but from the terrain maps I could only recover which places were clear terrain and which places used to contain terrain elements. To recover that data I just went ingame to see what was there, and rebuilt the map with a map editor.

The knowledge of the compressed format did help me there, because despite the compression I could slightly edit the mission INI file to uncover all terrain more easily (usually by replacing enemy defences by useless buildings  )
