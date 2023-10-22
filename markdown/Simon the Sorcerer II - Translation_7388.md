## Post #1
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2011-09-21T11:51:26+00:00
- Post Title: Simon the Sorcerer II - Translation

Hi there.

I have the polish version of Simon the Sorcerer II - unfortunately, there are some mistakes in translation and the polish dubbing is horrible. So I have 2 questions:

1. How can I get into game's files to unpack, change text and rebuild it?
2. How can I change polish voices into english voices from orginal game?
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-21T15:43:41+00:00
- Post Title: Simon the Sorcerer II - Translation

You have to find out where and how all the data you want to change is stored. [http://wiki.scummvm.org/index.php/AGOS/Formats](http://wiki.scummvm.org/index.php/AGOS/Formats) and the sourcecode of scummvm has details about the engine (AGOS) and the formats.
After extracting the files there is the next problem: If you change something the new voices and text-data differs from the original and you most likely have to rewrite an "index-file" of some kind (pointers to the right text; information about the new length of the files and so on).

PS. If you just need to correct some typos and you don't change the number of characters you can edit the text by using a hexeditor. Its stored somewhere in the SIMON2.GME. It's more or less plain text. Just search for the text you want to correct. Going this way you don't have to rebuild whole archive.
## Post #3
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2011-09-21T16:35:22+00:00
- Post Title: Simon the Sorcerer II - Translation

Thanks, buy how can I find text in that hexeditor? I can only see marks.
