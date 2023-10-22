## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2023-01-11T17:02:05+00:00
- Post Title: Media Station CXT files

Hi all,

Media Station, the company responsible for most Disney Animated Storybooks (and, ironically, one Living Book), had a game engine that relied on files ending with a .CXT extension. I always "love" it when companies use existing file extensions for their own proprietary file formats, don't you? Yep, these are not protected Cast files, but rather "context" files. I've mostly figured the structure out, but there are a few things I still don't know. Here's what I've managed to figure out.

Header:
* 8 bytes: 49490000EEEE0000 (most likely the magic number)
* 4 bytes: number of files
* 4 bytes: tail offset

Tail:
* For each file:
** 2 bytes: unknown (file ID/number?)
** 4 bytes: file offset
** 4 bytes: file length
** 4 bytes: unknown (NULL padding?)

IMTS files:
* "RIFF" ID string
* 4 bytes: length of RIFF file minus 8
* "IMTS" type string (don't know what it stands for/is short for, but this is why I call them "IMTS files")
* "rate" string
* 4 bytes: rate (of what, I don't know)
* 4 bytes: unknown
* "LIST" string
* 4 bytes: length of data sub-chunk
* "data" tag
* For each interleaved file chunk:
** 4 characters: name of file
** 4 bytes: size of chunk

Example CXT files (from 101 Dalmatians Animated Storybook): [https://mega.nz/file/f1xA3K7Z#xoxMBbUKk ... oedXlytEvg](https://mega.nz/file/f1xA3K7Z#xoxMBbUKkgaFrzWjW1r4d8oecSC33YgDOoedXlytEvg)

QuickBMS script for extracting the IMTS files themselves (but not de-interleaving them): [http://aluigi.altervista.org/bms/disney ... ng_cxt.bms](http://aluigi.altervista.org/bms/disney_lion_king_cxt.bms)

-Johnny
