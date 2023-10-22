## Post #1
- Username: Infernux
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 18, 2009 5:00 pm
- Post datetime: 2009-02-18T23:12:30+00:00
- Post Title: Shadow of the Colossus Archive (.DAT)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Infernux
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 18, 2009 5:00 pm
- Post datetime: 2009-02-24T10:59:32+00:00
- Post Title: Shadow of the Colossus Archive (.DAT)

Well, having no luck searching for more tools, I have decided to see if I can find a way to reverse engineer the archive format.  I do have a friend who has done reverse engineering in hex and I have read the entire Intro to reverse engineering a GRAF pdf, so I think I have an ok base.

And while I still do not know much about the .dat format itself, I have found out something about the .xff2 files within it.  the .Xff2 files seem to consist of scripting for the game (i think) as there are xff2 files that are not in the main game resource located on the CD.  Anyway, I have found out that the unsigned long at offset 0x00000014 of the xff2 file is the size of the xff2 file.  I think i can use this to outline where the xff2 files are inside the giant .dat file.

problem is, I am still no closer to locating a directory within the archive.  If anyone is willing to help, or has a copy of the game and knows more about this than I do, please reply.
## Post #3
- Username: moosotc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 28, 2009 1:29 pm
- Post datetime: 2009-04-28T07:10:09+00:00
- Post Title: Shadow of the Colossus Archive (.DAT)

The code to read/extract stuff from SotC is available at: [http://repo.or.cz/w/dormin.git](http://repo.or.cz/w/dormin.git)

There are dumper utilities in Python which should be pretty easy to follow plus the character animation player written in OCaml/C and a bit of documentation. You can see the result of running the player here: [http://video.google.com/videoplay?docid ... 6505311170](http://video.google.com/videoplay?docid=6489317706505311170)
## Post #4
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-04-05T00:47:52+00:00
- Post Title: Shadow of the Colossus Archive (.DAT)

No news for extract the models (.nmo files) from this game?
## Post #5
- Username: junior52999
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 26, 2011 1:53 am
- Post datetime: 2011-07-25T18:09:13+00:00
- Post Title: Shadow of the Colossus Archive (.DAT)

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-07-26T13:12:14+00:00
- Post Title: Shadow of the Colossus Archive (.DAT)

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2011-11-13T10:37:21+00:00
- Post Title: Shadow of the Colossus Archive (.DAT)

The contents of this post was deleted because of possible forum rules violation.
[japanstudio_720.rar](https://xentaxbackup.github.io/file/4838_japanstudio_720.rar)
## Post #8
- Username: thedarkknight
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 25, 2012 8:14 am
- Post datetime: 2012-01-25T21:58:28+00:00
- Post Title: Shadow of the Colossus Archive (.DAT)

hi, i managed to extract the models but i need help with the importer .
[A.rar](https://xentaxbackup.github.io/file/5015_A.rar)
