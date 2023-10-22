## Post #1
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2013-07-01T10:05:43+00:00
- Post Title: [REQ] GameMaker 8+/Valdis Story archive [*.win]

```
46 4F 52 4D 6C 3E 97 06  47 45 4E 38 30 02 00 00   FORMl>— GEN80   
```


Simple "blabla.win" file that comes with game "Valdis Story: Abyssal City". I know that the game is made with Game Maker (version 8 and above) so I assume the game data is packed as well with its tools.

You can grab the game demo here:
[http://www.mediafire.com/download/ecbvn ... C_Demo.exe](http://www.mediafire.com/download/ecbvn6x2ahif3cy/Valdis_Story_AC_Demo.exe)
[http://199.91.153.74/la0o7kl4ip1g/ecbvn ... C+Demo.exe](http://199.91.153.74/la0o7kl4ip1g/ecbvn6x2ahif3cy/Valdis+Story+AC+Demo.exe)

Or the archive itself here:
[http://www.sendspace.com/file/lmzo74](http://www.sendspace.com/file/lmzo74)

It does not looks like the file is encrypted, HyperRipper can extract png/wav content. So I assume a proper parsing and offset for quickBMS can do the job.

Anyone up to the task? I would be grateful.
## Post #2
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2013-07-03T11:57:38+00:00
- Post Title: [REQ] GameMaker 8+/Valdis Story archive [*.win]

So I assume this is more complicated than I thought or nobody actually care enough?
## Post #3
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2013-09-14T17:34:40+00:00
- Post Title: [REQ] GameMaker 8+/Valdis Story archive [*.win]

I tried GameMaker 8.1 Decompiler on it to no avail.
Then I found out it was actually compiled with GameMaker: Studio, which is the newest "model" (currently on v1.2).
This is just my insight, I don't have the technical skills to help out.
## Post #4
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2013-09-16T01:30:35+00:00
- Post Title: [REQ] GameMaker 8+/Valdis Story archive [*.win]

> Reply from ner0
>
> I tried GameMaker 8.1 Decompiler on it to no avail.
Then I found out it was actually compiled with GameMaker: Studio, which is the newest "model" (currently on v1.2).
This is just my insight, I don't have the technical skills to help out.
There is no decompiler for Studio version?
## Post #5
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2013-09-16T07:33:56+00:00
- Post Title: [REQ] GameMaker 8+/Valdis Story archive [*.win]

No, at this time there doesn't seem to be one.
## Post #6
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-10-10T06:23:27+00:00
- Post Title: [REQ] GameMaker 8+/Valdis Story archive [*.win]

Might as well post what I know here.
The format is actually fairly straight forward, it has a magic: "FORM", followed by the file length - 8, after that you have 21 sections, one for each type of data. Sections follow a basic structure as well, it has a 4 byte magic, followed by the length of the section data. The only section I've really cracked is the STRG section, which contains all the strings used by the project (including variable, constant, and function names)

The best part is: they have absolutely NO protection, and can be freely edited, knowledge of the GM8 bytecode is a must though, and since that's not documented it'll have to be reversed.
## Post #7
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-10T10:35:17+00:00
- Post Title: [REQ] GameMaker 8+/Valdis Story archive [*.win]

Quick note: the structure of the file uses standard IFF layout.
