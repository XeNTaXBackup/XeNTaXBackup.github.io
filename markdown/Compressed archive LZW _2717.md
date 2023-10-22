## Post #1
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-21T14:07:59+00:00
- Post Title: Compressed archive LZW ???

Hi,

I need to develope the compression/decompression code (c++) for this archive type: [test](http://www.mak.org.uk/test.l3).  The archive format is pretty straight forward so I can extract/add chunks with no problem - I just can't de/compress them.

I think the compression is derived from LZW but I really don't know anything about working directly with compression algorithms.  Here's what I've worked out about the archive structure though:

```
{
	char id[4];			// +0: "LSls"
	DWORD sig; 		// +4: 0c, 02, 37,00
	WORD w0;			// +8: 00, 00
	DWORD chunks; 	// +10: additional LSls chunks
	char c1[8];			// +14: 
	WORD chunks40; 		// +22: ??? 0x40 + chunks
	char c0;				// + 24 00
	DWORD space; 		// +25: 0x00001100 ??? free space after index
	DWORD size; 		// +29: 0x1100 + (sizeof(index_entry) * chunks)
				 		// size + LSls header == this chunk size
	WORD w1;			// +33:
	WORD time;			// +35:
	WORD date;			// +37: MSDOS date/time
	WORD w2;			// +39:
	char nameLen;		// +41:
	char name[13];		// +42: total size == 55 (0x37)
};

struct LSls_CHUNK // total size == 55 (0x37) // sizeof is invalid due to alignment
{
	char id[4];			// +0: "LSls"
	DWORD sig; 		// +4: 0c, 02, 37,00 - 0x0037020c
	WORD w0;			// +8: ??? 00, 00
	DWORD chunks; 	// +10: ???
	char c1[8];			// +14: ???
	WORD chunks40; 	// +22: ??? 0x41 for uncompressed file
	char compressed;	// +24: 0 = not compressed, 1 = compressed
	DWORD sizeU; 		// +25: file size uncompressed
	DWORD sizeC; 		// +29: file size compressed
	WORD w1;			// +33: 00 ???
	WORD time;			// +35:
	WORD date;			// +37: MSDOS date/time
	WORD w2;			// +39: 00 ???
	char nameLen;		// +41: len of file/chunk name
	char name[13];		// +42: 12 + null, padded with 0x20 for shorter names
};

struct INDEX_ENTRY
{
	char name[64]; // file name
	DWORD offset; // file offset to this LSls chunk
};
```


The file header is followed by an index entry for each file in the archive.  The index is then followed by 0x1100 bytes (maybe for the string table???) before the first compressed chunk.

The example in the link includes 5 files:
null.txt: Just 32 null bytes.
ff.txt: 32 bytes of 0xff.
abc.txt: repeated 'ABC'.
icon.ico: a small icon file.
texture.tga: a typical graphic file.If you'd like any particular files compressed to work with just let me know.  Likewise if you'd like some seperate compressed chunks.

I hope someone here can help me out with this as I'm not getting very far on my own.
## Post #2
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-23T10:38:12+00:00
- Post Title: Compressed archive LZW ???

I don't know if anyones actually having a look at this for me but here are a few examples of compressed data that someone may be able to decipher.

```

00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00

compressed
00 01 08 1c 48 b0 20 80 80
00000000 00000001 00001000 00011100 01001000 10110000 00100000 10000000 10000000

-------------------------------------------

ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff

compressed
00 ff 09 1c 48 b0 e0 bf 80
00000000 11111111 00001001 00011100 01001000 10110000 11100000 10111111 10000000

-------------------------------------------

cabababababababab
63 61 62 61 62 61 62 61 62 61 62 61 62 61 62 61 62
01100011 01100001 01100010 01100001 01100010 01100001 01100010 01100001 01100010
01100001 01100010 01100001 01100010 01100001 01100010 01100001 01100010
 
compressed
00 c7 84 11 33 b0 20 c1 83 06 03 02
00000000 11000111 10000100 00010001 00110011 10110000 00100000 11000001 10000011
00000110 00000011 00000010

-------------------------------------------

abababababababab
61 62 61 62 61 62 61 62 61 62 61 62 61 62 61 62
01100001 01100010 01100001 01100010 01100001 01100010 01100001 01100010
01100001 01100010 01100001 01100010 01100001 01100010 01100001 01100010
 
compressed
00 c3 88 11 48 70 a0 c1 82 01 01
00000000 11000011 10001000 00010001 01001000 01110000 10100000 11000001
10000010 00000001 00000001

-------------------------------------------
```
## Post #3
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-23T12:01:48+00:00
- Post Title: Compressed archive LZW ???

Just a small observation: The compressed data seems to be formatted as a bit stream comprised of alternating 1 bit and 8 bit entities (saved together as a 9 bit value), which are probably read from the LSB onwards (but not reversed).

Lets take the "cab-stream" as an example. Formatted as the aforementioned bit stream, the data looks as follows:

```
0 01100011 // "c"
0 01100001 // "a"
0 01100010 // "b"
1 00000011
1 00000101
1 00000100
1 00000111
1 00000110
1 00000001
000000     // leftover padding bits
```

I'd guess that the single bits serves as a compressed/uncompressed flag, where "0" indicates that the 8 bit sequence is a literal, while "1" indicates compression. In that case, the 8 bit sequence might stand for something like buffer offset/length references, but I'm not entirely sure about that.

The assumption that the single bit is a flag is backed by the other examples, such as the "ff-stream":

```
0 11111111 // 0xff
1 00000010
1 00000011
1 00000100
1 00000101
0 11111111 // 0xff
1 00000001
```

Note that the "00-stream" is identical to the above "ff-stream" (except for the literals, of course) when formatted this way, which I would consider a good indicator that the structure is basically correct.

Hope that helps!
## Post #4
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-23T12:57:31+00:00
- Post Title: Compressed archive LZW ???

Cheers Deniz, Good spot!  This certainly seems to be very significant.

That being the case, am I right in thinking that this is not based on LZW afterall?  Any ideas on what type of compression uses a format like this - or could it be custom?
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-23T13:37:22+00:00
- Post Title: Compressed archive LZW ???

It's probably custom to some extent, but might still be based on LZW. The 8 bit sequences flagged with "1" could be indexes for dictionary entries; I'd have to check that ...

Edit: Seems you were right, it is indeed LZW. Since literals are encoded separately, we can assume the first free dictionary entry to be 2 (codes 0 and 1 probably indicate beginning and end of stream). The compression sequence for cabababababababab would thus look like this:

```

-       c       c
c       a       ca              c       2: ca
a       b       ab              a       3: ab
b       a       ba              b       4: ba
a       b       ab
ab      a       aba             3       5: aba
a       b       ab
ab      a       aba
aba     b       abab            5       6: abab
b       a       ba
ba      b       bab             4       7: bab
b       a       ba
ba      b       bab
bab     a       baba            7       8: baba
a       b       ab
ab      a       aba
aba     b       abab
abab    -                       6
```

This would lead exactly to the compressed data seen in the example:

```
0 "c"
0 "a"
0 "b"
1 3
1 5
1 4
1 7
1 6
1 1 // end of stream
```

Just out of curiosity: Where does this particular archive originate from?

Edit #2: Another example for aaaaaaaaaaaaaaaa, with "a" representing 0x00 or 0xff:

```

-       a       a
a       a       aa              a       2: aa
a       a       aa
aa      a       aaa             2       3: aaa
a       a       aa
aa      a       aaa
aaa     a       aaaa            3       4: aaaa
a       a       aa
aa      a       aaa
aaa     a       aaaa
aaaa    a       aaaaa           4       5: aaaaa
a       a       aa
aa      a       aaa
aaa     a       aaaa
aaaa    a       aaaaa
aaaaa   a       aaaaaa          5       6: aaaaaa
a       -                       a
```
## Post #6
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-23T15:15:06+00:00
- Post Title: Compressed archive LZW ???

Jeez Deniz, that's great, thanks!  I just need to work out how to use this info now.   

This is the format used for links2003 golfer ani's.  The link in the first post gives an example of how these archives are packed.  There are a few unknowns in the chunk headers that may be dealing with rapping/renewing the dictionary - but I'm getting ahead of myself there.

This has been a great help in getting me started on the right track.
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-23T15:28:24+00:00
- Post Title: Compressed archive LZW ???

> Reply from Marctwo
>
> Jeez Deniz, that's great, thanks!  I just need to work out how to use this info now.
You're welcome. You'll probably get farthest by trying to do an implementation and seeing what happens. 

> Reply from Marctwo
>
> This is the format used for links2003 golfer ani's.
Ah, I see. Well, as soon as you have succeeded, don't forget to document the format. 

Good luck!
## Post #8
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-23T15:41:53+00:00
- Post Title: Compressed archive LZW ???

> Reply from Deniz Oezmen
>
> You'll probably get farthest by trying to do an implementation and seeing what happens.Yes, I'm on it.  Very interesting stuff to work with...

> Reply from Deniz Oezmen
>
> Ah, I see. Well, as soon as you have succeeded, don't forget to document the format.Will do!

Thanks again.
## Post #9
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-07-24T07:05:56+00:00
- Post Title: Compressed archive LZW ???

Just a note: The first bit and next 8 bits probably make up a 9bit code word.
"100000000" then indicates to clear the dictionary. Codes < 256 are literals and codes >= 258 indices into the dictionary.
You can probably use an existing LZW decompressor and play around with it.
## Post #10
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T07:39:41+00:00
- Post Title: Compressed archive LZW ???

> Reply from john_doe
>
> "100000000" then indicates to clear the dictionary. Codes < 256 are literals and codes >= 258 indices into the dictionary.
Good interpretation. Any idea for the code word "100000001" other than EOS?
## Post #11
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-07-24T07:46:58+00:00
- Post Title: Compressed archive LZW ???

No.
## Post #12
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T07:55:04+00:00
- Post Title: Compressed archive LZW ???

It is settled, then.
## Post #13
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-24T10:46:42+00:00
- Post Title: Compressed archive LZW ???

Early indications are that 0x100/0x101 are start/stop codes that are used in conjunction with a counter in the compressed chunk header.  So everytime you get 0x101, you decrement the counter, clear the dictionary and look for 0x100 to start the next stream (if indicated by counter).

Presumably, when a dictionary index higher than 0x111 (edit: 0x1ff   ) is required during compression, the dictionary is cleared, 0x101 is output to indicate EOS, the counter is incremented and a new stream is started with 0x100.

As I say, these are early indications - but I don't think they'll be to far off.
## Post #14
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-24T14:32:51+00:00
- Post Title: Compressed archive LZW ???

The bitlength is variable.  So when code 0x1ff is used, the words change from 9 to 10bits.  Don't know the maximum bitlength yet.
## Post #15
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-07-24T15:03:11+00:00
- Post Title: Compressed archive LZW ???

That's normal for LZW. The maximum length is probably 13 or 14 bits.
## Post #16
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-24T18:45:26+00:00
- Post Title: 

Right, cheers.

I've got it working fine on smaller files but with larger files, it gets to 13bits, works ok for about 100 char's and then starts to become garbled.   

At the point where it breaks up, the next available table offset is 0x103c so it's not too far in to the 13bit codes.  The next input code is 0x101b which would seem to confirm that I should be reading 13bit words at this point as 0x101b simply wouldn't work as anything but a 13bit code for the text files I'm testing with.

Most likely, I've overlooked something obvious in my code and I need a break.
## Post #17
- Username: Marctwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 21, 2007 6:39 am
- Post datetime: 2007-07-24T20:43:53+00:00
- Post Title: 

OK!  Unpacking is sorted!   

Variable 9-13bit; 0x100 is, as John said, the clear dictionary code; 0x101 comes only once to mark the end of the stream.

Think I'll have a break before I start on the packing code.
