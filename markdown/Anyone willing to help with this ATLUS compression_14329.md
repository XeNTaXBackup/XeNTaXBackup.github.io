## Post #1
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2016-05-12T03:06:30+00:00
- Post Title: Anyone willing to help with this ATLUS compression?

I've been researching PS2-era ATLUS games and noticed an occurrence of this same compression format in a lot of their RPG's (SMT3, DDS, DDS2, DS, DS2). Below I've included a RAR containing an uncompressed file (PAC) and a version of the same exact file - but compressed (LB).

The compression seems relatively poor, as a lot of data is still somewhat readable - though it's still unusable as is. 
From what I can gather of the header so far:

01 01 <= Always seems to be this for all compressed LB archives.
dd dd <= ID of the file in the archive.
xx xx xx xx <= Unsure exactly, looks like a filesize but doesn't seem consistent with compressed or uncompressed size?
yy yy yy yy <= Filetype of the file inside the archive.
zz zz zz zz <= Decompressed size of the file inside the archive.

[https://drive.google.com/file/d/0B5q4Lx ... sp=sharing](https://drive.google.com/file/d/0B5q4LxwS1je2WTY1TDE2SzhORUU/view?usp=sharing)
