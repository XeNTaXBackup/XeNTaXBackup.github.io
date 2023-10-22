## Post #1
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-12-21T01:01:04+00:00
- Post Title: text compression

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2011-12-21T01:52:45+00:00
- Post Title: text compression

This looks more like a in-game script than just text. It's partially compiled. I'm not sure of the format, but I do remember that Bounty Hunter was created using an in-house engine at Lucasarts.
## Post #3
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-12-21T15:32:29+00:00
- Post Title: text compression

> Reply from Teancum
>
> This looks more like a in-game script than just text. It's partially compiled. I'm not sure of the format, but I do remember that Bounty Hunter was created using an in-house engine at Lucasarts.
I don't think it is a script because in the archives directory the file name ends in .txt, and there are some strings that are cut off making me think it is compression.
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-12-22T00:04:40+00:00
- Post Title: text compression

Looks LZSS
## Post #5
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-12-22T01:00:26+00:00
- Post Title: text compression

> Reply from Vash
>
> Looks LZSS

I tried [http://dev.gameres.com/Program/Other/LZSS.C](http://dev.gameres.com/Program/Other/LZSS.C) as well as [http://www.koders.com/c/fidC554142F5E42 ... 92DF8.aspx](http://www.koders.com/c/fidC554142F5E42CA3433CD4C8B9043D09C8A092DF8.aspx) and neither decoded the file correctly.
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-12-22T12:49:04+00:00
- Post Title: text compression

yeah, seems a non-standard approach. Apparently instead of 1b flag 8b code uses 2b flag 16b code. With some strange variants...I'd need the uncompressed file to be able to crack it successfully. You can obtain it by looking for a compressed text file that you know appears in the beginning of the game than dump it from the ram/savestate. I don't know for which console is this game so I can't be more specific
## Post #7
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-12-22T16:33:14+00:00
- Post Title: text compression

> Reply from Vash
>
> yeah, seems a non-standard approach. Apparently instead of 1b flag 8b code uses 2b flag 16b code. With some strange variants...I'd need the uncompressed file to be able to crack it successfully. You can obtain it by looking for a compressed text file that you know appears in the beginning of the game than dump it from the ram/savestate. I don't know for which console is this game so I can't be more specific
It's from the PS2, and I don't have any methods of dumping the memory.

EDIT: Are there any magic values I could search in the ELF? I could re-write the decompression code in C from the MIPS assembly if I knew the function address.
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-12-22T17:06:55+00:00
- Post Title: text compression

Unfortunately not, it's pretty basic math functions...
You can dump it by making a savestate with the emulator when the text you've chosen appears on screen, then unpack the file with winrar/7zip or whatever and you'll have a file that weights 32MB (eememory.bin, but I'm not sure, can't check right now). That's the ram, now just look for the line of text inside there and you can cut the uncompressed file
## Post #9
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-12-22T23:10:02+00:00
- Post Title: text compression

> Reply from Vash
>
> Unfortunately not, it's pretty basic math functions...
You can dump it by making a savestate with the emulator when the text you've chosen appears on screen, then unpack the file with winrar/7zip or whatever and you'll have a file that weights 32MB (eememory.bin, but I'm not sure, can't check right now). That's the ram, now just look for the line of text inside there and you can cut the uncompressed file

Thanks for your help, but I'm more interested in decompressing the textures. I just used a text file as an example since I figured it would be easier to analyze.
## Post #10
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-12-23T09:06:20+00:00
- Post Title: text compression

yeah, and why wouldn't you extract some text to try to crack the compression?
## Post #11
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2012-07-07T01:24:21+00:00
- Post Title: text compression

I've managed to extract some uncompressed data from memory. The bad part is that it isn't 100% text. The game decompresses text to the stack and parses it there, so I can't really find it in memory as it all happens too quickly. If someone knows how to debug games in the pcsx2 emulator I could extract the text data.

Here are the two files. One extracted from the archive and compressed, the other extracted from memory and uncompressed.

EDIT: files removed. If someone thinks they can help, please pm me.
## Post #12
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2014-06-15T21:14:08+00:00
- Post Title: text compression

Almost exactly two years later, I have reverse engineered the decompression method. Here's the code:

```

typedef unsigned 	char BYTE;
typedef unsigned 	int  WORD; /* ps2 WORD = 4 bytes */
typedef signed 		int	 S_WORD; /* signed */

inline WORD read_marker(BYTE **src, WORD *block_index) {
	WORD marker;

	(*block_index) = BLOCK_SIZE;
	marker = (*src)[1] << 8 | (*src)[0];
	(*src) += 2;

	return marker;
}

inline WORD cycle_block(BYTE **src, WORD *block_index, WORD *marker) {
	WORD block_bit;

	block_bit = (*marker) & 1;
	(*block_index)--;

	if ((*block_index) > 0) {
		(*marker) >>= 1;
	} else {
		(*marker) = read_marker(src, block_index);
	}

	return block_bit;
}

WORD decompress(BYTE *src, BYTE *dest) {
	BYTE *dest_start, *dest_sub;
	WORD sub_index, sub_count;
	WORD marker, block_index;
	WORD bit_a, bit_b, byte_a, byte_b, byte_c; // dunno what these are called

	dest_start = dest;

	// ... read first marker in the file
	marker = read_marker(&src, &block_index);

PROCESS_MARKERS:
	// copy if regular data
	if (cycle_block(&src, &block_index, &marker) == 1) {
		dest++[0] = src++[0];
		goto PROCESS_MARKERS;
	}

	if (cycle_block(&src, &block_index, &marker) == 0) {
		bit_a = cycle_block(&src, &block_index, &marker) << 1;
		bit_b = cycle_block(&src, &block_index, &marker);

		sub_count = (bit_a | bit_b) + (WORD)3;
		sub_index = src++[0] | (WORD)0xFFFFFF00;

	} else {

		byte_a = src[1];
		byte_b = src[0];
		src += 2;

		sub_index = (((byte_a & 0xF0) << 4) - (WORD)0x1000) | byte_b;
		sub_count =	  (byte_a & 0x0F) + 3;

		if (sub_count != 3) {
			goto SUB_COPY;
		} else if ((byte_c = src++[0]) != 0) {
			sub_count = (byte_c + 1);
			goto SUB_COPY;
		}

		// else we're done decompressing

		return (dest - dest_start); // total decompresed
	}

SUB_COPY:
	dest_sub = (dest + (S_WORD)sub_index);

	if (sub_count == 0) {
		sub_count--;
		goto PROCESS_MARKERS;
	} else {
		do {
			dest++[0] = dest_sub++[0];
		} while (--sub_count > 0);
	}

	goto PROCESS_MARKERS;

	return 0;
}
```


To the thousands of people who will use this: you're welcome.
