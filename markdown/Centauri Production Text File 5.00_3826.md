## Post #1
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2009-11-02T19:44:36+00:00
- Post Title: Centauri Production Text File 5.00

Here's something from me.
It's a tool that can convert centauri's *.DB/DBS to readable INI and then convert the ini back to DB/DBS
[Centauri_Production_Text_File_5.00_converter_v1.0.zip](https://xentaxbackup.github.io/file/2495_Centauri_Production_Text_File_5.00_converter_v1.0.zip)
## Post #2
- Username: djokay
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jun 05, 2010 2:44 pm
- Post datetime: 2010-11-11T07:25:31+00:00
- Post Title: Centauri Production Text File 5.00

Hello
I tried your converter with the file " texts.txt " of the game Fairy tale.
I modified the extension txt in DB and tried to convert.
There was a crash because it's a file created with Centauri Production Text 2.1.
For information, despite the crash, I managed to create an ini file but there is no text inside.
Is it possible to create a converter for that file type?
Thank you
[fairy.rar](https://xentaxbackup.github.io/file/3589_fairy.rar)
## Post #3
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2010-11-14T18:50:00+00:00
- Post Title: Centauri Production Text File 5.00

> Reply from djokay
>
> Hello
I tried your converter with the file " texts.txt " of the game Fairy tale.
I modified the extension txt in DB and tried to convert.
There was a crash because it's a file created with Centauri Production Text 2.1.
For information, despite the crash, I managed to create an ini file but there is no text inside.
Is it possible to create a converter for that file type?
Thank you
I'll try, but that will be done tomorrow.
## Post #4
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2011-01-05T20:46:49+00:00
- Post Title: Centauri Production Text File 5.00

I tried to convert a Numen: Contest of Heroes .db to ini, which went fine. But when I want to convert it back to .db, it is really slow, I mean really. I literally waited half an hour, then stopped it.
I've attached the original .db file.
[TEXTS_EN.7z](https://xentaxbackup.github.io/file/3774_TEXTS_EN.7z)
## Post #5
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2011-01-08T16:28:22+00:00
- Post Title: Centauri Production Text File 5.00

> Reply from lostprophet
>
> I tried to convert a Numen: Contest of Heroes .db to ini, which went fine. But when I want to convert it back to .db, it is really slow, I mean really. I literally waited half an hour, then stopped it.
I've attached the original .db file.
No wonder, i've tested it only with Memento Mori files.

Edit:
Guess i've managed to find some kind of a workaround...
Open your converted .ini and modify these lines from:

```
misc3size=0
misc4size=0
```

to:

```
misc3size=1
misc4size=1
```


then scroll at the very bottom of the file and add these three entries:

```
id=0
t1=0
t2=0
str1=""
str2=""
str3=""

[MISC3_0]
id=0
t1=0
t2=0
str1=""
str2=""
str3=""

[MISC4_0]
id=0
t1=0
t2=0
str1=""
str2=""
str3=""
```


Basically, seems your game doesn't use misc 2, 3 and 4 data and my app got some nasty dead loop that i'm way too lazy to fix. It took about 3 minutes to convert the ini back to DB and then stop as expected. (Hope it works too ?)

Note to self: don't use ini's for that large files anymore.
## Post #6
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2011-01-09T13:27:30+00:00
- Post Title: Centauri Production Text File 5.00

For the "Pound of Ground" game, it works flawlessly, only Numen's file had some problem with it.

The workaround helped, works perfectly, thank you very much!:)
