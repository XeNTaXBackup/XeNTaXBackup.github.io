## Post #1
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2010-03-20T22:35:06+00:00
- Post Title: Metro 2033: about packed files in the game archives

hello.

this is content of packed and unpacked sample file:


i have a part of C code for unpack these files:

```
	const unsigned counts[16] = {	4, 0, 1, 0,
												2, 0, 1, 0,
												3, 0, 1, 0,
												2, 0, 1, 0	};
	unsigned char *outp = outbuf, *p;
	unsigned char *outlast = outbuf + outlen - 1;
	unsigned mask = 1, bits, len, off;
	for (;;) {
		assert(mask != 0);
		if (mask == 1) { mask = get_u32(inp); //printf("reload mask=%x\n", mask);
			inp += 4;}
		bits = get_u32(inp);
		if (mask & 1) {	mask >>= 1;	len = 3;++inp;
			if (bits & 3) {	++inp;
				if (bits & 2) {
					if (bits & 1) {	++inp;
						if ((bits & 0x7f) == 3) { ++inp; off = bits >> 15; len += (bits >> 7) & 0xff;}
						else { off = (bits >> 7) & 0x1ffff; len += ((bits >> 2) & 0x1f) - 1; }
					} else { off = (bits >> 6) & 0x3ff; len += (bits >> 2) & 0xf; }
				} else { off = (bits >> 2) & 0x3fff; }
			} else { off = (bits >> 2) & 0x3f; }
			//printf("back ref bits=%u off=%u len=%u\n", bits & 3, off, len);
			assert(outp - off >= outbuf);
			assert(outp + len <= outlast);
			p = outp;
			outp += len;
			do { put_u32(p, get_u32(p - off)); p += 3; } while (p < outp);
		} else
			if (outp < outlast - 10) { put_u32(outp, bits); len = counts[mask & 0x0f];
				//printf("literal run len=%u\n", len);
				outp += len; inp += len; mask >>= len;
			} else { //printf("tail len=%u\n", (unsigned)(outlast - outp));
				while (outp <= outlast) {
					if (mask == 1) { mask = 0x80000000; inp += 4; }
					*outp++ = *inp++; mask >>= 1; }
				return outlen; }
	}
}
```

anyone can help in determining the type of packer? сan i use the available types unpacker in quickbms?

in attachment sample files.
[packed_and_unpacked_files.zip](https://xentaxbackup.github.io/file/2873_packed_and_unpacked_files.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-03-21T14:20:25+00:00
- Post Title: Metro 2033: about packed files in the game archives

Hi, 1rst thanks for the unpacker it works great, and about the compression i have no idea, but i did a small test recompressing the sample file...and using 
7z i get: 201bytes 
winrar: 152bytes 
the original packed it's 123 
unpacked 526
Really strange..
And 

```

```

Maybe a LZ variant?
But we can ask in [http://www.encode.ru](http://www.encode.ru) (english forum) a scene-compression archive, sure we get some clue   
There you can found the creator of : paq, precomp, freearc..etc..a really amazing site.
## Post #3
- Username: deadok
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 22, 2010 10:24 pm
- Post datetime: 2010-03-23T22:09:34+00:00
- Post Title: Metro 2033: about packed files in the game archives

yeah, it one of LZ-family (can't say if it has name or smth).
though it quite simple.

read control bits packed in DWORD,
if current bit is 0 - next byte in input is raw data (should be simply copied to output)
if current bit is 1 - next byte(s)  in input contain length-distance pair(starting from 3-rd bit) and it's size-code(first 2 bits);

```
01dddddd dddddddd
10ssssdd dddddddd                      ; actual length = 3+ 'ssss'
11sssssd dddddddd dddddddd             ; actual length = 2+ 'sssss' (since minimum window size is 3, then 'sssss' should never equals 0)
1100000s sssssssd dddddddd dddddddd    ; actual length = 3+ 'ssssssss'

```

and, ofc, last 10 bytes in input always considered as 'raw'

btw, that code of yours decompresses only 1 chunk.
each chunk can be no more than 0x20000 bytes
and consists of:
* controlbyte (0x7c-0x7f), which specifies type of next chunk, 
* packed size (1/4 bytes)
* unpacked size (1/4 bytes)
* data (x bytes)
control byte defines type of chunk:
0x7f - compressed big chunk, p/u sizes are 4bytes
0x7e - not compressed big chunk, p/u sizes are 4 bytes (packed = unpacked + 9)
0x7d - compressed small chunk, p/u sizes are 1 byte
0x7c - not compressed small chunk, p/u sizes are 1 byte (packed = unpacked + 3) (actually, small chunk can't be more than 0xd8 bytes in length)
