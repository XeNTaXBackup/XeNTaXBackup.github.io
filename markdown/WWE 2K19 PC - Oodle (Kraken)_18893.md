## Post #1
- Username: doppler
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 10, 2012 2:48 am
- Post datetime: 2018-10-05T12:47:45+00:00
- Post Title: WWE 2K19 PC - Oodle (Kraken)

Hello,

WWE2K have switched from using zlib to Oodle. We've been toying around with trying to decompress it, but for whatever reason OodleLZ_Decompress just seems to fail. Here's what we know so far.

- Offset 10: 4 bytes are the uncompressed file size
- Offset 14:  4 bytes are the compressed file size minus the header size from that point (18 bytes or 24 dec). 

Quick note. The next 2 bytes (8C 06) following the file sizes are consistent between all files.

Having both those numbers should be enough for Oodle decompress to actually decompress right? For reason when I run OodleLZ_Decompress with those parameters the output buffer returns empty. Is there something else to the decompression here?

Would appreciate any help. 

Thanks.

Here are sample files. WWE 2K19 also uses oo2core_6_win64.dll version of the decompression.
[http://www.mediafire.com/file/f224da6ol ... s.rar/file](http://www.mediafire.com/file/f224da6oln9ipp2/Oodle_Sample_Files.rar/file)
