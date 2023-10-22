## Post #1
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2006-10-30T13:57:20+00:00
- Post Title: some basic questions

hi,

I have some general questions regarding to picture formats.

There is a lot of custom types of picture files, what I noticed is when somebody makes viewer, these files are converted in either memory or disk to bmp files. Is this really necessary? Does windows platform natively only support bmp format and everything other has to be converted into one?

I understand that at some point file has to be mapped/uncompressed into memory in some understandable format but what is this format?
Is it .bmp? or .raw?
## Post #2
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2006-11-01T03:29:50+00:00
- Post Title: some basic questions

When I code, a .bmp file is easy to stick into a picture box for display.  What needs to be determined in a graphics format is the the bit size, width, height, palette(if it has one), alpha format(if it has one), and orientation.  I don't believe that windows supports bmp with alpha so I usually convert to .dds format when exporting using a secondary dll.  TGA is also another viable format for export and import conversion.
## Post #3
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2006-11-01T09:25:01+00:00
- Post Title: some basic questions

I know but I was asking more specific about what you called "picture box".
Is't some kind of memory? I remember in old turbo pascal it was memory location which took care about displaying but how is it in winodws and what about non-standart custom game picture formats? How to display them? They just have to be somehow rearranged in memory to some common format in order for "picture box" to display them.
