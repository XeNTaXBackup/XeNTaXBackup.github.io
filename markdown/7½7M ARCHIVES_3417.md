## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-04T12:30:50+00:00
- Post Title: 7½7M ARCHIVES

There are numerous games utelizing an archive format starting with a 4 byte signature '7½7M'. I have uploaded a small archive from "Amelies Cafe". On request, I can provide a list of games utelizing same.

A sample 7½7M-archive can be downloaded from one of our websites: [http://motionpress.com/7_7M/7_7M.rar](http://motionpress.com/7_7M/7_7M.rar)

I will appreciate al help to unpack these archive formats (Trid returns an unknown format - in fact, all unpackers don't recognize it)

Regards

Hendrik Pretorius
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-04T13:54:00+00:00
- Post Title: 7½7M ARCHIVES

it is just xored with F7 Here is an un xored file.
once you xor the file with f7 you can use any generic file ripper.
[](http://xs.to/xs.php?h=xs138&d=09146&f=jpeg__4754193_xxxx599.jpg)
[jpeg_ 51_xxxx.rar](https://xentaxbackup.github.io/file/1953_jpeg_ 51_xxxx.rar)
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-04T13:59:57+00:00
- Post Title: 7½7M ARCHIVES

first XOR the entire file with the byte 0xf7

the first 4 bytes are the signature 0xc0 0x4a 0xc0 0xba
go at offset 9 and start the loop:
- 1 byte: length of the filename (n)
- n bytes: the filename
- 4 bytes: the size of the file
- 8 bytes: skip them
- 1 byte: 0x00 if there are other files, 0x80 if the list of files is terminated

the offsets of the files are all relative to the end of the list of files (the previous byte 0x80) and obviously are incremented with the size of the files.
so the offset of the first file in loc.pak is 0x819, the second is at offset 0x13c23 (0x819 + 0x1340a) and so on.
## Post #4
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2009-04-04T14:21:56+00:00
- Post Title: 7½7M ARCHIVES

yes,just a simple XOR
## Post #5
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-04T21:49:05+00:00
- Post Title: 7½7M ARCHIVES

Is there a software tool to XOR a file? 
CryptIt 1.4 has a XOR-decrypt function, but you XOR it with a key-file?
Can I XOR a file in "010 Editor", or is there any other software I can use?

Thanks

Hendrik
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-04T21:56:52+00:00
- Post Title: 7½7M ARCHIVES

This program is easy to use and does not seem to expire.
[http://www.acapsoft.com/det.php?prog=XorIt](http://www.acapsoft.com/det.php?prog=XorIt)
just use a hex editor to create the key file and save it as anything then just choose the source file and the xor file you made and your done.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-05T10:45:42+00:00
- Post Title: 7½7M ARCHIVES

if needed I have a command-line tool which makes just the xor job: [http://aluigi.org/mytoolz/xor.zip](http://aluigi.org/mytoolz/xor.zip)

xor loc.pak new_loc.pak 0xf7
## Post #8
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-05T17:56:37+00:00
- Post Title: 7½7M ARCHIVES

Thank you Bugtest (chrrox and others above). I just have one additional question:

The author of XorIt ([http://www.acapsoft.com/det.php?prog=XorIt](http://www.acapsoft.com/det.php?prog=XorIt)) notes the following with regards to XOR:

"I"t is extremely important to note that the file is Encrypted, not password locked. The difference being that there is no storing of the code itself anywhere - the whole file is mathematically scrambled based on the file you select. If you forget/lose the Cryption File there is no way at all to decrypt the file. (I.e. We cannot help!)"

Chrrox on the other hand determined above that my provided sample file "is just xored with F7". How do you determine the byte 0xf7 if the author of XotIt says that you need the Crypton File to decrypt it?

Regards

Hendrik Pretorius
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-05T19:21:57+00:00
- Post Title: 7½7M ARCHIVES

You normally debug the program that is accessing the encrypted data and find where in that program the encrypted key file is located and then you are all set.
In this case the encryption was so weak I could tell just by looking at the file it was xored with 0xF7 because the file contained no special compression like zlib and everywhere that a 0 would normally be was replaced with F7 and when you xor 0 and F7 you get F7 so that was the encryption key.
