## Post #1
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-04-13T05:27:24+00:00
- Post Title: Unknown Compression

Anyone ever seen this kind of compression before??

EOF is always 0x0080
[Unknown Compression.zip](https://xentaxbackup.github.io/file/692_Unknown Compression.zip)
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-04-13T11:45:10+00:00
- Post Title: Unknown Compression

1) This is binary, not hex, lol, i was trying to open it up in Notepad
2) what makes you think this is a compression? is this suppose to be text?
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-13T12:36:59+00:00
- Post Title: Unknown Compression

Judging from the pattern in the beginning (entries of about 0x26 in length) i'd say that is a header that's been XOR-encrypted containing info about files in the archive.  The first 32-bit value is the size of the file without the 32-bit value itself.
## Post #4
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-13T21:11:08+00:00
- Post Title: Unknown Compression

I'd like to point out Unknown Compression.hex isn't related to the other file.

Unknown Compression.hex - Is/Was Taken from an already decompressed file. There are indications that this could very well be compressed. I've included the trailing entries for this file. The first 2 entries are in this format and the last 4 are not. They are essentially world coordinates for Texture placement and a few other things.

The file Unknown Compression 2.hex is actually a map file for a SEA file. This is not the same as the other level files and looks to be similar to the above entry.
[trailing file.zip](https://xentaxbackup.github.io/file/697_trailing file.zip)
## Post #5
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-04-14T03:47:30+00:00
- Post Title: Unknown Compression

Thanks for clarifying silver.

To clarify further
This is the last file spec for Fable The Lost Chapters. Once this is complete we'd have every file format the game uses.
