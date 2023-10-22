## Post #1
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2006-02-19T18:47:39+00:00
- Post Title: Broken Sword 2 .CLU

Hi long time no post here! Not sure if being able to extract these would even be useful but if possible I would like to get the .CLU's from Broken Sword 2 extracted.

[http://lukereeve.co.uk/TEXT.CLU](http://lukereeve.co.uk/TEXT.CLU)
## Post #2
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-04T04:25:39+00:00
- Post Title: Broken Sword 2 .CLU

Sorry for old bump. I'm bored looked at file for a minute. Looked something like this.

18 Byte Header
[4] Bytes - Reference Lookup Table Offset
[4] Bytes - Null
[2] Bytes - Offset to first package/Header Size to calculate in later ( 8 )
[4] Bytes - Null 
[4] Bytes - Null

Reference Table (Lists each Section)
[4] Bytes - Offset ( you need to + (2 Bytes above)) this case offset + 8
[4] Bytes - Chunk Size

For Each Text Resource xxxx Package. 
Text Resource xxxx (null terminated)
[15] Bytes Null
[4] Bytes Number of files
~
(Number of files loop)
[4] Bytes - Offset in package (minus 10 bytes?)


~Text (Has 2 Byte ID of some sort) Actual Text is Null Terminated
## Post #3
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2022-12-28T09:03:37+00:00
- Post Title: Broken Sword 2 .CLU

Could someone with the proper expertise code an unpacker/repacker for this?

I've searched far and wide and didn't find any working tool, although I know that some fan translations exist out there.
## Post #4
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2023-01-02T18:16:38+00:00
- Post Title: Broken Sword 2 .CLU

Silver's post was very helpful, I did my own research on it and confirmed essentially the same things, although slight deviation in interpretation.

File header
4 bytes, lookup table offset
4 bytes, null


Text Resource
24 bytes, resource header
4 bytes, resource id
16 bytes, null
4 bytes, lookup table, total # of dialogue lines
4 bytes, lookup table, offset for each dialogue
(loop the one above until # of total dialogue lines)
2 bytes, dialogue ID
? bytes, dialogue text, null terminated 
(loop the one above until # of total dialogue lines)


File lookup table
4 bytes, text resource offset
4 bytes, text resource chunk size
(loop the two above until EOF)

Note: The 4 bytes previous to the Lookup Table are self-referencing (weird checksum? seems inconsequential...)

When changing a single dialogue line, for example, the following must be considered... let's assume that the original dialogue is 0x5a bytes and we add an extra 0x28 bytes to that line (0x82 bytes in total), the following must then be fixed:

- File header checksum offset: if it was 0xb1aa04 before, it should now be 0xd9aa04 (+0x28 bytes)

- Text Resource: byte-size must be divisible by 4, add enough null padding at the end of the resource if necessary.

- Text Resource lookup table: assuming this is the 3rd dialogue line, all subsequent offsets of this particular resource, for 4th dialogue line and onward, now need to be increased by 0x28 bytes (ex: 4th offset was 0xc302, it will become 0xeb02, and so on for all remaining offsets after the offset of the changed dialogue).

- File lookup table: the chunk size belonging to an edited text resource needs to be increased accordingly; any offsets bigger than the edited resource's also need to be adjusted accordingly (+0x28 bytes).


P.S: Attached a sample file, the original link is dead.
[TEXT.CLU.7z](https://xentaxbackup.github.io/file/23234_TEXT.CLU.7z)
