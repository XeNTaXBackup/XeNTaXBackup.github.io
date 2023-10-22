## Post #1
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-02-09T12:47:17+00:00
- Post Title: Sherlock Holmes: The Case of the Silver Earring - Texts

Is there a way to edit the texts in Sherlock Holmes: The Case of the Silver Earring? They have no extension  
[Files.rar](https://xentaxbackup.github.io/file/6180_Files.rar)
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-02-12T12:58:13+00:00
- Post Title: Sherlock Holmes: The Case of the Silver Earring - Texts

Have you tried to edit it by hand (hexeditor or anything else that supports unicode)? Maybe the game recognises text lengths etc. by controlcodes and you don't have to care about pointers. Just don't overwrite the end of a text but expand it (Inst key).
## Post #3
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-02-13T15:06:30+00:00
- Post Title: Sherlock Holmes: The Case of the Silver Earring - Texts

Try this tool: [http://www.sendspace.com/file/6a8b75](http://www.sendspace.com/file/6a8b75)
## Post #4
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-02-14T15:22:14+00:00
- Post Title: Sherlock Holmes: The Case of the Silver Earring - Texts

> Reply from swuforce
>
> Try this tool: http://www.sendspace.com/file/6a8b75

It's perfect. Thank you.

EDIT: Tools working perfectly, Thank you again. I just need one last help with the fonts, Is it possible to edit them? Thank you.
[fonts.rar](https://xentaxbackup.github.io/file/6193_fonts.rar)
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-02-15T08:18:11+00:00
- Post Title: Sherlock Holmes: The Case of the Silver Earring - Texts

There are TGA images at the end of the font files. Here are the offsets:

```
0x900 size of tga (4 byte)
0x904 tga file

Comic
0x5c0 size of tga (4 byte)
0x5c4 tga file
```

[http://s3.postimage.org/kdimxgrpv/fonts.jpg](http://s3.postimage.org/kdimxgrpv/fonts.jpg)
## Post #6
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-02-15T12:23:17+00:00
- Post Title: Sherlock Holmes: The Case of the Silver Earring - Texts

> Reply from Polefish
>
> There are TGA images at the end of the font files. Here are the offsets:
Code: Select allArial
0x900 size of tga (4 byte)
0x904 tga file

Comic
0x5c0 size of tga (4 byte)
0x5c4 tga file
http://s3.postimage.org/kdimxgrpv/fonts.jpg

oh, thank you.
