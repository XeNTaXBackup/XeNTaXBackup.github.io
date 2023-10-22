## Post #1
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-10-12T01:49:39+00:00
- Post Title: [Solved] Raptor GLB - decryption help (XOR?)

Hi all,

I am struggling to decrypt the filenames in the Raptor GLB format.  I have obtained the decrypted filenames from a memory dump, but I am stuck trying to figure out the decryption algorithm.

Here is the mapping between the encrypted bytes and the decrypted data.  Each character position has a slightly different algorithm (possibly due to an XOR encryption key) but all letters are the same - e.g. every time 0xc1 appears as the third character, it *always* translates to 0x41 (capital A), regardless of the characters that appear before or after it.

```
CHAR_DEC="41 42 43 44 45 46 47 48 49 4a 4b 4c 4d 4e 4f 50 51 52 53 54 55 56 57 58 59 5a"

# A-Z encoded as the first character in a filename (e.g. 41 encodes to CF, 42 encodes to CE, etc.)
CHAR1_ENC="cf ce cd cc cb ca c9 c8 d7 d6 00 d4 d3 d2 d1 00 00 de dd dc 00 da d9 00 00 00"

# A-Z encoded as the second character in a filename
CHAR2_ENC="c1 00 00 00 dd 00 df d8 d9 00 00 d4 d5 d6 d7 d0 00 d2 00 ec 00 ee 00 e8 00 00"

# Same again for third and fourth characters
CHAR3_ENC="c1 00 00 c4 c5 00 cb c8 c9 00 00 cc cd d2 d3 d0 00 d6 d7 d4 00 da db d8 d9 de"
CHAR4_ENC="47 46 00 44 4b 00 49 00 4f 00 00 4c b3 b2 b1 b0 00 b6 b5 b4 bb 00 00 00 00 00"

# The 00 bytes in the CHAR*_ENC values are where this character was not used in that position
# in the game files, so I don't know for certain what the encoded byte is.

```

If anyone can shed any light on this it would be much appreciated!  I'm after primarily a decryption algorithm but I do want to be able to re-encrypt filenames too.
## Post #2
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-10-12T09:13:58+00:00
- Post Title: [Solved] Raptor GLB - decryption help (XOR?)

Just to save anyone the time on this, I have reverse engineered the algorithm used by the game and so this problem is now solved.  As it turns out the game does not quite use XOR, which is why the values were appearing strangely.  I am in the process of writing up an explanation for the full encryption algorithm which will appear shortly on the [ModdingWiki page for the GLB format](http://www.shikadi.net/moddingwiki/GLB_Format).
