## Post #1
- Username: Killermannvs
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 07, 2013 4:57 am
- Post datetime: 2013-11-09T11:27:59+00:00
- Post Title: GTA V - GXT2 - export/import (X360 & PS3)

Hi guys!

I have made my own tool which will help you to export and import gxt2 files.

Ekey has made very similar tool, but I wanted to make export and import much faster than "one by one".

It is console application, so you will need command line.
.NET framework 4.0 is needed.

Well, the usage is very easy.

Exporting:
1) Put GXT2 Tool into folder where are gxt2 files
2) Use command "exp" - to export gxt2 files in folder
3) Wait for a few seconds
4) IT'S DONE!

All gxt2 files will be exported to csv files.
Info: In csv files hashes and strings are splited by pipe "|" - don't remove it
Warning: Sometimes u can see something like this...

```
~n~I just wanted to let you know,.....
~n~Regards,
~n~The Management (Rodney)

```


If there is some string on single line without hash, just leave it there.
It is information for me, that this line need to be "connected" to previous line by CR character (check ASCI table).

Importing:
1) Put GXT2 Tool into folder where are exported csv files
2) Use command "imp" - to import csv files in folder to gxt2 files (they will get "new_" prefix, original files will not be replaced)
3) Wait for a few seconds
4) IT'S DONE!

I think this tool is very easy to use and save you a lot of time.

Unfortunately, I didn't tested imported gxt2 files in the game, so let me know if you will get any issue.

Hope you enjoy it.
[GXT2 Tool.zip](https://xentaxbackup.github.io/file/6758_GXT2 Tool.zip)
## Post #2
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2016-12-29T09:00:33+00:00
- Post Title: GTA V - GXT2 - export/import (X360 & PS3)

Pc version?
