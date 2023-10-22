## Post #1
- Username: Dr Ishmael
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 31, 2010 10:59 am
- Post datetime: 2010-03-29T13:54:25+00:00
- Post Title: Guild Wars - compressed text strings within game files

I've been digging around in Guild Wars' Gw.dat file for a couple years now, inspired by the work done by people here at Xentax, mostly in [this thread](http://forum.xentax.com/viewtopic.php?f=10&t=1645&start=150&st=0&sk=t&sd=a), so thanks to everyone who contributed to that, especially the people that developed the GWUnpacker, without which I wouldn't have been able to do any of this.

On my own, I was able to figure out that a subset of the previously "unknown" files actually contained text, where I could find things like skill names and descriptions, item names, warning messages, and stuff like that.  The last 2 bytes of each file are flags that indicate the text language (English, Korean, etc.) and file number (currently 89 files per language).  The files each contain 1024 text strings, and each string has a 6-byte header.  The string itself is stored either as plain Unicode (UTF-16) or in some compressed format.  Currently, skill names and descriptions are all stored as Unicode, so I've been able to monitor them across game updates to catch any non-announced tweaks to the descriptions.

It is the compressed format that I would like to ask for some help figuring out.  I'm guessing that quest descriptions and other NPC dialogues are stored as compressed strings, so it would be really awesome if I could crack that.

The following snippet shows both a Unicode string (a skill name; header starts at 2C on the first line) and a compressed string (95% sure it's the skill description; header starts at 4E on the third line).

```
00005ea0h: 00 72 00 65 00 63 00 74 00 69 00 6F 00 6E 00 20 ; .r.e.c.t.i.o.n. 
00005eb0h: 00 53 00 69 00 67 00 6E 00 65 00 74 00 4E 00 52 ; .S.i.g.n.e.t.N.R
00005ec0h: 00 07 00 99 9E B8 99 05 DB AD 2B 7E BD EC 03 B2 ; ...™ž¸™.Û­+~½ì.²
00005ed0h: E7 41 C3 0A 32 CA FB 01 E7 01 BE 86 A6 58 DC 1C ; çAÃ.2Êû.ç.¾†¦XÜ.
00005ee0h: 6C 36 70 01 7A 27 1A C3 C4 69 B9 1D 63 04 EF 2C ; l6p.z'.ÃÄi¹.c.ï,
00005ef0h: C8 E0 20 11 25 4A 09 82 9C 45 0D CE 21 C0 4F 18 ; Èà .%J.‚œE.Î!ÀO.
00005f00h: 70 CD 38 5C A7 FF 52 31 95 CC 1B 00 00 00 00 00 ; pÍ8\§ÿR1•Ì......

```

Now, it wouldn't surprise me if someone recognized the format just by looking at that, but I'll go ahead and explain everything I've been able to figure out anyway.  The header breaks down as follows:

Bytes 1-2 are a uint16 giving the length of the string, in bytes, including the header.  Thus the first string here is 0x002C = 44 bytes long and the second string is 0x004E = 78 bytes.  (Gw.dat is little-endian, so the 00 byte is actually the one after the other byte in the snippet above)
Bytes 5-6 are another uint16 that seems to indicate the format of the string.  It is always 0x10 for Unicode strings, and usually 0x07 for compressed strings.
Bytes 3 and 4 are the real mystery.  For Unicode strings, they are always 0x00, and byte 4 remains 0x00 for most of the compressed strings, but it's also sometimes 0xFF, with no real correlation to the value of byte 3.

I made a discovery recently that shed a bit of light on byte 3, but not enough to completely solve this.  Currently, skill names and descriptions are all stored as Unicode strings, with the description immediately following the name 99% of the time.  On a whim, I pulled out my original GW install disc to check out the Gw.dat file there, and discovered that skill descriptions were actually compressed back then.

So I figured I'd grab the original skill descriptions off of GuildWiki's skill article histories and see what I could see.  And what I saw, after looking at only about 10 skills, was that byte 3 is actually the ASCII value of the lowest-value non-punctuation character within the description! Since for most text this would usually be a capital letter (0x41 - 0x5A), I ran a frequency check of byte 3, and sure enough, 80% of compressed strings have a byte 3 value within that range.

Long story short, I haven't been able to get anywhere after that.  I'm pretty sure it's actually a compression and not simply an encoding.  If it were just encoding, then descriptions that begin the same should still look the same when encoded, right?  The description for Resurrection Signet, above, and Resurrect, below, both begin with "Resurrect target party member...", but the compressed descriptions diverge after the first byte.

```
00007c00h: 00 65 00 63 00 74 00 21 00 52 00 07 00 99 47 47 ; .e.c.t.!.R...™GG
00007c10h: B4 D4 A4 D8 C2 23 D0 16 DC 62 32 5E 54 60 06 DF ; ´Ô¤ØÂ#Ð.Üb2^T`.ß
00007c20h: 22 9E 52 65 84 84 D2 99 00 00 00 00 00 00 00 00 ; "žRe„„Ò™........

```

I've attached a zip containing the two text files I pulled those snippets from.  Any help y'all can give me would be most appreciated.
[GW sample raw files.zip](https://xentaxbackup.github.io/file/2770_GW sample raw files.zip)
