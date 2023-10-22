## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-22T00:28:02+00:00
- Post Title: Gameloft CustomPak Extractor

For housekeeping, this will be the official page for this tool, instead of spreading it across posts on a research thread.

[Download at the tools blog.](http://forum.xentax.com/blog/?p=1085) Source code included.

This program is for extracting files from Gameloft games utilizing their Glitch game engine. This archive format has been used in the N.O.V.A., Asphalt, Modern Combat series, and various other games. This program is capable of extracting from both little and big endian versions of the archive, and can decrypt encrypted files and file names.

Usage:
Drag and drop your .gla file on to the extractor. It will extract files to a folder with the pak's name and "_extracted" appended to it. If extraction fails, check the following:
the endianess of the file. Open the file in a hex editor, and look across the first 4 ints (16 bytes). If null bytes comes at the front, the file is big endian. Otherwise, it is little endian. For little endian files, give the extractor argument "/l" on the command line in addition to your pak path.
whether or not file names are encrypted. In older Glitch games, file names are not encrypted. If you go to the offset indicated by the third int, you will see the file name table. If it's in ASCII, specify "/n" on the command line.
whether or not the directory is writable. It usually isn't a problem, but please check.

About GameloftDecryption:
It contains the implementation for ENCODE_XOR32 and DECODE_XOR32 functions. The compiled DLL must be present in the extractor's directory for the extractor to work. (If your pak's file names are not encrypted and there are no encrypted files in the pak, then this DLL do not necessarily need to be present. But that situation is quite rare.) I have not tried compiling this in 64-bits, so there's no guarantee on portability. (But it will work on a 64-bit system when compiled as 32-bits.)

Other notes:
The format is single level, meaning there are no sub-directories. The first int is unknown in its purpose, but as far as I can tell it's not actually being used in the games. Also, file extensions may be missing a few letters. That is not a bug in the extractor; it was packed like that. The source code for the extractor is not in my usual style, since I was trying to make an equivalent implementation to CCustomPakReader found in Gameloft's code. It's not identical, but you'll find that the public methods exposed in Gameloft's code are implemented and should work the same.

New discoveries:
There is now a version of the CustomPak that supports DEFLATE compression, along with a changed encryption key.

Version history
[1.0.2.0 2014-07-23]
Added decompression support
Added support for new encryption key
[1.0.1.0 2013-09-19]
Added "unencrypted file names" option
Added "little endian" option
[1.0 2012-10-24]
Initial release
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-23T17:09:38+00:00
- Post Title: Gameloft CustomPak Extractor

A GUI version of the program is available on the [tools blog](http://forum.xentax.com/blog/?p=1061).
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-07-23T15:41:47+00:00
- Post Title: Gameloft CustomPak Extractor

The program has been updated to have decompression support, and I added a new encryption key.
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-07-23T18:38:25+00:00
- Post Title: Gameloft CustomPak Extractor

GUI also updated check the blog
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-05T11:49:42+00:00
- Post Title: Gameloft CustomPak Extractor

Hello GMMan! Recently, I was trying to extract new Gameloft game - Modern Combat 5: Blackout with your tool, but this game appears to be using new version of .gla archives - .gla2. Could you take a look? 
Here's sample .gla2
[https://www.sendspace.com/file/x4zp72](https://www.sendspace.com/file/x4zp72)
Thanks in advance!
