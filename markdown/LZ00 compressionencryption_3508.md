## Post #1
- Username: Nick W
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 25, 2009 10:04 pm
- Post datetime: 2009-05-25T15:46:09+00:00
- Post Title: LZ00 compression/encryption

Hello, I need some help with figuring out this compression format. The data appears to be using an LZ based compression format with encryption.

Here is what the header looks like:

```
0x04 - 0x07 - Compressed filesize
0x10 - 0x2F - Filename for decompressed file
0x30 - 0x33 - Decompressed filesize
0x34 - 0x37 - Date that file was compressed on
0x40 - Start of compressed data
```


The date appears to be the encryption key or part of it, because similar files with the same date share some similar bytes in the file:
[http://www.puyonexus.net/files/resource ... TAFF01.mrz](http://www.puyonexus.net/files/resources/ppf2/data/psp/Menu/09_STAFF01.mrz)
[http://www.puyonexus.net/files/resource ... TAFF02.mrz](http://www.puyonexus.net/files/resources/ppf2/data/psp/Menu/09_STAFF02.mrz)
[http://www.puyonexus.net/files/resource ... TAFF03.mrz](http://www.puyonexus.net/files/resources/ppf2/data/psp/Menu/09_STAFF03.mrz)

when the date is different; the data is completely different:
[http://www.puyonexus.net/files/resource ... TAFF04.mrz](http://www.puyonexus.net/files/resources/ppf2/data/psp/Menu/09_STAFF04.mrz)

Also, here is the only [compressed](http://www.puyonexus.net/files/misc/01_00TITLE.mrz) and [uncompressed](http://www.puyonexus.net/files/misc/01_00TITLE.mrg) file pair I could find in the game.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-25T16:20:17+00:00
- Post Title: LZ00 compression/encryption

this tool can extract those decompressed archives.
[http://forums.sonicretro.org/index.php? ... 12158&st=0](http://forums.sonicretro.org/index.php?showtopic=12158&st=0)
it may also be able to extract the compressed ones.
is this from puyo games?
## Post #3
- Username: Nick W
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 25, 2009 10:04 pm
- Post datetime: 2009-05-25T16:23:24+00:00
- Post Title: LZ00 compression/encryption

> Reply from chrrox
>
> this tool can extract those decompressed archives.
http://forums.sonicretro.org/index.php? ... 12158&st=0
it may also be able to extract the compressed ones.
is this from puyo games?

That actually is my tool, so I can safely say it doesn't work with this compression format. And yes, it is from the Puyo games, Puyo Puyo Fever 2 to be exact.
