## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-25T23:50:41+00:00
- Post Title: Idolm@ster

Here is a quick bms script for bna files.

```
endian big
get files long
set files2 files
math files2 - 1
savepos ntablestart
for i = 0 < files
goto ntablestart
get folderoff long
get nameoff long
get offset long
get size long
savepos ntablestart
goto folderoff
get folder string
goto nameoff
get name string
if i == files2
string folder + /
endif
string folder + name
log folder offset size
next i

```
