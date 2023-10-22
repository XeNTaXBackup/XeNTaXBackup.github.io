## Post #1
- Username: plgkm6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 29, 2015 11:23 am
- Post datetime: 2016-01-01T13:35:17+00:00
- Post Title: 300 Heroes .x file analysis ？

First 84 bytes are mean meaningless -- file header, some chinese and URLs.
And the 4 bytes is a integer and it represents the size of the selected part of the image below.



无标题.png (44.05 KiB) Viewed 91 times


Then it is followed by 4 integers, respectively, the size of file1-unzip, the size of file2-unzip, the size of file1-zip and the size of file2-zip.
(They can be extracted by the offzip tool.)
Last is the 2 files which start with 78 9C.
