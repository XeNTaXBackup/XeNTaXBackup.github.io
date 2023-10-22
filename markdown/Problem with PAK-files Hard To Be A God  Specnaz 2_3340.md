## Post #1
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-02-04T23:27:36+00:00
- Post Title: Problem with PAK-files: Hard To Be A God / Specnaz 2

I want to unpack PAK-files from these two games:

"Hard To Be A God" and
"Specnaz 2".

Both games use a similar file format with XOR-encryption.
The general structure of a PAK-file is:

<HEADER>
(XORed)<NUMBER_OF_FILES><FILE_TABLE_WITH_OFFSETS_AND_LENGTHS>
<DATA_AREA>

The filetable is XORed with a key (values see attachment).
Any first 100h bytes of a data entry are XORed with the same key.
After de-XORing the filetable one will recognize a well-known filename/offset/length-structure.

But that's not the problem.
The problem is the de-XORing of the first 100h bytes of a data entry, because the XOR-key starts with a relative offset, which is different for each data entry.

There must be a rule or formula for calculating this XOR-key-offset.

Has somebody got any clue or hint? Thank you in advance.
[PAK.RAR](https://xentaxbackup.github.io/file/1858_PAK.RAR)
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-02-05T10:25:14+00:00
- Post Title: Problem with PAK-files: Hard To Be A God / Specnaz 2

Try this: [http://int0thegame.blogspot.com/2008/04 ... e-pak.html](http://int0thegame.blogspot.com/2008/04/burut-creative-team-engine-pak.html)
