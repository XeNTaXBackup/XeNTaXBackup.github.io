## Post #1
- Username: HUnterARG
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 22, 2022 4:54 pm
- Post datetime: 2022-03-24T13:48:06+00:00
- Post Title: Ninja Gaiden Sigma (PS3) - sprites

How do I extract this file?

It's from the game Ninja Gaiden Sigma from the PS3 version:

[https://www.mediafire.com/file/3t11zpl2 ... e.zip/file](https://www.mediafire.com/file/3t11zpl2mdkrfgk/file.zip/file)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-24T17:37:48+00:00
- Post Title: Ninja Gaiden Sigma (PS3) - sprites

opt file is probably some kind of index. It contains strings like sprite, texinfo, texture_info etc.
You need to parse it properly to get correct offsets and sizes.

opt (1) file is just raw image data. It has texture_image signature at the beginning.
You can view it with texture finder. [https://imgur.com/a/4WSrQS1](https://imgur.com/a/4WSrQS1)
