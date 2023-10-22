## Post #1
- Username: skstylez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 20, 2011 8:15 pm
- Post datetime: 2014-11-11T10:19:41+00:00
- Post Title: Recompressing Virtual Pro Wrestling 2 data

Hey there,

I'm working on a translation for Virtual Pro Wrestling 2 for the N64, but I've hit a road block in terms of recompressing a few files. I want to recompress the files so that it can be read by the game. I've used midwaydec to decompress the data which is (I'm assuming) LZSS_0B, according to the file list that came with the tool.

I'm attaching the original unmodified compressed and unmodified decompressed files. Basically I want to recompress the decompressed file so that it's pretty much the same as the original compressed file. Before I start modifying the decompressed data, I want to be sure that when I recompress the file, it should be how it should be, if that makes any sense.

Here's the headers for both files
For the original compressed file below the highlighted part shows the length in hex of the decompressed file.


For the decompressed file, it starts off with pointers to where the data is located. 0400 is the start of the first set of data, 0409 next set and so forth.


Any help is appreciated.

Thanks
[1B4DA6.zip](https://xentaxbackup.github.io/file/8064_1B4DA6.zip)
