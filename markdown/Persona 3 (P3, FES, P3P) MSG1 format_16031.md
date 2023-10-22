## Post #1
- Username: IlDucci
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 20, 2014 10:01 pm
- Post datetime: 2017-03-20T12:10:28+00:00
- Post Title: Persona 3 (P3, FES, P3P) MSG1 format

Good evening. I'm looking for help to translate the texts found in the Persona 3 games. MSG1 is the most used format (There's another two that are simpler), and so far I had no luck.

Here's the specs I found:

```
0x00: 07000000
0x04: Full file size
0x08: Magic word MSG1
0x0C: Unknown, filled with 0x00

0x10: End position of the text table, beginning of linejump table
0x14: Amount of pointer blocks
0x18: String amount (Two blocks per string)
0x1C: Apparently fixed value, 0x20000

POINTER BLOCKS
0x08 bytes
0x00: 0x00
0x04: Pointer to string block

STRING BLOCKS
Before the string block area there's an 0x10 byte row with extra content. If the file has character names, this will point to the character name area and the amount of names.
0x00 bytes: End of text block/Start of character size (If exists) (Relative to 0x20)
0x04 bytes: 0x00 if there's no character blocks, amount of character names if it exists.
0x08 bytes: Filled with 0x00s

Now to the string blocks themselves. Each one is aligned to 4 bytes.
0x00: String identifier (Filled with 0x00 as padding)
0x18: Seems like an identifier of the type of string (Normal string/With character name/Choice options)
0x1C: Unknown
0x20: String size
0x24: String contents

CHARACTER BLOCKS (If they exist)
0x04 bytes per pointer (Absolute to file), after that there's the names (They're not aligned).

LINEJUMP BLOCK
This is the funniest one. It seems that this area calculates the places where the text is cut between lines. 1 byte per linejump or line end.

```


Text encoding seems to be S-JIS for Japanese texts and simple ASCII for western texts.
[P3.7z](https://xentaxbackup.github.io/file/12663_P3.7z)
