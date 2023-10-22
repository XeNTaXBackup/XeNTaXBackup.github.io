## Post #1
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2021-12-31T18:24:35+00:00
- Post Title: Documents about dual UnityFS headers？

Hello everyone！
I found that many games have two UnityFS headers. All data before the second UnityFS header must be deleted to correctly identify the file.
However, many games have a lot of files, and the offset of the second UnityFS header of many files is different. Manual modification is very troublesome. . .
I have a bms script that determines the offset and then deletes it, which is not what I want.
Code:
get ArcName filename
set Name string "new\\"
string Name + ArcName
get Size asize
math Size - 0x04
log Name 0x04 Size


My idea is to determine the offset of the second header through the bms script, and then use math Size-the offset of the second header. I don't know how to write this script.
help me. . .

.

The following samples belong to the same game:


 Desktop.zip
(90.61 KiB) Downloaded 15 times
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-31T22:53:36+00:00
- Post Title: Documents about dual UnityFS headers？

Check this script
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Unity_UnityFS_double_header_script.bms)

It works on all of your samples
