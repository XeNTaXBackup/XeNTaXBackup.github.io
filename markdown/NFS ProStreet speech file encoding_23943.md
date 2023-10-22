## Post #1
- Username: TheUnpunished
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 12, 2021 6:58 pm
- Post datetime: 2021-05-25T06:46:58+00:00
- Post Title: NFS: ProStreet speech file encoding

Good day, people.
I've been trying to change the game's announcer speech files, but I could not even encode the files back using original game's sounds. There are 3 files that are used for the individual speech "archive": .hdr, .sth and .dat.
Here's the information I've found out so far:
.hdr has the structure like this:

```
0x02: parameters (userdata size, etc.)
0x03: number of files
0x04: sub-ID (used for different police voices in NFS games)
0x08: number of files
0x09: block size (seem to be always at 0)
0x0a: number of blocks (doesn't seem to do anything)
0x0c: number of sub-banks (seem to be always at 0)
0x0e: padding
0x10: start of the table
```

The table is a array of offsets that refer to .sth (2 bytes, big endian) + userdata (size of userdata)
.sth has the structure like this:

```
8 bytes: additonal info (small endian)
First 4 bits: version (0000, V0 for PS)
Next 4 bits: codec (0101/5/EL31 for PS)
Next 6 bits: channel configuration (000000 or mono for all the files in my case)
Next 18 bits: sample rate (44100 in my case)
Next 2 bits: type (01, streamed in my case)
Next 1 bit: loop flag (0, false, in my case)
Next 29 bits: sample count (varies on the file)
Repeat, until you get all the files.
```

.dat has this structure:

```
Next 3 bytes: chunk size, big endian (including the header)
4 bytes: sample count in the chunk, big endian
1 byte: seems to refer to some sort of raw data or not
```

I've tried a lot of things: adjusting the .sth accordingly, changing the .dat so it appears to be of the format like the original, but I had no success in it. Cannot open in the vgmstream (while the original can). The encoding of the new .dat was done using ealayer3. Probably the only thing I haven't done is trying to change the .mp3 files for encoding somehow.
Link for the original and reencoded files.
[https://drive.google.com/file/d/1Wa4V4B ... sp=sharing](https://drive.google.com/file/d/1Wa4V4BrLc-pYhAkqU1Twt9-e_dIQ6IQ8/view?usp=sharing)
