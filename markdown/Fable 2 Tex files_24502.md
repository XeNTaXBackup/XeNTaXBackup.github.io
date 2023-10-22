## Post #1
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2021-09-18T15:45:52+00:00
- Post Title: Fable 2 Tex files

Right, so I'm trying to make sense of Fable 2's texture files and they seem to be compressed.

The header files are stored in a separate archive bnk, even though the texture files I've seen have a lot, if not all of the header data in them.  Dimensions, crucially, are there in the first 20 or so bytes.

According to this post [viewtopic.php?t=4571#p39375](https://forum.xentax.com/viewtopic.php?t=4571#p39375) the tex files are lzma:192k compressed (although I'm not sure how they found this out as I can't get 7zip to tell me anything.)

Thing is, and I might be trying to do something wrong here, I cannot find a straightforward way to decompress/inflate the texture files so that I can see what they are, using 7zip or any other tool I can find.

Could it be a quirk of the bnk extractor that dumps the texture files without decompressing them?

Any help/input very gratefully received!

Sample file attached: 

 rs_thatched_roof.zip
(187.62 KiB) Downloaded 19 times
## Post #2
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2021-09-27T10:05:31+00:00
- Post Title: Fable 2 Tex files

Turns out they're encrypted as well, at least partially?

Attached .tex header file.

Again, any help or feedback much appreciated!
[rs_thatched_roof_header.zip](https://xentaxbackup.github.io/file/20908_rs_thatched_roof_header.zip)
