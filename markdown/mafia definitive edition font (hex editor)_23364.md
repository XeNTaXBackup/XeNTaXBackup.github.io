## Post #1
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-01-27T08:31:35+00:00
- Post Title: mafia definitive edition font (hex editor)

Hi 
I managed to extract the SUBtitle script. And translate it into my own language.
But I got a problem.The game doesn't support my language and I need to add my fonts to the game.
Now, my problem is I don't know how to make font and add it to the game.
I'd like if you could teach me how to make fonts, in my own language. And add it to the game.
I'd be so grateful if you would answer me.
## Post #2
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-01-27T08:46:18+00:00
- Post Title: mafia definitive edition font (hex editor)

this is my problem image: [https://drive.google.com/file/d/16iCPF0 ... sp=sharing](https://drive.google.com/file/d/16iCPF0Csm5iugZJFQ0Hn6af0L_237rnE/view?usp=sharing)
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-27T21:02:08+00:00
- Post Title: mafia definitive edition font (hex editor)

You need to share public link to your samples, because access is denied and we can't download them.
## Post #4
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-01-29T14:46:49+00:00
- Post Title: mafia definitive edition font (hex editor)

> Reply from ikskoks ↑Thu Jan 28, 2021 5:02 am at Thu Jan 28, 2021 5:02 am
>
> 
You need to share public link to your samples, because access is denied and we can't download them.
[photo_2021-01-28_21-48-20.jpg](https://xentaxbackup.github.io/file/19423_photo_2021-01-28_21-48-20.jpg)
## Post #5
- Username: farshidmj
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 02, 2021 3:12 am
- Post datetime: 2021-03-03T12:37:45+00:00
- Post Title: mafia definitive edition font (hex editor)

Hello
I have exactly the same problem, what should be done?
The letters in Arabic and Persian are shown as squares
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-03T13:23:00+00:00
- Post Title: mafia definitive edition font (hex editor)

> I have exactly the same problem, what should be done?
>
> The letters in Arabic and Persian are shown as squares

So the issue here is that characters used in your language are not defined in the font.
There are two ways to deal with this.
1. Add mapping for new characters to the font
2. Replace existing (unused) characters in the font

I would recommend second option as it is easier to do.
First you need to figure out what type of font is used in the game.
If it is TTF or DDS, then editing is easy and there are some tutorials for that like for example [https://ikskoks.pl/poradnik-8-edycja-cz ... -oraz-dds/](https://ikskoks.pl/poradnik-8-edycja-czcionek-w-formacie-ttf-oraz-dds/)

If font is in some custom format, then you have to do some reverse engineering work first.
Here are some tutorials for that [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #7
- Username: farshidmj
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 02, 2021 3:12 am
- Post datetime: 2021-03-03T14:41:20+00:00
- Post Title: mafia definitive edition font (hex editor)

Thanks for your reply. If I am not mistaken, this should be the file

[https://files.fm/u/vju4fsgkd](https://files.fm/u/vju4fsgkd)

The file is in gfx format
## Post #8
- Username: farshidmj
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 02, 2021 3:12 am
- Post datetime: 2021-03-03T14:51:04+00:00
- Post Title: mafia definitive edition font (hex editor)

file dds
[https://files.fm/f/hjw3gmrze](https://files.fm/f/hjw3gmrze)
## Post #9
- Username: farshidmj
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 02, 2021 3:12 am
- Post datetime: 2021-03-03T15:23:51+00:00
- Post Title: mafia definitive edition font (hex editor)

Hello again
I got this file and it is possible to edit it
Now to add Persian and Arabic letters, I have to delete something from the dds file and replace the Persian letters
## Post #10
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-03T15:30:37+00:00
- Post Title: mafia definitive edition font (hex editor)

> I have to delete something from the dds file and replace the Persian letters
Yeah, exactly. You have to also replace those letters in text files.
You can do it automatically with some program like Notepad++ or similar

As for GFX or SWF files, you can use JPEXS Free Flash Decompiler for editing.
## Post #11
- Username: farshidmj
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 02, 2021 3:12 am
- Post datetime: 2021-03-03T16:52:21+00:00
- Post Title: mafia definitive edition font (hex editor)

Regarding the gfx file, I could not open it with a program
You may test
## Post #12
- Username: farshidmj
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 02, 2021 3:12 am
- Post datetime: 2021-03-03T17:31:01+00:00
- Post Title: mafia definitive edition font (hex editor)

Your answer was wonderful, I concluded, Morsi
