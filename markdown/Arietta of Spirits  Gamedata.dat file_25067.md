## Post #1
- Username: ZamanYolcusu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 19, 2022 8:34 am
- Post datetime: 2022-02-19T00:48:31+00:00
- Post Title: Arietta of Spirits  Gamedata.dat file

Hi everyone. I am a random dude who just wants to make a translation for Arietta of Spirits. Also, I am new to modding and other stuff that requires technical knowledge. For that reason i couldnt open the gamedata.dat file. Is there anyone who can give me an idea or just show me the golden way of modding and opening game files ?

Thanks, Have a good day.
[334.PNG](https://xentaxbackup.github.io/file/21809_334.PNG)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-19T16:48:17+00:00
- Post Title: Arietta of Spirits  Gamedata.dat file

Try this script [https://aluigi.altervista.org/bms/yoyogames.bms](https://aluigi.altervista.org/bms/yoyogames.bms)
Use it with quickbms [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)


There is no one simple way to open and mod game files.
You can read more here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)


By the way, text seems to be stored in file "uitexts.json", not in "gamedata.dat".
You can open this file with Notepad++ or load it in some CAT tool like OmegaT.


Edit: Try this as well [https://github.com/krzys-h/UndertaleModTool](https://github.com/krzys-h/UndertaleModTool)
And check this article for reference [http://wiki.xentax.com/index.php/YoYo_Games_DAT_WIN](http://wiki.xentax.com/index.php/YoYo_Games_DAT_WIN)
## Post #3
- Username: ZamanYolcusu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 19, 2022 8:34 am
- Post datetime: 2022-02-20T00:53:09+00:00
- Post Title: Arietta of Spirits  Gamedata.dat file

Thanks for your advice my friend. I tried everything you said, but unfortunately none of them worked for me. Also i don't know why, but quickbms found 0 zero files and undertale modding tool simply didnt work. It just shows a black cmd screen and closes immediately. Anyway , thanks for your help again.
Have a good day.
[3333333.PNG](https://xentaxbackup.github.io/file/21821_3333333.PNG)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-20T11:34:40+00:00
- Post Title: Arietta of Spirits  Gamedata.dat file

You don't need to open "gamedata.bin" for translation, because all the fonts are in "data.win" file and text is in "uitexts.json".
Also gamedata.bin doesn't seem to contain anything important for translation. It's size is only 724 KB, while data.win's size is 167 MB.

You should be fine using UndertaleModTool on data.win file as it worked for me wothout any issues.
## Post #5
- Username: grsl12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 18, 2022 11:24 pm
- Post datetime: 2023-05-21T08:56:51+00:00
- Post Title: Arietta of Spirits  Gamedata.dat file

> Reply from ikskoks ↑Sun Feb 20, 2022 7:34 pm at Sun Feb 20, 2022 7:34 pm
>
> 
You don't need to open "gamedata.bin" for translation, because all the fonts are in "data.win" file and text is in "uitexts.json".
Also gamedata.bin doesn't seem to contain anything important for translation. It's size is only 724 KB, while data.win's size is 167 MB.

You should be fine using UndertaleModTool on data.win file as it worked for me wothout any issues.

I found this post while searching the internet. Honestly, I was looking for the language files like your friend said. The Ui text file contains texts about the interface of the game. I couldn't find the in-game dialogs. I took a cursory look at the language files with the Undertale tool, but I didn't come across it either. Or the language file escaped my attention. I don't know how to find the dialog files.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-05-21T12:22:51+00:00
- Post Title: Arietta of Spirits  Gamedata.dat file

@grsl12, try total commander method [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
## Post #7
- Username: grsl12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 18, 2022 11:24 pm
- Post datetime: 2023-05-21T14:53:39+00:00
- Post Title: Arietta of Spirits  Gamedata.dat file

> Reply from ikskoks ↑Sun May 21, 2023 8:22 pm at Sun May 21, 2023 8:22 pm
>
> 
@grsl12, try total commander method https://ikskoks.pl/searching-text-strin ... commander/

I used that method but there is no indication of which file the dialogs are in. I don't know if it is in the exe or in data.win
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-05-21T21:52:06+00:00
- Post Title: Arietta of Spirits  Gamedata.dat file

So text must be compressed or encrypted. You need to reverse engineer the game to get it.
But it may be easier to just contact authors and see if they want you to translate the game officially.
