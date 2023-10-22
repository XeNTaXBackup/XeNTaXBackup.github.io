## Post #1
- Username: Abyssinian
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 19, 2013 9:10 am
- Post datetime: 2014-02-28T22:31:31+00:00
- Post Title: Oil Rush's mesh files

Hey guys,

I was wondering if someone knew how to convert Oil Rush's .mesh file to a format that could be imported into 3ds max? I've attached two of them to this post.

Thanks in advance!
[Mesh files.rar](https://xentaxbackup.github.io/file/7055_Mesh files.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-01T12:10:07+00:00
- Post Title: Oil Rush's mesh files

[](http://www.pic-upload.de/view-22415690/wooden_temple.jpg.html)

not sure about UVs. So you'll have to fiddle around for yourself.
(You could try 0x54DB as a start address for the UVs block.
The DWORD before 0x33A= 826 is the count)

h2o file:
0x6EAF 1500
Vb1
18 99
0xEF 826
020000
0x3B07 8
## Post #3
- Username: Abyssinian
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 19, 2013 9:10 am
- Post datetime: 2014-03-03T01:57:16+00:00
- Post Title: Oil Rush's mesh files

Thanks for your anwser but that makes no sense to me  Could you please explain it for me?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-03T11:23:58+00:00
- Post Title: Oil Rush's mesh files

read "extracting simple models" from my sig
