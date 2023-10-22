## Post #1
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2007-09-13T13:21:41+00:00
- Post Title: Bioshock unpack. and all of unreal3 engine pack Compression

.blk is very clear with Catalog .bdc file .

i guess unpack file will like gear of war .xxx file.  its ureal 3 engine pack file too.

its also compressed too.  

but like u file. i used LZO decompressed.  not work.

not using LZO or something i wrong?
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2007-09-22T17:24:35+00:00
- Post Title: Bioshock unpack. and all of unreal3 engine pack Compression

The Bioshock .u files, using zlib compression.
The zlib beginning: 789c (hexa)
In the header is maybe the zlib files offset values.
The .u files contained many zlib files. All zlib size is ~34k. If you cut out all zlib files, and decompressed all of them, then with "copy /b..." command you can copy all files into one. That file is the really .u. But you can't edit this file. All viewing text in this .u file used unicode format.

That's all I know about that.
