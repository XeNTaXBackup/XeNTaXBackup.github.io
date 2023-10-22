## Post #1
- Username: yura04kizel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 15, 2023 5:19 am
- Post datetime: 2023-07-14T21:33:23+00:00
- Post Title: [Request] Game files from several Russian adventure games

Hi there. I understand that Resources Game Viewer program exists, but I'd like to see QuickBMS scripts that decode game files from these following graphic adventure games made in Russia: 
- Pilot Brothers series (Братья Пилоты) [*.exe, *.pak] 
- Leopold the Cat (Дача кота Леопольда или Особенности мышиной охоты) [*.bas, *.* (files without format)]
- GAG: The Imp*tent Mystery (ГЭГ: Отвязное Приключение) [*.cdf] 
- Red Comrades series (Петька и Василий Иванович) [*.str] 
- Shtyrlitz series (Штырлиц: Операция "Бюст", Штырлиц 2: Танго в Пампасах, Штырлиц 3: Агент СССР, ШтырлиТц: Открытие Америки, Штырлиц 4: Матрица - Шаг до Гибели) [*.res, *.rss]
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-15T06:02:11+00:00
- Post Title: [Request] Game files from several Russian adventure games

Please upload sample files to hosting sites like mega.nz or google drive and then share a public link here.
## Post #3
- Username: yura04kizel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 15, 2023 5:19 am
- Post datetime: 2023-07-15T14:45:48+00:00
- Post Title: [Request] Game files from several Russian adventure games

Sorry for being late, but here's the sample files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1wOUS7BDD7001aINcyI01B42ezHu8O7C6?usp=sharing)

Note that Pilot Brothers 1 & 2 files are compiled in .exe file, not in .pak
## Post #4
- Username: yura04kizel
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-15T21:35:43+00:00
- Post Title: [Request] Game files from several Russian adventure games

Here is the result of my research of "Red Comrades Save The Galaxy" SFX format:

quickBMS script --> [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Red%20Comrades%20Save%20The%20Galaxy/Red_Comrades_Save_The_Galaxy_SFX_script.bms)
File Format --> [http://wiki.xentax.com/index.php/Red_Co ... Galaxy_SFX](http://wiki.xentax.com/index.php/Red_Comrades_Save_The_Galaxy_SFX)
## Post #5
- Username: yura04kizel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 15, 2023 5:19 am
- Post datetime: 2023-07-15T23:54:20+00:00
- Post Title: [Request] Game files from several Russian adventure games

Excellent. This script actually works with all *.str format files in both Red Comrades 1 (Петька и Василий Иванович Спасают Галактику) and Red Comrades 2 (Петька и Василий Иванович 2: Судный День) from 1998-1999. 

Now I'm interested in QuickBMS scripts that decode *.res format files from Shtyrlitz (Штырлиц) games.
## Post #6
- Username: yura04kizel
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-16T08:04:10+00:00
- Post Title: [Request] Game files from several Russian adventure games

Script for GAME.RES file from "ShtyrliTz Discovery of America":
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/ShtyrliTz%20Discovery%20of%20America/ShtyrliTz_Discovery_of_America_RES_script.bms)

Entries are headerless, so you still would need a custom tool to convert it to usable files.
## Post #7
- Username: yura04kizel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 15, 2023 5:19 am
- Post datetime: 2023-07-16T08:45:33+00:00
- Post Title: [Request] Game files from several Russian adventure games

The script of course works with GAME.RES, but it doesn't work with SOUNDS.RES. Can I see scripts for Shtyrlitz 1, 2 and 3 then? 

Also, according to Resources Game Viewer, Shtyrlitz 1 and 2 files (*.res format) are encoded in the same algorithm, while Shtyrlitz 3 files (also *.res format) are encoded in completely different algorithm rather than Shtyrlitz 1 and 2.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-16T11:29:49+00:00
- Post Title: [Request] Game files from several Russian adventure games

> Can I see scripts for Shtyrlitz 1, 2 and 3 then?

I didn't find any index structures in those archives and also there is no documentation online for those formats, so I think I'll leave analyzing them to someone else.
