## Post #1
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2010-10-27T02:17:29+00:00
- Post Title: Zlib help

Recently I have been trying to modify some files that are compressed with zlib. They were originally compressed with zlib 1.2.3 using Z_SYNC_FLUSH. I can decompress the original files just fine. But if I try to rebuild the files, and decompress my rebuilt ones, it fails part way through with the error of "invalid stored block lengths". I have tried with both zlib 1.2.3 and 1.2.5. It seems to happen no matter how big the file is. I've created a small test project in Visual C++ 2008, included is the source code for the project which will generate a test file, compress it, and try to decompress it. You may have to relink the header/library search paths in the project, but I have included all needed headers/libs in the zlib folder. Dont forget to change the file paths the project uses. By default it uses C:\test\ for storing the test files. Any help is much appreciated, I have been messing with this for days and can not get it to work.
[Download](http://www.thefallen93.com/Files/FastCryptZlib.rar)
## Post #2
- Username: shakotay
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 29, 2010 5:43 am
- Post datetime: 2010-11-09T01:47:37+00:00
- Post Title: Zlib help

The streams_0_decompressed.bin is shorter than the streams_0_test.bin by 16896 bytes.

(edit: 0x4200 is the remainder if you devide the filesize 0x1C9C200 by 0x8000.)

Compresssing ends up with result = deflateEnd() = 0xfffffffd -> Z_DATA_ERROR.

To debug deflatedEnd() you should include zlib sources to your project. 

I'm just too lazy now to do this... (because it's time to sleep in good old europe;-)
