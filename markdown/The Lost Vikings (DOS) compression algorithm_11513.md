## Post #1
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2014-05-17T10:15:35+00:00
- Post Title: The Lost Vikings (DOS) compression algorithm

Hi all,

I'm hoping this is an easy one.  Does anyone know what compression algorithm is used by The Lost Vikings?

[Here is a sample compressed file](http://www.shikadi.net/files/games/lost-vikings/lostvikings-535.z).  After decompression it should be in XMI format.  I don't have a decompressed version of it, but [here is another file in XMI format](http://www.shikadi.net/files/games/lost-vikings/example.xmi) which should be much the same, apart from the file offsets (so the text fields like "FORM" and "XDIRINFO" should be the same at the same offsets.

It looks tantalisingly easy!  Any ideas?  The file offsets seem to be off by two so I wouldn't be surprised if the first two bytes are some sort of length value.

```
00000000  a4 01 ef 46 4f 52 4d fd  0f 0e 58 44 bf 49 52 49  |...FORM...XD.IRI|
00000010  4e 46 4f fd 0f 02 ff 01  00 43 41 54 20 00 00 bf  |NFO......CAT ...|
00000020  01 86 58 4d 49 44 00 30  01 bd 7a 1e 10 54 49 4d  |..XMID.0..z..TIM|
00000030  42 fd 0f 82 fd 40 1a 00  01 01 02 01 03 01 ff 04  |B....@..........|

Different file in same format, not compressed:
00000000  46 4f 52 4d 00 00 00 0e  58 44 49 52 49 4e 46 4f  |FORM....XDIRINFO|
00000010  00 00 00 02 01 00 43 41  54 20 00 00 08 a6 58 4d  |......CAT ....XM|
00000020  49 44 46 4f 52 4d 00 00  08 9a 58 4d 49 44 54 49  |IDFORM....XMIDTI|
00000030  4d 42 00 00 00 0c 05 00  71 00 31 00 20 00 49 00  |MB......q.1. .I.|

```
