## Post #1
- Username: TheLittleElf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 06, 2011 1:18 am
- Post datetime: 2013-06-30T17:24:05+00:00
- Post Title: Harry Potter and the Goblet of Fire *.str files

Hi there,

I have a PC game titled "Harry Potter and the Goblet of Fire". I have extracted the data.big file with GameExtractor, but in this archive there are more smaller archives with *.str extension. Can somebody write a BMS script for it? Thanks!

There are some examples:

[http://www.filedropper.com/59969448-377 ... 9c9cc2115b](http://www.filedropper.com/59969448-377d-4a43-acd2-069c9cc2115b)
[http://www.filedropper.com/27fe46ae-02b ... d797c44c9e](http://www.filedropper.com/27fe46ae-02bd-4363-bda0-cbd797c44c9e)
[http://www.filedropper.com/2c4dca3c-9a4 ... dfa119d99b](http://www.filedropper.com/2c4dca3c-9a49-41e8-a5c0-35dfa119d99b)

Some stuff I've found:

First and the third group of four bytes are the same in each file.
Second four bytes are a dword value indicates the size in bytes after the 16th byte in the file.
After a filename ending with *.dir there is a small description or whatever.
Filenames ending with *.end can be found at the end of the file.

Can somebody help me? Thanks in advance!
