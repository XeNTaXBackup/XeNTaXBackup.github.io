## Post #1
- Username: mix
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 16, 2008 2:14 am
- Post datetime: 2015-11-07T10:34:35+00:00
- Post Title: Call of Duty: Black Ops 3 FD inner compression

Hello,

in CoDBO3 there are FD files which are not encrypted, and I assume they would contain localization files. After signature, there's ZLIB compressed data. After decompressing, there seems to be yet another compression method used. It's possibly something dictionary based. Thanks for any collaboration.

Pictures of the inner compression:


Link to ZLIB decompressed blocks: [https://www.sendspace.com/file/ntktcg](https://www.sendspace.com/file/ntktcg)
## Post #2
- Username: RedEyeX32
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 22, 2014 4:38 am
- Post datetime: 2015-11-08T17:24:43+00:00
- Post Title: Call of Duty: Black Ops 3 FD inner compression

> Reply from mix
>
> Hello,

in CoDBO3 there are FD files which are not encrypted, and I assume they would contain localization files. After signature, there's ZLIB compressed data. After decompressing, there seems to be yet another compression method used. It's possibly something dictionary based. Thanks for any collaboration.

Pictures of the inner compression:


Link to ZLIB decompressed blocks: https://www.sendspace.com/file/ntktcg

They are using LZO1X as the other layer of compression.
## Post #3
- Username: mix
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 16, 2008 2:14 am
- Post datetime: 2015-11-09T11:50:08+00:00
- Post Title: Call of Duty: Black Ops 3 FD inner compression

Could you provide some more detail? How did you determine lzo1x? I tried lzo1x_decompress from minilzo and couldn't make it work. At which offset does the lzo compressed block start (I assume at least first 4 bytes to be a header)?
## Post #4
- Username: RedEyeX32
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 22, 2014 4:38 am
- Post datetime: 2015-11-09T14:47:07+00:00
- Post Title: Call of Duty: Black Ops 3 FD inner compression

> Reply from mix
>
> Could you provide some more detail? How did you determine lzo1x? I tried lzo1x_decompress from minilzo and couldn't make it work. At which offset does the lzo compressed block start (I assume at least first 4 bytes to be a header)?

Data seems to start at offset 0x04, I will try later today.
Seems like it is some other kind of LZ variant.
## Post #5
- Username: mix
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 16, 2008 2:14 am
- Post datetime: 2015-11-10T09:28:14+00:00
- Post Title: Call of Duty: Black Ops 3 FD inner compression

So any ideas a about the compression type?
