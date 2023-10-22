## Post #1
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2011-11-10T12:09:39+00:00
- Post Title: Stargunner DLT compression

Hi all,

Following on from [this post back in 2006](http://forum.xentax.com/viewtopic.php?f=10&t=1895) I had another look at the Stargunner compression format.  It looks tantalisingly simple, but alas I'm struggling somewhat.

I've [uploaded a couple of files](http://www.shikadi.net/files/games/stargunr/) (compressed and decompressed versions) so if anyone is willing to take a quick look that would be great.

From what I've made out so far, the files seem to be laid out like this:

 - "PGBP" signature
 - uint32 for decompressed size
 - uint16 for some kind of "chunk size" (in smaller files is equal to the number of bytes until EOF)
 - dictionary/lookup table, often until 00 00 which is frequently the last entry in the dictionary table (no idea how the dictionary size is set)
 - another uint16 chunk size for the data (in smaller files is again equal to the number of bytes until EOF)
 - actual data, with codes referring back to the dictionary.  The FF code is often replaced with 00 00, which seems to coincide with 00 00 being the last bytes in the dictionary
 - with larger files, at the end of the chunk the next chunk begins, seemingly with a new dictionary

If anyone has any insights it would be greatly appreciated!
## Post #2
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2011-11-12T00:09:19+00:00
- Post Title: Stargunner DLT compression

Looking at this further, it seems there are actually two variants to the compression, but they all seem to be based around [byte pair encoding](http://en.wikipedia.org/wiki/Byte_pair_encoding).  Focusing on one for the moment (the one in the files I posted above), it seems to be roughly in this structure (using data from title.mod as an example)

```
DC 20 05 00  // decompressed size
8C 02        // chunk size
FE 7F        // dictionary signature (different format follows if != 0x7FFE)
B0           // first code -1 (B0 means first code is B1)
F9 FD        // B1 expands to these two bytes (which in this case, each further expand to other bytes)
17           // this many byte pairs follow (although not always)
F9 F5        // B2 expands to these
ED DD        // B3 expands to these
B4 0A        // B4 expands to these (but maybe not as this is infinitely recursive)
...
FE 01        // length of data subchunk
B1           // Expanded as per code B1 above
53 74 61 72  // Passed through unchanged
...

```

This doesn't quite work for title.mod though (has some rubbish mixed in with the expanded data), but it does successfully decompress smaller files like menu.pal.  Byte pair encoding only seems to use bytes that aren't in the source data as codewords, however I'm not sure how to tell from the dictionary in these files which byte values are codewords and which aren't.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-12T16:35:28+00:00
- Post Title: Stargunner DLT compression

I gave a quick scan with my QuickBMS compression scanner but found nothing
## Post #4
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2011-11-15T09:27:01+00:00
- Post Title: Stargunner DLT compression

Thanks for investigating.

I've had an e-mail from someone who disassembled the algorithm and coverted it to C.  If anyone is interested, I will be documenting it over the coming weeks on the [Game Modding Wiki](http://www.shikadi.net/moddingwiki/DLT_Format) and of course implementing it in [Camoto/libgamearchive](http://www.shikadi.net/camoto).
