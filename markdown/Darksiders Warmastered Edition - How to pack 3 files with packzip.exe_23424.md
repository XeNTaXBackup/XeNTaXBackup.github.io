## Post #1
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2021-02-08T18:03:51+00:00
- Post Title: Darksiders Warmastered Edition - How to pack 3 files with packzip.exe

Hello all,

I was wondering how I can pack 3 files with packzip.exe
All the three files in the same folder with the rest of the packzip files.
I used the following command and I got an error

```
packzip.exe -o 0x00001004 fonts_ru.gfx + ui_ru_f0 + ui_ru_f1 ui_ru.oppc
```


Thanks
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-08T20:32:10+00:00
- Post Title: Darksiders Warmastered Edition - How to pack 3 files with packzip.exe

You mean packzip from aluigi?
[http://aluigi.altervista.org/mytoolz/packzip.zip](http://aluigi.altervista.org/mytoolz/packzip.zip)

What is the error you are getting?
And what is the name of the game you are trying to modify?
## Post #3
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2021-02-08T22:30:53+00:00
- Post Title: Darksiders Warmastered Edition - How to pack 3 files with packzip.exe

Hey ikskoks,

Q\ You mean packzip from aluigi?
http://aluigi.altervista.org/mytoolz/packzip.zip
A\Yes.

Q\What is the error you are getting?
A\ 
```

Error: Permission denied
```

Q\ And what is the name of the game you are trying to modify?
A\ Darksiders Warmastered Edition

*I can pack one single file but not 2 or more.
I just need the correct command to pack many files.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-09T10:47:37+00:00
- Post Title: Darksiders Warmastered Edition - How to pack 3 files with packzip.exe

You can just execute this one working command 3 times:

```
packzip.exe -o 0x00002004 in_file_2 out_file
packzip.exe -o 0x00003004 in_file_3 out_file
```


Or make a BAT script to automate that, something like this [https://github.com/bartlomiejduda/Tools ... FOLDER.BAT](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/DO%20FOR%20ALL%20FILES%20IN%20FOLDER.BAT)

I have checked the source code real quick and I didn't see any option for inserting more than one file.
## Post #5
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2021-02-10T13:50:54+00:00
- Post Title: Darksiders Warmastered Edition - How to pack 3 files with packzip.exe

Hey,
Thank you for your answer.
I merged the files in stages and the game did not recognize the font file.
Someone sent the file to me in a compressed form and the game recognized it. I asked him several times about the method and he didn't tell me.
