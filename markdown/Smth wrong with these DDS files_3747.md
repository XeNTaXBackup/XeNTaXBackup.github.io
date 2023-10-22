## Post #1
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-09-29T00:22:57+00:00
- Post Title: Smth wrong with these DDS files

Hello!  ^_^
I manually ripped a couple of dds files from archive. I'm sure i did it right. I tryed to open them with DirectX Texture Tool and with WTV, but they don't understand the file format. So i guess files are encrypted or somehow compressed.
If anyone has some idea what's wrong with these files, please tell me!
[dds files.rar](https://xentaxbackup.github.io/file/2400_dds files.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-29T13:10:46+00:00
- Post Title: Smth wrong with these DDS files

they are compressed for sure but the algorithm is unknown.
at a first look it seemed lzo but I have tried various offsets (because "DDS" is not compressed) without luck.
same thing for lzw, lzss and blast.
you should check in the executable if there is a reference to the name of the compression algorithm/library
## Post #3
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-09-29T14:08:54+00:00
- Post Title: Smth wrong with these DDS files

Thanks for reply. All in all seems like i have to reverse the game =\ Actually that is what i was afraid off because i don't really know how >_<
*gone to google*
## Post #4
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-13T06:55:07+00:00
- Post Title: Smth wrong with these DDS files

Solved
2 weeks = now i know how to reverse games. Curious. Did'n think it's so easy.
If anyone still interested, compression algorithm posted here:
[viewtopic.php?f=21&t=3774](http://forum.xentax.com/viewtopic.php?f=21&t=3774)
Topic can be closed i think
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-14T19:28:29+00:00
- Post Title: Smth wrong with these DDS files

Very good, Corwin.
