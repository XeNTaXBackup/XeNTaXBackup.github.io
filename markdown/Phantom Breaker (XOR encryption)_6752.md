## Post #1
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-06-08T14:08:34+00:00
- Post Title: Phantom Breaker (XOR encryption)

I recently began looking at files from Phantom Breaker hoping that I'd be able to get sprites quickly but was disappointed when I was confronted with a whole load of gibberish when I opened the file.  But after some examination with GGD I noticed that the data seemed to fall into patterns anyway, and large portions of data were identical between all the files.  I found that selecting parts of the file that repeated and using it as an XOR key allowed me to decrypt parts of the file into something that made sense, however the key changes depending on where in the file I am.  The key itself (aside from the one used to decrypt the header) appears to be procedurally generated.  Theoretically I could brute force the key for every part of the file but I don't think I want to spend that kind of time   
Any help or advice on this matter is appreciated.  The files themselves are quite large, it seems kinda foolish to only upload parts so I uploaded some in full on my website.  key.bin is the key I am using to decrypt the first parts of each file.

[http://www.justnopoint.com/lbends/Phantom_Breaker/](http://www.justnopoint.com/lbends/Phantom_Breaker/)
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-06-08T14:20:36+00:00
- Post Title: Phantom Breaker (XOR encryption)

the key just add 0x06 to the previous char...
ex:
first bytes of the key you uploaded:

79 7F 85 8B 91 97 9D A3 A9 AF B5 BB C1 C7 CD D3

0x79+0x06=0x7F +0x06=0x85 +0x06=0x8B and so on

when the sum is > 0xFF it just subtracts  0x100. Assuming it always starts from 0x79 do your algo

hope this helps
## Post #3
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-06-08T17:59:17+00:00
- Post Title: Phantom Breaker (XOR encryption)

Well that certainly eliminates the need for that key file, but as I mentioned in my first post the key changes radically after a certain point.  In fact, if I read the first four bytes of the file as an integer I get the position in the file that a new pattern starts (* -1).  Maybe the first part of the file is a clue to decrypt the rest of the file?  It looks like some sort of table.
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-06-08T18:27:07+00:00
- Post Title: Phantom Breaker (XOR encryption)

mmm what if that second part is NOT encrypted? can you upload some smaller files?
## Post #5
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-06-08T18:30:38+00:00
- Post Title: Phantom Breaker (XOR encryption)

Uploaded the two smallest ones, smsys and st000
## Post #6
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2012-02-08T13:04:57+00:00
- Post Title: Phantom Breaker (XOR encryption)

Finally getting back to this, after using the cipher on the file header I've determined (mostly) the header table to be as such:

1 byte  Unknown
3 byte  Signature
4*n bytes  Sub Table Offsets (values of FFFFFFFF are ignored, stop at a value less than -1 or greater than the header size)
>     2 bytes  Number of files
>     N bytes  Binary map of valid files   ceil(num files / 8 )
->           4 bytes  File Offset
->           4 bytes  File Size

After separating the files I can analyze them one by one, and I've managed to figure out how they are encrypted.  There's one slight problem though, the scheme changes from file to file.

Explanation:
The cipher is just a repeating cycle of 256 bytes, which can be described by a repeating sequence of the 4 low bits and the 4 high bits.  The low bits change every 2 bytes, and the high bits change every 32 bytes.  Below are my observations of each file in the bsys archive.  Left is the table of low bits (with high bit attached), right is the high bit sequence.

File	Low			High
0	02 02 00 00 06 06 04 04	(0 2 4 6 8 a c e)   
1	1c 1c 1e 1e 18 18 1a 1a	(1 3 5 7 9 b d f)
2	18 18 1a 1a 1c 1c 1e 1e	(1 3 5 7 9 b d f)
3	55 55 57 57 51 51 53 53	(5 7 1 3 d f 9 b)
4	1e 1e 1c 1c 1a 1a 18 18	(1 3 5 7 9 b d f)
5	4d 4d 4f 4f 49 49 4b 4b 	(4 6 0 2 c e 8 a)
6	26 26 24 24 22 22 20 20	??
7	58 58 5a 5a 5c 5c 5e 5e	(5 7 1 3 d f 9 b)
8	0a 0a 08 08 0e 0e 0c 0c	(0 2 4 6 8 a c e)

And analysis for the se archive
0	02 02 00 00 06 06 04 04	(0 2 4 6 8 a c e)   
1	19 19 1b 1b 1d 1d 1f 1f 	(1 3 5 7 9 b d f)
2	26 26 24 24 22 22 20 20	(2 0 6 4 a 8 e c)
3	29 29 2b 2b 2d 2d 2f 2f        (2 0 6 4 a 8 e c)
4	28 28 2a 2a 2c 2c 2e 2e (2 0 6 4 a 8 e c)
5	7b 7b 79 79 7f 7f 7d 7d  (7 5 3 1 f d b 9)
6	7a 7a 78 78 7e 7e 7c 7c  (7 5 3 1 f d b 9)
7	8f 8f 8d 8d 8b 8b 89 89  (8 a c e 0 2 4 6)
8	44 44 46 46 40 40 42 42  (4 6 0 2 c e 8 a)
... others

As you can see, it is not dependent on file number, which leaves us with a few options
- The archive header
- File sizes
- File offsets
So let's tabulate these

Size	Hex	Offset
8323098	7F001A	00000000
2425062	2500E6	007F001A
1379478 150C96	00A40100
3492674	354B42	00B90D96
480710	0755C6	00EE58D8
467466	07220A	00F5AE9E
7436438	717896	00FCD0A8
6357958	6103C6	016E493E
1019986	0F9052	01CF4D04

And once more for se

147478	024016	00000000
133534	02099E	00024016
134606	020DCE	000449B4
139438	0220AE	00065782
117454	01CACE	00087830
132462	02056E	000A42FE
132998	020786	000C486C
141046	0226F6	000E4FF2
143726	02316E	001076E8

As you can see the file sizes for the first file in both archives are radically different, but share the same pattern.  This leaves us with the file offsets and the header table itself.  Unfortunately, looking at the first file of smbgm quickly destroys the possibility of the file offset dependency.

0 0 2 2 4 4 6 6 (5 7 1 3 d f 9 b)

grp

e e c c a a 8 8 (0 2 4 6 8 a c e)


It's easy to check my results because the files in bsys and se have RIFF headers.
[http://www.justnopoint.com/lbends/junk/bsys_007_d.wav](http://www.justnopoint.com/lbends/junk/bsys_007_d.wav)
## Post #7
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2012-02-11T03:13:16+00:00
- Post Title: Phantom Breaker (XOR encryption)

Just an update, I've condensed my cipher into a nice couple of lines of code

```
{
	int key = 0x1c; //Whatever the XOR for the first byte is
	key = key ^ (((n/2)%4)<<1) ^ (((n/32)%8)<<5);
	input.position(n);
	output.position(n);
	output.put(n, (byte) (input.get()^key));
}
```


The problem now is determining what the key is supposed to start at.
## Post #8
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2012-11-30T07:38:39+00:00
- Post Title: Phantom Breaker (XOR encryption)

Finally revisiting this after a long break with other projects.
I've managed to create this table for a packfile which contains all RIFF files.

[http://www.justnopoint.com/lbends/junk/analysis.txt](http://www.justnopoint.com/lbends/junk/analysis.txt)
In order -  File#  XOR key Offset  Filesize

It seems very likely the the key is derived from the file number and filesize.  Whether or not the file number is odd has a direct correlation with whether the key is odd.  Sometimes a file has size 0, I have omitted these.
