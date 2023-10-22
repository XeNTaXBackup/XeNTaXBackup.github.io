## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-19T06:24:43+00:00
- Post Title: Writing a re-packer

I've been thinking about how to write a repacker but my design seems really inefficient.
I know the file table structure and the data is just compressed with zlib, so I was thinking of something like

-create stream for file table
-create stream for data
-for each file (recurse through folders), open the file, read it all in and compress it.
-write the file entry. filename/path is easy, size and compsize are easy. Offset is the size of the data stream.
-copy the compressed stream to the data stream
-repeat for all files

And then finally create a new file and write the table and data into it and there's my archive.

What's a different way to do it?
