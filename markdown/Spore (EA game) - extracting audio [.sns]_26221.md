## Post #1
- Username: HHYXTRMZ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 11, 2023 8:49 pm
- Post datetime: 2023-01-16T09:56:23+00:00
- Post Title: Spore (EA game) - extracting audio [*.sns]

I'm trying to extract the audio from the spore
first，I get .sns file from package.
but,When I run ealayer3 in cmd, it gives an error:
EA Layer 3 Stream Extractor/Decoder 0.7.0. Copyright (C) 2010-11, Ben Moench.
L: single block loader incorrect because of compression
L: header B loader incorrect because of block type
L: headerless loader correct
Ver. 6 and 7 header: granule size set incorrectly.
P: EAL3 ver. 6 and 7 incorrect with exception: There aren't any granules.
P: EAL3 ver. 5 incorrect with exception: The number of uncompressed samples exceeds the amount of data left.
The EALayer3 parser could not be initialized (the bitstream format is not readable).

here is the sns file[https://drive.google.com/file/d/1DNEVer ... share_link](https://drive.google.com/file/d/1DNEVerRjQCVpBJbpNI4ZBrBU0WyNUR4U/view?usp=share_link)

Can someone please help me? thank you very much！
## Post #2
- Username: willosaurus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 18, 2023 2:01 am
- Post datetime: 2023-02-17T18:05:26+00:00
- Post Title: Spore (EA game) - extracting audio [*.sns]

You should be able to use FFmpeg. Spore uses that. I recommend using FFBatch though.
