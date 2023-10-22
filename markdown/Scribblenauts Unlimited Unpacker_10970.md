## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-11-18T23:53:29+00:00
- Post Title: Scribblenauts Unlimited Unpacker

Download: [blog/?p=1108](http://forum.xentax.com/blog/?p=1108)

The program unpacks files from Scribblenauts Unlimited with file names. See Tools Blog page for usage info.

Other notes:
*.p files seem to have 64 bytes of header, the first int being the size of the file and the second int indicating whether or not the file should be resident (i.e. loaded into memory in its entirety). The rest of the header is unused.
I think the "flags" field is actually indication of the compression level (6 for normal Zlib compression). The odd thing is all of the compressed files are actually using fast compression. In any case, the value is only compared against 0.
All files have a trailing byte with the value being the file's compression level. Actual compressed size is one less than the one in the index. Some compressed files seem to have a gap after it in the *.p archive. The gaps are actually unindexed files. They were most likely replaced in another .p file.
Version History:
1.0.3.0 [November 18, 2014]
Now unpacks files from Scribblenauts Unmasked.

1.0.2.0 [November 25, 2013]
pmindex_for_code.xml and 1s will also be searched for file names
Added exception handling for pmindex.xml specifying an invalid index number

1.0.1.0 [November 19, 2013]
Added option to extract *.p files individually
Added and edited disposed check
Better parsing of pmindex.xml
Placeholder replacements are applied only during extraction

1.0.0.0 [November 18, 2013]
Initial release
BinkA2Wav:
I updated the program to be a full command line utility. Please see [blog/?p=1115](http://forum.xentax.com/blog/?p=1115).
## Post #2
- Username: Steven
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 26, 2014 5:42 pm
- Post datetime: 2014-11-13T17:24:54+00:00
- Post Title: Scribblenauts Unlimited Unpacker

Can i pack and unpack BPE
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-11-13T19:48:44+00:00
- Post Title: Scribblenauts Unlimited Unpacker

I dunno. This tool isn't designed to support BPE.
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-11-19T00:19:50+00:00
- Post Title: Scribblenauts Unlimited Unpacker

Unpacker has been updated to work with Scribblenauts Unmasked. [s]I don't have files from Unlimited at the moment, so if it breaks, message me.[/s] Still working fine on Unlimited.
## Post #5
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-11-26T13:48:48+00:00
- Post Title: Scribblenauts Unlimited Unpacker

audio.p wav?
## Post #6
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-11-26T18:21:23+00:00
- Post Title: Scribblenauts Unlimited Unpacker

> Reply from makcar
>
> audio.p wav?
Use BinkA2Wav.
## Post #7
- Username: Qnoops
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Aug 23, 2018 2:15 am
- Post datetime: 2018-10-30T07:22:08+00:00
- Post Title: Scribblenauts Unlimited Unpacker

any news from packing files again?
## Post #8
- Username: mightyloko1199
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 27, 2021 2:10 pm
- Post datetime: 2021-11-28T23:49:36+00:00
- Post Title: Scribblenauts Unlimited Unpacker

The download link says it's forbidden. Got an alt link?
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-29T09:26:32+00:00
- Post Title: Scribblenauts Unlimited Unpacker

> Reply from mightyloko1199 ↑Mon Nov 29, 2021 7:49 am at Mon Nov 29, 2021 7:49 am
>
> 
The download link says it's forbidden. Got an alt link?

Here is the mirror
[https://drive.google.com/file/d/1leQBqw ... sp=sharing](https://drive.google.com/file/d/1leQBqw1JuHTXxWUz3atDxniizjm0IYBb/view?usp=sharing)
