## Post #1
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-06-03T14:35:54+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

Hi,

I would like to extract the .d0xx files in this game. I uploaded two files, english.d000 (there are 4 in the game: d000, d001, etc) and resources.d000 (there are 19). I used filecutter and it's the first time I use this one. 

It is possible to make a bms script or something like that? I think files are under Phyton but i'm not totally sure.

Here is the files:

[english.d000](http://www.megaupload.com/?d=33B0918C)
[resources.d000](http://www.megaupload.com/?d=GK58A3PT)

Best regards.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-03T16:44:04+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

The game uses a free database engine, named SQLITE.
(You can find a file, named SQLITE3.DLL in the <Simon5installDir>\BIN\ folder)

The information files are:
ENGLISH.META for the english.d??? files,
(or GERMAN.META for the german.d??? files, if someone uses the german version of the game)
and RESOURCES.META for the resources.d??? files.

You can find some good sqlite database editor programs, for example:
SQLite Database Browser, [http://sqlitebrowser.sourceforge.net/](http://sqlitebrowser.sourceforge.net/)

Some time ago I wrote a program, that extracts the files from the game, named EVERLIGHT, which uses the same engine.
I try to find that program, and will upload soon. (My proggy also calls some of the SQLite3.dll functions)

Good news, if you want to modify some files, for example you translate it to your language,
you don't have to put the new files into the big archives, you can copy your files to the game's
appropriate directory.

Oh yes, the game's texts can be found in in the english.meta, named: text_db, and that is also inSQLite3
database format.

Updated: Here is the unpacker.
Important! If the program not works, copy the SQLite3.dll to the unpacker prog's directory.
## Post #3
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-06-03T18:18:44+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

I have already tried to extract the files and work perfectly!!   

Thanks a lot bacter!

Best Regards.
## Post #4
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2010-06-04T09:53:49+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

Not quite in time, but here's my tool for managing Simon 5 files.
You also can pack them back, but i didn't test them very well, so any comment about it will be appreciated. 
[Simon_the_Sorcerer_5_meta_file_manager_v1.0.zip](https://xentaxbackup.github.io/file/3107_Simon_the_Sorcerer_5_meta_file_manager_v1.0.zip)
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-07-29T12:47:04+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

> Reply from bacter
>
> The game uses a free database engine, named SQLITE.
(You can find a file, named SQLITE3.DLL in the <Simon5installDir>\BIN\ folder)

The information files are:
ENGLISH.META for the english.d??? files,
(or GERMAN.META for the german.d??? files, if someone uses the german version of the game)
and RESOURCES.META for the resources.d??? files.

You can find some good sqlite database editor programs, for example:
SQLite Database Browser, http://sqlitebrowser.sourceforge.net/

Some time ago I wrote a program, that extracts the files from the game, named EVERLIGHT, which uses the same engine.
I try to find that program, and will upload soon. (My proggy also calls some of the SQLite3.dll functions)

Good news, if you want to modify some files, for example you translate it to your language,
you don't have to put the new files into the big archives, you can copy your files to the game's
appropriate directory.

Oh yes, the game's texts can be found in in the english.meta, named: text_db, and that is also inSQLite3
database format.

Updated: Here is the unpacker.
Important! If the program not works, copy the SQLite3.dll to the unpacker prog's directory.

Hi,bacter

Can you make a command line version of this tool? Very thanks.
I want to make a language path of this game. 
so need unpack it in  command line.
## Post #6
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-07-29T13:02:39+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

I found a way ,just delete text_db's records in english.meta,the game will read it from english folder,so no need command line tool to pack it again. Thanks.
## Post #7
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-07-30T00:12:27+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

You don't need to remove anything. Only put text_db and credits files in the root folder and it'll work.

For the images put gui_lang folder in the root directoy as well.

Regards.
## Post #8
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-08-01T23:54:13+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

Sheen ,thanks for useful infomation!
## Post #9
- Username: jacquel
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 29, 2011 5:21 pm
- Post datetime: 2011-06-06T14:41:01+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

hello bacter
i need to extract Everlight_meta.
hello
i try with xp
i can see the extract button, but there are message error at the top of blue scream when t try with the demo game
cheers
## Post #10
- Username: dupa4488
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 28, 2012 1:55 pm
- Post datetime: 2012-03-29T06:19:15+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

I need some useful tool, to extract/edit text files from text_db.

Someone know something about such tool?
## Post #11
- Username: djokay
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jun 05, 2010 2:44 pm
- Post datetime: 2012-03-29T14:29:32+00:00
- Post Title: Simon The Sorcerer 5 - .d0xx files

You can use if you you have Mozilla Firefox, the Web application [SQLiteManager](http://www.sqlitemanager.org/en/)
