## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-07-27T07:47:58+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

Hi. I'm trying to extract the textures from this file. Information gained from another thread in this forum, tells me that it is compressed using bpe. can somebody help me uncompress this archive. I can post the file if needed.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-27T07:54:32+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

> Reply from plodtrew
>
> Hi. I'm trying to extract the textures from this file. Information gained from another thread in this forum, tells me that it is compressed using bpe. can somebody help me uncompress this archive. I can post the file if needed.

Please do post a file, that makes life a little easier for investigators
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-07-27T08:15:36+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-27T08:24:00+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

Yeah , that should do.
## Post #5
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-07-27T11:23:25+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

Thanks for your help. I've been trying to extract these texures ofr months with no success. I've managed to get some of the textures but they seem to be the textures from the create a wrestler mode and not of the in game superstars. 

This is what I do, maybe it'll help in uncompressing the archive:

1. Make an image of the game on your cpu
2. Open the CH.PAC file. using AFS Explorer v.3.7. Click file - import AFS file from CD image. Just say yes to all the warnings that appear.
3. Scroll to the bottom of the file list until you come across the files called blank_255 onwards. 
4. right click on these files and click on extract. 
5. Rename the extracted files to have a "tm2" extension.
6. Open the tm2 file with game graphics studio and click on scan for graphic files. 
7. The bigger tm2 files (around 100mb) should have about 3000 graphic files,you can extract these.

I have no idea how to put these into the game or wether they are used at all in the game. These textures seem to be repeated in few files.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-27T12:49:45+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

Hmm, BPE stands for Byte Pair Encoding.. Perhaps others have alread dealt with this type of compression before?
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-07-31T05:33:37+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

I've manage to extract the ch.pac file with rrunpack. i can also view the contents of the ch file with game extractor. It seems to have the same directory structure as the previous games but all the files have a bpe extension. Is seems all the textures and models are compressed in this manner.
## Post #8
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-07-31T07:11:42+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

Here's some info & source on BPE: [http://www.csse.monash.edu.au/cluster/R ... oblem.html](http://www.csse.monash.edu.au/cluster/RJK/Compress/problem.html)
## Post #9
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-07-31T09:06:03+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-08-01T06:22:12+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

[viewtopic.php?t=2318&start=15](http://forum.xentax.com/viewtopic.php?t=2318&start=15)

That was as far as I got. The decompressor messes up for an unknown reason but the initial chunk was decompressed.

In the second picture testa is the compresed source and testb is the data ran through the decompressor.
## Post #11
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-08-06T05:32:08+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

> Reply from Silver
>
> viewtopic.php?t=2318&start=15

That was as far as I got. The decompressor messes up for an unknown reason but the initial chunk was decompressed.

In the second picture testa is the compresed source and testb is the data ran through the decompressor.

I've searched the web and thats the only bpe decompressor I could find also. It also crashes for me. do you think a different compression algorythm was used in these files?
## Post #12
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-08-06T20:41:23+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

> Reply from plodtrew
>
> Silver wrote:viewtopic.php?t=2318&start=15

That was as far as I got. The decompressor messes up for an unknown reason but the initial chunk was decompressed.

In the second picture testa is the compresed source and testb is the data ran through the decompressor.

I've searched the web and thats the only bpe decompressor I could find also. It also crashes for me. do you think a different compression algorythm was used in these files?

It does not crash for me. I got it to extract in blocks but after so many bytes it seemed to "mess up". It is more than likely crashing because the source is not correct. In my post I'm extracting from +16 Bytes from the BPE header.
## Post #13
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-08-07T09:05:54+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

> Reply from Silver
>
> plodtrew wrote:Silver wrote:viewtopic.php?t=2318&start=15

That was as far as I got. The decompressor messes up for an unknown reason but the initial chunk was decompressed.

In the second picture testa is the compresed source and testb is the data ran through the decompressor.

I've searched the web and thats the only bpe decompressor I could find also. It also crashes for me. do you think a different compression algorythm was used in these files?

It does not crash for me. I got it to extract in blocks but after so many bytes it seemed to "mess up". It is more than likely crashing because the source is not correct. In my post I'm extracting from +16 Bytes from the BPE header.

I see what you mean. I knocked 16 bytes from the header and it extracts part of the file. It extracts a few textures correctly then crashes. same with the yobj model files.
## Post #14
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-08-16T05:37:55+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-11-20T06:21:42+00:00
- Post Title: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

I've been told that a save state from pcsx2 the playstation emulator, should contain uncompressed versions of the bpe files. The problem is that I dont know how to identify the files in the savestate file. If i post it will somebody be able to help find the files?
## Post #16
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-14T11:21:43+00:00
- Post Title: Re: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

After two years, I've made some progress. Thanks to the info from chrrox in the sf4 thread, I've managed to use 3d ripper tp grab some of the textures. I still havent had any luck with the models though as I cant make any sense of the model files dumped by 3d ripper.

The colour of the dds files are wierd though, anybody have any ideas on why:
[eef4d8ca.jpg](https://xentaxbackup.github.io/file/2190_eef4d8ca.jpg)
## Post #17
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2009-09-02T20:12:59+00:00
- Post Title: Re: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

Byte Pair Encoding?

Byte pair encoding (BPE) is a simple universal text compression scheme. Decompression is very fast and requires small work space. Moreover, it is easy to decompress an arbitrary part of the original text. However, it has not been so popular since the compression is rather slow and the compression ratio is not as good as other methods such as Lempel-Ziv type compression. In this paper, we bring out a potential advantage of BPE compression. We show that it is very suitable from a practical view point of compressed pattern matching, where the goal is to find a pattern directly in compressed text without decompressing it explicitly. We compare running times to find a pattern in (1) BPE compressed files, (2) Lempel-Ziv-Welch compressed files, and (3) original text files, in various situations. Experimental results show that pattern matching in BPE compressed text is even faster than matching in the original text. Thus the BPE compression reduces not only the disk space but also the searchin...
## Post #18
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-10-07T09:28:48+00:00
- Post Title: Re: Smackdown vs Raw 2007 pac files - Byte Pair Encoding

I have previously looked at the article posted about bpe but it doesnt uncompress the smackdown files.
