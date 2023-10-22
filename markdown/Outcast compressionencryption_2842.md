## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-08T03:20:59+00:00
- Post Title: Outcast compression/encryption

Those files are definitely compressed and most likely encrypted.
Any help appreciated 
[txts.rar](https://xentaxbackup.github.io/file/1389_txts.rar)
## Post #2
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-11-08T06:26:11+00:00
- Post Title: Outcast compression/encryption

All data from Outcast is compressed using the PKWare Data Compression Library. You can find decompression source code on the web.
The first two bytes (0x00 0x06) are the PKDCL header. There are other variations, too, they should be in the decompression code. Could be useful for your detection tool.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-08T20:41:06+00:00
- Post Title: Outcast compression/encryption

Thanks a lot. I already detected the 0x0006 sequence but didn't know it's DCL.
