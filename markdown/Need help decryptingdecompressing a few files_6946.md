## Post #1
- Username: DStalefish
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 08, 2011 12:26 am
- Post datetime: 2011-07-09T23:37:54+00:00
- Post Title: Need help decrypting/decompressing a few files

Not sure this is the right place to put this, but I've found a few files that I can't make heads or tails of.

I really have no idea what method is used to mask the file contents, so I figured I'd just post them here and see if anybody recognizes anything.  I'm giving two examples of each.  The game they're from is currently in beta.

First up is this guy.  Each extracted archive has exactly one of these, so I'm thinking it might be a reference of some sort, like an encrypted or compressed list of the files in the directory, but I can't see any discernible file structure.  I'm not a big file guy though, so it could be obvious and I'm missing it.

Another thing is that these types of files are always at the same location in the archive I extracted them from (which is why the second example is named differently, had to rename it)

[http://dl.dropbox.com/u/11234409/share/ ... 5A71E6.txt](http://dl.dropbox.com/u/11234409/share/00000000_E4B96113C75A71E6.txt)
[http://dl.dropbox.com/u/11234409/share/ ... 1E6_v2.txt](http://dl.dropbox.com/u/11234409/share/00000000_E4B96113C75A71E6_v2.txt)

Next up is a file that has a pretty consistent file structure.  The first 4 bytes are an address, followed by BNRY, followed by another 4 bytes, followed by LTLE.  At the bottom of the file, 12 bytes from the end is EGCD, followed consistently by 04 00 00 00, and then another 4 bytes at the end (usually just 00s).

[http://dl.dropbox.com/u/11234409/share/ ... 68B88B.csv](http://dl.dropbox.com/u/11234409/share/DEADBEEF_2AD86BA63068B88B.csv)
[http://dl.dropbox.com/u/11234409/share/ ... 7592D9.txt](http://dl.dropbox.com/u/11234409/share/DEADBEEF_1D130BA1AD7592D9.txt)

The next two are very common, or at least the header at the top is in a vast majority of the files in the archive.  They all start with the following 24 bytes:

29 DE 6C C0 BA A4 53 2B 25 F5 B7 A5 F6 66 E2 EE C8 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 07 00 00 00

Followed by 4 bytes that look like a byte address to somewhere else in the file, in this case it's pointing to a string near the bottom.  Some files have human readable text, others don't.

[http://dl.dropbox.com/u/11234409/share/ ... 9615A2.txt](http://dl.dropbox.com/u/11234409/share/DEADBEEF_1BD928EC599615A2.txt)
[http://dl.dropbox.com/u/11234409/share/ ... 00E14F.txt](http://dl.dropbox.com/u/11234409/share/DEADBEEF_1D36D238D600E14F.txt)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-09T23:49:54+00:00
- Post Title: Need help decrypting/decompressing a few files

first state the name of the game if you want help 2nd these look like game resource files not archives.
