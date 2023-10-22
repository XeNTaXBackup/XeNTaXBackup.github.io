## Post #1
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-06T20:03:18+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

in the game the text is in a res.pak file, which can be unpacked with a script from another game of the company, but it shows an error in one place and cannot be put back.
I attach the script.
What could be the problem?
The res.pak file itself is uploaded to [https://mega.nz/fm/Au4QQJgI](https://mega.nz/fm/Au4QQJgI).


 Script.zip
(469 Bytes) Downloaded 28 times
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-07T19:27:25+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

This link you provided for PAK file is not working. You need to share a public link here.
## Post #3
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-10T11:03:54+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

[https://mega.nz/file/E6wWjKQQ](https://mega.nz/file/E6wWjKQQ)
## Post #4
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-10T11:05:17+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

QbjHvueuxqamnvuHvIiWVcHIlP6IWE0J0kNOnmGGh8s
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-10T16:26:14+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

The script doesn't support "type 2" entries and that's why it's failing. 
I have added error handling to the script, so now at least you will be able to unpack and pack properly around 43% of the content.
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Shiro%20Games/Shiro_Games_PAK_script.bms)

But still - someone needs to figure out how to handle "type 2" entries.
## Post #6
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-19T07:14:56+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

sorry, didn't notice. will try it and thanks.
## Post #7
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-19T11:07:28+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

> Reply from ikskoks ↑Fri Mar 11, 2022 12:26 am at Fri Mar 11, 2022 12:26 am
>
> 
The script doesn't support "type 2" entries and that's why it's failing. 
I have added error handling to the script, so now at least you will be able to unpack and pack properly around 43% of the content.
https://github.com/bartlomiejduda/Tools ... script.bms

But still - someone needs to figure out how to handle "type 2" entries.

the thing is that the original northgard script unpacks the res.pak file 100% of the time, but gives an error when reimport it.
it tells you that there is a problem with the "2 types" and doesn't even start.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-19T11:41:23+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

Are you using quickbms_4gb_files.exe for extract and import? Original quickbms.exe won't work for such big archive.
## Post #9
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-19T16:34:43+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

yes.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-19T18:25:42+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

I think I wasn't precise enough with my question, here is the new one --> Are you sure you're using Shiro_Games_PAK_script.bms from my repository with quickbms_4gb_files.exe?  And you're using newest version of quickbms which is 0.11? If yes, then what is the error message? For me extraction went fine, I didn't try to reimport.

Maybe you have some issue with privileges or free disk space?
## Post #11
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-19T20:48:01+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

> Reply from ikskoks ↑Sat Mar 19, 2022 7:41 pm at Sat Mar 19, 2022 7:41 pm
>
> 
Are you using quickbms_4gb_files.exe for extract and import? Original quickbms.exe won't work for such big archive.

I can import the res.pak file, it has a 0000000000000f48.dat file of 2.7 GB, which contains the texts.
I can't reimport back.
## Post #12
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-19T20:51:17+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

the error message: 

- error in src\extra\xalloc.c line 618: xdbg_malloc()

Error: memory allocation problem
## Post #13
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-19T21:02:42+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

i was stupid, downloaded the wrong script. the import went through, so far so good, thanks. hope reimport will be good
## Post #14
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-19T21:08:45+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

or not, because the text .dat file was not imported
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-19T22:28:52+00:00
- Post Title: Wartales (by Shiro Games) - PAK archive

I think you're doing something wrong here... You shouldn't have "0000000000000f48.dat" file, because this file occurred only after extracting data with original script which wasn't aware of "type 2" entries (and that's why the filename is incorrect - it's an error). 

If you delete everything you have extracted so far, then use my updated script with quickbms_4gb_files.exe and then extract once again to different directory, everything should go well and all filenames should have proper names. Then you may try to reimport this and quickbms should allow this with standard reimport option, but as I said earlier - without proper support for "type 2" entries, you won't get far with this... 

That's all help I can offer for now.
## Post #16
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-20T07:09:51+00:00
- Post Title: Re: Wartales (by Shiro Games) - PAK archive

i see, but the error is not in the .dat, but in another one. the text is in the .dat, i could look at it with goggl, and i can edit it somehow, but i can't put it back. the new script doesn't have any text in it, so i can't work with it.
## Post #17
- Username: tomba
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 07, 2022 3:48 am
- Post datetime: 2022-03-24T14:56:26+00:00
- Post Title: Re: Wartales (by Shiro Games) - PAK archive

thanks for all your help, the new update has improved the translatability.
## Post #18
- Username: WannaBe
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 14, 2023 3:55 am
- Post datetime: 2023-05-13T20:27:49+00:00
- Post Title: Re: Wartales (by Shiro Games) - PAK archive

Hello, I'm interested in translating this game. To what extent have you made it? I'm looking for a way to mod this game.
## Post #19
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-06-03T10:34:56+00:00
- Post Title: Re: Wartales (by Shiro Games) - PAK archive

Wartales (Final) - Translating Tutorial by .:i2k:.
~~~~~~~~~~~~~~~~~~~~~~~~~
2023.04.16

FINAL Game's premiere: 2023
Engine version: ?
Game version: v1.0.25233+

Statistics/Statisztika:
~~~~~~~~~~~~
Words/Szó: ~140000
Lines/Sor: ~13700
Characters/Karakter: ~819000

PREREQUISITES - DOWNLOADS / Követelmények - Letöltések:
---------------------------------------
* - QuickBMS generic files extractor and reimporter 0.12 --- [https://aluigi.altervista.org/papers/quickbms.zip](https://aluigi.altervista.org/papers/quickbms.zip)
* - BMS file: Shiro_Games_PAK_script.bms --- [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Shiro%20Games/Shiro_Games_PAK_script.bms)
or [https://www.zenhax.com/download/file.ph ... f7c7075425](https://www.zenhax.com/download/file.php?id=12223&sid=eb58b690f3b30f11854043f7c7075425)
* - Notepad++ --- [https://notepad-plus-plus.org/downloads/](https://notepad-plus-plus.org/downloads/)
* - Wartales "res.pak" (~375 MB)

~~~~~~~~~~~~LET'S START THE WORK!~~~~~~~~~~~~


01 - EXTRACTION / Kitömörítés
~~~~~~~~~~~~
- Quick BMS + Shiro_Games_PAK_script.bms ->- "res.pak" file ->- EXTRACT

02 - TRANSLATING / FORDÍTÁS
~~~~~~~~~~~~
- With Notepad++ in <your extracted location>/lang folder carefully translate
- export_en.xml
- texts_en.xml
files!

- Notepad++-al a <kitömörítési könyvtárad>/lang mappában figyelmesen fordítsd a
- export_en.xml
- texts_en.xml
fájlokat!

03 - REPACKING / Visszacsomagolás
~~~~~~~~~~~~
- reimport2_4gb_files.bat + Shiro_Games_PAK_script.bms ->- "res.pak" file ->- <your extracted location> ->- Save
Copy the updated "res.pak" to your game's root and replace!

A fenti lépéssel frissített "res.pak" fájlt másold a játék gyökerébe és írd felül a már ott lévő fájlt!

04 - TESTING / TESZTELÉS

~~~~~~~~~~~~DONE!~~~~~~~~~~~~

PICTURES from Hungarian translation/KÉPEK a magyar fordításból
## Post #20
- Username: michanlew
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 29, 2012 8:21 am
- Post datetime: 2023-09-26T18:12:57+00:00
- Post Title: Re: Wartales (by Shiro Games) - PAK archive

Good afternoon. Please tell me how to extract assets.pak completely? The script retrieves only part of the data. Thank you.
## Post #21
- Username: michanlew
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 29, 2012 8:21 am
- Post datetime: 2023-09-26T18:18:47+00:00
- Post Title: Re: Wartales (by Shiro Games) - PAK archive

> Reply from michanlew ↑Wed Sep 27, 2023 2:12 am at Wed Sep 27, 2023 2:12 am
>
> 
Good afternoon. Please tell me how to extract assets.pak completely? The script retrieves only part of the data. Thank you.

I'm withdrawing the question. I found the required script.
