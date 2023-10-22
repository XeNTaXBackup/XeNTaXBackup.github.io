## Post #1
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2015-12-18T15:16:17+00:00
- Post Title: SAP Compression

Hey XentaX it's been ages!  I've been trying to crack this one for three years now without any significant progress so here's to hoping it's just something silly I've missed.
This type of file is found in two games, Aquapazza and Nitro+Blasterz: Heroines Duel.  It is used for every sprite/effect in the game but has different compression methods depending on flags found in the header.  These files also contain two streams per file, which are then either striped together or appended based on another flag.  The entire file should be read in Big Endian.

24 Bytes - Header
4 Bytes - Signature (.SAP)
4 Bytes - Flags
4 Bytes - Stream 1 decompressed size
4 Bytes - Stream 2 decompressed size
4 Bytes - Stream 1 file offset
4 Bytes - Stream 2 file offset

4 Bytes - Flags

Byte 1 - Unknown
Byte 2 - Striping mode.  0 = alternate every 4 bytes, 1 = alternate every 8 bytes, -1 = append the second stream to the first
Byte 3 - Stream 1 compression mode
Byte 4 - Stream 2 compression mode

Compression Mode 0
Read a short (2 bytes) and store as a control value.
For each bit in the control value starting with the most significant bit, do a check.
 - Read two bytes and place them in the output buffer.
 - Read a short and parse it.  The most significant 5 bits are the number of bytes to be copied, plus two.  The least significant 11 bits are an offset to copy from the output buffer, plus one, and then doubled.

```
int copy_bytes = (code & 0xf800)>>>11;
copy_bytes += 2;
int copy_offset = write_pos - 2 - ((code & 0x7ff) * 2);
```

 - Repeat until you've reached the end of the output buffer

Compression Mode 1 (Problem!)
Read a byte as a control value.
Loop through the control bits as before, but following these rules:
 - On a 1, read and store a byte.  Mark the fact that you've just read a 1.
 - On a 0 if the previous control bit was a 1, read another byte and follow the logic from Compression Mode 0.  Clear the state.
 - On a 1 if the previous control bit was 1, read another byte and follow the logic from Compression Mode 0 except for the offset, which is currently unknown.  Clear the state
 - On a 0 if the state is clear, read and output a byte.

So that's where I'm at currently.  Here's a link to my Java code and a sample file to mess with.
[https://twitter.com/LegendBlueShirt/sta ... 2858644480](https://twitter.com/LegendBlueShirt/status/677118632858644480)


Q: If you haven't figured it out yet, how do you know you're parsing the values correctly?
A: Because even though my output is garbage, the number of bytes is correct and uses up the input buffer completely.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-18T15:36:21+00:00
- Post Title: SAP Compression

hey just wondered if you knew what the sample image _should_ look like? i did a quick google of the game logos but they don't look too similar to the output you have.

edit

also, getChar() returns 2 bytes? and get() returns just 1? the source is confusing:

```

code = bb.get();

```
## Post #3
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2015-12-18T16:38:42+00:00
- Post Title: SAP Compression

The sample I provided should be a tornado effect.
In fact, every image where the problematic compression scheme shows up is a DXT texture.

Edit:  Welcome to Java.  Yes you are correct, get() returns a signed byte and getChar() returns an unsigned short.  Char and Short are both two byte primitives in Java.
