## Post #1
- Username: taezou
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 26, 2013 4:21 am
- Post datetime: 2013-09-27T03:15:18+00:00
- Post Title: Sen no Kiseki (PS3) .dat file compression

Earlier today, I posted a [thread](http://forum.xentax.com/viewtopic.php?f=10&t=10808) in the game archive discussion forum about trying to figure out the archive file format for this game. After a lot of tinkering and experimentation (I'm pretty new at this), I managed to figure it out. Unfortunately, the resulting files are definitely lightly compressed. The original archive's header contains two file sizes for each file, one for the compressed file contained in the archive, and one for the uncompressed file. When viewing the files in a hex editor with Shift-JIS support, it's easy to see that certain characters are missing in some strings. These files contain the game's script/event data.

Here's the beginning of one such file.

[](http://imgur.com/uqgNJaJ)

Here's an example of missing characters (highlighted)

[](http://imgur.com/5ojUCSR)

The compressed size of this file is 28382 bytes, and according to the .pkg it was stored in, the uncompressed file is 39439 bytes. I just have no idea what kind of compression method is being used.
If any additional information or data is necessary, I'll be happy to oblige.
## Post #2
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-27T05:10:20+00:00
- Post Title: Sen no Kiseki (PS3) .dat file compression

Hi. Since I'm not a programmer, I can't help you but..
Are those archive files different from ao no kikeki or zero no kiseki..?
What does missing character mean..? I can't understand.

You mean the character code, like #00xxF(ロイド・バニングス)..?
## Post #3
- Username: taezou
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 26, 2013 4:21 am
- Post datetime: 2013-09-27T14:43:20+00:00
- Post Title: Sen no Kiseki (PS3) .dat file compression

The file format looks like it may be similar to Zero/Ao once decompressed, but I need to figure out the compression first.

As for missing characters, in that case, what's missing is "した。" if I recall correctly, although I'd have to check again when I get home.
## Post #4
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-27T14:50:40+00:00
- Post Title: Sen no Kiseki (PS3) .dat file compression

> Reply from taezou
>
> The file format looks like it may be similar to Zero/Ao once decompressed, but I need to figure out the compression first.

As for missing characters, in that case, what's missing is "した。" if I recall correctly, although I'd have to check again when I get home.

Hmm.. I see..
That problems also occur in another files. (magic.tbl or book00.dat., etc)
For example, there are so many missing arts name in magic.tbl.
